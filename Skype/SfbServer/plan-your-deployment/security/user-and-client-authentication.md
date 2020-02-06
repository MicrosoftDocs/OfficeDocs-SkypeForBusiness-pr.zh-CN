---
title: Skype for business Server 的用户和客户端身份验证
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
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: 受信任的用户是其凭据已由 Skype for Business Server 中的受信任服务器进行身份验证的用户。 此服务器通常是标准版服务器、企业版前端服务器或控制器。 Skype for business 服务器依赖 Active Directory 域服务作为用户凭据的单个受信任的后端存储库。
ms.openlocfilehash: 2ffabce6546bf8b542503f8c80fe5cb2b952c568
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815580"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a>Skype for business Server 的用户和客户端身份验证
 
受信任的用户是其凭据已由 Skype for Business Server 中的受信任服务器进行身份验证的用户。 此服务器通常是标准版服务器、企业版前端服务器或控制器。 Skype for business 服务器依赖 Active Directory 域服务作为用户凭据的单个受信任的后端存储库。
  
身份验证是向受信任的服务器提供用户凭据的过程。 Skype for business 服务器使用以下身份验证协议，具体取决于用户的状态和位置。
  
- 对具有 Active Directory 凭据的内部用户的**Kerberos 版本5安全协议的 MIT** 。 Kerberos 需要与 Active Directory 域服务的客户端连接，这就是为什么无法使用它来对公司防火墙外部的客户端进行身份验证。
    
- 使用 Active Directory 凭据连接到公司防火墙外部终结点的用户的**NTLM 协议**。 Access Edge 服务将登录请求传递到 Director （如果存在）或前端服务器进行身份验证。 访问边缘服务本身不执行身份验证。
    
    > [!NOTE]
    > 与 Kerberos 相比，NTLM 协议提供的攻击保护较弱，所以有些组织最大程度地减少了对 NTLM 的使用。 因此，对 Skype for business 服务器的访问可能仅限于内部或通过 VPN 或 DirectAccess 连接连接的客户端。 
  
- **摘要式协议** - 用于所谓的匿名用户。匿名用户是指满足以下条件的外部用户：这些用户虽然不具备认可的 Active Directory 凭据，但已被邀请参与内部会议并且拥有有效的会议密钥。摘要式身份验证不用于其他客户端交互。
    
Skype for Business 服务器身份验证包含两个阶段：
  
1. 在客户端和服务器之间建立安全关联。
    
2. 客户端和服务器使用现有的安全关联签署它们发送的消息，以及验证所收到的消息。如果在服务器上启用了身份验证，则不会接受来自客户端的未经身份验证的消息。
    
用户信任会附加到用户发出的每条消息，而不会附加到用户标识本身。服务器将检查每条消息是否具有有效的用户凭据。如果用户凭据有效，则接收消息的第一台服务器以及受信任的服务器云中的所有其他服务器都不会对消息进行质询。
  
拥有联盟伙伴颁发的有效凭据的用户会受到信任，但其他限制可能会阻止这些用户享有与内部用户相同的全部权限。
  
ICE 和 TURN 协议也使用摘要式质询，如 IETF TURN RFC 中所述。
  
客户端证书为用户提供了另一种通过 Skype for Business 服务器进行身份验证的方法。 用户无需提供用户名和密码，因为他们具有证书以及解析加密质询所需的与证书对应的私钥。 （该证书必须具有标识用户的主题名称或使用者备用名称，并且必须由运行 Skype for Business Server 的服务器信任的根 CA 发出，在证书的有效期内且未被吊销。）若要进行身份验证，用户只需键入个人识别码（PIN）。 证书对电话、移动电话和其他难以输入用户名和密码的设备特别有用。
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>由于 ASP .NET 4.5 的加密要求 

从 Skype for Business Server 2015 CU5 不支持 ASP.NET 4.6 的 AES，这可能会导致 Skype 会议应用无法启动。 如果客户使用 AES 作为计算机密钥验证值，则需要将计算机密钥值重置为 IIS 上的 Skype 会议应用网站级别上的 SHA-1 或其他受支持的算法。 如有必要，请参阅[IIS 8.0 ASP.NET 配置管理](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management)以了解相关说明。
  
其他受支持的值为：
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
  不再允许使用值 AES、3DES 和 MD5，因为它们一次位于 ASP.NET 4 中。 [ASP.NET 4.5 中的加密改进](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/)有更多详细信息。
  
