# distictip

一个纯静态的 IP 去重工具，按 `IP:端口` 判断重复，支持选择去重与一键去重。

## 功能

- **一键去重**：自动保留每组中排在最后面的一条
- **选择去重**：弹出表格展示重复项，每组手动选一条，后缀（`#` 后面的备注）可直接编辑，跨页勾选状态保留
- 结果格式统一为 `IP:端口#后缀`
- 支持复制 / 下载结果
- 纯前端实现，无需后端

## 本地使用

直接用浏览器打开 `index.html` 即可。

## Cloudflare Pages 部署

### 方式一：上传资产（最简单）

1. 在 Cloudflare 控制台进入 **Workers & Pages** → **Create application** → **Pages** → **Upload assets**
2. 项目名填 `distictip`，把本仓库所有文件打包上传
3. 部署完成后访问 `https://distictip.pages.dev`

### 方式二：连接 Git 仓库

1. Cloudflare **Pages** → **Create** → **Connect to Git**，选择本仓库
2. 构建配置保持默认（无需构建命令），输出目录 `/`
3. 部署完成后访问分配到的 `.pages.dev` 域名

### 方式三：Wrangler CLI

```bash
npx wrangler pages deploy . --project-name distictip
```

## 去重标准

- 以 `IP:端口` 作为去重键（如 `23.227.38.65:443`）
- 无端口时按单独 IP 去重
- 输入支持每条一行，或以 `\` 分隔
