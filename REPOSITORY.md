# Private repository layout

This private repository archives the release-review bundle prepared on 2026-10-06.

- `pets/<pet-id>/`: extracted, ready-to-inspect pet folders. Each contains `pet.json`, `spritesheet.png`, and `NOTICE.txt`.
- `packages/`: the five original independent ZIP packages, unchanged.
- `previews/`: the original GIF previews, unchanged.
- `README.md`, `INSTALL.md`, `PROVENANCE.md`, `VALIDATION.md`, `NOTICE.txt`: original review documentation.
- `manifest.json` and `SHA256SUMS`: original bundle metadata and checksums. They cover the release-review bundle; the added extracted folders match the corresponding ZIP members byte-for-byte.

See `INSTALL.md` before loading a pet. Public distribution, attribution, and licensing remain undecided. No blanket license is granted by this upload.
