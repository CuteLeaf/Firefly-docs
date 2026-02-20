# Live2D / Spine 模型

Firefly 支持在页面上显示 Live2D 或 Spine 看板娘模型，两者可以二选一使用。

## 配置文件

`src/config/pioConfig.ts`

## Spine 模型配置

### 基础配置

| 属性 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `enable` | `boolean` | `false` | 是否启用 Spine 看板娘 |

### 模型配置

| 属性 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `model.path` | `string` | - | Spine 模型文件路径（.json） |
| `model.scale` | `number` | `1.0` | 模型缩放比例 |
| `model.x` | `number` | `0` | X 轴偏移 |
| `model.y` | `number` | `0` | Y 轴偏移 |

### 位置配置

| 属性 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `position.corner` | `string` | `"bottom-left"` | 显示位置：`"bottom-left"` `"bottom-right"` `"top-left"` `"top-right"` |
| `position.offsetX` | `number` | `0` | 水平偏移量 |
| `position.offsetY` | `number` | `0` | 垂直偏移量 |

### 尺寸配置

| 属性 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `size.width` | `number` | `135` | 容器宽度 |
| `size.height` | `number` | `165` | 容器高度 |

### 交互配置

| 属性 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `interactive.enabled` | `boolean` | `true` | 是否启用交互功能 |
| `interactive.clickAnimations` | `string[]` | - | 点击时随机播放的动画列表 |
| `interactive.clickMessages` | `string[]` | - | 点击时随机显示的文字消息 |
| `interactive.messageDisplayTime` | `number` | `3000` | 文字显示时间（毫秒） |
| `interactive.idleAnimations` | `string[]` | - | 待机动画列表 |
| `interactive.idleInterval` | `number` | `8000` | 待机动画切换间隔（毫秒） |

### 响应式配置

| 属性 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `responsive.hideOnMobile` | `boolean` | `true` | 是否在移动端隐藏 |
| `responsive.mobileBreakpoint` | `number` | `768` | 移动端断点（px） |

### 其他

| 属性 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `zIndex` | `number` | `1000` | 层级 |
| `opacity` | `number` | `1.0` | 透明度（0-1） |

## Live2D 模型配置

### 基础配置

| 属性 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `enable` | `boolean` | `false` | 是否启用 Live2D 看板娘 |

### 模型配置

| 属性 | 类型 | 说明 |
|------|------|------|
| `model.path` | `string` | Live2D 模型文件路径（model.json） |

### 位置配置

| 属性 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `position.corner` | `string` | `"bottom-left"` | 显示位置 |
| `position.offsetX` | `number` | `0` | 水平偏移量 |
| `position.offsetY` | `number` | `0` | 垂直偏移量 |

### 尺寸配置

| 属性 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `size.width` | `number` | `135` | 容器宽度 |
| `size.height` | `number` | `165` | 容器高度 |

### 交互配置

| 属性 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `interactive.enabled` | `boolean` | `true` | 是否启用交互功能 |
| `interactive.clickMessages` | `string[]` | - | 点击时随机显示的文字消息 |
| `interactive.messageDisplayTime` | `number` | `3000` | 文字显示时间（毫秒） |

::: info
Live2D 模型的 `motions` 和 `expressions` 会从模型 JSON 文件中自动读取，无需手动配置。
:::

### 响应式配置

| 属性 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `responsive.hideOnMobile` | `boolean` | `true` | 是否在移动端隐藏 |
| `responsive.mobileBreakpoint` | `number` | `768` | 移动端断点（px） |

## Spine 完整示例

```ts
export const spineModelConfig: SpineModelConfig = {
  enable: true,
  model: {
    path: "/pio/models/spine/firefly/1310.json",
    scale: 1.0,
    x: 0,
    y: 0,
  },
  position: {
    corner: "bottom-left",
    offsetX: 0,
    offsetY: 0,
  },
  size: { width: 135, height: 165 },
  interactive: {
    enabled: true,
    clickAnimations: ["emoji_0", "emoji_1", "emoji_2"],
    clickMessages: ["你好呀！", "今天也要加油哦！"],
    messageDisplayTime: 3000,
    idleAnimations: ["idle", "emoji_0"],
    idleInterval: 8000,
  },
  responsive: { hideOnMobile: true, mobileBreakpoint: 768 },
  zIndex: 1000,
  opacity: 1.0,
};
```

::: warning
在右下角放置模型可能会遮挡返回顶部按钮，建议使用 `"bottom-left"` 位置。
:::
