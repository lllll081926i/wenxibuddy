# WXiBuddy

> **Liquid Glass** 暗黑生产力前端 · 智能任务与项目管理  
> React 19 · TypeScript · Vite · Tailwind CSS v4 · Framer Motion

高保真液态毛玻璃（Liquid Glass）风格的企业级任务管理系统，含 **8 个完整功能页**、统一二级弹窗、自定义下拉、全程动效与可交互演示数据。

---

## ✨ 特性

- 🌑 **纯黑 Void + Liquid Glass** 材质（blur / 顶缘高光 / 透光）
- 🧭 **8 大模块**：任务 · 总览 · 文件 · 日程 · 团队 · 智能分析 · 知识库 · 设置
- 🃏 **3D CoverFlow** 文档堆：滚轮切卡、每卡播放钮、自适应尺寸
- 📅 **项目时间线** 按真实日期对齐甘特条 + 周/双周/月尺度
- 🔔 **消息 / 站内信 / 预约 / 编辑** 统一 `LiquidModal` 弹窗动效
- 🎛️ **LiquidSelect** 全站无原生 `<select>`
- ↔️ **左右流体布局**：侧栏 / 主区 / 详情随视口 `clamp` 伸缩
- 🎬 **切换必有动效**：路由、日周月、Tab、筛选 pill、`layoutId`

设计规范见 **[DESIGN.md](./DESIGN.md)**。

---

## 🧩 模块一览

| 模块 | 能力 |
|------|------|
| **任务管理** | KPI、看板分组、CoverFlow、Gantt 时间线、AI 智能详情、新增/编辑/完成 |
| **项目总览** | 健康度 / 风险 / 团队 Tab、模块进度下钻 |
| **文件归档** | 分类搜索、上传、预览、下载、重命名、分享、删除 |
| **日程管理** | 月 / 周 / 日视图动效、预约编辑删除、优先级筛选 |
| **团队协作** | 成员矩阵、邀请、站内消息 |
| **智能分析** | 周期切换、KPI、提效建议、风险、漏斗、成员效能 |
| **知识库** | 搜索、分类、发布、收藏、分享 |
| **设置中心** | 主题 / 模糊 / AI / 通知 / 账号 / 安全 / 系统 |

---

## 🛠️ 技术栈

| 层 | 选型 |
|----|------|
| 框架 | React 19 + TypeScript |
| 构建 | Vite 6 |
| 样式 | Tailwind CSS v4（`@tailwindcss/vite`） |
| 动效 | Framer Motion |
| 图标 | Lucide React |
| 反馈 | canvas-confetti |

---

## 🚀 快速开始

```bash
# 安装依赖
npm install

# 本地开发（默认 http://localhost:3000）
npm run dev

# 生产构建
npm run build

# 预览构建产物
npm run preview
```

---

## 📁 目录结构

```text
src/
  components/
    dashboard/     # KPI · 看板 · CoverFlow · 时间线 · 智能详情
    layout/        # Sidebar · TopBar
    modals/        # 任务 / 通知 / 文档预览等
    ui/            # LiquidModal · LiquidSelect · GlassCard · 过渡
  context/         # 全局任务 / 文档 / 主题状态
  pages/           # 8 个功能页
  lib/motion.ts    # 动效 tokens
  index.css        # 液态玻璃 + 流体布局
DESIGN.md          # 设计系统真源（必读）
```

---

## 🖱️ 交互速览

- 侧栏切换 8 页（带方向滑入动效）
- 「新增任务」写入全局列表，看板与 KPI 联动
- 点任务行 → 右侧智能详情同步
- CoverFlow **滚轮**切卡，卡片右下角 Play 预览文档
- 时间线条 / 阶段点击联动任务
- 铃铛 / 邮件打开 **弹窗**（非顶栏硬下拉）
- 设置里改主题色与毛玻璃模糊会写入 CSS 变量

---

## ☁️ 部署

`npm run build` 产物在 `dist/`，可托管到 Vercel / Netlify / Cloudflare Pages / OSS / Nginx。

SPA 需 fallback 到 `index.html`：

```nginx
server {
  listen 80;
  root /var/www/wenxibuddy/dist;
  index index.html;
  location / {
    try_files $uri $uri/ /index.html;
  }
}
```

---

## 📄 License

MIT — 演示与学习用途。界面风格致敬高保真 Liquid Glass 设计稿。
