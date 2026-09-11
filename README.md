# Portfolio — Michel de Freitas

Portfólio pessoal de Michel de Freitas, Engenheiro de Software (São Paulo, SP).

Design editorial/brutalista: fundo 100% preto, alto contraste, bordas quadradas.
Sistema de design completo em [`DESIGN.md`](./DESIGN.md). Conteúdo baseado no portfólio
antigo: https://michelfreitas.com/

## Stack

Astro 7 · React 19 (islands) · TailwindCSS v4 · shadcn/ui · TypeScript

## Comandos

| Comando           | Ação                            |
| :---------------- | :------------------------------ |
| `npm install`     | Instala dependências            |
| `npm run dev`     | Dev server em `localhost:4321`  |
| `npm run build`   | Build estático para `dist/`     |
| `npm run preview` | Preview do build                |

## Estrutura

```text
/
├── public/               # assets estáticos
├── src/
│   ├── components/       # componentes .astro + ui/ (shadcn/React)
│   ├── layouts/          # shell global (Layout.astro)
│   ├── pages/            # rotas (file-based routing)
│   ├── lib/              # utils (cn)
│   └── styles/           # global.css (tokens de design)
└── components.json       # config shadcn/ui
```

## Arquitetura

Astro-first: páginas e componentes estáticos em `.astro`. Islands React apenas para
interatividade e animação.

## Referências

- Design: https://coletti.is-a.dev/pt/
- Portfólio anterior (conteúdo): https://michelfreitas.com/
