# claude-mods

Catálogo dos meus mods de Claude Code. Adicione uma vez e escolha quais instalar. Cada mod mora no próprio repositório, com código, README e histórico próprios; este repositório só lista onde cada um está.

## Mods

| Mod | O que faz |
| --- | --- |
| [context-bar](https://github.com/iagodemacedo/context-bar) | Card acima do prompt com o uso da janela de contexto, limites de uso, custo da sessão e handoff com uma tecla |
| [query-pane](https://github.com/iagodemacedo/query-pane) | Painel lateral com as queries do AWS Athena: dados escaneados, custo, alertas, status da AWS e prévia do resultado |

## Instalar

1. Adicione o catálogo, uma vez, no terminal:

```bash
claude plugin marketplace add iagodemacedo/claude-mods
```

2. Instale os mods que quiser:

```bash
claude plugin install query-pane@iagodemacedo-mods
```

```bash
claude plugin install context-bar@iagodemacedo-mods
```

Instala no escopo de usuário: o mod vale para toda sessão nova, no terminal e na aba Code do app desktop. Abra uma sessão nova depois de instalar.

Dentro de uma sessão no terminal, `/plugin` também lista os mods do catálogo para escolher. O `/plugin` não existe na aba Code do app desktop: instale uma vez pelo terminal e o desktop passa a usar.

Cada mod continua instalável sozinho pelo próprio repositório (`--marketplace iagodemacedo/<mod>`), então os comandos antigos seguem valendo. Use um caminho ou o outro para cada mod, não os dois, para não carregar o mesmo mod duas vezes.

## Atualizar

```bash
claude plugin marketplace update iagodemacedo-mods
```

```bash
claude plugin update query-pane
```

## Adicionar um mod ao catálogo

1. Publique o mod no repositório dele, com `version` no `.claude-plugin/plugin.json`.
2. Acrescente uma entrada em `.claude-plugin/marketplace.json`:

```json
{
  "name": "<mod>",
  "source": { "source": "github", "repo": "iagodemacedo/<mod>" },
  "description": "<uma linha>",
  "homepage": "https://github.com/iagodemacedo/<mod>"
}
```

3. Acrescente a linha na tabela acima e rode `claude plugin validate .` antes do commit.

A cada release de um mod, suba o `version` no `plugin.json` dele; é por ela que quem já instalou recebe a atualização.

## Licença

MIT
