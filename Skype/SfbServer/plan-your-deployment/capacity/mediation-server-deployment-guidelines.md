---
title: 中介服务器部署指南Skype for Business Server
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
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: 本主题介绍中介服务器部署的规划准则。
ms.openlocfilehash: b65ff1335c32c17e61da97d90d290cf81b38ca33
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773552"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a>中介服务器部署指南Skype for Business Server
 
本主题介绍中介服务器部署的规划准则。
  
## <a name="collocated-or-stand-alone-mediation-server"></a>并站中介服务器还是独立中介服务器？

默认情况下，中介服务器并Standard Edition中央站点前端池中的前端服务器或前端服务器上。 可以处理的公用电话交换网 (PSTN) 呼叫的数量，池中所需的计算机数量将取决于：
  
- 中介服务器池控制对等网关的数量。
    
- 通过这些网关的高流量时段。
    
- 媒体绕过中介服务器的呼叫所占的呼叫百分比。
    
在规划时，请务必考虑不支持媒体旁路的 PSTN 呼叫和 A/V 会议的媒体处理要求，以及处理需要支持的忙时呼叫数的信号交互所需的处理。 如果没有足够的 CPU，则需要部署中介服务器独立池。 此外，PSTN 网关、IP-PBX 和 SDC 将需要拆分为子集，这些子集由一个池中的并站中介服务器和一个或多个独立池中独立的中介服务器控制。
  
如果部署的 PSTN 网关、IP-PBX 或会话边界控制器 (SDC) 缺少与中介服务器池交互的能力，则需要将其与由单个中介服务器组成的独立池相关联。 PSTN 网关、IP-PBXs SDC 需要执行以下一些操作：
  
- 在池 (中的中介服务器之间执行网络层域名系统 (DNS) 负载平衡) 。
    
- 接受来自池中任何中介服务器的流量。
    
可以使用 Skype for Business 规划工具来评估将中介服务器与前端池并排是否可以处理负载。 如果您的环境不能满足这些要求，则需要部署独立的中介服务器池。
  
## <a name="central-site-and-branch-site-considerations"></a>中央站点和分支站点注意事项

 中央站点的中介服务器可用于为分支站点的 IP-PBX 或 PSTN 网关路由呼叫。 但是，如果部署 SIP 中继，您必须在每个中继终止的站点上部署中介服务器。 在中央站点部署中介服务器为分支站点上的 IP-PBX 或 PSTN 网关路由呼叫不需要使用媒体旁路，但建议使用媒体旁路。 这是因为，如果可以启用媒体旁路，它将减少媒体路径延迟，从而改善媒体质量，因为媒体路径不需要遵循信号路径。 媒体绕过还将减少池中的处理负载。
  
> [!NOTE]
> 媒体旁路不会与每个 PSTN 网关、IP-PBX 和 SBC 互操作。 Microsoft 已经与认证合作伙伴一起测试了一组 PSTN 网关和 SDC，并且已经使用 Cisco IP-PBX 进行了一些测试。 只有统一通信开放式互操作性计划 - Lync Server 中列出的产品和版本才支持媒体旁路功能，这些版本位于探索支持并扩展您的 Skype for Business体验的经过测试[的设备、基础结构和工具](http://partnersolutions.skypeforbusiness.com/solutionscatalog)。 
  
如果要求具有分支站点恢复能力，则必须在分支站点部署 Survivable Branch Appliance 或部署前端服务器、中介服务器和网关的组合。  (分支站点恢复能力的假设是，状态和会议在站点中无法恢复。) 有关分支站点语音规划的指导，请参阅 Skype for Business Server 中的规划[企业语音 恢复能力](../enterprise-voice-solution/enterprise-voice-resiliency.md)。
  
对于与 IP-PBX 的交互，如果 IP-PBX 无法正确支持与多个早期对话的早期媒体交互和 RFC 3960 交互，则对于从 IP-PBX 到 Lync 终结点的传入呼叫，可能会截断问候语的前几个单词。 如果中央站点上的中介服务器为 IP-PBX 路由呼叫，其中路由终止于分支站点，这种行为可能更为严重，因为完成信号需要更长时间。 如果遇到此行为，在分支站点部署中介服务器是减少截断前几个单词的唯一方法。
  
最后，如果中央站点具有 TDM PBX，或者 IP-PBX 仍然需要 PSTN 网关，则必须在连接中介服务器和 PBX 的呼叫路由上部署网关。
  
> [!NOTE]
> 若要提高独立中介服务器的媒体性能，您应在这些服务器的网络适配器 (RSS) 启用接收端缩放。 通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。 有关详细信息，请参阅"[Receive-Side Scaling Enhancements in Windows Server"。](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11)) 若要详细了解如何启用 RSS，请参阅网络适配器文档。 
