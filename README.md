# HSC Brand Hub

Superfície institucional da marca HSC no domínio apex.

## Papel

O Brand Hub comunica:

- marca;
- identidade visual;
- linguagem;
- entrada institucional;
- links para produtos HSC.

Ele complementa, mas não substitui:

- HSC CS2 Portal;
- Player Area;
- Match Room;
- Backoffice.

## Estado atual do código

O repositório ainda representa uma superfície estática baseada em HTML/CSS.

Existe uma evolução planejada para:

```text
Angular 22
```

com nova identidade/layout já prototipada externamente.

Essa migração é uma frente própria e não faz parte do caminho crítico atual da Match Room.

## Deploy / hosting

Existe contexto operacional recente que precisa ser reconciliado antes de documentar o hosting como definitivo.

Não assumir automaticamente que:

- o webroot atual;
- o método atual de publicação;
- o target futuro VPS/web hosting

são equivalentes.

A decisão de manter web hosting ou consolidar na VPS deve ser tratada em uma frente específica com auditoria runtime.

## Redirects

Regras de redirect relacionadas ao ecossistema podem viver fora do artefato frontend, incluindo Nginx na VPS. Não duplicar regras cegamente no Angular.

## Lovable

Lovable pode ser usado como fonte de referência visual/prototipação.

Ele não é autoridade de:

- domínio;
- autenticação;
- contratos;
- routing produtivo;
- comportamento de runtime.

## Segurança

- não publicar arquivos internos;
- não transformar webroot em Git working tree;
- não fazer deploy por `git pull` em webroot;
- não expor `.env` ou configs operacionais.