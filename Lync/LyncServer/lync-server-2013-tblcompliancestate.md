---
title: Lync Server 2013：tblComplianceState
TOCTitle: tblComplianceState
ms:assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg615045(v=OCS.15)
ms:contentKeyID: 49314627
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 tblComplianceState

 

_**上一次修改主题：** 2015-03-09_

tblComplianceState 包含池范围的合规性状态信息。

### 列

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>类型</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>lastProcessedEntryID</p></td>
<td><p>bigint，不为 null</p></td>
<td><p>最新处理的合规性事件的 ID。</p></td>
</tr>
<tr class="even">
<td><p>activeServerID</p></td>
<td><p>int，不为 null</p></td>
<td><p>数据库上保留排除锁的合规性服务器 ID，或者，如果无则为 -1。</p></td>
</tr>
<tr class="odd">
<td><p>lockExpirationTime</p></td>
<td><p>datetime2，不为 null</p></td>
<td><p>锁定到期时间（如果 activeServerID 不为 -1）。</p></td>
</tr>
</tbody>
</table>

