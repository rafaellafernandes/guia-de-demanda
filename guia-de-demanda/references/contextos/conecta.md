# Contexto: Conecta (TCE-CE)

Última revisão: 2026-10-29. Fluxo, colunas e status conferidos no Jira em 2026-10-29 (leitura). Pessoas e convenções vêm de demandas anteriores; confirme no card antes de atribuir.

Leia este arquivo quando a demanda for do Conecta (cards `CONECTA-`). Para Figma, Design System e repositórios, leia também `design-system-tce.md`.

## Onde fica

- Site: https://tce-ce-comunicacao.atlassian.net (use esta URL como `cloudId` nas chamadas do conector).
- Projeto: **CONECTA** ("Conecta - Esteira"). Modelo Kanban, sem sprints.
- Dois boards no mesmo projeto:
  - **Projeto** (upstream, id 36): requisitos, design e documentação. Acesso: Rafaella, a analista de requisitos e quem coordena o projeto.
  - **Desenvolvimento** (downstream, id 37): desenvolvimento, integração, QA e homologação. Acesso: dev front, dev back, testes, Rafaella e a analista de requisitos.
- A conexão do Jira nesta conta está em nome da Rafaella (conferido em 2026-10-29). Confira de novo antes da primeira escrita da sessão.

## Pessoas e papéis

- Rafaella: UX/UI e pesquisa. Não desenvolve o código.
- Gabriela (Gabi): analista de requisitos e gestora do projeto. Escreve os requisitos e as histórias.
- Fabricio: dev front.
- Mardem e Renan: dev back (Renan cuida dos ajustes técnicos, como endpoints de validação das planilhas de ocorrências e destinatários).
- Rafael: testes.

Confirme no card quem é o responsável antes de atribuir. Quando não souber, deixe sem responsável e pergunte.

## Fluxo e status

14 status. **Nos dois boards, as colunas são:**

| Board | Colunas, em ordem (coluna → status quando o nome difere) |
|---|---|
| **Projeto** (36) | Backlog (vazia, é a área de backlog) → Devolvido do downstream (status **Voltar para up**) → Backlog → Requisitos → Design → Documentação → Pronto para desenvolvimento (status **Pronto para downstream**) → Concluído |
| **Desenvolvimento** (37) | Backlog (vazia) → Voltar para up → Para desenvolver (status Pronto para downstream e Para desenvolver) → Em desenvolvimento (máx. 3) → Code review → Aguardando integração front ↔ back → Em QA (máx. 2) → Homologação (máx. 2) → Concluído |

O upstream tem dois estados finais: **Pronto para downstream** (a atividade segue para o dev; é o que faz o card aparecer no board de Desenvolvimento) e **Concluído** (a atividade termina no upstream). Cards novos entram em **Requisitos**.

"Homologação" no Jira é do lado do dev, depois do QA. A validação do design (`../validacao-do-design.md`) é outra coisa.

### Cuidados do board (conferidos em 2026-10-29)

1. **O workflow é livre:** em CONECTA-144, qualquer status pode ir para qualquer outro (14 transições disponíveis). O Jira não impede pular etapas; os gates ficam com esta skill. Só um card foi testado.
2. **O status "Devolvido do downstream" não está em nenhuma coluna dos dois boards.** Um card movido para ele some dos dois. Para devolver, use **Voltar para up**, que tem coluna. Avise o time.
3. **Os dois boards escondem cards cuja versão de correção foi lançada** (filtro: versão não lançada ou sem versão). Não marque uma versão "Sprint N" como lançada enquanto houver cards abertos nela.
4. **Nomes de coluna diferentes dos status:** "Pronto para desenvolvimento" é o status Pronto para downstream; "Devolvido do downstream" (coluna) é o status Voltar para up.
5. **Concluído é o mesmo status nos dois boards.** Cards que seguem para o dev não devem ser concluídos pelo upstream.

### Onde fica a validação do design

Sem status novo: acontece dentro de **Design**. O card só passa para **Documentação** com a validação registrada em comentário. Documentação é a fase do handoff; **Pronto para downstream** é o momento da entrega. (Proposta aprovada em conversa; o Jira não impõe.)

## Tipos de card

Na criação use os nomes em português: **Épico**, **História**, **Problema** (bug), **Subtarefa**. "Tarefa" também existe, mas só como subtarefa.

- Histórias e Problemas ficam diretamente sob um Épico. Subtarefas ficam sob uma História ou um Problema.
- Em JQL o nome "Épico" deu erro de validação; prefira os ids dos tipos: Épico 10000, História 10006, Tarefa 10072, Subtarefa 10083, Problema 10084.

## Convenções de nome e etiqueta

- Épico e História: título em caixa alta com o módulo e dois-pontos, ex.: `CAMPOS DE OCORRÊNCIAS: Tooltip com a descrição dos campos`.
- Subtarefa: prefixo da área entre colchetes: `[UX/UI] ...`, `[Back] ...`, `[Front] ...`, `[Teste] ...`. Protótipo interativo: `[UX/UI] Protótipo interativo: tela ou fluxo`, com o label `prototipo-interativo`.
- Labels por área (`ux-ui`, `front`, `back`, `teste`) e por módulo ou tema. Rodadas de teste ganham um label com a data (ex.: `rodada-testes-29-10-2026`).
- Prioridade: High, Medium e Low (nomes em inglês).
- Versão de correção: "Sprint N", com início e fim na própria versão (Sprint 9: 19/10/2026 a 03/11/2026). Consulte as versões do projeto antes de usar uma. As sprints são planejadas no Miro (board "Conecta - Planning").

## Como organizar uma demanda nova

1. Um **card pai** agrupa (épico ou história, conforme o caso), com um label para filtrar.
2. Um **card filho por pendência**, com o tipo certo: Problema para o que está errado, História para o que é novo.
3. **Subtarefas só quando o item passa por mais de uma área** (UX/UI, back, front).
4. Itens que precisam de desenho começam no board Projeto. Itens só de dev vão direto para o Desenvolvimento.
5. A descrição diz o que foi observado, o que se espera e, se houver, a captura de tela.
6. Mostre a estrutura à Rafaella e só crie depois do sim.

## Histórias de usuário

Os requisitos são escritos pela analista de requisitos. Quando a Rafaella cria histórias para poder prototipar, é exceção ao fluxo: registre na descrição que foi criada por ela para permitir a prototipação e que a analista pode validar depois. Toda vez que histórias forem criadas, entregue também um arquivo .md com elas.

## Validação do design: quem valida

Pode ser **requisitos** (a analista), **clientes** ou **gestão** (esta menos comum, para prazo e escopo). A Gabriela acumula requisitos e coordenação do projeto: confirme quem valida o quê em cada demanda. "Clientes" no Conecta: **a confirmar** (áreas do TCE-CE, jurisdicionados ou depende da demanda; pergunte quando for o caso).

## Handoff no Conecta

- Existem três handoffs: design para o front, design para o back e back para o front. A esses se soma o pacote de teste para o QA (`../handoff.md`).
- Modelo em deltas: handoff completo uma vez (linha de base) e, depois, só a parte alterada. Toda correção ou adição é delta de um handoff anterior: procure a linhagem no changelog do handoff e nos cards antes de montar (`../handoff.md`, seções "Linhagem" e "Mapa para o dev"). IDs no padrão `HO-CONECTA-MODULO-nnn`.
- Os documentos do Project do Conecta (modelo de handoff, changelog do handoff, modelo de delta) devem ser lidos com a ferramenta de Projects antes de montar um handoff.
- O dev front usa o Claude conectado ao Figma por MCP para construir o front: o Figma precisa estar organizado para isso.

## Destinos de entrega

A definir (pasta do Drive e repositório padrão). Enquanto não estiverem definidos, pergunte o destino a cada entrega. Repositórios conhecidos: `conecta-docs` (specs e handoffs do Conecta) e `tce-design-system` (specs gerais do DS), com a regra de branch e pull request.

## Acordos do time

A definir: definição de pronto, definição de preparado, quem aprova o quê, regra de roteamento de defeitos encontrados no teste. Limites de trabalho em andamento no board de Desenvolvimento: 3 em desenvolvimento, 2 em QA, 2 em homologação.

## Pendência de produto que vale para o módulo de devolutivas do jurisdicionado

O sistema de acesso (perfis e permissões) ainda será definido pelo time de produto. Considere isso em toda tela desse módulo (card CONECTA-18). Perfis mapeados: Dirigente Máximo, Operador Nível 1, Operador Nível 2 e Supervisor. Isso sobe a profundidade da demanda (vários perfis e permissões).

## Módulos recorrentes

- **Criação e envio das comunicações devolutivas** (CONECTA-1): o nome correto do módulo é esse, não "comunicações devolutivas" em geral. No Figma, vive na página "💬 CD: Envio"; o acompanhamento e as prorrogações de prazo vivem em "💬 CD: Em andamento".
- **Campos de ocorrências, respostas e manifestações** (CONECTA-10).
- **Devolutivas do jurisdicionado** (CONECTA-8 e CONECTA-18).

## Pendências conhecidas do contexto

- Figma do Conecta (arquivo V2): link ainda não registrado aqui.
- Índice e specs do DS podem estar defasados em relação às decisões de 27 e 28/10 (px e rem, mínimo de 16px, prefixo `tcece`, base MUI). Confira antes de usar.
