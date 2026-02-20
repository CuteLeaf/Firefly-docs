# License

The license configuration controls the copyright information displayed at the top of posts.

## Config File

`src/config/licenseConfig.ts`

## Properties

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `enable` | `boolean` | `true` | Show license info on posts |
| `name` | `string` | `"CC BY-NC-SA 4.0"` | License name |
| `url` | `string` | - | License URL |

## Example

```ts
export const licenseConfig: LicenseConfig = {
  enable: true,
  name: "CC BY-NC-SA 4.0",
  url: "https://creativecommons.org/licenses/by-nc-sa/4.0/",
};
```

## Common Licenses

| License | Description |
|---------|-------------|
| CC BY 4.0 | Attribution |
| CC BY-SA 4.0 | Attribution-ShareAlike |
| CC BY-NC 4.0 | Attribution-NonCommercial |
| CC BY-NC-SA 4.0 | Attribution-NonCommercial-ShareAlike |
| CC BY-ND 4.0 | Attribution-NoDerivatives |
| CC BY-NC-ND 4.0 | Attribution-NonCommercial-NoDerivatives |
