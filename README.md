```markdown
# 3D-Love: Three.js 动态爱心网页（含背景音乐自定义）

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Technology Stack](https://img.shields.io/badge/Stack-JavaScript%20%7C%20Three.js%20%7C%20Canvas-blue.svg)](https://threejs.org/)

## 项目概述
3D-Love 是基于 Three.js 与 Canvas 技术构建的动态网页项目，核心呈现交互式 3D 爱心动画效果。项目在开源代码基础上优化，修复兼容性问题与性能瓶颈，新增背景音乐自定义功能，提供沉浸式体验，适用于个人展示、节日祝福等场景。

## 核心特性
- **3D 动态效果**：基于 Three.js 实现爱心形变与交互响应，支持鼠标控制视角（依赖 TrackballControls）。
- **背景音乐支持**：内置循环播放，支持本地音频与在线直链两种自定义方式。
- **轻量无依赖**：无需构建工具，浏览器直接打开运行，兼容主流现代浏览器。
- **代码优化**：修复原代码潜在 Bug，优化资源加载，提升启动速度。

## 快速上手

### 环境要求
- 浏览器：Chrome ≥ 70、Firefox ≥ 65、Edge ≥ 79、Safari ≥ 12（支持 HTML5 Canvas 与 Audio API）。
- 无需额外依赖，无需 Node.js 环境。

### 安装与运行
1. 克隆仓库
   ```bash
   git clone https://github.com/Luv9-cn/3D-Love.git
   ```
2. 进入项目根目录，用浏览器打开 `index.html` 文件启动项目。

## 背景音乐自定义指南

### 方式一：本地 MP3 音频（推荐离线使用）
1. 准备 MP3 格式音频（比特率 128-320kbps 为佳）。
2. 放入项目目录（建议新建 `music` 文件夹，如 `music/custom-song.mp3`）。
3. 编辑 `index.html`，修改 `audio` 标签配置：
   ```html
   <audio id="backgroundMusic" loop preload="auto">
     <source src="替换为本地音频路径" type="audio/mpeg">
   </audio>
   ```
4. 保存后刷新浏览器生效。

### 方式二：网易云音乐直链（推荐在线使用）
1. 打开网易云音乐网页版，找到目标歌曲，点击详情页「生成外链播放器」。
2. 提取音频链接并在浏览器打开。
3. 按 `Ctrl+Shift+I` 打开开发者工具，进入「网络」→「媒体」面板。
4. 刷新音频页面，复制目标请求的「请求 URL」（音频直链）。
5. 替换 `index.html` 中 `<source>` 标签的 `src` 属性，保存刷新即可。

## 项目结构
```
3D-Love/
├── index.html          # 主页面（含音频配置、DOM 结构）
├── favicon.ico         # 网页图标
└── js/                 # 核心依赖脚本
    ├── three.min.js       # Three.js 核心库
    ├── MeshSurfaceSampler.js  # 曲面采样工具
    ├── TrackballControls.js   # 鼠标控制交互
    ├── simplex-noise.js       # 噪声生成库
    ├── OBJLoader.js           # 3D 模型加载器
    ├── gsap.min.js            # 动画补间库
    └── main.js                # 3D 效果核心逻辑
```

## 配置与自定义扩展
### 音频参数调整
- 关闭循环：移除 `audio` 标签的 `loop` 属性。
- 取消自动加载：将 `preload="auto"` 改为 `preload="none"`。
- 音量控制：添加按钮，通过 `document.getElementById("backgroundMusic").volume` 控制。

### 3D 效果调整
- 修改颜色：编辑 `main.js` 中 `material.color` 配置。
- 调整速度：修改 `gsap` 动画的 `duration` 参数。

## 常见问题（FAQ）
1. **音频无法播放？**
   - 检查路径是否正确（相对路径基于 `index.html`）。
   - 确认格式为 MP3（其他格式需修改 `type` 属性）。
   - 浏览器可能限制自动播放，需手动点击页面触发。

2. **动态效果不显示？**
   - 确认浏览器支持 WebGL（老旧浏览器需升级）。
   - 检查 `js` 文件夹依赖文件是否完整。

3. **网易云直链失效？**
   - 版权限制可能导致直链过期，需重新获取。
   - 建议使用无版权限制歌曲或本地音频。

## 许可证
采用 MIT 许可证，详情见 [LICENSE](LICENSE)。允许个人学习、非商业使用，商业使用需联系作者授权。

## 贡献指南
欢迎提交 Issue 反馈 Bug 或需求，通过 Pull Request 参与优化。提交前确保代码规范，无破坏性修改。

## 联系方式
项目地址：[https://github.com/Luv9-cn/3D-Love](https://github.com/Luv9-cn/3D-Love)
原教程：[Three.js动态网页优化:背景音乐自定义教程](https://www.luv9.cn/archives/t5jgvsVX)
```

以上内容已完全包裹在代码框中，可直接复制保存为 `README.md` 文件使用。如果需要进一步调整格式或内容细节，请随时告知。
