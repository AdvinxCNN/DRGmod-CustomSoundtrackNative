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

- Missions: cave ambience, single swarms, sustained attacks (looping swarm music of events), machine events, Dreadnoughts and other bosses, core stones and core rifts, extraction, and the music while everyone loads into a mission.
- Sustained attacks can have songs per event: Escort finale, Power Stations, Caretaker, On-Site Refining, Lithophage Meteorite, Rival bomb, Data Deposit. When the music starts, the mod looks at which event is running (on clients too) and plays that event's songs, or the general ones if it has none.
- Mission end: the end screen of a mission won and of a mission lost, each with songs of its own (every won stage of a deep dive counts as won).
- Space Rig: the rig's music (seasonal tracks included), the memorial hall, the jukebox, and the fanfare when a dwarf is promoted.
- Anything you don't give songs to keeps the game's music.

### Adding songs

Three ways, mixed freely; songs of one kind are shuffled together.

- **Page**: pick a kind, paste a path and press Add (or Enter), or use **Browse…** to pick several files. You can preview songs and set volumes there.
- **Folders**: drop files into `FSD\Mods\CustomSoundtrack\Music\<kind>\`. The kind folders are created the first time you play: `Ambient`, `Swarm`, `Pressure`, `Machine`, `Dreadnought`, `CoreRift`, `Extraction`, `Loading`, `Victory`, `Defeat`, `RigAmbient`, `Jukebox`, `Memorial`, `Promotion`. Subfolders are just for grouping.
- **Text playlists**: `FSD\Mods\CustomSoundtrack\<kind>.txt`, the same files the pak-only edition reads.
- Songs for one biome only: in the cave kinds, put them in a subfolder named after the biome (ID, English or Chinese name, e.g. `Music\Ambient\Glacial Strata\`), or add them with that biome's button selected. A biome with songs of its own plays only those; others play the songs for all biomes.
- Songs for one sustained-attack event: a folder named after the event in `Music\Pressure\` (ID, English or Chinese name, e.g. `Music\Pressure\Caretaker\`; biome folders inside work too), an `event=Caretaker` section in `Pressure.txt`, or on the page: Ctrl+click **Sustained attack** and pick the event. An event without songs of its own plays the general ones.
- After changing folders or playlists, press **Reload playlists** on the page.
- Formats: flac, mp3, wav, ogg (Vorbis or Opus), opus by the mod's own decoders; m4a (AAC or ALAC), aac, mp4 and wma through Windows Media Foundation (Windows N editions need the Media Feature Pack).

### Features

- Follows the game: when the game starts, fades or stops a piece of music, your song does the same. The game's music is muted before its first sample plays.
- Gapless playback, or a crossfade of up to 10 seconds between songs.
- Master, per-kind and per-song volume (the Space Rig's own goes up to 300%); optional loudness match that brings every song to the loudness of the game's music.
- Shows song titles from the files' tags and what plays now. Each "playing" line has ◀ ▶ for the previous and next song of that track alone; **Find playing** shows the playing song in its list.
- Play mode: **shuffle** (every song once a round), **in order** (the list from top to bottom) or **repeat one**. One button sets it for everything.
- **Advanced** (the switch beside the language buttons) shows more:
  - A play mode of its own for a kind, one of its biomes or an event (the button right of the kind's title). Without one it follows the level above.
  - A menu on every song (the **···** button): play it now, switch it off without removing it, copy its path, or open its details.
  - A song's details: a display name, its volume, a loop region (start and end in seconds), fade-in and fade-out, each with a button back to the default, and a preview of the loop's seam.
- Loops: in repeat one, or when a song is the only one of its list, it goes back to the loop's start at the loop's end, without a gap (the first time it plays from the beginning, so an intro is heard once). Loop points in a file's tags are used by themselves: `LOOPSTART` with `LOOPLENGTH` or `LOOPEND`, or a WAV sampler chunk. Lossless files (FLAC, WAV) loop cleanly; with lossy formats the two ends may not meet exactly.
- A file that cannot be played is tried once and marked on the page; a kind left without a playable song keeps the game's music.
- Double-click a song's name to play it now, while its kind plays. The button beside it (Folder, Playlist, Added here) opens the song's folder in Explorer with the song selected; its tooltip says where the song is listed and how to remove it.
- The song list shows ten songs and scrolls (the bar beside it, or the mouse wheel over it); the biomes are a column beside the songs, each with its song count.
- Memorial hall and jukebox songs are heard only nearby, like the game's, and follow the sound effects volume.
- The open key can be a combination such as Alt+D: click the key box in the page's title bar and press it; right-click to clear.
- English and Simplified Chinese page.
- On first start, what you set up on the pak-only edition's page is imported once: its songs and volumes, and from its 1.4 each song's own settings and the play modes. If you used this edition before 0.6.0, only what is new is added (the three new kinds' songs, song settings and play modes you do not have here yet).

### Files

- Songs: `FSD\Mods\CustomSoundtrack\` (shared with the pak-only edition).
- This edition's settings, imported and page-added songs, each song's own settings and the log: `FSD\Saved\SaveGames\Mods\CustomSoundtrackNative\` (`Settings.ini`, `Imported\`, `SongSettings.txt`, `Log.txt`; `SongVolumes.txt` from earlier versions is still read).
- Console commands: `csn.status`, `csn.reload`, `csn.skip`, `csn.prev`, `csn.mode [shuffle|order|repeat]`, `csn.mode <kind or event>[.<biome>] <mode or follow>`.

### Good to know

- The open key does nothing while a terminal or the Esc menu is open (the game keeps the key).
- On the loading screen the cave music may already have started, quietly under the loading music, until you land. The game does the same with its own music.
- In exclusive fullscreen the file browser may send the game to the background.
- Mixing your songs with the game's own tracks (an option of the pak-only edition 1.4) is not in this edition.
- The page and `main.dll` come in one zip and must be of the same version; the page says so if they are not.
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

- 任务：洞穴环境、单波虫潮、持续攻势（各种事件的循环虫潮曲）、机器事件、无畏等 Boss 战、核心岩与核心裂隙、撤离，以及进任务时等所有人加载完的那段音乐（加载等待）。
- 持续攻势可以按事件分别配歌：护送终点、骇入发电站、看守者、就地精炼、噬岩体陨石、强敌炸弹、数据存储塔。音乐开始时模组看当时在进行哪个事件（客机也能认），放这个事件的歌，没有就放通用的歌。
- 任务结算：任务成功和任务失败的结算画面各配各的歌（深潜每过一层也算成功）。
- 太空站：太空站音乐（含节日活动曲）、纪念堂、点唱机，以及晋升矮人时的号角。
- 没配歌的保留原版音乐。

### 加歌

三种方式可以混用，同一类里的歌合在一起洗牌播放。

- **页面**：选一类音乐，粘贴路径后点“添加”（或按回车），或点“**浏览…**”一次选多首。还能试听、调音量。
- **文件夹**：把歌丢进 `FSD\Mods\CustomSoundtrack\Music\<类别>\`。第一次进游戏后会建好这些类别文件夹：`Ambient`、`Swarm`、`Pressure`、`Machine`、`Dreadnought`、`CoreRift`、`Extraction`、`Loading`、`Victory`、`Defeat`、`RigAmbient`、`Jukebox`、`Memorial`、`Promotion`。子文件夹只用来分组。
- **文本歌单**：`FSD\Mods\CustomSoundtrack\<类别>.txt`，与纯 pak 版读的是同一批文件。
- 只给某个群系的歌：洞穴的几类可以放进以群系命名的子文件夹（群系 ID、英文名、中文名都认，如 `Music\Ambient\冰封岩层\`），或在页面上选中该群系的按钮再加。有专属歌的群系只放专属歌，其余群系放“所有群系”的歌。
- 只给某个持续攻势事件的歌：放进 `Music\Pressure\` 下以事件命名的文件夹（事件 ID、英文名、中文名都认，如 `Music\Pressure\看守者\`，里面也可以再建群系文件夹），或在 `Pressure.txt` 里写 `event=Caretaker` 段，或在页面上按住 Ctrl 点“**持续攻势**”选事件再加。没有专属歌的事件放通用的歌。
- 改了文件夹或歌单后，点页面上的“**重新读取歌单**”。
- 格式：flac、mp3、wav、ogg（Vorbis 或 Opus）、opus 由模组自带的解码器解码；m4a（AAC 或 ALAC）、aac、mp4、wma 走 Windows Media Foundation（Windows N 版需安装“媒体功能包”）。

### 功能

- 跟着游戏走：游戏开始、淡出、停止一段音乐时，你的歌同样开始、淡出、停止；原版音乐在出声之前就被压住。
- 无缝接下一首，或开最长 10 秒的换歌淡变。
- 总音量、每类音量、每首音量（太空站的本类音量最高 300%）；可选“响度归一”，把每首歌调到和原版音乐一样响。
- 显示文件标签里的歌名和正在放的歌。每一行“正在放”都有 ◀ ▶，只切这一行那条音轨的上一首、下一首；“**定位正在放**”在列表里找到正在放的那首。
- 播放模式：**随机**（每轮每首放一次）、**顺序**（按列表从上到下）、**单曲循环**。一个按钮管全部。
- “**高级设置**”（语言按钮旁边的开关）打开后多出：
  - 某一类、它的某个群系或某个事件单独的播放模式（类别标题右边的按钮）；不设就跟随上一级。
  - 每首歌的菜单（“**···**”按钮）：立即播放、停用（留在列表里但不放）、复制路径、打开详细设置。
  - 一首歌的详细设置：显示名、音量、循环区间（起点和终点，秒）、淡入、淡出，每项都能恢复默认，还能试听循环的接缝。
- 循环：单曲循环时，或这首是它那组里唯一的一首时，放到循环终点就无缝回到循环起点（第一遍从头放，所以前奏只听到一次）。文件标签里带循环点的会自动使用：`LOOPSTART` 配 `LOOPLENGTH` 或 `LOOPEND`，或 WAV 的采样器块。无损文件（FLAC、WAV）接得上；有损格式两端可能对不齐。
- 放不了的文件只试一次，并在页面上标出；某一类没有能放的歌时保留原版音乐。
- 双击歌名立刻切到这首（这一类正在放时）。旁边的按钮（文件夹 / 歌单文件 / 页面添加）在资源管理器里打开这首歌所在的文件夹并选中它，悬停说明这首歌写在哪里、怎么去掉。
- 歌单一次显示 10 首，可以滚动（拖旁边的滚动条，或在歌单上滚鼠标滚轮）；群系是歌单左边的一列，各带歌数。
- 纪念堂和点唱机的歌和原版一样只在附近听得到，跟随音效音量。
- 打开键可以是 Alt+D 这样的组合键：点页面标题栏的键位框后按下即可，右键清除。
- 页面支持英文和简体中文。
- 第一次启动时，一次性导入你在纯 pak 版页面上设好的内容：歌和音量，以及纯 pak 1.4 里每首歌自己的设置和播放模式。0.6.0 之前就用过本版的，只补上新的部分（三个新类别的歌、这里还没有的歌曲设置和播放模式）。

### 文件位置

- 歌：`FSD\Mods\CustomSoundtrack\`（与纯 pak 版共用）。
- 本版的设置、导入和页面加的歌、每首歌自己的设置、日志：`FSD\Saved\SaveGames\Mods\CustomSoundtrackNative\`（`Settings.ini`、`Imported\`、`SongSettings.txt`、`Log.txt`；旧版本的 `SongVolumes.txt` 仍然会读）。
- 控制台命令：`csn.status`、`csn.reload`、`csn.skip`、`csn.prev`、`csn.mode [shuffle|order|repeat]`、`csn.mode <类别或事件>[.<群系>] <模式或 follow>`。

### 注意

- 终端或 Esc 菜单开着时按打开键没有反应（按键被游戏界面截走）。
- 加载画面里洞穴音乐可能已经开始，轻轻垫在加载等待的歌下面，直到落地。原版音乐也是这样。
- 独占全屏时，文件选择框可能把游戏切到后台。
- 纯 pak 版 1.4 的“混入原版曲”本版没有。
- 页面和 `main.dll` 在同一个 zip 里，版本必须相同；不一致时页面会提示。
- 遇到问题：把 `FSD\Saved\SaveGames\Mods\CustomSoundtrackNative\Log.txt` 和 `ue4ss\UE4SS.log` 里 `[CustomSoundtrackNative]` 前后几行发过来。
- 卸载：在 mintcat 里禁用即可。歌的文件夹和歌单不受影响；需要的话删掉 `FSD\Saved\SaveGames\Mods\CustomSoundtrackNative\`。
- 直播时注意音乐版权。感谢 Miracoulon 制作的原版 Miracle's Custom Soundtrack。
- 自带的解码库：dr_flac、dr_mp3、dr_wav、stb_vorbis、speexdsp 的重采样器、libopus、opusfile、libogg，许可证见每个 Release 附带的 `THIRD-PARTY-NOTICES.txt`。

### 链接

- Custom Soundtrack 纯 pak 版（mod.io）：https://mod.io/g/drg/m/custom-soundtrack
- mintcat：https://github.com/iris-cat-dev/mintcat
