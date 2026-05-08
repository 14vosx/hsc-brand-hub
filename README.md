# hsc-brand-hub

Hub público da marca HSC, responsável pela superfície institucional do apex `haxixesmokeclub.com`, identidade visual, linguagem de marca e assets públicos essenciais.

## Papel no ecossistema HSC

Este repositório mantém a superfície pública de marca no domínio apex `https://haxixesmokeclub.com`.

O Brand Hub apresenta o HSC como clube/marca e serve como referência prática para identidade visual, tom de voz e linguagem institucional. Ele complementa o Portal CS2, mas não substitui o produto player-facing competitivo.

Este repositório não é:

- o Portal CS2;
- o Backoffice;
- a Auth API;
- o ETL;
- a documentação canônica completa do ecossistema.

## Escopo

- Homepage estática do Brand Hub.
- SEO básico via `robots.txt` e `sitemap.xml`.
- Identidade visual e linguagem de marca.
- Baseline de marca em `docs/brand-identity-baseline.md`.
- Assets públicos necessários ao site estático, se existirem.

## Fora de escopo

- Rankings, partidas, mapas e Seasons do Portal CS2.
- Administração interna.
- Autenticação.
- Geração da Static API v2.
- Deploy de Auth API, Backoffice ou Portal.
- Configuração de Nginx, DNS ou TLS sem runbook explícito.

## Estrutura principal

- `index.html`: página principal estática do Brand Hub.
- `robots.txt`: diretivas básicas para crawlers.
- `sitemap.xml`: sitemap público do site.
- `docs/brand-identity-baseline.md`: baseline local de identidade visual e linguagem de marca.
- `AGENTS.md`: regras operacionais críticas para trabalho neste repositório.

## Desenvolvimento local

Como o site é estático e hoje não usa `package.json`, framework, build tool ou dependências, a revisão local pode ser feita abrindo `index.html` diretamente no navegador.

Opcionalmente, para servir a pasta com um servidor estático local simples:

```bash
python3 -m http.server 8080
```

Esse comando é apenas local, não representa produção e não adiciona dependência ao repositório.

## Publicação / deploy boundary

A produção usa release directories e um symlink `current`:

```text
/var/www/brand-hub/releases/<release-name>
/var/www/brand-hub/current
```

O webroot produtivo é:

```text
/var/www/brand-hub/current
```

Nunca trate `/var/www/brand-hub` ou `/var/www/brand-hub/current` como Git working tree.

Nunca rode `git pull` dentro de webroot público.

Publique somente os artefatos estáticos necessários ao Brand Hub.

Não publique:

- `.git`
- `.github`
- `.env`
- `.npmrc`
- `node_modules`
- `package-lock.json`, salvo se o projeto futuramente virar build-based por decisão explícita
- arquivos source-only não necessários ao site público

Deploy real exige aprovação e runbook explícito.

## Relação com outros repositórios

- `hsc-cs2-portal`: produto player-facing CS2; pode reutilizar identidade, mas não deve copiar layout cegamente.
- `hsc-cs2-etl`: gera Static API v2; sem dependência direta do Brand Hub.
- `hsc-auth-api`: Auth/content API; sem dependência direta do Brand Hub.
- `hsc-backoffice-admin`: UI administrativa; separado do Brand Hub.
- `hsc-docs`: documentação canônica do ecossistema e decisões.
- `hsc-brand-hub`: referência de marca e superfície apex.

## Segurança

- Não commitar segredos.
- Não adicionar `.env`.
- Não publicar arquivos internos.
- Preservar SEO files salvo tarefa explícita.
- Respeitar `AGENTS.md`.
- Não tomar decisões de Nginx, cutover ou domínio sem aprovação.

## Documentação relacionada

Local:

- `docs/brand-identity-baseline.md`

Canônica em `hsc-docs`:

- `docs/00-governance/hsc-repositories-map.md`
- `docs/03-portal-estatico/brand-hub-root-product-and-surface-decisions.md`
- `docs/03-portal-estatico/brand-hub-root-publishing-and-cutover-runtime.md`
- `docs/01-infra-hostinger/nginx-static-serving.md`
- `docs/03-portal-estatico/nginx-publishing-cache.md`

## Workflow

- Trabalhar em branch.
- Preferir PRs pequenos e focados.
- Antes de finalizar:

```bash
git diff --check
git diff --stat
git status --short
```

- Para mudanças visuais, validar manualmente a página.
- Não fazer deploy como parte de PR de README.
