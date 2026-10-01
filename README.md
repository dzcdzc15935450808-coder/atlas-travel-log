# ATLAS — 个人旅行图志

一个**纯单文件**的旅行足迹记录应用：用 3D 地球展示你的航班与火车行程，配合统计图表、行程管理与明暗主题。所有代码都在一个 `index.html` 里，双击即用，无需安装、无需构建、无需服务端。

![技术栈](https://img.shields.io/badge/依赖-Three.js%20·%20globe.gl%20·%20Chart.js-blue)

## ✨ 特性

- 🌍 **3D 地球** — 基于 globe.gl 的夜光地球，航线弧线与铁路 polyline 可视化，可拖拽缩放
- ✈️ 🚄 **航班 + 火车统一记录** — 输入航班号自动联网查询（adsbdb.com）；输入车次自动匹配内置时刻库
- 📊 **统计面板** — 月度出行柱状图、飞行/铁路占比环形图（按次数或距离切换）、年度筛选
- 🗂️ **旅途分组** — 将多段行程归入一次「旅途」（如「西班牙 14 天」）
- 💾 **数据自主** — 全部数据仅存于浏览器 localStorage；支持 JSON / CSV 导入导出
- 🌗 **明暗主题** — 跟随系统，也可手动切换
- 📱 **响应式** — 桌面与移动端均可使用

## 🚀 快速开始

```bash
git clone https://github.com/dzcdzc15935450808-coder/atlas-travel-log.git
```

然后直接用浏览器打开 `index.html` 即可。

> 也可以只下载 [index.html](./index.html) 这一个文件。首次打开为空数据，通过「添加行程」录入你的第一段行程。

## 🔒 数据与隐私

- **所有行程数据只保存在你自己的浏览器 localStorage 中**，不上传任何服务器
- 添加航班时，仅向 [adsbdb.com](https://www.adsbdb.com)（免费、无密钥、无追踪）发送航班号以查询起降机场
- 设置面板中可随时**导出 JSON/CSV 备份**或**清空全部数据**

## 🛠️ 自定义

所有配置都直接写在 `index.html` 源码内，搜索对应常量即可：

| 常量 | 用途 |
|---|---|
| `USER_TRAINS` | 常坐车次快捷导入表，首次启动自动录入 |
| `ROUTE_OVERRIDES` | 航班号 → 正确起降的手动修正表（adsbdb 查错时用） |
| `PLACES` / `FLIGHT_DB` / `TRAIN_DB` / `RAIL_GEO` | 内置机场/车站词典、航班/车次时刻库、铁路轨迹 |

## 📦 使用的开源项目

ATLAS 自身代码以 MIT 协议开源，运行时通过 CDN 加载以下优秀的开源库，感谢这些项目的作者：

| 项目 | 版本 | 许可证 | 用途 |
|---|---|---|---|
| [Three.js](https://github.com/mrdoob/three.js) | r160.1 | [MIT](https://github.com/mrdoob/three.js/blob/dev/LICENSE) | WebGL 3D 渲染基础 |
| [globe.gl](https://github.com/vasturiano/globe.gl) | 2.34.4 | [MIT](https://github.com/vasturiano/globe.gl/blob/master/LICENSE) | 3D 地球与航线/轨迹图层 |
| [three-globe](https://github.com/vasturiano/three-globe)（地球贴图素材） | — | [MIT](https://github.com/vasturiano/three-globe/blob/master/LICENSE) | 夜光地球 / 地形 / 星空纹理 |
| [Chart.js](https://github.com/chartjs/Chart.js) | 4.4.1 | [MIT](https://github.com/chartjs/Chart.js/blob/master/LICENSE.md) | 统计图表（柱状图 / 环形图） |
| [Inter](https://github.com/rsms/inter) | — | [SIL OFL 1.1](https://github.com/rsms/inter/blob/master/LICENSE.txt) | 界面字体（Google Fonts） |

外部服务：

- [adsbdb.com](https://www.adsbdb.com) — 免费开放航班路线数据库（仅查询航班号，无密钥）

## 🤝 贡献

欢迎 Issue 与 PR！由于是单文件应用，直接修改 `index.html` 后提交即可。提交前请确保：

1. 不要在代码中包含任何个人行程数据
2. 保持单文件形态（不引入构建步骤）
3. 新增第三方依赖时更新上方「使用的开源项目」表格

## 📄 许可证

[MIT](./LICENSE) © ATLAS contributors
