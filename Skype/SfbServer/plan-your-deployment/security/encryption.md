---
title: Skype for Business Server 2015 加密
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 9/15/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: 商业服务器 2015年的 Skype 使用 TLS 和 MTLS 即时消息进行加密。 无论通信是限制在内部网络还是跨内部网络外围，所有服务器到服务器的通信都需要使用 MTLS。 当连接到第三方 IPPBX 系统或 SIP 中继 TLS Skype 业务服务器 2015年时可选但强烈建议中介服务器和媒体网关之间。 如果在此链接上配置了 TLS，则 MTLS 是必需的。 因此，网关必须配置有中介服务器受信任的 CA 的证书。
ms.openlocfilehash: bf17f2c8ff8180fa5622957c665da3f4608ca833
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="encryption-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 加密
 
商业服务器 2015年的 Skype 使用 TLS 和 MTLS 即时消息进行加密。 无论通信是限制在内部网络还是跨内部网络外围，所有服务器到服务器的通信都需要使用 MTLS。 当连接到第三方 IPPBX 系统或 SIP 中继 TLS Skype 业务服务器 2015年时可选但强烈建议中介服务器和媒体网关之间。 如果在此链接上配置了 TLS，则 MTLS 是必需的。 因此，网关必须配置有中介服务器受信任的 CA 的证书。
  
> [!NOTE]
> 2014 年发布了关于 SSL 3.0 的安全公告。 为业务服务器 2015年禁用 SSL 3.0 在 Skype 是受支持的选项。 有关安全公告的详细信息，请参阅[在 Lync Server 2013 和 Skype 的业务服务器 2015年禁用 SSL 3.0](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/)。 
  
> [!安全说明] 来确保最强的加密协议，Skype 的业务服务器 2015年将向客户端提供 TLS 加密协议顺序如下： **TLS 1.2，TLS 1.1，TLS 1.0**。 TLS 是 Skype 业务服务器 2015年的一个重要方面，因此需要以保持受支持的环境。 
  
下表汇总了每种类型的通信的协议要求。 
  
**通信保护**

|**通信量类型**|**受**|
|:-----|:-----|
|服务器到服务器  <br/> |MTLS  <br/> |
|客户端到服务器  <br/> |TLS  <br/> |
|即时消息和状态  <br/> |TLS  <br/> |
|音频、视频和媒体的桌面共享  <br/> |SRTP  <br/> |
|桌面共享（信号）  <br/> |TLS  <br/> |
|Web 会议  <br/> |TLS  <br/> |
|会议内容下载、通讯簿下载和通讯组扩展  <br/> |HTTPS  <br/> |
   
## <a name="media-encryption"></a>媒体加密

媒体通信使用安全 RTP (SRTP) 进行加密，SRTP 是为 RTP 通信提供保密性、身份验证和重播攻击保护的实时传输协议 (RTP) 的配置文件。此外，中介服务器与其内部下一个跃点之间的双向媒体流也使用 SRTP 进行加密。中介服务器与媒体网关之间的双向媒体流的加密是可选的，但建议进行加密。中介服务器能够支持对媒体网关进行加密，但该网关必须支持 MTLS 和证书存储。
  
> [!NOTE]
> 如果您要实现的混合环境，还必须修改有关业务服务器 2015年加密级别 Skype。 默认情况下，加密级别为“必需”。 通过 Skype 业务服务器管理外壳程序，必须为支持更改此设置。 有关混合设置的详细信息，请参阅部署文档中[移动业务联机到内部部署 Skype 的用户](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-skype-for-business-online-to-on-premises.md)。
  
## <a name="fips"></a>FIPS

如果 Windows 服务器操作系统的系统被配置为使用 FIPS 140-2 算法的系统支持联邦信息处理标准 (FIPS) 140-2 算法运行 Skype 业务服务器 2015年和 Microsoft Exchange Server 2016加密技术。 若要实现 FIPS 支持，您必须配置运行 Skype 业务服务器 2015 来支持它的每个服务器。
  

