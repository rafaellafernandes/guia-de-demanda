# Insumos por tipo de demanda

Última revisão: 2026-10-29.

Use na etapa 4 do fluxo. A ideia: antes de desenhar ou orientar, confirmar que existe material suficiente. Começar sem o insumo certo gera retrabalho (tela desenhada sobre regra que não existe, handoff sem frame final) e é mais barato perguntar agora.

## Como classificar cada insumo

- **Encontrado:** achei e li (diga onde: card, Miro, Figma, documentos do Project).
- **Parcial:** existe, mas está incompleto, desatualizado ou ambíguo (diga o que falta).
- **Faltando:** não achei nem o card cita.

Insumo **bloqueante** faltando ou parcial: pare e peça, antes de qualquer etapa de execução. Insumo **desejável** faltando: diga e siga, deixando claro que a etapa assume algo e que isso precisa ser confirmado depois. A profundidade pode reduzir a lista: na leve, só os bloqueantes.

## Onde procurar antes de perguntar

1. Descrição, comentários, anexos e links do card, do pai e do épico.
2. Cards irmãos e relacionados (histórias originais, subtarefas de UX/UI já concluídas).
3. Miro e Confluence, se o perfil do contexto indicar onde.
4. Documentos do Project do contexto (handoffs, changelog, specs do DS, decisões em aberto) e o registro da demanda.
5. O que ela já disse nesta conversa.

Só então pergunte, e pergunte só o que não achou.

## Figma: acessar o que existe ou criar do zero

A primeira pergunta é se já existe página ou frame da demanda. Se o card, o épico, os documentos e a conversa não respondem, pergunte: "Já existe página ou frame disso no Figma, ou começamos do zero?"

**Já existe:** acesse o que existe, para não duplicar nem desenhar ao lado do que já foi feito. Se não houver link nem nome de frame, peça o link, de preferência com o node-id. Não procure frames no escuro nem presuma qual arquivo ou página é.

**Do zero (por exemplo, protótipo novo):** o insumo é o link do arquivo onde a demanda vai morar (o perfil do contexto diz qual costuma ser). Antes de criar, liste as páginas e seções do arquivo para ver se já existe algo parecido. Depois proponha:
- onde entra: página nova ou seção numa página existente (módulos costumam ter página própria, com seções que agrupam os frames);
- o nome, no padrão das páginas e seções do arquivo.
Confirme o nome e o lugar com ela e só crie depois do sim. Informe o nome e o ID do que foi criado.

Quando ela passar um link, sugira registrá-lo em um comentário do card, para as próximas vezes ninguém precisar perguntar de novo.

## Matriz por tipo

### 1. Tela nova, evolução ou protótipo de módulo (FEATURE, EVOLUÇÃO, PROTOTIPAÇÃO)
- Bloqueantes: história de usuário com critérios de aceitação; requisitos e regras de negócio da tela; link do Figma de referência (protótipo de baixa fidelidade ou frame existente) e onde a nova tela entra no arquivo; perfis de usuário envolvidos; quem vai validar o design.
- Desejáveis: decisões em aberto já registradas; dados e campos que o back entrega; componentes do DS que a tela deve reutilizar; prazo.
- Se faltar história ou critério: vá para o roteiro 4 antes de desenhar.

### 2. Correção, ajuste ou pendência vinda de teste (CORREÇÃO, AJUSTE)
- Bloqueantes: o que foi observado e o que se espera; captura de tela ou passos para reproduzir; link do frame atual no Figma ou da tela no ambiente de teste; qual ambiente e versão foram testados.
- Desejáveis: a história e os critérios originais; quem reportou; cards de dev relacionados em andamento.
- Um item reportado só com uma frase (por exemplo, "não suporta muitas colunas") é parcial: peça a captura e o critério do que seria "certo". O modelo de relato do QA (`handoff.md`) já traz isso.

### 3. Componente novo ou ajuste no Design System (COMPONENTE DS)
- Bloqueantes: nome e papel do componente; a tela ou demanda que o motivou; referência equivalente no MUI; link do arquivo do DS e a spec existente (se houver).
- Desejáveis: estados e variantes necessários; exemplos de uso em outras telas.

### 4. Histórias de usuário e critérios de aceitação (REQUISITOS)
- Bloqueantes: o protótipo ou documento de origem; os perfis e permissões; o card pai ou épico; as decisões de produto já tomadas.
- Desejáveis: histórias vizinhas já escritas (para manter o padrão); pendências conhecidas.
- Perguntas em aberto ganham um responsável por respondê-las e, quando respondidas, fonte e data. Não reabra pergunta já respondida.

### 5. Handoff
- Bloqueantes: o pedido dela; a validação do design registrada (ou risco aceito); os links dos frames finais (com ID); as histórias e critérios do card; para quem é (front, back, back para front, QA).
- **Linhagem (bloqueante):** procure se já existiu handoff do mesmo assunto (`handoff.md`, seção "Linhagem") e confirme com ela. Existindo, este é um delta: traga o handoff anterior, o estado do que foi entregue (cards do dev) e a lista do que mudou.
- Desejáveis: o changelog do handoff do contexto; lista do que mudou desde a última entrega.

### 6. Acompanhar implementação, teste e fechamento (ACOMPANHAMENTO)
- Bloqueantes: link da tela implementada (ambiente de teste) ou captura; frames de referência; critérios do card.
- Desejáveis: comentários do dev e do teste; build ou versão testada.

### 7. Organizar cards no Jira (ORGANIZAÇÃO)
- Bloqueantes: a lista das pendências; a ordem de prioridade que ela definiu; o épico ou pai de destino; a versão ou ciclo.
- Desejáveis: capturas e descrição do observado por item; quem fica com cada área.

### 8. Demanda sem card (SEM CARD)
- Bloqueantes: quem pediu e por quê; o resultado esperado; a área (UX/UI, back, front).
- Desejáveis: prazo, exemplos, material de referência.

### 9. Protótipo interativo no Claude
- Bloqueantes: história e critérios de aceitação; regras da tela; o modo de partida combinado com ela (pelas specs, pelo Figma ou híbrido); no modo pelas specs, as specs relevantes lidas, com data e versão; no modo pelo Figma, o link do frame.
- Desejáveis: decisões em aberto que afetam a tela; perfis e estados a cobrir; dados fictícios de exemplo.
- O link do arquivo do Figma passa a ser bloqueante só na hora de passar as telas para o Figma.

### 10. Validação do design
- Bloqueantes: revisão feita e sem achado Alta aberto; quem valida; o pacote preparado (frames ou protótipo, critérios, pendências).
- Desejáveis: perguntas guiadas (para clientes); resumo de uma página (para gestão).

## Como pedir o que falta

Uma única mensagem, curta, com só o que bloqueia, dizendo por que cada item importa para a etapa seguinte. Exemplo:

"Para redesenhar o layout de ocorrências eu preciso de duas coisas: o link do frame atual no Figma e como você define 'campo do órgão' e 'campo para todos'. Sem isso eu desenharia sobre uma suposição."

Se ela disser que não tem o insumo, ofereça o caminho mais curto: criar a história com critérios (roteiro 4), propor uma regra para ela validar ou desenhar uma primeira proposta marcada como HIPÓTESE.
