# Site do Casamento — Aylla & Filipe

Site estático de casamento publicado via GitHub Pages.

## Dados do evento

- **Noivos:** Aylla e Filipe
- **Data:** 11 de outubro de 2026, domingo, às 16h00
- **Cerimônia:** Capela Nossa Senhora do Rosário — Rua 9 de Julho, 1000, Centro, Lins/SP
- **Recepção:** Villa Vechia — R. Gen. Milton Fernandes de Mello, 1390, Chácara Flora, Lins/SP

## Estrutura do projeto

```
site-casamento/
├── index.html               # Página única (todo o site)
└── assets/
    ├── logo_cropped.png     # Logo "Aylla & Filipe" recortado sem margens (usado no hero e footer)
    ├── bg_church_illustration.jpg  # Esboço a lápis da fachada da Chapel (fundo do hero, mix-blend-mode: multiply, opacidade 22%)
    └── bg_pattern.jpg       # Padrão festivo do convite (câmeras, máscaras, taças) — fundo da seção de bênção, opacidade 12%
```

Os arquivos em `assets/` que NÃO estão no git (listados no `.gitignore`) são temporários de processamento ou os originais do convite.

## Design system

| Token | Valor | Uso |
|---|---|---|
| `--crimson` | `#9B1B4B` | Cor principal — textos de destaque, botões, dividers |
| `--silver` | `#B8B8C0` | Textos secundários, ornamentos |
| `--silver-light` | `#DCDCE4` | Bordas, separadores |
| `--bg` | `#FAFAF8` | Fundo padrão (hero, footer) |
| `--bg-warm` | `#F5F3EF` | Fundo alternado (locais) |
| `--text` | `#2D2D2D` | Texto corrido |
| `--text-light` | `#888` | Subtítulos, labels |

**Fontes (Google Fonts):**
- `Cormorant Garamond` — títulos, datas, nomes de locais (serif elegante)
- `Raleway` — subtítulos, labels, botões, corpo (sans-serif clean)

## Seções (ordem no HTML)

1. **Hero** — Logo + "Convidam para o seu casamento" + data + fundo com ilustração da igreja
2. **Countdown** — Contagem regressiva ao vivo até 11/10/2026 16:00 (fundo vinho sólido)
3. **O Grande Dia** — Cards lado a lado de cerimônia e recepção com links para o Google Maps
4. **Bênção** — "Com a bênção de Deus e seus pais" com padrão do convite ao fundo
5. **Footer** — Logo + data

## Como rodar localmente

```bash
npx serve -l 3456 .
```

Abrir em `http://localhost:3456`.

## Deploy

GitHub Pages — branch `main`, root do repositório.

URL publicada: `https://filipeguidastri.github.io/ayllaefilipe/`

Para atualizar o site após editar: `git add . && git commit -m "mensagem" && git push`.

## Seções não implementadas (possíveis adições futuras)

- **Nossa história** — texto sobre como se conheceram
- **RSVP** — formulário de confirmação de presença
- **Lista de presentes** — link externo ou PIX
- **Dress code** — orientações de traje
- **Galeria** — fotos do casal
- **Informações práticas** — hospedagem, estacionamento, etc.
