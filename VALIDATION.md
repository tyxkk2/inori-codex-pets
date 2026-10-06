# 校验说明 / Validation notes

## 中文
2026-10-06 初始打包时检查了五张确切原图的字节与结构，五套均通过当前宠物结构预检及本地 v2 结构检查：
- PNG / RGBA，1536×2288，192×208 单元格，8×11 网格。
- 行 0–10 的有效帧数为 6、8、8、4、5、8、6、6、6、8、8。
- 必须使用的格子有图像，未使用格子为空，透明背景符合结构要求。
- 每张图均小于 4 MiB；本地检查中的结构错误、警告均为空。
- 每个 pet.json 都是 UTF-8 JSON，字段与精灵图相符；各独立 ZIP 无多余外层目录。
- ZIP 中的 PNG 与输入原图 SHA-256 一致；GIF 也是逐字节复制。
- 预览首帧已检查，五套角色／服装与包名相符。

validation/*.json 保留逐套结果。Q 版三套还附有对应原始字节的既有质量审阅结果及其警告，例如个别视线过渡、方向判断或衣服内部透明区域提示。这些警告没有在打包时被删除或修复。标准比例版未附早期详细质量报告。

离线预览页的文件链接已检查，但本次未完成浏览器渲染验收；也可直接打开 previews 中的 GIF。

这次是结构与包装核验，不是重新进行完整动作、视觉质量或十六方向语义验收。现有 GIF 的尺寸、节奏、时长和展示范围不同，不能据此认定各客户端播放效果相同。未在用户设备上完成实际导入测试。

## English
During the initial 2026-10-06 packaging pass, all five exact source sheets passed pet structural preflight and local v2 structural validation: canonical geometry, populated required cells, empty unused cells and transparent backgrounds. Each sheet is below 4 MiB. All new structural checks have empty error/warning lists.

The UTF-8 manifests, root-level archive layout, unchanged PNG/GIF hashes and preview identities were checked. Per-variant JSON reports are in validation/.

The three Q variants carry forward earlier quality-review reports for the same bytes, including their warnings about some directional transitions, semantic judgments or interior transparency. Packaging did not remove or repair those warnings. Earlier detailed quality reports are not included for the two standard-proportion variants.

The offline preview page has passed local link checks, but browser rendering has not been verified in this packaging run. The GIFs can also be opened directly.

This is packaging and structural validation, not a new comprehensive visual/motion/directional review. Existing GIFs vary in size, timing and coverage. No import/runtime test was performed on a user device.

## Licensing/package update / 许可与打包更新
The licensing update retains the original five PNGs, six GIFs, five pet.json files, and validation reports. ZIPs were rebuilt with synchronized NOTICE.txt and per-pet LICENSE.md. Each ZIP contains exactly pet.json, spritesheet.png, NOTICE.txt, and LICENSE.md at its root; each member matches its extracted pets/<id>/ file. Archive integrity and complete-tree hashes were rechecked. This update does not claim a new image-quality review, browser-rendering acceptance, or client runtime test.

许可更新保留原始 PNG、GIF、pet.json 及历史校验报告。五个 ZIP 同步 NOTICE.txt 与逐套 LICENSE.md；每包根目录恰好四个文件，内容与 pets/<id>/ 对应文件一致。已重新核对压缩包完整性和全树哈希；未新增视觉质量、浏览器渲染或客户端运行验收。

## Integrity / 完整性
SHA256SUMS covers every repository payload file, including manifest.json, except SHA256SUMS itself. Git's internal .git/ directory is excluded.
manifest.json records all five variant identities, inner PNG/pet.json hashes, licensing status, and every payload file except itself and SHA256SUMS. The manifest is hashed by SHA256SUMS to avoid recursion.
From the extracted bundle root, optional local checks are:
- Linux: sha256sum -c SHA256SUMS
- macOS: shasum -a 256 -c SHA256SUMS

