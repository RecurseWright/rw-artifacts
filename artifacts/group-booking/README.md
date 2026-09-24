# Group Booking

Interactive artifact created for:

[**Experimental RecurseWright: Engineering on Moving Ground, and Other Pretty Problems with Stability**](https://rw.krupnyak.com/articles/experimental-recursewright-engineering-on-moving-ground/)

It is a small causal scene in which one unresolved engineering decision is made before later evidence changes what that decision means.

- [Open the published artifact →](https://rw.krupnyak.com/artifacts/group-booking/)
- [Read the article →](https://rw.krupnyak.com/articles/experimental-recursewright-engineering-on-moving-ground/)
- [Published snapshot: `group-booking-v1`](https://github.com/RecurseWright/rw-artifacts/tree/group-booking-v1)

## Source provenance

The public Git history preserves two real publication-stage snapshots:

- `rw-artifact-1-dev-v4.zip` was imported as the first publication-grade snapshot.
- `rw-artifact-1-dev-v5.zip` added a technical race-condition fix only; copy, design and flow were unchanged.

The current executable is `src/index.html`. Its runtime code corresponds to v5; the repository copy additionally carries the MPL-2.0 source notice.

Original v5 executable SHA-256:

`0313c86866c07dbe4585abb2841f00a7292d4bb62f4a9e092c35d9acfd4ad668`

Repository executable SHA-256 after adding the MPL-2.0 notice:

`6aafd578e4c3c95599ba84998b0a0143cfd69feb7402762702097adc58240192`

No runtime logic, copy, design, or flow changed when the license notice was added.

## Runtime invariant

Each embed instance starts from the initial state.

Interaction state is not persisted across page loads and is not shared between embed instances. The only parent-window communication is the height-reporting `postMessage` contract used by an embed host.
