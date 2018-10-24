---
title: Lync Server 2013：呼叫寄存容量规划
TOCTitle: 呼叫寄存容量规划
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg416493(v=OCS.15)
ms:contentKeyID: 49313273
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的呼叫寄存容量规划

 

_**上一次修改主题：** 2015-03-09_

下表介绍可用作容量规划要求基础的 呼叫寄存用户模型。

> [!IMPORTANT]  
> 请注意，在规划灾难恢复容量时，配对池中的每个池都应该能够处理这两个池中的 呼叫寄存服务的工作负载。


### 呼叫寄存用户模型

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>指标</th>
<th>每个 前端池 （具有 8 台前端服务器）</th>
<th>每个 Standard Edition Server</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>寄存速率</p></td>
<td><p>每分钟 8 个</p></td>
<td><p>每分钟 1 个</p></td>
</tr>
<tr class="even">
<td><p>取回寄存呼叫的速率</p></td>
<td><p>每分钟 8 个</p></td>
<td><p>每分钟 1 个</p></td>
</tr>
<tr class="odd">
<td><p>平均寄存持续时间</p></td>
<td><p>60 秒</p></td>
<td><p>60 秒</p></td>
</tr>
</tbody>
</table>

