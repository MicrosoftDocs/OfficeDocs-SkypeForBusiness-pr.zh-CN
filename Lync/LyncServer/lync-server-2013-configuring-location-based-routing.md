---
title: Lync Server 2013：配置基于位置的路由
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
ms.openlocfilehash: a0e82ae8a0dd9961bfeb9d2a513cb77b0affb2c4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a>在 Lync Server 2013 中配置基于位置的路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-03-12_

Lync Server 2013 CU1，基于位置的路由是企业语音的一项功能。 基于位置的路由是一种呼叫管理功能，用于控制如何通过 Lync Server 2013 CU1 路由呼叫。 它对根据 Lync 呼叫者的位置是否可以将呼叫路由到 PBX 或 PSTN 目标施加限制。 基于位置的路由根据呼叫者的网络位置将呼叫授权规则应用到 PSTN 呼叫。 呼叫方的位置取决于与呼叫者连接的网络子网相关联的网络站点。 配置基于位置的路由需要首先部署企业语音，然后配置网络区域、站点和子网。 这将为启用基于位置的路由建立基础。

在部署基于位置的路由之前，必须先部署企业语音，并配置网络区域、网站，并将网络子网与网络站点相关联。 完成后，您可以配置基于位置的路由。 有关如何配置网络区域、网站和子网的步骤，请参阅[Lync Server 2013 中的 "部署高级企业语音功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)"

本部分将指导你使用以下示例（如图）配置基于位置的路由。

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
<td><p>新德里企业办公室</p></td>
<td><p>DEL-LYNC-1、DEL-LYNC-2、DEL-LYNC-3</p></td>
</tr>
<tr class="even">
<td><p>Lync</p></td>
<td><p>Hyderabad 公司办公室</p></td>
<td><p>HYD-LYNC-1，HYD-LYNC-2，HYD-LYNC-3</p></td>
</tr>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>未知（如宾馆）</p></td>
<td><p>UNK-LYNC-1</p></td>
</tr>
<tr class="even">
<td><p>PBX</p></td>
<td><p>新德里企业办公室</p></td>
<td><p>DEL-PBX-1，DEL-PBX-2</p></td>
</tr>
<tr class="odd">
<td><p>PBX</p></td>
<td><p>Hyderabad 公司办公室</p></td>
<td><p>HYD-PBX-1，HYD-2</p></td>
</tr>
<tr class="even">
<td><p>PSTN</p></td>
<td><p>可知</p></td>
<td><p>PSTN-1、PSTN-2、PSTN-3</p></td>
</tr>
</tbody>
</table>

  

下表表示此示例环境中所示的系统。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>系统</th>
<th>位置</th>
<th>名称</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 CU1 池</p></td>
<td><p>任何</p></td>
<td><p>LS-PL1</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 CU1、中介服务器</p></td>
<td><p>任何</p></td>
<td><p>MS-PL1</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 网关1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-GW</p></td>
</tr>
<tr class="even">
<td><p>PSTN 网关2</p></td>
<td><p>Hyderabad</p></td>
<td><p>HYD-GW</p></td>
</tr>
<tr class="odd">
<td><p>PBX 1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-PBX</p></td>
</tr>
<tr class="even">
<td><p>PBX 2</p></td>
<td><p>Hyderabad</p></td>
<td><p>红 PBX</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中配置企业语音](lync-server-2013-configuring-enterprise-voice.md)

  - [在 Lync Server 2013 中部署网络区域、网站和子网](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [在 Lync Server 2013 中启用基于位置的路由](lync-server-2013-enabling-location-based-routing.md)

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

