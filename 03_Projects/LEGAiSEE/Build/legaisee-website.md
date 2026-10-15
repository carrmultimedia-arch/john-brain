---
name: legaisee-website
description: LEGAiSEE public website (legaisee.com) — luxury site build, lighting engine, portfolio page
sources: [backfill]
aliases: [legaisee.com]
---

> Exported from Claude memory on 2026-10-15. Lines marked [stated] were said directly by John. Treat as a first draft until John reviews it.
- [stated] Public website at legaisee.com
- [stated] Files: `legaisee.css` + `index/archaeology/method/serve/architect/commissions/registry.html`
- [stated] Fonts: Cinzel / Cormorant Garamond / Inter
- [stated] Palette locked: pure neutral blacks (#050505, #080808, #0c0c0c), clean 4000K museum-white light (255,248,225), gold at #C9A961; absolute no-violet rule
- [stated] Fixed-bg parallax images; gem metaphor on every page
- [stated] Seven-page structure: Home, Business Archaeology, The Practitioner, Methodology, Industries, Private Commissions, The Registry
- [stated] The Practitioner page framed as "Exhibit Zero: A Live Reconstruction"
- [stated] Aged copper + amber wood grain palette for "dig site" pages (archaeology, method, comparison); gloss obsidian + gold for "museum display" pages
- [stated] `intaketest.html` embed inside registry.html is the single brightest element on the site
- [stated] Hidden methodology comparison page styled as a discovered field document with archive badge
- [stated] CSS consolidation replaced `legaisee.css` and `legaisee-luxury.css` with a single master external stylesheet using `!important` throughout (required because page-level `<style>` blocks load after the external file)
- [stated] `lighting-test.html` debug page developed across four major versions to prove a viewport-space (not page-space) lighting engine before porting to the live cascade
- [stated] Lighting engine uses `getBoundingClientRect` per rAF frame, calculates distance from named viewport-fixed light sources (key/fill/back), accumulates additive contributions, and writes `--el-intensity`, `--el-specular`, `--el-angle`, `--el-key-x`, `--el-key-y` as custom properties on each lit element
- [stated] Per-page lighting rig configs (museum track, softbox, speakeasy, concert spotlight) loaded as data objects
- [stated] Gold material system has three levels (shadow/lit/specular): flat and dim in shadow, gaining luminance as elements enter a light zone, specular only at light center
- [stated] `.card--illumine` modifier class: museum light from top shining down, gold palette, hover-triggered
- [stated] `.card--illumine` HTML structure: insert `.illumine-layer` div (with `.slit`, `.lumen > .min + .mid + .hi`, `.darken > .sl + .ll + .slt + .srt`) as first child inside card; CSS lives in `legaisee-luxury.css`
- [stated] Apply `.card--illumine` to: `commissions.html` exhibit cards + Bedrock Pledge clauses; `serve.html` three archetype cards; `archaeology.html` Lindy proof cells; `registry.html` confidentiality cells
- [stated] Career portfolio page (`career.html`) built as a two-file system (career.html + career-config.js) with hierarchical folder-tree drill-down by Era → Station → content type, LEGAiSEE-styled lightbox, and YouTube thumbnail auto-generation
- [stated] Deployment lesson: use the Download button (not Copy) from Claude artifacts to avoid smart-quote and markdown corruption when pasting into cPanel
- [stated] Currently rebuilding the portfolio for job hunting purposes first, intending it to become the LEGAiSEE career page later; built a system this past weekend that scrapes YouTube playlist data into an organized portfolio page, but it isn't working as advertised yet
- [stated] legaisee.com email is already set up on cPanel
- [stated] Previously used HoneyBook with Stripe connected for billing; the flow was essentially an email containing a link to a payment page
- [stated] Was told the locked black+gold luxury palette and big top-menu layout are cliché/generic; site scored 80/100 on narrative but 30/100 on visual/experience; wants these design rules to evolve rather than stay fixed
- [stated] Envisions the redesign as a museum-metaphor experience: a Lobby entrance, then distinct non-linear "rooms" (not a straight hall to an exit), navigated via a smooth scroll experience with a Z-axis/depth feel, not just vertical or horizontal scroll — wants the whole site, start to finish, to feel like a single continuous experience
- [stated] Has pivoted the room-navigation concept toward a Myst-style pre-rendered approach: builds museum rooms in Lightwave, renders room-to-room travel/transition video clips connected by doors, extracts first/last frame stills, and sequences video-transition-lands-on-still with content animating in/out on trigger
- [stated] Already has a large set of rendered luxury-museum room concept images (gem display halls, artifact rooms, vaults, ateliers, libraries) originally made as backgrounds for gem-transformation explanation content
- [stated] Scrollytelling reference video (Envato preview) was only meant to show the STYLE of layered 3D depth/camera movement, not a literal video background — wants that achieved via code-driven parallax/3D element movement (not a slide-in-and-fade-over-a-flat-parallax-image approach)
- [stated] Wants NO video anywhere on the LEGAiSEE site — he's no longer positioning himself as a video producer, so isn't advertising video production work via LEGAiSEE
- [stated] Scroll pacing instinct from video background: ~1 second per word of text, lower-third minimum 4-5 seconds on screen even for short text — being translated into scroll-distance pinning (pin distance scales with word count, plus a minimum floor distance) since scroll has no fixed clock
- [stated] Recommended/decided stack direction for scrollytelling: CSS 3D transforms + GSAP ScrollTrigger (free), no Three.js/WebGL, no video assets
- [stated] Found existing scrollytelling planning docs in the git repo under `_governance/Docs/WEBSITE/`: `LEGAiSEE_Lux Scrollytelling Site_9-3-26/` folder (Governance Doctrine, Production Master Brief V1.0, Site Archaeology & Cinematic Opportunity Report) plus `+LEGAISEE-FINAL SITE COPY 6-18-26.md` (page-by-page live copy instructions with real pricing) — these are GPT-authored, not previously known to Claude before this session
- [stated] Design direction (10/6/26): scale back to restrained business colors with a few textures here and there (leather, marble, as in the scrollytelling camera site); use the raw-gem-to-museum-display metaphor sparingly as a single-stone excavation-to-display; ditch the rendered museum photos/backgrounds — at most show a museum room photo beside the stone at the step where the transformation happens
- [stated] Hero stone choice (10/6/26): fire obsidian (preferred over a ruby) for the single-stone raw-to-display metaphor; has renders of it raw in a volcanic landscape, rough-cut, polished and set in a bezel, and displayed in a museum room (plaque "LEGAiSEE Masterpiece No. 1")
- [stated] Priority (10/6/26): finish the front-end site first (better layout, colors, and verbiage for ALL pages, target audience = $10M+ companies), with stone renders dropped into placeholders last; wants to start promoting now while the server system is still being finished, to build a waiting line since the site says only 3 clients per quarter
- [stated] Registry page (registry.html) uses an AI-interview qualification questionnaire (forensic intake) instead of a generic contact form; as of 10/6/26 it is broken and he wants it working before promoting
- [stated] Finished-stone watch-shaped frame is intentional: prestige mounting in something familiar to the viewer rather than a generic museum mount, and the shape combines old stone with modern technology (old broadcast marketing to a modern content authority system)
- [stated] LEGAiSEE site redesign and registry questionnaire fix are on hold (10/6/26) until he finishes the money-making CAMERA cohort first
