# Repository layout / 仓库目录

Status: **public repository; no GitHub Release**. See [RELEASE_CHECKLIST.md](RELEASE_CHECKLIST.md).

- `pets/<pet-id>/`: five inspectable pet folders. Each contains `pet.json`, `spritesheet.png`, `NOTICE.txt`, and a self-contained asset `LICENSE.md`.
- `packages/`: five standalone ZIPs, rebuilt to include the same four files at the archive root. ZIP bytes change when notices change; the sprite and metadata bytes stay unchanged.
- `previews/`: five individual GIFs and one chibi comparison GIF, all original bytes.
- `validation/`: existing per-variant structural reports and retained historical quality warnings.
- `README.md`, `INSTALL.md`, `PREVIEW.html`: browsing and local-loading instructions.
- `LICENSE`: MIT for eligible original repository-level code/documentation only.
- `ASSETS_LICENSE.md`, `NOTICE.txt`, `PROVENANCE.md`: fan-asset scope, third-party rights, and source gaps.
- `CONTRIBUTING.md`: narrowly scoped contribution guidance.
- `RELEASE_CHECKLIST.md`: remaining publication and verification decisions.
- `manifest.json`: identities, license status, original sprite/metadata hashes, and hashes for repository payload files except itself and `SHA256SUMS`.
- `SHA256SUMS`: hashes all repository payload files except itself, including `manifest.json`.

Integrity lists exclude Git's internal `.git/` directory. Extracted pet files and corresponding ZIP members match byte-for-byte. Read [INSTALL.md](INSTALL.md) before loading.

此仓库已公开，尚无 GitHub Release。包内及原始许可/NOTICE 的私有状态文字保留自准备阶段，当前状态见 README。ZIP 因附带声明更新而重新打包；五张原始 PNG、六张 GIF 及五份 pet.json 保持不变。校验记录覆盖完整仓库文件（不含 Git 内部目录）；manifest 与 SHA256SUMS 排除自身哈希，避免递归。

