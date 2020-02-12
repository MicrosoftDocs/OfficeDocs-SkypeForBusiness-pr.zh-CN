---
title: Skype for Business 服务器中的简单 Url 的 DNS 要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 摘要：在为 Skype for business 服务器实施 DNS 记录之前，请查看本主题中的简单 URL 注意事项。
ms.openlocfilehash: 3296e3678d1d38f021b792a2362f61de66796d0f
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888471"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a>Skype for Business 服务器中的简单 Url 的 DNS 要求

**摘要：** 在为 Skype for Business 服务器实施 DNS 记录之前，请查看本主题中的简单 URL 注意事项。

简单的 Url 使你的用户加入会议更容易，并且让管理员可以更轻松地访问 Skype for Business 服务器管理工具。 简单 Url 使用其自己的域，这些域必须与你定义的任何 SIP 域不匹配。 

Skype for Business 服务器支持以下三个简单的 Url： "开会"、"拨入" 和 "管理员"。您需要为 "满足" 和 "拨入" 设置简单的 Url，"管理员简单 URL" 是可选的。 需要支持简单 Url 的域名系统（DNS）记录取决于你定义这些简单 Url 的方式，以及你是否希望支持简单 Url 的灾难恢复。 

## <a name="simple-url-scope"></a>简单的 URL 范围

你可以将简单 Url 配置为具有全局范围，或者你可以为你的组织中的每个中心网站指定不同的简单 Url。 如果同时指定了全局简单 url 和网站简单 URL，则网站简单 URL 优先。 

在大多数情况下，我们建议你仅在全局级别设置简单的 Url，以便用户的 "满足简单 URL" 从一个网站移动到另一个网站时不会更改。 例外情况是需要对不同站点上的电话拨入用户使用不同电话号码的组织。 请注意，如果在网站上将一个简单的 URL （如拨入式简单 URL）设置为网站级简单 URL，则还必须将该网站上的其他简单 Url 设置为网站级别。

可以在拓扑生成器中设置全局简单的 Url。 若要在网站级别设置简单的 URL，请使用 CsSimpleURLConfiguration cmdlet。

定义简单的 URL 还需要在 DNS 配置中设置 A 和/或 AAAA 记录。

## <a name="simple-url-naming-and-validation-rules"></a>简单的 URL 命名和验证规则
<a name="BK_Valid"> </a>

拓扑生成器和 Skype for Business Server Management Shell cmdlet 针对你的简单 Url 强制执行几条验证规则。 您需要为 "满足" 和 "拨入" 设置简单的 Url，但为 "管理员" 设置一个是可选的。 每个 SIP 域都必须具有单独的 "匹配" 的 "匹配" 简单 URL，但对于整个组织，只需一个拨入简单的 url 和一个管理员简单的 URL。

组织中的每个简单 URL 都必须具有唯一的名称，并且不能是另一个简单 URL 的前缀（例如，不能将 SfB2015.contoso.com/Meet 设置为您的 "满足简单 url" 和 "SfB2015.contoso.com/Meet/Dialin" 作为拨入简单 URL）。 简单的 URL 名称不能包含任何池的 FQDN，也不能包含任何端口信息（例如https://FQDN:88/meet ，不允许）。 所有简单的 Url 必须以 https://前缀开头。 

简单 Url 只能包含字母数字字符（即 a-z、a-z、0-9 和句号（.）。 如果使用其他字符，则简单 Url 可能不会按预期工作。

## <a name="changing-simple-urls-after-deployment"></a>在部署后更改简单的 Url
<a name="BK_Valid"> </a>

如果你在初始部署后更改简单的 URL，你必须知道更改对简单 Url 的 DNS 记录和证书有何影响。 如果简单 URL 的基础发生更改，则您还必须更改 DNS 记录和证书。 例如，从https://SfB2015.contoso.com/Meet https://meet.contoso.com SfB2015.contoso.com 更改为 meet.contoso.com 的基本 URL，因此你需要更改 DNS 记录和证书才能引用 meet.contoso.com。 如果将简单 URL 更改https://SfB2015.contoso.com/Meet为 "与https://SfB2015.contoso.com/Meetings"，SfB2015.contoso.com 的基 url 保持不变，因此不需要任何 DNS 或证书更改。

但是，当您更改简单的 URL 名称时，必须在每个 Director 和前端服务器上运行**Enable-CsComputer**以注册更改。

## <a name="naming-examples-for-simple-urls"></a>简单 Url 的命名示例
<a name="BK_Valid"> </a>

有三个推荐选项可用于命名简单 Url。 选择哪个选项对您设置 DNS A 记录和支持简单 Url 的证书有何影响。 在每个选项中，必须为组织中的每个 SIP 域配置一个 "满足简单 URL"。 

你始终只需要在整个组织中使用一个简单的 URL 进行拨入，一个用于管理，无论你拥有多少个 SIP 域。

在选项1中，为每个简单的 URL 创建一个新的 SIP 域名。

如果使用此选项，则每个简单 URL 都需要一个单独的 DNS A 记录，并且每个 "满足简单 URL" 都必须在证书中命名。

**简单的 URL 命名选项1**


| **简单的 URL** <br/> | **示例** <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| 会议  <br/>          | https://meet.contoso.com， https://meet.fabrikam.com等等（组织中的每个 SIP 域一个）  <br/> |
| 拨入  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| Iis  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

通过选项2，简单 Url 基于域名 SfB2015.contoso.com。 因此，只需一个 DNS A 记录即可启用所有三种类型的简单 Url。 此 DNS A 记录引用 SfB2015.contoso.com。 此外，你的组织中的其他 SIP 域仍需要单独的 DNS A 记录。 

**简单的 URL 命名选项2**


| **简单的 URL** <br/> | **示例** <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| 会议  <br/>          | https://SfB2015.contoso.com/Meet， https://SfB2015.fabrikam.com/Meet等等（组织中的每个 SIP 域一个）  <br/> |
| 拨入  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| Iis  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

如果你有多个 SIP 域，而你希望它们具有单独的符合简单的 Url，但希望尽量减少这些简单 Url 的 DNS 记录和证书要求，则选项3非常有用。 

**简单的 URL 命名选项3**


| **简单的 URL** <br/> | **示例** <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| 会议  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| 拨入  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| Iis  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a>简单 Url 的灾难恢复选项
<a name="BK_Valid"> </a>

如果你有多个包含前端池的网站，并且 DNS 提供程序支持 GeoDNS，你可以为简单的 Url 设置 DNS 记录以支持灾难恢复，以便即使一个完整的前端池停止运行，简单的 URL 功能也会继续。 此灾难恢复功能支持 "开会" 和 "拨入" 简单 Url。

若要配置此设置，请创建两个 GeoDNS 地址。 每个地址都有两个 DNS A 或 CNAME 记录，它们可解析为两个池，这些记录结合在一起以供灾难恢复之用。 一个 GeoDNS 地址用于内部访问，并解析为两个池的内部 web FQDN 或负载平衡器 IP 地址。 其他 GeoDNS 地址用于外部访问，并解析为两个池的外部 web FQDN 或负载平衡器 IP 地址。 下面是使用池的 Fqdn 的 "满足简单 URL" 的示例。 

```console
Meet-int.geolb.contoso.com
     Pool1InternalWebFQDN.contoso.com
     Pool2InternalWebFQDN.contoso.com
```

```console
Meet-ext.geolb.contoso.com
     Pool1ExternalWebFQDN.contoso.com
     Pool2ExternalWebFQDN.contoso.com
```

然后，创建将您的 "满足简单 URL" （如 meet.contoso.com）解析为两个 GeoDNS 地址的 CNAME 记录。

> [!NOTE]
> 如果你的网络使用 hairpinning （通过外部链接路由所有简单的 URL 流量，包括来自组织内部的流量），则只需配置外部 GeoDNS 地址并将你的 "仅限" 简单 URL 解析为仅外部地址。

使用此方法时，你可以将每个 GeoDNS 地址配置为使用循环复用方法将请求分配到两个池，或主要连接到一个池（如位于地理位置较近的池），并使用另一个池（仅限情况连接失败。 

你可以为拨入式简单 URL 设置相同配置。 若要执行此操作，请创建如前面的示例中所示`dialin`的`meet`其他记录，并在 DNS 记录中替换。 对于 "管理员简单 URL"，请使用本节前面列出的三个选项之一。

设置此配置后，必须使用监视应用程序设置 HTTP 监视以监视失败。 对于外部访问，请进行监视以确保 HTTPS 获取 lyncdiscover。<sipdomain> 对两个池的外部 web FQDN 或负载平衡器 IP 地址的请求成功。 例如，以下请求不得包含任何**ACCEPT**标头，并且必须返回**200 OK**。

```console
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

对于内部访问，你必须在两个池的内部 web FQDN 或负载平衡器 IP 地址上监视端口5061。 如果检测到任何连接失败，这些池的 VIP 必须关闭端口80、443和4443。


