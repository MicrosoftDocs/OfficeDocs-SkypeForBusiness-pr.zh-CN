---
title: Skype for business 服务器加密
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
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype for business 服务器使用 TLS 和 MTLS 对即时消息进行加密。 无论通信是限制在内部网络还是跨内部网络外围，所有服务器到服务器的通信都需要使用 MTLS。 将 Skype for Business 服务器连接到第三方 IPPBX 系统或 SIP 中继 TLS 是可选的，但强烈建议在中介服务器和媒体网关之间使用 TLS。 如果在此链接上配置了 TLS，则 MTLS 是必需的。 因此，网关必须配置来自中介服务器信任的 CA 的证书。
ms.openlocfilehash: 64e7199cf761ad7d7ec18b00e8f3b7f27fed6f04
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815660"
---
# <a name="encryption-for-skype-for-business-server"></a>Skype for business 服务器加密
 
Skype for business 服务器使用 TLS 和 MTLS 对即时消息进行加密。 无论通信是限制在内部网络还是跨内部网络外围，所有服务器到服务器的通信都需要使用 MTLS。 将 Skype for Business 服务器连接到第三方 IPPBX 系统或 SIP 时中继 TLS 是可选的，但强烈建议在中介服务器和媒体网关之间使用。 如果在此链接上配置了 TLS，则 MTLS 是必需的。 因此，网关必须配置来自中介服务器信任的 CA 的证书。
  
> [!NOTE]
> 2014 年发布了关于 SSL 3.0 的安全公告。 在 Skype for business Server 2015 中禁用 SSL 3.0 是受支持的选项。 若要了解有关安全公告的详细信息，请参阅[在 Lync Server 2013 和 Skype for Business Server 2015 中禁用 SSL 3.0](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/)。<br/>
**安全说明：** 为确保使用最强的加密协议，Skype for Business Server 2015 将按以下顺序向客户端提供 TLS 加密协议： **tls 1.2、tls 1.1、tls 1.0**。 TLS 是 Skype for Business Server 2015 的一个重要方面，因此它是维护受支持的环境所必需的。<br/>
**安全说明：** 为确保使用最强的加密协议，Skype for Business Server 2019 将按以下顺序向客户端提供 TLS 加密协议： **tls 1.3，tls 1.2**。 TLS 是 Skype for Business Server 2019 的一个重要方面，因此它是维护受支持的环境所必需的。 
  
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
> 有关设置混合的详细信息，请参阅[规划混合连接](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)。
  
## <a name="fips"></a>FIPS

如果 Windows Server 操作系统配置为使用 FIPS 140-2 算法进行系统加密，则 Skype for business 服务器和 Microsoft Exchange Server 2016 的操作支持联邦信息处理标准（FIPS）140-2 算法. 若要实现 FIPS 支持，必须配置运行 Skype for Business 服务器的每台服务器以支持它。
  

