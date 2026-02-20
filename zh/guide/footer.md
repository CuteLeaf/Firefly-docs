# 页脚

页脚配置允许在站点底部注入自定义 HTML 内容，如备案号等。

## 配置文件

- TypeScript 配置：`src/config/footerConfig.ts`
- HTML 内容：`src/config/FooterConfig.html`

## 配置项

| 属性 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `enable` | `boolean` | `false` | 是否启用 Footer HTML 注入功能 |

```ts
export const footerConfig: FooterConfig = {
  enable: false,
};
```

## 自定义内容

直接编辑 `src/config/FooterConfig.html` 文件来添加备案号等自定义内容。

```html
<!-- src/config/FooterConfig.html 示例 -->
<div style="text-align: center; font-size: 12px;">
  <a href="https://beian.miit.gov.cn/" target="_blank">京ICP备XXXXXXXX号</a>
</div>
```

::: tip
修改 HTML 文件后，如果 `enable` 已设为 `true`，页面会自动更新（开发模式下）。
:::
