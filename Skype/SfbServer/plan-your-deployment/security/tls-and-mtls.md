---
title: Skype for business 服务器的 TLS 和 MTLS
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
ms.assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
description: 传输层安全性 (TLS) 和相互传输层安全性 (MTLS) 协议提供 Internet 上的加密通信和终结点身份验证。 Skype for Business 服务器使用这两个协议创建受信任服务器的网络，并确保通过该网络的所有通信均已加密。 服务器之间的所有 SIP 通信都通过 MTLS 进行。 从客户端到服务器的 SIP 通信都通过 TLS 进行。
ms.openlocfilehash: 5030916780c9e39eee10bf2c2fcb6fb213c9b075
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815590"
---
# <a name="tls-and-mtls-for-skype-for-business-server"></a>Skype for business 服务器的 TLS 和 MTLS
 
传输层安全性 (TLS) 和相互传输层安全性 (MTLS) 协议提供 Internet 上的加密通信和终结点身份验证。 Skype for Business 服务器使用这两个协议创建受信任服务器的网络，并确保通过该网络的所有通信均已加密。 服务器之间的所有 SIP 通信都通过 MTLS 进行。 从客户端到服务器的 SIP 通信都通过 TLS 进行。
  
TLS 允许用户通过其客户端软件对其连接的 Skype for business 服务器服务器进行身份验证。 在 TLS 连接上，客户端从服务器请求有效证书。 有效证书必须满足以下条件：由受客户端信任的 CA 颁发，且服务器的 DNS 名称必须与证书上的 DNS 名称一致。 如果证书有效，则客户端使用证书中的公钥对用于通信的对称加密密钥进行加密，因此只有证书的原始所有者可以使用其私钥对通信内容进行解密。 生成的连接将会受到信任，之后再不会受到其他受信任的服务器或客户端的质询。 在此上下文中，可将用于 Web 服务的安全套接字层 (SSL) 视为是基于 TLS 的。
  
服务器到服务器的连接依赖 MTLS 来进行相互身份验证。 在 MTLS 连接上，发出消息的服务器和接收消息的服务器交换来自相互信任的 CA 的证书。 证书可向一台服务器证明另一台服务器的身份。 在 Skype for Business 服务器部署中，由所有内部客户端和服务器颁发的企业 CA 颁发的证书将自动视为所有内部客户端和服务器的有效期，因为所有活动的成员Directory 域信任该域中的企业 CA。 在联盟方案中，发证 CA 必须得到联盟伙伴双方的信任。 如果需要，任一伙伴均可以使用不同的 CA，只要该 CA 同时获得另一个伙伴的信任即可。 此信任最容易由在其受信任根 Ca 中拥有合作伙伴的根 CA 证书的边缘服务器或使用双方信任的第三方 CA 完成。
  
TLS 和 MTLS 有助于防止窃听攻击和中间人攻击。 在中间人攻击中，攻击者通过攻击者的计算机重置两个网络实体之间的通信，而不了解任何一方的知识。 适用于受信任服务器的 TLS 和 Skype for business 服务器规范（仅在拓扑生成器中指定的服务器）通过使用公钥协调的端到端加密减少了部分在应用层上的中间人攻击风险这两个终结点之间的加密，并且攻击者必须拥有一个具有相应私钥的有效且受信任的证书，并将该证书颁发给客户端进行通信的服务的名称以解密通信。 不过，最终，您还是必须遵循有关您的网络基础结构（在此示例中为企业 DNS）的最佳安全做法。 Skype for Business 服务器假设 DNS 服务器的信任方式与域控制器和全局编录的信任方式相同，但 DNS 确实通过阻止攻击者的服务器响应，提供了针对 DNS 劫持攻击的保护级别成功地向欺骗名称发出请求。
  

