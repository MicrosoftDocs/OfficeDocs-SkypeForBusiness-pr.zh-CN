---
title: Lync Server 2013：响应组的容量规划
TOCTitle: 响应组的容量规划
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412754(v=OCS.15)
ms:contentKeyID: 49313805
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中响应组的容量规划

 

_**上一次修改主题：** 2015-03-09_

下表介绍可用作容量规划要求基础的 响应组用户模型。

> [!NOTE]  
> 下表中的数值假定所有响应组音频文件使用的是 16 kHz、单声道、16 位的 Wave (.wav) 文件。如果使用其他文件格式（如 Windows Media 音频 (.wma)），则数值可能会有所不同。



> [!IMPORTANT]  
> 请记住，对于灾难恢复容量规划，一对池中的每一个池都应能处理这两个池中的所有响应组的工作负荷。


### 响应组用户模型

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>指标</th>
<th>每个 Enterprise Edition 池 （具有 8 台前端服务器）</th>
<th>每台 Standard Edition Server</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>每秒传入的呼叫数</p></td>
<td><p>16</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>连接到 IVR 或 MoH 的并发呼叫数</p></td>
<td><p>480</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>并发的匿名会话数（无 IM）</p></td>
<td><p>224</p></td>
<td><p>28</p></td>
</tr>
<tr class="even">
<td><p>并发的匿名会话数（具有 IM）</p></td>
<td><p>64</p></td>
<td><p>8</p></td>
</tr>
<tr class="odd">
<td><p>活动代理数（正式和非正式）</p></td>
<td><p>1200</p></td>
<td><p>1200</p></td>
</tr>
<tr class="even">
<td><p>智能寻线数</p></td>
<td><p>400</p></td>
<td><p>400</p></td>
</tr>
<tr class="odd">
<td><p>IVR 组数（使用语音识别）</p></td>
<td><p>200</p></td>
<td><p>200</p></td>
</tr>
</tbody>
</table>

