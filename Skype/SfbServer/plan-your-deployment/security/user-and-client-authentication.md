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
description: 受信任的用户是其凭据已经过身份验证通过 Skype 在受信任的服务器的业务服务器 2015年。 此服务器通常是标准版，企业版前端服务器或服务器主管。 Skype 业务服务器依赖于 Active Directory 域服务单一、 信任后端存储库的用户凭据。
ms.openlocfilehash: d8fa9265a4c27432dd4c2dba6e15c07e39f348b8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="user-and-client-authentication-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 的用户和客户端身份验证
 
受信任的用户是其凭据已经过身份验证通过 Skype 在受信任的服务器的业务服务器 2015年。 此服务器通常是标准版，企业版前端服务器或服务器主管。 Skype 业务服务器依赖于 Active Directory 域服务单一、 信任后端存储库的用户凭据。
  
身份验证是向受信任的服务器提供用户凭据的过程。 Skype 业务服务器将使用下列身份验证协议，具体取决于状态和用户的位置。
  
- 对于内部用户使用 Active Directory 凭据**MIT Kerberos 版本 5 的安全协议**。 Kerberos 需要与 Active Directory 域服务，这是为什么它不能用于身份验证客户端在公司防火墙外部的客户端连接。
    
- 使用 Active Directory 凭据连接从公司防火墙外的终结点用户的**NTLM 协议**。 访问边缘服务传递给主管，（如果存在） 或前端服务器进行身份验证的登录请求。 访问边缘服务本身执行任何身份验证。
    
    > [!NOTE]
    > 与 Kerberos 相比，NTLM 协议提供的攻击保护较弱，所以有些组织最大程度地减少了对 NTLM 的使用。 结果是，Skype 业务服务器 2015年的访问可能仅限于内部或客户端通过 VPN 或 DirectAccess 连接进行连接。 
  
- **摘要式协议** - 用于所谓的匿名用户。匿名用户是指满足以下条件的外部用户：这些用户虽然不具备认可的 Active Directory 凭据，但已被邀请参与内部会议并且拥有有效的会议密钥。摘要式身份验证不用于其他客户端交互。
    
Skype 业务服务器 2015年身份验证包括两个阶段：
  
1. 在客户端和服务器之间建立安全关联。
    
2. 客户端和服务器使用现有的安全关联签署它们发送的消息，以及验证所收到的消息。如果在服务器上启用了身份验证，则不会接受来自客户端的未经身份验证的消息。
    
用户信任会附加到用户发出的每条消息，而不会附加到用户标识本身。服务器将检查每条消息是否具有有效的用户凭据。如果用户凭据有效，则接收消息的第一台服务器以及受信任的服务器云中的所有其他服务器都不会对消息进行质询。
  
拥有联盟伙伴颁发的有效凭据的用户会受到信任，但其他限制可能会阻止这些用户享有与内部用户相同的全部权限。
  
ICE 和 TURN 协议也使用摘要式质询，如 IETF TURN RFC 中所述。
  
客户端证书提供对用户进行身份验证通过 Skype 业务服务器 2015年的另一种方法。 用户无需提供用户名和密码，因为他们具有证书以及解析加密质询所需的与证书对应的私钥。 （此证书主题名称或者主题备用名称标识用户和必须由受信任的服务器运行 Skype 业务服务器 2015年由根 CA 颁发，可以在证书的有效期内，并不被吊销时必须有）要进行身份验证，用户只需输入个人识别码 (PIN)。 证书对电话、移动电话和其他难以输入用户名和密码的设备特别有用。
  

