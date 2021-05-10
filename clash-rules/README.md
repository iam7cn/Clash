# 简介

本项目生成适用于 [**Clash Premium 内核**](https://github.com/Dreamacro/clash/releases/tag/premium)的规则集（RULE-SET），同时适用于所有使用 Clash Premium 内核的 Clash 图形用户界面（GUI）客户端。

## 说明

本项目规则集（RULE-SET）的数据主要来源于项目 [@Loyalsoldier/v2ray-rules-dat](https://github.com/Loyalsoldier/v2ray-rules-dat) 和 [@v2fly/domain-list-community](https://github.com/v2fly/domain-list-community)；[`Apple`](https://github.com/Loyalsoldier/clash-rules/blob/release/apple.txt) 和 [`Google`](https://github.com/Loyalsoldier/clash-rules/blob/release/google.txt) 列表里的域名来源于项目 [@felixonmars/dnsmasq-china-list](https://github.com/felixonmars/dnsmasq-china-list)；中国大陆 IPv4 地址数据使用 [@17mon/china_ip_list](https://github.com/17mon/china_ip_list)。

本项目的规则集（RULE-SET）只适用于 Clash **Premium** 版本。Clash Premium 相对于普通版，增加了 **TUN 增强模式**，能接管设备所有 TCP 和 UDP 流量，类似 [Surge for Mac](https://nssurge.com) 的增强模式。更多高级特性请看[官方 wiki](https://github.com/Dreamacro/clash/wiki/premium-core-features)。

### Clash Premium 各版本下载地址

- Clash Premium **命令行**版（适用于 Windows、macOS、Linux、OpenWRT 等多种平台）：[https://github.com/Dreamacro/clash/releases/tag/premium](https://github.com/Dreamacro/clash/releases/tag/premium)
- Clash Premium **图形用户界面**版：
  - [ClashX Pro](https://install.appcenter.ms/users/clashx/apps/clashx-pro/distribution_groups/public)（适用于 macOS）
  - [Clash for Windows](https://github.com/Fndroid/clash_for_windows_pkg/releases)（适用于 Windows、macOS）
  - [Clash for Android](https://github.com/Kr328/ClashForAndroid/releases)（适用于 Android）

## 规则文件地址及使用方式

### 在线地址（URL）

> 如果无法访问域名 `raw.githubusercontent.com`，可以使用第二个地址（`cdn.jsdelivr.net`），但是内容更新会有 12 小时的延迟。以下地址填写在 Clash 配置文件里的 `rule-providers` 里的 `url` 配置项中。

- **直连域名列表 Direct.list**：
  - [https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Direct.list](https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Direct.list)

- **PT直连域名列表 Pter.list**：
  - [https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Pter.list](https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Pter.list)

- **代理域名列表 Proxy.list**：
  - [https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Proxy.list](https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Proxy.list)
  
- **广告域名列表 Reject.list**：
  - [https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Reject.list](https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Reject.list)
  
- **私有网络专用域名列表 Private.list**：
  - [https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Private.list](https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Private.list)

- **Apple 域名列表 Apple.list**：
  - [https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Apple.list](https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Apple.list)
  
- **iCloud 域名列表 Icloud.list**：
  - [https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Icloud.list](https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Icloud.list)
- **Google 域名列表 Google.list**：
  - [https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Google.list](https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Google.list)
  
- **GFWList 域名列表 GFW.list**：
  - [https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/GFW.list](https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/GFW.list)

- **GreatFire 域名列表 Greatfire.list**：
  - [https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Greatfire.list](https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Greatfire.list)

- **非中国大陆使用的顶级域名列表 Tld-not-cn.list**：
  - [https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Tld-not-cn.list](https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Tld-not-cn.list)
  
- **Telegram 使用的 IP 地址列表 Telegramcidr.list**：
  - [https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Telegramcidr.list](https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Telegramcidr.list)
  
- **局域网 IP 及保留 IP 地址列表 Lancidr.list**：
  - [https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Lancidr.list](https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Lancidr.list)
  
- **中国大陆 IPv4 地址列表 CNcidr.list**：
  - [https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/CNcidr.list](https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/CNcidr.list)
  
- **国内国外互联网公司广告 BanAD.list**：  
  - [https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/BanAD.list](https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/BanAD.list)

### 使用方式

关于 Clash Premium 使用方式，请查看[官方文档](https://github.com/Dreamacro/clash/wiki/premium-core-features) 或 [Lancellc's GitBook](https://lancellc.gitbook.io/clash/)。

要想使用本项目的规则集，只需要在 Clash 配置文件中添加如下 `rule-providers` 和 `rules`。

#### Rule Providers 配置方式

```yaml
rule-providers:
  Reject: # 屏蔽网址
    type: http
    behavior: domain
    url: "https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Reject.list"
    path: ./ruleset/reject.yaml
    interval: 3600
    
  Pter: # PT直连网址
    type: http
    behavior: domain
    url: "https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Pter.list"
    path: ./ruleset/Pter.yaml
    interval: 3600

  Icloud: # icloud网址
    type: http  
    behavior: domain
    url: "https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Icloud.list"
    path: ./ruleset/icloud.yaml
    interval: 3600

  Apple: # apple网址
    type: http
    behavior: domain
    url: "https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Apple.list"
    path: ./ruleset/apple.yaml
    interval: 3600

  Google: # google网址
    type: http
    behavior: domain
    url: "https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Google.list"
    path: ./ruleset/google.yaml
    interval: 3600

  Proxy: # 代理网址
    type: http
    behavior: domain
    url: "https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Proxy.list"
    path: ./ruleset/proxy.yaml
    interval: 3600

  Direct: # 直连网址
    type: http
    behavior: domain
    url: "https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Direct.list"
    path: ./ruleset/direct.yaml
    interval: 3600

  Private: # 自定义代理网址
    type: http
    behavior: domain
    url: "https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Private.list"
    path: ./ruleset/private.yaml
    interval: 3600

  GFW: # GFW网址
    type: http
    behavior: domain
    url: "https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/GFW.list"
    path: ./ruleset/gfw.yaml
    interval: 3600

  Greatfire: # GFW网址
    type: http
    behavior: domain
    url: "https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Greatfire.list"
    path: ./ruleset/greatfire.yaml
    interval: 3600

  Tld-not-cn: # 非CN网址
    type: http
    behavior: domain
    url: "https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Tld-not-cn.list"
    path: ./ruleset/tld-not-cn.yaml
    interval: 3600

  Telegramcidr: # TG IP地址
    type: http
    behavior: ipcidr
    url: "https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Telegramcidr.list"
    path: ./ruleset/telegramcidr.yaml
    interval: 3600

  CNcidr: # china-ip地址
    type: http
    behavior: ipcidr
    url: "https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/CNcidr.list"
    path: ./ruleset/cncidr.yaml
    interval: 3600

  Lancidr: # 内网IP地址
    type: http
    behavior: ipcidr
    url: "https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/Lancidr.list"
    path: ./ruleset/lancidr.yaml
    interval: 3600  

  BanAD: # 广告拦截
    type: http
    behavior: classical # domain, ipcidr or classical (premium core only)
    url: "https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/clash-rules/BanAD.list"
    path: ./ruleset/BanAD.yaml
    interval: 3600
```

#### 白名单模式 Rules 配置方式（推荐）

- 白名单模式，意为「**没有命中规则的网络流量，统统使用代理**」，适用于服务器线路网络质量稳定、快速，不缺服务器流量的用户。
- 以下配置中，除了 `DIRECT` 和 `REJECT` 是默认存在于 Clash 中的 policy（路由策略/流量处理策略），其余均为自定义 policy，对应配置文件中 `proxies` 或 `proxy-groups` 中的 `name`。如你直接使用下面的 `rules` 规则，则需要在 `proxies` 或 `proxy-groups` 中手动配置一个 `name` 为 `PROXY` 的 policy。
- 如你希望 Apple、iCloud 和 Google 列表中的域名使用代理，则把 policy 由 `DIRECT` 改为 `PROXY`，以此类推，举一反三。
- 如你不希望进行 DNS 解析，可在 `GEOIP` 规则的最后加上 `,no-resolve`，如 `GEOIP,CN,DIRECT,no-resolve`。

```yaml
rules:
  - PROCESS-NAME,v2ray,DIRECT
  - PROCESS-NAME,xray,DIRECT
  - PROCESS-NAME,naive,DIRECT
  - PROCESS-NAME,trojan,DIRECT
  - PROCESS-NAME,trojan-go,DIRECT
  - PROCESS-NAME,ss-local,DIRECT
  - PROCESS-NAME,privoxy,DIRECT
  - PROCESS-NAME,leaf,DIRECT
  - PROCESS-NAME,v2ray.exe,DIRECT
  - PROCESS-NAME,xray.exe,DIRECT
  - PROCESS-NAME,naive.exe,DIRECT
  - PROCESS-NAME,trojan.exe,DIRECT
  - PROCESS-NAME,trojan-go.exe,DIRECT
  - PROCESS-NAME,ss-local.exe,DIRECT
  - PROCESS-NAME,privoxy.exe,DIRECT  
  - PROCESS-NAME,leaf.exe,DIRECT
  - PROCESS-NAME,Surge,DIRECT
  - PROCESS-NAME,Surge 2,DIRECT
  - PROCESS-NAME,Surge 3,DIRECT
  - PROCESS-NAME,Surge 4,DIRECT
  - PROCESS-NAME,Surge%202,DIRECT
  - PROCESS-NAME,Surge%203,DIRECT
  - PROCESS-NAME,Surge%204,DIRECT
  - PROCESS-NAME,Thunder,DIRECT
  - PROCESS-NAME,DownloadService,DIRECT
  - PROCESS-NAME,qBittorrent,DIRECT
  - PROCESS-NAME,Transmission,DIRECT
  - PROCESS-NAME,fdm,DIRECT
  - PROCESS-NAME,aria2c,DIRECT
  - PROCESS-NAME,Folx,DIRECT
  - PROCESS-NAME,NetTransport,DIRECT
  - PROCESS-NAME,uTorrent,DIRECT
  - PROCESS-NAME,WebTorrent,DIRECT
  - PROCESS-NAME,aria2c.exe,DIRECT
  - PROCESS-NAME,BitComet.exe,DIRECT
  - PROCESS-NAME,fdm.exe,DIRECT
  - PROCESS-NAME,NetTransport.exe,DIRECT
  - PROCESS-NAME,qbittorrent.exe,DIRECT
  - PROCESS-NAME,Thunder.exe,DIRECT
  - PROCESS-NAME,ThunderVIP.exe,DIRECT
  - PROCESS-NAME,transmission-daemon.exe,DIRECT
  - PROCESS-NAME,transmission-qt.exe,DIRECT
  - PROCESS-NAME,uTorrent.exe,DIRECT
  - PROCESS-NAME,WebTorrent.exe,DIRECT
  - DOMAIN,clash.razord.top,DIRECT
  - DOMAIN,yacd.haishan.me,DIRECT
  - RULE-SET,Private,DIRECT
  - RULE-SET,Pter,DIRECT
  - RULE-SET,Reject,REJECT
  - RULE-SET,Icloud,DIRECT
  - RULE-SET,Apple,DIRECT
  - RULE-SET,Google,DIRECT
  - RULE-SET,Proxy,PROXY
  - RULE-SET,Direct,DIRECT
  - RULE-SET,Telegramcidr,PROXY
  - RULE-SET,BanAD,REJECT
  - GEOIP,,DIRECT
  - GEOIP,CN,DIRECT
  - MATCH,PROXY
```

#### 黑名单模式 Rules 配置方式

- 黑名单模式，意为「**只有命中规则的网络流量，才使用代理**」，适用于服务器线路网络质量不稳定或不够快，或服务器流量紧缺的用户。通常也是软路由用户、家庭网关用户的常用模式。
- 以下配置中，除了 `DIRECT` 和 `REJECT` 是默认存在于 Clash 中的 policy（路由策略/流量处理策略），其余均为自定义 policy，对应配置文件中 `proxies` 或 `proxy-groups` 中的 `name`。如你直接使用下面的 `rules` 规则，则需要在 `proxies` 或 `proxy-groups` 中手动配置一个 `name` 为 `PROXY` 的 policy。

```yaml
rules:
  - PROCESS-NAME,v2ray,DIRECT
  - PROCESS-NAME,xray,DIRECT
  - PROCESS-NAME,naive,DIRECT
  - PROCESS-NAME,trojan,DIRECT
  - PROCESS-NAME,trojan-go,DIRECT
  - PROCESS-NAME,ss-local,DIRECT
  - PROCESS-NAME,privoxy,DIRECT
  - PROCESS-NAME,leaf,DIRECT
  - PROCESS-NAME,v2ray.exe,DIRECT
  - PROCESS-NAME,xray.exe,DIRECT
  - PROCESS-NAME,naive.exe,DIRECT
  - PROCESS-NAME,trojan.exe,DIRECT
  - PROCESS-NAME,trojan-go.exe,DIRECT
  - PROCESS-NAME,ss-local.exe,DIRECT
  - PROCESS-NAME,privoxy.exe,DIRECT
  - PROCESS-NAME,leaf.exe,DIRECT
  - PROCESS-NAME,Surge,DIRECT
  - PROCESS-NAME,Surge 2,DIRECT
  - PROCESS-NAME,Surge 3,DIRECT
  - PROCESS-NAME,Surge 4,DIRECT
  - PROCESS-NAME,Surge%202,DIRECT
  - PROCESS-NAME,Surge%203,DIRECT
  - PROCESS-NAME,Surge%204,DIRECT
  - PROCESS-NAME,Thunder,DIRECT
  - PROCESS-NAME,DownloadService,DIRECT
  - PROCESS-NAME,qBittorrent,DIRECT
  - PROCESS-NAME,Transmission,DIRECT
  - PROCESS-NAME,fdm,DIRECT
  - PROCESS-NAME,aria2c,DIRECT
  - PROCESS-NAME,Folx,DIRECT
  - PROCESS-NAME,NetTransport,DIRECT
  - PROCESS-NAME,uTorrent,DIRECT
  - PROCESS-NAME,WebTorrent,DIRECT
  - PROCESS-NAME,aria2c.exe,DIRECT
  - PROCESS-NAME,BitComet.exe,DIRECT
  - PROCESS-NAME,fdm.exe,DIRECT
  - PROCESS-NAME,NetTransport.exe,DIRECT
  - PROCESS-NAME,qbittorrent.exe,DIRECT
  - PROCESS-NAME,Thunder.exe,DIRECT
  - PROCESS-NAME,ThunderVIP.exe,DIRECT
  - PROCESS-NAME,transmission-daemon.exe,DIRECT
  - PROCESS-NAME,transmission-qt.exe,DIRECT
  - PROCESS-NAME,uTorrent.exe,DIRECT
  - PROCESS-NAME,WebTorrent.exe,DIRECT
  - DOMAIN,clash.razord.top,DIRECT
  - DOMAIN,yacd.haishan.me,DIRECT
  - RULE-SET,Private,DIRECT
  - RULE-SET,Pter,DIRECT
  - RULE-SET,Reject,REJECT
  - RULE-SET,Icloud,DIRECT
  - RULE-SET,Apple,DIRECT
  - RULE-SET,Google,DIRECT
  - RULE-SET,Proxy,PROXY
  - RULE-SET,Direct,DIRECT
  - RULE-SET,Telegramcidr,PROXY
  - RULE-SET,BanAD,REJECT
  - MATCH,DIRECT
```

## 致谢

- [@Loyalsoldier/v2ray-rules-dat](https://github.com/Loyalsoldier/v2ray-rules-dat)
- [@Loyalsoldier/cn-blocked-domain](https://github.com/Loyalsoldier/cn-blocked-domain)
- [@gfwlist/gfwlist](https://github.com/gfwlist/gfwlist)
- [@v2fly/domain-list-community](https://github.com/v2fly/domain-list-community)
- [@felixonmars/dnsmasq-china-list](https://github.com/felixonmars/dnsmasq-china-list)
- [@17mon/china_ip_list](https://github.com/17mon/china_ip_list)
- [@Loyalsoldier/clash-rules](https://github.com/Loyalsoldier/clash-rules)
- [@ACL4SSR/ACL4SSR](https://github.com/ACL4SSR/ACL4SSR/tree/master)
