# SilentXx Components

SilentXx 主题开源的 Astro 组件合集 — 从 [silentxx.com](https://silentxx.com) 主站主题中提取的独立组件，通用、干净、可直接复用。

Open-source Astro components extracted from the SilentXx theme. Clean, reusable, framework-agnostic (Astro + React).

## 组件列表 / Components

### 🎵 Music
| 组件 | 说明 | 依赖 |
|------|------|------|
| `GlobalMusicPlayer-EyeVersion` | 大眼睛音乐播放器（纯前端、随机播放、眨眼动画） | 无 |

### 🎨 Theme
| 组件 | 说明 | 依赖 |
|------|------|------|
| `ThemeToggle` | 明暗主题切换开关 | 无 |
| `LanguageSwitcher` / `LanguageSwitcherPopup` | 中英文切换 | `@lib/i18n` |

### ✨ Fun
| 组件 | 说明 | 依赖 |
|------|------|------|
| `QuoteMarquee` | 名言跑马灯 | 无 |
| `WaterfallFlow` | 瀑布流 | 无 |
| `FloatingColorBalls` | 漂浮彩球动画 | 无 |
| `Lollipop` | 棒棒糖动画 | 无 |
| `StarryBackground` | 星空背景 | 无 |

### 📝 Post / Blog
| 组件 | 说明 | 依赖 |
|------|------|------|
| `PostItemCard` | 文章卡片 | `@lib/content`, `@lib/datetime`, `@lib/route` |
| `Paginator` | 分页器 | 无 |
| `CategoryCards` | 分类卡片 | `@lib/content`, `@lib/i18n`, `@lib/route` |
| `SeriesNavigation` | 系列文章导航 | 无 |

### 🧩 Common / UI
| 组件 | 说明 | 依赖 |
|------|------|------|
| `CustomContent` | 文章内容增强（外链新窗口 + 平滑滚动） | 无 |
| `avatar` / `badge` / `button` / `card` / `divider` / `popover` / `segmented` / `MenuIcon` | UI 基础组件 (React) | `@lib/utils` |

## 使用 / Usage

组件库依赖 `@` 别名（指向仓库 `src/`）。在你的 Astro 项目中配置：

```ts
// astro.config.mjs
import { defineConfig } from 'astro/config';
import react from '@astrojs/react';
import tailwindcss from '@tailwindcss/vite';

export default defineConfig({
  integrations: [react()],
  vite: {
    plugins: [tailwindcss()],
    resolve: {
      alias: { '@': new URL('./src', import.meta.url) }
    }
  }
});
```

然后将需要的组件复制到你的项目 `src/components/` 下（连同 `src/lib/`、`src/constants/` 中对应依赖）。

示例 — 大眼睛音乐播放器：

```astro
---
import GlobalMusicPlayer from '@components/music/GlobalMusicPlayer-EyeVersion.astro';
---
<GlobalMusicPlayer />
```

## 说明 / Notes

- 本组件库只包含**通用组件**，不含任何交易数据、账户信息或私人内容（主站生产版为私有仓库）。
- 组件保持原样提取，仅剥离了主站内部的数据依赖。
- This library contains only generic UI components. No trading data, account info, or private content (the production site repo is private).

## License

MIT
