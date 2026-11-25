# AdBlock List

[![Update Filters](https://github.com/olkiolki/adblock_list/actions/workflows/auto-update.yml/badge.svg)](https://github.com/olkiolki/adblock_list/actions/workflows/auto-update.yml)
[![License](https://img.shields.io/github/license/olkiolki/adblock_list)](./LICENSE)

整合多来源广告过滤规则，自动去重、转换格式，定时更新。

规则由 [fordes123/ad-filters-subscriber](https://github.com/fordes123/ad-filters-subscriber) 生成，
本仓库维护规则源清单（[`config/application.yaml`](config/application.yaml)）与私有补充规则（[`inputs/private.txt`](inputs/private.txt)）。

> **产物发布在 `release` 分支**，不是 `main`。`main` 只存放生成器与配置。

---

## 订阅地址

按你使用的工具选择**一个**即可，不要重复添加。

| 文件 | 格式 | 适用工具 |
|:--|:--|:--|
| [`dns.txt`](../../raw/release/dns.txt) | AdGuard DNS 规则 | **AdGuard Home** / 基于 DNS 的过滤 |
| [`adblock.txt`](../../raw/release/adblock.txt) | uBlock 语法 | **uBlock Origin** / AdGuard / AdBlock Plus |
| [`hosts.txt`](../../raw/release/hosts.txt) | hosts | **AdAway** / 系统 hosts / 路由器 |
| [`dnsmasq.txt`](../../raw/release/dnsmasq.txt) | dnsmasq conf | 路由器 dnsmasq |
| [`smartdns.txt`](../../raw/release/smartdns.txt) | SmartDNS | SmartDNS |
| [`clash.yaml`](../../raw/release/clash.yaml) | mihomo rule-provider | **Clash / mihomo** |
| [`sing-box.json`](../../raw/release/sing-box.json) | sing-box rule-set | **sing-box** |

直连地址格式：

```
https://raw.githubusercontent.com/olkiolki/adblock_list/release/<文件名>
```

加速镜像（第三方服务，可用性无保证，失效请改用直连）：

```
https://gh-proxy.com/https://raw.githubusercontent.com/olkiolki/adblock_list/release/<文件名>
```

> `jsDelivr` 不适用于本仓库：`adblock.txt` 等文件超过其 20 MB 单文件上限。

## 如何使用

<details>
<summary><b>AdGuard Home</b></summary>

过滤器 → DNS 黑名单 → 添加黑名单 → 粘贴 `dns.txt` 地址。
</details>

<details>
<summary><b>uBlock Origin</b></summary>

设置 → 过滤器列表 → 导入 → 粘贴 `adblock.txt` 地址。
</details>

<details>
<summary><b>AdGuard（软件 / 扩展）</b></summary>

过滤器 → 自定义过滤器 → 添加自定义过滤器 → 粘贴 `adblock.txt` 地址。
</details>

<details>
<summary><b>AdAway</b></summary>

hosts 源 → 添加 → 粘贴 `hosts.txt` 地址。
</details>

<details>
<summary><b>Clash / mihomo</b></summary>

在 `rule-providers` 中引用 `clash.yaml`，`behavior` 设为 `domain`。
</details>

<details>
<summary><b>sing-box</b></summary>

在 `route.rule_set` 中以 `remote` 类型引用 `sing-box.json`，`format` 为 `source`。
</details>

## 规则来源

共 16 个上游来源 + 2 个本仓库私有规则，完整链接见 [`config/application.yaml`](config/application.yaml)。

<details>
<summary>展开查看</summary>

| 来源 | 类型 |
|:--|:--|
| [AdGuard Base filter](https://github.com/AdguardTeam/FiltersRegistry) | filter |
| [AdGuard Chinese filter](https://github.com/AdguardTeam/FiltersRegistry) | filter |
| [AdGuard Mobile Ads filter](https://github.com/AdguardTeam/AdguardFilters) | filter |
| [AdGuard DNS filter](https://github.com/AdguardTeam/AdGuardSDNSFilter) | filter |
| [AdRules DNS List](https://github.com/Cats-Team/AdRules) | filter |
| [CJX's Annoyance List](https://github.com/cjx82630/cjxlist) | filter |
| [EasyList](https://easylist.to/) | filter |
| [EasyList China](https://easylist.to/) | filter |
| [EasyPrivacy](https://easylist.to/) | filter |
| [xinggsf mv filter](https://github.com/xinggsf/Adblock-Plus-Rule) | filter |
| [jiekouAD](https://github.com/damengzhu/banad) | filter |
| [AWAvenue Ads Rule](https://github.com/TG-Twilight/AWAvenue-Ads-Rule) | dns |
| [DNS-Blocklists PRO mini](https://github.com/hagezi/dns-blocklists) | dns |
| [OISD Basic](https://oisd.nl/) | dns |
| [StevenBlack hosts](https://github.com/StevenBlack/hosts) | hosts |
| [Pollock hosts](https://someonewhocares.org/hosts/) | hosts |
| `inputs/private-adblock.txt` | 私有 |
| `inputs/private-hosts.txt` | 私有 |

</details>

选源原则：只收录仍在维护、误杀率低的清单。已排除 anti-AD、yhosts、Notracking（停更）、
ADgk、SmartTV Blocklist、1024 hosts、ad-wars hosts（长期未更新）、NEO DEV HOST、
xinggsf rule、1Hosts Lite、Hblock（误杀较多）。

> 私有规则按语法分为两个文件：`private-adblock.txt` 放 `||域名^`、`@@`、`##` 等过滤语法，
> `private-hosts.txt` 放 `0.0.0.0` / `::1` 形式的 hosts 条目。**两者不可混写**，
> 否则与声明的 `type` 不符的条目会被静默丢弃。

## 更新机制

- GitHub Actions 定时抓取全部输入源，去重后一次性生成所有格式。
- 产物强制推送到 `release` 分支，**该分支始终只有一个提交**，历史不累积。
- `main` 分支只保留生成器源码与配置，体积恒定。

## 维护

- 增删规则源：编辑 `config/application.yaml` 的 `input` 列表。
- 添加私有规则：编辑 `inputs/private.txt`（**不能**放进 `rule/`，那是输出目录）。
- 手动重新生成：Actions → **Update Filters** → Run workflow。
- 本地验证需 JDK 25：`./gradlew shadowJar` 后用 `adfs -c config/application.yaml` 运行。

## 免责声明

规则来自公开上游项目，本仓库仅做整合与格式转换，不对拦截效果与误杀负责。
如遇正常站点被拦截，请提交 Issue 并附上域名。

## License

[MIT](./LICENSE)
