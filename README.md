# Simple Cloze Overlapper template for Anki 2.1 (probably any version, as it's JavaScript-only)

Hey 👋

I got a bit confused with the original [Cloze Overlapper](https://github.com/glutanimate/cloze-overlapper), and it felt a bit wrong to keep redundant information in our collections. The author also [keeps updates for Anki 2.1 behind a paywall](https://github.com/glutanimate/cloze-overlapper/issues/42#issuecomment-675031109).

Here is a pure JavaScript version that you can paste into your card templates:
* the JavaScript module responsible for rendering is in
  [_cloze-overlapper.mjs](_cloze-overlapper.mjs), and it **must be put into** Anki's
  [collection.media folder](https://docs.ankiweb.net/media.html#manually-adding-media),
* the front side is in [front.html](front.html),
* the back side is in [back.html](back.html).

![screen-recording](screen-recording.gif)

It has been tested to work on Anki (desktop), and AnkiDroid. I assume it should work everywhere indefinitely, as it's written in JavaScript only.

I hope the recording will be self-explanatory! The last two modes seem odd to me, but they were trivial to add, maybe someone will find them useful.

Reddit thread: https://old.reddit.com/r/Anki/comments/116nky2/simple_cloze_overlapper_template_for_anki_21/

## Options (per note)

A good idea is to create a new note type (based on Cloze), e.g. “Cloze (overlapping)”, copy the front and back templates from here, and add a new field to it to control the behavior per each note. The templates below assume that the field will be called `Before|After|OnlyContext|RevelAll|InactiveHints`.

The options (separated by space, comma, pipe, etc.) are:

1. (default: `1`) The number of leading clozes to uncover.
2. (default: `0`) The number of following clozes.
3. (default: `false`) Whether to show only context (leading + cloze + following) – set to true for e.g. long lyrics/poems.
4. (default: `false`) Whether to reveal all clozes on the back (the ones we didn't ask for).
5. (default: `false`) Whether to reveal all user-defined hints (placeholders).

## Card asking for all clozes

If you need an extra card that asks you for all the clozes at once, add another cloze with an unused number and `ask-all` in its content. E.g. `{{c99::ask-all}}` – as in the recording (thanks to `/u/Spiritual_Issue7174`).
