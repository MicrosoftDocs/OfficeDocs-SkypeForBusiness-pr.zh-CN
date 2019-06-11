---
title: Lync Server 2013：会议的基于位置的路由的配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 657978ee622713ffd830d4aeb92a05d949287568
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837470"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 中会议的基于位置的路由的配置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-09-11_

基于位置的路由会议应用程序依赖于 Lync Server 2013 基于位置的路由的配置。 主要配置如下：

  - 加入会议的参与者的位置基于其网络站点进行确定。 必须在 Lync Server 中定义网络网站及其关联的网络子网, 才能强制执行基于位置的路由。

  - 若要强制使用基于位置的会议路由, 必须为 Lync 参与者启用基于位置的路由。

  - 若要强制使用基于位置的 PSTN 终结点路由加入会议, 则必须为基于位置的路由配置用于连接 PSTN 终结点的 SIP 中继。

有关部署和配置 Lync Server 2013 基于位置的路由的其他信息, 请参阅配置[基于位置的路由](lync-server-2013-configuring-location-based-routing.md)。

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a>启用基于位置的路由会议应用程序

默认情况下, 基于位置的路由会议应用程序处于禁用状态。 在启用此应用程序之前，您需要确定要为该应用程序分配的适当优先级。 若要确定此优先级, 请在 Lync Server 命令行管理程序中运行以下 cmdlet:

CsServerApplication-身份服务: 注册机构:\<池 FQDN\>

在此 cmdlet 中\<, 池\> FQDN 是要在其中启用基于位置的路由会议应用程序的池。

此 cmdlet 将返回由 Lync Server 托管的应用程序的列表及其每个应用程序的优先级值。 需要为基于位置的路由会议应用程序分配一个比 "UdcAgent" 应用程序更大的优先级值, 并小于 "DefaultRouting"、"ExumRouting" 和 "OutboundRouting" 应用程序。 我们建议你分配基于位置的路由会议应用程序, 该优先级值比 "UdcAgent" 应用程序的优先级值高一个点。

例如, 如果 "UdcAgent" 应用程序的优先级值为 "2", 则 "DefaultRouting" 应用程序的优先级值为 "8", "ExumRouting" 应用程序的优先级值为 "9", "OutboundRouting" 应用程序的优先级值为 "10", 然后你应该为基于位置的路由会议应用程序分配优先级值 "3"。 这样做将按以下顺序设定应用程序的优先级：其他应用程序（优先级：0 到 1）、“UdcAgent”（优先级：2）、基于位置的路由会议应用程序（优先级：3）、其他应用程序（优先级：4 到 8）、“DefaultRouting”（优先级：9）、“ExumRouting”（优先级：10）和“OutboundRouting”（优先级：11）。

找到基于位置的路由会议应用程序的正确优先级值后, 为每个前端池或标准版服务器键入以下 cmdlet, 以便为基于位置的路由启用家庭用户:

CsServerApplication-\<Identity 服务: 注册机构: 池 FQDN\>/LBRouting-启用优先级\<的应用\>程序优先级已启用 $true-严重 $true Urihttp://www.microsoft.com/LCS/LBRouting

例如：

New-CsServerApplication-Identity 服务:Registrar:LS2013CU2LBRPool/LBRouting-启用优先级3的 $true 关键 $true-Urihttp://www.microsoft.com/LCS/LBRouting

使用此 cmdlet 后, 重启池中的所有前端服务器或启用基于位置的路由会议应用程序的标准版服务器。

<div>


> [!IMPORTANT]  
> 在重新启动适用的池或标准版服务器中的所有前端服务器之前, 不会强制执行基于位置的路由 enforcements 到会议或咨询式传输。



</div>

一旦基于位置的路由会议应用程序已成功启用并且所有适用的 Lync 服务器都已重新启动, 则将监视所有由 Lync 用户组织的基于位置的路由所组织的会议, 以防止 PSTN 免绕过

</div>

</div>

<span> </span>

</div>

</div>

</div>

