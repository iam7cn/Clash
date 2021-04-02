## 简介

---

本目录中Clash 规则的配置文件。

### 说明 

---

# 配置文件

Clash 运行的依据是规则文件，系统会内置一个默认的规则文件，你只需要填写其他诸如服务器信息即可使用。不过实际情况需要分两种情况讨论。

第一，服务提供商提供了 Clash 的“订阅链接”；

​        你可以直接用订阅链接代理上网

第二，服务提供商没有提供 Clash 的“订阅链接”。

​         我们可以通过在线转换工具转成 Clash 支持的订阅链接。

​         [Subscription Converter (wcc.best)](https://sub-web.wcc.best/)

​         比如这个转换工具

你也可以手动修正配置例子见  [Config.yml](https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/Profiles/config.yml)

如果你觉得太复杂可以使用 [mini.yml](https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/Profiles/mini.yml)

测试配置 https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/Profiles/test.yaml 



配合目前很流行的ProxyPool项目 [@zu1k/ProxyPool](https://github.com/zu1k/proxypool) 和 [@sansui233/proxypool](https://github.com/sansui233/proxypool)

#### Proxy-Providers 配置方式

```yaml
proxy-providers:
  sub:
    type: http
    url: "https://cdn.jsdelivr.net/gh/iam7cn/Clash@main/Profiles/sub.list" # 替换自己的节点
    interval: 3600
    path: xiao7/sub.yaml
    health-check:
      enable: true
      interval: 600
      url: http://www.gstatic.com/generate_204
```

您只需修改url中的地址就行

提供几个ProxyPool搭建的代理池

[KingFu景福 https://free.kingfu.cf](https://free.kingfu.cf/)

[碧海免费节点池 (bihai.cf)](https://bihai.cf/)

[Free Proxies (proxypoolss.tk)](https://proxypoolss.tk)

[Free Proxies (proxypoolsstest.herokuapp.com)](https://proxypoolsstest.herokuapp.com/)

[hm2019721.ml](https://hm2019721.ml/)

[fq.lonxin.net](https://fq.lonxin.net/)

[proxypool.ednovas.xyz](https://proxypool.ednovas.xyz/)

[sspool.herokuapp.com](https://sspool.herokuapp.com/)

# 客户端的使用


