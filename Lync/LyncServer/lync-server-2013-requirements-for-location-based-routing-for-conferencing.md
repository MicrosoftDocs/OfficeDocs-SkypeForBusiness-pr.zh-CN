---
title: 'Lync Server 2013: 适用于会议的基于位置的路由的要求'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 925b71497012d7e6ed9c19042a079a7b30630c47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 中基于位置的会议路由的要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-07-19_

以下是安装和配置基于位置的路由会议应用程序所需的要求:

  - Lync Server 2013 累积更新2必须部署在拓扑中的所有服务器或池上。

<div>


> [!NOTE]  
> 如果拓扑中的 Lync 服务器或池未安装 Lync Server 2013 累积更新2或更高版本, 则不能保证对 Lync 会议的基于位置的路由的强制。



</div>

  - Lync Server 2013 基于位置的路由是基于位置的路由会议应用程序的先决条件。 有关配置 Lync Server 2013 基于位置的路由的详细信息, 请参阅[配置基于位置的路由](lync-server-2013-configuring-location-based-routing.md)。

  - 基于位置的路由会议应用程序的要求与 Lync Server 2013 基于位置的路由的要求相同。 有关详细信息, 请参阅[规划基于位置的路由](lync-server-2013-planning-for-location-based-routing.md)。

<div>

## <a name="supported-servers"></a>支持的服务器

基于位置的路由会议应用程序要求在拓扑中的所有前端池和标准版服务器上部署 Lync Server 2013 累积更新2。 如果您的拓扑中的某些 Lync 服务器上未安装 Lync Server 2013 累积更新 2, 基于位置的路由限制不能在 Lync 会议和咨询式呼叫转移上完全强制实施。

下表标识了支持基于位置的路由的服务器角色和版本的组合。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>前端池版本</p></td>
<td><p>中介服务器版本</p></td>
<td><p>支持</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 累积更新 2</p></td>
<td><p>Lync Server 2013 累积更新 2</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 累积更新 2</p></td>
<td><p>Lync Server 2013 累积更新 1</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 累积更新 2</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 累积更新 2</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 累积更新 1</p></td>
<td><p>任意</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010</p></td>
<td><p>任意</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>任意</p></td>
<td><p>否</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a>支持的客户端

支持 Lync 会议基于位置路由的 Lync 客户端是支持 Lync Server 2013 基于位置的路由的相同客户。 有关详细信息, 请参阅[客户端和服务器支持以获取基于位置的路由](lync-server-2013-client-and-server-support-for-location-based-routing.md)。

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a>咨询式呼叫转移的中介服务器要求

基于位置的路由会议应用程序需要部署独立的中介服务器, 以便在咨询式呼叫转移上强制使用基于位置的路由限制。

若要强制执行基于位置的咨询呼叫转移路由, 中介服务器只能与需要基于位置的路由的网络区域中的一个中介服务器对等 (如 PBX、SIP 网关等) 相关联。 如果在同一网络区域中部署其他中介服务器对等, 则中介服务器必须与不同的中介服务器相关联。 此要求的详细信息如下:

  - 每台多个中介服务器对等的单中介服务器当通过将多个 SIP 中继配置为多个对等 (即 Pbx 和网关) 的中介服务器将咨询呼叫转移路由到中介服务器对等如果通过某些 SIP 中继允许咨询呼叫转接, 但禁止通过其他 SIP 中继, 则呼叫转接被阻止, 以防止 PSTN 长途电话旁路。
    
    例如, 在单个中介服务器处理 PSTN 网关中介服务器对等和 PBX 中介服务器对等的情况下, 将看到以下行为:
    
      - 当来自给定网站 (即站点 1) 的 Lync 用户尝试通过顾问式转移将具有 PSTN 终结点的呼叫转移到其他网站 (即 site 2) 中的 Lync 用户时, 将禁止呼叫阻止 PSTN 免绕过。
    
      - 当来自给定网站 (即站点 1) 的 Lync 用户尝试将同一站点 (站点 1) 中的 PBX 终结点与 Lync 用户 (即 site 2) 转移到来自另一个网站 (即 site 2) 的 Lync 用户时, 即使不是在潜在的 PSTN tol 中, 也将禁止呼叫。l 忽略。

  - 每个中介服务器对等单独的中介服务器
    
    当向中介服务器对等进行定向传输时, 将根据中介服务器提供服务的单个中介服务器对来评估咨询转移。 无论其他 Mediations 服务器在不同的中介服务器中提供服务, 该呼叫都将在 PSTN 免绕过的可能性内被禁止或允许使用。
    
    例如, 在单独的中介服务器处理 PSTN 网关中介服务器对等和 PBX 中介服务器对等的情况下, 将看到以下行为:
    
      - 当来自给定网站 (即站点 1) 的 Lync 用户尝试通过顾问式转移将具有 PSTN 终结点的呼叫转移到其他网站 (即 site 2) 中的 Lync 用户时, 将禁止呼叫阻止 PSTN 免绕过。
    
      - 当来自给定网站 (即站点 1) 的 Lync 用户尝试将同一站点 (站点 1) 中的 PBX 终结点与 Lync 用户 (即 site 2) 从咨询转移转移到其他网站 (即 site 2) 上的 lync 用户时, 将允许进行呼叫, 因为它不会在潜在的 PSTN 免绕过&.

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a>基于位置的路由会议应用程序不支持的功能

基于位置的路由会议应用程序不支持以下功能:

  - 电话拨入式会议。 不能为电话拨入式会议强制使用基于位置的路由。 对给定会议的任何拨入请求不会受到基于位置的路由限制, 即使会议组织者是启用了基于位置的路由的 Lync 用户。

  - 建议在需要强制实施基于位置的路由限制的区域中设置会议访问号码。

</div>

</div>

<span> </span>

</div>

</div>

</div>

