---
title: Lync Server 2013：针对会议的基于位置的路由配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bc901b9ef1b4b358771427f44d220631e4a40ee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>在 Lync Server 2013 中为会议进行基于位置的路由的配置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-09-11_

基于位置的路由会议应用程序依赖于 Lync Server 2013 基于位置的路由的配置。 主要配置如下所示：

  - 加入会议的参与者的位置根据其网络网站确定。 必须在 Lync Server 中定义网络站点及其关联的网络子网，才能强制实施基于位置的路由。

  - 若要强制实施会议的基于位置的路由，必须为 Lync 参与者启用基于位置的路由。

  - 若要强制对 PSTN 终结点进行基于位置的路由加入会议，必须为用于连接 PSTN 终结点的 SIP 中继配置基于位置的路由。

有关部署和配置 Lync Server 2013 基于位置的路由的其他信息，请参阅配置[基于位置的路由](lync-server-2013-configuring-location-based-routing.md)。

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a>启用基于位置的路由会议应用程序

默认情况下，基于位置的路由会议应用程序处于禁用状态。 在启用此应用程序之前，您需要确定要分配给应用程序的正确优先级。 若要确定此优先级，请在 Lync Server 命令行管理程序中运行以下 cmdlet：

CsServerApplication-Identity Service：注册器：\<池 FQDN\>

在此 cmdlet 中\<，池\> FQDN 是在其中启用基于位置的路由会议应用程序的池。

此 cmdlet 将返回由 Lync Server 托管的应用程序的列表及其每个应用程序的优先级值。 需要为基于位置的路由会议应用程序分配比 "UdcAgent" 应用程序更大的优先级值，而不是 "DefaultRouting"、"ExumRouting" 和 "OutboundRouting" 应用程序。 建议为基于位置的路由会议应用程序分配一个比 "UdcAgent" 应用程序的优先级值高1磅的优先级值。

例如，如果 "UdcAgent" 应用程序的优先级值为 "2"，则 "DefaultRouting" 应用程序的优先级值为 "8"，"ExumRouting" 应用程序的优先级值为 "9"，而 "OutboundRouting" 应用程序的优先级值为 "10"，则应为基于位置的路由会议应用程序分配优先级值 "3"。 这样做会按以下顺序放置应用程序的优先级：其他应用程序（优先级：0到1）、"UdcAgent" （优先级：2）、基于位置的路由会议应用程序（优先级：4）、其他应用程序（优先级：4到8）、"DefaultRouting "（优先级：9）、" ExumRouting "（优先级：10）和" OutboundRouting "（优先级：11）。

在找到基于位置的路由会议应用程序的正确优先级值之后，为每个前端池或 Standard Edition 服务器键入以下 cmdlet，以便让用户为其启用基于位置的路由的主用户：

CsServerApplication-\<Identity Service：注册器：池 FQDN\>/LBRouting-启用优先级\<的应用\>程序优先级已启用 $true 关键 $true-Urihttps://www.microsoft.com/LCS/LBRouting

例如：

CsServerApplication-Identity Service:Registrar:LS2013CU2LBRPool/LBRouting-已启用优先级3的 $true-关键 $true-Urihttps://www.microsoft.com/LCS/LBRouting

使用此 cmdlet 之后，请重新启动池中的所有前端服务器或启用了基于位置的路由会议应用程序的 Standard Edition 服务器。

<div>


> [!IMPORTANT]  
> 在重新启动适用的池中的所有前端服务器或 Standard Edition 服务器之前，将不会强制执行基于位置的路由之后或咨询转移。



</div>

在已成功启用基于位置的路由会议应用程序并重新启动所有适用的 Lync 服务器之后，将监控所有由 Lync 用户组织的启用了基于位置的路由的会议，以防止 PSTN 收费旁路

</div>

</div>

<span> </span>

</div>

</div>

</div>

