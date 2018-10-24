---
title: Lync Server 2013：规划出站语音路由
TOCTitle: 规划出站语音路由
ms:assetid: 37c55fa4-175a-4190-b9e4-c2e5ac7b9261
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425853(v=OCS.15)
ms:contentKeyID: 49312498
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中规划出站语音路由

 

_**上一次修改主题：** 2015-03-09_

出站呼叫路由适用于发往公用电话交换网 (PSTN) 网关、中继或专用交换机 (PBX) 的呼叫。当用户发出呼叫时，服务器会在必要时将电话号码规范化为 E.164 格式，并尝试将其与 SIP URI 进行匹配。如果服务器无法进行匹配，则会根据提供的拨号串应用出站呼叫路由逻辑。通过配置下表中所述的服务器设置定义该逻辑。

### Lync Server 出站呼叫路由设置

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>名称</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>拨号计划</p></td>
<td><p>拨号计划是一组指定的规范化规则，可将指定位置、单个用户或联系人对象的电话号码转换为统一标准 (E.164) 格式，以进行电话授权和呼叫路由。</p></td>
</tr>
<tr class="even">
<td><p>规范化规则</p></td>
<td><p>规范化规则定义如何针对每个指定的位置、用户或联系对象来路由以不同格式表示的电话号码。同一拨号串的解析和转换可能不同，具体取决于拨打该号码的位置，以及发出呼叫的人员或联系对象。一组与特定位置相关联的规范化规则构成一个拨号计划。</p></td>
</tr>
<tr class="odd">
<td><p>语音策略</p></td>
<td><p>语音策略将一个或多个 PSTN 用法记录与一个用户或一组用户相关联。语音策略还提供了可以启用或禁用的呼叫功能列表。</p></td>
</tr>
<tr class="even">
<td><p>PSTN 用法记录</p></td>
<td><p>PSTN 用法记录指定组织中各个用户或用户组所能进行的呼叫类别（如内部、本地或长途）。</p></td>
</tr>
<tr class="odd">
<td><p>呼叫路由</p></td>
<td><p>呼叫路由将目标电话号码与特定中继和 PSTN 用法记录相关联。PSTN 网关被视为中继。</p></td>
</tr>
</tbody>
</table>


## 本部分内容

本节提供配置以下出站呼叫路由服务器设置的指南：

  - [Lync Server 2013 中的拨号计划和规范化规则](lync-server-2013-dial-plans-and-normalization-rules.md)

  - [Lync Server 2013 中的语音策略](lync-server-2013-voice-policies.md)

  - [Lync Server 2013 中的 PSTN 用法记录](lync-server-2013-pstn-usage-records.md)

  - [Lync Server 2013 中的语音路由](lync-server-2013-voice-routes.md)

## 另请参阅

#### 概念

[Lync Server 2013 中的 SIP 中继](lync-server-2013-sip-trunking.md)  
[Lync Server 2013 中的直接 SIP 连接](lync-server-2013-direct-sip-connections.md)

