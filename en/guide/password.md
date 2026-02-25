# Encryption Post 

Firefly supports password protection for posts. Encrypted posts are encrypted at build time using the AES-256-GCM algorithm — no plaintext content exists in the page source. Visitors must enter the correct password, and the browser decrypts the content locally via the Web Crypto API.

## Basic Usage

Add the `password` field to the Front-matter to enable encryption:

```yaml
---
title: Private Post
published: 2025-01-01
password: "your-password"
---

All content here will be encrypted.
```

## Password Hint

Optionally add a `passwordHint` field to give visitors a hint:

```yaml
---
title: Private Post
published: 2025-01-01
password: "your-password"
passwordHint: "My birthday"
---
```

## Front-matter Properties

| Property | Type | Required | Description |
|----------|------|----------|-------------|
| `password` | `string` | No | Post password. When set, the post will be encrypted |
| `passwordHint` | `string` | No | Password hint displayed above the input field |

## Encryption Scope

| Content | Handling |
|---------|----------|
| Post body | Encrypted |
| Sponsor / Share block | Encrypted |
| License block | Encrypted |
| Title, metadata | Not encrypted |
| Cover image | Not encrypted |
| Comments | Hidden |
| Table of Contents | Shown after decryption |
| RSS output | Title and description only, no body |

## Session Cache

- After entering the correct password, it is cached in the browser's `sessionStorage`
- Refreshing the page within the same session does not require re-entering the password
- Cache is cleared when the browser is closed

## Technical Details

- **Encryption**: AES-256-GCM
- **Key Derivation**: PBKDF2 (SHA-256, 100,000 iterations)
- **Build-time encryption**: Node.js `crypto` module
- **Client-side decryption**: Native Web Crypto API, no third-party dependencies
- Supports both `.md` and `.mdx` formats

::: tip
The password is written in plaintext in the Front-matter and is only used at build time. The build output does not contain the original password — only the encrypted ciphertext.
:::

::: warning
Encryption security depends on password strength. Since the ciphertext is publicly visible in the page source, weak passwords can theoretically be brute-forced. Use a sufficiently complex password.
:::
