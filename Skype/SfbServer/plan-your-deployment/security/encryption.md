---
title: Skype for Business Server 加密
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
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype for Business Server 使用 TLS 和 MTLS 加密即时消息。 所有服务器到服务器流量都需要 MTLS，无论通信是限制在内部网络还是跨内部网络外围。 将 Skype for Business Server 连接到第三方 IPPBX 系统或 SIP 中继时，TLS 是可选的，但强烈建议在中介服务器和媒体网关之间使用 TLS。 如果在此链接上配置了 TLS，则 MTLS 是必需的。 因此，必须使用中介服务器信任的 CA 颁发的证书配置网关。
ms.openlocfilehash: 269a5394f5438802c68dabed17081c71a353a2b5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104228"
---
# <a name="encryption-for-skype-for-business-server"></a>Skype for Business Server 加密
 
Skype for Business Server 使用 TLS 和 MTLS 加密即时消息。 所有服务器到服务器流量都需要 MTLS，无论通信是限制在内部网络还是跨内部网络外围。 将 Skype for Business Server 连接到第三方 IPPBX 系统或 SIP 中继 TLS 是可选的，但强烈建议在中介服务器和媒体网关之间使用 TLS。 如果在此链接上配置了 TLS，则 MTLS 是必需的。 因此，必须使用中介服务器信任的 CA 颁发的证书配置网关。
  
> [!NOTE]
> 2014 年发布了关于 SSL 3.0 的安全公告。 支持在 Skype for Business Server 2015 中禁用 SSL 3.0。 若要了解有关安全公告的详细信息，请参阅[Disabling SSL 3.0 in Lync Server 2013 and Skype for Business Server 2015。](/archive/blogs/uclobby/disabling-ssl-3-0-in-lync-server-2013)<br/>
**安全说明：** 为了确保使用最强加密协议，Skype for Business Server 2015 将按以下顺序向客户端提供 TLS 加密协议 **：TLS 1.2、TLS 1.1、TLS 1.0。** TLS 是 Skype for Business Server 2015 的关键方面，因此维护支持的环境需要 TLS。<br/>
**安全说明：** 为了确保使用最强加密协议，Skype for Business Server 2019 将按以下顺序向客户端提供 TLS 加密协议 **：TLS 1.3、TLS 1.2。** TLS 是 Skype for Business Server 2019 的一个关键方面，因此需要 TLS 才能维护支持的环境。 
  
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

如果 Windows Server 操作系统配置为使用 FIPS 140-2 算法进行系统加密，则 Skype for Business Server 和 Microsoft Exchange Server 2016 支持联邦信息处理标准 (FIPS) 140-2 算法。 若要实现 FIPS 支持，必须配置运行 Skype for Business Server 的每台服务器以支持它。
