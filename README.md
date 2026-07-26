# Chris Birch

> Data engineer — pipelines, warehousing, and the cloud platforms around them.

Most of my data engineering is corporate and lives in private repositories, so it
isn't on this profile. What's here is what I build off the clock: a personal
software ecosystem, treated as production rather than as throwaway projects —
deployed on a homelab, tested, and used every day.

## Selected work

### Platform

- **[ichrisbirch](https://github.com/datapointchris/ichrisbirch)** — personal
  life-management platform and the oldest thing here. FastAPI + PostgreSQL + Vue 3,
  with Redis, a scheduler service, and a Streamlit chat interface behind Traefik:
  tasks, habits, books, projects, events, articles, recipes. It deploys blue/green
  on the homelab, so a push to `main` swaps container sets with zero downtime, and
  `icb` — a Go CLI over the same API — is the front door for scripts and for Claude.
- **[dotfiles](https://github.com/datapointchris/dotfiles)** — one configuration
  tree for macOS, Arch Linux, and WSL, installed from a per-machine manifest.
  Configs are written once in `common/` and overridden only where a platform
  forces it. The installer is built for hostile networks: one download failing
  doesn't abort the run, and the install ends with a report of exactly what's
  missing and how to install it by hand.

### Tools

- **[theme](https://github.com/datapointchris/theme)** — one theme across the whole
  desktop, not just the terminal. Thirty generators write Ghostty, Kitty, Alacritty,
  tmux, Neovim, btop, bat, delta, yazi, waybar, rofi, dunst, hyprlock, VS Code, and
  Firefox from a single `theme apply`, on macOS, Arch/Hyprland, and WSL. It also
  generates or recolors the wallpaper to match, so the machine changes look all at
  once instead of one config at a time.
- **[font](https://github.com/datapointchris/font)** — the same idea for fonts: one
  apply writes every terminal on the machine. Every apply, like, dislike, and
  rejection is logged, so it ranks fonts two ways — by what I said I liked, and by
  hours actually used. The two lists disagree, which is the interesting part.
- **[syncer](https://github.com/datapointchris/syncer)** — checks that every local
  repo is actually pushed before I switch machines. Fetches all repos concurrently,
  classifies each branch (ahead, behind, diverged, gone), and reports what a
  per-machine policy *would* do; acting on it is opt-in. Output is ordered so the
  repos needing attention land at the bottom, next to the prompt, rather than
  scrolling off the top.
- **[todoui](https://github.com/datapointchris/todoui)** — Bubble Tea TUI for
  projects and tasks, on local SQLite with background sync to ichrisbirch. It never
  blocks on the network: changes made while the API is unreachable queue and retry
  themselves, and a pending refresh waits while you're mid-edit instead of moving
  the ground under you.
- **[forge](https://github.com/datapointchris/forge)** — runs commands and managed
  scripts across every repo in a shared registry. The scripts are embedded in the
  binary, so a fresh machine gets the entire library from one `go install` — nothing
  to clone, sync, or symlink first.
- **[toolbox](https://github.com/datapointchris/toolbox)** — answers "what did I
  install six months ago, and why?" Searches a registry of every CLI tool in my
  dotfiles by name, tag, description, and why-I-use-it note, and reads shell
  functions and aliases straight out of the dotfiles source, so the listing can't
  drift from what's installed.
- **[goselfupdate](https://github.com/datapointchris/goselfupdate)** — the `update`
  command for CLIs released with goreleaser: check GitHub, pick the right asset,
  replace the running binary, print the changelog. The core package imports only the
  standard library.

### Apps

- **[meso](https://github.com/datapointchris/meso)** — mobile-first training app.
  Movements compile into workouts, workouts sequence into goal-directed mesocycles,
  sessions get logged against them. Go API + Go CLI + Vue 3. The CLI is a
  first-class surface rather than an afterthought, so Claude can read the real
  session history and help draft the next cycle. Defined as much by what it leaves
  out — no videos, streaks, badges, or motivational copy.
- **[chris-birch](https://github.com/datapointchris/chris-birch)** — my blog,
  [chris-birch.com](https://chris-birch.com). Astro static site with a design system
  ported from ichrisbirch: 14 themes and 14 self-hosted fonts, switchable at
  runtime and applied before first paint so there's no flash of the wrong theme.
- **[timeline](https://github.com/datapointchris/timeline)** — interactive
  historical timeline with relationship mapping (Vue 3).

### Smaller pieces

- **[logsift](https://github.com/datapointchris/logsift)** — LLM-assisted log analysis.
- **[shadows](https://github.com/datapointchris/shadows)** — sync files that live in a git repo but shouldn't be committed.
- **[typos](https://github.com/datapointchris/typos)** — passive typing analyzer; captures real prose keystrokes in Neovim.
- **[sess](https://github.com/datapointchris/sess)** — tmux session manager over live sessions, tmuxinator projects, and defaults.
- **[keymap-align](https://github.com/datapointchris/keymap-align)** — aligns ZMK keymap bindings to the keyboard's physical layout.
- **[markdown-toc.nvim](https://github.com/datapointchris/markdown-toc.nvim)** — generate and auto-update a table of contents.
- **[flexoki-moon-nvim](https://github.com/datapointchris/flexoki-moon-nvim)** — Neovim colorscheme, dark and purple.
- **[webviewrs](https://github.com/datapointchris/webviewrs)** — Rust webview wrapper.

A few larger pieces stay private: a Proxmox homelab, a content-synthesis engine
(`relate`), semantic search across every repo and note I own (`indy`), a
city-research app (`nomad`), and a structured-learning tracker.

## Skills

| Area | Technologies |
| --- | --- |
| **Languages** | Python · SQL · Go · Bash · TypeScript · Scala |
| **Data & pipelines** | PySpark · Polars · pandas · Databricks · Iceberg · Parquet · PostgreSQL |
| **Cloud** | AWS (S3, Redshift, Glue, Lambda, Kinesis, EC2, IAM, RDS, DynamoDB) · Azure (Data Factory, Entra ID, Storage) |
| **Modeling & serving** | dimensional modeling · FastAPI · Flask · REST APIs · CLI-first tooling |
| **Platform** | Linux · Docker · Terraform · Traefik · blue/green deploys · git-based workflows |
