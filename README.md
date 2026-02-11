# CIIA Workshops - Site Estático

## 1. Objetivo
Este repositório contém o site estático de apoio aos workshops do CIIA/MPPA sobre IA generativa. Foi construído integralmente com o Codex/ChatGPT-5.3.
O conteúdo principal inclui:
- trilha introdutória e conceitual;
- biblioteca de prompts;
- simulador didático de LLM;
- playlists de vídeos;
- biblioteca de documentos em PDF.

## 2. Stack
- Frontend: `HTML + CSS + JavaScript` (vanilla)
- Backend: não há
- Build/empacotamento: não há
- Testes automatizados: não há

## 3. Estrutura Atual
- `index.html`: página principal (hub do conteúdo).
- `prompts.html`: biblioteca de prompts com botões de cópia.
- `llm.html`: simulador didático de funcionamento de LLM.
- `videos.html`: playlists do YouTube com cards estáticos (3 mais recentes por playlist), thumbnails locais em `img/thumb-*.svg` e links diretos.
- `documentos.html`: cards de documentos com thumbnail em `img/doc-thumb-*.svg`, resumo curto e link direto para PDF.
- `exercicios-prompts.html`: página de apoio/exemplo (não está no menu principal).
- `docsworkshop/`: PDFs exibidos em `documentos.html`.
- `docs/`: arquivos-fonte em Word.
- `img/`: logos e thumbnails (`thumb-*.svg` e `doc-thumb-*.svg`).
- `promptsApoioClaude/`: material de apoio para atualização de vídeos.

## 4. Navegação Principal
Menu padronizado (topo e rodapé) nas páginas principais:
- `index.html`
- `prompts.html`
- `llm.html`
- `videos.html`
- `documentos.html`

Observação: `exercicios-prompts.html` permanece no projeto como material de referência, mas não faz parte da navegação principal.

## 5. Execução Local
Sem build. Basta servir arquivos estáticos:

```bash
cd /home/paulosrl/projetos/ciiaworkshops
python3 -m http.server 8000
```

Acesse:
- `http://localhost:8000/index.html`

## 6. Pontos de JavaScript Relevantes
- `prompts.html`: `copyToClipboard` para copiar prompts.
- `llm.html`: fluxo do simulador (`processWord`, `resolveContext`, base de conhecimento local).
- `exercicios-prompts.html`: `copyToClipboard` para gabaritos (página de apoio).

## 7. Validação Manual Recomendada
1. Navegação entre `index`, `prompts`, `llm`, `videos` e `documentos`.
2. Botões de cópia em `prompts.html`.
3. Fluxo do simulador em `llm.html`.
4. Abertura dos vídeos em `videos.html`.
5. Abertura dos PDFs em `documentos.html`.
6. Responsividade (desktop e mobile).

## 8. Arquitetura (resumo)
```txt
[Browser]
  -> [index.html] (hub)
       -> [prompts.html]
       -> [llm.html]
       -> [videos.html]
       -> [documentos.html]

  -> [prompts.html]
       -> catálogo + cópia de prompts

  -> [llm.html]
       -> simulador local sem backend

  -> [videos.html]
       -> playlists do YouTube com cards estáticos (links diretos + thumbnails locais)

  -> [documentos.html]
       -> lista de PDFs de docsworkshop (cards com thumbnail e resumo)

[docsworkshop/*.pdf]
  -> acervo documental exibido no site

[img/*.svg|*.png]
  -> logos e thumbnails
```

## 9. Manutenção
- Manter este README sincronizado sempre que houver mudança em páginas, navegação ou estrutura de pastas.
- Se novos PDFs forem adicionados em `docsworkshop`, atualizar os cards e o contador em `documentos.html`.
- Ao atualizar `videos.html`, manter 3 vídeos mais recentes por playlist, ordenados por publicação (mais recente primeiro).
- Os cards de vídeo devem conter thumbnail, título, data/hora de publicação e duração.
- Usar links diretos (sem embed) quando houver risco de erro 153.
