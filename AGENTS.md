# Contexto Persistente do Projeto (Codex)

## Objetivo
Manter continuidade de trabalho nas sessões do Codex neste repositório.

## Estado Atual Relevante
- O projeto é um site estático com páginas principais: `index.html`, `prompts.html`, `llm.html`, `exercicios-prompts.html` e `videos.html`.
- A página `videos.html` deve listar vídeos da playlist do CIIA com **thumbnail separado por vídeo**.
- Playlists consideradas em `videos.html`:
  - `https://www.youtube.com/playlist?list=PLRB6VgPZeUc0wMwoz_45LAbFLrSaV1dLN`
  - `https://www.youtube.com/playlist?list=PLRB6VgPZeUc01I4CHrdrQ9FII43W43Ucv`
  - `https://www.youtube.com/playlist?list=PLRB6VgPZeUc19kCVzp8Z4bOgRy_-UqbS7`
- Exibição em `videos.html`: separar por playlist e mostrar os 3 vídeos mais recentes de cada uma (quando houver).
- A ordem exibida em `videos.html` deve ser por **publicação (mais recente primeiro)**.
- Os cards de vídeo devem conter: thumbnail, título, data/hora de publicação e duração.
- Em caso de falha de embed do YouTube (ex.: erro 153), priorizar links diretos com preview em thumbnail.

## Preferências de Edição
- Preservar a identidade visual já existente nas páginas.
- Fazer mudanças objetivas, sem alterar estruturas não relacionadas ao pedido do usuário.
- Ao atualizar a playlist, manter o mesmo padrão visual dos cards em `videos.html`.
