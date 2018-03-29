---
title: Skype for Business Server 2015 中会议的基于位置的路由
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 10/13/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: 规划业务服务器企业语音会议在 Skype 的基于位置的路由，包括咨询呼叫转移。
ms.openlocfilehash: 4cfa76e10ed0107c1dc1fe4c1759a89536529ada
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中会议的基于位置的路由
 
规划业务服务器企业语音会议在 Skype 的基于位置的路由，包括咨询呼叫转移。
  
基于位置的路由，使得可能限制电话 VoIP 终结点和 PSTN 基于位置的调用方的端点之间的路由。 基于位置的路由会议使您能够强制基于位置的路由规则的会议 （即会议） 以防止 PSTN 收费旁路。 应用程序监视活动会议，并加强基于位置的路由限制根据用户参与的位置。 另外会议应用程序基于位置的路由，使咨询涉及 PSTN 终结点的传输到基于位置的路由限制的强制执行。
  
绕过一种机制来防止 PSTN 电话业务会议到 Skype 提供基于位置的路由会议应用程序。 应用程序监视活动会议，并加强基于位置的路由限制适用于业务用户参与 Skype 的位置。 
  
基于位置的路由会议应用程序确定是否满足以下条件时才能实施商务会议 Skype 在基于位置的路由：
  
- 会议组织者已启用基于位置的路由。 基于位置的路由限制将只应用于通过启用基于位置的路由的用户组织的会议。
    
- PSTN 终结点中至少有一名会议参与者。 基于位置的路由限制是仅适用于包括 PSTN 终结点的会议。
    
- 用于将会议桥接到 PSTN 的 PSTN 网关所在的网络站点以及组织者和参与者用于从中连接的网络站点。 
    
基于位置的路由的会议应用程序可防止 Skype 业务用户和 PSTN 终结点从不同的网络站点到同一个会议的参与。 如果会议组织者已启用基于位置的路由，会议应用程序强制执行以下限制：
  
- 参加商务会议 Skype 的终结点取决于终结点已加入会议，此限制调整作为连接终结点离开和新的终结点加入会议。 如果组织者和参与者加入 Skype 业务会议从相同的网络站点，然后 PSTN 终结点、 从同一网络上的其他参与者，从不同的网络站点的其他参与者或参与者来自未知的网络站点允许加入。
    
- 如果组织者和参与者从不同或未知的网络站点加入会议，则如果 PSTN 呼叫从启用了基于位置的路由的 SIP 中继传入，将不允许 PSTN 终结点加入会议。
    
- 如果组织者和参与者所有加入同一个网络站点从会议而没有参加同一个会议与 PSTN 的参与者，从不同的网络站点业务端点的 Skype 不允许参加会议。
    
下表总结了这些会议基于位置的路由限制。 
  
| |
|**用户在任意给定时刻会议中**|**允许参加会议的用户**|**用户不允许参加会议**|
|:-----|:-----|:-----|
|Skype 业务 VoIP 客户端用户从单个网络站点  <br/> |Skype 的业务 VoIP 客户端用户从相同的网络站点  <br/> Skype 业务 VoIP 客户端用户从不同的网络站点  <br/> Skype 业务 VoIP 客户端用户从未知的网络站点  <br/> 联合的 Skype 业务 VoIP 客户端用户  <br/> 从 PSTN 终结点加入的用户  <br/> |无  <br/> |
|Skype 业务 VoIP 客户端用户从一个未知的网络站点  <br/> |Skype 业务 VoIP 客户端用户从任何站点  <br/> 从未知网站业务 VoIP 客户端用户的 Skype  <br/> 联合的 Skype 业务 VoIP 客户端用户  <br/> |通过 PSTN 终结点加入的用户  <br/> |
|Skype 业务 VoIP 客户端用户从不同的网络站点  <br/> |从任何网络站点业务 VoIP 客户端用户的 Skype  <br/> Skype 业务 VoIP 客户端用户从未知的网络站点  <br/> 联合的 Skype 业务 VoIP 客户端用户  <br/> |通过 PSTN 终结点加入的用户  <br/> |
|Skype 业务 VoIP 客户端用户从单个网络站点和用户加入从 PSTN 终结点  <br/> |Skype 的业务 VoIP 客户端用户从相同的网络站点  <br/> |Skype 业务 VoIP 客户端用户从不同的网络站点  <br/> Skype 业务 VoIP 客户端用户从未知的网络站点  <br/> 联合的 Skype 业务 VoIP 客户端用户  <br/> |
   
以下是其他特征的会议应用程序基于位置的路由：
  
- 当不允许用户加入会议提供基于位置的路由限制，大会对的调用将被拒绝，Skype 业务客户端将报表调用没有完成，或已经结束。
    
- 加入会议执行进行基于位置的路由不会受到限制，如果未启用基于位置的路由干线通过加入该终结点，而不管其状态如何参加会议 PSTN 终结点。
    
- 通过不出口到 PSTN 呼叫的 SIP 中继连接到中介服务器的 PBX 系统都不具有相同为 Skype 的执行进行为商业用户位于同一个网络站点在其中定义 SIP 中继。 例如，PSTN 终结点将能够参加与 PBX 用户和业务用户的 Skype 的会议，如果它们位于同一个网络站点;否则，PSTN 终结点，不会允许 PBX 用户是否在不同的网络站点比企业用户 Skype 参加会议。
    
> [!NOTE]
> 有了 Skype for Business 累积更新 4，将会观察到下表中的行为： 
  
|**用户**|**另一方**|**操作**|**结果**|
|:-----|:-----|:-----|:-----|
|Skype for Business 移动  <br/> |PSTN  <br/> |Skype for Business 移动进行 PSTN 通话。Skype for Business 移动然后将通话升级为会议自动助理 (CAA)。  <br/> |呼叫被阻止，并显示相应的错误消息。  <br/> |
|Skype for Business 移动  <br/> |Skype for Business 客户端或联盟用户  <br/> |联合用户的客户端是 VoIP 呼叫到 Business Mobile Location-Based 路由用户的 Skype，任何一方将升级到 CAA。  <br/> |升级呼叫被阻止，并显示相应的错误消息。  <br/> |
   
## <a name="consultative-call-transfers"></a>咨询呼叫转接

除了强制基于位置的路由添加到 Skype 业务会议，为会议应用程序基于位置的路由加强对到 PSTN 端点的出口咨询呼叫转移的基于位置的路由限制。 咨询电话传输是其中的一方转移给新用户调用的两个当事方之间建立的调用。 例如，PSTN 端点调用用户 (业务被呼叫方的 Skype)。 用户 A 决定 PSTN 用户应该被转发到用户 B (Skype 业务用户)。 用户 A 位置的呼叫 PSTN 用户处于暂停状态，然后调用用户 B 同意与 PSTN 用户交谈。 用户 A 将暂挂电话传送到用户 b。
  
**咨询呼叫转移呼叫流**

![会议的基于位置的路由图示](../../media/LocationBasedRoutingForConferencing.jpg)
  
当用户启用基于位置的路由启动 PSTN 终结点 （上图所示） 的咨询呼叫转移时，这将创建两个活动调用，业务用户 A，Skype 与 PSTN 用户之间的一次调用，另一种为 Skype 之间通过基于位置的路由的会议应用程序强制执行业务用户 A 和 Skype 为业务用户 B 以下行为：
  
- 如果 SIP 中继路由 PSTN 呼叫有权重新路由到网络站点位置业务用户 B （即转移目标） 的 Skype 的位置、 然后将允许呼叫转移; PSTN 呼叫否则，将阻止咨询呼叫转移。 此授权转移的方位置处于同一路由组路由到 PSTN 的端点的活动调用 SIP 中继网络站点上执行基于。 
    
- 如果入站的 PSTN 呼叫路由 SIP 中继无权访问到网络站点位置被转移的方 (针对业务用户 B 的 Skype) 的位置或被转移的方位于未知的网络站点的路由呼叫，咨询呼叫转移到PSTN 终结点 （即呼叫转移目标） 将被阻止。
    
下表描述如何基于位置的路由限制所应用的基于位置的路由咨询呼叫转移的会议应用程序。 尽管 PBX 终结点并非直接与某个网络站点关联，但可以为 PBX 连接到的 SIP 中继分配一个网络站点。 因此，PBX 终结点可以间接与网络站点关联。
  

|**网络站点的呼叫转接方**|**呼叫转移目标网络站点**|**行为**|
|:-----|:-----|:-----|
|PSTN 终结点  <br/> |在同一个网络站点 （即 1） 中的业务用户的 Skype  <br/> |咨询转接将被允许  <br/> |
|PSTN 终结点  <br/> |在不同的网络站点 （如站点 2） 中的业务用户的 Skype  <br/> |咨询转接将被禁止  <br/> |
|PSTN 终结点  <br/> |未知的网络站点中的业务用户的 Skype  <br/> |咨询转接将被禁止  <br/> |
|PSTN 终结点  <br/> |联合的 Skype 业务用户  <br/> |咨询转接将被禁止  <br/> |
|PSTN 终结点  <br/> |PBX 终结点位于相同站点（即站点 1）  <br/> |咨询转接将被允许  <br/> |
|PSTN 终结点  <br/> |PBX 终结点位于不同站点（即站点 2）  <br/> |咨询转接将被禁止  <br/> |
|PBX 终结点位于相同站点（即站点 1）  <br/> |PSTN 终结点  <br/> |咨询转接将被允许  <br/> |
|PBX 终结点位于不同站点（即站点 2）  <br/> |PSTN 终结点  <br/> |咨询转接将被禁止  <br/> |
|PBX 终结点位于任意站点  <br/> |在同一个网络站点 （即 1） 中的业务用户的 Skype  <br/> |咨询转接将被允许  <br/> |
|PBX 终结点位于任意站点  <br/> |在不同的网络站点 （如站点 2） 中的业务用户的 Skype  <br/> |咨询转接将被允许  <br/> |
|PBX 终结点位于任意站点  <br/> |未知的网络站点中的业务用户的 Skype  <br/> |咨询转接将被允许  <br/> |
|PBX 终结点位于任意站点  <br/> |联合的 Skype 业务用户  <br/> |咨询转接将被允许  <br/> |
   
## <a name="requirements"></a>要求

对于会议的应用程序要求在所有前端池和标准版服务器拓扑中部署 Skype 业务服务器，或是 Lync 服务器 2013年累计更新 2年基于位置的路由。 如果您的拓扑结构中的某些服务器上未安装这些服务器版本，基于位置的路由限制不能充分实施在会议上和咨询呼叫转移。
  
下表列出了服务器角色和支持基于位置的路由版本的组合。
  

|**前端的池库版本**|**中介服务器版本**|**支持**|
|:-----|:-----|:-----|
|Skype 业务服务器或 Lync Server 2013 累积更新 2  <br/> |Skype 业务服务器或 Lync Server 2013 累积更新 2  <br/> |是  <br/> |
|Lync Server 2013 累积更新 2  <br/> |Lync Server 2013 累积更新 1  <br/> |否  <br/> |
|Lync Server 2013 累积更新 2  <br/> |Lync Server 2010  <br/> |否  <br/> |
|Lync Server 2013 累积更新 2  <br/> |Office Communications Server 2007 R2  <br/> |否  <br/> |
|Lync Server 2013 累积更新 1  <br/> |任意  <br/> |否  <br/> |
|Lync Server 2010  <br/> |任意  <br/> |否  <br/> |
|Office Communications Server 2007 R2  <br/> |任意  <br/> |否  <br/> |
   
## <a name="configuration-of-location-based-routing-for-conferencing"></a>会议的基于位置的路由的配置

基于位置的路由的会议应用程序依赖的基于位置的路由配置。 主要配置如下： 
  
- 加入会议的参与者的位置基于其网络站点进行确定。 网络站点和其关联的网络子网必须为了强制基于位置的路由定义中 Skype 业务服务器。
    
- 要加强会议的基于位置的路由，Skype 业务参与者必须启用基于位置的路由。
    
- 要强制加入会议的 PSTN 终结点的基于位置的路由，必须基于位置的路由配置用于 PSTN 端点连接 SIP 中继。
    
## <a name="enabling-the-location-based-routing-for-conferencing"></a>启用基于位置的路由选择的会议

基于位置的路由的会议应用程序在默认情况下处于禁用状态。 在启用此应用程序之前，您需要确定要为该应用程序分配的适当优先级。 要确定此优先级，请运行以下 cmdlet Skype 业务服务器管理外壳程序为：
  
获得 CsServerApplication-标识服务： 注册：<Pool FQDN>在此 cmdlet，\<池的 FQDN\>是用来启用基于位置的路由的会议应用程序池。
  
此 cmdlet 将返回由 Skype 承载业务服务器的优先级值，为每个应用程序的列表。 基于位置的路由的会议应用程序需要分配优先级值大于"UdcAgent"应用程序和小比"DefaultRouting"、"ExumRouting"和"OutboundRouting"的应用程序。 我们建议您将分配会议应用程序基于位置的路由都通过单点高于优先级值的"UdcAgent"应用程序优先级值。
  
如果"UdcAgent"应用程序优先级值为"2"，例如，"DefaultRouting"应用程序具有的优先级值是"8"、"ExumRouting"应用程序的优先级值为"9"和"OutboundRouting"应用程序优先级值为"10"然后应将会议应用程序基于位置的路由分配的优先级值是"3"。 这样可以将应用程序的优先级顺序如下： 其他应用程序 (优先级： 0 1)，"UdcAgent"(优先级： 2)，基于位置的路由会议应用程序 (优先级： 3)，其他应用程序 (优先级： 4 至 8)，"DefaultRouting"(优先级： 9)，"ExumRouting"(优先级： 10) 和"OutboundRouting"(优先级： 11)。
  
基于位置的路由的会议应用程序中查找正确的优先级值之后，键入以下 cmdlet 为每个家庭用户启用基于位置的路由的前端池或标准版服务器：
  
新 CsServerApplication-标识服务： 注册：<Pool FQDN>/LBRouting-优先级<Application Priority>-启用 $true 的关键 $true Urihttp://www.microsoft.com/LCS/LBRoutingFor的示例：
  
新 CsServerApplication-标识 Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting-优先级 3-启用的 $true 的关键 $true Urihttp://www.microsoft.com/LCS/LBRoutingAfter使用此 cmdlet，该池或标准版服务器在重新启动所有的前端服务器位置会议已启用应用程序的基于位置的路由。
  
> [!IMPORTANT]
> 直到所有前端服务器中可用的池不会强制执行会议或咨询转移到基于位置的路由执行进行或者标准版服务器被重新启动。 如果设置了**-关键**到在前面的 cmdlet 的**$true** ，您的企业服务器服务 Skype 将立即重新启动。 如果不希望立即重新启动这些服务，将**-关键** **$false**为，然后使用更改**集 CsServerApplication**到**-关键**到**$true**以后，已经重新启动服务后。
  
已成功启用基于位置的路由的会议应用程序并重新启动所有适用的服务器，将监视所有会议组织通过 Skype 为商务用户启用基于位置的路由以防止PSTN 电话绕过
  

