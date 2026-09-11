# AGENTS.md — Portfolio de Michel de Freitas

## Projeto

Portfólio pessoal de Michel de Freitas, Engenheiro de Software (São Paulo, SP).
Site estático (Astro, `output: static`). Textos e conteúdo baseados no portfólio antigo:
https://michelfreitas.com/ — antes de escrever conteúdo novo, reaproveitar o texto de lá.

## Stack

- Astro 7 · TypeScript (strict)
- React 19 — usado apenas como islands (ver Arquitetura)
- TailwindCSS v4 — config via CSS em `src/styles/global.css`
- shadcn/ui (Base UI) — config em `components.json`

## Arquitetura

- **Astro-first**: usar componentes `.astro` (HTML/CSS estático, zero JS) sempre que possível.
- **Islands React** apenas em casos específicos: interatividade, estado ou animação — com
  `client:load`, `client:visible` ou `client:only` em componentes pequenos e isolados.
- Nunca um root React `client:only` envolvendo a página inteira.
- Sem SSR, sem endpoints ou rotas de servidor.

## Design

Editorial / Brutalismo. Sistema completo em `DESIGN.md`. Resumo:

- Fundo 100% preto (`#000000`), texto branco, alto contraste.
- Bordas sempre quadradas (`--radius: 0`). Nunca `border-radius`, gradientes ou sombras difusas.
- Display: Archivo Variable (peso 700, tracking negativo). Labels/metadados: IBM Plex Mono.
- Referência visual: https://coletti.is-a.dev/pt/

## Estrutura de pastas

```
src/
  components/     # componentes .astro reutilizáveis
    ui/           # componentes shadcn/ui (React — usar apenas dentro de islands)
  layouts/        # Layout.astro: shell global (importa styles/global.css)
  pages/          # rotas (file-based routing)
  lib/            # utils (cn)
  styles/         # global.css (tokens Tailwind v4 + shadcn)
public/           # assets estáticos
components.json   # config do shadcn
```

## Convenções de código

- TypeScript strict, sem `any`.
- Alias `@/*` → `src/*`.
- Estilização com classes utilitárias Tailwind; tokens de design somente em `global.css`.
- Sem comentários em código.
- Textos do site em pt-BR.
- Novo componente shadcn: `npx shadcn@latest add <componente>`.
- Não adicionar dependências sem necessidade.

## Comandos

- `npm run dev` — dev server (preferir `astro dev --background`; ver seção Development)
- `npm run build` — build estático para `dist/`
- `npm run preview` — preview do build
- `npx shadcn@latest add <componente>` — adicionar componente shadcn

## Development

When starting the dev server, use background mode:

```
astro dev --background
```

Manage the background server with `astro dev stop`, `astro dev status`, and `astro dev logs`.

## Documentation

Full documentation: https://docs.astro.build

Consult these guides before working on related tasks:

- [Adding pages, dynamic routes, or middleware](https://docs.astro.build/en/guides/routing/)
- [Working with Astro components](https://docs.astro.build/en/basics/astro-components/)
- [Using React, Vue, Svelte, or other framework components](https://docs.astro.build/en/guides/framework-components/)
- [Adding or managing content](https://docs.astro.build/en/guides/content-collections/)
- [Adding styles or using Tailwind](https://docs.astro.build/en/guides/styling/)
- [Supporting multiple languages](https://docs.astro.build/en/guides/internationalization/)
