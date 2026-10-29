# Contexto: Figma e Design System TCE

Última revisão: 2026-10-29.

Leia quando a demanda envolver Figma, telas, componentes, Design System ou handoff. Essas regras existem porque tudo o que sai do Figma vira o que o dev front recebe e implementa com MUI; um valor solto ou um nome fora do padrão vira retrabalho.

## Arquivos

- **V2 Conecta:** arquivo das telas do Conecta. O módulo de criação e envio das comunicações devolutivas está nas páginas "💬 CD: Envio" e "💬 CD: Em andamento". No Figma, "módulo" quer dizer uma seção que agrupa frames (ex.: "1 · Telas do fluxo"); frame solto fora de seção não conta como módulo organizado. O link do arquivo ainda não está registrado: peça a ela.
- **⭐ Design System TCE:** fileKey `mn0wkryj2sBHmW412qD2o8`, página "🧩 Componentes". Componente novo do DS é criado aqui, nunca no arquivo do Conecta.
- Antes de qualquer chamada de arquivo do Figma, abra uma sessão para o arquivo e carregue a skill do Figma exigida pela ferramenta.

## Regras em cada tela

1. Informe o nome do frame, com o ID, de tudo o que criar ou alterar.
2. Avise antes de mudar de frame e espere o "sim".
3. Respeite o DS e a spec de tipografia: textos usam as variáveis de tipografia ligadas, nunca valores soltos.
4. A cada tela, veja quais componentes não existem no DS, sugira a criação e a inclusão no documento do DS no Figma. Antes de adicionar um item ao checklist de sugestões do DS, pergunte se ele entra. O checklist é um .md, com o artefato publicado e o link no card CONECTA-18 como registro da atividade.
5. No módulo de devolutivas do jurisdicionado, cada tela deve estar preparada para mudar conforme o perfil (sistema de acesso ainda indefinido).

## Regras do Design System

- O DS é baseado no MUI. O front usa MUI 9.1.1 (`@mui/material`, `@mui/icons-material`, `@mui/system`, Emotion). Nomes de componentes e propriedades no Figma equivalem aos do MUI. Para consultar a documentação do MUI, use o Context7 quando estiver disponível.
- Prefixo `tcece` para tudo que o DS inventa (variáveis, variantes, chaves de tema, propriedades só do Figma). O que espelha o MUI fica sem prefixo e sem usar palavras reservadas do MUI.
- Fontes: Noto Sans na tipografia normal; Atkinson Hyperlegible Next geralmente para textos pequenos ou números.
- Nenhum texto do DS abaixo de 16px.
- Alvos clicáveis: 44px no desktop e 48px no mobile.
- Ícones: os do MUI (Material Icons, estilos Outlined e Filled), na página "Ícones" do arquivo do DS; Icons_TCE é o padrão de uso.
- Foco visível dos componentes mantém amarelo e preto.
- Cor nunca é o único indicador de status.
- Unidades: px no Figma e no protótipo, rem no código, com conversão nas specs.
- As specs seguem Atomic Design (átomos, moléculas, organismos, templates, páginas). Cada spec traz no cabeçalho a data da última atualização e a versão, a camada, de quais specs depende e por quais é usada. Ao atualizar uma spec, confira as relacionadas. Itens marcados "A DECIDIR" não são implementados: pergunte.
- As specs do DS ficam focadas no TCE Ceará; o que é específico do Conecta vai para o handoff do Conecta.
- Onde a spec e o Figma divergirem, a spec vale, exceto nos itens "A DECIDIR".

## Repositórios (só quando ela pedir para versionar)

- `conecta-docs`: specs e handoffs do Conecta. `tce-design-system`: specs gerais do DS (sempre vivas). O `conecta-docs` só referencia o `tce-design-system`.
- Regra fixa: toda alteração começa numa branch nova criada a partir da principal; a principal só muda por pull request mesclado por ela.
- Ela usa o GitHub Desktop e não domina Git. Explique de forma simples o que vai fazer antes de fazer.
