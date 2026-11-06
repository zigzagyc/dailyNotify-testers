# PNCC Care (dailyNotify) Video Production & Improvement Guide
# 视频制作与二次开发全流程维护指南

本文档旨在为后续接手的剪辑师、产品经理、技术支持或开发人员提供**开箱即用（Out-of-the-Box）的视频制作与二次优化指南**。通过本项目提供的模块化自动化流水线，任何接手人均可在数分钟内修改幻灯片文案、替换专业真人配音、重录 App 操作片段或重新压制完整视频。

---

## 目录结构速览 (Repository Assets)

```
Docs/manuals/
├── PNCC_Care_Demo_ZH.mp4            # 中文全套 20 章节最终广播级视频 (~13 分 25 秒)
├── PNCC_Care_Demo_ZH.srt            # 中文标准外挂/内嵌字幕文件
├── PNCC_Care_Demo_EN.mp4            # 英文全套 20 章节最终广播级视频 (~12 分 04 秒)
├── PNCC_Care_Demo_EN.srt            # 英文标准外挂/内嵌字幕文件
├── Audio_Review_Player.html         # 音频试听审查器（浏览器直接双击打开，支持逐句试听与对照）
│
├── audio_materials/                 # 核心解说音频原素材库
│   ├── zh/                          # 中文 1~20 章独立 MP3（sec_01.mp3 ~ sec_20.mp3）
│   └── en/                          # 英文 1~20 章独立 MP3（sec_01.mp3 ~ sec_20.mp3）
│
├── assets/videos/                   # 右侧真实真机/模拟器录屏片段库
│   ├── CLIP_01_LAUNCH_OVERVIEW.mp4  # 中文各章操作视频 (01~20)
│   └── CLIP_01_LAUNCH_OVERVIEW_EN.mp4 # 英文各章操作视频 (01~20)
│
├── video_production/                # 自动化装配中间产物（临时背景图、片段分段，可随时重新生成）
│
scripts/
├── generate_auto_video.py           # 视频装配总控流水线（合成背景+录屏+语音+字幕+无缝拼接）
├── record_demo_clips.py             # 模拟器自动化录屏脚本（与 Flutter 原生 App 实时通讯）
├── generate_pptx_and_video_script.py # 中文幻灯片元数据、解说词字典与 PPTX 导出脚本
├── slides_data_en.py                # 纯英文幻灯片元数据字典（无任何中文字符）
└── generate_bilingual_video_script.py # 双语解说词与时间戳字典

lib/
└── screenshot_runner.dart           # 原生 Flutter 界面投屏与自动化控制器 (Port 8899)
```

---

## 核心工作流与二次开发场景

### 场景一：只替换解说音频（例如更换真人录音或调整语速）

流水线采用**“音频解耦优先”**设计：
1. **替换音频**：将新的录音文件重命名为对应的章节编号（例如第 5 页为 `sec_05.mp3`），直接放入 `Docs/manuals/audio_materials/zh/` 或 `Docs/manuals/audio_materials/en/` 覆盖对应文件。
2. **试听检查**：双击在浏览器中打开 `Docs/manuals/Audio_Review_Player.html`，无需打开视频即可直接逐页听取音频质量与连贯性。
3. **重新合成**：
   - 预览单页效果（约 3 秒）：
     ```bash
     python3 scripts/generate_auto_video.py --sec 05 --lang zh
     ```
   - 重新压制整套视频（自动重新对齐字幕与拼接）：
     ```bash
     python3 scripts/generate_auto_video.py --all --lang both
     ```

---

### 场景二：修改幻灯片标题、分类或 4 点核心文字

1. **修改中文文字**：编辑 `scripts/generate_pptx_and_video_script.py` 中的 `SLIDES_DATA` 字典。
2. **修改英文文字**：编辑 `scripts/slides_data_en.py` 中的 `SLIDES_DATA_EN` 字典。
3. **重新渲染视频**：
   流水线中的 `render_slide_backdrop()` 会使用 Pillow 自动进行高清字形绘制与单词折行换行：
   ```bash
   python3 scripts/generate_auto_video.py --all --lang both
   ```

---

### 场景三：更新或重录手机操作视频片段

右侧演示使用的是来自 `lib/screens/` 的原生真实界面（无任何手工假 Mockup）：
1. **启动模拟器**：
   打开 iOS 模拟器（推荐 iPhone 15）。
2. **启动 Flutter 控制器**：
   ```bash
   flutter run -d <iPhone_Simulator_UUID> -t lib/screenshot_runner.dart
   ```
   *应用启动后会在手机本地监听 `http://127.0.0.1:8899` 端口。*
3. **一键自动化重录所有操作片段**：
   ```bash
   python3 scripts/record_demo_clips.py --lang both
   ```
   *若只重录某一个章节（如第 9 章照顾者端）：*
   ```bash
   python3 scripts/record_demo_clips.py --sec 09 --lang both
   ```
4. **重新合成视频**：
   ```bash
   python3 scripts/generate_auto_video.py --all --lang both
   ```

---

## 环境依赖清单 (Prerequisites)

后续接手者在运行前请确认本地安装了以下工具：
- **ffmpeg** (建议 5.0+): 用于音视频混流、PTS重采样与无缝串接 (`brew install ffmpeg`)
- **Python 3.9+**:
  - `Pillow`: 用于幻灯片背景卡片绘制
  - `edge-tts`: 用于微软神经语音备用合成
  - `python-docx` / `python-pptx`: 用于生成对应的文档与幻灯片文件
- **Flutter SDK** (可选，仅在重新捕获操作画面时需要)

---

## 核心设计规范与避坑要点 (Strict Rules)

1. **绝不使用假 Mockup 界面**：
   所有的手机端操作画面必须通过 `lib/screenshot_runner.dart` 严格调用 `lib/screens/` 中的真实组件（`HomeScreen`, `CaregiverScreen`, `MyCaregiversScreen`, `SettingsScreen` 等）。
2. **语言严格隔离**：
   英文版左侧卡片只读取 `SLIDES_DATA_EN`，右侧屏幕参数传入 `lang=en`，严禁在英文版中出现中文字符。
3. **业务逻辑准确性**：
   - 系统为**滚动自适应超时机制（Rolling Inactivity Timer）**，绝无“固定 10:00 截止打卡”之说；
   - 警报延时为 **Timer 2 - Timer 1**，用户可在设置中完全自定义分钟数，绝非固定的“25分钟”；
   - 照顾者列表使用系统通用默认人像图标，不使用任何虚构的长辈真人照片。
