# 个人资料

个人资料配置控制侧边栏中的用户资料卡片，包括头像、名字、签名和社交链接。

## 配置文件

`src/config/profileConfig.ts`

## 配置项

| 属性 | 类型 | 必填 | 说明 |
|------|------|------|------|
| `avatar` | `string` | 否 | 头像图片路径 |
| `name` | `string` | 是 | 名字 |
| `bio` | `string` | 否 | 个人签名 |
| `links` | `array` | 是 | 社交链接列表 |

### 头像路径

头像支持三种格式：

1. **public 目录**（以 `/` 开头，不优化）：`"/assets/images/avatar.webp"`
2. **src 目录**（不以 `/` 开头，自动优化，推荐）：`"assets/images/avatar.avif"`
3. **远程 URL**：`"https://example.com/avatar.jpg"`

### 社交链接

| 属性 | 类型 | 必填 | 说明 |
|------|------|------|------|
| `name` | `string` | 是 | 链接名称 |
| `icon` | `string` | 是 | 图标（Iconify 格式） |
| `url` | `string` | 是 | 链接地址 |
| `showName` | `boolean` | 否 | 是否显示名称（默认 `false` 只显示图标） |

## 配置示例

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
已预装的图标集：`fa7-brands`、`fa7-regular`、`fa7-solid`、`material-symbols`、`simple-icons`。

访问 [icones.js.org](https://icones.js.org/) 获取更多图标代码。如果需要其他图标集，可安装：

```bash
pnpm add @iconify-json/<icon-set-name>
```
:::
