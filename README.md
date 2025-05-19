# 520LovePwaApp
# 520 Love PWA App 部署与上线指南

## 1. GitHub Pages（静态托管）
1. 在仓库页面点击“Settings” → “Pages”。
2. 在“Source”一栏选择 `main` 分支，根目录 (`/root`)。
3. 保存后几分钟即可获得 `https://<用户名>.github.io/520LovePwaApp/` 地址。

## 2. Netlify / Vercel（自动化部署）
- **Netlify**：登录后选择“New site from Git”，关联本仓库，构建命令留空或 `npm run build`，发布目录 `.`。
- **Vercel**：登录后“Import Project”，选择 GitHub 仓库，保持默认即可一键部署。

## 3. 本地打包成原生应用（可选）
1. 安装 Capacitor：
   ```bash
   npm install @capacitor/core @capacitor/cli --save
   ```
2. 初始化项目：
   ```bash
   npx cap init 520LovePwaApp com.example.520love "520的心"
   ```
3. 构建 Web 资源：
   ```bash
   npm run build # 或手动复制所有文件到 www/ 目录
   ```
4. 添加平台：
   ```bash
   npx cap add android
   npx cap add ios
   ```
5. 打开平台工程：
   ```bash
   npx cap open android # 在 Android Studio 中
   npx cap open ios     # 在 Xcode 中
   ```
6. 真机调试 & 打包：使用 Android Studio / Xcode 的打包流程生成 APK/IPA。

## 4. 测试与调试
- 在不同手机浏览器中访问部署地址，测试“添加到主屏幕”功能。
- 检查离线模式：断网后刷新页面，应能正常加载缓存资源。
- 调整图标、启动画面（可在 `manifest.json` 中配置）。

> **提示**：如需 HTTPS 协议，GitHub Pages、Netlify 与 Vercel 默认支持 HTTPS，无需额外配置。
