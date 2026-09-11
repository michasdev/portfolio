# DESIGN.md — Sistema de Design

Estilo: **Editorial / Brutalismo**. Tema escuro fixo (não existe light mode).

Direção visual baseada em https://coletti.is-a.dev/pt/ (tokens tipográficos, de espaçamento
e movimento medidos do site original, adaptados para tema escuro). Textos do site baseados
no portfólio antigo: https://michelfreitas.com/

## Cores

| Token                  | Valor     | Uso                          |
| ---------------------- | --------- | ---------------------------- |
| `--background`         | `#000000` | Fundo geral — 100% preto     |
| `--foreground`         | `#ffffff` | Texto principal              |
| `--primary`            | `#ffffff` | Botões invertidos (branco)   |
| `--primary-foreground` | `#000000` | Texto sobre botão branco     |
| `--secondary`          | `#1a1a1a` | Superfícies levemente claras |
| `--secondary-foreground` | `#ffffff` |                           |
| `--muted`              | `#1a1a1a` | Fundos recessivos            |
| `--muted-foreground`   | `#767676` | Texto secundário / labels    |
| `--accent`             | `#1a1a1a` | Hover / ênfase               |
| `--accent-foreground`  | `#ffffff` |                              |
| `--border`             | `#ffffff` | Bordas duras, alto contraste |
| `--input`              | `#ffffff` | Campos de entrada            |
| `--ring`               | `#ffffff` | Focus ring                   |
| `--destructive`        | `#ff3b30` | Erro                         |

## Tipografia

| Papel   | Fonte            | Peso   | Tamanho | Line-height | Tracking  |
| ------- | ---------------- | ------ | ------- | ----------- | --------- |
| Display | Archivo Variable | 700    | 122px   | 0.9         | -4.256px  |
| Heading | Archivo Variable | 700    | escala  | —           | -4.256px  |
| Body    | Archivo Variable | 400    | 16px    | normal      | 0         |
| Mono    | IBM Plex Mono    | 400/500 | 14px   | normal      | 1.6128px  |

Display deve escalar com `clamp()` em telas menores.

## Espaçamento

Base de 4px. Escala: `4, 8, 20, 24, 32, 40, 88, 96, 128`.

## Bordas e raio

- `--radius: 0` — todas as bordas 100% quadradas, sem exceção.
- Bordas: `1px solid var(--border)` — linhas brancas duras separando seções.

## Movimento

- `duration-fast: 180ms` · `duration-base: 200ms` · `duration-slow: 200ms`
- `easing: ease`
- Animações pontuais e secas; nada de movimentos longos ou fluidos em excesso.

## Regras de direção

1. Preto absoluto no fundo, sempre.
2. Contraste máximo: texto branco sobre preto. Nunca cores pastéis.
3. Sem `border-radius`, sem gradientes, sem sombras difusas. Sombras duras com offset
   (ex.: `4px 4px 0 #ffffff`) são permitidas para elementos interativos.
4. Estrutura editorial: seções numeradas (01, 02, 03…), grid rígido, metadados em mono.
5. Display gigante ocupando a largura toda, com tracking negativo.
6. Acessibilidade: contraste AAA; focus ring branco visível.

## Implementação

Tokens aplicados em `src/styles/global.css` (Tailwind v4 + shadcn/ui). Componentes shadcn
herdam o tema automaticamente via CSS variables.
