# Artifact publishing contract

This repository is the canonical source history for published RecurseWright artifacts.

Published article embeds should reference immutable artifact versions rather than a mutable latest build.

For Group Booking, the first production target is:

`/embeds/group-booking/v1/`

The artifact presentation page may evolve independently from the executable artifact.

The same immutable executable may be embedded more than once in one article. Each iframe instance must start from its own initial state and must not inherit interaction state from another instance.

A later artifact version must not silently replace the version referenced by an already published article.

A published version should be traceable to a Git commit or tag in this repository.
