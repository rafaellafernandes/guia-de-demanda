# Registro da demanda

Última revisão: 2026-10-29.

Um registro **curto** por demanda, para retomar sem reexplicar. Ele guarda o raciocínio (decisões, dúvidas, o que foi validado e entregue); o Jira guarda o estado do card. Não duplique o Jira.

## Quando e onde

- Abra na etapa 5, **com o sim dela**, para demandas de profundidade padrão ou profunda. Na leve, bastam o cabeçalho e as decisões, ou só um comentário no card.
- Atualize ao fim de cada etapa.
- Onde guardar: um documento da demanda no Project do contexto (por exemplo, `demanda-CHAVE.md`), escrito com a ferramenta de Projects e só depois do sim dela. Alternativas: comentário no card ou arquivo no repositório do contexto (regra de branch e pull request).
- Ao retomar uma demanda, leia o registro antes de reler o card.
- Mantenha em até uma tela. Se crescer, condense: um registro que vira diário deixa de ser lido.

## Marcação das afirmações

Marque o que não for óbvio: **FATO** (fonte e data), **OBSERVAÇÃO**, **INFERÊNCIA**, **HIPÓTESE**, **DECISÃO**. Não registre como respondida uma pergunta que você deduziu: resposta tem fonte e data.

## Modelo

```
# Demanda: chave ou nome curto
Contexto: Conecta / outro | Aberta em: data
Tipo: ... (declarado: ... ) | Profundidade: ... (gatilhos: ...)
Quem valida o design: ... | Quem recebe o handoff: front / back / QA
Estado: última etapa concluída → próxima etapa

## Pedido como chegou
Transcrição literal, curta.

## Decisões
D01 | decisão | sustentada por (fonte, data) | data
D02 ...

## Em aberto
Q01 | pergunta ou incerteza | responsável por responder | estado

## Premissas que caíram (opcional)
O que se achava e deixou de valer, e por quê.

## Etapas puladas e risco aceito
Etapa | por quê | risco | quem aceitou

## Revisão
Resultado da última revisão (sem Alta aberta?) e achados abertos.

## Validação do design
Quem | data | versão mostrada | resultado | ajustes

## Handoff
ID do handoff | relação (primeira entrega, correção, adição, alteração, substituição) | baseado em (IDs anteriores) | destinatário | formato | onde está | data | pendências

## Reaberturas
Data | etapa reaberta | evidência nova | impacto

## Escritas em ferramentas
Data | onde (Jira, Figma, Drive, repositório) | o que foi escrito | confirmada por ela | resultado
```

## Cuidados

- Registre reabertura quando nova evidência mudar uma etapa já aprovada.
- Registre em "Escritas em ferramentas" tudo que você criou ou alterou fora do chat, com o nome ou ID (card, frame, arquivo). É o que permite desfazer e conferir.
- Dado sensível de terceiros não entra no registro.
