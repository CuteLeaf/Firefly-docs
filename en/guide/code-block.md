# Code Block

Code block configuration is based on [Expressive Code](https://expressive-code.com/), supporting custom themes and code collapsing.

## Config File

`src/config/expressiveCodeConfig.ts`

## Properties

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `darkTheme` | `string` | `"one-dark-pro"` | Dark mode code theme |
| `lightTheme` | `string` | `"one-light"` | Light mode code theme |

See [Expressive Code Themes](https://expressive-code.com/guides/themes/) for more themes.

## Code Collapsing

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `pluginCollapsible.enable` | `boolean` | `true` | Enable collapsing |
| `pluginCollapsible.lineThreshold` | `number` | `15` | Line count threshold for collapse button |
| `pluginCollapsible.previewLines` | `number` | `8` | Preview lines when collapsed |
| `pluginCollapsible.defaultCollapsed` | `boolean` | `true` | Default to collapsed for long blocks |

```ts
pluginCollapsible: {
  enable: true,
  lineThreshold: 15,
  previewLines: 8,
  defaultCollapsed: true,
},
```

::: warning
Restart the Astro dev server after changing this configuration.
:::
