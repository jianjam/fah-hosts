# Folding@home hosts 订阅

用于解决国内网络下 Folding@home 客户端无法获取工作单元的问题。

## 订阅地址（加到 SwitchHosts 的“远程”）

```
https://gh-proxy.org/https://raw.githubusercontent.com/jianjam/fah-hosts/main/hosts
```

- 类型：远程 / Remote
- 刷新间隔：86400 秒（每天）
- 建议同时勾选“启动时刷新”

## 背景

`api.foldingathome.org` / `api2` / `api4` 解析到 `18.219.10.165`，该 IP 在国内常被阻断，
导致 FAH 客户端连得上账号服务器却拿不到任务。`api3.foldingathome.org`
（`3.141.152.240`）通常可用，因此把这三个域名统一指向当前可达的 API 后端。

## 内容示例

```hosts
3.141.152.240  api.foldingathome.org
3.141.152.240  api2.foldingathome.org
3.141.152.240  api4.foldingathome.org
```

## 自动更新方式

本文件由本地脚本 `update-fah-hosts.ps1` 每天探测一次“本机当前可达”的
`api*.foldingathome.org` 后端，并把结果推送到本仓库。之所以在本地探测而不是用
GitHub Actions，是因为“哪个 IP 在国内可用”只有本机网络知道。

## 删除

如果不再需要，可删除本仓库，并在 SwitchHosts 中移除对应条目。
