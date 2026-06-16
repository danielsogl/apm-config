# apm-config

Zentrales Producer-Repo für AI-Agent-Primitives (Skills, Hooks, Instructions, Agents, Prompts),
verteilt über [APM](https://github.com/microsoft/apm) an alle Projekt-Repos.

## Pakete

| Paket            | Gültig für                          |
| ---------------- | ----------------------------------- |
| `base`           | **Alle** Repos (globale Standards)  |
| `stayfriends`    | Projekt StayFriends                 |
| `lebensfreunde`  | Projekt Lebensfreunde               |
| `wonda`          | Projekt Wonda                       |
| `multiplatform`  | Projekt Multiplatform               |

Jedes Paket liegt unter `packages/<name>/` und authort seine Primitives in `.apm/`:

```
.apm/
  instructions/   # Always-on-Regeln (an File-Globs gebunden)
  skills/         # mehrteilige Skills (<name>/SKILL.md + assets)
  hooks/          # Lifecycle-Hooks (pre/post events)
  agents/         # benannte Agents
  prompts/        # wiederverwendbare Prompt-Templates
```

## Verwendung im Projekt-Repo

In der `apm.yml` des Projekts das `base`-Paket plus das projektspezifische Paket referenzieren:

```yaml
name: mein-projekt
version: 1.0.0
dependencies:
  apm:
    - git: git@github.com:danielsogl/apm-config.git
      path: packages/base
      ref: main
    - git: git@github.com:danielsogl/apm-config.git
      path: packages/stayfriends
      ref: main
```

Dann:

```bash
apm install
```

## Git-Hooks (lefthook)

Beim Commit wird die APM-Config jedes Pakets mit gestageten Änderungen automatisch
über `apm compile --validate` geprüft ([Docs](https://microsoft.github.io/apm/producer/preview-and-validate/)).
So landen keine kaputten Primitives (Frontmatter/Struktur) im Repo.

Einmalig einrichten (nach dem Clone):

```bash
brew install lefthook   # oder: https://lefthook.dev/installation/
lefthook install        # installiert die Git-Hooks aus lefthook.yml
```

Manuell ausführen:

```bash
lefthook run pre-commit
```

> Voraussetzung: das `apm` CLI muss installiert sein
> ([Installation](https://microsoft.github.io/apm/getting-started/installation/)).

## Versionierung

Repo taggen (`git tag v1.0.0 && git push --tags`) und in den Projekten `ref:` auf den Tag
statt auf `main` pinnen. So können einzelne Projekte unabhängig auf älteren/neueren Versionen bleiben.
