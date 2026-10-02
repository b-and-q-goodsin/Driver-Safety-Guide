# Worksop Driver Safety Pilot

Static page for GitHub Pages. 13 languages: English, French, Romanian, Polish, Russian, Bulgarian, Ukrainian, Lithuanian, Latvian, Portuguese, Spanish, German and Turkish.

Live address: https://b-and-q-goodsin.github.io/Worksop-driver-safety-guide/
Reviewer address: the live address with `?review=1` on the end.

The printed QR signs point to the live address. If it ever changes, the signs must be reprinted.

## Source of truth
The English rules and the Goods-In driver instructions follow the gatehouse sheets, which are accepted by management and H&S. Do not change English wording without the same approval.

## Files
- `index.html`: the whole app, one file. All text for all languages is inside it.
- `404.html`: page shown for wrong addresses. The repository already has a `.nojekyll` file, so nothing else is needed.
- `translation-review/`: one sheet per language for the reviewers. Not needed for hosting. Remove after review if you prefer.
- `audio/`, `audio-scripts.csv`, `AUDIO_GUIDE.md`: optional recorded voice. See the guide.
- `voice-test.html`: testing page that lists the voices on a phone. Delete it before the QR goes live.
- `record.html`: recorder page for native speakers to record the audio. Delete it before the QR goes live, once the recordings are done.
- `TRANSLATION_REVIEW.md`, `PRELAUNCH_CHECKLIST.md`: working notes. Same advice applies.

## Two views of the same page
- **Live address (drivers):** only languages marked reviewed can be tapped. Today that is English only. The others show "Pending translation review".
- **Reviewer address (`?review=1`):** every language can be tapped. A red DRAFT banner shows on each page, and each language button says whether the phone has a voice for it.

## Translation status
Native reviewers have returned corrections for French, Romanian, Russian, Bulgarian, Ukrainian, Lithuanian, Latvian, Portuguese, Spanish, German and Turkish, and the page holds their wording. Polish has not been returned yet. Every language except English stays locked for drivers until you set it to true below.

## Language release control
Near the top of the script in `index.html` is a line starting `const REVIEWED=`. It lists every language as true or false. Change a language to `true` only after a reviewer has signed it off.

## Publish
1. Upload every file from this folder to the repository root, keeping the `audio` and `translation-review` folders.
2. In Settings > Pages, choose Deploy from a branch, select `main` and `/ (root)`.
3. Open the live address on a phone. Check the welcome page says Pilot 2.3.
4. Keep a downloaded copy of each release.

## Controls
- Do not upload the source PDFs.
- Do not add analytics, credentials, internal links or employee contact details.
- Change the version label on the welcome page (`Pilot 2.3` in `index.html`) with every release so you can tell which version a printed QR points to.

## Voice playback
- Plays a recording (mp3, m4a or webm) for a page when one exists in `audio/<language>/` (see `AUDIO_GUIDE.md`).
- Otherwise uses the voices already installed on the driver's phone. The page picks the most natural-sounding voice the phone has for the language, reads one sentence at a time, and pauses between sentences and rules.
- Phone voices vary a lot by language. On Android the voice data must be installed for each language, so any language can be missing. Test every language on real Android and iPhone devices, and use recordings for languages that fail.
- If a phone has no voice for the chosen language and no recording exists, the page says so in that language and tells the driver to ask Goods-In.
- Printed and colleague-assisted fallbacks stay in place.
