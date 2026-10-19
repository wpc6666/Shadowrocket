# Shadowrocket 配置

> 小火箭（Shadowrocket）iOS 代理工具配置集 —— 分流规则 + 按地区自动测速 + 双 DNS 防污染，订阅即用。

[![Platform](https://img.shields.io/badge/Platform-iOS-000000?logo=apple&logoColor=white)](https://apps.apple.com/us/app/shadowrocket/id932747118)
[![App](https://img.shields.io/badge/App-Shadowrocket-1E90FF)](https://apps.apple.com/us/app/shadowrocket/id932747118)
[![Config](https://img.shields.io/badge/Config-v2025.5.17-2ea44f)](./2025.5.17.conf)

**在线介绍页**：<https://wpc6666.github.io/Shadowrocket/>

---

## 快速开始

### 1. 安装 Shadowrocket

App Store **美区 / 港区**搜索 Shadowrocket，付费应用（约 $2.99）。国区不可用。

### 2. 添加订阅

打开 App → 首页右上角 `+` → 类型选 `Subscribe`（订阅）→ URL 填：

```
https://raw.githubusercontent.com/wpc6666/Shadowrocket/refs/heads/main/2025.5.17.conf
```

保存后下拉更新，选中该配置，打开顶部开关即可。

### 3. 后续更新

配置里的 `update-url` 已指向本仓库，App 内点「更新」就能拿到最新版。

---

## 配置内容

| 段落 | 作用 |
|---|---|
| `[General]` | 全局开关：IPv6、DNS 服务器、`bypass-tun` 内网直连、`skip-proxy` 排除列表 |
| `[Proxy Group]` | 16 个 `url-test` 策略组，按地区（韩国 / 日本 / 美国 / 台湾等）自动测速选最快节点 |
| `[Rule]` | 44 条分流规则：域名 / IP 段 / 地区匹配后走指定策略 |
| `[URL Rewrite]` | URL 重写规则（默认关闭，按需启用） |
| `[MITM]` | HTTPS 中间人解密主机名列表，配合 URL Rewrite 使用 |

### 文件

| 文件 | 说明 |
|---|---|
| `2025.5.17.conf` | 主配置文件（114 行），Shadowrocket 订阅这个 |
| `index.html` | 在线介绍页（GitHub Pages） |
| `README.md` | 本文件 |

---

## ⚠️ 注意事项

- **本仓库不含任何节点信息**。只有分流规则与策略组，节点需自备（从你自己的机场或自建服务导入）。
- **MITM 与 URL Rewrite 默认关闭**。开启后 App 会解密 HTTPS 流量，请只对你信任的站点启用，并确认证书已安装且被信任。
- **规则会随上游列表变化**，建议每周更新一次。
- 某站点访问异常时，先检查是不是规则把它判成了「直连」。

---

## 目录结构

```
Shadowrocket/
├── 2025.5.17.conf   # 主配置
├── index.html       # 在线介绍页
└── README.md
```

---

## 相关

- [Quantumult 配置](https://github.com/wpc6666/Quantumult)
- [作者主页](https://wpc6666.github.io/)

---

## 许可

配置文件中的规则部分来自公开社区列表，版权归原作者。本仓库的整合与说明部分采用 MIT License。
