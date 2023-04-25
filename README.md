## AbBlock List

广告过滤规则整合，使用 [fordes123/ad-filters-subscriber](https://github.com/fordes123/ad-filters-subscriber) 定时更新
> AdGuard客户端(软件、扩展)、AdBlock、AdBlockPlus、uBlock Origin 推荐使用：`all.txt`</br>
> AdGuardHome 推荐使用：`dns.txt`</br>
> AdAway 等其他仅支持 hosts 的工具，推荐使用：`hosts.txt`

| 名称            | 说明                                                                   |                                       Github                                       |                                                ghproxy                                                 |
|---------------|:---------------------------------------------------------------------|:----------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------:|
| `all.txt`     | 去重的规则合集，包含`DOMAIN`、`REGEX`、`MODIFY`、`HOSTS`，适用于 `AdGuard`、`AdBlock`等 |  [Link](https://raw.githubusercontent.com/xndeye/adblock_list/main/rule/all.txt)   |  [Link](https://ghproxy.com/https://raw.githubusercontent.com/xndeye/adblock_list/main/rule/all.txt)   |
| `dns.txt`     | 包含 `DOMAIN`、`REGEX`、`HOSTS`规则，适用于`AdGuardHome` 等基于DNS的过滤工具           |  [Link](https://raw.githubusercontent.com/xndeye/adblock_list/main/rule/dns.txt)   |  [Link](https://ghproxy.com/https://raw.githubusercontent.com/xndeye/adblock_list/main/rule/dns.txt)   |
| `domain.txt`  | `DOMAIN` 域名规则，仅完整域名                                                 | [Link](https://raw.githubusercontent.com/xndeye/adblock_list/main/rule/domain.txt) | [Link](https://ghproxy.com/https://raw.githubusercontent.com/xndeye/adblock_list/main/rule/domain.txt) |
| `hosts.txt`   | `HOSTS` 规则，适用于几乎所有设备                                             | [Link](https://raw.githubusercontent.com/xndeye/adblock_list/main/rule/hosts.txt)  | [Link](https://ghproxy.com/https://raw.githubusercontent.com/xndeye/adblock_list/main/rule/hosts.txt)  |
| `modify.txt`  | `MODIFY` 修饰规则，添加了一些修饰符号的规则，AdG支持, `modify.txt` + `dns.txt` = `all.txt`                | [Link](https://raw.githubusercontent.com/xndeye/adblock_list/main/rule/modify.txt) | [Link](https://ghproxy.com/https://raw.githubusercontent.com/xndeye/adblock_list/main/rule/modify.txt) |
| `private.txt` | 由本仓库维护的私有规则，主要是对上游规则的补充                                              | [Link](https://raw.githubusercontent.com/xndeye/adblock_list/main/rule/private.txt) | [Link](https://ghproxy.com/https://raw.githubusercontent.com/xndeye/adblock_list/main/rule/private.txt) |
| `regex.txt`   | `REGEX` 正则规则，包含正则的域名规则，AdGH支持                                                 | [Link](https://raw.githubusercontent.com/xndeye/adblock_list/main/rule/regex.txt) | [Link](https://ghproxy.com/https://raw.githubusercontent.com/xndeye/adblock_list/main/rule/regex.txt) |

<details>
<summary>点击查看上游规则</summary>
<ul>
    <li><a href="https://raw.githubusercontent.com/AdguardTeam/FiltersRegistry/master/filters/filter_2_Base/filter.txt">AdGuard 基础过滤器</a></li>
    <li><a href="https://raw.githubusercontent.com/AdguardTeam/FiltersRegistry/master/filters/filter_11_Mobile/filter.txt">AdGuard 移动广告过滤器</a></li>
    <li><a href="https://adguard.com/kb/zh-CN/general/ad-filtering/adguard-filters/">AdGuard 防跟踪保护过滤器</a></li>
    <li><a href="https://raw.githubusercontent.com/AdguardTeam/FiltersRegistry/master/filters/filter_17_TrackParam/filter.txt">AdGuard URL跟踪过滤器</a></li>
    <li><a href="https://raw.githubusercontent.com/AdguardTeam/FiltersRegistry/master/filters/filter_4_Social/filter.txt">AdGuard 社交媒体过滤器</a></li>
    <li><a href="https://raw.githubusercontent.com/AdguardTeam/FiltersRegistry/master/filters/filter_14_Annoyances/filter.txt">AdGuard 恼人广告过滤器</a></li>
    <li><a href="https://raw.githubusercontent.com/AdguardTeam/FiltersRegistry/master/filters/filter_10_Useful/filter.txt">AdGuard 解除搜索广告和自我推销过滤器</a></li>
    <li><a href="https://raw.githubusercontent.com/AdguardTeam/FiltersRegistry/master/filters/filter_224_Chinese/filter.txt">AdGuard 中文过滤器</a></li>
    <li><a href="https://adaway.org/hosts.txt">AdAway Default Blocklist</a></li>
    <li><a href="https://raw.githubusercontent.com/crazy-max/WindowsSpyBlocker/master/data/hosts/spy.txt">WindowsSpyBlocker</a></li>
    <li><a href="https://github.com/jdlingyu/ad-wars">ad-wars(大圣净化)</a></li>
    <li><a href="https://github.com/TG-Twilight/AWAvenue-Adblock-Rule">AWAvenue-Adblock-Rule</a></li>
    <li><a href="https://github.com/sbwml/halflife-list">halflife-list</a></li>

</ul>
</details>
