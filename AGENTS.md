# AGENTS.md — HSC Brand Hub

## Project context

This repository contains the public Brand Hub for Haxixe Smoke Club.

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

## Critical deployment boundary

Never treat the public webroot as a Git working tree.

Do not suggest or run:

```text
git pull inside /var/www/brand-hub
git pull inside /var/www/brand-hub/current
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
```

## Architecture decision policy

Do not make architecture, Nginx, deploy, cutover, or domain-routing decisions independently.

For those topics, stop and ask the human.

Implementation work is allowed when the task scope is explicit.

## Brand identity boundary

This Brand Hub is the central identity reference for HSC.

Other HSC products may reuse tokens, tone, logo usage, and brand language, but should not blindly copy this layout.

The CS2 Portal must remain a player-facing competitive portal, not a dashboard clone and not a visual copy of this homepage.

## Git workflow

Work on branches after the initial import.

Before finalizing changes, show:

```text
git status --short
git diff --stat
```

Prefer small commits and focused changes.

## General rules

* Keep changes scoped.
* Do not introduce dependencies without approval.
* Do not alter production files directly.
* Do not edit Nginx without an explicit runbook.
* Preserve SEO files unless the task explicitly changes them.
