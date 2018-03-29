---
title: Skype for Business Server 2015 的 TLS 和 MTLS
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 5/5/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
description: 传输层安全性 (TLS) 和相互传输层安全性 (MTLS) 协议提供 Internet 上的加密通信和终结点身份验证。 业务服务器 2015年的 Skype 使用下列两种协议来创建受信任的服务器的网络，以确保该网络上的所有通信进行都加密。 服务器之间的所有 SIP 通信都通过 MTLS 进行。 从客户端到服务器的 SIP 通信都通过 TLS 进行。
ms.openlocfilehash: 1cc7554ab14e29fd85d2964d1323fccdfd4af604
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tls-and-mtls-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 的 TLS 和 MTLS
 
传输层安全性 (TLS) 和相互传输层安全性 (MTLS) 协议提供 Internet 上的加密通信和终结点身份验证。 业务服务器 2015年的 Skype 使用下列两种协议来创建受信任的服务器的网络，以确保该网络上的所有通信进行都加密。 服务器之间的所有 SIP 通信都通过 MTLS 进行。 从客户端到服务器的 SIP 通信都通过 TLS 进行。
  
TLS 允许用户，他们的客户端软件，通过对 Skype 业务服务器 2015年与它们所连接的服务器进行身份验证。 在 TLS 连接上，客户端从服务器请求有效证书。 有效证书必须满足以下条件：由受客户端信任的 CA 颁发，且服务器的 DNS 名称必须与证书上的 DNS 名称一致。 如果证书有效，则客户端使用证书中的公钥对用于通信的对称加密密钥进行加密，因此只有证书的原始所有者可以使用其私钥对通信内容进行解密。 生成的连接将会受到信任，之后再不会受到其他受信任的服务器或客户端的质询。 在此上下文中，可将用于 Web 服务的安全套接字层 (SSL) 视为是基于 TLS 的。
  
服务器到服务器的连接依赖 MTLS 来进行相互身份验证。 在 MTLS 连接上，发出消息的服务器和接收消息的服务器交换来自相互信任的 CA 的证书。 证书可向一台服务器证明另一台服务器的身份。 在 Skype 业务服务器 2015年部署，由企业 CA 签发的证书期间并不被颁发 CA 吊销其合法性过程中所被自动视为有效所有内部客户端和服务器因为所有成员的活动目录域信任的企业 CA 域中。 在联盟方案中，发证 CA 必须得到联盟伙伴双方的信任。 如果需要，任一伙伴均可以使用不同的 CA，只要该 CA 同时获得另一个伙伴的信任即可。 通过边缘服务器合作伙伴的根 CA 证书在其受信任根 Ca，或者通过使用第三方 CA 信任的双方，这种信任很容易实现。
  
TLS 和 MTLS 有助于防止窃听攻击和中间人攻击。 在人为干预攻击中，攻击者重排两个网络实体通过的任何一方不知情的情况下攻击者的计算机之间的通信。 TLS 和 Skype 业务服务器 2015年规范 （只有在拓扑生成器中指定） 的受信任服务器通过使用协调的公共密钥端对端加密降低手册在中间部分在应用程序层攻击的风险加密的两个端点之间的攻击者必须有有效的受信任证书对应的私钥和颁发给向其客户端通信进行解密通信服务的名称。 不过，最终，您还是必须遵循有关您的网络基础结构（在此示例中为企业 DNS）的最佳安全做法。 Skype 的业务服务器 2015年假定 DNS 服务器都信任的方式相同，域控制器和全局编录是可信的但 DNS 提供的 DNS 劫持攻击的防范级别通过防止攻击者的服务器响应成功地欺骗名称的请求。
  

