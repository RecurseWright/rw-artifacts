# Artifact publishing contract

This repository is the canonical source history for published RecurseWright artifacts.

Published article embeds should reference immutable artifact versions rather than a mutable latest build.

For Group Booking, the published production path is:

`/embeds/group-booking/v1/`

The published snapshot is traceable to the `group-booking-v1` tag in this repository.

The canonical presentation page is:

https://rw.krupnyak.com/artifacts/group-booking/

The first full article using this artifact is:

https://rw.krupnyak.com/articles/experimental-recursewright-engineering-on-moving-ground/

The artifact presentation page may evolve independently from the executable artifact.

The same immutable executable may be embedded more than once in an article. Each embed instance must start from its own initial state and must not inherit interaction state from another instance.

A later artifact version must not silently replace the version referenced by an already published article.

External publication platforms may use an adapter when they cannot embed the canonical runtime directly. That adapter must still resolve to the same immutable published snapshot rather than a moving branch or latest build.

A published version should remain traceable to a Git commit or tag in this repository.
