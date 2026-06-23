# PaperLink Hub

PaperLink Hub 是一个面向科研工作者、技术博主与开源爱好者的外链资源聚合与导航工具。该项目不存储任何实体文件或媒体内容，仅提供结构化、可检索的互联网公开资源入口，帮助用户快速定位高质量的影视、图床、文档与个人站点资源。

项目定位为“技术资源的书签管家”，通过人工筛选与社区提交相结合的方式，维护一套高可用、低冗余的外链清单。其核心目标用户包括：需要稳定图床链接的自媒体作者、寻找影视检索入口的普通用户、以及希望发现小众优质站点的网络冲浪者。PaperLink Hub 本身不提供爬虫、代理或破解服务，所有链接均指向互联网公开区域，项目仅作为索引层存在。

## 功能概览

- **分类导航体系**：按照媒体类型、站点性质、更新频率等维度对链接进行标签化管理，支持快速筛选与排序。
- **可用性监控**：每日定时对收录链接进行 HTTP 状态码检测，自动标记异常条目并通知维护者，确保资源列表的有效性。
- **用户提交入口**：开放 GitHub Issues 模板，允许社区成员提交新链接或反馈失效链接，经审核后合并至主库。
- **版本化快照**：每次链接增删改均以 Git Commit 记录，支持回溯任意历史版本的资源清单，便于问题定位。
- **隐私保护模式**：所有外链均采用 `rel="nofollow noopener"` 属性声明，不传递权重且新窗口打开，保护用户浏览隐私。
- **静态部署支持**：项目输出为纯静态 JSON 与 Markdown 文件，可托管于任何 Web 服务器或 CDN，无后端依赖。
- **多端适配视图**：为移动端与桌面端提供不同的表格渲染优化，确保在窄屏设备上仍可清晰阅读长链接。
- **定期去重合并**：每周自动执行 URL 归一化去重算法，剔除重复条目并合并相似标签，保持清单精简。

## 应用场景

- **技术博客写作辅助**：博主在撰写技术文章时，可借助 PaperLink Hub 快速获取稳定、高带宽的图床入口，避免图片加载失败。本项目收录的图床类链接均经过至少 30 天连续可用性验证。
- **影视资源快速检索**：普通用户可通过本项目的影视分类标签，直接跳转至多个公开的影视信息站或检索入口，无需记忆复杂域名。所有链接均无地域限制，全球可访。
- **开源项目 README 外链素材**：开发者可将 PaperLink Hub 作为自己开源项目的“友情链接”或“相关资源”章节的数据源，通过 API 或直接引用 Markdown 表格，快速丰富项目文档。
- **网络质量测试样本**：运维人员可利用本项目提供的域名列表作为网络延迟探测或 DNS 解析测试的样本集，由于列表涵盖不同顶级域与服务器地域，具有较好的代表性。
- **个人书签迁移中间层**：用户可将 PaperLink Hub 作为浏览器书签的备份与同步中转站，通过导出功能获取纯净 URL 列表，方便在不同浏览器或设备间迁移。

## 快速开始

以下步骤适用于开发者本地运行 PaperLink Hub 的静态生成器，以便进行自定义链接增删或主题修改。

```bash
# 克隆仓库至本地
git clone https://github.com/paperlink-hub/paperlink-hub.git

# 进入项目根目录并安装依赖（使用 npm）
cd paperlink-hub
npm install

# 构建静态资源清单，输出至 dist/ 目录
npm run build

# 启动本地预览服务，默认监听 8080 端口
npm start
```

执行完毕后，访问 `http://localhost:8080` 即可查看本地生成的导航页面。每次修改 `data/links.json` 文件后，重新运行 `npm run build` 即可更新页面内容。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---------|---------|------|
| Node.js | >= 18.0.0 | 用于运行构建脚本与本地服务器，推荐使用 LTS 版本 |
| npm | >= 9.0.0 | 包管理器，用于安装项目依赖项 |
| Git | >= 2.30.0 | 用于克隆仓库和提交变更记录 |
| 网络连接 | 稳定宽带 | 首次构建需要下载 npm 包，后续监控功能需要外网访问以检测链接状态 |
| 磁盘空间 | >= 100 MB | 用于存放源码、依赖包及构建产物，实际占用约 80 MB |
| 操作系统 | Linux / macOS / Windows | 跨平台支持，但推荐使用 Unix-like 环境以获得最佳性能 |

## 文档导航

| 层面 | 目录位置 | 回答的问题 |
|-----|---------|-----------|
| 用户手册 | `docs/user-guide.md` | 如何使用分类标签、如何提交新链接、如何报告失效链接 |
| 维护者指南 | `docs/maintainer-guide.md` | 审核标准是什么、如何批量更新链接、如何处理冲突的提交请求 |
| API 参考 | `docs/api-reference.md` | 如何通过 HTTP 接口获取 JSON 格式的链接列表、如何过滤标签 |
| 部署手册 | `docs/deployment.md` | 如何将项目部署到 Vercel / Netlify / 自建 Nginx 服务器 |

## 资源列表

以下为 PaperLink Hub 当前收录的全部外链资源，按类别分组展示。所有链接均保留用户原始提交格式，未经任何协议补全或域名修改。

影视检索类

mjtt88.top
panzitv.beer
paopaomv.xyz

图床与媒体存储类

mjwang.pics
movieli.pics

## 项目结构

```
paperlink-hub/
├── .github/                         # GitHub 社区配置文件
│   └── ISSUE_TEMPLATE/              # 用户提交链接与反馈问题的模板
├── data/
│   ├── links.json                   # 主链接清单，包含所有 URL 及其标签、状态
│   ├── categories.json              # 分类定义文件，控制导航栏分组显示
│   └── allowlist.txt                # 域名白名单，用于构建时过滤非法输入
├── docs/                            # 完整文档目录，涵盖用户与开发者手册
│   ├── user-guide.md                # 面向普通用户的详细操作指南
│   ├── maintainer-guide.md          # 面向维护者的审核流程说明
│   ├── api-reference.md             # 对外提供的只读 API 文档
│   └── deployment.md                # 不同平台部署配置参考
├── scripts/
│   ├── build.js                     # 核心构建脚本，读取 data/ 生成静态页面
│   ├── monitor.js                   # 可用性监控脚本，每日定时检测链接状态
│   └── dedupe.js                    # 去重合并工具，定期清理冗余条目
├── static/
│   ├── css/                         # 样式文件，包含移动端与暗色主题适配
│   ├── js/                          # 前端交互脚本，处理过滤与排序逻辑
│   └── assets/                      # 图片与字体等静态资源
├── tests/
│   ├── link-validator.test.js       # 单元测试，验证链接格式与白名单规则
│   └── dedupe.test.js               # 去重算法的边界条件测试
├── .gitignore                       # Git 忽略规则，排除 node_modules/ 与 dist/
├── package.json                     # npm 项目配置，定义依赖与脚本命令
├── README.md                        # 项目首页文档（即当前文件）
└── LICENSE                          # MIT 许可证全文
```

## 贡献指南

我们欢迎社区以多种方式参与 PaperLink Hub 的建设，所有贡献均需遵守行为准则与贡献协议。

1. 提交新链接或反馈失效链接：请使用 GitHub Issues 中的标准模板，填写完整域名、来源说明及分类建议。提交前请确认链接内容不违反中国法律法规及 GitHub 服务条款。
2. 改进文档或修复笔误：可直接发起 Pull Request，修改 `docs/` 目录下的 Markdown 文件。请确保语法正确且无拼写错误，修改范围不超过 5 个文件时无需运行测试。
3. 完善监控脚本或构建流程：若您对 Node.js 或正则表达式有经验，欢迎优化 `scripts/monitor.js` 中的超时重试机制或 `scripts/dedupe.js` 的归一化算法。提交前请确保所有单元测试通过。
4. 翻译界面或国际化支持：我们目前仅提供中文版本，如果您希望添加英文或日文界面，请新增 `static/lang/` 目录下的 JSON 语言包，并同步修改构建脚本的读取逻辑。
5. 参与可用性测试：定期使用本项目提供的链接列表，在真实网络环境下测试访问速度与稳定性，并将结果反馈至 Discussion 板块。长期活跃的测试者将被列入致谢名单。

## 常见问题

**问：PaperLink Hub 是否提供视频播放或文件下载功能？**

答：不提供。本项目仅为 URL 索引服务，不存储、缓存或代理任何媒体文件。所有指向第三方站点的链接均需用户自行承担访问责任与安全风险。我们强烈建议用户安装广告拦截插件与反病毒软件后再访问外部链接。

**问：我发现某个收录链接无法访问，应该如何处理？**

答：请前往 GitHub Issues 选择“链接失效报告”模板，填写完整的域名、您的位置和网络环境（如运营商、是否使用代理）。维护团队将在 48 小时内进行人工复核，若确认失效则从主清单移除或标记为“暂停”。您也可以直接提交 Pull Request 修改 `data/links.json` 中的对应条目。

**问：为什么某些域名看起来像是个人站点或非知名服务？**

答：PaperLink Hub 秉持“去中心化”与“多样性”原则，并不以流量或知名度作为收录标准。凡经社区提交且通过基础安全审核（不含恶意软件、钓鱼页面、侵权内容）的链接，均有机会收录。我们相信长尾资源同样具有价值。

## 许可证

MIT License

Copyright (c) 2026 PaperLink Hub Contributors

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

> 外链数量: 5 | 生成时间: 2026-06-23 23:49:23
