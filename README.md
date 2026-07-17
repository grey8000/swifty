# Swifty — SWIFT/OS

Marketing site for **Swifty**, a digital agency built around speed, precision and craft.

Brutalist-editorial art direction: paper `#F2F0EA`, ink `#0C0C0C`, a single safety-orange accent `#FF4A00`, Archivo Expanded 900 for display type and JetBrains Mono for every label, index and datum. Hairline rules, sharp corners, broken grids.

## Pages

| File | Description |
|---|---|
| `index.html` | Home — hero, services index, proof, method, work, signals, CTA |
| `contact.html` | Contact — project brief form |

## Running it

No build step, no dependencies to install. Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
```

## Stack

Each page is one self-contained file: all CSS in a `<style>` tag, all JS in a `<script>` tag, zero images. The only external resources are CDN-loaded:

- [Google Fonts](https://fonts.google.com) — Archivo (variable) + JetBrains Mono
- [GSAP 3.13](https://gsap.com) + ScrollTrigger — scroll choreography
- [Lenis](https://lenis.darkroom.engineering) — smooth scroll

## Signature moments

- **Preloader** — mono counter `000 → 100` with a boot log, then a curtain wipe into the hero
- **Generative field** — hand-rolled Canvas 2D dot grid that repels and ignites under the cursor
- **Kinetic bands** — marquees that accelerate and skew with scroll velocity
- **Work** — pinned section where vertical scroll drives horizontal travel
- **Custom cursor** — crosshair with a labelled context ring

## Degradation

Both pages render fully static and legible when JavaScript is off, when the CDNs are unreachable, or when `prefers-reduced-motion` is set. Nothing stays hidden behind an animation that never fires — the pinned work rail becomes a native snap-scroller, and the preloader is removed outright.

## Contact form

The site is fully static, so the form composes a structured email and hands it to the visitor's mail client, with the direct address shown as a fallback. To collect submissions server-side, point the form at a handler (Formspree, FormSubmit, or your own endpoint).
