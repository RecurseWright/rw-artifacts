# Did the Pipeline Actually Help?

Interactive artifact for the RecurseWright Note "Apparently, Knowledge Has Recurring Charges".

It lets a reader experience one distinction from the Note: on the next slice, settled questions stay settled while genuinely new uncertainty can still appear. The reader runs a small slice, makes one choice about what deserves to reopen on a synthetic case, and sees the resulting boundary: what stays closed, what reopens, and what must still hold.

## Run it locally

The executable is one self-contained file: `src/index.html`. Download it and open it in a browser. There is no build step, no dependency and no network request.

## Runtime invariant

Each instance starts from its initial state. Nothing is persisted, sent anywhere or shared between embed instances; reloading starts again. The artifact makes no network requests. The only parent-window communication is the height-reporting `postMessage` contract used by an embed host (`{ type: 'rwa:height', height }`), which carries a number and nothing else.

The cases are a small fixed set, always shown in the same order. Nothing is generated at random, no remote service or AI is called, and the reader is never asked for their own data.

## What it deliberately does not do

- It calculates no score and grades no choice.
- It reaches no verdict about any pipeline; the reader keeps the judgment.
- Its challenge asks nothing of the reader: it supposes one more settled condition changed, moves that item from KEEP CLOSED to REOPEN, and can restore the original boundary. The artifact integrates no AI provider.
