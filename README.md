# Software Archaeology — raylib

> CSI412 – Engenharia de Software I (UFOP/DECSI) · Semestre 2026/2 · Prof. Igor Muzetti Pereira

## Integrantes
- [PREENCHER: nome 1]
- [PREENCHER: nome 2]

## Software analisado
- **raylib** — biblioteca C (C99) para programação de jogos, ferramentas e aplicações gráficas.
- Projeto original: https://github.com/raysan5/raylib
- Release analisada: **6.2** (tag `6.2`, commit `0256645`, publicada em 15/out/2026). Código de `master` consultado em 01/nov/2026.
- Licença: zlib/libpng (sem modificações).

## Objetivo do trabalho
Investigar o raylib com base em evidências (releases, issues, wiki, documentação), reconstruir requisitos e modelos UML,
propor uma evolução ancorada em uma issue real e implementar experimentalmente uma pequena intervenção em fork próprio.

## Resumo da proposta de evolução
Issue upstream **#5978** — `[rlsw] LoadRenderTexture() framebuffer is INCOMPLETE_ATTACHMENT unless SW_FRAMEBUFFER_DEPTH_TYPE == D32`.
No renderizador por software (`rlsw`), compilar com profundidade `D8`/`D16` (útil em hardware restrito) faz `LoadRenderTexture()`
produzir framebuffer incompleto. Proposta: coagir o formato de profundidade ao formato compilado em `swTexStorage2D()`,
emitir um aviso de log e cobrir com teste de completude para D8/D16/D32. Detalhes em `05-evolucao/` e `06-implementacao/`.

## Como executar a intervenção
[PREENCHER após implementar — ver `06-implementacao/plano-implementacao.md`]

## Estrutura
| Pasta | Conteúdo (seção do enunciado) |
|---|---|
| `01-discovery/` | O que é o software, personas e JTBD (3.1) |
| `02-processo/` | Evolução e processo de desenvolvimento (3.2) |
| `03-requisitos/` | Requisitos, histórias de usuário e cenários (4) |
| `04-uml/` | 5 diagramas UML + correspondências com o código (5) |
| `05-evolucao/` | Proposta, MVP e análise de impacto (6) |
| `06-implementacao/` | Plano, patch, testes, modelo de PR e revisão (7) |
| `07-etica/` | Questões éticas (8) |
| `08-ia/` | Registro de uso de IA — `ia.md` (9) |

**Leia primeiro:** `PENDENCIAS.md` (o que a dupla ainda precisa verificar e fazer).
