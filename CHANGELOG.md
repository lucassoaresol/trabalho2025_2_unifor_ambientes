# Changelog

Todas as mudanças notáveis neste repositório são documentadas neste arquivo.

## [0.1.0] - 2025-10-06
### Added
- Versão inicial do projeto (release v0.1.0).
- Adicionado workflow de CI em `.github/workflows/ci.yaml` para:
  - Processar PRs aprovadas automaticamente.
  - Detectar tipo de branch (feature/bugfix/release/hotfix) e executar ações específicas.
  - Fazer merge automático de feature/bugfix, e de releases/hotfixes para `main` com criação de tag e release via `gh`.
  - Sincronizar a branch de desenvolvimento (`dev` ou `development`) com `main` após release/hotfix.
- `README.md` inicial (documentação básica do repositório).

### Changed
- Nada nesta release.

### Fixed
- Nada nesta release.

### Notes
- A lógica de release/tag é implementada no workflow de CI e espera branchs nomeadas como `release/X.Y.Z` ou `hotfix/X.Y.Z` (formato semântico X.Y.Z). Se o nome da branch não obedecer esse padrão, o workflow falhará com erro explícito.
- O workflow usa o CLI `gh` e o token `GITHUB_TOKEN` para operar (merge automático, criação de release). Garanta que a conta/runner tem permissões apropriadas.

### Verificação rápida
1. Conferir o workflow: `.github/workflows/ci.yaml` — campos principais:
   - `pull_request_review` trigger
   - cheque de aprovação (`approved`) e detecção de tipo de branch
   - passos para `processar release` e `processar hotfix` que criam tag e release
2. Verificar `README.md` para instruções de uso do projeto.
3. Conferir se o branch de release usado para gerar esta versão seguiu a convenção `release/0.1.0`.

### Como usar este changelog
- Este arquivo segue o estilo "Keep a Changelog" resumido para facilitar leitura de releases.
- Para gerar notas de release no GitHub, copie a seção `## [0.1.0] - 2025-10-06` como corpo da Release.

---

Se quiser, eu posso:
- Gerar automaticamente o corpo completo da Release no formato do GitHub (texto pronto para colar),
- Incluir uma seção `Unreleased` para futuras mudanças,
- Extrair commits/PRs reais para preencher entradas "Added/Fixed" com mensagens reais (preciso de permissão para acessar histórico de commits ou você pode me fornecer um log `git log --pretty=oneline`).

Resumo das alterações: criei `CHANGELOG.md` com o registro da release `0.1.0` e instruções de verificação.