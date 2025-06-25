# Monitoramento e Entrega Contínua

![Diagnostic Workflow Status](https://img.shields.io/github/actions/workflow/status/Rafaelrs21/rafael_santiago_DR3_AT/diagnostic.yml?label=diagnostic&logo=github&style=flat-square)


Este projeto visa automatizar a verificação de serviços como parte de uma pipeline de entrega contínua.

---

## Git na Entrega Contínua

O Git é essencial na entrega contínua pois permite:

- Versionamento de código com histórico completo
- Controle de alterações com branches e merges
- Marcação de versões estáveis com tags

### Branches

Branches são como "cópias" do seu código que você pode modificar sem afetar o código principal.  
Elas permitem que várias pessoas trabalhem em funcionalidades, correções de bugs ou novas configurações de forma isolada.

Por exemplo:

- A branch `main` normalmente guarda a versão mais estável e pronta para produção do seu projeto.
- Você pode criar uma branch chamada `feature/login` para desenvolver a tela de login. Isso garante que, enquanto você trabalha nessa parte, 
  o restante do projeto continua funcionando normalmente.
- Depois que terminar e testar sua mudança, você pode unir essa branch de volta à principal.

**Vantagens:**

- Trabalho em paralelo sem conflitos
- Código principal protegido contra mudanças instáveis
- Organização clara das tarefas: features, correções, testes, etc

### Tags

Tags são marcadores fixos em pontos importantes da história do projeto, geralmente associados a versões.

Por exemplo:

- `v0.1.0` — primeira versão funcional do projeto
- `v1.0.0` — primeiro grande lançamento
- `v1.0.1` — correção de um pequeno bug

**Vantagens:**

- Facilita o controle de versões e lançamentos
- Útil para fazer deploys ou voltar para uma versão específica

---

## Uso de Variáveis, Secrets e Contextos no GitHub Actions

Neste projeto, utilizamos diferentes tipos de valores dinâmicos nos workflows do GitHub Actions para garantir flexibilidade, 
segurança e reutilização de configurações.

### `env` 

- São definidas no bloco `env:` e passadas ao shell no momento da execução.
- Acessíveis via `$VARIAVEL` Linux/macOS ou `%VARIAVEL%` Windows.
- Exemplo:
  ```yaml
  env:
    APP_ENV: ${{ vars.APP_ENV }}
