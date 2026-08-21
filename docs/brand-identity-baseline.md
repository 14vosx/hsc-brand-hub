# HSC Brand Identity Baseline

## Contexto

Este documento registra a identidade visual vigente do:

```text
HASH SMOKE CLUB
```

aplicada ao Brand Hub público em:

```text
https://haxixesmokeclub.com/
```

O nome oficial da marca é `HASH SMOKE CLUB`.

A sigla institucional permanece `HSC`.

O domínio `haxixesmokeclub.com` permanece como endereço público atual e não determina a nomenclatura da marca.

---

## Fonte visual vigente

A identidade atual do Brand Hub adota como referência visual a linguagem consolidada pelo:

```text
HSC CS2 Portal
Tema 03
```

A direção vigente é:

```text
black
graphite
ivory
antique gold
```

A geração visual anterior baseada em cyan, Inter e Kumbh Sans não é mais referência para novos desenvolvimentos.

---

## Princípios da identidade

A identidade HSC deve transmitir:

* competição;
* comunidade;
* presença;
* sobriedade;
* atmosfera noturna;
* personalidade própria;
* linguagem premium sem aparência corporativa genérica.

Evitar:

* excesso de elementos decorativos;
* aparência de dashboard administrativo;
* excesso de glow;
* excesso de cores de destaque;
* componentes sem função;
* densidade visual desnecessária.

A marca deve ter presença sem competir com o conteúdo principal da superfície em que estiver aplicada.

---

## Paleta — Tema 03

### Background

```css
--color-bg-base: #000000;
--color-background-top: #0b0c11;
```

### Surfaces

```css
--color-bg-elevated: rgba(40, 42, 58, 0.94);

--color-surface-base: #15161d;
--color-surface-subtle: #1e202b;
--color-surface-strong: #282a3a;
```

### Text

```css
--color-text-main: #f2eee7;
--color-text-muted: #b2ada5;
--color-text-subtle: #77736d;
--color-text-brand: #d8b675;
```

### Gold accents

```css
--color-primary: #c69749;
--color-primary-strong: #d8ad68;

--color-gold-dark: #735f32;
--color-gold-medium: #a98b49;
--color-gold-light: #d7b26e;
--color-gold-light-strong: #e4c58b;
```

### Borders

```css
--color-border-subtle: rgba(242, 238, 231, 0.08);
--color-border-default: rgba(242, 238, 231, 0.16);
--color-border-strong: rgba(242, 238, 231, 0.28);
--color-border-focus: #c69749;
```

O gold principal `#c69749` deve funcionar como acento.

Usos adequados:

* CTA primário;
* marca institucional;
* estados ativos;
* pontos de destaque;
* detalhes de prestígio.

O gold não deve se tornar a superfície dominante da interface.

---

## Tipografia

A identidade vigente utiliza:

```css
--font-display:
  "Chakra Petch",
  ui-sans-serif,
  system-ui,
  sans-serif;

--font-sans:
  "Barlow",
  ui-sans-serif,
  system-ui,
  -apple-system,
  BlinkMacSystemFont,
  "Segoe UI",
  sans-serif;
```

### Chakra Petch

Uso:

* marca;
* headings;
* hero;
* CTA;
* labels de destaque;
* elementos competitivos.

Pesos principais:

```text
500
600
700
```

### Barlow

Uso:

* textos corridos;
* descrições;
* conteúdo auxiliar;
* metadados;
* interfaces de leitura.

Pesos principais:

```text
400
500
600
700
```

---

## Escudo HSC

O asset web oficial vigente é:

```text
img/logo/svg/HSC-shield-primary-gold.svg
```

Características:

* SVG vetorial;
* fundo transparente;
* monocromático;
* gold Tema 03;
* escalável sem perda visual;
* adequado para uso direto na web.

Cor principal:

```text
#c69749
```

Regras:

* não distorcer proporção;
* não rasterizar sem necessidade;
* não adicionar efeitos pesados;
* não substituir por arte genérica;
* preferir o SVG vetorial oficial em superfícies web.

Os antigos SVGs com imagens raster/base64 embutidas foram descontinuados e removidos da árvore atual do repositório.

---

## Brand Hub

O `hsc-brand-hub` é a superfície pública institucional da marca.

Ele não é:

* CS2 Portal;
* Área do Jogador;
* Match Room;
* Auth API;
* Backoffice;
* ETL;
* dashboard administrativo.

Sua função é apresentar o `HASH SMOKE CLUB` e direcionar o visitante ao ecossistema HSC.

---

## Landing page vigente

A homepage atual é intencionalmente minimalista.

Estrutura:

```text
fullscreen CS2 gameplay
+
dark overlay
+
HSC shield
+
HASH SMOKE CLUB
+
COUNTER-STRIKE 2 CLUB
+
ENTRAR NO PORTAL
```

Características:

* viewport inteira;
* zero scroll;
* vídeo em loop;
* sem menu;
* sem seta de scroll;
* sem cards;
* sem footer visual;
* sem seções adicionais;
* um único CTA principal.

O CTA oficial aponta para:

```text
https://haxixesmokeclub.com/portal/cs2
```

---

## Vídeo hero

Asset vigente:

```text
video/hsc-hero-60.mp4
```

Características aprovadas:

* H.264;
* 1920x1080;
* 60 fps;
* sem áudio;
* autoplay;
* muted;
* loop;
* playsinline.

A fluidez de 60 fps é uma decisão intencional para conteúdo de Counter-Strike 2.

Não reduzir para 30 fps apenas para perseguir métricas sintéticas de performance.

Poster:

```text
img/hero/hsc-hero-poster.webp
```

O poster funciona como fallback e first paint antes da reprodução do vídeo.

---

## Composição do hero

O conteúdo institucional permanece no terço superior da viewport.

Objetivo:

* preservar o crosshair;
* preservar o centro de ação;
* evitar cobrir kills e gameplay;
* manter a leitura cinematográfica da cena.

A composição visual vigente é considerada aprovada.

Não deve ser modificada por refinamentos estéticos sem nova decisão explícita.

---

## Overlay

O overlay existe para:

* assegurar contraste;
* integrar gameplay à identidade;
* proteger legibilidade;
* aplicar atmosfera HSC.

Evitar:

* filtro gold pesado;
* tratamento monocromático excessivo;
* overlay que destrua a leitura do gameplay.

O jogo deve continuar reconhecível.

---

## CTA

Texto vigente:

```text
ENTRAR NO PORTAL
```

Destino:

```text
https://haxixesmokeclub.com/portal/cs2
```

O CTA deve permanecer:

* único;
* inequívoco;
* diretamente acionável;
* visualmente destacado sem dominar a composição.

---

## Responsividade

A landing deve preservar o conceito em diferentes viewports.

Cenários já validados:

```text
desktop
390 × 844
360 × 800
844 × 390
```

Requisitos:

* nenhum scroll horizontal;
* nenhum scroll vertical;
* vídeo sem deformação;
* logo íntegro;
* título íntegro;
* subtítulo íntegro;
* CTA íntegro;
* gameplay ainda reconhecível.

Não criar media queries adicionais apenas por preferência estética quando a composição vigente estiver funcional.

---

## Acessibilidade

Requisitos:

* HTML semântico;
* heading principal identificável;
* CTA acessível por teclado;
* foco visível;
* contraste adequado;
* vídeo decorativo oculto de tecnologias assistivas quando apropriado.

Mudanças de acessibilidade não devem alterar desnecessariamente a composição visual aprovada.

---

## SEO

A marca deve aparecer semanticamente como:

```text
HASH SMOKE CLUB
HSC
Counter-Strike 2 Club
HSC CS2
Hash Smoke Club CS2
```

O domínio permanece:

```text
https://haxixesmokeclub.com/
```

A diferença entre o nome atual da marca e o domínio legado é intencional.

Elementos mínimos:

* title;
* meta description;
* canonical;
* robots;
* Open Graph;
* heading principal;
* CTA crawlable.

`robots.txt` e `sitemap.xml` permanecem parte do contrato SEO do Brand Hub.

---

## Relação com o HSC CS2 Portal

Brand Hub e Portal compartilham identidade, mas possuem responsabilidades diferentes.

### Brand Hub

```text
marca
impacto visual
entrada institucional
direcionamento
```

### Portal

```text
competição
jogadores
partidas
mapas
ranking
temporadas
notícias
área do jogador
experiências de match e lobby
```

O Brand Hub não deve reproduzir a estrutura funcional do Portal.

O Portal não precisa reproduzir o layout cinematográfico do Brand Hub.

A identidade é compartilhada.

A arquitetura de produto não é.

---

## Identidade legada descontinuada

Não utilizar como baseline vigente:

```text
Haxixe Smoke Club
cyan como accent principal
#32d1ff
#1da7f2
Kumbh Sans
Inter como tipografia principal HSC
HSC-shield-mono-dark.svg
HSC-shield-mono-light.svg
HSC-shield-primary-accent.svg
```

Esses elementos pertencem à geração visual anterior.

Eles permanecem apenas no histórico Git e nesta seção de rastreabilidade documental.

---

## Regra de evolução

Mudanças na identidade visual não autorizam automaticamente mudanças em:

* Portal;
* Auth API;
* Backoffice;
* ETL;
* Nginx;
* DNS;
* TLS;
* rotas;
* deploy.

Da mesma forma, mudanças técnicas nesses produtos não devem alterar silenciosamente a identidade institucional.

Mudanças estruturais de marca devem ser deliberadas e registradas.