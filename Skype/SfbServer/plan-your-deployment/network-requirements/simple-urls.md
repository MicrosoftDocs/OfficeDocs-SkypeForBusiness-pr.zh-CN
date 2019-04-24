---
title: Skype 中的简单 url 的业务服务器的 DNS 要求
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 摘要： DNS 记录的 Skype 实现业务服务器之前查看本主题中的简单 URL 注意事项。
ms.openlocfilehash: 1fffb1303381797a800a235d3965fe387e4d8eb2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213800"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a>Skype 中的简单 url 的业务服务器的 DNS 要求

**摘要：** DNS 记录的 Skype 实现业务服务器之前查看本主题中的简单 URL 注意事项。

简单 Url 使您的用户更易于加入会议，又便于到 Skype 业务 Server 管理工具的管理员。 简单 Url 使用自己的域，该域不匹配任何您定义的 SIP 域。 

Skype 业务 server 支持以下三种简单 Url： 满足，电话拨入式，和管理员。您需要设置为开会会议和电话拨入简单 Url 也是可选的管理简单 URL。 支持简单 Url 所需的域名系统 (DNS) 记录取决于您如何定义这些简单 Url，以及是否希望以支持的简单 Url 的灾难恢复。 

## <a name="simple-url-scope"></a>简单 URL 作用域

您可以配置简单 Url 具有全局范围，或者您可以在组织中指定不同的简单 Url 的每个中央站点。 如果指定全局简单 URL 和网站的简单 URL，该网站的简单 URL 优先级。 

在大多数情况下，我们建议将简单 Url 设置仅在全局级别，以便如果他们从一个网站移动到另一个用户的会议简单 URL 不会更改。 异常采用不同的电话号码用于电话拨入式用户在不同的站点所需要的组织。 请注意，是否在网站级别的简单 URL 网站设置一个简单 URL （如的电话拨入式简单 URL)，还必须设置其他简单 Url 以及为网站级别的站点。

在拓扑生成器中，您可以设置全局简单 Url。 要在网站级别设置的简单 URL，请使用集 CsSimpleURLConfiguration cmdlet。

定义简单 URL 还将需要在您的 DNS 配置设置的 A 和/或 AAAA 记录。

## <a name="simple-url-naming-and-validation-rules"></a>简单 URL 命名和验证规则
<a name="BK_Valid"> </a>

拓扑生成器和业务 Server Management Shell cmdlet Skype 强制几个有效性规则的简单 Url。 您需要为 Meet 和 Dialin，设置简单 Url，但设置另一个用于管理是可选的。 每个 SIP 域必须单独的会议简单 URL，但您需要为整个组织只有一个 Dialin 简单 URL 和一个管理简单 URL。

您的组织中每个简单 URL 必须具有唯一名称，并且不能是另一个简单 URL 的前缀 （例如，您无法设置为会议的简单 URL 的 SfB2015.contoso.com/Meet 和 SfB2015.contoso.com/Meet/Dialin 为您的拨入简单 URL）。 简单 URL 名称不能包含任何池，或任何端口信息的 FQDN (例如，https://FQDN:88/meet不允许)。 所有简单 Url 必须以前缀 https:// 开头。 

简单 Url 只能包含字母数字字符 （即，a-z、 A-Z、 0-9 和句点 （.）。 如果您使用其他字符，简单 Url 可能未按预期。

## <a name="changing-simple-urls-after-deployment"></a>在部署后更改简单 Url
<a name="BK_Valid"> </a>

如果在初始部署后更改简单 URL，您必须知道如何更改会影响您的 DNS 记录和证书的简单 Url。 如果简单 URL 的更改，则必须更改的 DNS 记录和证书以及。 例如，从更改https://SfB2015.contoso.com/Meet到https://meet.contoso.com的基 URL 从变为 SfB2015.contoso.com meet.contoso.com，因此需要更改 DNS 记录和证书来引用 meet.contoso.com。 如果您已经更改中的简单 URLhttps://SfB2015.contoso.com/Meet到https://SfB2015.contoso.com/Meetings、 基 URL 的 SfB2015.contoso.com 保持不变，因此没有 DNS 或所需证书的更改。

无论何时更改简单 URL 名称，但是，必须以注册该更改每台控制器和前端服务器上运行**Enable-cscomputer** 。

## <a name="naming-examples-for-simple-urls"></a>简单 url 命名示例
<a name="BK_Valid"> </a>

有三个命名简单 Url 的建议的选项。 选择哪个选项有如何设置您的 DNS A 记录和证书支持简单 Url 的影响。 在每个选项，必须在组织中配置一个会议的简单 URL，每个 SIP 域。 

始终需要只有一个简单 URL 中的电话拨入式，为整个组织和一个管理，无论您有多少个 SIP 域。

在选项 1 中，您将创建每个简单 URL 的新 SIP 域名。

如果使用此选项，则需要一个单独的 DNS A 记录，必须在证书中命名每个简单 URL 和每个会议简单 URL 的。

**简单 URL 命名选项 1**


| **简单 URL** <br/> | **示例** <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| 满足  <br/>          | https://meet.contoso.comhttps://meet.fabrikam.com，依此类推 （一个为组织中每个 SIP 域）  <br/> |
| 拨入  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| 管理  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

选项 2 简单 Url 基于 SfB2015.contoso.com 的域名。 因此，您需要使所有三种类型的简单 Url 只有一个 DNS A 记录。 此 DNS A 记录引用 SfB2015.contoso.com。 此外，您仍需要单独的 DNS A 记录的其他 SIP 域中您的组织。 

**简单 URL 命名选项 2**


| **简单 URL** <br/> | **示例** <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| 满足  <br/>          | https://SfB2015.contoso.com/Meethttps://SfB2015.fabrikam.com/Meet，依此类推 （一个为组织中每个 SIP 域）  <br/> |
| 拨入  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| 管理  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

如果您具有多个 SIP 域，并希望其具有单独的会议简单 Url，但希望大程度地减少这些简单 Url 的 DNS 记录和证书要求选项 3 最为有用。 

**简单 URL 命名选项 3**


| **简单 URL** <br/> | **示例** <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| 满足  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| 拨入  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| 管理  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a>简单 Url 的灾难恢复选项
<a name="BK_Valid"> </a>

如果您有多个站点包含前端池的 DNS 提供程序支持 GeoDNS，您可以设置以支持灾难恢复的简单 Url 的 DNS 记录，以便简单 URL 功能仍即使一个整个前端池不可用。 此灾难恢复功能支持 Meet 和电话拨入式简单 Url。

若要配置该，创建两个 GeoDNS 地址。 每个地址具有两个解析为其用于灾难恢复目的成对出现两个池的 DNS A 或 CNAME 记录。 一个 GeoDNS 地址用于内部访问权限，并且将解析为内部 web FQDN 或负载平衡器 IP 地址的两个池。 用于外部访问的其他 GeoDNS 地址并且将解析为的外部 web FQDN 或负载平衡器 IP 地址的两个池。 下面是一个有关会议的简单 URL，并使用的池的 Fqdn 示例。 

```
Meet-int.geolb.contoso.com
     Pool1InternalWebFQDN.contoso.com
     Pool2InternalWebFQDN.contoso.com
```

```
Meet-ext.geolb.contoso.com
     Pool1ExternalWebFQDN.contoso.com
     Pool2ExternalWebFQDN.contoso.com
```

然后，创建您会议简单 URL （如 meet.contoso.com) 解析到两个 GeoDNS 地址的 CNAME 记录。

> [!NOTE]
> 如果您的网络使用 hairpinning （路由通过外部链接，包括来自组织内的通信的所有简单 URL 流量），然后可以仅配置的外部 GeoDNS 地址并解析为仅的会议的简单 URL外部地址。

轮循机制方法分发到两个池的请求或用于连接到一个池 （如位于地理位置靠近的池） 的主要并使用另一个池仅中的情况下使用此方法时，您都可以配置为使用每个 GeoDNS 地址连接故障。 

您可以设置电话拨入式简单 url 相同的配置。 为此，请创建类似于上一示例中的其他记录替换`dialin`的`meet`中的 DNS 记录。 为管理简单 URL，使用本节中前面列出的三个选项之一。

一旦此配置的设置方式，您必须使用监视应用程序设置 HTTP 监视的故障。 用于外部访问，以确保该 HTTPS 获取 lyncdiscover 的监视器。<sipdomain> 对外部 web FQDN 或负载平衡器 IP 地址的两个池的请求是成功的。 例如，以下请求不能包含任何**ACCEPT**标头，必须返回**200 确定**。

```
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

用于内部访问，您必须监视端口 5061 上的内部 web FQDN 或负载平衡器的两个池的 IP 地址。 如果检测到任何连接失败，则为这些池 VIP 必须关闭端口 80、 443 和 4443。


