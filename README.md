# Moana & the Manta Ray — first playable build

A dependency-free HTML/CSS/JavaScript adventure for touch devices, with a watercolor lagoon and illustrated traditional objects. No D1, accounts, analytics, or backend.

## Play locally
Open `dist/index.html` in a desktop browser, or run `npm run dev` from this directory and visit http://localhost:4173. Browser voice availability varies by device. Start the adventure with sound on, then tap the music-note button to repeat an instruction.

## Deploy to Cloudflare
Workers Static Assets: with Wrangler installed and authenticated, run `npx wrangler deploy` from this directory. The included `wrangler.jsonc` points at `dist`; no build step or bindings are needed.

Cloudflare Pages: upload the contents of `dist` as a Direct Upload project. For a Git-based Pages project, use no framework and `dist` as the output directory. Keep `package.json`, this README, and Wrangler configuration outside the public asset folder.

Official documentation: https://developers.cloudflare.com/workers/static-assets/ and https://developers.cloudflare.com/pages/get-started/direct-upload/

## Implemented
- Seven chapters: packing, coconut quantities, sail decoration, manta following, letters/counts/patterns, picnic and tidying, completion.
- Little voyager (counts 1–3) and growing voyager (counts 1–5) settings.
- Pointer-based dragging and tap alternatives; repeatable browser speech, gentle synthesized chimes, visual hints after inactivity.
- Portrait and landscape CSS; reduced-motion preference support; keyboard activation and dialog focus management.
- Device-local chapter, difficulty, sound and sail storage. Chapters restart on resume. Italian content is not implemented.

## Remaining before family release
- Visible Moana artwork is now included on the welcome screen and beside every activity prompt. See artwork attribution below.
- Desktop browser checks cover character loading, phone portrait and landscape layouts, packing, narrator controls, and saved voice selection. Game-flow and voice-selection checks pass. Actual iPad voice quality still needs a listening check.
- Test on an actual iPad and phone, including short landscape screens, dragging, speech interruption, mute, restore, and browser storage restrictions.
- The 10–15 minute duration is a design target, not measured. A fast child may complete this initial activity set sooner; observe a play session before expanding repetitions or activities.
- Narration prefers known feminine English voices (Samantha first), handles asynchronously available voices, and provides a parent voice picker with preview. The choice is saved locally. If no preferred voice is installed, an available English voice is used; voice gender cannot be guaranteed on every device. This is device speech synthesis, not a cloned character voice.
- The user deployed this repository to Cloudflare. Updates to the connected production branch can trigger deployment.

## Artwork
Built-in image generation produced `dist/assets/lagoon.webp` and `dist/assets/objects.webp` (optimized from PNG).

Final scenery prompt: gently illustrated watercolor tropical lagoon, turquoise open water center/right, leafy islands, palms, sandy shore, warm sunlight, wooden canoe left, no text or UI.

Final object prompt: transparent 3×3 evenly spaced atlas of clay water bottle, wooden oar, coconut, woven basket, bananas, woven sun hat, friendly manta ray, shell and starfish; soft watercolor storybook illustration, isolated objects, no text.

Character artwork: `dist/assets/voyager.webp` is an optimized transparent Moana illustration sourced from https://www.pngaaa.com/detail/289852 (download https://www.pngaaa.com/api-download/289852). The source labels it non-commercial use; Disney character/artwork rights remain with their owners. This third-party illustration is not covered by the repository’s MIT code license. Original character generation was attempted but rejected by the image service.
