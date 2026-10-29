# Roteiros por tipo de demanda

Última revisão: 2026-10-29.

Escolha o roteiro que combina com o tipo (`classificacao-e-profundidade.md`). Antes de executar qualquer um, confira os insumos do tipo em `insumos-por-tipo.md` e peça o que bloqueia. Se a demanda misturar tipos, combine os roteiros e diga isso. Em todos, conduza uma etapa por vez e releia o card antes de retomar. Os passos dizem o que cada etapa precisa entregar; adapte à demanda e à profundidade em vez de seguir como lista fixa.

Quase todo roteiro de design termina em **revisão → validação do design → handoff**. Os detalhes estão em `revisao-do-design.md`, `validacao-do-design.md` e `handoff.md`.

## 1. Tela nova, evolução ou protótipo de módulo

1. **Insumos.** Leia o card, as histórias e critérios, o protótipo de baixa fidelidade (ponto de partida; tem limitações) e frames já existentes. Cruze com o que o dev já implementou.
2. **Lacunas.** Liste o que está em aberto (regras, perfis, estados) e pergunte só o que bloqueia. Se faltar história, vá para o roteiro 4.
3. **Estrutura.** Proponha as telas e estados (vazio, erro, carregando, sucesso, perfis) antes de desenhar.
4. **Desenho.** Antes de abrir o Figma, confirme se já existe página ou frame da demanda (se existir, acesse; se for do zero, proponha a página ou seção e o nome e espere o sim antes de criar). Prototipe em alta fidelidade com os componentes do DS (regras do contexto). Informe o frame com ID e espere o sim antes de mudar de frame.
5. **Componentes faltantes.** Para cada componente que não existe no DS, sugira a criação e pergunte se entra no checklist (roteiro 3).
6. **Revisão.** `revisao-do-design.md`, até não haver Alta aberta.
7. **Validação do design.** `validacao-do-design.md`, com quem foi definido na etapa 5.
8. **Atualizar o card.** Com o sim dela, comente a validação e mova o card para a etapa seguinte do contexto.
9. **Handoff.** Quando ela pedir, por destinatário (roteiro 5).

## 2. Correção, ajuste ou pendência vinda de teste

1. **Entender o que foi observado.** Leia o card do problema e a captura, se houver. Separe o que é defeito do dev (back ou front), o que é ajuste de UX e o que é melhoria nova.
2. **Classificar e priorizar.** Defina a ordem pelo que ela disser. Itens só de dev vão direto ao downstream; itens que precisam de desenho começam no upstream.
3. **Estruturar os cards.** Proponha pai, filhos, tipos, prioridades e subtarefas por área (roteiro 7) e espere o sim antes de criar.
4. **Desenhar o que precisa de desenho.** Siga o roteiro 1 só para esses itens, na ordem de prioridade (o layout antes dos detalhes que dependem dele, como tooltips).
5. **Revisar e validar.** Em demanda leve, um checklist rápido e a aprovação por comentário no card bastam.
6. **Passar ao dev.** Correção costuma ser delta de um handoff anterior: procure a linhagem e entregue só o que mudou, com o mapa para o dev (roteiro 5).
7. **Acompanhar o reteste** (roteiro 6).

## 3. Componente novo ou ajuste no Design System

1. **Confirmar se já existe.** Procure no DS e na biblioteca do MUI antes de criar. Prefira o componente do MUI e adapte.
2. **Definir o papel.** Nome equivalente ao MUI quando o papel existe; prefixo do DS para o que é só dele.
3. **Criar no arquivo do DS**, com variáveis de tipografia, cor e espaçamento ligadas, e foco conforme a regra do DS.
4. **Spec.** Crie ou atualize a spec (camada de Atomic Design, dependências, data e versão) e confira as specs relacionadas.
5. **Checklist.** Registre no checklist de sugestões do DS só o que ela aprovar.
6. **Versionar.** Se ela pedir, suba no repositório do DS por branch nova e pull request, explicando cada passo antes.

## 4. Histórias de usuário e critérios de aceitação

Os requisitos costumam ser de quem faz requisitos no contexto; quando a Rafaella cria histórias para poder prototipar, é exceção ao fluxo (o perfil do contexto diz como registrar).

1. **Origem.** Leia o protótipo de baixa fidelidade, o card pai e o que o time já decidiu. Aponte decisões ainda pendentes.
2. **Redigir.** Formato "Como [perfil], eu quero [ação], para [benefício]", com critérios de aceitação objetivos e as pendências marcadas como decisão pendente.
3. **Registrar a exceção** na descrição, quando for o caso: criada por ela para permitir a prototipação, para validação posterior de quem faz requisitos.
4. **Criar os cards** só depois do sim, e entregue também o arquivo .md com as histórias.

## 5. Handoff

Detalhes em `handoff.md`.

1. **Esperar o pedido.** Ela pede; não atualize o handoff durante o trabalho. Mas ofereça ao fim da validação do design.
2. **Escolher destinatário e formato:** front, back, back para front ou QA.
3. **Procurar a linhagem.** Já existiu handoff deste assunto? Procure (registro, cards, changelog, Figma) e confirme com ela. Defina a relação: primeira entrega, correção, adição, alteração ou substituição.
4. **Linha de base ou delta.** Primeira entrega: completo. Depois: apenas o que mudou, apontando os frames alterados (com ID). Confira nos cards do dev o estado do que foi entregue antes.
5. **Montar o mapa para o dev** no topo (ID, "Baseado em", "Leia primeiro", "O que mudou"), pensando que o dev entrega o documento a uma IA.
6. **Conferir** o checklist de prontidão.
7. **Entregar e registrar.** Anexe ao card, ligue-o ao card ou handoff anterior, comente com o sim dela e acrescente a linha no changelog do handoff do contexto.

## 6. Acompanhar a implementação, o teste e o fechamento

1. **Reler os cards.** Veja status, comentários e subtarefas do dev e do teste.
2. **Responder dúvidas do dev** com base no Figma e nas specs, e levar a resposta ao handoff ou à spec. Se exigir decisão de produto, diga a ela.
3. **Revisar a implementação (design QA).** Compare a tela entregue com o Figma e liste as diferenças em tabela (divergência, severidade, decisão, status), separando erro de implementação de mudança de desenho.
4. **Relatos do QA.** Se o QA reportar algo, use o modelo de relato; se faltar informação, peça só o que falta.
5. **Devolver ou fechar.** Cards com diferenças voltam ao dev (pelo status que o contexto indicar para devolução); os aprovados seguem, com o sim dela.
6. **Registrar aprendizados** quando ela pedir (problema, solução, tempo antes e depois, qualidade, impacto na entrega).

## 7. Organizar cards no Jira

Siga as convenções do perfil do contexto: pai e filhos, tipo certo, subtarefas só quando passa por mais de uma área, prioridade, versão e labels. Mostre a estrutura e espere o sim antes de criar. Depois de criar, confira a contagem (a busca pode demorar a refletir) e entregue um resumo com as chaves.

## 8. Demanda sem card

Pergunte de onde ela vem e quem pediu. Ajude a escrever o objetivo, o que se espera e a área (UX/UI, back, front). Proponha onde o card entra (épico existente ou novo) e só crie depois do sim.

## 9. Protótipo interativo no Claude

Detalhes, tabela de usos e comentário padrão do card em `prototipo-interativo.md`.

1. **Insumos.** Confira história, critérios e regras (`insumos-por-tipo.md`). Escolha o modo de partida: pelas specs (padrão para tela nova), pelo Figma (já há frames) ou híbrido.
2. **Estrutura no card.** Proponha a subtarefa de protótipo interativo (nome no perfil do contexto) e espere o sim antes de criar.
3. **Construir.** Use MUI e os tokens do DS. Para cada item que não achar nas specs, leia só aquele ponto no Figma e pergunte: criar uma spec rascunho (A) ou só usar o que viu por enquanto (B).
4. **Revisar e validar.** Mostre as telas, alterne estados e perfis, revise (`revisao-do-design.md`). O protótipo é o pacote natural de validação com clientes. Compartilhe como artefato só quando ela autorizar.
5. **Passar para o Figma.** A cada tela ou fluxo validado, reconstrua os frames com componentes e variáveis do DS, informando nome e ID. Espere o sim antes de mudar de lugar no Figma.
6. **Registrar.** Comentário padrão no card, lacunas do DS no checklist (perguntando antes) e specs novas por branch e pull request, se ela aprovar.
7. **Handoff.** Quando ela pedir, em delta (roteiro 5).
