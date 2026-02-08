# PRD — Portal CIIA Workshops (Site Estático)

## Resumo
Portal estático para disponibilizar todo o material utilizado nas aulas dos workshops do CIIA/MPPA. O foco é acesso simples, organizado e confiável para Promotores, Assessores e Servidores do MPPA.

## Problema
O material de apoio dos workshops está disperso e não há um ponto único e organizado para consulta posterior pelos participantes.

## Objetivo
Centralizar e disponibilizar todos os materiais das aulas dos workshops em um site estático de fácil navegação.

## Público-alvo
Promotores, Assessores e Servidores do MPPA.

## Métrica de sucesso
Taxa de envio/realização dos formulários de avaliação do curso (ex.: % de participantes que respondem ao formulário após o workshop).

## KPIs adicionais
- % de acesso a `documentos.html` e `videos.html` por sessão.
- Cliques em PDFs (taxa por documento e total).
- Cliques em vídeos (taxa por playlist e total).
- Tempo médio na página (`documentos.html` e `videos.html`).
- Taxa de retorno (usuários que voltam ao portal em até 30 dias).

## Observabilidade
- Os KPIs dependem de instrumentação externa (ex.: analytics ou logs de servidor). Sem isso, as métricas devem ser tratadas como estimativas.

## Escopo (MVP)
- Hub central de navegação (`index.html`).
- Biblioteca de prompts (`prompts.html`) com cópia rápida.
- Simulador didático de LLM (`llm.html`).
- Vídeos organizados por playlist com cards (3 mais recentes por playlist) (`videos.html`).
- Documentos em PDF com thumbnails, resumo e link direto (`documentos.html`).
- Navegação consistente entre páginas principais.

## Fora de escopo
- Backend, login, personalização por usuário.
- Analytics avançado.
- Busca global nos materiais.
- Upload dinâmico de conteúdo.

## Requisitos funcionais
1. Menu e rodapé sincronizados entre páginas principais.
2. `videos.html` deve separar por playlist e mostrar 3 vídeos mais recentes, ordenados por publicação.
3. Cards de vídeo devem mostrar thumbnail, título, data/hora e duração.
4. `documentos.html` deve listar todos os PDFs de `docsworkshop/`, com thumbnail, título e resumo.
5. Links diretos para vídeos (evitar embed em caso de erro 153).

## Requisitos não funcionais
- Site estático (HTML/CSS/JS vanilla).
- Carregamento rápido em desktop e mobile.
- Acessibilidade básica: labels, alt texts, links claros.
- Sem dependência de backend.

## Riscos
- Atualização manual de playlists e documentos pode ficar defasada.
- Falhas de embed do YouTube.
- KPIs sem instrumentação podem não ser medidos com precisão.

## Mitigações
- Processo simples de atualização manual (checklist de manutenção).
- Preferir links diretos com thumbnails locais em `videos.html`.

## Dependências
- Conteúdo atualizado em `docsworkshop/`.
- Thumbnails locais em `img/`.
- URL do formulário de avaliação do curso (externo ao site).

## Experiência do usuário (alto nível)
- Entrada no `index.html` com acesso rápido a todas as seções.
- Consulta rápida a materiais e links diretos para PDFs e vídeos.
- Interação simples, sem fricção.

## Critérios de aceitação
- Todos os PDFs de `docsworkshop/` aparecem em `documentos.html`.
- Cada playlist em `videos.html` exibe os 3 vídeos mais recentes com dados completos.
- Navegação principal consistente em todas as páginas.

## Checklist operacional de atualização
### Vídeos (`videos.html`)
1. Verificar as 3 playlists definidas no projeto.
2. Identificar os 3 vídeos mais recentes de cada playlist (ordem por data de publicação).
3. Atualizar cards com:
   - título
   - data/hora de publicação
   - duração
   - link direto do vídeo
4. Gerar/atualizar thumbnails locais em `img/thumb-<VIDEO_ID>.svg`.
5. Atualizar o contador de playlist (ex.: "3 de 6 vídeos").
6. Validar que todos os links abrem corretamente.

### Documentos (`documentos.html`)
1. Verificar a pasta `docsworkshop/` e listar PDFs atuais.
2. Para cada PDF:
   - confirmar título e resumo curto no card
   - conferir link direto para o arquivo correto
3. Atualizar/gerar thumbnail em `img/doc-thumb-*.svg`.
4. Atualizar o contador total de documentos exibido na página.
5. Validar que todos os PDFs abrem corretamente.

## Marcos (sem prazo)
1. Revisão de conteúdo atual e validação do acervo.
2. Verificação de navegação, links e responsividade.
3. Publicação/atualização final.
