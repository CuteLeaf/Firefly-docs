# 许可证

许可证配置控制文章顶部显示的版权信息。

## 配置文件

`src/config/licenseConfig.ts`

## 配置项

| 属性 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `enable` | `boolean` | `true` | 是否在文章顶部显示许可证信息 |
| `name` | `string` | `"CC BY-NC-SA 4.0"` | 许可证名称 |
| `url` | `string` | - | 许可证链接 |

## 配置示例

```ts
export const licenseConfig: LicenseConfig = {
  enable: true,
  name: "CC BY-NC-SA 4.0",
  url: "https://creativecommons.org/licenses/by-nc-sa/4.0/",
};
```

## 常用许可证

| 许可证 | 说明 |
|--------|------|
| CC BY 4.0 | 署名 |
| CC BY-SA 4.0 | 署名-相同方式共享 |
| CC BY-NC 4.0 | 署名-非商业性使用 |
| CC BY-NC-SA 4.0 | 署名-非商业性使用-相同方式共享 |
| CC BY-ND 4.0 | 署名-禁止演绎 |
| CC BY-NC-ND 4.0 | 署名-非商业性使用-禁止演绎 |
