---
title: Lync Server 2013：会议的 Location-Based 路由要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66be7f9dd3faeb167519d9ce815e84f8cf692c22
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511849"
---
# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a>在 Lync Server 2013 中为会议 Location-Based 路由的要求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-07-19_

以下是安装和配置 Location-Based 路由会议应用程序所需的要求：

  - Lync Server 2013 累积更新2必须部署在拓扑中的所有服务器或池上。

<div>


> [!NOTE]  
> 如果拓扑中的 Lync server 或池未安装 Lync Server 2013 累积更新2或更高版本，则不能保证 Lync 会议的 Location-Based 路由的强制执行。



</div>

  - Lync Server 2013 Location-Based 路由是 Location-Based 路由会议应用程序的先决条件。 有关配置 Lync Server 2013 Location-Based 路由的详细信息，请参阅 [配置 Location-Based 路由](lync-server-2013-configuring-location-based-routing.md)。

  - Location-Based 路由会议应用程序的要求与 Lync Server 2013 Location-Based 路由的要求相同。 有关详细信息，请参阅 [规划 Location-Based 路由](lync-server-2013-planning-for-location-based-routing.md)。

<div>

## <a name="supported-servers"></a>支持的服务器

Location-Based 路由会议应用程序要求在拓扑中的所有 Front-End 池和 Standard Edition 服务器上部署 Lync Server 2013 累积更新2。 如果您的拓扑中的某些 Lync 服务器上未安装 Lync Server 2013 累积更新2，则不能在 Lync 会议和咨询呼叫转移上完全强制执行 Location-Based 路由限制。

下表标识了支持 Location-Based 路由的服务器角色和版本的组合。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Front-End 池版本</p></td>
<td><p>中介服务器版本</p></td>
<td><p>支持</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 累积更新2</p></td>
<td><p>Lync Server 2013 累积更新2</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 累积更新2</p></td>
<td><p>Lync Server 2013 累积更新1</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 累积更新2</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 累积更新2</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 累积更新1</p></td>
<td><p>任何</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010</p></td>
<td><p>任何</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>任何</p></td>
<td><p>否</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a>支持的客户端

支持 Lync 会议 Location-Based 路由的 Lync 客户端是支持 Lync Server 2013 Location-Based 路由的相同客户端。 有关详细信息，请参阅 [客户端和服务器支持 Location-Based 路由](lync-server-2013-client-and-server-support-for-location-based-routing.md)。

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a>咨询呼叫转移的中介服务器要求

Location-Based 路由会议应用程序需要部署独立中介服务器，以便在咨询呼叫转移上强制执行 Location-Based 路由限制。

若要强制 Location-Based 路由的咨询呼叫转移，中介服务器必须仅与网络区域中的一个中介服务器对等 (（即 PBX、SIP 网关) 等）相关联，其中需要有 Location-Based 路由。 如果在同一网络区域中部署其他中介服务器对等方，则必须将中介服务器对等方与不同的中介服务器相关联。 此要求的详细说明如下：

  - 每台多个中介服务器对等台中介服务器：当通过配置了多个 SIP 中继的中介服务器将咨询呼叫转移路由到中介服务器对等方 (（即 Pbx 和网关) ，如果通过某些 SIP 中继允许咨询呼叫转移但禁止通过其他 SIP 中继，则会阻止咨询呼叫转移，以防止 PSTN 收费旁路。
    
    例如，在单个中介服务器为 PSTN 网关中介服务器对等方和 PBX 中介服务器对等方提供服务时，将会看到以下行为：
    
      - 当来自给定网站 (的 Lync 用户（例如，站点 1) 尝试从其他站点将带有 PSTN 终结点的呼叫转移到 Lync 用户 (（即 site 2) 通过咨询转移）时，将不允许该呼叫阻止 PSTN 收费旁路。
    
      - 当来自给定网站的 Lync 用户 (（例如，站点 1) 尝试将同一站点中与 PBX 终结点 (站点 1) 的呼叫转移到来自不同站点的 Lync 用户 (（即 site 2) 通过咨询转移），即使在潜在的 PSTN 收费绕过，也不会出现该呼叫。

  - 每个中介服务器对等的单独中介服务器
    
    在面向中介服务器的对等客户端进行咨询转移时，将根据中介服务器提供服务的单个中介服务器对来评估咨询转移。 根据不同中介服务器提供服务中的所有其他 Mediations 服务器等方，此呼叫将因其在 PSTN 收费旁路中的潜在情况而不允许或允许出现。
    
    例如，在单独的中介服务器为 PSTN 网关中介服务器对等方和 PBX 中介服务器对等方提供服务时，将会看到以下行为：
    
      - 当来自给定网站 (的 Lync 用户（例如，站点 1) 尝试从其他站点将带有 PSTN 终结点的呼叫转移到 Lync 用户 (（即 site 2) 通过咨询转移）时，将不允许该呼叫阻止 PSTN 收费旁路。
    
      - 当来自给定网站 (的 Lync 用户（例如，站点 1) 尝试将来自同一站点 (站点 1) 的 PBX 终结点转移到来自不同站点的 Lync 用户 (（即 site 2) 通过咨询转移）时，将允许该呼叫，因为它不会在潜在的 PSTN 收费绕过中产生。

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a>Location-Based 路由会议应用程序不支持的功能

Location-Based 路由会议应用程序不支持以下功能：

  - 电话拨入式会议。 无法对电话拨入式会议强制执行 Location-Based 路由。 即使会议组织者是为 Location-Based 路由启用的 Lync 用户，Location-Based 路由也不会限制对给定会议的任何拨入请求。

  - 建议不要在需要强制实施 Location-Based 路由限制的区域中设置会议访问号码。

</div>

</div>

<span> </span>

</div>

</div>

</div>

