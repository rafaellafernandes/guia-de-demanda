# Handoff

Última revisão: 2026-10-29.

Use na etapa 9 e no roteiro 5.

## Regra

**Toda demanda de design termina com um handoff.** O formato varia; o mínimo é fixo.

- Ela decide quando o handoff sai. Você o oferece ao fim da validação do design e não fecha a demanda sem ele.
- Não atualize documentos de handoff durante o trabalho; só quando ela pedir.
- Se a validação do design não estiver registrada, o handoff não sai (ou o risco aceito está registrado).

## Mínimo fixo (em qualquer formato)

1. **Onde está o resultado:** frames com ID, ou link do protótipo.
2. **O que mudou:** em relação à entrega anterior, ou "primeira entrega".
3. **Critérios de aceite** da história.
4. **Pendências e o que ficou fora do escopo**, cada pendência com responsável.
5. **Quem recebeu e quando.**
6. **De onde vem:** o handoff anterior relacionado, ou "primeira entrega, confirmada" depois de procurar (seção "Linhagem").

## Linhagem: este handoff nasce de outro?

Muitas demandas são correção ou adição de algo já entregue. Antes de definir o formato, descubra se já existiu handoff do mesmo assunto. **Só chame de "primeira entrega" depois de procurar e de ela confirmar.**

Procure nesta ordem, sem perguntar antes:

1. O registro da demanda e os registros de demandas relacionadas.
2. O card, o pai, o épico e os irmãos: links entre cards, comentários e anexos que mencionem handoff.
3. O changelog e os documentos de handoff do contexto (documentos do Project, repositório de documentos).
4. O Figma: a seção da tela ou do módulo, com notas de versão e frames já marcados como entregues.

Se não achar, pergunte: "Já houve handoff desta tela ou módulo?"

**Tipo de relação com o handoff anterior:**

| Relação | Significa |
|---|---|
| **Primeira entrega** | Nada foi entregue antes sobre isso |
| **Correção** | Muda algo já entregue para ficar como deveria ser |
| **Adição** | Acrescenta sem alterar o que já existe |
| **Alteração** | Muda o comportamento ou o desenho do que já foi entregue |
| **Substituição** | Troca o desenho anterior inteiro |

**Estado do que foi entregue antes:** confira nos cards do dev se está não iniciado, em desenvolvimento, em teste ou concluído. Isso decide o que o dev faz: se ainda não começou, ele ignora a versão antiga; se já implementou, o novo handoff diz o que mudar no código que existe. Se havia trabalho de dev em andamento sobre o mesmo assunto, avise o responsável antes de entregar.

## Mapa para o dev (bloco obrigatório no topo)

Todo handoff abre com este bloco, e o dev costuma entregá-lo a uma IA. Por isso ele é **autoexplicativo e previsível**: sempre os mesmos títulos, o mesmo vocabulário, IDs estáveis e frames com ID. Em correção, adição, alteração e substituição, a tabela "O que mudou" é obrigatória.

```
# Handoff: título curto
ID: HO-CONTEXTO-MODULO-003 | Versão | Data
Tipo: primeira entrega, correção, adição, alteração ou substituição
Destinatário: front, back, back para front ou QA
Cards: chaves relacionadas
Baseado em: HO-CONTEXTO-MODULO-002 (link ou caminho), depois HO-...-001
Estado do que foi entregue antes: não iniciado, em desenvolvimento, em teste ou concluído (cards)

## Leia primeiro (instruções para quem lê com IA)
1. Este handoff não é autônomo: leia antes os handoffs de "Baseado em", do mais antigo ao mais recente.
2. Onde este documento divergir de um anterior, este prevalece, apenas nos itens da tabela "O que mudou".
3. Tudo que não está em "O que mudou" continua valendo como no handoff anterior.
4. Frames marcados como "substituído" ou "removido" não devem ser usados.
5. Item marcado "pendente" não deve ser implementado.

## O que mudou
Tela ou componente | frame antigo (ID) | frame novo (ID) | relação: novo, alterado, removido, substituído ou sem mudança | o que fazer no código | critério de aceite

## O que continua valendo
Lista curta, com os IDs dos frames que não mudaram.

## Pendências e fora do escopo
Cada pendência com responsável.
```

Regras:

- **ID estável:** `HO-` + contexto + módulo + número sequencial. Nunca reutilize um ID.
- **Linha do tempo:** registre cada handoff no changelog do contexto, com a cadeia (001 → 002 → 003) e a relação de cada um.
- **Mesmo vocabulário em todos:** os cinco tipos de relação e os cinco valores da coluna "relação" acima, sem sinônimos.
- **Primeira entrega:** o bloco continua, com "Baseado em: nenhum" e "O que mudou" listando tudo como "novo".
- **No card:** link para o handoff anterior (relação entre cards) e um comentário com o ID do novo.

## O que faz o formato variar

1. **Quem recebe** (o fator que mais pesa).
2. **Primeira entrega ou mudança:** primeira entrega leva o completo (linha de base); as seguintes, só o delta, apontando os frames alterados com ID.
3. **Tipo de demanda:** tela nova ou módulo pede handoff completo, com estados, fluxos e protótipo interativo; correção ou ajuste cabe num delta curto (antes e depois); componente do DS tem a spec como handoff.
4. **Profundidade:** quanto maior o risco, mais entra (passagem ao vivo, checklist de prontidão, design QA).
5. **Onde mora:** comentário no card, arquivo em repositório, anexo ou Drive (`regras-de-escrita-e-entregas.md`).

Proponha o formato ao fim da etapa e peça o ok: "É uma correção para o front, então um delta curto no card basta. Pode ser?"

## Destinatários

| Destinatário | O que recebe |
|---|---|
| **Dev front** | Mapa para o dev, frames com ID, nomes dos componentes iguais aos do MUI, estados, tokens e critérios de aceite. Se ele usa o Claude conectado ao Figma, o Figma precisa estar organizado para isso |
| **Dev back** | Mapa para o dev, contrato de dados (campo, fonte, obrigatoriedade, o que acontece na ausência), regras, mensagens e exceções. Quase não importa o visual |
| **Back para front** | O que o back entrega (endpoints, formatos, limites) e o front precisa saber. Quando o dado vem do back, o registro dele é insumo do front |
| **QA** | Pacote de teste (abaixo) e o modelo de relato |

No perfil do contexto estão os documentos-modelo de cada um (por exemplo, modelo de handoff, changelog e modelo de delta do Conecta, nos documentos do Project). Leia-os antes de montar.

## Pacote de teste (QA)

É derivado do handoff, quase sem trabalho extra:

- **Checklist dos critérios de aceite**, um item por critério, para o teste marcar.
- **Estados e perfis a cobrir:** vazio, carregando, erro, sucesso e cada perfil que muda a tela.
- **Casos de limite**, que são os que mais escapam: muitas colunas, número muito grande, texto longo, lote parcial, lista vazia, valor zero.
- **Referência visual:** os frames com ID, para comparar a tela implementada com o desenho.
- **Fora do escopo e pendências**, para o teste não reportar como defeito o que é decisão em aberto.

### Modelo de relato (do QA para você)

Para o QA preencher quando achar algo. É exatamente o que a skill pede como insumo nas correções vindas de teste (`insumos-por-tipo.md`, tipo 2):

```
O que foi observado:
O que se esperava:
Captura de tela ou passos para reproduzir:
Ambiente e versão testados:
Card da história relacionada:
```

## Checklist de prontidão

Item em falha bloqueia o handoff completo (no delta curto, confira os que se aplicam).

- [ ] Validação do design registrada
- [ ] Todos os estados desenhados (padrão, foco, desabilitado, carregando, erro, vazio, parcial, lote)
- [ ] Textos finais escritos, sem "mensagem apropriada"
- [ ] Componentes e tokens pelos nomes do DS e do MUI, sem valor solto
- [ ] Critérios de aceite escritos e acordados
- [ ] Contrato de dados fechado, quando há back
- [ ] Comportamento responsivo especificado
- [ ] Acessibilidade conferida na revisão
- [ ] Pendências com responsável; fora do escopo declarado
- [ ] Perfis e permissões cobertos, ou a pendência de acesso declarada

## Depois que o dev começa

- **Dúvida de dev:** responda no handoff ou na spec, não só no chat, e versione.
- **Estado que existe no código e não no Figma:** desenhe antes de ir a homologação ou remova do escopo.
- **Implementação divergiu do desenho:** registre no design QA e decida com ela se corrige o código ou atualiza o desenho com justificativa.
- **Passagem ao vivo** (profundidade profunda): percorra com o dev o caminho feliz, um fluxo de erro e o caso de lote. Cada pergunta que surgir revela uma lacuna a corrigir na spec.

### Design QA da implementação

```
# | divergência | severidade | decisão (corrigir código / atualizar desenho) | status
```

Aprovação dela para seguir à homologação do lado do dev, em demandas de profundidade padrão ou profunda.

## Erros comuns

| Erro | Correção |
|---|---|
| Handoff só por link | Mínimo fixo sempre; passagem ao vivo na profunda |
| Entregar com estado faltando | Todos os estados antes |
| Atualizar o handoff durante o trabalho | Só quando ela pedir |
| Uma versão única para todos | O formato segue o destinatário |
| Chamar de primeira entrega sem procurar | Procure a linhagem e confirme com ela |
| Delta sem dizer onde está a base | Todo delta traz "Baseado em" e a instrução "Leia primeiro" |
| Mudar vocabulário ou títulos entre handoffs | Mesmos títulos e mesmos termos, para a IA do dev ler sempre igual |
| Encerrar sem registrar as pendências abertas | Elas são o insumo da próxima rodada |
