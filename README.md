# **GOFREE · 赛博菩萨 Cloudflare**

> 一个充满科技感与温馨感的现代导航页，致敬 Cloudflare 免费生态。

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


| **地址**                                                 | **说明** |
| :------------------------------------------------------ | :------ |
| [gofree.ggff.net](https://gofree.ggff.net/)            | 主站     |
| [GitHub Repo](https://github.com/your-username/gofree) | 源码仓库   |


> 如果你的域名也绑定在 Cloudflare 上，可以直接 Fork 本仓库，修改 `index.html` 中的链接后部署。

---

## **🚀 部署指南**

### **方式一：Cloudflare Pages（推荐）**

1. **Fork 本仓库**
2. 登录 [Cloudflare Dashboard](https://dash.cloudflare.com/) → **Workers &amp; Pages** → **Create** → **Pages** → **Connect to Git**
3. 选择你 Fork 的仓库，配置如下：
   
   | **配置项**                | **值**  |
   | :---------------------- | :------ |
   | Production branch      | `main` |
   | Build command          | *(留空)* |
   | Build output directory | `/`    |
   
4. 点击 **Save and Deploy**，等待部署完成
5. 进入 **Custom domains** → 添加 `gofree.ggff.net`
6. 在域名 DNS 中添加 CNAME 记录指向 Pages 分配的域名

### **方式二：直接上传**

bash

```plaintext
# 1. 克隆仓库
git clone https://github.com/your-username/gofree.git
cd gofree

# 2. 直接拖拽 index.html 到 Cloudflare Pages 的 Upload 界面
```

### **方式三：Wrangler CLI**

bash

```plaintext
npm install -g wrangler
wrangler pages deploy . --project-name=gofree
```

---

## **🛠️ 自定义**

所有内容都集中在 `index.html` 的 `<script>` 标签内，数据格式如下：

javascript

```plaintext
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


| **内容**      | **位置**                              |
| :----------- | :----------------------------------- |
| 标题 `GOFREE` | `<h1>GOFREE</h1>`                   |
| 副标题         | `<p class="hero-sub">`              |
| 煽情文案        | `<p class="hero-desc">`             |
| 统计数字        | 自动计算（基于 `DATA` 数组长度）                |
| 页脚文案        | `<footer class="footer">`           |
| 主题色         | CSS 变量 `--accent` / `--accent-blue` |


### **更换主题色**

css

```plaintext
:root {
  --accent: #f6821f;        /* Cloudflare 橙 */
  --accent-blue: #2563eb;   /* 科技蓝 */
  --bg: #f6f8fb;            /* 背景色 */
}
```

---

## **📁 项目结构**

text

```plaintext
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

[MIT](https://license/) © 2025 GOFREE

---

## **💛 致谢**

- [Cloudflare](https://www.cloudflare.com/) — 赛博菩萨，永远免费
- [awesome-cloudflare-selfhosted](https://github.com/theoephraim/awesome-cloudflare-selfhosted) — 项目数据来源
- 每一个把数字生命搬进边缘网络的开发者

---

**GOFREE · 赛博菩萨 Cloudflare**

*永远免费，永远热泪盈眶*

⬆ 回到顶部



---

