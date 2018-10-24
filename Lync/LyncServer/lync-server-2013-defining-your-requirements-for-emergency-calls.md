---
title: Lync Server 2013：定义紧急呼叫要求
TOCTitle: 定义紧急呼叫要求
ms:assetid: 5c12b517-9be6-41d0-83e2-11c78793620c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398404(v=OCS.15)
ms:contentKeyID: 49312972
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中定义紧急呼叫要求

 

_**上一次修改主题：** 2015-03-09_

您应该先能回答以下部分中的问题，然后才能开始 Microsoft Lync Server 2013 E9-1-1 部署。您需要执行的规划取决于选择部署的 E9-1-1 解决方案的类型 - SIP 中继 E9-1-1 服务提供商或紧急位置标识符号 (ELIN) 网关。下表确定了本规划工作簿中您需要针对上述每个解决方案回顾的部分。

### 按 E9-1-1 解决方案的类型显示的规划步骤

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>SIP 中继服务提供商</th>
<th>ELIN 网关</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">在 Lync Server 2013 中定义 E9-1-1 部署的范围</a></p></td>
<td><p><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">在 Lync Server 2013 中定义 E9-1-1 部署的范围</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">在 Lync Server 2013 中定义用于确定位置的网络元素</a></p></td>
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">在 Lync Server 2013 中定义用于确定位置的网络元素</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">在 Lync Server 2013 中为用户启用 E9-1-1</a></p></td>
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">在 Lync Server 2013 中为用户启用 E9-1-1</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">在 Lync Server 2013 中管理 SIP 中继服务提供商的位置</a></p></td>
<td><p><a href="lync-server-2013-managing-locations-for-elin-gateways.md">在 Lync Server 2013 中管理 ELIN 网关的位置</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">在 Lync Server 2013 中定义手动获取位置的用户体验</a></p></td>
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">在 Lync Server 2013 中定义手动获取位置的用户体验</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">在 Lync Server 2013 中为 E9-1-1 设计 SIP 中继</a></p></td>
<td><p><a href="lync-server-2013-including-the-security-desk.md">在 Lync Server 2013 中包括安全服务台</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-including-the-security-desk.md">在 Lync Server 2013 中包括安全服务台</a></p></td>
<td><p><a href="lync-server-2013-defining-the-location-policy.md">为 Lync Server 2013 定义位置策略</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">选择 Lync Server 2013 的 E9-1-1 服务提供商</a></p></td>
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">在 Lync Server 2013 中分配位置策略作用域</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-location-policy.md">为 Lync Server 2013 定义位置策略</a></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">在 Lync Server 2013 中分配位置策略作用域</a></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## 本部分内容

  - [在 Lync Server 2013 中定义 E9-1-1 部署的范围](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [在 Lync Server 2013 中定义用于确定位置的网络元素](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [在 Lync Server 2013 中为用户启用 E9-1-1](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [在 Lync Server 2013 中管理 SIP 中继服务提供商的位置](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [在 Lync Server 2013 中管理 ELIN 网关的位置](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [在 Lync Server 2013 中定义手动获取位置的用户体验](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [在 Lync Server 2013 中为 E9-1-1 设计 SIP 中继](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [在 Lync Server 2013 中包括安全服务台](lync-server-2013-including-the-security-desk.md)

  - [选择 Lync Server 2013 的 E9-1-1 服务提供商](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [为 Lync Server 2013 定义位置策略](lync-server-2013-defining-the-location-policy.md)

  - [在 Lync Server 2013 中分配位置策略作用域](lync-server-2013-assigning-location-policy-scope.md)

