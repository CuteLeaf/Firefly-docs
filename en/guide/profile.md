# Profile

The profile configuration controls the user profile card in the sidebar, including avatar, name, bio and social links.

## Config File

`src/config/profileConfig.ts`

## Properties

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| `avatar` | `string` | No | Avatar image path |
| `name` | `string` | Yes | Display name |
| `bio` | `string` | No | Personal bio |
| `links` | `array` | Yes | Social links list |

### Avatar Path

The avatar supports three formats:

1. **public directory** (starts with `/`, no optimization): `"/assets/images/avatar.webp"`
2. **src directory** (no leading `/`, auto-optimized, recommended): `"assets/images/avatar.avif"`
3. **Remote URL**: `"https://example.com/avatar.jpg"`

### Social Links

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| `name` | `string` | Yes | Link name |
| `icon` | `string` | Yes | Icon (Iconify format) |
| `url` | `string` | Yes | Link URL |
| `showName` | `boolean` | No | Show name alongside icon (default: `false`) |

## Example

```ts
export const profileConfig: ProfileConfig = {
  avatar: "assets/images/avatar.avif",
  name: "Firefly",
  bio: "Hello, I'm Firefly.",
  links: [
    {
      name: "GitHub",
      icon: "fa7-brands:github",
      url: "https://github.com/CuteLeaf",
      showName: false,
    },
    {
      name: "Email",
      icon: "fa7-solid:envelope",
      url: "mailto:your@email.com",
      showName: false,
    },
    {
      name: "RSS",
      icon: "fa7-solid:rss",
      url: "/rss/",
      showName: false,
    },
  ],
};
```

::: tip
Pre-installed icon sets: `fa7-brands`, `fa7-regular`, `fa7-solid`, `material-symbols`, `simple-icons`.

Visit [icones.js.org](https://icones.js.org/) for more icon codes. Install additional sets:

```bash
pnpm add @iconify-json/<icon-set-name>
```
:::
