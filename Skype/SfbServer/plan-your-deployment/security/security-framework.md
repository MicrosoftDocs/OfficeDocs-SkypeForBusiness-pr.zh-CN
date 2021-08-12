---
title: 安全框架Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: 本节概述了构成安全框架的基本Skype for Business Server。 了解这些元素如何协同工作对于做出有关保护特定部署部署的安全Skype for Business Server至关重要。
ms.openlocfilehash: a0f6513f86d7416f546c6a744fc1b40df7c7137a18dae5d76fcf18166a4f2eb1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337710"
---
# <a name="security-framework-for-skype-for-business-server"></a>安全框架Skype for Business Server
 
本节概述了构成安全框架的基本Skype for Business Server。 了解这些元素如何协同工作对于做出有关保护特定部署部署的安全Skype for Business Server至关重要。
  
这些要素如下所示：
  
- Active Directory 域服务 (AD DS) 为用户帐户和网络资源提供一个受信任的后端存储库。
    
- Role-Based访问控制 (RBAC) 使您能够在保持高安全标准的同时委派管理任务。
    
- PKI (PKI) 使用受信任的证书颁发机构 (CA 颁发的) 验证服务器并确保数据完整性。
    
- 传输层安全性 (TLS)、HTTPS over SSL (HTTPS) 和相互 TLS (MTLS) 可实现终结点身份验证和 IM 加密。点对点音频、视频和应用程序共享流使用安全实时传输协议 (SRTP) 进行加密。
    
- 用于用户身份验证的行业标准协议，如果可能。
    
- Windows PowerShell 提供默认启用的安全功能，这样用户便无法轻松或在不知情的情况下运行脚本。
    
这些基本安全元素共同定义受信任的用户、服务器、连接和操作，以帮助确保安全的基础Skype for Business Server。
  
## <a name="in-this-section"></a>本节内容

本节中的主题介绍每个基本元素如何工作以增强基础结构Skype for Business Server的安全性。
  
- [Active Directory 域服务Skype for Business Server](active-directory-domain-services.md)
    
- [基于角色的访问控制 (RBAC) for Skype for Business Server](role-based-access-control-rbac.md)
    
- [用于基础结构的公钥Skype for Business Server](public-key-infrastructure-for-skype.md)
    
- [TLS 和 MTLS for Skype for Business Server](tls-and-mtls.md)
    
- [加密Skype for Business Server](encryption.md)
    
- [用户和客户端身份验证Skype for Business Server](user-and-client-authentication.md)
    
- [Windows PowerShell Skype for Business Server管理工具](management-tools.md)
    

