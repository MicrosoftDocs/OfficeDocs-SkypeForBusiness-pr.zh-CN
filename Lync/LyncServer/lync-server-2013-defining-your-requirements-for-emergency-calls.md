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
ms.openlocfilehash: 4455e7072e6bdb25fb2b2bc0cd4e7bc39f1f05d1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a><span data-ttu-id="a3011-102">在 Lync Server 2013 中定义紧急呼叫要求</span><span class="sxs-lookup"><span data-stu-id="a3011-102">Defining your requirements for emergency calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3011-103">_**上次修改的主题：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="a3011-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="a3011-104">在开始 Microsoft Lync Server 2013 E9-1-1 部署之前，应首先回答以下部分中详细介绍的问题。</span><span class="sxs-lookup"><span data-stu-id="a3011-104">Before you begin a Microsoft Lync Server 2013 E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="a3011-105">您需要执行的规划取决于选择部署的 E9-1-1 解决方案的类型 - SIP 中继 E9-1-1 服务提供商或紧急位置标识符号 (ELIN) 网关。</span><span class="sxs-lookup"><span data-stu-id="a3011-105">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="a3011-106">下表确定了本规划工作簿中您需要针对上述每个解决方案回顾的部分。</span><span class="sxs-lookup"><span data-stu-id="a3011-106">The following table identifies the sections in this planning workbook that you’ll need to review for each of those solutions.</span></span>

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a><span data-ttu-id="a3011-107">按 E9-1-1 解决方案的类型显示的规划步骤</span><span class="sxs-lookup"><span data-stu-id="a3011-107">Planning Steps by Type of E9-1-1 Solution</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3011-108">SIP 中继服务提供商</span><span class="sxs-lookup"><span data-stu-id="a3011-108">SIP trunk service provider</span></span></th>
<th><span data-ttu-id="a3011-109">ELIN 网关</span><span class="sxs-lookup"><span data-stu-id="a3011-109">ELIN gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3011-110"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">在 Lync Server 2013 中定义 E9-1-1 部署的范围</a></span><span class="sxs-lookup"><span data-stu-id="a3011-110"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3011-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">在 Lync Server 2013 中定义 E9-1-1 部署的范围</a></span><span class="sxs-lookup"><span data-stu-id="a3011-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3011-112"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">定义用于确定 Lync Server 2013 中的位置的网络元素</a></span><span class="sxs-lookup"><span data-stu-id="a3011-112"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3011-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">定义用于确定 Lync Server 2013 中的位置的网络元素</a></span><span class="sxs-lookup"><span data-stu-id="a3011-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3011-114"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">在 Lync Server 2013 中为用户启用 E9-1-1</a></span><span class="sxs-lookup"><span data-stu-id="a3011-114"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3011-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">在 Lync Server 2013 中为用户启用 E9-1-1</a></span><span class="sxs-lookup"><span data-stu-id="a3011-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3011-116"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">在 Lync Server 2013 中管理 SIP 中继服务提供商的位置</a></span><span class="sxs-lookup"><span data-stu-id="a3011-116"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Managing locations for SIP trunk service providers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3011-117"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">在 Lync Server 2013 中管理 ELIN 网关的位置</a></span><span class="sxs-lookup"><span data-stu-id="a3011-117"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Managing locations for ELIN gateways in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3011-118"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">定义在 Lync Server 2013 中手动获取位置的用户体验</a></span><span class="sxs-lookup"><span data-stu-id="a3011-118"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3011-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">定义在 Lync Server 2013 中手动获取位置的用户体验</a></span><span class="sxs-lookup"><span data-stu-id="a3011-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3011-120"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">在 Lync Server 2013 中为 E9-1-1 设计 SIP 中继</a></span><span class="sxs-lookup"><span data-stu-id="a3011-120"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Designing the SIP trunk for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3011-121"><a href="lync-server-2013-including-the-security-desk.md">在 Lync Server 2013 中包括安全桌面</a></span><span class="sxs-lookup"><span data-stu-id="a3011-121"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3011-122"><a href="lync-server-2013-including-the-security-desk.md">在 Lync Server 2013 中包括安全桌面</a></span><span class="sxs-lookup"><span data-stu-id="a3011-122"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3011-123"><a href="lync-server-2013-defining-the-location-policy.md">定义 Lync Server 2013 的位置策略</a></span><span class="sxs-lookup"><span data-stu-id="a3011-123"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3011-124"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">为 Lync Server 2013 选择 E9-1-1 服务提供商</a></span><span class="sxs-lookup"><span data-stu-id="a3011-124"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Choosing an E9-1-1 service provider for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a3011-125"><a href="lync-server-2013-assigning-location-policy-scope.md">在 Lync Server 2013 中分配位置策略作用域</a></span><span class="sxs-lookup"><span data-stu-id="a3011-125"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3011-126"><a href="lync-server-2013-defining-the-location-policy.md">定义 Lync Server 2013 的位置策略</a></span><span class="sxs-lookup"><span data-stu-id="a3011-126"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3011-127"><a href="lync-server-2013-assigning-location-policy-scope.md">在 Lync Server 2013 中分配位置策略作用域</a></span><span class="sxs-lookup"><span data-stu-id="a3011-127"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="a3011-128">本部分内容</span><span class="sxs-lookup"><span data-stu-id="a3011-128">In This Section</span></span>

  - [<span data-ttu-id="a3011-129">在 Lync Server 2013 中定义 E9-1-1 部署的范围</span><span class="sxs-lookup"><span data-stu-id="a3011-129">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [<span data-ttu-id="a3011-130">定义用于确定 Lync Server 2013 中的位置的网络元素</span><span class="sxs-lookup"><span data-stu-id="a3011-130">Defining the network elements used to determine location in Lync Server 2013</span></span>](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [<span data-ttu-id="a3011-131">在 Lync Server 2013 中为用户启用 E9-1-1</span><span class="sxs-lookup"><span data-stu-id="a3011-131">Enabling users for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [<span data-ttu-id="a3011-132">在 Lync Server 2013 中管理 SIP 中继服务提供商的位置</span><span class="sxs-lookup"><span data-stu-id="a3011-132">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [<span data-ttu-id="a3011-133">在 Lync Server 2013 中管理 ELIN 网关的位置</span><span class="sxs-lookup"><span data-stu-id="a3011-133">Managing locations for ELIN gateways in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [<span data-ttu-id="a3011-134">定义在 Lync Server 2013 中手动获取位置的用户体验</span><span class="sxs-lookup"><span data-stu-id="a3011-134">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [<span data-ttu-id="a3011-135">在 Lync Server 2013 中为 E9-1-1 设计 SIP 中继</span><span class="sxs-lookup"><span data-stu-id="a3011-135">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [<span data-ttu-id="a3011-136">在 Lync Server 2013 中包括安全桌面</span><span class="sxs-lookup"><span data-stu-id="a3011-136">Including the security desk in Lync Server 2013</span></span>](lync-server-2013-including-the-security-desk.md)

  - [<span data-ttu-id="a3011-137">为 Lync Server 2013 选择 E9-1-1 服务提供商</span><span class="sxs-lookup"><span data-stu-id="a3011-137">Choosing an E9-1-1 service provider for Lync Server 2013</span></span>](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [<span data-ttu-id="a3011-138">定义 Lync Server 2013 的位置策略</span><span class="sxs-lookup"><span data-stu-id="a3011-138">Defining the location policy for Lync Server 2013</span></span>](lync-server-2013-defining-the-location-policy.md)

  - [<span data-ttu-id="a3011-139">在 Lync Server 2013 中分配位置策略作用域</span><span class="sxs-lookup"><span data-stu-id="a3011-139">Assigning location policy scope in Lync Server 2013</span></span>](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

