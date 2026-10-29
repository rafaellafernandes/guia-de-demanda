# guia-de-demanda

Skill do Claude que guia a Rafaella em cada demanda de design e produto, do pedido ao handoff e ao fechamento, em qualquer contexto de trabalho (Conecta, Design System TCE e outros).

Repositório privado: o perfil do Conecta traz nomes de pessoas do time e o endereço do Jira.

## O que tem aqui

| Caminho | O que é |
|---|---|
| `guia-de-demanda/SKILL.md` | O núcleo da skill: o fluxo da demanda |
| `guia-de-demanda/references/` | Classificação, insumos, roteiros, revisão, validação do design, handoff, registro da demanda, regras de escrita e planos futuros |
| `guia-de-demanda/references/contextos/` | Um perfil por lugar de trabalho (`conecta.md`, `design-system-tce.md`) e o modelo para criar novos |
| `CHANGELOG.md` | O que mudou em cada versão |

## Como atualizar

1. Toda mudança começa numa **branch nova** a partir da `main`.
2. A `main` só muda por **pull request** mesclado pela Rafaella.
3. A cada mudança, registre no `CHANGELOG.md` a versão, a data e o que mudou, e atualize a linha "Última revisão" dos arquivos alterados.
4. Depois de mesclar, gere de novo o arquivo `.skill` e salve no Claude ("Salvar skill").

## Para instalar no Claude

Peça ao Claude para empacotar a pasta `guia-de-demanda/` como `.skill` e clique em "Salvar skill" no cartão que aparecer.
