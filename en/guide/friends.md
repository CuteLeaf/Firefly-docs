# Friends

The friends configuration manages the friend links page display.

## Config File

`src/config/friendsConfig.ts`

## Page Configuration

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `columns` | `number` | `2` | Display columns: `2` or `3` |

## Friend Link Properties

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| `title` | `string` | Yes | Link title |
| `imgurl` | `string` | Yes | Avatar image URL |
| `desc` | `string` | Yes | Description |
| `siteurl` | `string` | Yes | Site URL |
| `tags` | `string[]` | No | Tags |
| `weight` | `number` | Yes | Sort weight (higher = first) |
| `enabled` | `boolean` | Yes | Whether enabled |

## Example

```ts
export const friendsConfig: FriendLink[] = [
  {
    title: "My Friend",
    imgurl: "https://example.com/avatar.jpg",
    desc: "A great blog",
    siteurl: "https://example.com",
    tags: ["Blog"],
    weight: 10,
    enabled: true,
  },
];
```

::: tip
- Set `enabled: false` to temporarily hide a friend link without deleting it
- Links are sorted by `weight` in descending order
- Custom content below the friends page can be written in `src/content/spec/friends.md`
:::
