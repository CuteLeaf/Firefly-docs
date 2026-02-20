# 更新模板

本指南介绍如何将 Firefly 模板更新到最新版本。

## 更新方式

### 方法一：Git 合并（推荐）

如果你是通过 `git clone` 获取的项目，可以通过 Git 拉取上游更新。

#### 1. 添加上游仓库

如果还没有添加过上游仓库：

```bash
git remote add upstream https://github.com/CuteLeaf/Firefly.git
```

#### 2. 拉取最新代码

```bash
git fetch upstream
```

#### 3. 合并更新

```bash
git merge upstream/master
```

#### 4. 解决冲突

如果出现合并冲突，通常发生在你修改过的配置文件上。手动解决冲突后：

```bash
git add .
git commit -m "merge: update Firefly theme"
```

::: tip
建议只修改 `src/config/` 目录下的配置文件和 `src/content/` 目录下的内容文件，尽量不要修改主题核心文件，这样更新时冲突会比较少。
:::

### 方法二：手动覆盖

如果 Git 合并冲突太多或者你做了大量自定义修改：

1. 备份你的配置文件和内容：
   - `src/config/` — 所有配置文件
   - `src/content/` — 文章和页面内容
   - `public/` — 静态资源（图片、字体等）

2. 下载最新版本的 Firefly

3. 将备份的文件还原到对应目录

4. 重新安装依赖：

```bash
pnpm install
```

5. 启动开发服务器，检查是否有报错：

```bash
pnpm dev
```

## 更新后检查

更新完成后，建议检查以下内容：

1. **配置文件兼容性**：新版本可能新增了配置项，查看仓库的 commit 记录了解变更
2. **类型检查**：如果 TypeScript 报错，说明配置文件的类型定义可能有变化，参照类型定义补充新增的必填字段
3. **依赖更新**：运行 `pnpm install` 确保依赖是最新的
4. **本地预览**：运行 `pnpm dev` 在本地预览，确认页面渲染正常
5. **构建测试**：运行 `pnpm build` 确认构建没有错误
