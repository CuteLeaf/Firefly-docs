# Navbar

The navbar configuration controls the top navigation menu links and search functionality.

## Config File

`src/config/navBarConfig.ts`

## Preset Links

Firefly provides built-in navigation link presets:

| Preset | Description |
|--------|-------------|
| `LinkPreset.Home` | Home page |
| `LinkPreset.Archive` | Archive |
| `LinkPreset.About` | About |
| `LinkPreset.Friends` | Friends |
| `LinkPreset.Sponsor` | Sponsor |
| `LinkPreset.Guestbook` | Guestbook |
| `LinkPreset.Bangumi` | Bangumi |

## Custom Links

Custom links support the following properties:

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| `name` | `string` | Yes | Link name |
| `url` | `string` | Yes | Link URL |
| `icon` | `string` | No | Icon (Iconify format) |
| `external` | `boolean` | No | External link |
| `children` | `array` | No | Submenu items (supports nesting) |

## Example

```ts
import { LinkPreset, type NavBarLink } from "../types/config";

const links: (NavBarLink | LinkPreset)[] = [
  LinkPreset.Home,
  LinkPreset.Archive,

  // Custom link with submenu
  {
    name: "Links",
    url: "/links/",
    icon: "material-symbols:link",
    children: [
      {
        name: "GitHub",
        url: "https://github.com/CuteLeaf/Firefly",
        external: true,
        icon: "fa7-brands:github",
      },
    ],
  },

  LinkPreset.Friends,
];
```

## Search Configuration

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `method` | `NavBarSearchMethod` | `NavBarSearchMethod.PageFind` | Search method, currently supports PageFind |

## Dynamic Navbar

The navbar automatically adjusts based on `siteConfig.pages` settings:

- `pages.guestbook: false` — hides Guestbook link
- `pages.sponsor: false` — hides Sponsor link
- `pages.bangumi: false` — hides Bangumi link

::: tip
Pre-installed icon sets: `fa7-brands`, `fa7-regular`, `fa7-solid`, `material-symbols`, `simple-icons`. Visit [icones.js.org](https://icones.js.org/) for icon codes. Install additional sets with: `pnpm add @iconify-json/<icon-set-name>`.
:::
