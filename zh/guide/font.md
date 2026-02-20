# 字体

Firefly 支持自定义字体配置，可以使用 CDN 字体或本地字体文件。

## 配置文件

`src/config/fontConfig.ts`

## 基础配置

| 属性 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `enable` | `boolean` | `false` | 是否启用自定义字体 |
| `preload` | `boolean` | `true` | 是否预加载字体文件 |
| `selected` | `string \| string[]` | `["misans-regular"]` | 当前选择的字体 ID，支持多个字体组合 |
| `fallback` | `string[]` | `["system-ui", ...]` | 全局字体回退列表 |

```ts
export const fontConfig = {
  enable: false,
  preload: true,
  selected: ["misans-regular"],
  fallback: [
    "system-ui",
    "-apple-system",
    "BlinkMacSystemFont",
    "Segoe UI",
    "Roboto",
    "sans-serif",
  ],
};
```

## 字体项配置

每个字体项支持以下属性：

| 属性 | 类型 | 必填 | 说明 |
|------|------|------|------|
| `id` | `string` | 是 | 字体唯一标识符 |
| `name` | `string` | 是 | 字体显示名称 |
| `src` | `string` | 是 | 字体文件路径或 URL |
| `family` | `string` | 是 | CSS `font-family` 名称 |
| `weight` | `string \| number` | 否 | 字体粗细 |
| `style` | `string` | 否 | 字体样式：`"normal"`、`"italic"`、`"oblique"` |
| `display` | `string` | 否 | `font-display` 属性：`"auto"`、`"block"`、`"swap"`、`"fallback"`、`"optional"` |

## 内置字体

Firefly 预置了以下字体配置：

| ID | 名称 | 来源 |
|----|------|------|
| `system` | 系统字体 | 系统内置 |
| `zen-maru-gothic` | Zen Maru Gothic | Google Fonts |
| `inter` | Inter | Google Fonts |
| `misans-normal` | MiSans Normal | unpkg CDN |
| `misans-regular` | MiSans Regular | unpkg CDN |
| `misans-semibold` | MiSans Semibold | unpkg CDN |

## 添加自定义字体

```ts
fonts: {
  "my-font": {
    id: "my-font",
    name: "My Custom Font",
    src: "https://fonts.googleapis.com/css2?family=My+Font&display=swap",
    family: "My Font",
    display: "swap",
  },
},
```

然后将其添加到 `selected` 中：

```ts
selected: ["my-font"],
```

::: warning
- 推荐使用 CDN 字体，天然支持按需加载，性能较好
- 本地字体文件需自行进行字体子集化处理，否则会导致页面加载缓慢
- 字体子集化会导致动态内容（如评论、Bangumi 等）无法正确显示字体
:::
