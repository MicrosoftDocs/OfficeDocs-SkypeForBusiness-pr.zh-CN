---
title: Skype 加密业务服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype 业务服务器使用 TLS 和 MTLS 来加密即时消息。 无论通信是限制在内部网络还是跨内部网络外围，所有服务器到服务器的通信都需要使用 MTLS。 当业务服务器 Skype 连接到第三方 IPPBX 系统或 SIP 中继 TLS 是可选的但强烈建议在中介服务器与媒体网关之间。 如果在此链接上配置了 TLS，则 MTLS 是必需的。 因此，必须使用从中介服务器信任的 CA 证书配置网关。
ms.openlocfilehash: 7ed4297ef766b769827b6805087d02f0ad708fe7
ms.sourcegitcommit: 4967c9b1010a444475dcfbdb6dd3c058494449d9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2019
ms.locfileid: "30069630"
---
# <a name="encryption-for-skype-for-business-server"></a>Skype 加密业务服务器
 
Skype 业务服务器使用 TLS 和 MTLS 来加密即时消息。 无论通信是限制在内部网络还是跨内部网络外围，所有服务器到服务器的通信都需要使用 MTLS。 当业务服务器 Skype 连接到第三方 IPPBX 系统或 SIP 中继 TLS 是可选的但强烈建议在中介服务器与媒体网关之间。 如果在此链接上配置了 TLS，则 MTLS 是必需的。 因此，必须使用从中介服务器信任的 CA 证书配置网关。
  
> [!NOTE]
> 2014 年发布了关于 SSL 3.0 的安全公告。 为业务服务器 2015年禁用中 Skype SSL 3.0 是受支持的选项。 若要了解有关顾问的安全性的详细信息，请参阅[Lync Server 2013 和 Skype 的业务服务器 2015年中禁用 SSL 3.0](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/)。<br/>
**安全说明：** 要确保使用的最强的加密协议，业务服务器 2015年的 Skype 将按以下顺序的 TLS 加密协议为客户端提供： **TLS 1.2 TLS 1.1、 TLS 1.0**。 TLS 是业务服务器 2015年的 Skype 的一个重要方面，因此需要为了保持受支持的环境。<br/>
**安全说明：** 要确保使用的最强的加密协议，业务服务器 2019年的 Skype 将按以下顺序的 TLS 加密协议为客户端提供： **TLS 1.3、 TLS 1.2**。 TLS 是业务服务器 2019年的 Skype 的一个重要方面，因此需要为了保持受支持的环境。 
  
下表汇总了每种类型的通信的协议要求。 
  
**通信保护**

|**通信类型**|**保护协议**|
|:-----|:-----|
|服务器到服务器  <br/> |MTLS  <br/> |
|客户端到服务器  <br/> |TLS  <br/> |
|即时消息和状态  <br/> |TLS   <br/> |
|音频、视频和媒体的桌面共享  <br/> |SRTP  <br/> |
|桌面共享（信号）  <br/> |TLS  <br/> |
|Web 会议  <br/> |TLS  <br/> |
|会议内容下载、通讯簿下载和通讯组扩展  <br/> |HTTPS  <br/> |
   
## <a name="media-encryption"></a>媒体加密

媒体通信使用安全 RTP (SRTP) 进行加密，SRTP 是为 RTP 通信提供保密性、身份验证和重播攻击保护的实时传输协议 (RTP) 的配置文件。此外，中介服务器与其内部下一个跃点之间的双向媒体流也使用 SRTP 进行加密。中介服务器与媒体网关之间的双向媒体流的加密是可选的，但建议进行加密。中介服务器能够支持对媒体网关进行加密，但该网关必须支持 MTLS 和证书存储。
  
> [!NOTE]
> 有关设置混合的详细信息，请参阅[规划混合连接性](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)。
  
## <a name="fips"></a>FIPS

如果在 Windows Server 操作系统配置为使用 FIPS 140-2 算法来进行系统加密 Business Server 和 Microsoft Exchange Server 2016 Skype 操作联邦信息处理标准 (FIPS) 140-2 算法的支持. 若要实现 FIPS 支持，必须配置每台运行 Skype 业务服务器支持它。
  

