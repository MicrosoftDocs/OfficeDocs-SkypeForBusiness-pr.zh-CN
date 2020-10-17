---
title: Lync Server 2013：定义紧急呼叫的要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for emergency calls
ms:assetid: 5c12b517-9be6-41d0-83e2-11c78793620c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398404(v=OCS.15)
ms:contentKeyID: 48184276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d190d240db85016bd13bfd2480b42b088ca5f88
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504359"
---
# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a>在 Lync Server 2013 中定义紧急呼叫要求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-06-06_

在开始 Microsoft Lync Server 2013 E9-1-1 部署之前，应首先回答以下部分中详细介绍的问题。 您需要执行的规划取决于选择部署的 E9-1-1 解决方案的类型 - SIP 中继 E9-1-1 服务提供商或紧急位置标识符号 (ELIN) 网关。 下表确定了本规划工作簿中您需要针对上述每个解决方案回顾的部分。

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a>按 E9-1-1 解决方案的类型显示的规划步骤

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
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">定义用于确定 Lync Server 2013 中的位置的网络元素</a></p></td>
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">定义用于确定 Lync Server 2013 中的位置的网络元素</a></p></td>
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
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">定义在 Lync Server 2013 中手动获取位置的用户体验</a></p></td>
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">定义在 Lync Server 2013 中手动获取位置的用户体验</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">在 Lync Server 2013 中为 E9-1-1 设计 SIP 中继</a></p></td>
<td><p><a href="lync-server-2013-including-the-security-desk.md">在 Lync Server 2013 中包括安全桌面</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-including-the-security-desk.md">在 Lync Server 2013 中包括安全桌面</a></p></td>
<td><p><a href="lync-server-2013-defining-the-location-policy.md">定义 Lync Server 2013 的位置策略</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">为 Lync Server 2013 选择 E9-1-1 服务提供商</a></p></td>
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">在 Lync Server 2013 中分配位置策略作用域</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-location-policy.md">定义 Lync Server 2013 的位置策略</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">在 Lync Server 2013 中分配位置策略作用域</a></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中定义 E9-1-1 部署的范围](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [定义用于确定 Lync Server 2013 中的位置的网络元素](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [在 Lync Server 2013 中为用户启用 E9-1-1](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [在 Lync Server 2013 中管理 SIP 中继服务提供商的位置](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [在 Lync Server 2013 中管理 ELIN 网关的位置](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [定义在 Lync Server 2013 中手动获取位置的用户体验](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [在 Lync Server 2013 中为 E9-1-1 设计 SIP 中继](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [在 Lync Server 2013 中包括安全桌面](lync-server-2013-including-the-security-desk.md)

  - [为 Lync Server 2013 选择 E9-1-1 服务提供商](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [定义 Lync Server 2013 的位置策略](lync-server-2013-defining-the-location-policy.md)

  - [在 Lync Server 2013 中分配位置策略作用域](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

