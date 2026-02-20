# 友链

友链配置管理友情链接页面的展示内容。

## 配置文件

`src/config/friendsConfig.ts`

## 页面配置

| 属性 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `columns` | `number` | `2` | 显示列数：`2` 或 `3` |

## 友链项属性

| 属性 | 类型 | 必填 | 说明 |
|------|------|------|------|
| `title` | `string` | 是 | 友链标题 |
| `imgurl` | `string` | 是 | 头像图片 URL |
| `desc` | `string` | 是 | 友链描述 |
| `siteurl` | `string` | 是 | 友链地址 |
| `tags` | `string[]` | 否 | 标签数组 |
| `weight` | `number` | 是 | 权重，数字越大排序越靠前 |
| `enabled` | `boolean` | 是 | 是否启用 |

## 配置示例

```ts
export const friendsConfig: FriendLink[] = [
  {
    title: "夏夜流萤",
    imgurl: "https://q1.qlogo.cn/g?b=qq&nk=7618557&s=640",
    desc: "一个博客站点",
    siteurl: "https://blog.cuteleaf.cn",
    tags: ["Blog"],
    weight: 10,
    enabled: true,
  },
  {
    title: "Astro",
    imgurl: "https://avatars.githubusercontent.com/u/44914786",
    desc: "The web framework for content-driven websites.",
    siteurl: "https://github.com/withastro/astro",
    tags: ["Framework"],
    weight: 8,
    enabled: true,
  },
];
```

::: tip
- 设置 `enabled: false` 可以暂时隐藏某个友链而不需要删除
- 友链按 `weight` 降序排列，权重越大越靠前
- 可以在 `src/content/spec/friends.md` 中编写友链页面下方的自定义内容
:::
