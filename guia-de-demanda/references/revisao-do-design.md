# Revisão do design

Última revisão: 2026-10-29.

Use na etapa 7. É a checagem interna, feita antes de mostrar o resultado a quem vai validar. Serve também, depois da implementação, para comparar a tela entregue com o desenho (design QA, roteiro 6).

## Como conduzir

1. **Veja antes de ler.** Primeira passada de uns três segundos: qual é a intenção principal da tela? Registre o que entendeu antes de estudar os detalhes. Se não era a intenção pretendida, já é um achado.
2. Passe pelas dimensões abaixo e pelos critérios de acessibilidade.
3. Confronte com a história: cada critério de aceite está coberto por algum frame ou estado?
4. Classifique cada achado, apontando **o critério violado** (preferência pessoal não é achado).
5. Proponha a correção de cada Alta e Média, aplique com o ok dela e **revise de novo**. Repita até não haver Alta aberta.
6. Registre o resultado no registro da demanda.

## Severidade

| Severidade | Significa | Efeito |
|---|---|---|
| **Alta** | Quebra um critério de aceite, acessibilidade, ou induz erro grave | Bloqueia a validação do design |
| **Média** | Prejudica, mas não impede o uso | Corrigir antes do handoff |
| **Baixa** | Melhoria | Registrar para depois |

## Dimensões

| Dimensão | Pergunta | Falha típica |
|---|---|---|
| Clareza | A intenção principal é óbvia sem ler tudo? | Hierarquia achatada |
| Ação | Todo dado mostrado tem próximo passo? | Número sem ação possível |
| **Escala** | Funciona com 1 item e com 200? Com poucas e com muitas colunas? Com número pequeno e muito grande? Com texto curto e longo? | Lista, tabela ou contador que quebra num dos extremos |
| Feedback | A pessoa sabe que a ação funcionou? | Ação sem retorno visível |
| Transparência | O erro parcial é dito com exatidão? | "Concluído" escondendo falha em parte do lote |
| Consistência | Usa o padrão que já existe no produto e no DS? | Componente novo sem motivo |
| Eficiência | Quantos passos para a tarefa principal? | Passo redundante |
| Estados | Vazio, carregando, erro, sucesso, desabilitado, parcial, lote? | Só o caminho feliz foi desenhado |
| Perfis | A tela muda conforme o perfil, quando deveria? | Um perfil esquecido |
| Textos | Todo texto que o usuário vê está escrito e é final? | "Mensagem de erro apropriada" |
| Cobertura | Cada critério de aceite tem onde ser visto? | Critério sem frame |

## Acessibilidade (bloqueante)

Aplique as regras do Design System do contexto (tamanhos mínimos, foco, tokens). Em qualquer contexto, confira ao menos:

- texto e elementos com contraste suficiente (WCAG AA);
- foco visível em todo elemento interativo e navegação por teclado;
- campo com rótulo associado, não só texto de exemplo;
- ícone sem texto com nome acessível;
- erro e status comunicados por texto ou ícone, nunca só por cor;
- alvos clicáveis do tamanho mínimo que o DS exige;
- tabela com cabeçalho acessível;
- diálogo e painel com título associado.

Falha aqui é Alta.

## Modelo de resultado

```
Revisão: nome da tela ou fluxo, data
Primeira leitura: o que entendi / era a intenção? sim ou não
Achados:
  R01 | achado | critério violado | Alta, Média ou Baixa | correção proposta | aberto ou corrigido
Cobertura dos critérios de aceite: critério → onde está
Resultado: sem Alta aberta, pronto para validar / com Alta aberta, volta a produzir
```

## Erros comuns

| Erro | Correção |
|---|---|
| Revisar depois de estudar a tela | A primeira leitura é o dado mais valioso |
| Achado sem critério | Todo achado aponta o que foi violado |
| Aprovar por estar bonito e consistente com o DS | Consistência é uma dimensão entre várias |
| Deixar Alta "para depois" | Alta bloqueia |
| Não revisar de novo depois do ajuste | O ciclo só fecha com nova rodada sem Alta |
