# Registro de uso de IA (`ia.md`)

> **Regra do enunciado:** uma resposta gerada por IA não é evidência do projeto. Preencha a coluna "Verificado pela dupla" **apenas depois** de conferir no próprio repositório.

## Ferramenta
Claude (Anthropic) — Sonnet 5.5, interface web, com busca e leitura de páginas web. Sessão de 01/nov/2026.

## Objetivo
Acelerar o levantamento de evidências públicas do raylib e produzir um *rascunho estruturado* de todas as seções do trabalho.

## Principais prompts
1. Enunciado anexado (PDF) + "realize esse trabalho todo seguindo todas as orientações" + link do repositório.
   *(A dupla deve acrescentar aqui os prompts que usar nas revisões e ajustes.)*

## O que a IA fez (e como)
Leu, por busca web: página principal do repositório, `CONTRIBUTING.md`, `ROADMAP.md`, página de Releases (4.5 a 6.2), lista de issues abertas, issue #5978 e wiki *raylib architecture*.
**Não** teve acesso ao código-fonte, ao histórico de commits nem a PRs. **Não** compilou nem executou nada.

## Resultados utilizados (rascunhos) e verificação
| Resultado | Origem | Verificado pela dupla? | Como verificar |
|---|---|---|---|
| Descrição, licença, funcionalidades (3.1) | README | [ ] | Ler README e LICENSE |
| Cinco eventos de evolução com hashes | Página de releases | [ ] | Abrir cada commit/tag, ler notas |
| Mapeamento para processos | Interpretação da IA sobre práticas observadas | [ ] | Discutir; abrir PRs/issues recentes e observar revisão |
| Ausência de testes automatizados | Árvore de arquivos da raiz | [ ] | Buscar `test` em `src/` e `examples/`; ver workflows em `.github/` |
| Diagramas e correspondências | Wiki + issue #5978 + conhecimento geral | [ ] | Abrir cada arquivo citado; ajustar diagramas |
| Proposta (#5978) e causa-raiz | Texto da issue | [ ] | Abrir `rlsw.h` e `rlgl.h`, localizar as funções citadas |
| Plano de implementação | Texto da issue | [ ] | Executar e preencher a tabela antes/depois |

## Resultados descartados
[PREENCHER — ex.: sugestões que a dupla recusou e por quê.]

## Limitações conhecidas da IA nesta sessão
- Personas são proto-personas inferidas, sem entrevistas.
- Detalhes internos do código (campos de structs, sequência exata de chamadas) vieram de conhecimento geral e estão marcados "(verificar)".
- A issue #5978 pode ter mudado (PR vinculado, fechada) desde a consulta.
