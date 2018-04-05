---
title: 在 Skype 的简单 Url 的业务服务器 2015年的 DNS 要求
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/9/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 摘要： 为 Skype 的 DNS 记录实施的业务服务器 2015年前查看本主题中的简单的 URL 注意事项。
ms.openlocfilehash: 87346a7c4c03837e5ebfdf0143cdb7c786f0e43b
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2018
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server-2015"></a>在 Skype 的简单 Url 的业务服务器 2015年的 DNS 要求
 
**摘要：**实现业务服务器 2015 DNS 记录为 Skype 之前，请查看本主题中的简单的 URL 注意事项。
  
简单的 Url 让您的用户更方便地加入会议，并使您能够获取到 Skype 业务服务器管理工具更容易为管理员。 简单的 Url 使用自己不匹配任何您定义的 SIP 域的域。 
  
Skype 业务服务器支持以下三个简单的 Url： 满足，拨入和管理员。需要的满足和拨入设置简单的 Url 和管理简单的 URL 是可选的。 支持简单 URL 所需的域名系统 (DNS) 记录取决于定义这些简单 URL 的方式以及是否要对简单 URL 支持灾难恢复。 
  
## <a name="simple-url-scope"></a>简单的 URL 范围

您可以配置您简单的 Url 具有全局作用域，或您的组织中可以指定为每个中心站点的不同简单的 Url。 指定全局简单的 URL 和网站简单的 URL，如果网站简单 URL 具有优先权。 
  
在大多数情况下，建议，这样如果他们从一个站点移动到另一个用户的满足简单的 URL 不会更改您只能在全球范围内，设置简单的 Url。 异常将需要为在不同站点中的拨入用户使用不同电话号码的组织。 请注意，如果您在站点级简单的 URL 设置为设置一个简单的 URL （如拨入简单 URL 中)，您还必须在该站点也是站点级设置其他简单的 Url。
  
在拓扑生成器，您可以设置全局简单的 Url。 若要在站点级别设置简单的 URL，请使用组 CsSimpleURLConfiguration cmdlet。
  
定义简单的 URL 也需要在您的 DNS 配置设置的 A 和/或 AAAA 记录。
  
## <a name="simple-url-naming-and-validation-rules"></a>简单的 URL 命名和验证规则
<a name="BK_Valid"> </a>

拓扑生成器和业务服务器管理外壳 cmdlet 的 Skype 实施几个有效性规则为您简单的 Url。 您需要简单的 Url 和设置的满足拨入，但是设置一个用于管理是可选的。 每个 SIP 域必须单独满足简单的 URL，但您需要为您的整个组织只有一个拨入简单的 URL 和一个管理简单的 URL。
  
您的组织中每个简单的 URL 必须具有唯一的名称，而不能是另一个简单的 URL 前缀 （例如，您无法设置作为您满足简单的 URL 的 SfB2015.contoso.com/Meet 和 SfB2015.contoso.com/Meet/Dialin 为您拨入简单的 URL）。 简单的 URL 名称不能包含任何您的池，或任何端口信息的 FQDN (例如，https://FQDN:88/meet不允许)。 所有简单的 Url 必须以 https:// 前缀开头。 
  
简单的 Url 只能包含字母数字字符 （a-z、 A-Z、 0-9 和句点 （.）。 如果您使用其他字符，简单的 Url 可能无法按预期的方式。
  
## <a name="changing-simple-urls-after-deployment"></a>在部署后更改简单的 Url
<a name="BK_Valid"> </a>

如果您在初始部署后更改简单的 URL，您必须了解如何更改会影响您的 DNS 记录和证书的简单的 Url。 然后简单的 URL 的更改时，如果必须更改 DNS 记录和证书也。 例如，从更改https://SfB2015.contoso.com/Meet到https://meet.contoso.com从 SfB2015.contoso.com 到 meet.contoso.com，更改的基 URL，因此需要更改 DNS 记录和证书请参阅 meet.contoso.com。如果您更改了从简单的 URLhttps://SfB2015.contoso.com/Meet到https://SfB2015.contoso.com/Meetings、 基 URL 的 SfB2015.contoso.com 保持不变，因而没有 DNS 或需要证书更改。
  
无论何时更改一个简单的 URL 名称，但是，必须注册该更改每个控制器和前端服务器上运行**启用 CsComputer** 。
  
## <a name="naming-examples-for-simple-urls"></a>对于简单的 Url 命名示例
<a name="BK_Valid"> </a>

有三种建议的方法来命名自己简单的 Url。 选择哪个选项有含义如何设置您的 DNS A 记录和证书支持简单的 Url。 在每个选项，必须在组织中配置一个满足简单的 URL 的每个 SIP 域。 
  
在您的整个组织的拨入和一个用于管理，不管有多少个 SIP 域始终需要只是一个简单的 URL。
  
选项 1，则在您创建新的 SIP 域名称对于每个简单的 URL。
  
如果使用此选项时，您需要单独的 DNS A 记录，每个简单的 URL 和每个满足简单的 URL 必须命名您的证书中。
  
**简单的 URL 命名选项 1**

|**简单 URL** <br/> |**示例** <br/> |
|:-----|:-----|
|会议  <br/> |https://meet.contoso.comhttps://meet.fabrikam.com，依此类推 （一个用于您的组织中的每个 SIP 域）  <br/> |
|拨入  <br/> |https://dialin.contoso.com  <br/> |
|管理员  <br/> |https://admin.contoso.com  <br/> |
   
使用选项 2，简单的 Url 基于 SfB2015.contoso.com 的域名称。因此，您需要只有一个 DNS A 记录，它使所有三种类型的简单的 Url。 此 DNS A 记录引用 SfB2015.contoso.com。此外，您仍然需要单独的 DNS A 记录其他 SIP 域的组织中。 
  
**简单的 URL 命名选项 2**

|**简单 URL** <br/> |**示例** <br/> |
|:-----|:-----|
|会议  <br/> |https://SfB2015.contoso.com/Meethttps://SfB2015.fabrikam.com/Meet，依此类推 （一个用于您的组织中的每个 SIP 域）  <br/> |
|拨入  <br/> |https://SfB2015.contoso.com/Dialin  <br/> |
|管理员  <br/> |https://SfB2015.contoso.com/Admin  <br/> |
   
选项 3 是最有用的如果您有多个 SIP 域，并且您希望它们有单独满足简单的 Url，但想要最小化这些简单的 Url 的 DNS 记录和证书要求。 
  
**简单的 URL 命名选项 3**

|**简单 URL** <br/> |**示例** <br/> |
|:-----|:-----|
|会议  <br/> |https://SfB2015.contoso.com/contosoSIPdomain/Meet  <br/> https://SfB2015.contoso.com/fabrikamSIPdomain/Meet  <br/> |
|拨入  <br/> |https://SfB2015.contoso.com/Dialin  <br/> |
|管理员  <br/> |https://SfB2015.contoso.com/Admin  <br/> |
   
## <a name="disaster-recovery-option-for-simple-urls"></a>简单的 Url 的灾难恢复选项
<a name="BK_Valid"> </a>

如果您有包含前端池的多个站点，并且 DNS 提供程序支持 GeoDNS，您可以设置您的 DNS 记录的简单的 Url 来支持灾难恢复，，这样简单的 URL 功能仍然存在，即使一个整个前端池出现故障。 此灾难恢复功能支持“会议”和“拨入”简单 URL。
  
若要进行此配置，请创建两个 GeoDNS 地址。每个地址具有两个 DNS A 或 CNAME 记录，这些记录解析到出于灾难恢复目的配对在一起的两个池。一个 GeoDNS 地址用于内部访问，并解析到两个池的内部 Web FQDN 或负载平衡器 IP 地址。另一个 GeoDNS 地址用于外部访问，并解析到两个池的外部 Web FQDN 或负载平衡器 IP 地址。下面是使用池的 FQDN 的“会议”简单 URL 的示例。 
  
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

然后，创建将“会议”简单 URL（如 meet.contoso.com）解析到两个 GeoDNS 地址的 CNAME 记录。
  
> [!NOTE]
> 如果您的网络使用 hairpinning （路由通过外部链接，其中包括来自组织内部的通信的所有简单的 URL 通信），然后只需配置外部的 GeoDNS 地址并解决您满足简单的 URL，仅外部地址。
  
使用此方法时，您可以将每个 GeoDNS 地址配置为使用循环方法向两个池分发请求，或主要连接到一个池（如地理位置上接近的池）并仅在连接失败的情况下使用另一个池。 
  
您可以对“拨入”简单 URL 设置相同的配置。 若要执行此操作，创建类似于前面的示例中的其他记录替换`dialin`的`meet`中的 DNS 记录。 对于“管理”简单 URL，请使用本节前面所列的三个选项之一。
  
设置完此配置后，您必须使用监控应用程序来设置 HTTP 监控以留意故障。 对于外部访问，监视，以确保该 HTTPS 得到 lyncdiscover。<sipdomain> 到外部站点的两个池的 FQDN 或负载平衡器 IP 地址的请求才会成功。 例如，以下请求不能包含任何**ACCEPT**标头，并且必须返回**200 确定**。
  
```
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

对于内部访问，您必须监控两个池的内部 Web FQDN 或负载平衡器 IP 地址上的端口 5061。如果检测到任何连接失败，这些池的 VIP 必须关闭端口 80、443 和 4443。
  

