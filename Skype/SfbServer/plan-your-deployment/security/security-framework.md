---
title: Skype for Business Server 的安全框架
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
description: 本部分概述了构成 Skype for Business Server 安全框架的基本元素。 了解这些元素如何协同工作对于做出有关保护特定 Skype for Business Server 部署的明智决定至关重要。
ms.openlocfilehash: 94d2ffac30e029ab6631557a69d6da3ec108657f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832092"
---
# <a name="security-framework-for-skype-for-business-server"></a>Skype for Business Server 的安全框架
 
本部分概述了构成 Skype for Business Server 安全框架的基本元素。 了解这些元素如何协同工作对于做出有关保护特定 Skype for Business Server 部署的明智决定至关重要。
  
这些要素如下所示：
  
- Active Directory 域服务 (AD DS) 为用户帐户和网络资源提供一个受信任的后端存储库。
    
- Role-Based访问控制 (RBAC) 允许您委派管理任务，同时维护高安全标准。
    
- PKI (PKI) 使用受信任证书颁发机构颁发的证书 (CA) 服务器进行身份验证并确保数据完整性。
    
- 传输层安全性 (TLS)、HTTPS over SSL (HTTPS) 和相互 TLS (MTLS) 可实现终结点身份验证和 IM 加密。点对点音频、视频和应用程序共享流使用安全实时传输协议 (SRTP) 进行加密。
    
- 用于用户身份验证的行业标准协议，如果可能。
    
- Windows PowerShell 提供默认启用的安全功能，这样用户便无法轻松或在不知情的情况下运行脚本。
    
这些基本安全元素共同定义受信任的用户、服务器、连接和操作，以帮助确保 Skype for Business Server 的安全基础。
  
## <a name="in-this-section"></a>本节内容

本节中的主题介绍每个基本元素如何工作以增强 Skype for Business Server 基础结构的安全性。
  
- [适用于 Skype for Business Server 的 Active Directory 域服务](active-directory-domain-services.md)
    
- [基于角色的访问控制 (RBAC) For Skype for Business Server](role-based-access-control-rbac.md)
    
- [Skype for Business Server 的公钥基础结构](public-key-infrastructure-for-skype.md)
    
- [Skype for Business Server 的 TLS 和 MTLS](tls-and-mtls.md)
    
- [Skype for Business Server 加密](encryption.md)
    
- [Skype for Business Server 的用户和客户端身份验证](user-and-client-authentication.md)
    
- [Windows PowerShell和 Skype for Business Server 管理工具](management-tools.md)
    

