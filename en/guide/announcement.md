# Announcement

The announcement component displays in the sidebar for showing important notices or messages.

## Config File

`src/config/announcementConfig.ts`

## Properties

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `title` | `string` | - | Announcement title |
| `content` | `string` | - | Announcement content |
| `icon` | `string` | - | Icon (Iconify format) |
| `type` | `string` | - | Type: `"info"`, `"warning"`, `"success"`, `"error"` |
| `closable` | `boolean` | `true` | Allow users to close |

## Link Configuration

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `link.enable` | `boolean` | `true` | Enable link |
| `link.text` | `string` | - | Link text |
| `link.url` | `string` | - | Link URL |
| `link.external` | `boolean` | `false` | External link |

## Example

```ts
export const announcementConfig: AnnouncementConfig = {
  title: "Announcement",
  content: "Welcome to my blog! This is a sample announcement.",
  closable: true,
  link: {
    enable: true,
    text: "Learn more",
    url: "/about/",
    external: false,
  },
};
```

::: tip
The announcement component's visibility is controlled in `sidebarConfig.ts` by setting the `announcement` component's `enable` property.
:::
