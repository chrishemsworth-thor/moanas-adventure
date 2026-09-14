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
- Visible Moana artwork is missing: both character generation attempts were rejected by the image service. A sourced character download also failed due network restrictions. The scenery, manta ray and object illustrations are included locally.
- This session blocked the local preview server and local-file browser access. JavaScript syntax and automated state-flow checks passed, but visual layout and real touch/speech behavior have not been browser-tested.
- Test on an actual iPad and phone, including short landscape screens, dragging, speech interruption, mute, restore, and browser storage restrictions.
- The 10–15 minute duration is a design target, not measured. A fast child may complete this initial activity set sooner; observe a play session before expanding repetitions or activities.
- Narration currently uses the device's English speech synthesis rather than recorded audio. Device voice selection and pronunciation vary.
- Not deployed: no authenticated Cloudflare connection was available in this session.

## Artwork
Built-in image generation produced `dist/assets/lagoon.webp` and `dist/assets/objects.webp` (optimized from PNG).

Final scenery prompt: gently illustrated watercolor tropical lagoon, turquoise open water center/right, leafy islands, palms, sandy shore, warm sunlight, wooden canoe left, no text or UI.

Final object prompt: transparent 3×3 evenly spaced atlas of clay water bottle, wooden oar, coconut, woven basket, bananas, woven sun hat, friendly manta ray, shell and starfish; soft watercolor storybook illustration, isolated objects, no text.
