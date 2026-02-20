# Comment System

Firefly supports multiple comment systems including Twikoo, Waline, Giscus, Disqus, and Artalk.

## Config File

`src/config/commentConfig.ts`

## Basic Configuration

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `type` | `string` | `"none"` | Comment system: `"none"`, `"twikoo"`, `"waline"`, `"giscus"`, `"disqus"`, `"artalk"` |

Set `type` to the desired comment system name to enable it, or `"none"` to disable comments.

## Twikoo

[Twikoo](https://twikoo.js.org/) is a simple, safe, free comment system for static sites.

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `twikoo.envId` | `string` | - | Twikoo environment ID or backend URL |
| `twikoo.lang` | `string` | `"zh-CN"` | Language |
| `twikoo.visitorCount` | `boolean` | `true` | Enable visitor count |

## Waline

[Waline](https://waline.js.org/) is a comment system derived from Valine with backend support.

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `waline.serverURL` | `string` | - | Waline backend URL |
| `waline.lang` | `string` | `"zh-CN"` | Language |
| `waline.login` | `string` | `"enable"` | Login mode: `"enable"`, `"force"`, `"disable"` |
| `waline.visitorCount` | `boolean` | `true` | Enable visitor count |

## Artalk

[Artalk](https://artalk.js.org/) is a self-hosted comment system.

| Property | Type | Default | Description |
|----------|------|---------|-------------|
| `artalk.server` | `string` | - | Artalk backend API URL |
| `artalk.locale` | `string` | `"zh-CN"` | Language |
| `artalk.visitorCount` | `boolean` | `true` | Enable visitor count |

## Giscus

[Giscus](https://giscus.app/) is a comment system powered by GitHub Discussions.

| Property | Type | Description |
|----------|------|-------------|
| `giscus.repo` | `string` | GitHub repository (`owner/repo`) |
| `giscus.repoId` | `string` | Repository ID |
| `giscus.category` | `string` | Discussion category name |
| `giscus.categoryId` | `string` | Category ID |
| `giscus.mapping` | `string` | Mapping method (e.g., `"title"`) |
| `giscus.strict` | `string` | Strict mode |
| `giscus.reactionsEnabled` | `string` | Enable reactions |
| `giscus.emitMetadata` | `string` | Emit metadata |
| `giscus.inputPosition` | `string` | Input position |
| `giscus.lang` | `string` | Language |
| `giscus.loading` | `string` | Loading method |

::: tip
Visit [giscus.app](https://giscus.app/) to get your repository configuration parameters.
:::

## Disqus

[Disqus](https://disqus.com/) is a third-party comment hosting platform.

| Property | Type | Description |
|----------|------|-------------|
| `disqus.shortname` | `string` | Disqus shortname |
