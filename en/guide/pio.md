# Live2D / Spine Model

Firefly supports displaying Live2D or Spine mascot models on the page. Choose one of the two.

## Config File

`src/config/pioConfig.ts`

## Spine Model

### Basic

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `enable` | `boolean` | `false` | Enable Spine mascot |

### Model

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `model.path` | `string` | - | Spine model file path (.json) |
| `model.scale` | `number` | `1.0` | Scale |
| `model.x` | `number` | `0` | X offset |
| `model.y` | `number` | `0` | Y offset |

### Position

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `position.corner` | `string` | `"bottom-left"` | Position: `"bottom-left"` `"bottom-right"` `"top-left"` `"top-right"` |
| `position.offsetX` | `number` | `0` | Horizontal offset |
| `position.offsetY` | `number` | `0` | Vertical offset |

### Size

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `size.width` | `number` | `135` | Container width |
| `size.height` | `number` | `165` | Container height |

### Interaction

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `interactive.enabled` | `boolean` | `true` | Enable interaction |
| `interactive.clickAnimations` | `string[]` | - | Click animations |
| `interactive.clickMessages` | `string[]` | - | Click messages |
| `interactive.messageDisplayTime` | `number` | `3000` | Message display time (ms) |
| `interactive.idleAnimations` | `string[]` | - | Idle animations |
| `interactive.idleInterval` | `number` | `8000` | Idle animation interval (ms) |

### Responsive

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `responsive.hideOnMobile` | `boolean` | `true` | Hide on mobile |
| `responsive.mobileBreakpoint` | `number` | `768` | Mobile breakpoint (px) |

### Other

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `zIndex` | `number` | `1000` | Z-index |
| `opacity` | `number` | `1.0` | Opacity (0-1) |

## Live2D Model

### Basic

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `enable` | `boolean` | `false` | Enable Live2D mascot |

### Model

| Property | Type | Description |
|----------|------|-------------|
| `model.path` | `string` | Live2D model file path (model.json) |

### Position

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `position.corner` | `string` | `"bottom-left"` | Display position |
| `position.offsetX` | `number` | `0` | Horizontal offset |
| `position.offsetY` | `number` | `0` | Vertical offset |

### Size

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `size.width` | `number` | `135` | Container width |
| `size.height` | `number` | `165` | Container height |

### Interaction

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `interactive.enabled` | `boolean` | `true` | Enable interaction |
| `interactive.clickMessages` | `string[]` | - | Click messages |
| `interactive.messageDisplayTime` | `number` | `3000` | Message display time (ms) |

::: info
Live2D model `motions` and `expressions` are automatically read from the model JSON file.
:::

### Responsive

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `responsive.hideOnMobile` | `boolean` | `true` | Hide on mobile |
| `responsive.mobileBreakpoint` | `number` | `768` | Mobile breakpoint (px) |

## Spine Full Example

```ts
export const spineModelConfig: SpineModelConfig = {
  enable: true,
  model: {
    path: "/pio/models/spine/firefly/1310.json",
    scale: 1.0,
    x: 0,
    y: 0,
  },
  position: { corner: "bottom-left", offsetX: 0, offsetY: 0 },
  size: { width: 135, height: 165 },
  interactive: {
    enabled: true,
    clickAnimations: ["emoji_0", "emoji_1", "emoji_2"],
    clickMessages: ["Hello!", "Have a nice day!"],
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
Placing the model in the bottom-right corner may block the back-to-top button. Consider using `"bottom-left"`.
:::
