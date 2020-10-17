---
title: Lync Server 2013：会议的 Location-Based 路由配置
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
ms.openlocfilehash: bd5ada5e4af1ed4ed43434ddf4d82abc25f4cd5e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507799"
---
# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>在 Lync Server 2013 中为会议 Location-Based 的路由配置

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-09-11_

Location-Based 路由会议应用程序依赖于 Lync Server 2013 Location-Based 路由的配置。 主要配置如下所示：

  - 加入会议的参与者的位置根据其网络网站确定。 必须在 Lync Server 中定义网络站点及其关联的网络子网，才能强制 Location-Based 路由。

  - 若要强制 Location-Based 传送会议，必须为 Lync 参与者启用 Location-Based 路由。

  - 若要强制 Location-Based 路由 PSTN 终结点加入会议，必须为用于连接 PSTN 终结点的 SIP 中继配置 Location-Based 路由。

有关在 Location-Based 路由的情况下部署和配置 Lync Server 2013 的详细信息，请参阅配置 [基于位置的路由](lync-server-2013-configuring-location-based-routing.md)。

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a>启用 Location-Based 路由会议应用程序

默认情况下，Location-Based 路由会议应用程序处于禁用状态。 在启用此应用程序之前，您需要确定要分配给应用程序的正确优先级。 若要确定此优先级，请在 Lync Server 命令行管理程序中运行以下 cmdlet：

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

在此 cmdlet 中， \<Pool FQDN\> 是要在其中启用 Location-Based 路由会议应用程序的池。

此 cmdlet 将返回由 Lync Server 托管的应用程序的列表及其每个应用程序的优先级值。 需要为 Location-Based 路由会议应用程序分配比 "UdcAgent" 应用程序更大的优先级值，而不是 "DefaultRouting"、"ExumRouting" 和 "OutboundRouting" 应用程序。 我们建议您为 Location-Based 的路由会议应用程序分配一个比 "UdcAgent" 应用程序的优先级值高一个点的优先级值。

例如，如果 "UdcAgent" 应用程序的优先级值为 "2"，则 "DefaultRouting" 应用程序的优先级值为 "8"，"ExumRouting" 应用程序的优先级值为 "9"，"OutboundRouting" 应用程序的优先级值为 "10"，则应为 Location-Based 路由会议应用程序分配优先级值 "3"。 这样做会按以下顺序放置应用程序的优先级：其他应用程序 (优先级：0到 1) ，"UdcAgent" (优先级： 2) ，Location-Based 路由会议应用程序 (优先级： 3) ，其他应用程序 (优先级：4到 8) ，"DefaultRouting" (优先级： 9) ，"ExumRouting" (优先级： 10) and "OutboundRouting" (优先级： 11) 。

找到 Location-Based 路由会议应用程序的正确优先级值之后，为每个 Front-End 池或 Standard Edition Server 键入以下 cmdlet，以便为 Location-Based 路由启用了家庭用户：

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

例如：

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

使用此 cmdlet 之后，请重新启动池中的所有前端服务器或已在其中启用 Location-Based 路由会议应用程序的 Standard Edition 服务器。

<div>


> [!IMPORTANT]  
> 在所有前端服务器或标准版服务器重新启动之前，不会强制 Location-Based 路由之后到会议或咨询转移。



</div>

在成功启用 Location-Based 路由会议应用程序并重新启动所有适用的 Lync 服务器之后，将监控所有由启用了 Location-Based 路由的 Lync 用户组织的会议，以防止 PSTN 收费旁路

</div>

</div>

<span> </span>

</div>

</div>

</div>

