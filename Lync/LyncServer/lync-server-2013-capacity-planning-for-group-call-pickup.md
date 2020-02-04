---
title: Lync Server 2013：组呼叫装货的容量规划
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d694b20d026d83b4cef37c713e38ab8066e22f3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a>Lync Server 2013 中组呼叫装货的容量规划

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-12_

<div id="sectionSection0" class="section">

下表介绍了组呼叫装货用户模型，您可以将其用作容量规划要求的基础。

<div>


> [!IMPORTANT]  
> 组呼叫分拣基于呼叫寄存应用程序。 请记住，对于灾难恢复容量规划，配对池的每个池都应该能够处理呼叫驻留服务的工作负荷，包括组呼叫在两个池中的呼叫。



</div>

### <a name="group-call-pickup-user-model"></a>组呼叫装货用户模型

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>指标</th>
<th>每个前端池（具有8个前端服务器）</th>
<th>每台 Standard Edition Server</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>建议的每组用户数</p></td>
<td><p>50</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>建议的组数</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>针对组内呼叫应答启用的每个池的最大用户数</p></td>
<td><p>25,000</p></td>
<td><p>3,000</p></td>
</tr>
<tr class="even">
<td><p>每个池每分钟针对组内呼叫应答启用的所有用户的最大传入呼叫速率</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>每个池每分钟用户使用组内呼叫应答检索的最大呼叫速率</p></td>
<td><p>200</p></td>
<td><p>二十五</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>对于少于八个前端服务器的前端池，按线性计算指标。 例如，如果您的前端池有一个前端服务器，请将最大负载计算为表中显示的值1/8。</P>
> <LI>
> <P>只要不超过每个池的最大用户数，您就可以增加或减少建议的组数以及每组用户数。 例如，你的标准版服务器可以拥有每组25个用户的120组，因为为组呼叫挑选启用的用户数仍在用户模型的最大范围内（即，120组乘以25个3000用户为组呼叫装货启用的用户）。</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

