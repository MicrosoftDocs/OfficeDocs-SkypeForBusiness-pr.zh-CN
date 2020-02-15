---
title: Skype for business on Mac 客户端要求
ms.author: v-lanac
author: lanachin
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
description: 阅读本主题，了解在 Mac 上运行 Skype for Business 所需的硬件、软件和基础结构要求。
ms.openlocfilehash: f4f62246a86dabeb628755d3c75a10bc285ede12
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42013455"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Skype for business on Mac 客户端要求
 
阅读本主题，了解在 Mac 上运行 Skype for Business 所需的硬件、软件和基础结构要求。
  
[Mac 客户端上的 Skype For business](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac)可供下载。
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Mac 上 Skype for business 的硬件和软件要求

Mac 客户端上的 Skype for Business 需要 Mac OS X El Capitan 和更高版本，并且至少使用 100 MB 的磁盘空间。 我们支持使用所有内置的音频和视频设备。 外部设备必须位于[Skype For Business 解决方案目录](https://partnersolutions.skypeforbusiness.com/solutionscatalog)中。 
  
> [!NOTE]
> 此列表是初步的，有些设备可能符合 Lync 的要求，但在 Mac 上的 Skype for Business 中不受支持。 请参阅[系统要求](https://products.office.com/office-system-requirements)以了解所需的最低硬件。
  
### <a name="legacy-mac-clients"></a>旧版 Mac 客户端

Skype for Business Server 2015 还支持运行 Mac OS 10.5.8 的计算机上的以下旧客户端，或最新的 service pack 或 release （基于 Intel 的）操作系统（当前不支持 Mac OS 10.9 操作系统）。 有关支持的功能的详细信息，请参阅[适用于 Skype For business 的桌面客户端功能比较](desktop-feature-comparison.md)。
  
- Microsoft Lync for Mac 2011 （请参阅[Lync For mac 2011 部署指南](https://go.microsoft.com/fwlink/p/?LinkId=268786)）
    
- Microsoft Communicator for Mac 2011 （请参阅[Communicator For mac 2011 部署指南](https://go.microsoft.com/fwlink/p/?LinkId=268787)）
 
Skype for Business Server 2019 不支持这些客户端。
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Mac 版 Skype for business 的基础结构要求
<a name="Infrastructure"> </a>

Mac 客户端上的 Skype for Business 同时利用统一通信管理平台（UCMP）以及我们的移动客户端使用的统一通信 Web API （UCWA）。
  
客户端与移动客户端的要求相同，您必须具有在受支持的配置中部署的访问边缘服务器和反向代理。 
  
### <a name="authentication"></a>身份验证

Skype for Business on Mac 客户端支持基于证书的身份验证、Microsoft 新式身份验证和多重身份验证（如果已部署并启用）。
  
> [!NOTE]
> 由于当前限制，用户的 Exchange 凭据必须与 Skype for business 凭据相同。 
  
### <a name="certificates"></a>证书

访问边缘上使用的证书、反向代理和前端服务器不得使用 SHA-512 哈希算法。
  
HTTP 证书吊销列表必须由客户端进行定义和访问。 例如，我们不支持证书中的 LDAP 条目作为证书吊销列表。
  
### <a name="dns"></a>DNS

若要使 Skype for Business 在 Mac 客户端上正常工作，必须正确部署移动性。 一个常见的故障方案是在内部网络上同时解析以下两个 DNS 条目：
  
- lyncdiscoverinternal..\<sipdomain\>
    
- lyncdiscover..\<sipdomain\>
    
有关详细信息，请参阅：[在 Lync server 2013 中部署移动](https://go.microsoft.com/fwlink/p/?LinkId=798224)功能和[Microsoft Lync Server 2010 移动版指南](https://go.microsoft.com/fwlink//p/?LinkId=798226)。
  
## <a name="see-also"></a>另请参阅
<a name="Infrastructure"> </a>

[Skype for Business Server 的 DNS 要求](../../plan-your-deployment/network-requirements/dns.md)

[常见问题解答](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[已知问题](https://go.microsoft.com/fwlink/p/?LinkId=798228)
