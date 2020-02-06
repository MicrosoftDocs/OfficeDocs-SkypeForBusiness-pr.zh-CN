---
title: Skype for business Server 的安全框架
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: 本部分概述了构成 Skype for business 服务器安全框架的基本元素。 了解这些元素如何协同工作对于做出有关保护特定 Skype for Business 服务器部署的明智决策至关重要。
ms.openlocfilehash: 432d4cda013e5bdec2613e3c9052f10b7d619302
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815610"
---
# <a name="security-framework-for-skype-for-business-server"></a>Skype for business Server 的安全框架
 
本部分概述了构成 Skype for business 服务器安全框架的基本元素。 了解这些元素如何协同工作对于做出有关保护特定 Skype for Business 服务器部署的明智决策至关重要。
  
这些要素如下所示：
  
- Active Directory 域服务（AD DS）为用户帐户和网络资源提供单个受信任的后端存储库。
    
- 通过基于角色的访问控制 (RBAC)，您能够在保持高标准安全性的同时委派管理任务。
    
- 公钥基础结构 (PKI) 使用受信任的证书颁发机构 (CA) 颁发的证书来对服务器进行身份验证，并确保数据完整性。
    
- 传输层安全性 (TLS)、HTTPS over SSL (HTTPS) 和相互 TLS (MTLS) 可实现终结点身份验证和 IM 加密。点对点音频、视频和应用程序共享流使用安全实时传输协议 (SRTP) 进行加密。
    
- 用于用户身份验证的行业标准协议，如果可能。
    
- Windows PowerShell 提供默认启用的安全功能，以便用户无法轻松或不知不觉地运行脚本。
    
这些基本的安全元素协同工作以定义受信任的用户、服务器、连接和操作，以帮助确保 Skype for business 服务器的安全基础。
  
## <a name="in-this-section"></a>本节内容

本部分中的主题介绍了每个基本元素如何工作以增强 Skype for business 服务器基础结构的安全性。
  
- [适用于 Skype for business 服务器的 Active Directory 域服务](active-directory-domain-services.md)
    
- [Skype for business Server 的基于角色的访问控制（RBAC）](role-based-access-control-rbac.md)
    
- [Skype for business 服务器的公共密钥基础结构](public-key-infrastructure-for-skype.md)
    
- [Skype for business 服务器的 TLS 和 MTLS](tls-and-mtls.md)
    
- [Skype for business 服务器加密](encryption.md)
    
- [Skype for business Server 的用户和客户端身份验证](user-and-client-authentication.md)
    
- [Windows PowerShell 和 Skype for business 服务器管理工具](management-tools.md)
    

