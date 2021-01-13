---
title: Skype for Business Server 的用户和客户端身份验证
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
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: 受信任用户是其凭据已由 Skype for Business Server 中的受信任服务器进行身份验证的用户。 此服务器通常是 Standard Edition Server、Enterprise Edition 前端服务器或控制器。 Skype for Business Server 依赖 Active Directory 域服务作为用户凭据的单一受信任后端存储库。
ms.openlocfilehash: bf0bde8478cd6c4e2eb068ffade7fba7fac14d56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832002"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a>Skype for Business Server 的用户和客户端身份验证
 
受信任用户是其凭据已由 Skype for Business Server 中的受信任服务器进行身份验证的用户。 此服务器通常是 Standard Edition Server、Enterprise Edition 前端服务器或控制器。 Skype for Business Server 依赖 Active Directory 域服务作为用户凭据的单一受信任后端存储库。
  
身份验证是向可信服务器提供用户凭据的过程。 Skype for Business Server 使用下列身份验证协议，具体取决于用户的状态和位置。
  
- **MIT Kerberos 版本 5 安全协议** - 用于具有 Active Directory 凭据的内部用户。Kerberos 要求客户端与 Active Directory 域服务连接，这就是此协议不能用于对企业防火墙外部的客户端进行身份验证的原因。
    
- **NTLM 协议** - 用于具有 Active Directory 凭据且从企业防火墙外部的终结点进行连接的用户。访问边缘服务将登录请求传递给控制器（如果存在）或前端服务器以进行身份验证。而访问边缘服务本身不执行任何身份验证。
    
    > [!NOTE]
    > 与 Kerberos 相比，NTLM 协议提供的攻击保护较弱，所以某些组织最大程度地降低对 NTLM 的使用。 因此，对 Skype for Business Server 的访问可能仅限于内部或通过 VPN 或 DirectAccess 连接连接的客户端。 
  
- **摘要式协议** - 用于所谓的匿名用户。匿名用户是指满足以下条件的外部用户：这些用户虽然不具备认可的 Active Directory 凭据，但已被邀请参与内部会议并且拥有有效的会议密钥。摘要式身份验证不能用于其他客户端交互活动。
    
Skype for Business Server 身份验证包含两个阶段：
  
1. 在客户端和服务器之间建立安全关联。
    
2. 客户端和服务器使用现有的安全关联签署它们发送的消息并验证接收到的消息。如果在服务器上启用身份验证，则不会接受来自客户端的未经身份验证的消息。
    
用户信任将会附加在用户发出的每条消息上，而不是附加在用户标识本身上。服务器检查每条消息，查看是否具有有效的用户凭据。如果用户凭据有效，则接收消息的第一台服务器以及可信服务器云中的所有其他服务器都不会对消息进行质询。
  
拥有联盟伙伴颁发的有效凭据的用户会受到信任，但其他限制可能会阻止这些用户享有与内部用户相同的全部权限。
  
ICE 和 TURN 协议也会使用摘要式质询，如 IETF TURN RFC 中所述。
  
客户端证书为用户提供了通过 Skype for Business Server 进行身份验证的替代方法。 无需提供用户名和密码，用户具有证书以及解析加密质询所需的与证书对应的私钥。  (此证书必须具有标识用户的使用者名称或使用者替代名称，并且必须由运行 Skype for Business Server 的服务器信任的根 CA 颁发，且在证书有效期内且尚未吊销。) 若要进行身份验证，用户只需键入个人标识号 (PIN) 。 证书对于电话、移动电话和其他难以输入用户名和密码的设备特别有用。
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>ASP .NET 4.5 的加密要求 

自 Skype for Business Server 2015 CU5 起，ASP.NET 4.6 不支持 AES，这可能会导致 Skype 会议应用无法启动。 如果客户端使用 AES 作为计算机密钥验证值，则需要将计算机密钥值重置为 SHA-1 或 IIS 上 Skype 会议应用站点级别支持的另一算法。 如有必要，请参阅 [IIS 8.0 ASP.NET Configuration Management](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) 了解说明。
  
其他支持的值包括：
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
  不再允许值 AES、3DES 和 MD5，因为它们曾经在 ASP.NET 4 中。 [ASP.NET 4.5 pt. 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) 中的加密改进具有更多详细信息。
  
