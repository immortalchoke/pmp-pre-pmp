# Fonts in this repository

The original Webflow export bundled four typefaces that **cannot be redistributed**:

| Family | Owner | Why it was removed |
|---|---|---|
| Optimistic | Meta | Proprietary brand typeface |
| FacebookReader | Meta | Proprietary brand typeface |
| FreightSans Pro | Frere-Jones Type | Commercial licence, redistribution prohibited |
| Helvetica Neue LT Pro | Monotype | Commercial licence, redistribution prohibited |

They shipped as raw `.otf` / `.ttf` desktop files — 63 files, 5.8 MB — and committing
those to a public repository would be redistribution in breach of both commercial EULAs.

## What replaced them

Every `@font-face` rule keeps its original `font-family` name, `font-weight` and
`font-style`; only the `src` was repointed. So every `font-family:` reference in the
stylesheet still resolves, and the layout is unchanged — the glyphs simply come from an
open substitute:

- `Freigsan*` → **Source Sans 3**
- everything else (`Optimistic*`, `Facebookreader`, `Helveticaneueltpro*`) → **Inter**

Both are variable fonts, which is why a single file covers every declared weight. Four
files, 212 KB total.

**Typography here is therefore an approximation, not the shipped design.** Weights,
rhythm and layout hold; letterforms differ.

## Licence

Inter and Source Sans 3 are both licensed under the SIL Open Font License 1.1, which
permits redistribution. Full text: https://openfontlicense.org

- Inter — https://github.com/rsms/inter
- Source Sans 3 — https://github.com/adobe-fonts/source-sans
