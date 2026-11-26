# PyCharm 前端实时编辑环境

## 启动

在 PyCharm 打开项目根目录，在底部 Terminal 执行：

```bash
pnpm install
pnpm dev
```

然后打开 http://localhost:4321/。Astro 开发服务器支持热更新，保存 `.astro`、`.css` 或 `.ts` 文件后浏览器会自动刷新。

也可以在右上角运行配置中选择 **Astro Dev Server**，点击运行按钮启动。该配置已保存在 `.idea/runConfigurations/Astro_Dev.xml`。

## 通过浏览器定位源码

1. 在浏览器打开开发者工具（F12）。
2. 点击左上角的元素选择器，再点击页面上的元素。
3. 查看元素的 `class`、文本或 `data-*` 属性。
4. 在 PyCharm 使用 `Ctrl+Shift+F` 全局搜索这些关键词。
5. 修改对应的 `.astro` 或 `.css` 文件，保存后查看实时效果。

浏览器开发者工具中的 CSS 修改只是临时预览，确认效果后需要复制到源码。

## 常用源码位置

| 页面区域 | 文件 |
| --- | --- |
| 全局布局 | `src/theme/Layout.astro` |
| 顶部导航 | `src/theme/components/Header.astro` |
| 文章卡片 | `src/theme/components/PostCard.astro` |
| 侧边栏 | `src/theme/components/Aside.astro` |
| 右侧按钮 | `src/theme/components/Rightside.astro` |
| 页脚 | `src/theme/components/Footer.astro` |
| 全局颜色、字体 | `src/theme/styles/global.css` |
| 文章正文样式 | `src/theme/styles/content.css` |
| 网站菜单和基本信息 | `src/config.ts` |

## 修改完成后的检查

```bash
pnpm run check
pnpm run build
```

构建成功后提交部署：

```bash
git add src .idea/runConfigurations/Astro_Dev.xml docs/pycharm-frontend-workflow.md
git commit -m "chore: add PyCharm Astro development workflow"
git push origin main
```
