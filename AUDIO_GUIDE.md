# Audio guide

## Why some languages have no voice
The page can only use voices that are already installed on the phone. This depends on the phone and the language, so some phones will not speak some languages. On Android, Google's voice data has to be installed for each language, even though Google supports languages such as Bulgarian, Latvian, Lithuanian and Romanian. Drivers will not have installed these, so phone voices cannot be relied on for every language.

Recorded audio solves this. It plays the same on every phone, and it sounds human.

## How the page chooses
- If a recording exists for that language and page, the page plays it. It looks for `.mp3`, then `.m4a`, then `.webm`.
- If there is no recording, or it fails to load, the page uses the phone's own voice.
- You can launch with phone voices and add recordings language by language. No code changes are needed.

## Recording with the recorder page
1. Make sure the language's translation has been signed off. If the text changes later, that page must be recorded again.
2. The narrator, a native speaker, opens `record.html` on their phone: the live address with `record.html` on the end.
3. They choose their language. The page shows the 6 texts to read.
4. For each text: tap Record, read it aloud slowly and clearly, exactly as written, tap Stop, check it with Play, then tap Save.
5. They send you the 6 saved files, named like `fr_s2.m4a`, `fr_s3.m4a` and so on up to `fr_s7.m4a`.

Tips for the narrator: quiet room, phone about 15 cm from the mouth, steady pace, short pauses between rules, no background music.

Recording on an iPhone gives `.m4a` files, which play on every phone. Recording on Android gives `.webm` files, which will not play on iPhones. Android recordings should be converted to mp3 first.

## Turning the recordings into audio files
**Option A.** Send the files to Claude. They will be converted to mp3, trimmed, named correctly and put in the right folders, and you get an updated package.

**Option B.** Do it yourself:
1. On your computer, make a folder called `audio`, and inside it one folder per language code, for example `fr`.
2. Put the 6 files in the language folder and rename them: `fr_s2.m4a` becomes `s2.m4a`, `fr_s3.m4a` becomes `s3.m4a`, and so on.
3. Upload the `audio` folder to the repository, then check the page plays them.

Language codes: en, fr, ro, pl, ru, bg, uk, lt, lv, pt, es, de, tr.

## Listening to the phone voices for review
Reviewers can hear more languages if they install the voice data on their own phone. Menu names vary by phone, so search Settings for "text-to-speech" on Android or "spoken content" on iPhone, then download the voice for the language. I cannot confirm the exact menu names on every phone or iOS version.

## Files
`audio-scripts.csv` has the exact text for every file, 6 per language, 78 for 13 languages. Only record the languages you will launch.

## Testing
1. Open the live page and choose the language.
2. Tap Read this page on each of the 6 pages. The recording should play, not the phone voice.
3. Tap Stop. It must stop at once.
4. Change language in the middle of playback. Nothing should keep playing.
5. Test on Android and iPhone, on mobile data and Wi-Fi.
6. Rename one file and confirm the page falls back to the phone voice for that page.

## Caching
Browsers can keep an old audio file for a short time after you replace it. After replacing a file, test on a phone you have not used before, or clear the browser cache.
