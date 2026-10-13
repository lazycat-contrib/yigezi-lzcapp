# yigezi-lzcapp

[一个字的一生](https://github.com/Ivan666jjj/yigezi) 的懒猫微服打包：**只发喵喵商店**。

- **形态**：纯静态单页应用，**没有容器镜像**（`contentdir: ./dist` + `upstreams.backend: file:///lzcapp/pkg/content/`）。
- **版本来源**：`version_source.type: git`（上游仓库无 tag / release，版本由本仓库 `package.yml` 与 tag 决定）。
- **内容**：`dist/` 里是从上游原样同步的四个文件——`index.html`（含内联数据与样式）、`seal.woff2`（小篆，8.7 MB）、`orac.woff2`（甲骨文）、`stats.js`。字体是 `index.html` 里 `url(seal.woff2)` 的相对引用，必须与页面同目录一起打包，否则字形不显示。
- **名称**：中文「一个字的一生」；英文名 **The Life of a Chinese Character**（`package.yml` 的 `locales.en`，`name` 与 `description` 都翻成英文）。
- **图标**：`icon.png`（512×512，由用户提供的 `font.png` 放大）。
- **路由**：`/` → `file:///lzcapp/pkg/content/`，`public_path: [/]`。
- **上游外部依赖**：页面头部保留了一个不蒜子访客统计 `<script src="https://busuanzi.ibruce.info/...">`（第三方、可选；离线时该脚本加载失败不影响页面功能）。

## 授权

- **代码** MIT（见 `LICENSE`）。
- **收录数据**：小篆（OFL-1.1 / OGDL-Taiwan-1.0）、甲骨文（OFL-1.1）、《说文》释义（Apache-2.0）、OpenCC（Apache-2.0）、中古音（CC BY 4.0）、上古音（CC BY 4.0）。完整声明见 `THIRD_PARTY_NOTICES.md`，许可原文在 `licenses/`。

## 商店状态

- **喵喵商店**：`cloud.lazycat.app.yigezi` 由 Action 发布（`stores.private`）。
- **官方商店**：未启用。
