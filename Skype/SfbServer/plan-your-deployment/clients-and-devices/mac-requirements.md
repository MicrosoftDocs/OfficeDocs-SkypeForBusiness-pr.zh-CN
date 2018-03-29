---
title: Skype 为 Mac 客户端要求的企业的
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: 阅读本主题，以了解有关硬件、 软件和基础架构要求： 运行业务的 Skype 上 mac。
ms.openlocfilehash: 1b5fa68a9618126ab69f4ca78f13e65f1ab3ee4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Skype 为 Mac 客户端要求的企业的
 
阅读本主题，以了解有关硬件、 软件和基础架构要求： 运行业务的 Skype 上 mac。
  
[业务 Mac 客户端上的 Skype](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3#Mac)已可供下载。
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-the-mac"></a>Mac 上的 Skype for Business 的硬件和软件要求

对于 Mac 客户端上的业务 Skype 要求 Mac OS X El Capitan 和更高版本，并使用至少 100 MB 的磁盘空间。 我们支持使用所有内置音频和视频设备。 外部设备必须[使用 Lync 使用经鉴定的设备的列表](https://go.microsoft.com/fwlink/p/?LinkId=798223)。 
  
> [!NOTE]
> 此列表是初步和某些设备可能适合 Lync，但业务在 mac 上的 Skype 上不受支持 > 请参阅[系统要求](https://products.office.com/en-us/office-system-requirements)的最低硬件配置要求。
  
### <a name="legacy-mac-clients"></a>Mac 的旧客户端

Skype 的业务服务器 2015年还支持计算机运行的 Mac OS 10.5.8 或最新的 service pack 或释放 （基于 Intel 的） 操作系统 （不，目前支持 Mac OS 10.9 操作系统） 下面的旧客户端。 有关受支持的功能的详细信息，请参阅[为 Skype 业务桌面客户端功能比较](desktop-feature-comparison.md)。
  
- Mac （请参见[Mac 2011 部署指南的 Lync](https://go.microsoft.com/fwlink/p/?LinkId=268786)） 2011年的 Microsoft Lync
    
- Mac （请参见[Mac 2011 部署指南 Communicator](https://go.microsoft.com/fwlink/p/?LinkId=268787)） 2011年的 Microsoft Communicator
    
## <a name="infrastructure-requirements-for-skype-for-business-on-the-mac"></a>Mac 上的 Skype for Business 的基础结构要求
<a name="Infrastructure"> </a>

对于 Mac 客户端上的业务 Skype 利用统一通信管理平台 (UCMP) 以及统一通信 Web API (UCWA)，我们移动客户机使用。
  
该客户与移动客户端具有相同要求，用户必须在支持的配置中部署访问边缘服务器和反向代理。 此外，必须为用户的帐户启用移动性。
  
### <a name="authentication"></a>身份验证

Skype 的 Mac 客户端上的业务支持 NTLM 身份验证。 此外，客户端支持 Microsoft 新式身份验证和多重身份验证（在部署并启用时）。
  
> [!NOTE]
> 由于当前的限制，用户的 Exchange 凭据必须与他们 Skype 业务的凭据相同。 
  
### <a name="certificates"></a>证书

在访问边缘、反向代理和前端服务器上使用的证书不能使用 SHA-512 哈希算法。
  
HTTP 证书吊销列表必须已定义并且可由客户端访问。 例如，我们不支持 LDAP 条目在证书作为您的证书吊销列表。
  
### <a name="dns"></a>DNS

移动必须正确地部署业务 Skype 为 Mac 客户端程序才能正常工作。 一个常见的故障情况是在内部网络上同时让以下两个 DNS 条目可解析：
  
- lyncdiscoverinternal。\<sipdomain\>
    
- lyncdiscover。\<sipdomain\>
    
有关详细信息，请参阅：[部署灵活性 Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=798224)和[Microsoft Lync Server 2010 行动指南](https://go.microsoft.com/fwlink//p/?LinkId=798226)。
  
## <a name="see-also"></a>另请参阅
<a name="Infrastructure"> </a>

#### 

[Skype 的业务服务器 2015 DNS 要求](../../plan-your-deployment/network-requirements/dns.md)
#### 

[常见问题](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[已知的问题](https://go.microsoft.com/fwlink/p/?LinkId=798228)

