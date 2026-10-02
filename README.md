# RecurseWright Artifacts

Public source for versioned interactive artifacts published by [RecurseWright](https://rw.krupnyak.com/).

Artifacts are not demonstrations of a finished framework. They are small executable or interactive parts of an investigation: places where assumptions can be exposed, decisions made observable, and new evidence produced.

Each artifact lives under `artifacts/<slug>/` and may have one or more immutable published versions.

Published snapshots referenced by articles should remain reproducible even as the artifact continues to evolve.

---

## Published artifacts

### Group Booking

A small interactive causal scene built for the first full RecurseWright article.

It begins with one unresolved engineering decision and lets the reader make a call before later evidence changes what that decision means.

- [Open the artifact →](https://rw.krupnyak.com/artifacts/group-booking/)
- [Read the article →](https://rw.krupnyak.com/articles/experimental-recursewright-engineering-on-moving-ground/)
- [Browse the source →](./artifacts/group-booking/)
- [Published version: `group-booking-v1`](https://github.com/RecurseWright/rw-artifacts/tree/group-booking-v1)

---

## Publishing contract

A published artifact version is treated as immutable.

Articles and other public material should reference a versioned snapshot rather than a moving branch. Later development may produce another version, but should not silently change what an earlier publication meant or executed.

For Group Booking, `group-booking-v1` resolves to the exact runtime used by the published article.

Implementation and publishing notes live under [`docs/`](./docs/).

---

## License

Licensed under the Mozilla Public License 2.0. See [`LICENSE`](./LICENSE).
