# Custom Soundtrack Native

Deep Rock Galactic mod: play your own music (flac, mp3, ogg, opus, wav, m4a…) in missions and on the Space Rig, following the game's music. Native (DLL) edition for mintcat.

深岩银河模组：用自己的歌（flac、mp3、ogg、opus、wav、m4a 等）替换任务和太空站的音乐，跟着游戏的音乐走。依赖 mintcat 的原生（DLL）版。

**Download / 下载：** native edition, this repo / 原生版（本仓库）：[GitHub Releases](https://github.com/AdvinxCNN/DRGmod-CustomSoundtrackNative/releases/latest) · pak-only edition / 纯 pak 版：[mod.io](https://mod.io/g/drg/m/custom-soundtrack)

Add the zip in [mintcat](https://github.com/iris-cat-dev/mintcat) with UE4SS turned on; neither mint nor the game's built-in Modding Menu can load its `main.dll`. On mint or the Modding Menu, use the pak-only edition from mod.io.

请在 [mintcat](https://github.com/iris-cat-dev/mintcat) 里开启 UE4SS 后添加 zip；mint 和游戏内置 Modding Menu 都加载不了其中的 `main.dll`。用 mint 或 Modding Menu 的话请装 mod.io 上的纯 pak 版。

---

## English

Play your own music in Deep Rock Galactic: missions, swarms, Dreadnoughts, extraction and the Space Rig. Your songs follow the game's music. This is the native (DLL) edition of [Custom Soundtrack](https://mod.io/g/drg/m/custom-soundtrack): the same page, plus flac / ogg / opus, songs played straight from folders, and a file browser.

### Requirements and installation

- Deep Rock Galactic on Steam, Windows 64-bit.
- **[mintcat](https://github.com/iris-cat-dev/mintcat) with UE4SS turned on.** Download the zip from GitHub Releases and add the whole zip in mintcat (it holds `main.dll` and `CustomSoundtrackNative.pak`); do not extract just the pak. Subscribing in the game's Modding Menu does not load `main.dll`.
- **mint is not supported**: mint installs only the `.pak` from a zip and has no loader for `main.dll`, so with mint you get the page but no music is replaced. On mint, use the pak-only edition from mod.io.
- **Mod Hub is optional**: with it the page is a Mod Hub tab; without it, press the open key (**K** by default) on the Space Rig or in a mission.
- Client-side: teammates don't need it and hear the game's music.
- Enable only one edition. If the pak-only Custom Soundtrack from mod.io is enabled too, this edition plays and the other stays idle. Disable Miracle's Custom Soundtrack.
- **The Microsoft Store (Xbox app) version of the game is not supported for now**: mintcat installs native mods into `Binaries\Win64`, while that version runs from `Binaries\WinGDK`, so `main.dll` never loads. Use the pak-only edition there.

### What you can replace

- Missions: cave ambience, single swarms, sustained attacks (looping swarm music: escort finale, shield generators, pumps, hacking, data vault guardians…), machine events, Dreadnoughts and other bosses, core stones and core rifts, extraction.
- Space Rig: the rig's music (seasonal tracks included), the memorial hall, the jukebox.
- Anything you don't give songs to keeps the game's music.

### Adding songs

Three ways, mixed freely; songs of one kind are shuffled together.

- **Page**: pick a kind, paste a path and press Add (or Enter), or use **Browse…** to pick several files. You can preview songs and set volumes there.
- **Folders**: drop files into `FSD\Mods\CustomSoundtrack\Music\<kind>\`. The kind folders are created the first time you play: `Ambient`, `Swarm`, `Pressure`, `Machine`, `Dreadnought`, `CoreRift`, `Extraction`, `RigAmbient`, `Memorial`, `Jukebox`. Subfolders are just for grouping.
- **Text playlists**: `FSD\Mods\CustomSoundtrack\<kind>.txt`, the same files the pak-only edition reads.
- Songs for one biome only: in the cave kinds, put them in a subfolder named after the biome (ID, English or Chinese name, e.g. `Music\Ambient\Glacial Strata\`), or add them with that biome's button selected. A biome with songs of its own plays only those; others play the songs for all biomes.
- After changing folders or playlists, press **Reload playlists** on the page.
- Formats: flac, mp3, wav, ogg (Vorbis or Opus), opus by the mod's own decoders; m4a (AAC or ALAC), aac, mp4 and wma through Windows Media Foundation (Windows N editions need the Media Feature Pack).

### Features

- Follows the game: when the game starts, fades or stops a piece of music, your song does the same. The game's music is muted before its first sample plays.
- Gapless playback, or a crossfade of up to 10 seconds between songs.
- Master, per-kind and per-song volume; optional loudness match that brings every song to the loudness of the game's music.
- Shows song titles from the files' tags, what plays now, and has "Next song".
- Memorial hall and jukebox songs are heard only nearby, like the game's, and follow the sound effects volume.
- The open key can be a combination such as Alt+D: click the key box in the page's title bar and press it; right-click to clear.
- English and Simplified Chinese page.
- On first start, songs and volumes added on the pak-only edition's page are imported once.

### Files

- Songs: `FSD\Mods\CustomSoundtrack\` (shared with the pak-only edition).
- This edition's settings, imported and page-added songs, per-song volumes and log: `FSD\Saved\SaveGames\Mods\CustomSoundtrackNative\` (`Settings.ini`, `Imported\`, `SongVolumes.txt`, `Log.txt`).
- Console commands: `csn.status`, `csn.reload`, `csn.skip`.

### Good to know

- The open key does nothing while a terminal or the Esc menu is open (the game keeps the key).
- In exclusive fullscreen the file browser may send the game to the background.
- Found a problem? Send `FSD\Saved\SaveGames\Mods\CustomSoundtrackNative\Log.txt` and the lines around `[CustomSoundtrackNative]` in `ue4ss\UE4SS.log`.
- To uninstall, disable it in mintcat. Your song folders and playlists stay; delete `FSD\Saved\SaveGames\Mods\CustomSoundtrackNative\` if you want.
- Mind copyright when streaming. Thanks to Miracoulon for the original Miracle's Custom Soundtrack.
- Bundled decoders: dr_flac, dr_mp3, dr_wav, stb_vorbis, speexdsp's resampler, libopus, opusfile and libogg. Their licenses are in `THIRD-PARTY-NOTICES.txt` on each release.

### Links

- Custom Soundtrack, pak-only edition (mod.io): https://mod.io/g/drg/m/custom-soundtrack
- mintcat: https://github.com/iris-cat-dev/mintcat

---

## 简体中文

用自己的歌替换深岩银河的音乐：任务、虫潮、无畏、撤离和太空站，你的歌跟着游戏的音乐走。这是 [Custom Soundtrack](https://mod.io/g/drg/m/custom-soundtrack) 的原生（DLL）版：页面相同，另外支持 flac / ogg / opus，歌放进文件夹就能播，还有文件选择框。

### 依赖与安装

- Steam 版深岩银河，Windows 64 位。
- **[mintcat](https://github.com/iris-cat-dev/mintcat)，并开启 UE4SS。** 从 GitHub Releases 下载 zip，在 mintcat 里添加整个 zip（里面是 `main.dll` 和 `CustomSoundtrackNative.pak`），不要只取 pak。只在游戏内 Modding Menu 订阅不会加载 `main.dll`。
- **不支持 mint**：mint 只安装 zip 里的 `.pak`，没有加载 `main.dll` 的功能，用 mint 装只会出现页面、不会替换音乐。用 mint 的话请装 mod.io 上的纯 pak 版。
- **Mod Hub 可选**：有它就多一个 Mod Hub 页签；没有它，在太空站或任务里按打开键（默认 **K**）打开页面。
- 纯客户端：队友不用装，也听不到你的歌。
- 两个版本只开一个。mod.io 上的纯 pak 版 Custom Soundtrack 同时启用时，由本版播放、纯 pak 版不启动。Miracle's Custom Soundtrack 请禁用。
- **微软商店版（Xbox App）的游戏目前用不了**：mintcat 把原生模组装进 `Binaries\Win64`，商店版的游戏在 `Binaries\WinGDK`，`main.dll` 不会加载。商店版请用纯 pak 版。

### 能换的音乐

- 任务：洞穴环境、单波虫潮、持续攻势（循环的虫潮曲：护送终点、护盾发生器、泵站、骇入、数据宝库守卫者等）、机器事件、无畏等 Boss 战、核心岩与核心裂隙、撤离。
- 太空站：太空站音乐（含节日活动曲）、纪念堂、点唱机。
- 没配歌的保留原版音乐。

### 加歌

三种方式可以混用，同一类里的歌合在一起洗牌播放。

- **页面**：选一类音乐，粘贴路径后点“添加”（或按回车），或点“**浏览…**”一次选多首。还能试听、调音量。
- **文件夹**：把歌丢进 `FSD\Mods\CustomSoundtrack\Music\<类别>\`。第一次进游戏后会建好这些类别文件夹：`Ambient`、`Swarm`、`Pressure`、`Machine`、`Dreadnought`、`CoreRift`、`Extraction`、`RigAmbient`、`Memorial`、`Jukebox`。子文件夹只用来分组。
- **文本歌单**：`FSD\Mods\CustomSoundtrack\<类别>.txt`，与纯 pak 版读的是同一批文件。
- 只给某个群系的歌：洞穴的几类可以放进以群系命名的子文件夹（群系 ID、英文名、中文名都认，如 `Music\Ambient\冰封岩层\`），或在页面上选中该群系的按钮再加。有专属歌的群系只放专属歌，其余群系放“所有群系”的歌。
- 改了文件夹或歌单后，点页面上的“**重新读取歌单**”。
- 格式：flac、mp3、wav、ogg（Vorbis 或 Opus）、opus 由模组自带的解码器解码；m4a（AAC 或 ALAC）、aac、mp4、wma 走 Windows Media Foundation（Windows N 版需安装“媒体功能包”）。

### 功能

- 跟着游戏走：游戏开始、淡出、停止一段音乐时，你的歌同样开始、淡出、停止；原版音乐在出声之前就被压住。
- 无缝接下一首，或开最长 10 秒的换歌淡变。
- 总音量、每类音量、每首音量；可选“响度归一”，把每首歌调到和原版音乐一样响。
- 显示文件标签里的歌名、正在放的歌，有“下一首”。
- 纪念堂和点唱机的歌和原版一样只在附近听得到，跟随音效音量。
- 打开键可以是 Alt+D 这样的组合键：点页面标题栏的键位框后按下即可，右键清除。
- 页面支持英文和简体中文。
- 第一次启动时，一次性导入纯 pak 版页面上加的歌和音量。

### 文件位置

- 歌：`FSD\Mods\CustomSoundtrack\`（与纯 pak 版共用）。
- 本版的设置、导入和页面加的歌、每首音量、日志：`FSD\Saved\SaveGames\Mods\CustomSoundtrackNative\`（`Settings.ini`、`Imported\`、`SongVolumes.txt`、`Log.txt`）。
- 控制台命令：`csn.status`、`csn.reload`、`csn.skip`。

### 注意

- 终端或 Esc 菜单开着时按打开键没有反应（按键被游戏界面截走）。
- 独占全屏时，文件选择框可能把游戏切到后台。
- 遇到问题：把 `FSD\Saved\SaveGames\Mods\CustomSoundtrackNative\Log.txt` 和 `ue4ss\UE4SS.log` 里 `[CustomSoundtrackNative]` 前后几行发过来。
- 卸载：在 mintcat 里禁用即可。歌的文件夹和歌单不受影响；需要的话删掉 `FSD\Saved\SaveGames\Mods\CustomSoundtrackNative\`。
- 直播时注意音乐版权。感谢 Miracoulon 制作的原版 Miracle's Custom Soundtrack。
- 自带的解码库：dr_flac、dr_mp3、dr_wav、stb_vorbis、speexdsp 的重采样器、libopus、opusfile、libogg，许可证见每个 Release 附带的 `THIRD-PARTY-NOTICES.txt`。

### 链接

- Custom Soundtrack 纯 pak 版（mod.io）：https://mod.io/g/drg/m/custom-soundtrack
- mintcat：https://github.com/iris-cat-dev/mintcat
