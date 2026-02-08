# CIIA Workshops - Onboarding

## 1. Objetivo do sistema
Este repositório contém um site **estático** de apoio a workshops do CIIA/MPPA sobre IA generativa.

O sistema reúne:
- trilha de conteúdo introdutório e metodológico;
- biblioteca prática de prompts;
- exercícios guiados com gabaritos;
- simulador didático de funcionamento de LLM.

## 2. Stack e características
- **Frontend:** HTML + CSS + JavaScript vanilla.
- **Backend:** não há.
- **Build/empacotamento:** não há.
- **Testes automatizados:** não há.

## 3. Estrutura de pastas
- `index.html`: página principal (hub do conteúdo).
- `prompts.html`: biblioteca de prompts e material prático.
- `exercicios-prompts.html`: exercícios pós-workshop com gabaritos.
- `llm.html`: simulador didático de tokenização/contexto/classificação.
- `docs/`: documentos-fonte em Word (`GEMINI-Prompt*.docx`).
- `img/`: logos PNG.

## 4. Pontos de entrada e navegação
Ponto de entrada principal:
- `index.html`

Navegação entre módulos:
- `index.html` -> `prompts.html`
- `index.html` -> `llm.html`
- `index.html` -> `exercicios-prompts.html`

Entradas de comportamento JavaScript relevantes:
- `index.html`: bootstrap de UI e interações visuais.
- `prompts.html`: função de cópia de prompts (`copyToClipboard`).
- `exercicios-prompts.html`: função de cópia de gabaritos.
- `llm.html`: fluxo principal do simulador (`processWord`, `resolveContext`, `moveToGroup`).

## 5. Como executar localmente
Como não há build, basta servir arquivos estáticos.

```bash
cd /home/paulosrl/projetos/ciiaworkshops
python3 -m http.server 8000
```

Abra no navegador:
- `http://localhost:8000/index.html`

## 6. Testes e validação
Não existe suíte de testes automatizados neste momento.

Validação recomendada (manual):
1. Navegação entre páginas pelo menu.
2. Botões de cópia em `prompts.html`.
3. Botões de cópia em `exercicios-prompts.html`.
4. Fluxo completo do simulador em `llm.html`.
5. Responsividade básica (desktop/mobile).

## 7. Ordem de leitura recomendada (primeiros 10 blocos)
1. `index.html` (entrada e contexto do produto)
2. seção POEMA em `index.html` (núcleo metodológico)
3. script final de `index.html` (interações globais)
4. base de conhecimento em `llm.html`
5. função principal `processWord` em `llm.html`
6. catálogo de prompts em `prompts.html`
7. seção POEMA aplicada em `prompts.html`
8. função `copyToClipboard` em `prompts.html`
9. seção de exercícios em `exercicios-prompts.html`
10. função de cópia em `exercicios-prompts.html`

## 8. Arquitetura (texto)
```txt
[Browser]
  -> [index.html] (hub)
       -> links para [prompts.html], [llm.html], [exercicios-prompts.html]
       -> JS: navegação/efeitos de interface

  -> [prompts.html]
       -> catálogo de prompts
       -> utilitário de cópia (Clipboard API + fallback)
       -> links externos (ChatGPT, Claude, Gemini, Copilot)

  -> [exercicios-prompts.html]
       -> exercícios + gabaritos
       -> utilitário de cópia

  -> [llm.html]
       -> simulador local sem backend
       -> módulos internos: llmKnowledgeBase, contextKeywords,
          resolveContext(), processWord(), moveToGroup()

[docs/*.docx]
  -> fonte editorial (não executada em runtime)

[img/*.png]
  -> ativos de identidade visual
```

## 9. Observações de manutenção
- Parte dos logos está embutida como `data:image/...` dentro dos HTML.
- A pasta `img/` ainda existe com versões PNG dos logos.
- Para facilitar onboarding contínuo, manter este README sincronizado após mudanças de estrutura/fluxo.
