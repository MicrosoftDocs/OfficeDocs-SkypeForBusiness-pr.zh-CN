---
title: Skype for Business Server 2015 的用户和客户端身份验证
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: 受信任的用户是指其凭据已经过身份验证的 Skype 中的受信任服务器的业务服务器 2015年。 此服务器通常是 Standard Edition server，Enterprise Edition 前端服务器或控制器。 Skype 业务服务器依赖于 Active Directory 域服务的用户凭据的单一的受信任后端存储库。
ms.openlocfilehash: 0cdf51da260c8251ca5abbb3ce0834e196a8d51b
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2018
ms.locfileid: "19546521"
---
# <a name="user-and-client-authentication-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 的用户和客户端身份验证
 
受信任的用户是指其凭据已经过身份验证的 Skype 中的受信任服务器的业务服务器 2015年。 此服务器通常是 Standard Edition server，Enterprise Edition 前端服务器或控制器。 Skype 业务服务器依赖于 Active Directory 域服务的用户凭据的单一的受信任后端存储库。
  
身份验证是向受信任的服务器提供用户凭据的过程。 Skype 业务服务器使用以下身份验证协议，具体取决于状态和用户的位置。
  
- **MIT Kerberos 版本 5 安全协议-用于**具有 Active Directory 凭据的内部用户。 Kerberos 要求客户端连接到 Active Directory 域服务，这是它不能用于对企业防火墙外部的客户端进行身份验证的原因。
    
- **NTLM 协议**-用于具有 Active Directory 凭据且从企业防火墙外部的终结点进行连接的用户。 访问边缘服务将登录请求传递给 Director，如果存在此参数或前端服务器进行身份验证。 访问边缘服务本身不执行任何身份验证。
    
    > [!NOTE]
    > 与 Kerberos 相比，NTLM 协议提供的攻击保护较弱，所以有些组织最大程度地减少了对 NTLM 的使用。 因此，访问 Skype 的业务服务器 2015年可能仅限于内部或客户端通过 VPN 或 DirectAccess 连接进行连接。 
  
- **摘要式协议** - 用于所谓的匿名用户。匿名用户是指满足以下条件的外部用户：这些用户虽然不具备认可的 Active Directory 凭据，但已被邀请参与内部会议并且拥有有效的会议密钥。摘要式身份验证不用于其他客户端交互。
    
Skype 业务服务器 2015年身份验证包括两个阶段：
  
1. 在客户端和服务器之间建立安全关联。
    
2. 客户端和服务器使用现有的安全关联签署它们发送的消息，以及验证所收到的消息。如果在服务器上启用了身份验证，则不会接受来自客户端的未经身份验证的消息。
    
用户信任会附加到用户发出的每条消息，而不会附加到用户标识本身。服务器将检查每条消息是否具有有效的用户凭据。如果用户凭据有效，则接收消息的第一台服务器以及受信任的服务器云中的所有其他服务器都不会对消息进行质询。
  
拥有联盟伙伴颁发的有效凭据的用户会受到信任，但其他限制可能会阻止这些用户享有与内部用户相同的全部权限。
  
ICE 和 TURN 协议也使用摘要式质询，如 IETF TURN RFC 中所述。
  
客户端证书提供用户进行身份验证的 Skype 的业务服务器 2015年另一种的方法。 用户无需提供用户名和密码，因为他们具有证书以及解析加密质询所需的与证书对应的私钥。 （此证书必须使用者名称或使用者替代名称的标识用户必须由受信任的服务器运行业务服务器 2015 Skype 根 CA 颁发、 位于内的证书有效期限和不具有已吊销。）要进行身份验证，用户只需键入个人标识号 (PIN)。 证书对电话、移动电话和其他难以输入用户名和密码的设备特别有用。
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>由于 ASP.NET 4.5 加密要求 

截止业务服务器 2015 CU5 的 Skype，AES 不支持 ASP.NET 4.6，这可能会导致 Skype 会议应用程序无法启动。 如果客户端使用的作为计算机关键验证值 AES 需要计算机密钥值重置为 sha-1 或在 IIS 上的 Skype 会议应用程序网站级别上的另一个受支持的算法。 如有必要，请参阅[IIS 8.0 ASP.NET 配置管理](https://docs.microsoft.com/en-us/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management)说明。
  
其他支持的值包括：
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
 AES、 3DES 和 MD5 不再允许，像一次 ASP.NET 4 中的值。 [ASP.NET 4.5，磅 2 中的加密改进](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/)具有更多详细信息。
  
