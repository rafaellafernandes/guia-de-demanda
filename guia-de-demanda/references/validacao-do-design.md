# Validação do design

Última revisão: 2026-10-29.

Use na etapa 8. O que foi produzido não vai direto para o desenvolvimento: antes passa por quem aprova. Chamamos de **validação do design** para não confundir com o status "Homologação" do Jira, que costuma ser do lado do dev.

## Pré-condições

- Revisão feita e sem achado Alta aberto (`revisao-do-design.md`).
- Quem valida definido (pergunta feita na etapa 5).
- Pacote pronto (abaixo).

## Quem valida

Varia por demanda. Pode haver mais de um, em sequência (por exemplo, requisitos primeiro e clientes depois). A profundidade ajuda a decidir: na leve basta um; na profunda, mais de um ou clientes.

| Quem valida | O que olha | O que preparar |
|---|---|---|
| **Requisitos** | Se as regras e os critérios de aceite estão cobertos | Frames com ID ou link, checklist dos critérios (um item por critério), estados e perfis cobertos, decisões e pendências em aberto |
| **Clientes** | Se entendem e conseguem usar | Protótipo navegável (o interativo serve bem), dados fictícios, linguagem sem jargão, roteiro curto de apresentação, perguntas guiadas para colher o retorno |
| **Gestão** (menos comum) | Prazo, escopo, esforço e impacto | Resumo de uma página: o que foi entregue, o que falta, riscos, decisões que dependem da pessoa. Estimativa de tempo só se vier de fonte; senão, marque como HIPÓTESE |

No perfil do contexto, confira quem ocupa cada papel e quem é "cliente" ali (áreas internas, usuários finais...). Se não estiver escrito, pergunte.

## Como conduzir

1. **Prepare o pacote** conforme a tabela. Ofereça-se para redigir a mensagem de convite; quem envia é ela. Você não escreve a terceiros sem o sim dela.
2. **Defina o que vai ser perguntado.** Para clientes, perguntas abertas sobre a tarefa ("o que você faria para enviar a comunicação?") rendem mais do que "gostou?". Não invente falas nem resultados de usuários que não aconteceram.
3. **Colha o retorno** e traga para o chat (ou deixe que ela cole). Registre quem disse o quê.
4. **Classifique cada retorno:**

   | Retorno | Destino |
   |---|---|
   | Ajuste de design | Volta à produção; depois, revisão e nova validação do que mudou |
   | Mudança de regra ou requisito | Volta aos requisitos (quem escreve os requisitos decide); reabre a etapa |
   | Fora do escopo desta demanda | Vira card novo, com o sim dela |
   | Dúvida respondível | Responda e registre |

5. **Resultado:** aprovado, aprovado com ajustes ou reprovado. Aprovado com ajustes exige que os ajustes sejam feitos e confirmados antes do handoff. Reprovado volta a produzir.
6. **Registre** no registro da demanda e, com o sim dela, comente no card.

## Gate

A demanda só segue para a documentação e o handoff com a validação registrada. Se ela decidir dispensar (prazo, por exemplo), registre a etapa como pulada, o risco aceito e quem aceitou. Retorno que muda requisito reabre a etapa de requisitos, mesmo já aprovada.

## Modelo do comentário de validação (card)

```
Validação do design, data
Quem validou: nome e papel (requisitos, clientes ou gestão)
O que foi mostrado: frames com ID ou link do protótipo, e a versão
Resultado: aprovado / aprovado com ajustes / reprovado
Ajustes pedidos: lista curta, com o que já foi feito
Pendências e decisões em aberto: lista curta
Próximo passo: documentação e handoff / nova rodada / volta a requisitos
```

## Cuidados

- **Dados fictícios.** Nunca coloque dados reais de pessoas, entidades ou processos em protótipos mostrados a terceiros.
- **Privacidade do protótipo.** Um artefato publicado é privado até ela compartilhar. Avise antes de compartilhar o link.
- **Cliente não é projetista.** Peça o problema que ele enfrenta, não a solução de tela.
- **Gestão.** Resumo curto, sem jargão. Não prometa prazo que a demanda não sustenta; diga o que depende de quem.
- **Aprovação do dev não fecha a validação.** Dev dizer "está ok" é outra coisa, e não substitui quem valida o design.
