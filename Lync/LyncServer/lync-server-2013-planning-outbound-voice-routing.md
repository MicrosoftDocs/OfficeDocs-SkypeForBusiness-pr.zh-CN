---
title: Lync Server 2013：规划出站语音路由
description: Lync Server 2013：规划出站语音路由。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning outbound voice routing
ms:assetid: 37c55fa4-175a-4190-b9e4-c2e5ac7b9261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425853(v=OCS.15)
ms:contentKeyID: 48183835
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 057f81b995e231c2025a9fcb07e675086a662efe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563978"
---
# <a name="planning-outbound-voice-routing-in-lync-server-2013"></a><span data-ttu-id="ca310-103">在 Lync Server 2013 中规划出站语音路由</span><span class="sxs-lookup"><span data-stu-id="ca310-103">Planning outbound voice routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca310-104">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ca310-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="ca310-p101">出站呼叫路由适用于发往公用电话交换网 (PSTN) 网关、中继或专用交换机 (PBX) 的呼叫。当用户发出呼叫时，服务器会在必要时将电话号码规范化为 E.164 格式，并尝试将其与 SIP URI 进行匹配。如果服务器无法进行匹配，则会根据提供的拨号串应用出站呼叫路由逻辑。通过配置下表中所述的服务器设置定义该逻辑。</span><span class="sxs-lookup"><span data-stu-id="ca310-p101">Outbound call routing applies to calls that are destined for a public switched telephone network (PSTN) gateway, trunk, or private branch exchange (PBX). When a user places a call, the server normalizes the phone number to E.164 format, if necessary, and attempts to match it to a SIP URI. If the server cannot make the match, it applies outbound call routing logic based on the supplied dial string. You define that logic by configuring the server settings that are described in the following table.</span></span>

### <a name="lync-server-outbound-call-routing-settings"></a><span data-ttu-id="ca310-109">Lync Server 出站呼叫路由设置</span><span class="sxs-lookup"><span data-stu-id="ca310-109">Lync Server Outbound Call Routing Settings</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca310-110">Object</span><span class="sxs-lookup"><span data-stu-id="ca310-110">Object</span></span></th>
<th><span data-ttu-id="ca310-111">说明</span><span class="sxs-lookup"><span data-stu-id="ca310-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca310-112">拨号计划</span><span class="sxs-lookup"><span data-stu-id="ca310-112">Dial Plan</span></span></p></td>
<td><p><span data-ttu-id="ca310-113">拨号计划是一组指定的规范化规则，可将指定位置、单个用户或联系对象的电话号码转换为统一标准 (E.164) 格式，以进行电话授权和呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="ca310-113">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca310-114">规范化规则</span><span class="sxs-lookup"><span data-stu-id="ca310-114">Normalization rule</span></span></p></td>
<td><p><span data-ttu-id="ca310-p102">规范化规则定义如何针对每个指定的位置、用户或联系对象来路由以不同格式表示的电话号码。同一拨号串的解析和转换可能不同，具体取决于拨打该号码的位置，以及发出呼叫的人员或联系对象。一组与特定位置相关联的规范化规则构成一个拨号计划。</span><span class="sxs-lookup"><span data-stu-id="ca310-p102">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object. The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object that makes the call. A set of normalization rules associated with a particular location constitutes a dial plan.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca310-118">语音策略</span><span class="sxs-lookup"><span data-stu-id="ca310-118">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="ca310-p103">语音策略将一个或多个 PSTN 用法记录与一个用户或一组用户相关联。语音策略还提供了可以启用或禁用的呼叫功能列表。</span><span class="sxs-lookup"><span data-stu-id="ca310-p103">A voice policy associates one or more PSTN usage records with one user or a group of users. A voice policy also provides a list of calling features that you can enable or disable.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca310-121">PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="ca310-121">PSTN usage record</span></span></p></td>
<td><p><span data-ttu-id="ca310-122">PSTN 用法记录指定组织中各个用户或用户组所能进行的呼叫类别（如内部、本地或长途）。</span><span class="sxs-lookup"><span data-stu-id="ca310-122">A PSTN usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users, or groups of users, in an organization.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca310-123">呼叫路由</span><span class="sxs-lookup"><span data-stu-id="ca310-123">Call Route</span></span></p></td>
<td><p><span data-ttu-id="ca310-p104">呼叫路由将目标电话号码与特定中继和 PSTN 用法记录相关联。PSTN 网关被视为中继。</span><span class="sxs-lookup"><span data-stu-id="ca310-p104">A call route associates destination phone numbers with particular trunks and PSTN usage records. A PSTN gateway is considered a trunk.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="ca310-126">本部分内容</span><span class="sxs-lookup"><span data-stu-id="ca310-126">In This Section</span></span>

<span data-ttu-id="ca310-127">本节提供配置以下出站呼叫路由服务器设置的指南：</span><span class="sxs-lookup"><span data-stu-id="ca310-127">This section provides guidelines for configuring the following outbound call routing server settings:</span></span>

  - <span></span>  
    [<span data-ttu-id="ca310-128">Lync Server 2013 中的拨号计划和规范化规则</span><span class="sxs-lookup"><span data-stu-id="ca310-128">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)

  - <span></span>  
    [<span data-ttu-id="ca310-129">Lync Server 2013 中的语音策略</span><span class="sxs-lookup"><span data-stu-id="ca310-129">Voice policies in Lync Server 2013</span></span>](lync-server-2013-voice-policies.md)

  - <span></span>  
    [<span data-ttu-id="ca310-130">Lync Server 2013 中的 PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="ca310-130">PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-pstn-usage-records.md)

  - <span></span>  
    [<span data-ttu-id="ca310-131">Lync Server 2013 中的语音路由</span><span class="sxs-lookup"><span data-stu-id="ca310-131">Voice routes in Lync Server 2013</span></span>](lync-server-2013-voice-routes.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ca310-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca310-132">See Also</span></span>


[<span data-ttu-id="ca310-133">Lync Server 2013 中的 SIP 中继</span><span class="sxs-lookup"><span data-stu-id="ca310-133">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)  
[<span data-ttu-id="ca310-134">Lync Server 2013 中的直接 SIP 连接</span><span class="sxs-lookup"><span data-stu-id="ca310-134">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

