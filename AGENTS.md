# AGENTS.md — HSC Brand Hub

## Project context

This repository contains the public Brand Hub for Haxixe Smoke Club.

Repository:

```text
hsc-brand-hub
```

Production URL:

```text
https://haxixesmokeclub.com
```

Production webroot boundary:

```text
/var/www/brand-hub/current
```

Current production deploy model uses release directories and a `current` symlink:

```text
/var/www/brand-hub/releases/<release-name>
/var/www/brand-hub/current -> /var/www/brand-hub/releases/<release-name>
```

This repository is the brand/static identity surface. It is not the CS2 Portal, not the Player Bunker, not the Auth API, not the Backoffice, and not the ETL.

## Product boundary

The Brand Hub owns the public apex brand surface and identity baseline.

It must not become:

```text
CS2 Portal
Player Bunker
Auth API
Backoffice Admin
Static API v2
ETL runtime
/player/* reverse proxy owner
cutoff controller for /portal/cs2 or /portal/cs2-next
```

Do not add Player Bunker routes, player auth flows, Steam login flows, authenticated dashboard UI, or `/player/*` behavior to this repository unless the human explicitly starts a new approved brand/product architecture task.

Known related surfaces:

```text
/portal/cs2
  current official/legacy CS2 portal path

/portal/cs2-next
  active public canary for Angular CS2 Next and Player Bunker

/player/*
  Auth API-backed Player Auth/Bunker routes reverse-proxied by Hostinger Nginx
```

The Brand Hub may link to other HSC surfaces when requested, but it should not own their runtime behavior.

## Brand identity boundary

This Brand Hub is the central identity reference for HSC.

Other HSC products may reuse tokens, tone, logo usage, and brand language, but should not blindly copy this layout.

The CS2 Portal must remain a player-facing competitive portal, not a dashboard clone and not a visual copy of this homepage.

The Player Bunker must remain a logged-in competitive player area, not a Brand Hub section.

The Backoffice must remain admin/internal, not a Brand Hub section.

## Critical deployment boundary

Never treat the public webroot as a Git working tree.

Do not suggest or run:

```text
git pull inside /var/www/brand-hub
git pull inside /var/www/brand-hub/current
git pull inside /var/www/brand-hub/releases/*
git pull inside any /var/www public webroot
```

Correct deploy flow must be explicit and approved before production changes.

Only publish static site artifacts required by the Brand Hub.

Never publish:

```text
.git
.github
.env
.npmrc
node_modules
package-lock.json unless the project intentionally becomes build-based
source-only files not required by the public site
secrets
private keys
deployment notes containing credentials
```

Do not alter release symlinks, Nginx, DNS, TLS, redirects, or production webroots without an explicit approved runbook.

## Architecture decision policy

Do not make architecture, Nginx, deploy, cutoff, auth, API, ETL, billing, subdomain, or domain-routing decisions independently.

For those topics, stop and ask the human.

Implementation work is allowed only when the task scope is explicit.

## Allowed work

Codex may work on:

```text
static HTML/CSS/JS already in this repo
brand copy
brand layout refinements
image references/assets already approved
README/docs updates
SEO metadata when explicitly requested
robots/sitemap when explicitly requested
small static-site fixes
```

Good tasks include:

```text
fix copy
adjust static layout
improve semantic HTML
improve accessibility
document brand usage
update README
validate no source/runtime leakage
```

## Forbidden work without explicit approval

Do not perform production-sensitive or cross-product work without explicit approval.

Forbidden by default:

```text
deployment changes
release symlink changes
Nginx changes
DNS/TLS changes
Auth API changes
Portal changes
Backoffice changes
ETL changes
/player/* routing
Steam login
Player Bunker UI
billing/subscription UI
new dependencies
build-system conversion
CI/CD changes
production URL/routing changes
```

Do not modify these files or concepts unless the task explicitly asks for it:

```text
.github/**
package.json
package-lock.json
build tooling
deployment scripts
server config
Nginx config
```

Read-only review is allowed when relevant.

## Static asset and SEO rules

Preserve SEO files unless the task explicitly changes them:

```text
robots.txt
sitemap.xml
metadata
canonical links
favicon/logo references
```

Do not remove or rename public assets without checking references.

Do not introduce heavy assets without approval.

Do not include copyrighted third-party assets unless the human explicitly provides usage rights or asks for a placeholder/reference.

## Secret and environment safety

This repository should not require secrets.

Do not create or commit:

```text
.env
.env.local
.env.production
secrets
private keys
tokens
credentials
```

Never hardcode credentials, cookies, API keys, OAuth details, DB URLs, SMTP values, or session values.

If a task appears to need secrets or environment-specific values, stop and ask the human.

## Git workflow

Work on branches after the initial import.

Before finalizing changes, show:

```bash
git status --short
git diff --check
git diff --stat
```

Prefer small commits and focused changes.

Do not commit generated artifacts unless they are intentionally part of the static site.

## Validation

For static changes, validate what is relevant:

```text
git status --short
git diff --check
git diff --stat
manual review of changed HTML/CSS
link/path sanity
asset reference sanity
SEO file sanity if touched
```

If a build system is introduced in the future, do not assume existing deploy flow remains valid. Ask for approval and update docs/runbooks first.

## Relation to other HSC repositories

Canonical project-wide documentation lives in:

```text
hsc-docs
```

Runtime/application owners:

```text
hsc-cs2-portal
  CS2 Next Portal and Player Bunker UI

hsc-auth-api
  Auth API, Admin Auth, Player Auth, Steam auth, Bunker gateway

hsc-cs2-etl
  Static API v2 materialization and competitive stats artifacts

hsc-backoffice-admin
  Admin/internal SPA

hsc-brand-hub
  static public brand surface
```

Do not move responsibilities between repositories without explicit architecture approval.

## General rules

- Keep changes scoped.
- Do not introduce dependencies without approval.
- Do not alter production files directly.
- Do not edit Nginx without an explicit runbook.
- Preserve SEO files unless the task explicitly changes them.
- Preserve the Brand Hub as brand/static surface.
- Do not implement Player Bunker or Portal features here.
- Do not perform cutoff or domain routing changes from this repository.

## Stop and ask when

Stop and ask the human when the task involves:

```text
production deploy
release/current symlink
Nginx
DNS/TLS
domain routing
cutoff between /portal/cs2-next and /portal/cs2
Auth API
/player/* routes
Player Bunker
Steam auth
Backoffice
ETL
billing/subscriptions/entitlements
new dependencies
build-system changes
secrets
large visual redesign
brand positioning changes
```
