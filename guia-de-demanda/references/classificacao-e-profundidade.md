# Classificação e profundidade

Última revisão: 2026-10-29 (proposta inicial, inspirada em um processo de design orquestrado por tipo e risco; calibre com o uso).

Use este arquivo na etapa 3 do fluxo. Duas perguntas diferentes, nesta ordem:

1. **Que trabalho é este?** É o **tipo**. Define o roteiro (`roteiros-por-tipo.md`) e o que a demanda entrega.
2. **Quanto rigor ele merece?** É a **profundidade**. Define quanta checagem, validação e handoff.

Confundir as duas faz um ajuste de rótulo virar projeto, ou uma tela nova de módulo ser tratada como retoque.

## Tipos (design e produto)

| Tipo | A demanda pergunta | Roteiro |
|---|---|---|
| **FEATURE** | Como deve ser algo que ainda não existe? | 1 (e 9 se for prototipar no Claude) |
| **EVOLUÇÃO** | Como mudar o comportamento de algo que já existe? | 1 |
| **PROTOTIPAÇÃO** | Como isso deve parecer e se comportar, a partir de requisito já fechado por terceiro? | 1 (e 9) |
| **AJUSTE** | Como corrigir a superfície (texto, ícone, cor, espaçamento) sem mudar o que o usuário consegue fazer? | 2 |
| **CORREÇÃO** | O que veio de teste está errado no desenho ou no comportamento? | 2 |
| **COMPONENTE DS** | Falta ou precisa mudar um componente, token ou spec do Design System? | 3 |
| **REQUISITOS** | Falta escrever histórias, regras ou critérios para poder desenhar? | 4 |
| **ORGANIZAÇÃO** | É preciso estruturar cards ou pendências no Jira? | 7 |
| **ACOMPANHAMENTO** | Acompanhar implementação, teste ou fechamento? | 6 |
| **SEM CARD** | A demanda ainda nem existe no Jira? | 8 |
| **NÃO É DEMANDA** | Dúvida que as specs ou o contexto respondem, ou defeito de implementação | Responder, ou encaminhar como Problema ao dev |

Handoff (roteiro 5) e validação do design não são tipos: são etapas que quase toda demanda de design percorre.

## Árvore de decisão

Percorra na ordem. A primeira resposta afirmativa decide.

1. É uma dúvida que as specs ou o perfil do contexto respondem, sem trabalho de design? → **NÃO É DEMANDA**. Responda.
2. A tela implementada diverge do que foi especificado ou desenhado? → **NÃO É DEMANDA de design**: é defeito de implementação e vai ao dev como Problema (roteiro 7).
3. O trabalho é sobre componente, token ou spec do DS? → **COMPONENTE DS**.
4. O pedido é escrever histórias, regras ou critérios? → **REQUISITOS**.
5. Muda só a superfície, sem alterar o que o usuário consegue fazer? → **AJUSTE**.
6. O comportamento está conforme o especificado e mesmo assim o usuário erra? → **CORREÇÃO**, mas veja a nota abaixo.
7. Existe requisito escrito e fechado por terceiro e falta desenhar? → **PROTOTIPAÇÃO**.
8. O fluxo já existe e vai mudar de comportamento? → **EVOLUÇÃO**.
9. O fluxo não existe? → **FEATURE**.

Nota sobre o item 6: um usuário que erra mesmo com tudo conforme a spec costuma pedir pesquisa (entender o que acontece). Pesquisa ainda não faz parte desta skill. Trate como correção de design, registre a causa como HIPÓTESE e sugira a ela levar o caso a uma pesquisa quando houver espaço (`planos-futuros.md`).

## Sinais de reclassificação

O tipo declarado no card é hipótese. Quando o sinal contradiz, proponha a mudança, mostre o sinal e espere a decisão dela.

| Declarado | Sinal observado | Provável |
|---|---|---|
| PROTOTIPAÇÃO | Não há história, regra ou critério escrito por terceiro | REQUISITOS primeiro (roteiro 4), depois FEATURE |
| AJUSTE | A mudança altera o que o usuário consegue fazer, não só o que vê | EVOLUÇÃO |
| CORREÇÃO | O pedido é, na verdade, um comportamento novo | EVOLUÇÃO ou FEATURE |
| FEATURE | Ninguém sabe dizer qual problema ela resolve | Pare e converse com ela; é lacuna de requisitos (e, no futuro, de pesquisa) |
| Qualquer um | O escopo cresceu durante a demanda | Reclassifique e registre a reabertura |

Cada demanda tem **um** tipo. Se contém dois (por exemplo, "corrigir o filtro e já desenhar a tela nova"), proponha duas demandas com dependência declarada.

## Profundidade

| Nível | Quando |
|---|---|
| **LEVE** | Mudança pequena, local e fácil de desfazer |
| **PADRÃO** | Tela ou fluxo novo ou alterado, com impacto moderado |
| **PROFUNDA** | Risco alto: ação em lote, vários perfis e permissões, dados sensíveis, difícil de desfazer, muitas áreas afetadas |

**Piso por tipo** (o risco pode subir o nível, nunca descer abaixo do piso):

| Tipo | Piso |
|---|---|
| AJUSTE · CORREÇÃO · REQUISITOS · ORGANIZAÇÃO · ACOMPANHAMENTO | LEVE |
| FEATURE · EVOLUÇÃO · PROTOTIPAÇÃO · COMPONENTE DS | PADRÃO |

**Gatilhos para subir de nível** (proposta inicial; ajuste com o uso):

- ação em lote ou sobre várias unidades;
- vários perfis com permissões diferentes, ou sistema de acesso ainda indefinido;
- dados sensíveis ou de terceiros;
- ação difícil de desfazer (envio, exclusão, publicação);
- muitos módulos ou telas afetados;
- dependência de back ainda não confirmada;
- regra de negócio em aberto;
- componente do DS que será reutilizado em muitos lugares.

Nenhum gatilho: fica no piso. Um ou dois: PADRÃO. Três ou mais, ou lote/irreversível: PROFUNDA. Diga o nível e os gatilhos que o sustentam.

## O que a profundidade muda

| Etapa | LEVE | PADRÃO | PROFUNDA |
|---|---|---|---|
| Insumos | Só os bloqueantes | Matriz completa | Matriz completa, com decisões em aberto fechadas |
| Revisão | Checklist rápido | Checklist completo | Completo, em mais de uma rodada |
| Validação do design | Aprovação por comentário no card | Demonstração com registro | Mais de um validador, ou clientes, com roteiro de perguntas |
| Handoff | Delta curto | Por destinatário (front, back, QA) | Por destinatário, com passagem ao vivo e design QA pós-implementação |
| Registro da demanda | Cabeçalho e decisões | Completo | Completo, com riscos aceitos |

## Etapas puladas e etapas fora da rota

- **Fora da rota:** uma etapa que o tipo nunca previu (por exemplo, handoff de back em um ajuste só de texto). Não é pulada e não gera registro de risco.
- **Pulada:** uma etapa prevista que ela decidiu dispensar (por prazo, por exemplo). Registre o que foi pulado, o risco aceito e quem aceitou. Prazo muda o risco aceito, não o tipo nem o piso.
