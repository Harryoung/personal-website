# 个人网站部署指南

## 项目状态
✅ 项目已完成本地搭建和内容填充
✅ 构建测试通过
✅ 开发服务器运行中（http://localhost:4321）

## 部署步骤

### 方案一：使用GitHub Pages（推荐）

#### 1. 创建GitHub仓库
1. 访问 https://github.com/new
2. 仓库名称：`personal-website`（或其他你喜欢的名称）
3. 设置为**Public**仓库（GitHub Pages免费版需要公开）
4. **不要**勾选"Add a README file"
5. 点击"Create repository"

#### 2. 推送代码到GitHub

在项目目录执行：
```bash
cd /workspace/personal-website
git branch -M main
git remote add origin https://github.com/Harryoung/personal-website.git
git add .
git commit -m "Initial commit: Personal website with Codefolio theme"
git push -u origin main
```

#### 3. 配置GitHub Pages

**方法A：通过GitHub Actions自动部署（推荐）**

1. 在GitHub仓库页面，点击"Settings"
2. 左侧菜单找到"Pages"
3. "Build and deployment"下：
   - Source: 选择 **GitHub Actions**
4. GitHub会自动推荐Astro的workflow配置，点击"Configure"
5. 提交默认的workflow文件

**方法B：手动部署（备选）**

每次更新后手动执行：
```bash
npm run build
# 将dist目录内容推送到gh-pages分支
```

#### 4. 访问网站

部署完成后（通常需要1-2分钟），访问：
- 如果仓库是 `harryoung/harryoung.github.io`：https://harryoung.github.io
- 如果是其他仓库名：https://harryoung.github.io/仓库名

### 方案二：绑定独立域名（可选）

如果你购买了域名（如youjiangbin.com）：

1. 在 `public` 目录创建 `CNAME` 文件，内容为：
   ```
   youjiangbin.com
   ```

2. 在域名提供商（如阿里云、Cloudflare）添加DNS记录：
   - 类型：CNAME
   - 主机记录：@ 或 www
   - 记录值：harryoung.github.io

3. 在GitHub仓库的Settings > Pages中配置自定义域名

## 后续维护

### 更新内容
1. 修改 `src/pages/` 下的文件
2. 本地预览：`npm run dev`
3. 提交更新：
   ```bash
   git add .
   git commit -m "Update: 描述你的更改"
   git push
   ```
4. GitHub Actions会自动构建和部署

### 添加新项目
编辑对应的 `.astro` 文件，在 `projects` 数组中添加新项目即可。

### 个性化定制建议
- 替换头像：`public/assets/sam.jpg`
- 修改配色：编辑 `public/assets/styles.css`
- 添加联系方式：在首页和Sidebar中更新邮箱、社交媒体链接

## 本地开发命令

```bash
cd /workspace/personal-website

# 安装依赖（如果需要）
npm install

# 启动开发服务器
npm run dev

# 构建生产版本
npm run build

# 预览构建后的网站
npm run preview
```

## 注意事项

1. **隐私信息**：网站已脱敏，不要添加家庭住址、家人姓名等私密信息
2. **efka项目**：确保GitHub仓库链接正确，README完善
3. **工作内容**：星辰·偕作项目描述已脱敏，不涉及商业机密

## 技术栈

- **框架**: Astro 5.17
- **主题**: Codefolio（MIT开源许可）
- **部署**: GitHub Pages
- **托管**: 免费（GitHub公开仓库）

---

**AI分身备注**：所有准备工作已完成，按上述步骤操作即可上线！🚀
