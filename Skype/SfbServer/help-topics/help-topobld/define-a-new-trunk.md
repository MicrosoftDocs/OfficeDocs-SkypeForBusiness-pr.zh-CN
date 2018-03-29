---
title: 定义新干线
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 您定义新的会话启动协议 (SIP) 干线通过提供以下信息：
ms.openlocfilehash: ec0832c0e9cd103b034ada5b0ddc23391294b5ed
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="f31f9-103">定义新干线</span><span class="sxs-lookup"><span data-stu-id="f31f9-103">Define a New Trunk</span></span>
 
<span data-ttu-id="f31f9-104">您定义新的会话启动协议 (SIP) 干线通过提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="f31f9-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>
  
- <span data-ttu-id="f31f9-105">**干线名称**： 表明此中继拓扑中的唯一名称</span><span class="sxs-lookup"><span data-stu-id="f31f9-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>
    
- <span data-ttu-id="f31f9-106">**关联的 PSTN 网关**： 部署从列表中选择已部署和配置 PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="f31f9-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>
    
- <span data-ttu-id="f31f9-107">**IP/PSTN 网关的侦听端口**： IP PBX 或 PSTN 网关监听的端口。</span><span class="sxs-lookup"><span data-stu-id="f31f9-107">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on.</span></span> <span data-ttu-id="f31f9-108">从所有配置中部署其他干线侦听端口必须唯一</span><span class="sxs-lookup"><span data-stu-id="f31f9-108">Must be unique from all other trunk listening ports configured in your deployment</span></span>
    
- <span data-ttu-id="f31f9-109">**SIP 传输协议**： 从列表中选择 TCP 或 TLS</span><span class="sxs-lookup"><span data-stu-id="f31f9-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>
    
- <span data-ttu-id="f31f9-110">**相关中介服务器**： 从列表中选择中介服务器部署并在您的部署配置</span><span class="sxs-lookup"><span data-stu-id="f31f9-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>
    
- <span data-ttu-id="f31f9-111">**相关中介服务器端口**： 将端口值设置为等于该 SIP 中继将使用中介服务器的 TCP 或 TLS 端口值</span><span class="sxs-lookup"><span data-stu-id="f31f9-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="f31f9-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f31f9-112">See also</span></span>

#### 

[<span data-ttu-id="f31f9-113">在业务服务器 2015年的 Skype 的 M:N 干线</span><span class="sxs-lookup"><span data-stu-id="f31f9-113">M:N trunk in Skype for Business Server 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)
#### 

[<span data-ttu-id="f31f9-114">如何实现 SIP 中继？</span><span class="sxs-lookup"><span data-stu-id="f31f9-114">How do I implement SIP trunking?</span></span>](http://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)

