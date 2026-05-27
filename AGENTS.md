# Instruções para agentes de IA — Site Aylla & Filipe

## Contexto do projeto

Site estático de casamento — um único arquivo `index.html` com CSS e JS inline. Sem framework, sem build step, sem dependências de npm. Para entender o projeto completo leia o `CLAUDE.md` primeiro.

## Antes de qualquer mudança

1. Leia o `CLAUDE.md` para ter o contexto do evento e do design system
2. Leia o `index.html` completo para entender a estrutura atual
3. Use o servidor local para validar visualmente toda alteração

## Como rodar o servidor local

```bash
npx serve -l 3456 .
```

Use as ferramentas de preview (`preview_start`, `preview_screenshot`, `preview_resize`) para verificar o resultado no browser antes de reportar a tarefa como concluída. Sempre teste desktop e mobile (375px).

## Convenções de código

- **CSS:** variáveis via `--tokens` definidas em `:root`. Não use valores de cor ou fonte hardcoded — sempre use os tokens existentes.
- **Tipografia:** `Cormorant Garamond` para títulos/datas, `Raleway` para tudo mais.
- **Responsivo:** use `clamp()` para tamanhos de fonte, `min()` para larguras, e `@media (max-width: 580px)` para quebras de layout.
- **Animações:** entradas do hero usam `fadeUp` com `animation-fill-mode: forwards` e `opacity: 0` inicial — mantenha esse padrão para novos elementos animados.
- **Backgrounds ilustrados:** use pseudo-elemento `::before`/`::after` ou div com `position: absolute` para backgrounds com opacidade, nunca `opacity` no elemento pai (afetaria o conteúdo).

## Assets disponíveis

| Arquivo | O que é | Como usar |
|---|---|---|
| `assets/logo_cropped.png` | Logo Aylla & Filipe recortado | `mix-blend-mode: multiply` para fundo transparente |
| `assets/bg_church_clean.jpg` | Ilustração da chapel sem texto | Background com opacidade ~25-30% |
| `assets/bg_pattern.jpg` | Padrão festivo do convite | Background com opacidade ~10-15% |

Se o usuário trouxer novas imagens, processe-as com Python (PIL/NumPy já disponíveis) antes de usar.

## Adicionando novas seções

- Insira entre `<!-- ── BÊNÇÃO ──>` e `<!-- ── FOOTER ──>` para manter a bênção e o footer sempre por último
- Siga a estrutura: `<section class="nome-section">` com `padding: 90px 24px`, título em `Cormorant Garamond`, ornamento `✦` entre título e conteúdo
- Adicione a seção no `CLAUDE.md` (tabela "Seções") após implementar

## Deploy

Após qualquer alteração aprovada pelo usuário:

```bash
git add index.html        # (e outros arquivos alterados)
git commit -m "descrição da mudança"
git push
```

GitHub Pages atualiza automaticamente em ~1 minuto.

**Nunca faça push sem confirmação explícita do usuário.**

## O que não fazer

- Não introduzir frameworks (React, Vue, etc.) ou bundlers — o site é estático por design
- Não criar arquivos CSS ou JS separados sem o usuário pedir — manter tudo inline no `index.html`
- Não alterar as cores do design system sem aprovação — a paleta vinho/cinza é a identidade visual do casamento
- Não subir para o git os arquivos listados no `.gitignore` (originais do convite, arquivos temporários de processamento)
- Não fazer commit ou push automaticamente — sempre confirmar com o usuário antes
