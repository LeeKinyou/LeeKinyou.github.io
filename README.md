# LeeKinyou's Blog

> 记录技术与成长 - 后端开发 | 算法爱好者 | 持续学习

## 关于本站

这是一个基于 **Astro** 框架和 **Firefly** 主题的个人博客网站，主要用于记录学习历程、技术分享和算法总结。

## 博客内容

- **后端开发**：Go、Python 等语言的项目实践
- **算法与数据结构**：LeetCode 刷题笔记、算法学习总结
- **技术工具**：Git、Linux 等开发工具的使用心得
- **学习笔记**：课程复习总结、新技术探索

## 本地运行

```bash
# 安装依赖
pnpm install

# 启动开发服务器
pnpm dev

# 构建网站
pnpm build
```

## 提交规范

本项目使用 **Biome** 进行代码格式化和检查。每次提交代码前，**必须**先格式化代码，否则 Biome 会报错。

### 格式化命令

```bash
# 格式化 src 目录下的所有文件
pnpm format

# 检查并自动修复代码问题
pnpm lint
```

### 提交流程

1. 编写或修改文章/代码
2. 运行 `pnpm format` 格式化代码
3. 运行 `pnpm lint` 检查并修复问题
4. 提交代码

> **注意**：如果忘记格式化就直接提交，CI 检查会因 Biome 报错而失败。

## 技术栈

- [Astro](https://astro.build) - 静态站点生成器
- [Tailwind CSS](https://tailwindcss.com) - CSS 框架
- [Firefly](https://github.com/CuteLeaf/Firefly) - 博客主题

## 许可协议

本项目基于 MIT 开源协议。
