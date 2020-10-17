---
title: Lync Server 2013：配置 Location-Based 路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b703aa084204a2c103e02ebff5f913a6647ae94
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517410"
---
# <a name="configuring-location-based-routing-in-lync-server-2013"></a>在 Lync Server 2013 中配置 Location-Based 路由

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-12_

Lync Server 2013 CU1，Location-Based 路由是企业语音的一项功能。 Location-Based 路由是一种呼叫管理功能，用于控制 Lync Server 2013 CU1 路由呼叫的方式。 它强制实施限制，即是否可以根据 Lync 呼叫者的位置将呼叫路由到 PBX 或 PSTN 目标。 Location-Based 路由根据呼叫者的网络位置将呼叫授权规则应用于 PSTN 呼叫。 呼叫者的位置根据与呼叫者连接的网络子网关联的网络站点来确定。 若要配置 Location-Based 路由，必须首先部署企业语音，然后配置网络区域、站点和子网。 这将设置启用 Location-Based 路由的基础。

在部署 Location-Based 路由之前，必须先部署企业语音，并配置网络区域、站点，并将网络子网与网络站点关联。 完成后，您可以配置 Location-Based 路由。 有关如何配置网络区域、站点和子网的步骤，请参阅 [在 Lync Server 2013 中部署高级企业语音功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

本部分将指导您使用下面的示例作为图示，以了解 Location-Based 路由的配置。

![基于企业语音位置的路由示例](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "基于企业语音位置的路由示例")

  
下表表示在此示例中定义的用户。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>终结点类型</th>
<th>位置</th>
<th>用户</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>新德里公司办公室</p></td>
<td><p>DEL-LYNC-1，DEL-LYNC-2，DEL-LYNC-3</p></td>
</tr>
<tr class="even">
<td><p>Lync</p></td>
<td><p>Hyderabad 企业办公室</p></td>
<td><p>HYD-LYNC-1，HYD-LYNC-2，HYD-LYNC-3</p></td>
</tr>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>未知 (，即旅馆) </p></td>
<td><p>UNK-LYNC-1</p></td>
</tr>
<tr class="even">
<td><p>PBX</p></td>
<td><p>新德里公司办公室</p></td>
<td><p>DEL-PBX-1，DEL-PBX-2</p></td>
</tr>
<tr class="odd">
<td><p>PBX</p></td>
<td><p>Hyderabad 企业办公室</p></td>
<td><p>HYD-1，HYD-2</p></td>
</tr>
<tr class="even">
<td><p>PSTN</p></td>
<td><p>未知</p></td>
<td><p>PSTN-1、PSTN-2、PSTN-3</p></td>
</tr>
</tbody>
</table>

  

下表表示在此示例环境中说明的系统。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>系统警报</th>
<th>位置</th>
<th>名称</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 CU1 池</p></td>
<td><p>任意</p></td>
<td><p>LS-PL1</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 CU1，中介服务器</p></td>
<td><p>任意</p></td>
<td><p>MS-PL1</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 网关1</p></td>
<td><p>德里</p></td>
<td><p>DEL-GW</p></td>
</tr>
<tr class="even">
<td><p>PSTN 网关2</p></td>
<td><p>Hyderabad</p></td>
<td><p>HYD-GW</p></td>
</tr>
<tr class="odd">
<td><p>PBX 1</p></td>
<td><p>德里</p></td>
<td><p>DEL-PBX</p></td>
</tr>
<tr class="even">
<td><p>PBX 2</p></td>
<td><p>Hyderabad</p></td>
<td><p>RED-PBX</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中配置企业语音](lync-server-2013-configuring-enterprise-voice.md)

  - [在 Lync Server 2013 中部署网络区域、站点和子网](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [在 Lync Server 2013 中启用 Location-Based 路由](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中部署高级企业语音功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

