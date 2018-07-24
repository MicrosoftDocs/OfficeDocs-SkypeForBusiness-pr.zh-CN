---
title: Skype 业务服务器中的中介服务器的部署指南
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: 本主题介绍中介服务器部署的规划指南。
ms.openlocfilehash: 0e5568b93e0edb0b30bf3edf0893f5eb43ac8d19
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967931"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a>Skype 业务服务器中的中介服务器的部署指南
 
本主题介绍中介服务器部署的规划指南。
  
## <a name="collocated-or-stand-alone-mediation-server"></a>并置或独立中介服务器？

中介服务器，默认情况下，并置在 Standard Edition server 或前端池在中央站点前端服务器上。 可以处理的公用电话交换网 (PSTN) 呼叫数和池中所需的计算机数取决于以下因素：
  
- 中介服务器池控制的对等网关数。
    
- 通过这些网关的高流量时段。
    
- 是其媒体绕过中介服务器的呼叫的呼叫的百分比。
    
规划时，请确保考虑不支持媒体旁路的 PSTN 呼叫和 A/V 会议的媒体处理要求，同时考虑处理必须支持的忙时呼叫数量的信号交互所需的处理要求。 如果您没有足够的 CPU，您将需要部署独立的中介服务器池。 此外，将需要 PSTN 网关、 IP Pbx 和 Sbc 拆分成将由一个池中的并置的中介服务器和一个或多个独立的池中独立的中介服务器控制的子集。
  
如果您部署 PSTN 网关、 Ip-pbx 或缺少的功能与中介服务器池进行交互的会话边界控制器 (Sbc)，他们将需要要与独立包含将单个中介服务器池关联。 您的 PSTN 网关、IP-PBX 或 SBC 需要执行的某些操作包括：
  
- 执行网络层域名系统 (DNS) 负载平衡池中的中介服务器之间 （或否则将流量统一路由到池中的所有中介服务器）。
    
- 接受来自池中任意中介服务器的流量。
    
您可以使用业务规划工具的 Skype 评估是否并置中介服务器与前端池可以处理负载。 如果您的环境无法满足这些要求，您将需要部署独立的中介服务器池。
  
## <a name="central-site-and-branch-site-considerations"></a>中央站点和分支站点注意事项

 在中央站点的中介服务器可用于将呼叫路由到 IP Pbx 或 PSTN 网关在分支站点。 如果部署 SIP 中继，但是，您需要部署中介服务器，其中每个中继终止站点。 在中央站点具有中介服务器路由呼叫的 IP PBX 或 PSTN 网关在分支站点不需要使用媒体绕过，但建议使用媒体绕过。 这是因为，如果可以启用媒体绕过，则可以降低媒体路径延迟，从而改善媒体质量，因为媒体路径不再需要遵循信号路径。 媒体绕过还将减少池中的处理负载。
  
> [!NOTE]
> 媒体旁路将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。 Microsoft 与认证合作伙伴一起对一组 PSTN 网关和 SBC 进行了测试，另外也对 Cisco IP-PBX 进行了一些测试。 仅与产品支持媒体绕过和版本上列出统一通信开放互操作性计划的 Lync Server 上的[浏览测试设备、 基础结构和工具的支持和扩展您的业务体验 Skype](http://partnersolutions.skypeforbusiness.com/solutionscatalog)。 
  
如果分支站点恢复能力是必需的 Survivable Branch Appliance 或前端服务器、 中介服务器和网关的组合必须部署在分支站点。 （具有分支站点恢复能力假设是状态和会议不弹性站点。）规划语音分支站点的指南，请为它仍然应该为相关的业务服务器 2015 Skype 参阅我们[分支站点语音恢复能力的规划](https://technet.microsoft.com/en-us/library/gg398477%28v=ocs.15%29.aspx)文档。
  
对于与 IP PBX 的交互，如果 IP PBX 不正确支持与多个早期对话的早期媒体交互和 RFC 3960 交互，都可以从 IP PBX 到 Lync 终结点的传入呼叫的问候语的几个单词的第一个剪切。 此行为会很多严重是否在中央站点中介服务器的 IP PBX 的呼叫路由路由其中终止分支站点，因为信号完成需要更多时间。 如果您遇到此行为，部署中介服务器在分支站点是减少剪切第一个几个单词的唯一方式。
  
最后，如果您的中央站点有 TDM PBX，或将 IP PBX 不消除 PSTN 网关的需要，您必须部署上连接中介服务器与 PBX 的呼叫路由的网关。
  
> [!NOTE]
> 要提高独立的中介服务器的媒体性能，应在这些服务器的网络适配器上启用接收方缩放 (RSS)。 通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。 有关详细信息，请参阅"[接收端在 Windows Server 中的缩放增强功能](https://go.microsoft.com/fwlink/p/?LinkId=268731)"。 有关如何启用 RSS 的详细信息，请参阅网络适配器文档。 
  

