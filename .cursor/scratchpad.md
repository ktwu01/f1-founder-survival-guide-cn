# Project Scratchpad

## Background and Motivation

用户希望创建一个面向中文 F1 创业者的“进攻 + 退路”资源仓库，先搭建非常简单的中文骨架，后续再补充复杂上下文与深度规划。

## Key Challenges and Analysis

- 需要保持内容简单可扩展，避免一开始过度设计。
- 需要明确“信息整理”定位，避免被误解为法律建议。
- 需要保留英文高质量来源，方便交叉验证。

## High-level Task Breakdown

- [x] 创建仓库 `f1-founder-survival-guide-cn`
  - Success Criteria: 目录创建并完成 `git init`
- [x] 创建最简基础文件
  - Success Criteria: `README.md`、`CONTRIBUTING.md`、`DISCLAIMER.md` 已创建
- [x] 创建分类目录与导航文件
  - Success Criteria: `resources` 下 4 个目录均有 `README.md`
- [ ] 等待用户补充上下文，进入复杂计划阶段
  - Success Criteria: 用户提供更多目标与边界后再细化任务

## Project Status Board

- [x] Milestone 1: 仓库与最简中文骨架完成
- [ ] Milestone 2: 收集并分类第一批可验证来源
- [ ] Milestone 3: 增加模板与实操清单

## Current Status / Progress Tracking

- 当前状态：已完成超简仓库骨架，已可开始增量填充内容。
- 下一步：等待用户提供额外上下文后，Planner 输出复杂版本路线图。
- 执行进展（2026-03-07）：已新增 `docs/` Docsify 模板（`index.html`、`_sidebar.md`、文档页面与 resources 子页），并将根目录 `README.md`、`TODO.md` 改为 GitHub 友好可点击结构。
- 校验目标：确保 GitHub 与 Docsify 两套入口都可点击跳转，降低首次阅读门槛。
- 执行进展（2026-03-07）：按用户要求在每个文档页末尾新增“风险提示 + 完整免责声明链接”，覆盖根目录文档、`resources/*/README.md`、`docs/*.md` 与 `docs/resources/*.md`。
- 执行进展（2026-03-07）：按用户要求新增中文文档 `docs/doc-standard-cn.md`（模板、来源分级、发布前自检），并接入 Docsify 顶部导航（`_navbar.md`）与侧边栏（`_sidebar.md`）。
- 执行进展（2026-03-08）：修复 GitHub Pages 下 Docsify 导航加载异常：移除 `docs/index.html` 中 `alias` 重写、将 `docs/_navbar.md` 与 `docs/_sidebar.md` 首页链接从 `/` 改为 `#/`，并新增 `docs/.nojekyll` 以确保 `_navbar.md`/`_sidebar.md` 在 Pages 可被访问。
- 执行进展（2026-03-08）：按用户指定参考 `US-Financial-Survival-Guide` 的可用格式，改为“仅侧边栏导航”模式：在 `docs/index.html` 移除 `loadNavbar`/`mergeNavbar`，并设置 `repo` 为仓库地址与 `homepage: "README.md"`，用于恢复右上角 GitHub 图标与首页路由稳定性。
- 执行进展（2026-03-08）：按用户要求“完全对齐参考仓库格式”，进一步同步 `docs/index.html` 为参考仓库同款配置结构（`autoHeader/subMaxLevel/maxLevel/notFoundPage/search object`、`docsify.min.js` 与插件脚本写法）；`docs/_sidebar.md` 改为同款分组/缩进风格；新增 `docs/404.md`；删除 `docs/_navbar.md`，彻底采用与参考仓库一致的“无 navbar，仅 sidebar”模式。

## Executor's Feedback or Assistance Requests

- 请用户补充：目标读者画像（硕士/博士/OPT 阶段）、最优先的痛点（签证、公司、失败退出、融资之一），以便下一版计划更精准。
- 已完成本轮结构化文档搭建，请用户手动确认两项：
  1) GitHub 首页链接体验是否符合预期；
  2) `npx docsify-cli serve docs` 后侧边栏与页面跳转是否正常。
- 已补充“每页末尾免责声明链接”需求，请用户抽样点击以下路径验证：
  - 根目录：`README.md`、`TODO.md`、`CONTRIBUTING.md`
  - Docsify：`docs/README.md`、`docs/project-todo.md`、`docs/resources/*.md`
- 外部参考仓库学习进展（2026-03-07）：
  - 已本地克隆并阅读 `charlax/entrepreneurship-resources` 与 `jugaldb/resources_abroad`；
  - 下一步建议：先引入“标准条目模板 + 来源可信度分级 + 更新时间戳”，再扩充条目数量。
- 执行进展（2026-03-07）：
  - 注入幽默风格：在 README 与 4 个核心模块中加入“灵魂拷问”与“真实反面教材”。
  - 修复 Docsify：解决导航栏消失问题，增加上一页/下一页翻页功能。
  - 新增模块：`05 融资指南`（Non-dilutive Capital）与 `06 招人指南`（Intern/Co-founder）。
  - 代码提交：已完成所有变更的 commit 与 push。
- 本轮请用户手动验证（2026-03-08）：
  1) GitHub Pages 源设置为 `main` + `/docs`；
  2) 页面刷新后侧边栏与右上角 GitHub 图标是否出现；
  3) 手动访问一个不存在路径（如 `/#/not-exist`）是否显示 `404.md` 内容；
  4) 侧边栏首页链接（当前按参考仓库设置为 `/`）在 GitHub Pages 项目路径下是否仍可回到 Docs 首页。

## Lessons

- 先用最小可用结构启动，后续按证据和需求迭代。
- 所有关键结论都应附可验证来源链接。
- 参考仓库可复用的是“信息架构与模板化写法”，不是整段内容搬运。
- Docsify 在 GitHub Project Pages 下应优先使用 `#/` 路由首页链接，避免 `/` 指向站点根导致导航异常。
- 如果 Docsify 使用 `_navbar.md` / `_sidebar.md`，GitHub Pages 需放置 `.nojekyll` 以避免下划线文件被过滤。
- 当用户明确要求“完全对齐参考仓库格式”时，执行端应优先保持配置形态一致，再由用户验证其在当前仓库路径下的行为差异。
