# Regras de escrita e entregas

Última revisão: 2026-10-29.

Tudo que a skill escreve fora do chat afeta o time ou é difícil de desfazer sem barulho. Estas regras valem em qualquer contexto.

## Princípio

Diga o que vai fazer, mostre o conteúdo exato e espere o "sim". Um sim vale para a ação mostrada; a próxima escrita pede outro, salvo estrutura aprovada em conjunto (por exemplo, "pai e quinze filhos" aprovados de uma vez). Nunca escreva como efeito colateral de terminar uma etapa.

## Jira

- **Mostre o conteúdo exato antes:** título, tipo, prioridade, labels, versão, descrição, pai e destino.
- **Confira em nome de quem a conexão está autenticada** antes da primeira escrita da sessão (operação de usuário atual do conector). Se não for ela, pare e avise: o autor ficaria errado e o relator pode não ser editável.
- **Não mova card de status como efeito de uma etapa.** Mover exige o gate cumprido (revisão, validação do design, handoff, conforme a etapa) e o sim dela. Em muitos fluxos o Jira deixa mover para qualquer status; quem segura os gates é esta skill.
- **Transcreva a demanda literal** ao puxar um card. A forma como foi pedida é informação.
- **Depois de criar, confira a contagem.** A busca por JQL demora a refletir; se vier menos, espere e busque de novo antes de concluir que falhou.
- **Conector indisponível ou erro:** entregue o texto pronto para colar, registre a escrita como pendente e **nunca diga que foi feita**.
- **Versões, filtros e colunas:** confira no perfil do contexto os cuidados do board (por exemplo, filtros que escondem cards).
- **Histórias de usuário:** sempre que cards de história forem criados, entregue também um arquivo .md com elas.
- **Texto para o chat do time:** curto. Link do card, ordem de prioridade e como será a esteira.

## Figma

- Antes de qualquer chamada em arquivo do Figma, abra uma sessão para o arquivo e carregue a skill do Figma exigida pela ferramenta.
- **Informe o nome e o ID de tudo que criar ou alterar.**
- **Avise antes de mudar de frame:** qual frame, onde está e o que será feito. Espere o sim.
- Antes de criar uma página ou seção, liste o que já existe e proponha o nome e o lugar.
- Componente novo do DS é criado no arquivo do DS, nunca no arquivo da demanda.

## Repositórios

- Toda alteração começa numa **branch nova** a partir da principal. A principal só muda por **pull request mesclado por ela**.
- Ela não domina Git: explique em linguagem simples o que vai fazer antes de fazer, um passo por vez.
- Nunca grave token, senha ou chave em arquivo de repositório.

## Destinos de entrega

Cada entrega tem um lugar. O padrão de cada contexto está no perfil dele; quando não estiver, **pergunte o destino** antes de enviar.

| Entrega | Destino típico |
|---|---|
| Handoff para dev | Comentário ou anexo no card, mais o arquivo no repositório de documentos do contexto (branch e pull request) |
| Pacote de teste e modelo de relato (QA) | Comentário no card, onde o QA lê |
| Comentário de validação do design | Card |
| Resumo para a gestão | Drive ou Docs, com o link no card |
| Protótipo interativo | Artefato publicado, com o link no card |
| Specs do DS | Repositório do DS (branch e pull request) |
| Histórias de usuário | Cards e arquivo .md |

Ao enviar:

1. Diga o destino e o nome do arquivo, e espere o sim.
2. Use o conector disponível (Drive, Docs, Confluence, repositório). Confira que ele está conectado **antes** de prometer; se não estiver, entregue o arquivo na conversa e diga o que falta conectar.
3. **Não altere permissões de compartilhamento** sem ela pedir.
4. Devolva o link e registre no registro da demanda.
5. Arquivos que ela anexa são os originais: trabalhe em cópia e devolva o resultado.

## Dados de terceiros

Nada de dados reais de pessoas, entidades ou processos em protótipos, registros ou textos de exemplo. Use dados fictícios.
