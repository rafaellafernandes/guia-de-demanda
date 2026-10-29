# Modelo de perfil de contexto

Use quando a demanda vier de um lugar de trabalho que ainda não tem perfil em `references/contextos/`. Faça só as perguntas que faltam, numa mensagem curta, e crie o perfil depois do sim dela. Marque como "a confirmar" o que não foi lido.

## Perguntas mínimas

1. **Onde ficam os cards?** Ferramenta, endereço, projeto e boards. Há chave de card reconhecível (prefixo)?
2. **Quais são os status e as colunas**, na ordem, e o que cada um significa? O que acontece quando um card volta? Há limites de trabalho em andamento?
3. **Quem faz o quê?** Requisitos, design, front, back, teste, aprovação, gestão.
4. **Onde mora o design?** Arquivo e páginas do Figma, Design System, specs.
5. **Onde estão requisitos e contexto?** Miro, Confluence, Drive, repositório.
6. **Convenções:** nomes de card, labels, prioridades, versões.
7. **Quem valida o design**, e quem são os "clientes" e a "gestão" nesse contexto?
8. **Quem recebe o handoff** e em que formato? Há documentos-modelo?
9. **Onde cada entrega mora** (card, Drive, repositório)? Há regra de branch e pull request?
10. **Acordos do time:** definição de pronto, de preparado, regra para defeitos.
11. **Pendências de produto** que valem para tudo nesse contexto.

## Estrutura do arquivo

```
# Nome do contexto
Última revisão: data

## Onde fica        (ferramentas, endereços, boards)
## Pessoas e papéis
## Fluxo e status   (ordem, significado, cuidados do board)
## Convenções       (nomes, labels, prioridade, versões)
## Validação do design (quem valida o quê)
## Handoff          (destinatários, modelos, onde mora)
## Destinos de entrega
## Acordos do time  (ou "a definir")
## Pendências e módulos recorrentes
## Cuidados
```

Registre a data da revisão. Se um dado ficar velho, a skill avisa em vez de repeti-lo.
