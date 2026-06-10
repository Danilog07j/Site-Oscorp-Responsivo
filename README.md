# Site-Oscorp-Responsivo
# Oscorp Industries — Site Responsivo

Projeto front-end desenvolvido para a **Semana da Indústria**, simulando o site institucional da Oscorp Industries. O objetivo é demonstrar responsividade, uso de media queries, variáveis CSS e construção de interfaces modernas — sem nenhuma linha de JavaScript.

---

## Estrutura de arquivos

```
oscorp/
├── index.html          # Estrutura HTML
├── style.css           # Estilos externos
├── banner-desktop.jpg  # Banner para desktop (≥ 1025px)
├── banner-tablet.jpg   # Banner para tablet (768px–1024px)
├── banner-mobile.jpg   # Banner para mobile (≤ 768px)
└── README.md
```

---

## Seções da página

| Seção | Descrição |
|---|---|
| **Navbar** | Fixa, com logo à esquerda e links à direita. Menu hamburguer em mobile (CSS puro) |
| **Banner / Hero** | Imagem responsiva por breakpoint, título animado, stats e botões de ação |
| **Introdução** | Texto institucional + 4 pilares da empresa em grid |
| **Projetos** | Cards em CSS Grid com card destaque ocupando 2 colunas |
| **Galeria** | Grid com itens tall/wide, hover com zoom e legenda |
| **Contato** | Formulário nativo + informações de contato |
| **Footer** | Links organizados em colunas, colapsa em mobile |

---

## Responsividade

Três breakpoints principais com imagens de banner trocadas via CSS:

```css
/* Desktop — padrão */
.banner { background-image: url('banner-desktop.jpg'); }

/* Tablet */
@media (max-width: 1024px) {
  .banner { background-image: url('banner-tablet.jpg'); }
}

/* Mobile */
@media (max-width: 768px) {
  .banner { background-image: url('banner-mobile.jpg'); }
}
```

| Breakpoint | Alvo |
|---|---|
| `≥ 1025px` | Desktop |
| `768px – 1024px` | Tablet |
| `≤ 768px` | Mobile |
| `≤ 480px` | Mobile pequeno (iPhone SE) |

---

## Técnicas utilizadas

**CSS puro — zero JavaScript**

- **Variáveis CSS** — paleta, fontes, espaçamentos e transições centralizadas em `:root`
- **Flexbox** — navbar, intro, contato, footer
- **CSS Grid** — projetos, galeria, pillars
- **Media queries** — layout, tipografia e imagens adaptados por breakpoint
- **`animation-timeline: scroll()`** — efeito de navbar ao fazer scroll (sem JS)
- **Checkbox hack** — menu hamburguer abre/fecha via `input:checked` + `label` (sem JS)
- **`clip-path` animado** — transição de abertura do menu mobile
- **`@keyframes`** — animações de entrada do banner, badge rotativo, dot piscando
- **`clamp()`** — tipografia e espaçamentos fluidos entre breakpoints

---

## Fontes

Carregadas via Google Fonts:

- [Plus Jakarta Sans](https://fonts.google.com/specimen/Plus+Jakarta+Sans) — textos e UI
- [Geist Mono](https://fonts.google.com/specimen/Geist+Mono) — labels, eyebrows, dados técnicos

---

## Identidade visual

| Token | Valor | Uso |
|---|---|---|
| `--green-vivid` | `#00ff41` | Cor principal, destaques, ícones |
| `--green-mid` | `#00c832` | Hover de botões |
| `--black` | `#050a05` | Fundo principal |
| `--black-mid` | `#0c140c` | Fundo de seções alternadas |
| `--steel` | `#111811` | Superfície de cards |
| `--white` | `#e8f0e8` | Headings |
| `--fog-light` | `#a8bca8` | Texto corrido |

---

## Como rodar localmente

**Python (sem dependências):**
```bash
cd oscorp
python -m http.server 8080
# Acesse: http://localhost:8080
```

**VS Code — Live Server:**
1. Instale a extensão **Live Server**
2. Clique em **Go Live** no rodapé do VS Code

**Testar no celular (mesma rede Wi-Fi):**
```bash
# Windows — descubra seu IP:
ipconfig

# Mac/Linux:
ifconfig

# Acesse no celular:
http://SEU-IP:8080
```

---

## Testar responsividade no navegador

`F12` → ícone de celular (ou `Ctrl + Shift + M`) → selecione o dispositivo ou arraste a largura manualmente.

Larguras recomendadas para testar: `375px` · `768px` · `1024px` · `1440px`

---

## Compatibilidade

| Recurso | Chrome | Firefox | Safari |
|---|---|---|---|
| `animation-timeline: scroll()` | ✅ 115+ | ✅ 110+ | ✅ 18.2+ |
| `clip-path` animado | ✅ | ✅ | ✅ |
| CSS Grid / Flexbox | ✅ | ✅ | ✅ |
| Checkbox hack | ✅ | ✅ | ✅ |

> Para Safari anterior ao 18.2, a navbar não terá o efeito de scroll — permanece transparente. Todos os outros recursos funcionam normalmente.

---

## Autor

Desenvolvido como projeto prático do curso Técnico em Desenvolvimento de Sistemas.
