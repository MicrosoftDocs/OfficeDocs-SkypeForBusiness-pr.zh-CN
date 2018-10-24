---
title: 分配每用户状态策略
TOCTitle: 分配每用户状态策略
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182614(v=OCS.15)
ms:contentKeyID: 49314854
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 分配每用户状态策略

 

_**上一次修改主题：** 2015-03-09_

状态策略是影响状态的一组限制和约束。下表描述了 Lync Server 2013 中提供的状态策略设置。

### 状态策略设置

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>XML 名称</th>
<th>显示名称</th>
<th>说明</th>
<th>类型</th>
<th>值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CategorySubscriptions</p></td>
<td><p>最大订阅者类别订阅数</p></td>
<td><p>限制订阅者类别订阅数。例如，当 Communicator 订阅用户的状态时，会获取每个联系人卡片、日历数据、注释、服务和状态类别的类别订阅。</p>
<p>设置为 0 意味着其他人无法订阅用户或联系人对象。</p>
<div>

> [!NOTE]  
> 如果设置为较大的数值，则此设置会对性能产生显著的影响，且会有大量用户订阅普通用户的状态。


</div></td>
<td><p>整数</p></td>
<td><p>0-3000</p></td>
</tr>
<tr class="even">
<td><p>PromptedSubscribers</p></td>
<td><p>排队状态订阅通知的最大数量</p></td>
<td><p>限制提示订阅者表中的条目数。此设置确定可为给定用户排队的最大提示数。例如，当用户 A 订阅用户 B 的状态时，用户 B 会收到用户 A 现在订阅用户 B 的提示，且会在用户 B 的提示订阅者表中创建确认提示。用户 B 接受或确认该订阅后，会从用户 B　的提示订阅者表中删除该确认提示。</p>
<p>设置为 0 意味着当某人订阅用户的状态时不会提示该用户。</p></td>
<td><p>整数或标记</p></td>
<td><p>0-500</p></td>
</tr>
</tbody>
</table>


默认情况下，“默认策略”和“服务: 中等”状态策略会在部署 Lync Server 时进行安装。下表描述了两种状态策略的特定设置。

### 状态策略

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>策略名称</th>
<th>说明</th>
<th>CategorySubscriptions</th>
<th>PromptedSubscribers</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>默认策略</p></td>
<td><p>典型用户的策略。这是默认状态策略。</p></td>
<td><p>1000</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>服务: 中等</p></td>
<td><p>要求更多用户订阅对象的状态的应用程序策略。</p></td>
<td><p>1000</p></td>
<td><p>0</p></td>
</tr>
</tbody>
</table>

