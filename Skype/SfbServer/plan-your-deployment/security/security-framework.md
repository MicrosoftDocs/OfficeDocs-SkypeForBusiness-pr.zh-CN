---
title: Skype for Business Server 2015 安全框架
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: 本节概述了业务服务器 2015年的 Skype 形成安全框架的基本元素。 了解这些元素在一起工作的方式对有关保护您特定的业务服务器 2015年部署 Skype 明智决策至关重要。
ms.openlocfilehash: c29941a3e903b6318db2de0453589b5017e6f51b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="security-framework-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 安全框架
 
本节概述了业务服务器 2015年的 Skype 形成安全框架的基本元素。 了解这些元素在一起工作的方式对有关保护您特定的业务服务器 2015年部署 Skype 明智决策至关重要。
  
这些要素如下所示：
  
- Active Directory 域服务 (AD DS) 提供一个可靠的后端存储库的用户帐户和网络资源。
    
- 通过基于角色的访问控制 (RBAC)，您能够在保持高标准安全性的同时委派管理任务。
    
- 公钥基础结构 (PKI) 使用受信任的证书颁发机构 (CA) 颁发的证书来对服务器进行身份验证，并确保数据完整性。
    
- 传输层安全性 (TLS)、HTTPS over SSL (HTTPS) 和相互 TLS (MTLS) 可实现终结点身份验证和 IM 加密。点对点音频、视频和应用程序共享流使用安全实时传输协议 (SRTP) 进行加密。
    
- 用于用户身份验证的行业标准协议，如果可能。
    
- Windows PowerShell 提供安全功能，默认情况下启用，以便用户不能轻松地不知不觉地或运行脚本。
    
这些基本的安全元素一起工作来定义受信任的用户、 服务器、 连接和操作，来帮助确保安全的基础的 Skype 业务服务器 2015年。
  
## <a name="in-this-section"></a>本节内容

本节中的主题描述每个基本元素的工作方式来提高您 Skype 业务服务器基础结构的安全性。
  
- [Skype 业务服务器 2015年的 active Directory 域服务](active-directory-domain-services.md)
    
- [为业务服务器 2015年的 Skype 的基于角色的访问控制 (RBAC)](role-based-access-control-rbac.md)
    
- [Skype 业务服务器 2015年的公钥基础结构](public-key-infrastructure-for-skype.md)
    
- [TLS 和 Skype 业务服务器 2015年的 MTLS](tls-and-mtls.md)
    
- [对 Skype 业务服务器 2015年的加密](encryption.md)
    
- [用户和客户端的身份验证为 Skype 的业务服务器 2015](user-and-client-authentication.md)
    
- [Windows PowerShell 和 Skype 业务服务器 2015年管理工具](management-tools.md)
    

