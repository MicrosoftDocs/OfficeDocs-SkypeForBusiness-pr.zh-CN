---
title: 组内呼叫应答的容量规划
TOCTitle: 组内呼叫应答的容量规划
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ984297(v=OCS.15)
ms:contentKeyID: 52060959
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 组内呼叫应答的容量规划

 

_**上一次修改主题：** 2015-03-09_

下表介绍可用作容量规划要求基础的组内呼叫应答用户模型。

> [!IMPORTANT]  
> 组内呼叫应答基于呼叫寄存应用程序。请记住，在规划灾难恢复容量时，配对池中的每个池都应该能够处理这两个池中呼叫寄存服务（包括组内呼叫应答）的工作负载。


### 组内呼叫应答用户模型

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>指标</th>
<th>每个前端池 （具有 8 台前端服务器）</th>
<th>每个 Standard Edition Server</th>
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
<td><p>25</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> <ul><li><p>对于前端服务器数少于八个的前端池，按照线性方式计算指标。例如，如果您的前端池有一个前端服务器，则按照表中所示值的 1/8 计算最大负载。</p></li>
> <li><p>只要不超过每个池的最大用户数，您就可以增加或减少建议的组数以及每组用户数。例如，您的 Standard Edition Server 可以有 120 个组，每组 25 个用户，因为针对组内呼叫应答启用的用户数仍然没有超过用户模型最大值（即针对组内呼叫应答启用 120 组乘以 25 用户等于 3,000 用户）。</p></li></ul>


