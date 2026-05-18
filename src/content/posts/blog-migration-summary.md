---
title: 博客迁移总结 - 从 Hexo 到 Astro Firefly
published: 2026-05-18
description: 记录将博客从 Hexo Next 主题迁移到 Astro Firefly 主题的完整过程与心得
tags: [博客, Astro, Hexo, 迁移, 技术]
category: 技术分享
draft: false
pinned: true
---

## 博客迁移总结 - 从 Hexo 到 Astro Firefly

> 年少学历蜀山涧，老大飘零巴水畔。  
> 若君愿详今安在——南山林深云掩半。

<!--more-->

## 📋 迁移背景

我的博客最初基于 **Hexo** 框架和 **Next** 主题构建，运行在 GitHub Pages 上。随着技术栈的更新和对更好写作体验的追求，我决定将博客迁移到更现代的 **Astro** 框架，并采用 **Firefly** 主题模板。

### 为什么选择 Astro + Firefly？

- **Astro**：现代静态站点生成器，支持多种框架，构建速度快，SEO 友好
- **Firefly**：基于 Astro 和 Fuwari 开发的清新美观博客主题，功能丰富且高度可定制
- **更好的开发体验**：TypeScript 支持、热更新、组件化开发

## 🔄 迁移过程

### 第一阶段：项目初始化

1. 克隆 Firefly 模板仓库
2. 安装项目依赖（pnpm）
3. 确认开发服务器正常运行

### 第二阶段：历史文章迁移

将旧博客中的 **7 篇历史文章** 从 Hexo 格式转换为 Astro Markdown 格式：

| 原文件名 | 新文件名 | 分类 |
|---------|---------|------|
| git学习.md | git-learning.md | 技术工具 |
| 前缀和与差分.md | prefix-sum-and-difference.md | 算法 |
| 单调队列.md | monotonic-queue.md | 算法 |
| 数据结构.md | data-structures-review.md | 学习笔记 |
| 算法提高清单.md | algorithm-checklist.md | 算法 |
| Easy X 图形库学习心得.md | easyx-learning.md | 学习笔记 |
| markdown常用公式.md | markdown-formulas.md | 技术工具 |

**格式转换要点**：
- Hexo 的 Frontmatter 转换为 Astro 标准格式
- 保留所有 Markdown 内容和 LaTeX 数学公式
- 更新图片引用路径（外部链接保持不变）
- 添加 `description` 字段用于 SEO 优化

### 第三阶段：配置文件个性化

根据旧博客 `_config.yml` 中的个人信息，替换了以下配置文件：

#### siteConfig.ts
- 站点标题：`KinyouLee的个人博客`
- 副标题：`Enjoy my coding life`
- 站点 URL：`https://LeeKinyou.github.io`
- 描述：`a university student majoring in CS, CQUPT`
- 关键词：Agent开发、CS、CQUPT、后端开发、算法等

#### profileConfig.ts
- 名字：`Kinyou`
- 签名：`a university student majoring in CS, CQUPT`
- GitHub 链接：`https://github.com/LeeKinyou`
- 邮箱：`1412901165@qq.com`

#### navBarConfig.ts
- 简化导航菜单，移除无关链接
- 保留主页、归档、友链、关于等核心页面

#### 其他配置
- 友链配置：仅保留 Astro 官方链接
- 公告内容：更新为个性化欢迎语
- 赞助功能：关闭

### 第四阶段：关于我页面融合

将旧博客的个性化内容融合到新博客：

- **趣味档案**：保留幽默风格（华为、战狼、原神、吴京等）
- **打油诗**：保留原创打油诗
- **技术介绍**：更新为 Astro + Firefly 技术栈
- **联系方式**：使用真实邮箱地址

### 第五阶段：清理冗余文件

- 删除所有 Firefly 示例文章和演示图片
- 删除多语言 README 和 CONTRIBUTING.md
- 简化项目结构，保留核心功能

## 📊 迁移成果

### 文章统计
- 迁移历史文章：**7 篇**
- 分类：**4 个**（算法、学习笔记、技术工具、技术分享）
- 标签：**10+ 个**（Git、前缀和、差分、单调队列、数据结构、EasyX、Markdown、LaTeX 等）

### 功能完整性
- ✅ 文章发布与展示
- ✅ 分类与标签管理
- ✅ 文章归档
- ✅ 全文搜索（Pagefind）
- ✅ 亮暗色模式切换
- ✅ 响应式设计
- ✅ 侧边栏组件（分类、标签、日历、目录）

### 技术栈
- **框架**：Astro 6.x
- **主题**：Firefly（基于 Fuwari）
- **样式**：Tailwind CSS
- **部署**：GitHub Pages
- **包管理**：pnpm

## 🎯 后续计划

1. **补充头像和壁纸**：添加个人头像和自定义背景图片
2. **评论系统**：配置 Giscus 或 Waline 评论系统
3. **统计分析**：接入 Umami 或 51la 统计
4. **持续更新**：定期发布新的技术文章和学习笔记
5. **SEO 优化**：完善 OpenGraph 和站点元数据

## 💡 迁移心得

1. **Astro 的优势**：构建速度快、TypeScript 原生支持、组件化开发体验好
2. **Firefly 主题**：功能丰富、配置灵活、界面美观
3. **数据迁移**：Markdown 格式通用性强，迁移成本低
4. **个性化配置**：通过配置文件即可实现大部分定制需求

---

*感谢 Hexo 和 Next 主题的陪伴，也感谢 Astro 和 Firefly 带来的全新体验。博客迁移不仅是技术的升级，更是记录成长的新起点。*

> 代码会老去，热爱不会。愿每一行代码，都不负韶华。
