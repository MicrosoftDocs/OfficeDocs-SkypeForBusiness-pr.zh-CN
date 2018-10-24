---
title: Lync Server 2013：Dialog 表
TOCTitle: Dialog 表
ms:assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398313(v=OCS.15)
ms:contentKeyID: 49312797
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Dialog 表

 

_**上一次修改主题：** 2015-03-09_

Dialog 表是一个支持表；每条记录代表一个会话初始协议 (SIP) 对话。


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
<td><p>主</p></td>
<td><p>用户体验质量 (QoE) 代理从呼叫者或被叫方接收第一个报告的时间。与 SessionSeq 结合使用来唯一地标识会话。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>当会话具有相同的 ConferenceDateTime 时区分会话的序号。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogID</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p></p></td>
<td><p>全局唯一的对话 ID。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogIDChecksum</strong></p></td>
<td><p>int</p></td>
<td><p>索引</p></td>
<td><p>对话 ID 的校验和。</p></td>
</tr>
</tbody>
</table>

