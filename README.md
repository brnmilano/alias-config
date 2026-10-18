# alias-config

Aliases e abreviações do `~/.bashrc` usados no dia a dia.

Para usar, copie as linhas desejadas para o `~/.bashrc` e rode `source ~/.bashrc`.

## Projetos

### PMASWeb 2.0 (frontend e backend)

| Alias | O que faz |
| --- | --- |
| `start-pmas-front` | Entra em `~/work/frontend`, abre o VS Code e o Claude |
| `start-pmas-back` | Entra em `~/work/backend`, sobe o Docker de dev e abre o VS Code |
| `finish-pmas-dk` | Derruba o Docker de dev do backend (funciona de qualquer pasta) |

```bash
alias start-pmas-front='cd ~/work/frontend && code . && claude'
alias start-pmas-back='cd ~/work/backend && docker-compose -f docker-compose.dev.yml up -d && code .'
alias finish-pmas-dk='docker compose -f ~/work/backend/docker-compose.dev.yml down'
```

### SEDS-UI (biblioteca de componentes com Storybook)

| Alias | O que faz |
| --- | --- |
| `start-seds-ui` | Entra em `~/work/seds-ui`, abre o VS Code e o Claude |

```bash
alias start-seds-ui='cd ~/work/seds-ui && code . && claude'
```

### CONSEAS (monorepo)

| Alias | O que faz |
| --- | --- |
| `start-conseas` | Entra em `~/work/conseas`, sobe o Docker de dev, abre o VS Code e o Claude |
| `finish-conseas-dk` | Derruba o Docker de dev (funciona de qualquer pasta) |

```bash
alias start-conseas='cd ~/work/conseas && docker compose -f docker-compose.dev.yml up -d && code . && claude'
alias finish-conseas-dk='docker compose -f ~/work/conseas/docker-compose.dev.yml down'
```

### Auxílio Aluguel (monorepo)

| Alias | O que faz |
| --- | --- |
| `start-aa` | Entra em `~/work/auxilio-aluguel`, sobe o Docker de dev, abre o VS Code e o Claude |
| `restart-aa` | Reinicia os containers de dev (funciona de qualquer pasta) |
| `down-aa` | Derruba o Docker de dev (funciona de qualquer pasta) |

```bash
alias start-aa='cd ~/work/auxilio-aluguel && docker compose -f docker-compose.dev.yml up -d && code . && claude'
alias restart-aa='docker compose -f ~/work/auxilio-aluguel/docker-compose.dev.yml restart'
alias down-aa='docker compose -f ~/work/auxilio-aluguel/docker-compose.dev.yml down'
```

`restart-aa` aceita o nome de um serviço no fim para reiniciar só ele
(ex.: `restart-aa mailpit`). Os serviços são `auxilio-aluguel-db`,
`auxilio-aluguel-frontend`, `auxilio-aluguel-php-cli`, `auxilio-aluguel-nginx`
e `mailpit`.

> Os aliases `finish-*`, `down-aa` e `restart-aa` usam caminho absoluto para o
> arquivo do compose. Com caminho relativo (`-f docker-compose.dev.yml`) eles só
> funcionam de dentro da pasta do projeto.

## Abreviações do Git

| Alias | Comando |
| --- | --- |
| `gst` | `git status --short` |
| `ga` | `git add` |
| `gcm` | `git commit -m` |
| `gpl` | `git pull` |
| `gps` | `git push` |
| `gco` | `git checkout` |
| `gcb` | `git checkout -b` |
| `gd` | `git diff` |
| `gl` | `git log --oneline -10` |

```bash
alias gst='git status --short'
alias ga='git add'
alias gcm='git commit -m'
alias gpl='git pull'
alias gps='git push'
alias gco='git checkout'
alias gcb='git checkout -b'
alias gd='git diff'
alias gl='git log --oneline -10'
```
