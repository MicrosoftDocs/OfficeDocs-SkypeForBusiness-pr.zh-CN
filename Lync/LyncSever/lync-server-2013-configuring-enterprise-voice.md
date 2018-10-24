---
title: 在 Lync Server 2013 中配置企业语音
TOCTitle: 在 Lync Server 2013 中配置企业语音
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994041(v=OCS.15)
ms:contentKeyID: 52061061
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置企业语音

 

_**上一次修改主题：** 2015-03-09_

要部署 企业语音，您需要配置以下内容：

  - 创建 Trunk

  - 定义语音策略

  - 定义语音路由

  - 为用户启用企业语音

## 创建 Trunk

您必须在您的企业语音部署中定义 Trunk。对于基于位置的路由，您必须按 Trunk 创建 Trunk 配置。使用 Lync Server拓扑生成器 定义您的 Trunk，并使用 Lync ServerWindows PowerShell 命令 New-CsTrunkConfiguration 或 Lync Server 控制面板 定义对应的 Trunk 配置。有关如何在 Trunk 配置上启用基于位置的路由的更多信息可在主题[在 Lync Server 2013 中启用基于位置的路由](lync-server-2013-enabling-location-based-routing.md)的“为 Trunk 启用基于位置的路由”部分中找到。对于此示例，下表说明了此方案中使用的 Trunk。

有关详细信息，请参阅[在 Lync Server 2013 拓扑生成器中定义其他中继](lync-server-2013-define-additional-trunks-in-topology-builder.md)。


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
<th>Trunk 名称</th>
<th>系统类型</th>
<th>名称</th>
<th>位置</th>
<th>中介服务器</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Trunk 1 DEL-GW</p></td>
<td><p>PSTN 网关</p></td>
<td><p>DEL-GW</p></td>
<td><p>德里</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>Trunk 2 HYD-GW</p></td>
<td><p>PSTN 网关</p></td>
<td><p>HYD-GW</p></td>
<td><p>海德拉巴</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="odd">
<td><p>Trunk 3 DEL-PBX</p></td>
<td><p>PBX</p></td>
<td><p>DEL-PBX</p></td>
<td><p>德里</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>Trunk 4 HYD-PBX</p></td>
<td><p>PBX</p></td>
<td><p>HYD-PBX</p></td>
<td><p>海德拉巴</p></td>
<td><p>MS1</p></td>
</tr>
</tbody>
</table>



## 定义语音策略

您必须为您的企业语音部署定义语音策略。定义一个语音策略，以便当只有一小组用户需要使用基于位置的路由时才为他们强制实施基于位置的路由限制。对于此示例，下表说明了此方案中使用的语音策略。出于说明目的，该表中仅包括特定于基于位置的路由的设置。

有关详细信息，请参阅[在 Lync Server 2013 中配置语音策略和 PSTN 用法记录以授权呼叫功能和权限](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>语音策略 1</th>
<th>语音策略 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>语音策略 ID</p></td>
<td><p>德里语音策略</p></td>
<td><p>海得拉巴语音策略</p></td>
</tr>
<tr class="even">
<td><p>PSTN 用法</p></td>
<td><p>德里用法、PBX Del 用法、PBX Hyd 用法</p></td>
<td><p>海得拉巴用法、PBX Hyd 用法、PBX Del 用法</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>False</p></td>
<td><p>False</p></td>
</tr>
</tbody>
</table>



## 定义语音路由

您必须为您的企业语音部署定义语音路由。对于此示例，下表说明了此方案中使用的语音路由。出于说明目的，该表中仅包括特定于基于位置的路由的设置。

有关详细信息，请参阅[在 Lync Server 2013 中配置出站呼叫的语音路由](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)。


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
<th></th>
<th>语音路由 1</th>
<th>语音路由 2</th>
<th>语音路由 3</th>
<th>语音路由 4</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>名称</p></td>
<td><p>德里路由</p></td>
<td><p>海德拉巴路由</p></td>
<td><p>PBX Del 路由</p></td>
<td><p>PBX Hyd 路由</p></td>
</tr>
<tr class="even">
<td><p>PSTN 用法</p></td>
<td><p>德里用法</p></td>
<td><p>海德拉巴用法</p></td>
<td><p>PBX Del 用法</p></td>
<td><p>PBX Hyd 用法</p></td>
</tr>
<tr class="odd">
<td><p>Trunk</p></td>
<td><p>Trunk 1 DEL-GW</p></td>
<td><p>Trunk 2 HYD-GW</p></td>
<td><p>Trunk 3 DEL-PBX</p></td>
<td><p>Trunk 4 HYD-PBX</p></td>
</tr>
</tbody>
</table>



## 为用户启用企业语音

为用户启用企业语音并为他们分配您之前定义的语音策略。 对于此示例，下表说明了此方案中使用的分配。出于说明目的，该表中仅包括特定于基于位置的路由的设置。

有关详细信息，请参阅[在 Lync Server 2013 中为用户启用企业语音](lync-server-2013-enable-users-for-enterprise-voice.md)。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>位于德里的用户</th>
<th>位于海得拉巴的用户</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>关联的语音策略</p></td>
<td><p>德里语音策略</p></td>
<td><p>海得拉巴语音策略</p></td>
</tr>
<tr class="even">
<td><p>示例用户</p></td>
<td><p>DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</p></td>
<td><p>HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</p></td>
</tr>
</tbody>
</table>



## 另请参阅

#### 其他资源

[在 Lync Server 2013 中配置基于位置的路由](lync-server-2013-configuring-location-based-routing.md)

