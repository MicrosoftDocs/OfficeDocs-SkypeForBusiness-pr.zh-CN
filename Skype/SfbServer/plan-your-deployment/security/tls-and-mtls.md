---
title: Skype for Business Server 的 TLS 和 MTLS
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
ms.assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
description: 传输层安全性 (TLS) 和相互传输层安全性 (MTLS) 协议在 Internet 上提供加密的通信和终结点身份验证。 Skype for Business Server 使用这两种协议创建受信任服务器网络，并确保通过该网络的所有通信都经过加密。 服务器之间的所有 SIP 通信都通过 MTLS 进行。 从客户端到服务器的 SIP 通信通过 TLS 进行。
ms.openlocfilehash: 7acc75ef35a9fe9c3f155ca31f06ac38df371e37
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832012"
---
# <a name="tls-and-mtls-for-skype-for-business-server"></a>Skype for Business Server 的 TLS 和 MTLS
 
传输层安全性 (TLS) 和相互传输层安全性 (MTLS) 协议在 Internet 上提供加密的通信和终结点身份验证。 Skype for Business Server 使用这两种协议创建受信任服务器网络，并确保通过该网络的所有通信都经过加密。 服务器之间的所有 SIP 通信都通过 MTLS 进行。 从客户端到服务器的 SIP 通信通过 TLS 进行。
  
TLS 使用户能够通过其客户端软件来验证他们连接到的 Skype for Business Server 服务器。 在 TLS 连接上，客户端从服务器请求有效证书。 有效证书必须满足以下条件：由受客户端信任的 CA 颁发，且服务器的 DNS 名称必须与证书上的 DNS 名称一致。 如果证书有效，则客户端使用证书中的公钥对用于通信的对称加密密钥进行加密，因此只有证书的原始所有者可以使用其私钥对通信内容进行解密。 生成的连接将会受到信任，之后再不会受到其他受信任的服务器或客户端的质询。 在此上下文中，可将用于 Web 服务的安全套接字层 (SSL) 视为是基于 TLS 的。
  
服务器到服务器连接依赖于 MTLS 进行相互身份验证。 在 MTLS 连接上，发出消息的服务器和接收消息的服务器交换来自相互信任的 CA 的证书。 证书可向一台服务器证明另一台服务器的身份。 在 Skype for Business Server 部署中，所有内部客户端和服务器都会自动将企业 CA 颁发的证书视为有效证书，因为 Active Directory 域的所有成员都信任该域中的企业 CA。 在联盟方案中，发证 CA 必须得到联盟伙伴双方的信任。 如果需要，任一伙伴均可以使用不同的 CA，只要该 CA 同时获得另一个伙伴的信任即可。 通过边缘服务器在受信任的根 CA 中拥有合作伙伴的根 CA 证书，或使用双方信任的第三方 CA，可最轻松地实现此信任。
  
TLS 和 MTLS 有助于防止窃听攻击和中间人攻击。 在中间人攻击中，攻击者在任一方不知情的情况下通过攻击者的计算机重新路由两个网络实体之间的通信。 受信任服务器的 TLS 和 Skype for Business Server 规范 (只有拓扑生成器) 中指定的服务器，通过使用两个终结点之间使用公钥加密协调的端到端加密在应用程序层上部分降低中间人攻击的风险，攻击者必须拥有一个包含相应私钥的有效受信任证书，并颁发给客户端要与之通信以解密通信的服务的名称。 不过，最终，您还是必须遵循有关您的网络基础结构（在此示例中为企业 DNS）的最佳安全做法。 Skype for Business Server 假定 DNS 服务器受信任的方式与域控制器和全局编录的受信任方式相同，但 DNS 通过阻止攻击者的服务器成功响应对欺骗名称的请求，提供了一个级别的 DNS 劫持攻击防护。
  

