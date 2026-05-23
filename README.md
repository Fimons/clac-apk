# 计算器APK构建指南

## 方案一：使用GitHub自动构建（推荐，最简单）

### 步骤：

1. **创建GitHub仓库**
   - 访问 https://github.com/new
   - 创建一个新仓库（如：calculator-app）
   - 上传以下文件：
     - calculator.html
     - manifest.json
     - icon-192.png
     - icon-512.png
     - .github/workflows/build-apk.yml（新创建的）

2. **触发构建**
   - 推送代码后，GitHub会自动触发构建
   - 或手动触发：点击仓库的 Actions → Build Android APK → Run workflow

3. **下载APK**
   - 构建完成后，点击 artifact 下载 calculator.apk

---

## 方案二：使用在线PWA转APK工具

如果不想用GitHub，可以直接在线转换：

1. 部署文件到任意静态网页托管（如Vercel、GitHub Pages）
2. 访问 https://appmaker.xyz/pwa-to-apk/
3. 输入你的网站地址
4. 下载生成的APK

---

## 方案三：本地使用VS2022构建

如果你熟悉VS2022，可以手动创建Android项目：

1. 用VS2022创建新的"移动应用(Xamarin)"项目
2. 将 calculator.html 放入 Assets 文件夹
3. 用 WebView 加载本地HTML文件
4. 直接在VS中编译打包APK

---

## 文件清单

请确保上传以下文件到GitHub：
- calculator.html   （主应用）
- manifest.json     （PWA配置）
- icon-192.png      （图标）
- icon-512.png      （图标）
- .github/workflows/build-apk.yml （构建脚本）

压缩包文件结构如下：
calculator-app/
├── calculator.html
├── manifest.json
├── icon-192.png
├── icon-512.png
└── .github/
    └── workflows/
        └── build-apk.yml
