---
title: Skype for Business Mac 客户端要求
ms.author: jambirk
author: PhillipGarding
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: 阅读此主题以了解有关硬件、 软件和基础结构要求运行 for Business 的 Skype mac。
ms.openlocfilehash: 184f94dfb272ce2160667d31825309001ab8396d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886376"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Skype for Business Mac 客户端要求
 
阅读此主题以了解有关硬件、 软件和基础结构要求运行 for Business 的 Skype mac。
  
[Skype for Mac 客户端上的 Business](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3#Mac)是可供下载。
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-the-mac"></a>Mac 上的 Skype for Business 的硬件和软件要求

Skype for Mac 客户端上的业务需要 Mac OS X El Capitan 和更高版本，并使用至少 100 MB 的磁盘空间。 我们支持使用所有内置音频和视频设备。 外部设备必须[Skype 业务解决方案目录](https://partnersolutions.skypeforbusiness.com/solutionscatalog)中。 
  
> [!NOTE]
> 此列表为初稿，以后和某些设备可能合格的 lync，但不是支持在 mac 上的业务的 Skype 引用了所需的最低硬件的[系统要求](https://products.office.com/en-us/office-system-requirements)。
  
### <a name="legacy-mac-clients"></a>旧 Mac 客户端

Skype 的业务服务器 2015年运行的 Mac OS 10.5.8 或最新 service pack 或版本 （基于 Intel） 操作系统 （Mac OS 10.9 操作系统目前不支持） 的计算机上还支持下列旧客户端。 有关受支持的功能的详细信息，请参阅[for Business 的 Skype 的桌面客户端功能比较](desktop-feature-comparison.md)。
  
- Microsoft Lync for Mac 2011 （请参阅[Lync for Mac 2011 部署指南 》](https://go.microsoft.com/fwlink/p/?LinkId=268786)）
    
- Microsoft Communicator for Mac 2011 （请参阅[Communicator for Mac 2011 部署指南 》](https://go.microsoft.com/fwlink/p/?LinkId=268787)）
 
这些客户端不支持 Skype 的业务服务器 2019年。
   
## <a name="infrastructure-requirements-for-skype-for-business-on-the-mac"></a>Mac 上的 Skype for Business 的基础结构要求
<a name="Infrastructure"> </a>

For Mac 客户端上的 Business Skype 利用统一通信管理平台 (UCMP) 以及统一通信 Web API (UCWA) 我们移动客户端使用。
  
该客户与移动客户端具有相同要求，用户必须在支持的配置中部署访问边缘服务器和反向代理。 
  
### <a name="authentication"></a>身份验证

For Mac 客户端上的 Business Skype 支持基于证书的身份验证、 Microsoft 现代身份验证以及部署和启用时的多因素身份验证。
  
> [!NOTE]
> 当前限制，因为用户的 Exchange 凭据必须业务凭据其 Skype 相同。 
  
### <a name="certificates"></a>证书

在访问边缘、反向代理和前端服务器上使用的证书不能使用 SHA-512 哈希算法。
  
HTTP 证书吊销列表必须已定义并且可由客户端访问。 例如，我们不支持的 LDAP 条目证书中为您的证书吊销列表。
  
### <a name="dns"></a>DNS

移动功能，必须正确部署 for Business Skype 在 Mac 客户端能够正常工作。 一个常见的故障情况是在内部网络上同时让以下两个 DNS 条目可解析：
  
- lyncdiscoverinternal。\<sipdomain\>
    
- lyncdiscover。\<sipdomain\>
    
有关详细信息，请参阅：[部署 Lync Server 2013 中的移动](https://go.microsoft.com/fwlink/p/?LinkId=798224)性和[Microsoft Lync Server 2010 移动指南](https://go.microsoft.com/fwlink//p/?LinkId=798226)。
  
## <a name="see-also"></a>另请参阅
<a name="Infrastructure"> </a>

[Skype for Business Server 的 DNS 要求](../../plan-your-deployment/network-requirements/dns.md)

[常见问题 (英文）](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[已知的问题](https://go.microsoft.com/fwlink/p/?LinkId=798228)