---
title: Skype 业务服务器的 TLS 和 MTLS
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
description: 传输层安全性 (TLS) 和相互传输层安全性 (MTLS) 协议提供 Internet 上的加密通信和终结点身份验证。 Skype 业务服务器使用这两项协议来创建受信任的服务器网络和确保网络上的所有通信进行都加密。 服务器之间的所有 SIP 通信都通过 MTLS 进行。 从客户端到服务器的 SIP 通信都通过 TLS 进行。
ms.openlocfilehash: b00ce2102d858db36500f78af47596677ce6d6dd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213499"
---
# <a name="tls-and-mtls-for-skype-for-business-server"></a>Skype 业务服务器的 TLS 和 MTLS
 
传输层安全性 (TLS) 和相互传输层安全性 (MTLS) 协议提供 Internet 上的加密通信和终结点身份验证。 Skype 业务服务器使用这两项协议来创建受信任的服务器网络和确保网络上的所有通信进行都加密。 服务器之间的所有 SIP 通信都通过 MTLS 进行。 从客户端到服务器的 SIP 通信都通过 TLS 进行。
  
TLS 启用用户，他们的客户端软件，通过进行身份验证连接到业务 Server 服务器 Skype。 在 TLS 连接上，客户端从服务器请求有效证书。 有效证书必须满足以下条件：由受客户端信任的 CA 颁发，且服务器的 DNS 名称必须与证书上的 DNS 名称一致。 如果证书有效，则客户端使用证书中的公钥对用于通信的对称加密密钥进行加密，因此只有证书的原始所有者可以使用其私钥对通信内容进行解密。 生成的连接将会受到信任，之后再不会受到其他受信任的服务器或客户端的质询。 在此上下文中，可将用于 Web 服务的安全套接字层 (SSL) 视为是基于 TLS 的。
  
服务器到服务器的连接依赖 MTLS 来进行相互身份验证。 在 MTLS 连接上，发出消息的服务器和接收消息的服务器交换来自相互信任的 CA 的证书。 证书可向一台服务器证明另一台服务器的身份。 Skype 业务服务器部署，在由企业 CA 颁发的证书的过程期间，而不由发证 CA 吊销其有效性中都会自动认为有效所有内部客户端和服务器因为活动中的所有成员目录域信任企业 CA 的域中。 在联盟方案中，发证 CA 必须得到联盟伙伴双方的信任。 如果需要，任一伙伴均可以使用不同的 CA，只要该 CA 同时获得另一个伙伴的信任即可。 通过边缘服务器具有合作伙伴的根 CA 证书中其受信任的根 Ca，或使用第三方 CA 受信任的双方，很容易实现此信任。
  
TLS 和 MTLS 有助于防止窃听攻击和中间人攻击。 在中间中中间人攻击中，攻击者重排通过攻击者的计算机的任何一方不知情的情况下的两个网络实体之间的通信。 TLS 和 Skype 的受信任服务器的服务器 （仅在拓扑生成器中指定） 的业务服务器规格缓解部分应用程序图层上手册中中间攻击的风险使用协调使用公钥的端到端加密加密之间的两个端点，攻击者必须有对应的私钥与证书有效且受信任和颁发给到客户端通信进行解密通信服务的名称。 不过，最终，您还是必须遵循有关您的网络基础结构（在此示例中为企业 DNS）的最佳安全做法。 Skype 业务 server 假定 DNS 服务器受信任的域控制器和全局编录是受信任，但 DNS 提供针对 DNS 劫持攻击保护级别通过防止攻击者的服务器响应方式相同成功地为欺骗名称的请求。
  

