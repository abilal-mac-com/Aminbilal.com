# SIGNAL v5.0 — Estate Migration Manifest
**aminbilal.com · 8 August 2026 · prepared by Claude Fable 5**

Dialect **C-v2 "Aurora"** is the estate token set. Doctrine: one warm ground;
one hue, two duties, two bloodlines — **rose #F0566F is the hand** (everything
actionable, every here-you-are), **gold #E3AC49 is the medal** (complete,
correct, distinguished). Print values `--crimson-true #861831` and
`--gold-true #B08D2E` are reserved for artwork, which sits on light plates
with its legacy palette pinned.

## Commit layout (paths are exact; keep filenames lowercase)

| File | Size |
|---|---|
| `assets/signal.css` | 75.1 KB |
| `assets/fonts/ArchDaughter.woff2` | 13.8 KB |
| `assets/fonts/Caveat.woff2` | 77.1 KB |
| `assets/fonts/Geist.woff2` | 34.7 KB |
| `assets/fonts/GeistMono.woff2` | 35.5 KB |
| `assets/fonts/Newsreader.woff2` | 155.0 KB |
| `assets/fonts/NewsreaderIt.woff2` | 175.9 KB |
| `index.html` | 205 KB |
| `technology.html` | 1662 KB |
| `finance-architecture.html` | 124 KB |
| `markets.html` | 711 KB |
| `physics.html` | 208 KB |
| `quotes.html` | 39 KB |
| `books.html` | 124 KB |
| `latest/index.html` | 17 KB |

**Note the rename:** the file shipped as `latest/index.html` in this tree; it
was previously delivered as `latest-index.html` to avoid colliding with the
root landing in flat delivery.

## Invariant change — for the architecture record
The single-file-per-page model is retired (8 Aug 2026, approved). Presentation
now lives in `/assets/signal.css` (`?v=5.0` cache key); each page carries only
a body class (`p-technology`, `p-markets`, …). Rationale: coherence and the
end of drift — the 34px/52px mark divergence and the orphaned
`.page-top.is-static` rule are both closed in this cut, the second now
structurally impossible. Rollback is per-page: every page still builds from
source, and the v4 set is preserved.

Fonts are self-hosted at `/assets/fonts` — Geist, Geist Mono, Newsreader
(roman + italic), Caveat, Architects Daughter — subset to the estate's
character union plus Latin-1 and Latin Extended-A headroom (339 codepoints);
every family falls back to embedded Geist before any system font. The
Google Fonts dependency is deleted estate-wide; the only third-party request
remaining anywhere is Plausible. One documented exemption: U+2009 (thin
space, landing page) renders from the system, as no source face carries it.

## Verification (all suites green)
Bodies byte-identical to the deployed v4 set except the single body-class
attribute; landing body byte-identical including the photograph. Head diffs
confined to fonts, stylesheet link, theme-colour and the v5 record. Selector
coverage at v4 parity on every page. Contrast (Aurora): body 13.5:1, accent
6.7:1 on ground, button ink 6.6:1, gold 9.5:1, artwork-plate ink 16.4:1 —
floors 4.5/3.0 cleared everywhere. `prefers-reduced-motion` and
`prefers-contrast:more` honoured; keyframes deduplicated; brace-balanced.

## Outstanding — needed to finish the estate
1. **Uploads required** (currency rule: live copies only): the 13 Latest
   article pages, `latest/notes/index.html`, the two note pages, and
   `football/premier-league-2026-27.html`. A project-directory copy of the
   football page exists but is not used, per the rule. Until migrated, those
   pages keep the old cream dress and will clash on click-through.
2. **Share images**: the `og*.png` set still shows the light style; the
   Pillow pipeline can regenerate them in SIGNAL dress in a later session.
3. After the first push, run LinkedIn Post Inspector on changed URLs.

## Preview caveat
Root-absolute asset paths resolve on the live domain, not from `file://`.
For a visual check before pushing, use the C-v2 specimen
(`technology-signal-c-v2.html`, self-contained, identical dress), or push to
a branch preview.
