---
title: 用于简单 URL 的 DNS Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 摘要：实施 DNS 记录之前，请查看本主题中的简单 URL 注意事项Skype for Business Server。
ms.openlocfilehash: d638ff2d3d1b89deaad90c054698692e70ffaae7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777912"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a>用于简单 URL 的 DNS Skype for Business Server

**摘要：** 实施 DNS 记录之前，请查看本主题中的简单 URL 注意事项Skype for Business Server。

简单 URL 使用户更容易加入会议，并且使管理员Skype for Business Server访问管理工具。 简单 URL 使用其自己的域，该域不能匹配您定义的任何 SIP 域。 

Skype for Business Server以下三个简单的 URL：会议、拨入和管理。您需要设置会议简单 URL 和拨入简单 URL，并且管理简单 URL 是可选的。 支持简单 URL 所需的域名系统 (DNS) 记录取决于定义这些简单 URL 的方式以及是否要对简单 URL 支持灾难恢复。 

## <a name="simple-url-scope"></a>简单 URL 范围

可以将简单 URL 配置为具有 global 作用域，也可以为组织中的每个中央站点指定不同的简单 URL。如果同时指定全局简单 URL 和站点简单 URL，则站点简单 URL 具有优先权。 

在大多数情况下，我们建议您仅在全局级别设置简单 URL，以便用户的会议简单 URL 在从一个网站移动到另一个网站时不会更改。 例外情况是对于不同站点的拨入用户需要使用不同电话号码的组织。 请注意，如果要将某个站点上的一个简单 URL（如拨入简单 URL）设置为站点级别的简单 URL，您还必须将该站点上的其他简单 URL 设置为站点级别。

可以在拓扑生成器中设置全局简单 URL。 若要在网站级别设置简单 URL，请使用 Set-CsSimpleURLConfiguration cmdlet。

定义简单 URL 还需要在 DNS 配置中设置 A 和/或 AAAA 记录。

## <a name="simple-url-naming-and-validation-rules"></a>简单 URL 命名和验证规则
<a name="BK_Valid"> </a>

拓扑生成器和Skype for Business Server命令行管理程序 cmdlet 对简单 URL 强制执行多个验证规则。 您必须设置会议简单 URL 和拨入简单 URL，但可以选择设置管理简单 URL。 每个 SIP 域都必须具有单独的会议简单 URL，但整个组织只需要一个拨入简单 URL 和一个管理简单 URL。

您组织的每个简单 URL 必须具有唯一的名称，并且不能是另一个简单 URL (例如，您不能设置为会议简单 URL 和 Dialin 简单 `SfB2015.contoso.com/Meet` `SfB2015.contoso.com/Meet/Dialin` URL) 。 简单 URL 名称不能包含任何池的 FQDN，也不能包含任何端口 (例如，不允许任何 https://FQDN:88/meet 端口) 。 所有简单 URL 都必须以 https:// 前缀开头。 

简单 URL 只能包含字母数字字符（即，a-z、A-Z、0-9 和圆点 (.)）。如果使用其他字符，则简单 URL 可能不会正常工作。

## <a name="changing-simple-urls-after-deployment"></a>部署后更改简单 URL
<a name="BK_Valid"> </a>

如果在初始部署后更改简单 URL，您必须注意更改如何影响简单 URL 的 DNS 记录和证书。 如果简单 URL 的基础发生更改，则还必须更改 DNS 记录和证书。 例如，从 更改为 将基 URL 从 更改为 ，因此你需要将 `https://SfB2015.contoso.com/Meet` DNS 记录和证书更改为 引用 `https://meet.contoso.com` `SfB2015.contoso.com` `meet.contoso.com` `meet.contoso.com` 。 如果将简单 URL 从 更改为 ，则 基 URL 保持不变，因此不需要 `https://SfB2015.contoso.com/Meet` `https://SfB2015.contoso.com/Meetings` 更改 DNS `SfB2015.contoso.com` 或证书。

但是，只要更改简单 URL 名称，就必须在每个控制器和前端服务器上运行 **Enable-CsComputer** 以注册更改。

## <a name="naming-examples-for-simple-urls"></a>简单 URL 的命名示例
<a name="BK_Valid"> </a>

有三种推荐的选项可用于命名简单 URL。您选择的选项会暗示设置支持简单 URL 的 DNS A 记录和证书的方式。在每个选项中，您必须为组织中的每个 SIP 域配置一个会议简单 URL。 

无论具有多少个 SIP 域，整个组织始终只需要一个拨入简单 URL 和一个管理简单 URL。

在选项 1 中，为每个简单 URL 创建新的 SIP 域名。

如果使用此选项，则需要为每个简单 URL 配置单独的 DNS A 记录，而且必须在证书中命名每个会议简单 URL。

**简单 URL 命名选项 1**


| **简单 URL** <br/> | **示例** <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | `https://meet.contoso.com``https://meet.fabrikam.com`、、等 (组织中每个 SIP 域一)   <br/> |
| 拨入  <br/>       | `<https://dialin.contoso.com>`  <br/>                                                                                  |
| 管理员  <br/>         | `<https://admin.contoso.com>`  <br/>                                                                                   |

在选项 2 中，简单 URL 基于域名 `SfB2015.contoso.com` 。 因此，只需一个可启用全部三种类型简单 URL 的 DNS A 记录。 此 DNS A 记录引用 `SfB2015.contoso.com` 。 此外，仍需要为组织中的其他 SIP 域配置单独的 DNS A 记录。 

**简单 URL 命名选项 2**


| **简单 URL** <br/> | **示例** <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | `https://SfB2015.contoso.com/Meet``https://SfB2015.fabrikam.com/Meet`、、等 (组织中每个 SIP 域一)   <br/> |
| 拨入  <br/>       | `<https://SfB2015.contoso.com/Dialin>`  <br/>                                                                                          |
| 管理员  <br/>         | `<https://SfB2015.contoso.com/Admin>`  <br/>                                                                                           |

如果具有许多 SIP 域，并且希望每个 SIP 域具有单独的会议简单 URL，但希望最大程度地减少这些简单 URL 所要求的 DNS 记录和证书，则选项 3 是最有用的。 

**简单 URL 命名选项 3**


| **简单 URL** <br/> | **示例** <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | `<https://SfB2015.contoso.com/contosoSIPdomain/Meet>`  <br/> `<https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>`  <br/> |
| 拨入  <br/>       | `<https://SfB2015.contoso.com/Dialin>`  <br/>                                                                            |
| 管理员  <br/>         | `<https://SfB2015.contoso.com/Admin>`  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a>简单 URL 的灾难恢复选项
<a name="BK_Valid"> </a>

如果有多个站点包含前端池，并且 DNS 提供程序支持 GeoDNS，您可以为简单 URL 设置 DNS 记录以支持灾难恢复，以便即使整个前端池关闭，简单 URL 功能也将继续运行。 此灾难恢复功能支持“会议”和“拨入”简单 URL。

若要进行此配置，请创建两个 GeoDNS 地址。每个地址具有两个 DNS A 或 CNAME 记录，这些记录解析到出于灾难恢复目的配对在一起的两个池。一个 GeoDNS 地址用于内部访问，并解析到两个池的内部 Web FQDN 或负载平衡器 IP 地址。另一个 GeoDNS 地址用于外部访问，并解析到两个池的外部 Web FQDN 或负载平衡器 IP 地址。下面是使用池的 FQDN 的“会议”简单 URL 的示例。 

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

然后创建可解析会议简单 URL 的 CNAME (例如) `meet.contoso.com` 两个 GeoDNS 地址。

> [!NOTE]
> 如果您的网络使用发夹（通过外部链接路由所有简单 URL 通信，包括来自您组织内部的通信），您可以只配置外部 GeoDNS 地址并将“会议”简单 URL 仅解析到该外部地址。

使用此方法时，您可以将每个 GeoDNS 地址配置为使用循环方法向两个池分发请求，或主要连接到一个池（如地理位置上接近的池）并仅在连接失败的情况下使用另一个池。 

您可以对“拨入”简单 URL 设置相同的配置。 为此，请创建与上例中类似的其他记录，在 DNS 记录中  `dialin` `meet` 代之以 。 对于“管理”简单 URL，请使用本节前面所列的三个选项之一。

设置完此配置后，您必须使用监控应用程序来设置 HTTP 监控以留意故障。 对于外部访问，请监视以确保 HTTPS GET lyncdiscover。<sipdomain> 对两个池的外部 Web FQDN 或负载平衡器 IP 地址的请求成功。 例如，以下请求不得包含任何 **ACCEPT** 标头且必须返回 **200 OK**。

```console
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

对于内部访问，您必须监控两个池的内部 Web FQDN 或负载平衡器 IP 地址上的端口 5061。 如果检测到任何连接故障，则这些池的 VIP 必须关闭端口 80、443 和 4443。


