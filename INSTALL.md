# 本地加载 / Local loading
核对日期 / Checked: 2026-10-06
适用范围 / Scope: Petdex Desktop, source revision 7e327034c27098bb7b701b834e34af81c2cfbdba

## 中文
1. 先阅读 [素材使用声明](ASSETS_LICENSE.md)。从仓库的 [packages/](packages/) 下载单只 ZIP（例如 inori-q-school.zip），或下载完整仓库后在该目录选择一套。仓库现已公开。
2. 将该独立 ZIP 解压到同名文件夹中。文件结构应为：
   - inori-q-school/pet.json
   - inori-q-school/spritesheet.png
   - inori-q-school/NOTICE.txt
   - inori-q-school/LICENSE.md
3. 将这个文件夹放到当前用户的 ~/.codex/pets/ 下，或 Petdex Desktop 的 ~/.petdex/pets/ 下。最终路径例如 ~/.codex/pets/inori-q-school/pet.json。~ 表示当前用户的主目录。
4. 在已安装的 Petdex Desktop 中打开 Settings → Pets → Installed，点击 Refresh，搜索文件夹名称（例如 inori-q-school），再点击 Select。Custom pets → Open folder 是另一个打开素材目录的按钮。
5. 若已有同名文件夹，先保留备份或选择其他版本，避免覆盖。两个目录内出现同一 slug 时，当前实现优先使用 ~/.petdex/pets/ 下的那一份。

请保留 pet.json 与 spritesheet.png 的相对位置，不要只复制 GIF。GIF 仅供预览。单只 ZIP 根目录直接是这四个文件；不要额外多套一层同名文件夹。将独立 ZIP 放进空的同名目标文件夹再解压即可得到上述结构。

这里只说明读取本地素材，不需要提交到 Petdex 画廊、登录账号或配置 agent hooks。本次没有代为安装软件、导入到用户设备或测试实际运行。安装软件本身请另行查看其官方说明。

### 兼容性边界
- pet.json 使用当前 Petdex 示例中的五字段格式：id、displayName、description、spriteVersionNumber、spritesheetPath；明确设置 spriteVersionNumber 为 2。
- v2 图保留全部 11 行。当前 Petdex Desktop 播放前九行动作；后两行十六方向视线保留在素材内，当前桌面播放器不使用。
- 每张 PNG 小于当前桌面加载器的 4 MiB 编码文件上限。
- 本说明验证的是 Petdex 的本地目录加载规则；没有验证当前 ChatGPT 原生 ZIP 或本地文件夹导入界面。
- 总 ZIP 包含五个独立 ZIP，不是单只宠物包。公开上传、发布和授权审阅不属于这里的本地加载步骤。

## English
1. Read the [asset notice](ASSETS_LICENSE.md), then select a standalone ZIP from [packages/](packages/) in this public repository, or download the repository and choose a ZIP from that folder. No repository membership is required to download.
2. Extract it into a folder with the matching slug, such as inori-q-school/. Its root must contain pet.json, spritesheet.png, NOTICE.txt, and LICENSE.md.
3. Place that folder under your user's ~/.codex/pets/ or ~/.petdex/pets/. Example: ~/.codex/pets/inori-q-school/pet.json. The tilde means your home directory.
4. In an already-installed Petdex Desktop, open Settings → Pets → Installed, click Refresh, search for the folder slug (for example inori-q-school), then click Select. Custom pets → Open folder is a separate control for opening the local pets directory.
5. Back up any existing same-slug folder before replacing it. When both locations contain the same slug, ~/.petdex/pets/ takes precedence.

Keep the license and notice with the assets. Keep pet.json next to spritesheet.png. GIFs are previews only. Extracting a per-pet ZIP into an empty folder named for that pet produces the required layout without another nested folder.

Loading existing local files does not require gallery submission, an account, or agent-hook setup. This bundle has not been installed or runtime-tested on a user device.

The manifests use Petdex's five-field example with spriteVersionNumber: 2. Preserve all eleven atlas rows. Current Petdex Desktop animates rows 0–8 and does not use the two directional rows. Every sheet is below the loader's 4 MiB encoded-file cap. These checks establish packaging against Petdex source; they do not verify a current ChatGPT-native ZIP/local-folder import UI.

## Sources
- [Manifest fixture](https://github.com/crafter-station/petdex/blob/7e327034c27098bb7b701b834e34af81c2cfbdba/.github/workflows/desktop-native-ci.yml)
- [Local directory scan](https://github.com/crafter-station/petdex/blob/7e327034c27098bb7b701b834e34af81c2cfbdba/packages/petdex-desktop-native/src/main.zig#L1216-L1242)
- [Settings controls](https://github.com/crafter-station/petdex/blob/7e327034c27098bb7b701b834e34af81c2cfbdba/packages/petdex-desktop-native/src/settings_view.zig)
- [Loader limits](https://github.com/crafter-station/petdex/blob/7e327034c27098bb7b701b834e34af81c2cfbdba/packages/petdex-desktop-native/src/main.zig#L1417-L1486)
- [Animation rows](https://github.com/crafter-station/petdex/blob/7e327034c27098bb7b701b834e34af81c2cfbdba/packages/petdex-desktop-native/src/sprite.zig)

