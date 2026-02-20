# 公告

公告组件显示在侧边栏中，用于展示重要通知或消息。

## 配置文件

`src/config/announcementConfig.ts`

## 配置项

| 属性 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `title` | `string` | `"公告"` | 公告标题 |
| `content` | `string` | - | 公告内容 |
| `icon` | `string` | - | 公告图标（Iconify 格式） |
| `type` | `string` | - | 公告类型：`"info"` `"warning"` `"success"` `"error"` |
| `closable` | `boolean` | `true` | 是否允许用户关闭公告 |

## 链接配置

| 属性 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `link.enable` | `boolean` | `true` | 是否启用链接 |
| `link.text` | `string` | `"了解更多"` | 链接文本 |
| `link.url` | `string` | - | 链接地址 |
| `link.external` | `boolean` | `false` | 是否为外部链接 |

## 配置示例

```ts
export const announcementConfig: AnnouncementConfig = {
  title: "公告",
  content: "欢迎来到我的博客！这是一则示例公告。",
  closable: true,
  link: {
    enable: true,
    text: "了解更多",
    url: "/about/",
    external: false,
  },
};
```

::: tip
公告组件的显示/隐藏在 `sidebarConfig.ts` 中控制，通过设置 `announcement` 组件的 `enable` 属性来开关。
:::
