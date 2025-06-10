
Este projeto visa automatizar a verificação de serviços como parte de uma pipeline de entrega contínua.

## Git na Entrega Contínua

O Git é essencial na entrega contínua (CI/CD) pois permite:
- Versionamento de código com histórico completo
- Controle de alterações com branches e merges
- Marcação de versões estáveis com tags

### Branches

Branches permitem trabalhar em features, correções e configurações de forma isolada, sem impactar a base principal (ex: `main`, `develop`, `ci/setup`).

### Tags

Tags são usadas para marcar versões específicas do projeto. Por exemplo, `v0.1.0` representa a primeira versão funcional.

---

## ⚙️ Uso de Variáveis, Secrets e Contextos no GitHub Actions

No projeto, utilizamos três tipos de valores dinâmicos nos workflows:

### 🔹 `env`
- Variáveis de ambiente passadas para o shell no momento da execução.
- Acessadas dentro dos scripts como `$VARIAVEL`.
- Exemplo de uso:
  ```yaml
  env:
    APP_ENV: ${{ vars.APP_ENV }}

