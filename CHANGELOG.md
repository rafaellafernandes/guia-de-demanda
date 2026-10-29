# Changelog

## 1.0.0 (2026-10-29)

Primeira versão genérica, sucessora da skill `guia-de-demanda-tce`.

- Núcleo independente de contexto, com perfis em `references/contextos/` (Conecta e Design System TCE) e um modelo para contextos novos.
- Classificação da demanda por tipo e profundidade (leve, padrão, profunda), com sinais de reclassificação.
- Revisão do design com severidade (Alta, Média, Baixa).
- Validação do design com quem aprova (requisitos, clientes ou gestão), antes do handoff.
- Handoff sempre presente, com mínimo fixo e formato por destinatário (front, back, back para front e QA), incluindo pacote de teste e modelo de relato.
- Linhagem entre handoffs: procurar handoff anterior, classificar a relação (primeira entrega, correção, adição, alteração, substituição) e abrir todo handoff com um mapa para o dev (ID, "Baseado em", "Leia primeiro", "O que mudou"), pensado para o dev entregar a uma IA.
- Registro curto por demanda.
- Regras de escrita (Jira, Figma, repositórios) e destinos de entrega.
- Fluxo e status do Jira do Conecta conferidos em 2026-10-29, com os cuidados do board.
- Planos futuros registrados: visão da esteira, pesquisa, destinos padrão, acordos do time e validação do caminho do protótipo ao Figma.
