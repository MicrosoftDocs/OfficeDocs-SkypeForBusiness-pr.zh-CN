---
title: Mac 版 Skype for business 客户端要求
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
description: 阅读本主题，了解在 Mac 上运行 Skype for Business 的硬件、软件和基础结构要求。
ms.openlocfilehash: 08f3aeabbfd88b432c28f05727ec7cf009e297a7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803592"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Mac 版 Skype for business 客户端要求
 
阅读本主题，了解在 Mac 上运行 Skype for Business 的硬件、软件和基础结构要求。
  
[Mac 客户端版 Skype For business](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3#Mac)可供下载。
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Mac 版 Skype for business 的硬件和软件要求

Mac 版 Skype for business 客户端需要 Mac OS X El Capitan 和更高版本，并使用至少100MB 的磁盘空间。 我们支持使用所有内置音频和视频设备。 外部设备必须位于[Skype For Business 解决方案目录](https://partnersolutions.skypeforbusiness.com/solutionscatalog)中。 
  
> [!NOTE]
> 此列表是初步的，某些设备可能合格 Lync，但在 Mac 上的 Skype for Business 上不受支持。 请参阅[系统要求](https://products.office.com/en-us/office-system-requirements)以了解所需的最低硬件要求。
  
### <a name="legacy-mac-clients"></a>旧版 Mac 客户端

Skype for Business Server 2015 还支持在运行 Mac OS 10.5.8 或最新服务包或发布（基于 Intel）操作系统（目前不支持 Mac OS 10.9 操作系统）的计算机上执行以下旧客户端。 有关支持的功能的详细信息，请参阅[Skype for business 的桌面客户端功能比较](desktop-feature-comparison.md)。
  
- Microsoft Lync for Mac 2011 （请参阅[Lync For mac 2011 部署指南](https://go.microsoft.com/fwlink/p/?LinkId=268786)）
    
- Microsoft Communicator for Mac 2011 （请参阅[Communicator For mac 2011 部署指南](https://go.microsoft.com/fwlink/p/?LinkId=268787)）
 
Skype for Business Server 2019 不支持这些客户端。
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Mac 版 Skype for business 的基础结构要求
<a name="Infrastructure"> </a>

Mac 版 Skype for business 客户端利用统一通信管理平台（UCMP）以及我们的移动客户端使用的统一通信 Web API （UCWA）。
  
该客户与移动客户端具有相同要求，用户必须在支持的配置中部署访问边缘服务器和反向代理。 
  
### <a name="authentication"></a>身份验证

Mac 版 Skype for business 客户端支持基于证书的身份验证、Microsoft 新式身份验证和多重身份验证（如果已部署并启用）。
  
> [!NOTE]
> 由于当前限制，用户的 Exchange 凭据必须与他们的 Skype for Business 凭据相同。 
  
### <a name="certificates"></a>证书

在访问边缘、反向代理和前端服务器上使用的证书不能使用 SHA-512 哈希算法。
  
HTTP 证书吊销列表必须已定义并且可由客户端访问。 例如，我们不支持证书中的 LDAP 条目作为你的证书吊销列表。
  
### <a name="dns"></a>DNS

必须正确部署适用于 Mac 客户端的 Skype for Business 才能正常工作的移动。 一个常见的故障情况是在内部网络上同时让以下两个 DNS 条目可解析：
  
- lyncdiscoverinternal.\<sipdomain\>
    
- lyncdiscover.\<sipdomain\>
    
有关详细信息，请参阅：[在 Lync server 2013 中部署移动性](https://go.microsoft.com/fwlink/p/?LinkId=798224)和[Microsoft Lync Server 2010 移动版指南](https://go.microsoft.com/fwlink//p/?LinkId=798226)。
  
## <a name="see-also"></a>另请参阅
<a name="Infrastructure"> </a>

[Skype for business 服务器的 DNS 要求](../../plan-your-deployment/network-requirements/dns.md)

[常见问题](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[已知问题](https://go.microsoft.com/fwlink/p/?LinkId=798228)
