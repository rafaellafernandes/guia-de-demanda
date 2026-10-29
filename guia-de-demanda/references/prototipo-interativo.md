# Protótipo interativo no Claude

Última revisão: 2026-10-29.

Leia este arquivo quando a Rafaella quiser prototipar (ou validar o comportamento de uma tela) no próprio Claude, em vez de ou antes do Figma. A regra de ouro: **o Figma e as specs do Design System são a fonte; o protótipo é um consumidor delas.** O protótipo nunca cria valor, componente ou regra que não exista no DS sem passar por ela. Isso evita duas fontes de verdade e protege o handoff, porque o dev front lê o Figma.

## 1. Para que serve (possibilidades de uso)

| Uso | O que entrega | Quando vale | Exemplo no Conecta |
|---|---|---|---|
| Validar comportamento | Tela que reage de verdade (rolagem, filtros, estados, validação) | A tela tem algo que o Figma mostra mal | Tabela de ocorrências com muitas colunas, contadores com números grandes, tooltips, validação de planilha |
| Explorar alternativas | 2 ou 3 variações navegáveis lado a lado | Há dúvida de layout ou de fluxo | Separar campos do TCE-CE dos campos para todos: abas, colunas fixas ou agrupamento |
| Validar com o time ou com usuários | Link para navegar e comentar, sem exigir o Figma | Reunião de alinhamento, teste rápido de usabilidade | Fluxo de criação e envio da comunicação |
| Cobrir estados e perfis | Alternância de perfil, erro, vazio, carregando, sucesso | Telas que mudam por perfil | Devolutivas do jurisdicionado, enquanto o sistema de acesso não está definido |
| Apoiar o dev | Referência viva do comportamento, usando MUI | O dev precisa ver a interação, não só a aparência | Handoff em delta com link do protótipo |
| Descobrir lacunas do DS | Lista de componentes, estados e tokens que faltam | Qualquer protótipo | Tabela, modal e card, que ainda não têm spec |
| Registrar aprendizado | Tempo, número de iterações e erros evitados | Quando ela pedir para guardar aprendizados | Material para a apresentação à gestão |

Prefira começar pelo Figma (e não pelo Claude) quando: é um módulo grande com muitas telas e várias pessoas precisam alinhar a estrutura; o trabalho é criar ou alterar um componente do DS; ou a demanda já tem frames e só falta ajustar.

## 2. Modos de partida

Pergunte (ou deduza do card) de onde o protótipo parte:

1. **Pelas specs (padrão para tela nova).** Use o índice do DS e as specs. Gasta menos e segue a fonte oficial. O Figma só entra nas lacunas e no fim.
2. **Pelo Figma (quando a demanda já tem frames).** Leia o frame e as variáveis dele e monte a versão interativa a partir dali.
3. **Híbrido.** Estrutura vinda do Figma, tokens e regras vindos das specs.

## 3. Specs primeiro, Figma nas lacunas

Para cada token, componente ou padrão necessário:

1. Procure no índice e nas specs. Achou: use, conferindo data e versão. Se a spec parecer antiga, avise.
2. Não achou: leia no Figma só aquele item (arquivo do DS ou frames da demanda).
3. Achou no Figma: pergunte a ela, com uma recomendação:
   - **A. Criar uma spec rascunho a partir do que vi.** Recomende quando o item é reaproveitável, aparece em mais de um lugar ou é componente do DS.
   - **B. Só usar o que vi no Figma por enquanto.** Recomende quando é específico de uma tela ou do Conecta (vai para o handoff do Conecta, não para as specs do DS).
4. Não achou nem no Figma: é lacuna. Registre no checklist de sugestões do DS (perguntando antes) ou leve como decisão de design.

Se ela escolher A:
- Siga o formato das specs do DS: regras obrigatórias, tokens, como escolher, componentes, responsivo, mapa Figma ↔ código, checklist e pontos em aberto.
- No cabeçalho, coloque a data, a versão, a camada de Atomic Design, as dependências, o ID do nó do Figma de origem e o status "rascunho derivado do Figma". Até ela aprovar, o Figma manda nesse item.
- Atualize o índice e confira as specs relacionadas.
- A alteração no repositório começa numa branch nova a partir da main e só chega à main por pull request dela. Explique cada passo em linguagem simples antes de fazer.
- Itens marcados "A DECIDIR" nas specs não são implementados no protótipo: pergunte.

## 4. Regras do protótipo

- Use MUI com os tokens do DS (prefixo `tcece` para o que é só do TCE). Nunca valor solto de fonte, cor, espaçamento ou raio.
- Texto nunca abaixo de 16px; alvo clicável de 44px no desktop e 48px no mobile; foco visível em amarelo e preto; cor nunca como único indicador de status.
- Cubra os estados (vazio, carregando, erro, sucesso) e, quando houver, os perfis.
- Use **dados fictícios**. Não coloque no protótipo dados reais de jurisdicionados, entidades ou processos.
- Dê a cada tela o nome do frame do Figma correspondente (com o ID, quando existir) e mantenha um mapa tela do protótipo → frame → card do Jira no cabeçalho do protótipo, com data e versão.
- Quando precisar compartilhar, publique como artefato e use o link no card. O artefato é privado até ela compartilhar.

## 5. Na esteira (Jira)

As colunas e os nomes dependem do contexto (veja o perfil em `contextos/`). A estrutura sugerida:

1. **Card:** uma subtarefa de protótipo interativo no card da história ou do problema, com o label `prototipo-interativo` (nome e prefixo no perfil do contexto). Ela já é a responsável.
2. **Requisitos:** insumos conferidos (história, critérios, specs ou Figma).
3. **Design:** protótipo em andamento; revisão (`revisao-do-design.md`) e validação do design com quem aprova (`validacao-do-design.md`); decisões registradas. O protótipo é o pacote natural de validação com clientes.
4. **Documentação:** estados finais reconstruídos no Figma, specs criadas ou atualizadas, lacunas do DS registradas, comentário padrão no card.
5. **Pronto para o dev:** frames no Figma e link do protótipo anexados. Handoff só quando ela pedir, e em delta.
6. **Depois:** acompanhar o dev e o teste pelo roteiro 6.

**Comentário padrão no card ao fechar uma etapa** (só depois do sim dela):
- Link do protótipo e versão.
- Frames criados ou alterados no Figma (nome e ID).
- O que mudou em relação ao Figma anterior.
- Specs criadas ou atualizadas, e lacunas do DS.
- Pendências e decisões em aberto.

## 6. Passar para o Figma (reconstruir, não converter)

A cada tela ou fluxo validado, e não só no fim da demanda:

1. Antes de criar, confira se já existe página ou frame da demanda e proponha onde entra (página nova ou seção, com nome no padrão do arquivo). Espere o sim antes de mudar de lugar no Figma.
2. Reconstrua os frames usando instâncias dos componentes do DS e as variáveis de tipografia, cor e espaçamento ligadas, com nomes equivalentes aos do MUI. Use o protótipo como referência. A conversão direta de código para Figma pode servir de rascunho, mas costuma gerar frames sem instâncias nem variáveis, então não é entrega.
3. Informe o nome e o ID de tudo o que criou ou alterou.
4. Confira o que o protótipo inventou e sugira o que falta no DS, perguntando se entra no checklist.
5. Registre tudo no card.

Esse caminho ainda não foi validado nas telas do Conecta. Teste com uma tela real antes de adotá-lo como padrão e ajuste este arquivo com o que aprender.

## 7. Cuidados

- Mantenha o protótipo pequeno: um fluxo ou tela por vez. Arquivos grandes encarecem cada ajuste.
- Antes de fechar um desenho, veja se o back ou o front têm trabalho aberto no mesmo assunto (por exemplo, template e validação de planilha) e avise a pessoa responsável.
- Se o protótipo e o Figma divergirem, a decisão é dela: pergunte qual vale e atualize o outro.
- Sugira melhorias nesta própria rotina quando perceber fricção (seção "Melhoria contínua" do SKILL.md).
