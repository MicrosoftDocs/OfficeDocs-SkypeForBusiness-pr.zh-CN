---
title: Lync Server 2013：Dialog 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dialog table
ms:assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398313(v=OCS.15)
ms:contentKeyID: 48184068
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f0ef564ad1224ba9970b7cceb5db60e0eb344da
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialog-table-in-lync-server-2013"></a>Lync Server 2013 中的 Dialog 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-02_

对话框表是支持表;每条记录表示一个会话初始协议（SIP）对话框。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>列</strong></th>
<th><strong>数据类型</strong></th>
<th><strong>键/索引</strong></th>
<th><strong>详细信息</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>优质（QoE） agent 接收来自呼叫方或被叫方的第一个报告的时间。 与 SessionSeq 结合使用以唯一标识会话。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>序列号，以便在具有相同的 ConferenceDateTime 时区分会话。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogID</strong></p></td>
<td><p>varchar （256）</p></td>
<td></td>
<td><p>全局唯一的对话框 ID。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogIDChecksum</strong></p></td>
<td><p>int</p></td>
<td><p>食指</p></td>
<td><p>对话框 ID 的校验和。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

