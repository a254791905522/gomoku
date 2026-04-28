# iOS App — App Store 发布规范

> Starry Gomoku 发布检查清单

---

## 项目信息

| 字段 | 值 |
|------|-----|
| App 名称 | `Starry Gomoku` |
| Bundle ID | `com.company.gomoku` |
| 版本号 | `1.0.0` |
| 构建号 | `1` |
| 版权 | `© 2026 Starry Gomoku` |
| App Store Connect Team | `待填入` |

---

## 输出文件目录结构

```
publish/gomoku/
├── index.html              # 游戏介绍页（全英文）
├── privacy.html            # 隐私政策页（全英文）
── PUBLISH_CHECKLIST.md    # 本清单
├── screenshots_65/         # iPhone 6.5寸 (1284×2778) — 5 张
│   ├── 01_menu.png
│   ├── 02_early_gameplay.png
│   ├── 03_gameplay.png
│   ├── 04_level_select.png
│   ── 05_gameover.png
└── screenshots_55/         # iPhone 5.5寸 (1242×2208) — 5 张
    ├── 01_menu.png
    ├── 02_early_gameplay.png
    ├── 03_gameplay.png
    ├── 04_level_select.png
    └── 05_gameover.png
```

---

## 1. Archive 构建

### 构建命令
```bash
cd /path/to/project
xcodebuild -project StarryGomoku.xcodeproj \
  -scheme StarryGomoku \
  -configuration Release \
  clean archive \
  -archivePath build/StarryGomoku.xcarchive
```

### Archive 检查清单
- [ ] `productName` = `StarryGomoku`（project.pbxproj）
- [ ] `PRODUCT_BUNDLE_IDENTIFIER` = `com.company.gomoku`
- [ ] `CFBundleDisplayName` = `Starry Gomoku`（Info.plist）
- [ ] App Icon 无 Alpha 通道（RGB 模式，非 RGBA）
- [ ] `ITSAppUsesNonExemptEncryption` = false（Info.plist）

---

## 2. 上传方式

### Transporter（推荐）
1. Mac App Store 下载 [Transporter](https://apps.apple.com/us/app/transporter/id1450874784)
2. 打开后拖入 `.xcarchive` 文件
3. 点击 Deliver

---

## 3. App Store Connect 填写规范

### 基本信息

| 字段 | 填写内容 |
|------|---------|
| App 名称 | `Starry Gomoku` |
| 副标题 | `Gomoku Puzzle Challenge` |
| 主语言 | `English` |
| Bundle ID | `com.company.gomoku` |
| 版本号 | `1.0.0` |
| 隐私政策 URL | `https://your-domain.com/privacy.html` |

### 关键词（100字符限制，逗号分隔无空格）
```
gomoku,puzzle,board,logic,strategy,casual,five in a row,brain,mind,game
```
> 字符数：~70（含逗号）

### 推广文本（170字符）
```
Challenge your mind with 150 cosmic puzzle levels! Master Gomoku strategy with undo, hints, and a star rating system. Free, offline, no ads.
```

### 描述（4000字符）
```
Starry Gomoku transforms the classic five-in-a-row board game into an addictive puzzle experience set against a beautiful cosmic backdrop.

★ 150 UNIQUE PUZZLE LEVELS
Progressively challenging Gomoku puzzles that test your strategic thinking. Each level requires you to place pieces carefully to form five in a row.

★ UNDO & HINT SYSTEM
Made a wrong move? No problem! Undo your moves or use hints to get guidance when you're stuck.

★ STAR RATING SYSTEM
Complete levels efficiently to earn up to 3 stars per level. Can you achieve a perfect score across all 150 levels?

★ SPACE-THEMED DESIGN
Enjoy a stunning cosmic aesthetic with stars, planets, and nebulae while you play. A relaxing visual experience for focused gameplay.

★ 100% FREE — NO ADS
No in-app purchases. No advertisements. No login required. No data collection. Play anytime, anywhere — completely offline.

Whether you're a Gomoku beginner or a seasoned player looking for a puzzle twist, Starry Gomoku offers a fresh take on the beloved board game. Download now and start your cosmic puzzle journey!
```

### 版权
```
© 2026 Starry Gomoku
```

### 审核备注
```
This is a single-player puzzle game with no login, no ads, no in-app purchases, and no data collection. All 150 levels are available offline.
```

---

## 4. 加密文稿（第1页）

| 字段 | 选择 |
|------|------|
| 你的 App 是否使用加密？ | **否** |

---

## 5. 截图规格

### 必填尺寸

| 类型 | 尺寸 | 文件夹 |
|------|------|--------|
| iPhone 6.5寸 | **1284×2778 px** | `screenshots_65/` |
| iPhone 5.5寸 | **1242×2208 px** | `screenshots_55/` |

### 截图内容（5 张）

| 编号 | 文件名 | 说明 |
|------|--------|------|
| 01 | `01_menu.png` | 主菜单 — 游戏标题 "Starry Gomoku" 和 Play/Levels/Settings 按钮 |
| 02 | `02_early_gameplay.png` | 早期玩法 — 开局阶段，少量棋子在棋盘上 |
| 03 | `03_gameplay.png` | 核心玩法 — 进行中，棋盘上有较多棋子，展示 Undo/Hint 功能 |
| 04 | `04_level_select.png` | 关卡选择 — 150 关的关卡选择界面，分页浏览 |
| 05 | `05_gameover.png` | 游戏结束 — "Try Again" 重试界面 |

---

## 6. App 预览视频（可选）

本游戏暂无 App 预览视频。

---

## 7. 隐私政策页面 (privacy.html)

- [ ] `privacy.html` 已生成并部署到 `https://your-domain.com/privacy.html`
- [ ] 声明"不收集、不存储、不传输任何个人信息"
- [ ] 声明不含广告 SDK、分析工具等第三方集成
- [ ] 声明适合所有年龄用户
- [ ] 声明游戏数据仅存储在设备本地

---

## 8. 游戏介绍页面 (index.html)

- [ ] `index.html` 已生成，全英文
- [ ] 引用 `screenshots_65/` 目录下的截图
- [ ] 包含游戏描述、功能特性、下载按钮

---

## 9. 提交流程

- [ ] 准备输出文件目录（截图 + index.html + privacy.html）
- [ ] 执行 Archive 构建并验证检查清单
- [ ] 通过 Transporter 上传 `.xcarchive`
- [ ] 登录 App Store Connect 创建 App
- [ ] 填写基本信息（名称、Bundle ID、关键词、描述等）
- [ ] 上传截图（6.5寸 + 5.5寸，各 5 张）
- [ ] 填写加密文稿（选"否"）
- [ ] 填写隐私政策 URL
- [ ] 提交审核

---

## 10. 快速复制汇总

| 字段 | 内容 |
|------|------|
| **App 名称** | `Starry Gomoku` |
| **副标题** | `Gomoku Puzzle Challenge` |
| **Bundle ID** | `com.company.gomoku` |
| **版本号** | `1.0.0` |
| **版权** | `© 2026 Starry Gomoku` |
| **关键词** | `gomoku,puzzle,board,logic,strategy,casual,five in a row,brain,mind,game` |
| **推广文本** | `Challenge your mind with 150 cosmic puzzle levels! Master Gomoku strategy with undo, hints, and a star rating system. Free, offline, no ads.` |
| **隐私政策** | `https://your-domain.com/privacy.html` |
| **加密** | 否 |
| **审核备注** | `This is a single-player puzzle game with no login, no ads, no in-app purchases, and no data collection.` |

---

## 11. 描述全文（直接复制用）

```
Starry Gomoku transforms the classic five-in-a-row board game into an addictive puzzle experience set against a beautiful cosmic backdrop.

★ 150 UNIQUE PUZZLE LEVELS
Progressively challenging Gomoku puzzles that test your strategic thinking. Each level requires you to place pieces carefully to form five in a row.

★ UNDO & HINT SYSTEM
Made a wrong move? No problem! Undo your moves or use hints to get guidance when you're stuck.

★ STAR RATING SYSTEM
Complete levels efficiently to earn up to 3 stars per level. Can you achieve a perfect score across all 150 levels?

★ SPACE-THEMED DESIGN
Enjoy a stunning cosmic aesthetic with stars, planets, and nebulae while you play. A relaxing visual experience for focused gameplay.

★ 100% FREE — NO ADS
No in-app purchases. No advertisements. No login required. No data collection. Play anytime, anywhere — completely offline.

Whether you're a Gomoku beginner or a seasoned player looking for a puzzle twist, Starry Gomoku offers a fresh take on the beloved board game. Download now and start your cosmic puzzle journey!
```
