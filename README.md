# **GOFREE · 赛博菩萨 Cloudflare**

> 一个充满科技感与温馨感的现代导航页，致敬 Cloudflare 免费生态。

**中文** | [English](#english)

---

## **📖 简介**

**GOFREE** 是一个单文件的现代导航页，收录了 [awesome-cloudflare-selfhosted](https://github.com/theoephraim/awesome-cloudflare-selfhosted) 中所有可部署在 Cloudflare 上的自托管项目。

它不只是一个链接列表——它是一座桥，连接着每一个想用免费额度搭建数字家园的人。

> 世界上有一种温柔，叫做 **Cloudflare 永远免费**。  
> 没有月租，没有宕机，没有「您的套餐已到期」。  
> 只有 Workers 在运行，D1 在低语，R2 在守候。

---

## **✨ 特性**

- 🎨 **浅色科技风** — 温暖、明亮、不刺眼，拒绝深色主题
- 🔍 **实时搜索** — 支持项目名、英文描述、中文描述、标签、分类多维度检索
- 📂 **自动分类** — 15+ 分类，120+ 项目，卡片式布局自动分组
- 🌏 **中英双语** — 每个项目保留英文原名，附带英文原描述 + 中文翻译
- 🏷️ **标签系统** — 标注项目依赖的 Cloudflare 服务（D1 / R2 / KV / Durable Objects / Workers AI 等）
- 📱 **响应式设计** — 桌面、平板、手机全适配
- ⚡ **零依赖** — 单个 HTML 文件，无需构建，无需框架，无需后端
- 🚀 **一键部署** — 拖进 Cloudflare Pages 即可上线

---

## **🖥️ 在线预览**

| **地址** | **说明** |
| :--- | :--- |
| [gofree.ggff.net](https://gofree.ggff.net/) | 主站 |
| [GitHub Repo](https://github.com/tidesea/cloudflare-app-list) | 源码仓库 |

> 如果你的域名也绑定在 Cloudflare 上，可以直接 Fork 本仓库，修改 `index.html` 中的链接后部署。

---

## **🚀 部署指南**

### **方式一：Cloudflare Pages（推荐）**

1. **Fork 本仓库**
2. 登录 [Cloudflare Dashboard](https://dash.cloudflare.com/) → **Workers & Pages** → **Create** → **Pages** → **Connect to Git**
3. 选择你 Fork 的仓库，配置如下：

   | **配置项** | **值** |
   | :--- | :--- |
   | Production branch | `main` |
   | Build command | *(留空)* |
   | Build output directory | `/` |

4. 点击 **Save and Deploy**，等待部署完成
5. 进入 **Custom domains** → 添加 `gofree.ggff.net`
6. 在域名 DNS 中添加 CNAME 记录指向 Pages 分配的域名

### **方式二：直接上传**

```bash
# 1. 克隆仓库
git clone https://github.com/your-username/gofree.git
cd gofree

# 2. 直接拖拽 index.html 到 Cloudflare Pages 的 Upload 界面
```

### **方式三：Wrangler CLI**

```bash
npm install -g wrangler
wrangler pages deploy . --project-name=gofree
```

---

## **🛠️ 自定义**

所有内容都集中在 `index.html` 的 `<script>` 标签内，数据格式如下：

```javascript
const DATA = [
  {
    cat: "📊 Analytics",              // 分类（emoji + 名称）
    name: "Counterscale",              // 项目英文名（保持不变）
    desc: "Google Analytics alternative...",  // 英文描述
    descZh: "基于 Analytics Engine 的...",     // 中文描述
    url: "https://github.com/...",     // 项目链接
    tags: ["R2", "Analytics Engine"]   // 标签
  },
  // ...
];
```

### **修改站点信息**

| **内容** | **位置** |
| :--- | :--- |
| 标题 `GOFREE` | `<h1>GOFREE</h1>` |
| 副标题 | `<p class="hero-sub">` |
| 煽情文案 | `<p class="hero-desc">` |
| 统计数字 | 自动计算（基于 `DATA` 数组长度） |
| 页脚文案 | `<footer class="footer">` |
| 主题色 | CSS 变量 `--accent` / `--accent-blue` |

### **更换主题色**

```css
:root {
  --accent: #f6821f;        /* Cloudflare 橙 */
  --accent-blue: #2563eb;   /* 科技蓝 */
  --bg: #f6f8fb;            /* 背景色 */
}
```

---

## **📁 项目结构**

```text
gofree/
├── index.html      # 全部内容（HTML + CSS + JS）
├── README.md       # 本文件
└── LICENSE         # MIT
```

没错，只有一个文件。

---

## **🧩 数据来源**

本项目数据来自：

- [awesome-cloudflare-selfhosted](https://github.com/theoephraim/awesome-cloudflare-selfhosted) — 由 [@theoephraim](https://github.com/theoephraim) 维护
- 收录范围：所有可部署在 Cloudflare 上的开源自托管项目
- 更新方式：手动同步，或提交 PR 自动追加

如果你发现某个项目已失效、描述有误、或想新增项目，欢迎提交 PR。

---

## **🤝 贡献**

欢迎任何形式的贡献！

1. Fork 本仓库
2. 创建分支：`git checkout -b feat/add-project`
3. 在 `DATA` 数组中添加或修改条目
4. 提交：`git commit -m "feat: add xxx project"`
5. 推送：`git push origin feat/add-project`
6. 发起 Pull Request

**贡献规范：**

- 项目名称保持英文原文
- 英文描述尽量简洁（1-2 句）
- 中文描述准确传达功能
- 标签使用 Cloudflare 官方服务名（D1、R2、KV、Durable Objects、Workers AI、Queues、Workflows、Cron、Email、Images、Vectorize、Hyperdrive、Browser Rendering、Analytics Engine、AI Gateway、Pipelines、Containers）
- 分类尽量归入已有类别，如需新类别请说明理由

---

## **📜 License**

[MIT](https://opensource.org/licenses/MIT) © 2025 GOFREE

---

## **💛 致谢**

- [Cloudflare](https://www.cloudflare.com/) — 赛博菩萨，永远免费
- [awesome-cloudflare-selfhosted](https://github.com/theoephraim/awesome-cloudflare-selfhosted) — 项目数据来源
- 每一个把数字生命搬进边缘网络的开发者

---

**GOFREE · 赛博菩萨 Cloudflare**

*永远免费，永远热泪盈眶*

[⬆ 回到顶部](#gofree--赛博菩萨-cloudflare)

---
---

<a name="english"></a>

# **GOFREE · Cyber Bodhisattva Cloudflare**

> A modern navigation page that blends tech vibes with warmth, paying tribute to Cloudflare's free ecosystem.

[中文](#gofree--赛博菩萨-cloudflare) | **English**

---

## **📖 Introduction**

**GOFREE** is a single-file modern navigation page that collects all self-hosted projects deployable on Cloudflare from [awesome-cloudflare-selfhosted](https://github.com/theoephraim/awesome-cloudflare-selfhosted).

It's more than a link list — it's a bridge connecting everyone who wants to build a digital home with free tiers.

> There is a kind of tenderness in this world called **Cloudflare is forever free**.  
> No monthly fees, no downtime, no "your plan has expired".  
> Only Workers running, D1 whispering, R2 watching over.

---

## **✨ Features**

- 🎨 **Light tech theme** — Warm, bright, easy on the eyes. No dark mode.
- 🔍 **Real-time search** — Search across project names, English descriptions, Chinese descriptions, tags, and categories.
- 📂 **Auto categorization** — 15+ categories, 120+ projects, card layout grouped automatically.
- 🌏 **Bilingual** — Each project keeps its English name, with original English description plus Chinese translation.
- 🏷️ **Tag system** — Labels showing which Cloudflare services a project depends on (D1 / R2 / KV / Durable Objects / Workers AI, etc.).
- 📱 **Responsive** — Fully adapted for desktop, tablet, and mobile.
- ⚡ **Zero dependencies** — Single HTML file. No build, no framework, no backend.
- 🚀 **One-click deploy** — Drag into Cloudflare Pages and go live.

---

## **🖥️ Live Preview**

| **URL** | **Description** |
| :--- | :--- |
| [gofree.ggff.net](https://gofree.ggff.net/) | Main site |
| [GitHub Repo](https://github.com/your-username/gofree) | Source code |

> If your domain is also on Cloudflare, you can fork this repo, modify the links in `index.html`, and deploy.

---

## **🚀 Deployment Guide**

### **Option 1: Cloudflare Pages (Recommended)**

1. **Fork this repo**
2. Log in to [Cloudflare Dashboard](https://dash.cloudflare.com/) → **Workers & Pages** → **Create** → **Pages** → **Connect to Git**
3. Select your forked repo and configure:

   | **Setting** | **Value** |
   | :--- | :--- |
   | Production branch | `main` |
   | Build command | *(leave empty)* |
   | Build output directory | `/` |

4. Click **Save and Deploy** and wait for deployment to finish.
5. Go to **Custom domains** → add `gofree.ggff.net`
6. Add a CNAME record in your DNS pointing to the Pages-assigned domain.

### **Option 2: Direct Upload**

```bash
# 1. Clone the repo
git clone https://github.com/your-username/gofree.git
cd gofree

# 2. Drag and drop index.html into Cloudflare Pages Upload interface
```

### **Option 3: Wrangler CLI**

```bash
npm install -g wrangler
wrangler pages deploy . --project-name=gofree
```

---

## **🛠️ Customization**

Everything is inside the `<script>` tag in `index.html`. Data format:

```javascript
const DATA = [
  {
    cat: "📊 Analytics",              // Category (emoji + name)
    name: "Counterscale",              // Project English name (keep as is)
    desc: "Google Analytics alternative...",  // English description
    descZh: "基于 Analytics Engine 的...",     // Chinese description
    url: "https://github.com/...",     // Project link
    tags: ["R2", "Analytics Engine"]   // Tags
  },
  // ...
];
```

### **Modify Site Info**

| **Content** | **Location** |
| :--- | :--- |
| Title `GOFREE` | `<h1>GOFREE</h1>` |
| Subtitle | `<p class="hero-sub">` |
| Hero copy | `<p class="hero-desc">` |
| Stats | Auto-calculated (based on `DATA` array length) |
| Footer copy | `<footer class="footer">` |
| Theme colors | CSS variables `--accent` / `--accent-blue` |

### **Change Theme Colors**

```css
:root {
  --accent: #f6821f;        /* Cloudflare orange */
  --accent-blue: #2563eb;   /* Tech blue */
  --bg: #f6f8fb;            /* Background */
}
```

---

## **📁 Project Structure**

```text
gofree/
├── index.html      # Everything (HTML + CSS + JS)
├── README.md       # This file
└── LICENSE         # MIT
```

Yep, just one file.

---

## **🧩 Data Source**

Data comes from:

- [awesome-cloudflare-selfhosted](https://github.com/theoephraim/awesome-cloudflare-selfhosted) — maintained by [@theoephraim](https://github.com/theoephraim)
- Scope: all open-source self-hosted projects deployable on Cloudflare
- Updates: manual sync, or automatically appended via PR

If you find a project that's dead, a description that's wrong, or want to add a new project, feel free to submit a PR.

---

## **🤝 Contributing**

Any form of contribution is welcome!

1. Fork this repo
2. Create a branch: `git checkout -b feat/add-project`
3. Add or modify entries in the `DATA` array
4. Commit: `git commit -m "feat: add xxx project"`
5. Push: `git push origin feat/add-project`
6. Open a Pull Request

**Guidelines:**

- Keep project names in their original English form
- Keep English descriptions concise (1–2 sentences)
- Chinese descriptions should accurately convey the functionality
- Use official Cloudflare service names for tags (D1, R2, KV, Durable Objects, Workers AI, Queues, Workflows, Cron, Email, Images, Vectorize, Hyperdrive, Browser Rendering, Analytics Engine, AI Gateway, Pipelines, Containers)
- Try to fit into existing categories; if a new category is needed, explain why

---

## **📜 License**

[MIT](https://opensource.org/licenses/MIT) © 2025 GOFREE

---

## **💛 Credits**

- [Cloudflare](https://www.cloudflare.com/) — Cyber Bodhisattva, forever free
- [awesome-cloudflare-selfhosted](https://github.com/theoephraim/awesome-cloudflare-selfhosted) — Data source
- Every developer who moved their digital life to the edge

---

**GOFREE · Cyber Bodhisattva Cloudflare**

*Forever free, forever moved to tears*

[⬆ Back to top](#gofree--cyber-bodhisattva-cloudflare)
