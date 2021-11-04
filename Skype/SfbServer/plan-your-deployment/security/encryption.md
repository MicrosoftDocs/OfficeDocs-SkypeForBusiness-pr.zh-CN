---
title: 加密Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype for Business Server TLS 和 MTLS 加密即时消息。 所有服务器到服务器流量都需要 MTLS，无论通信是限制在内部网络还是跨内部网络外围。 在将Skype for Business Server IPPBX 系统或 SIP 中继连接到第三方 IPPBX 系统或 SIP 中继时，TLS 是可选的，但强烈建议在中介服务器和媒体网关之间使用 TLS。 如果在此链接上配置了 TLS，则 MTLS 是必需的。 因此，必须使用中介服务器信任的 CA 颁发的证书配置网关。
ms.openlocfilehash: 5a7f4d562c3433a2ca44c61659aa4ca2fe7ed271
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746698"
---
# <a name="encryption-for-skype-for-business-server"></a>加密Skype for Business Server
 
Skype for Business Server TLS 和 MTLS 加密即时消息。 所有服务器到服务器流量都需要 MTLS，无论通信是限制在内部网络还是跨内部网络外围。 在将Skype for Business Server IPPBX 系统或 SIP 中继连接到第三方 IPPBX 系统或 SIP 中继时，TLS 是可选的，但强烈建议在中介服务器和媒体网关之间使用 TLS。 如果在此链接上配置了 TLS，则 MTLS 是必需的。 因此，必须使用中介服务器信任的 CA 颁发的证书配置网关。
  
> [!NOTE]
> 2014 年发布了关于 SSL 3.0 的安全公告。 支持在 Skype for Business Server 2015 中禁用 SSL 3.0。 若要了解有关安全公告的详细信息，请参阅[Disabling SSL 3.0 in Lync Server 2013 and Skype for Business Server 2015。](/archive/blogs/uclobby/disabling-ssl-3-0-in-lync-server-2013)<br/>
**安全说明：** 为确保使用最强加密协议，Skype for Business Server 2015 将按以下顺序向客户端提供 TLS 加密协议 **：TLS 1.2、TLS 1.1、TLS 1.0。** TLS 是 2015 Skype for Business Server的一个关键方面，因此维护受支持的环境需要 TLS。<br/>
**安全说明：** 为确保使用最强加密协议，Skype for Business Server 2019 将按以下顺序向客户端提供 TLS 加密协议 **：TLS 1.3、TLS 1.2**。 TLS 是 2019 Skype for Business Server的一个关键方面，因此维护受支持的环境需要 TLS。 
  
下表汇总了每种类型的通信的协议要求。 
  
**通信保护**

|**通信类型**|**保护协议**|
|:-----|:-----|
|服务器到服务器  <br/> |MTLS  <br/> |
|客户端到服务器  <br/> |TLS  <br/> |
|即时消息和状态  <br/> |TLS  <br/> |
|音频、视频和媒体的桌面共享  <br/> |SRTP  <br/> |
|桌面共享（信号）  <br/> |TLS  <br/> |
|Web 会议  <br/> |TLS  <br/> |
|会议内容下载、通讯簿下载和通讯组扩展  <br/> |HTTPS  <br/> |
   
## <a name="media-encryption"></a>媒体加密

媒体通信是使用安全 RTP (SRTP) 进行加密的，SRTP 是为 RTP 通信提供保密性、身份验证和重播攻击保护的实时传输协议 (RTP) 的配置文件。 此外，在中介服务器和其内部下一个跃点之间的双向媒体也使用 SRTP 进行加密。 中介服务器与媒体网关之间的两个方向的媒体流（可选）已加密，建议进行加密。 中介服务器能够支持对媒体网关进行加密，但该网关必须支持 MTLS 和证书存储。
  
> [!NOTE]
> 有关设置混合连接的信息，请参阅规划 [混合连接](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)。
  
## <a name="fips"></a>FIPS

Skype for Business Server 和 Microsoft Exchange Server 2016 支持联邦信息处理标准 (FIPS) 140-2 算法（如果将 Windows Server 操作系统配置为使用 FIPS 140-2 算法进行系统加密）。 若要实现 FIPS 支持，必须配置每台运行 FIPS Skype for Business Server以支持它。
