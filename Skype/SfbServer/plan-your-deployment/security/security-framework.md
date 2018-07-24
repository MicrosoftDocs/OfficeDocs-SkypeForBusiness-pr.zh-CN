---
title: Skype 业务服务器的安全框架
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: 本节概述了业务服务器 Skype 的表单的安全框架的基本要素。 了解这些要素协同工作的方式对于做出有关保护您的业务服务器部署的特定 Skype 的明智的决定至关重要。
ms.openlocfilehash: 487b3ea7f57c1a008327be2b9b31664a160e8425
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20983614"
---
# <a name="security-framework-for-skype-for-business-server"></a>Skype 业务服务器的安全框架
 
本节概述了业务服务器 Skype 的表单的安全框架的基本要素。 了解这些要素协同工作的方式对于做出有关保护您的业务服务器部署的特定 Skype 的明智的决定至关重要。
  
这些要素如下所示：
  
- Active Directory 域服务 (AD DS) 为用户帐户和网络资源提供单个受信任的后端存储库。
    
- 通过基于角色的访问控制 (RBAC)，您能够在保持高标准安全性的同时委派管理任务。
    
- 公钥基础结构 (PKI) 使用受信任的证书颁发机构 (CA) 颁发的证书来对服务器进行身份验证，并确保数据完整性。
    
- 传输层安全性 (TLS)、HTTPS over SSL (HTTPS) 和相互 TLS (MTLS) 可实现终结点身份验证和 IM 加密。点对点音频、视频和应用程序共享流使用安全实时传输协议 (SRTP) 进行加密。
    
- 用于用户身份验证的行业标准协议，如果可能。
    
- Windows PowerShell 提供默认启用的以便用户无法轻松或在不知情的情况下运行脚本的安全功能。
    
这些基本安全要素共同定义受信任的用户、 服务器、 连接和操作，以帮助确保安全的基础的 Skype 业务服务器。
  
## <a name="in-this-section"></a>本节内容

本节中的主题介绍每个基本要素如何工作以增强您 Skype Business Server 基础结构的安全性。
  
- [业务服务器 Skype 的的 active Directory 域服务](active-directory-domain-services.md)
    
- [基于角色的访问控制 (RBAC) 的 Skype 业务服务器](role-based-access-control-rbac.md)
    
- [公钥基础结构 Skype 业务服务器](public-key-infrastructure-for-skype.md)
    
- [Skype 业务服务器的 TLS 和 MTLS](tls-and-mtls.md)
    
- [Skype 加密业务服务器](encryption.md)
    
- [用户和客户端身份验证的 Skype 业务服务器](user-and-client-authentication.md)
    
- [Windows PowerShell 和 Skype 的业务 Server 管理工具](management-tools.md)
    

