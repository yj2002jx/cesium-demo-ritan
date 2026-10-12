# 日坛三维可视化项目 | Cesium WebGIS Demo
## 项目简介
本项目基于 Cesium.js 原生开发轻量化三维 WebGIS 可视化平台，以北京日坛公园为可视化对象，实现三维地球场景搭建、多源底图切换、矢量要素加载、要素属性查询、缓冲区空间分析等典型 GIS 前端功能。项目采用静态部署方式托管于 GitHub Pages，支持公网在线访问演示。
> 技术栈：
- 前端框架：原生 JavaScript
- 三维GIS引擎：Cesium.js
- 地图服务：天地图 WMTS 瓦片服务（矢量/影像）
- 地理数据：GeoJSON 矢量边界数据
- 部署方式：GitHub Pages 静态部署

## ✨ 功能清单
1. 三维地球场景初始化
  - 搭建标准 Cesium 三维球面场景，适配网页端自适应展示
  - 关闭默认不必要控件，界面简洁轻量化
2. 多底图图层切换功能
  - 接入天地图 WMTS 服务：矢量底图、卫星影像底图
  - 配置 OSM 开源底图作为跨环境兜底方案
  - 解决国内外网络适配问题，兼顾本地开发与线上演示稳定性
3. GeoJSON 矢量要素加载与拾取查询
  - 加载日坛公园边界矢量面数据
  - 支持鼠标点击拾取要素，弹窗展示名称、范围、属性信息
  - 实现三维场景要素交互查询能力
4. 缓冲区空间分析可视化
  - 基于球面坐标系生成 500m 圆形缓冲区
  - 半透明覆盖层可视化展示空间范围
  - 模拟 GIS 缓冲区分析业务场景
🌐 在线演示地址
https://yj2002jx.github.io/cesium-demo-ritan/
✅ 公网可直接访问，无需本地部署，支持完整功能演示

📷 项目截图
<img width="1891" height="966" alt="4e3849de9edfce59a284557548127505" src="https://github.com/user-attachments/assets/800eee49-0413-4c9a-b76b-df86e6fe5987" />
<img width="1905" height="905" alt="1c51ef64a3a82100025454b6c4627cc0" src="https://github.com/user-attachments/assets/04dfd685-53fd-48f9-aad2-089547610f9c" />
<img width="1891" height="906" alt="407b221abc034d4ca682fec9737e8239" src="https://github.com/user-attachments/assets/6867a0be-3688-44c1-9f7e-9820ecf344d1" />


🧩 项目难点与解决方案
1. 天地图域名白名单 403 蓝屏问题解决
  - 问题：天地图 Key 仅授权 GitHub Pages 线上域名，本地 localhost / 127.0.0.1 预览会瓦片加载失败、蓝屏报错
  - 解决：增加运行环境自动判断逻辑，线上环境正常加载天地图 WMTS 服务，本地开发环境自动降级为 OSM 底图，兼容双场景
2. 国内外网络适配优化
  - Cesium 默认必应底图国内访问缓慢，替换为稳定开源底图兜底
  - 区分 VPN/非VPN 网络场景，规避国内外地图服务冲突问题
3. 三维球面缓冲区适配
  - 基于 Cesium 球面坐标系生成缓冲区，避免平面坐标偏移问题，保证三维地理精度

📂 本地运行方式
1. Clone / 下载项目代码
2. 使用 VSCode 打开项目，安装 Live Server 插件
3. 右键 index.html → Open with Live Server 启动
4. 本地自动降级 OSM 底图，线上自动启用天地图完整功能

## 🚀 在线预览
https://yj2002jx.github.io/cesium-demo-ritan/


## 本地运行
直接用浏览器打开index.html即可。

📝 项目总结
本项目完整实现了 三维场景搭建、多源底图切换、矢量要素交互、空间缓冲区分析、公网静态部署 全套 WebGIS 前端开发流程。适配本地开发、线上演示双环境，解决了地图服务域名限制、网络适配、三维球面地理计算等典型工程问题，可作为 WebGIS / 三维GIS 前端求职完整作品集项目。
