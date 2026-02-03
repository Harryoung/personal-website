# SEO和Google Analytics配置指南

> 个人网站SEO优化和访问统计配置

---

## 已完成配置

### 1. Google Analytics 4 (GA4)

**组件位置**: `src/components/GoogleAnalytics.astro`

**配置方式**:
```bash
# 设置环境变量
export PUBLIC_GA_ID="G-XXXXXXXXXX"
```

**获取Measurement ID**:
1. 访问 [Google Analytics](https://analytics.google.com/)
2. 创建GA4属性
3. 复制Measurement ID（格式：`G-XXXXXXXXXX`）
4. 在GitHub中设置为Repository Secret：`PUBLIC_GA_ID`

**GitHub Actions配置**:
```yaml
# 在.github/workflows/deploy.yml中添加
env:
  PUBLIC_GA_ID: ${{ secrets.PUBLIC_GA_ID }}
```

### 2. Sitemap自动生成

**已安装**: `@astrojs/sitemap`

**访问地址**: `https://harryoung.github.io/personal-website/sitemap-index.xml`

**配置**:
- 更新频率：每周
- 优先级：0.7
- 自动包含所有页面

### 3. SEO优化

**已添加**:
- ✅ Open Graph标签（社交分享）
- ✅ Twitter Card标签
- ✅ Favicon配置
- ✅ 响应式viewport
- ✅ 语义化HTML

---

## 搜索引擎提交

### Google Search Console

1. 访问 [Google Search Console](https://search.google.com/search-console)
2. 添加属性：选择「网址前缀」，输入 `https://harryoung.github.io/personal-website/`
3. 验证所有权：通过GitHub Pages验证或HTML文件上传
4. 提交Sitemap：在左侧菜单选择「站点地图」，提交 `sitemap-index.xml`

### Bing Webmaster Tools

1. 访问 [Bing Webmaster Tools](https://www.bing.com/webmasters)
2. 添加网站
3. 验证所有权
4. 提交Sitemap

### 百度搜索资源平台

1. 访问 [百度搜索资源平台](https://ziyuan.baidu.com/)
2. 添加网站
3. 验证网站
4. 链接提交：支持API推送、Sitemap、手动提交

---

## 环境变量配置

### GitHub Secrets设置

在GitHub仓库设置中添加以下Secrets：

| Secret名称 | 说明 | 示例值 |
|-----------|------|--------|
| `PUBLIC_GA_ID` | Google Analytics Measurement ID | `G-XXXXXXXXXX` |

### 本地开发

创建 `.env` 文件：
```bash
# .env
PUBLIC_GA_ID=G-XXXXXXXXXX
```

**注意**: `.env` 文件已加入 `.gitignore`，不会提交到仓库

---

## 验证配置

### 检查GA是否加载

1. 打开网站
2. 打开浏览器开发者工具（F12）
3. 切换到Network标签
4. 刷新页面
5. 搜索 `google-analytics.com` 或 `gtag`

### 检查Sitemap

访问：`https://harryoung.github.io/personal-website/sitemap-index.xml`

应该看到XML格式的站点地图

---

## 下一步

1. **主身需要做的**：
   - [ ] 创建Google Analytics账号并获取Measurement ID
   - [ ] 在GitHub仓库设置中添加`PUBLIC_GA_ID` Secret
   - [ ] 提交网站到Google Search Console
   - [ ] 提交网站到Bing Webmaster Tools（可选）

2. **自动完成**：
   - ✅ GA4代码已集成（仅生产环境加载）
   - ✅ Sitemap已自动生成
   - ✅ SEO标签已优化

---

## 参考资源

- [Google Analytics 4 文档](https://support.google.com/analytics/answer/9304153)
- [Google Search Console](https://search.google.com/search-console)
- [Astro SEO指南](https://docs.astro.build/en/guides/seo/)
- [Schema.org结构化数据](https://schema.org/)

---

**创建时间**: 2026-02-03
**状态**: 配置完成，等待主身添加GA ID
