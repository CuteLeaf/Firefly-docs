# Font

Firefly supports custom font configuration using CDN fonts or local font files.

## Config File

`src/config/fontConfig.ts`

## Basic Configuration

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `enable` | `boolean` | `false` | Enable custom fonts |
| `preload` | `boolean` | `true` | Preload font files |
| `selected` | `string \| string[]` | `["misans-regular"]` | Selected font ID(s) |
| `fallback` | `string[]` | `["system-ui", ...]` | Global font fallback list |

## Font Item Properties

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| `id` | `string` | Yes | Unique font identifier |
| `name` | `string` | Yes | Display name |
| `src` | `string` | Yes | Font file path or URL |
| `family` | `string` | Yes | CSS `font-family` name |
| `weight` | `string \| number` | No | Font weight |
| `style` | `string` | No | Font style: `"normal"`, `"italic"`, `"oblique"` |
| `display` | `string` | No | `font-display`: `"auto"`, `"block"`, `"swap"`, `"fallback"`, `"optional"` |

## Built-in Fonts

| ID | Name | Source |
|----|------|--------|
| `system` | System Font | Built-in |
| `zen-maru-gothic` | Zen Maru Gothic | Google Fonts |
| `inter` | Inter | Google Fonts |
| `misans-normal` | MiSans Normal | unpkg CDN |
| `misans-regular` | MiSans Regular | unpkg CDN |
| `misans-semibold` | MiSans Semibold | unpkg CDN |

## Adding Custom Fonts

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

Then add it to `selected`:

```ts
selected: ["my-font"],
```

::: warning
- CDN fonts are recommended as they support on-demand loading with good performance
- Local font files require font subsetting, otherwise pages will load slowly
- Font subsetting may cause dynamic content (comments, Bangumi, etc.) to display incorrectly
:::
