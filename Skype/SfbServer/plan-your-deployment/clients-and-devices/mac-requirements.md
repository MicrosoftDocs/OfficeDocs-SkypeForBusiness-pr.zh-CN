---
title: Mac 上的 Skype for Business 客户端要求
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: 阅读本主题，了解在 Mac 上运行 Skype for Business 的硬件、软件和基础结构要求。
ms.openlocfilehash: 5f967bab3a5dcc41a3419324c9fe09b48a8fb674
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832162"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Mac 上的 Skype for Business 客户端要求
 
阅读本主题，了解在 Mac 上运行 Skype for Business 的硬件、软件和基础结构要求。
  
Mac [客户端上的 Skype for Business](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac) 可供下载。
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Mac 上的 Skype for Business 的硬件和软件要求

Mac 版 Skype for Business 客户端需要 Mac OS X El 一级及更高版本，并且至少使用 100MB 磁盘空间。 我们支持使用所有内置音频和视频设备。 外部设备必须在 [Skype for Business 解决方案目录中](https://partnersolutions.skypeforbusiness.com/solutionscatalog)。 
  
> [!NOTE]
> 此列表是初步列表，某些设备可能限定为 Lync，但在 Mac 上的 Skype for Business 上不受支持。 有关最低 [硬件要求](https://products.office.com/office-system-requirements) ，请参阅系统要求。
  
### <a name="legacy-mac-clients"></a>旧版 Mac 客户端

Skype for Business Server 2015 还支持运行 Mac OS 10.5.8 或最新 Service Pack 或基于 (Intel 的) 操作系统版本 (Mac OS 10.9 操作系统的计算机上以下旧版客户端) 。 有关受支持的功能的详细信息，请参阅 [Skype for Business 的桌面客户端功能比较](desktop-feature-comparison.md)。
  
- Microsoft Lync for Mac 2011 (请参阅[Lync for Mac 2011 部署指南) ](https://go.microsoft.com/fwlink/p/?LinkId=268786)
    
- Microsoft Communicator for Mac 2011 (请参阅 [Communicator for Mac 2011 部署](https://go.microsoft.com/fwlink/p/?LinkId=268787) 指南) 
 
Skype for Business Server 2019 不支持这些客户端。
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Mac 上 Skype for Business 的基础结构要求
<a name="Infrastructure"> </a>

Mac 上的 Skype for Business 客户端同时利用统一通信管理平台 (UCMP) 以及移动客户端使用的统一通信 Web API (UCWA) 。
  
客户端具有与移动客户端相同的要求，因为您必须在受支持的配置中部署访问边缘服务器和反向代理。 
  
### <a name="authentication"></a>身份验证

在部署和启用 Mac 上的 Skype for Business 客户端时，支持基于证书的身份验证、Microsoft 新式验证和多重身份验证。
  
> [!NOTE]
> 由于当前存在限制，用户的 Exchange 凭据必须与 Skype for Business 凭据相同。 
  
### <a name="certificates"></a>证书

访问边缘、反向代理和前端服务器上使用的证书不得使用 SHA-512 哈希算法。
  
客户端必须定义并可访问 HTTP 证书吊销列表。 例如，我们不支持证书中的 LDAP 条目作为证书吊销列表。
  
### <a name="dns"></a>DNS

必须正确部署移动功能，Mac 客户端上的 Skype for Business 正常运行。 常见的失败方案是使以下两个 DNS 条目在内部网络上可解析：
  
- lyncdiscoverinternal。\<sipdomain\>
    
- lyncdiscover。\<sipdomain\>
    
有关详细信息，请参阅[：Deploying Mobility in Lync Server 2013，](https://go.microsoft.com/fwlink/p/?LinkId=798224)and the [Microsoft Lync Server 2010 Mobility Guide.](https://go.microsoft.com/fwlink//p/?LinkId=798226)
  
## <a name="see-also"></a>另请参阅
<a name="Infrastructure"> </a>

[Skype for Business Server 的 DNS 要求](../../plan-your-deployment/network-requirements/dns.md)

[常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[已知问题](https://go.microsoft.com/fwlink/p/?LinkId=798228)
