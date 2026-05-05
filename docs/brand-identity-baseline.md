# HSC Brand Identity Baseline

## Contexto

Este documento registra a identidade visual base do Haxixe Smoke Club a partir do Brand Hub publicado em:

```text
https://haxixesmokeclub.com
```

O Brand Hub é a referência central de marca, mas outros produtos HSC não devem copiar seu layout diretamente.

Produtos relacionados, como o Portal CS2 Next, devem reutilizar:

```text
- tokens de cor;
- linguagem de marca;
- atmosfera visual;
- uso do escudo/logo;
- princípios de UI.
```

E devem evitar:

```text
- copiar seções inteiras do Hub;
- replicar o layout da homepage;
- transformar o Portal CS2 em dashboard/admin;
- expor linguagem técnica para usuários finais.
```

## Posicionamento verbal

Frases e conceitos centrais da marca:

```text
Haxixe Smoke Club
Clube antes de servidor.
Tactical Chill.
Competição com identidade.
Clube digital onde competição e resenha coexistem.
```

Tom desejado:

```text
- competitivo;
- comunitário;
- premium;
- noturno;
- direto;
- confiante;
- sem linguagem corporativa genérica.
```

Evitar:

```text
- painel operacional;
- dashboard técnico;
- linguagem de API/cache/sync/build para player;
- excesso de termos administrativos.
```

## Paleta base

### Dark foundation

```css
--hsc-dark-04: #05080b;
--hsc-dark-06: #080c10;
--hsc-dark-08: #0b1015;
--hsc-dark-10: #10161c;
--hsc-dark-12: #141b22;
--hsc-dark-15: #1a232d;
```

Uso esperado:

```text
- fundo principal;
- superfícies elevadas;
- seções alternadas;
- cards;
- overlays sutis.
```

### Cyan accent

```css
--hsc-cyan-50: #e8f8ff;
--hsc-cyan-60: #beefff;
--hsc-cyan-70: #7fe2ff;
--hsc-cyan-80: #32d1ff;
--hsc-cyan-90: #1da7f2;
--hsc-cyan-95: #0e7fd1;
```

Uso esperado:

```text
- ações primárias;
- destaques de ranking;
- estados ativos;
- glows controlados;
- elementos de prestígio competitivo.
```

Não usar cyan em excesso. O acento deve guiar atenção, não dominar a tela.

### Text colors

```css
--hsc-white: #f3f8fb;

--hsc-grey-50: #6f7d89;
--hsc-grey-60: #8896a2;
--hsc-grey-70: #a2afb8;
--hsc-grey-80: #c1cbd2;
--hsc-grey-90: #dce3e8;
--hsc-grey-95: #eef3f6;
```

Uso esperado:

```text
- texto primário: branco frio;
- texto secundário: grey 70/80;
- metadados: grey 50/60;
- nunca deixar metadados competir com placar, ranking ou CTA.
```

## Tokens semânticos recomendados

```css
--color-bg: var(--hsc-dark-06);
--color-bg-deep: var(--hsc-dark-04);
--color-surface: var(--hsc-dark-10);
--color-surface-hover: var(--hsc-dark-12);

--color-text: var(--hsc-white);
--color-text-muted: var(--hsc-grey-70);
--color-text-subtle: var(--hsc-grey-50);

--color-primary: var(--hsc-cyan-90);
--color-primary-bright: var(--hsc-cyan-80);
--color-primary-soft: var(--hsc-cyan-70);
--color-primary-deep: var(--hsc-cyan-95);

--color-border: rgba(255, 255, 255, 0.06);
--color-border-strong: rgba(255, 255, 255, 0.10);
--color-glow-primary: rgba(29, 167, 242, 0.22);
```

## Tipografia

Base atual do Brand Hub:

```css
body: Inter, Arial, Helvetica, sans-serif;
brand/headings: "Kumbh Sans", Inter, Arial, sans-serif;
```

Direção:

```text
- Inter para leitura e tabelas;
- Kumbh Sans para marca, hero e títulos fortes;
- headings com peso alto e espaçamento controlado;
- evitar aparência de admin table-first.
```

## Formas, bordas e profundidade

Tokens observados:

```css
--radius-sm: 12px;
--radius-md: 16px;
--radius-lg: 20px;
--radius-xl: 28px;
--radius-pill: 999px;

--shadow-soft: 0 12px 30px rgba(0, 0, 0, 0.28);
--shadow-strong: 0 24px 80px rgba(0, 0, 0, 0.42);
```

Direção:

```text
- radius mais generoso;
- bordas muito sutis;
- cards translúcidos quando fizer sentido;
- sombras escuras, não coloridas em excesso;
- glow cyan somente para pontos de atenção.
```

## Backgrounds

O Hub usa fundo escuro com gradientes radiais e lineares.

Direção para outros produtos:

```text
- manter atmosfera noturna;
- usar gradientes como profundidade, não decoração gratuita;
- evitar grid técnico que remeta a dashboard;
- usar textura visual com moderação.
```

## Logo e escudo

Assets atuais:

```text
img/logo/svg/HSC-shield-mono-dark.svg
img/logo/svg/HSC-shield-mono-light.svg
img/logo/svg/HSC-shield-primary-accent.svg
```

Observação técnica:

```text
Os SVGs atuais contêm data:image/base64 embutido e são grandes.
Devem ser preservados no baseline inicial, mas precisam de otimização futura em branch própria.
```

Uso recomendado:

```text
- escudo como marca institucional;
- evitar substituir toda identidade por texto "HSC" em caixa;
- usar versão light/accent conforme contraste;
- não distorcer proporção.
```

## Aplicação no Portal CS2 Next

O Portal CS2 Next deve usar esta identidade como base, mas manter personalidade própria.

Objetivo do Portal:

```text
Ser um portal player-facing de competição, partidas, mapas, ranking, seasons e notícias do clube.
```

Não deve parecer:

```text
- dashboard administrativo;
- painel de API;
- relatório técnico;
- cópia da homepage.
```

Direção de UI:

```text
- hero editorial/competitivo;
- placares e rankings como conteúdo principal;
- CTAs claros para partidas, mapas, ranking e seasons;
- linguagem voltada ao jogador;
- dados técnicos escondidos ou secundários;
- status de API apenas em áreas técnicas como /api-smoke.
```

Termos a substituir no Portal quando forem player-facing:

```text
"API online" -> evitar na home pública
"Saúde da API" -> evitar na home pública
"Static API v2" -> usar apenas em debug/api-smoke
"Build local" -> remover da experiência pública
"cache" -> evitar, exceto em documentação técnica
"busca local" -> "buscar jogador", "filtrar partidas", "explorar mapas"
"Panorama operacional" -> "temporada, partidas e rankings do clube"
```

## Season Ranking UI

A UI de Ranking da Season deve destacar:

```text
- Season ativa;
- resumo competitivo;
- pódio Top 3;
- elegibilidade;
- tabela completa;
- regras claras;
- aviso de premiação.
```

Texto aprovado:

```text
Top 3 da Season serão premiados. Premiação será anunciada em breve.
```

Regras que devem aparecer de forma clara:

```text
- ranking baseado apenas nos mapas válidos da Season;
- mapas válidos têm vencedor, pelo menos 12 rounds e end_time dentro da janela da Season;
- para concorrer ao Top 3 premiável:
  - mínimo de 5 mapas válidos;
  - mínimo de 100 rounds jogados.
```

## Princípios finais

```text
Identidade, não cópia.
Competição, não dashboard.
Clube, não sistema.
Dados como experiência, não como debug.
```

