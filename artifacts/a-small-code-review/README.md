# A Small Code Review

Interactive artifact created for the RecurseWright article **Experimental RecurseWright: The Cube That Doesn't Wait for a Command**:

https://rw.krupnyak.com/articles/experimental-recursewright-the-cube-that-doesnt-wait-for-a-command/

The reader looks at a tiny library application and five successive changes, and makes a few straightforward judgements as a developer. What the exercise is about is left for the reader to find. There is no AI in it.

## Version

`v1`. Release tag: `a-small-code-review-v1`. The RecurseWright site serves the same file at `/embeds/a-small-code-review/v1/index.html`.

## Run it locally

The executable is one self-contained file: `src/index.html`. Download it and open it in a browser. There is no build step, no dependency and no network request.

## Source provenance

`src/index.html` is the source of record for this version. It is not regenerated from anything in this repository.

It was derived from `A_Small_Code_Review_v0_2_source.html`, a file in the author's publication kit, which is not in this repository.

Kit file SHA-256:

`c07bf9e4fa76d8132c8a9413ed656e58d905f3c710c6ffe51d4e877559edd368`

The derivation made exactly these changes:

- Added the MPL-2.0 source notice.
- Removed the draft label and the `v0.2` version mentions.
- Replaced both privacy lines with `Your answers stay on this page.`
- Set the article's address, in the closing block and in the line "Copy your result" produces.
- Added the host adapter described below.

The scenario, answers, reveal, encore and engine are otherwise unchanged.

Repository executable SHA-256:

`c147ec5f32af3a4c48f2e68bf279fd080301fe7e403da92160a952200cf9b388`

The kit file and the script that applied these changes live outside this repository, so the derivation can be read here but not rerun from here.

## Runtime invariant

Each instance starts from its initial state. Reader answers are not persisted, sent to a server or shared between embed instances; reloading starts again. The artifact makes no network requests. Its parent-window messages contain only frame height and navigation signals.

Your answers stay in the page. "Copy your result" puts one line on the clipboard, only when the reader presses it: the two scores, a fixed sentence and the article's address, not the individual answers.

A page that hosts the artifact in a frame is a separate document with its own behaviour. The RecurseWright site counts that a reader entered the frame. It cannot see what happens inside it.

## Host message contract

The adapter acts only when the file runs in a frame. It posts two messages to the parent window, with target origin `*`, and they carry no reader data:

- `{ type: 'rwa:height', height }`: the scene's height in pixels, on load and whenever the scene changes size.
- `{ type: 'rwa:top' }`: the scene moved to a new screen or restarted, so a host that sized the frame can bring its top back into view.

The artifact listens for no messages. A host may ignore both.

In a frame:

- A frame tall enough for the scene does not scroll, so a host that follows `rwa:height` shows no scrollbar.
- A frame that stays shorter than the scene keeps native scrolling, and screen changes return to the top of that frame.
- Links stand down, because in a sandbox they could only navigate the frame itself.

## Known limitations

- **Compiled CSS.** The styles in `<style id="tw">` are compiled Tailwind CSS output. The Tailwind configuration and class sources are not in this repository, so the stylesheet cannot be rebuilt from here. It can only be edited as it stands.
- **Short frames.** The scene is taller than many fixed frames: about 1,100 px at 680 px wide, and over 1,400 px on the narrowest phones. In such a frame it scrolls inside the frame.
- **Hosts that rebuild the document.** A host that inserts the file into its own document loses the attributes of `<body>`. No text colour depends on them in the screens checked.
- **Clipboard.** "Copy your result" depends on what the host's frame allows, with a legacy fallback.

## License notices

This artifact is licensed under the Mozilla Public License 2.0; see [`LICENSE`](../../LICENSE) at the repository root. The source notice stands at the top of `src/index.html`.

The compiled stylesheet includes output of Tailwind CSS v3.4.19. Its notice is kept in the file as `/*! tailwindcss v3.4.19 | MIT License | https://tailwindcss.com*/`. The license it refers to:

```text
MIT License

Copyright (c) Tailwind Labs, Inc.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
