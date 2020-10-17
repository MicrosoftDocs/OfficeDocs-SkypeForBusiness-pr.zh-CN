---
title: Lync Server 2013：分配每用户状态策略
description: Lync Server 2013：分配每用户状态策略。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user presence policies
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48185955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c3d4b4bda0c4bb85065d546fdbb4b2578db0e3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563368"
---
# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a><span data-ttu-id="26b32-103">在 Lync Server 2013 中分配每用户状态策略</span><span class="sxs-lookup"><span data-stu-id="26b32-103">Assigning per-user presence policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26b32-104">_**上次修改的主题：** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="26b32-104">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="26b32-105">状态策略是一组影响状态的限制和限制。</span><span class="sxs-lookup"><span data-stu-id="26b32-105">A presence policy is a set of limits and restrictions that affect presence.</span></span> <span data-ttu-id="26b32-106">下表描述了 Lync Server 2013 中可用的状态策略设置。</span><span class="sxs-lookup"><span data-stu-id="26b32-106">The following table describes the presence policy settings available in Lync Server 2013.</span></span>

### <a name="presence-policy-settings"></a><span data-ttu-id="26b32-107">状态策略设置</span><span class="sxs-lookup"><span data-stu-id="26b32-107">Presence Policy Settings</span></span>

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
<th><span data-ttu-id="26b32-108">XML 名称</span><span class="sxs-lookup"><span data-stu-id="26b32-108">XML name</span></span></th>
<th><span data-ttu-id="26b32-109">显示名</span><span class="sxs-lookup"><span data-stu-id="26b32-109">Display name</span></span></th>
<th><span data-ttu-id="26b32-110">说明</span><span class="sxs-lookup"><span data-stu-id="26b32-110">Description</span></span></th>
<th><span data-ttu-id="26b32-111">类型</span><span class="sxs-lookup"><span data-stu-id="26b32-111">Type</span></span></th>
<th><span data-ttu-id="26b32-112">值</span><span class="sxs-lookup"><span data-stu-id="26b32-112">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="26b32-113">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="26b32-113">CategorySubscriptions</span></span></p></td>
<td><p><span data-ttu-id="26b32-114">订阅者类别订阅的最大数量</span><span class="sxs-lookup"><span data-stu-id="26b32-114">Maximum Number of Subscriber Category Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="26b32-115">限制订阅者类别订阅的数量。</span><span class="sxs-lookup"><span data-stu-id="26b32-115">Limits the number of subscriber category subscriptions.</span></span> <span data-ttu-id="26b32-116">例如，当 Communicator 订阅用户的状态时，它会获取每个联系人卡片、日历数据、便笺、服务和状态类别的类别订阅。</span><span class="sxs-lookup"><span data-stu-id="26b32-116">For example, when Communicator subscribes to a user’s presence, it obtains a category subscription for each of the contact card, calendar data, notes, services, and state categories.</span></span></p>
<p><span data-ttu-id="26b32-117">设置为0表示用户或联系人对象不能由其他人订阅。</span><span class="sxs-lookup"><span data-stu-id="26b32-117">A setting of 0 means that the user or contact object cannot be subscribed to by others.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="26b32-118">如果将此设置设置为较高的数值，则此设置可能会对性能产生重大影响，并且一般用户有大量订阅他或她的状态的用户。</span><span class="sxs-lookup"><span data-stu-id="26b32-118">This setting can have a significant impact on performance if it is set to a high number, and the average user has a large number of users subscribing to his or her presence.</span></span>


</div></td>
<td><p><span data-ttu-id="26b32-119">整数</span><span class="sxs-lookup"><span data-stu-id="26b32-119">Integer</span></span></p></td>
<td><p><span data-ttu-id="26b32-120">0-3000</span><span class="sxs-lookup"><span data-stu-id="26b32-120">0-3000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26b32-121">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="26b32-121">PromptedSubscribers</span></span></p></td>
<td><p><span data-ttu-id="26b32-122">排队状态订阅警报的最大数量</span><span class="sxs-lookup"><span data-stu-id="26b32-122">Maximum Number of Queued Presence Subscription Alerts</span></span></p></td>
<td><p><span data-ttu-id="26b32-123">限制 "提示订阅者" 表中的条目数。</span><span class="sxs-lookup"><span data-stu-id="26b32-123">Limits the number of entries in the prompted subscribers table.</span></span> <span data-ttu-id="26b32-124">此设置确定可为给定用户排队的最大提示数。</span><span class="sxs-lookup"><span data-stu-id="26b32-124">This setting determines the maximum number of prompts that can be queued for a given user.</span></span> <span data-ttu-id="26b32-125">例如，当用户 A 订阅用户 B 的状态时，用户 B 会收到一条提示，指明用户 A 现在已订阅用户 B，并在用户 B 的 "提示订阅者" 表中创建确认提示。</span><span class="sxs-lookup"><span data-stu-id="26b32-125">For example, when user A subscribes to user B’s presence, user B receives a prompt that user A is now subscribed to user B, and an acknowledgement prompt is created in user B’s prompted subscribers table.</span></span> <span data-ttu-id="26b32-126">在用户 B 接受（或确认）订阅后，将从用户 B 的 "提示订阅者" 表中删除确认提示。</span><span class="sxs-lookup"><span data-stu-id="26b32-126">After user B accepts, or acknowledges, the subscription, the acknowledgement prompt is removed from user B’s prompted subscribers table.</span></span></p>
<p><span data-ttu-id="26b32-127">设置为0表示当有人订阅他或她的状态时不会提示用户。</span><span class="sxs-lookup"><span data-stu-id="26b32-127">A setting of 0 means that the user is not prompted when someone subscribes to his or her presence.</span></span></p></td>
<td><p><span data-ttu-id="26b32-128">Integer 或 Token</span><span class="sxs-lookup"><span data-stu-id="26b32-128">Integer or Token</span></span></p></td>
<td><p><span data-ttu-id="26b32-129">0-500</span><span class="sxs-lookup"><span data-stu-id="26b32-129">0-500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="26b32-130">默认情况下，在您部署 Lync Server 时，会安装 " **默认策略** 和 **服务：中等** 状态策略"。</span><span class="sxs-lookup"><span data-stu-id="26b32-130">By default, the **Default Policy** and **Service: Medium** presence policies are installed when you deploy Lync Server.</span></span> <span data-ttu-id="26b32-131">下表介绍了这两种状态策略的特定设置。</span><span class="sxs-lookup"><span data-stu-id="26b32-131">The following table describes the specific settings of the two presence policies.</span></span>

### <a name="presence-policies"></a><span data-ttu-id="26b32-132">状态策略</span><span class="sxs-lookup"><span data-stu-id="26b32-132">Presence Policies</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="26b32-133">策略名称</span><span class="sxs-lookup"><span data-stu-id="26b32-133">Policy name</span></span></th>
<th><span data-ttu-id="26b32-134">说明</span><span class="sxs-lookup"><span data-stu-id="26b32-134">Description</span></span></th>
<th><span data-ttu-id="26b32-135">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="26b32-135">CategorySubscriptions</span></span></th>
<th><span data-ttu-id="26b32-136">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="26b32-136">PromptedSubscribers</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="26b32-137">默认策略</span><span class="sxs-lookup"><span data-stu-id="26b32-137">Default Policy</span></span></p></td>
<td><p><span data-ttu-id="26b32-138">典型用户的策略。</span><span class="sxs-lookup"><span data-stu-id="26b32-138">Policy for typical users.</span></span> <span data-ttu-id="26b32-139">这是默认的状态策略。</span><span class="sxs-lookup"><span data-stu-id="26b32-139">This is the default presence policy.</span></span></p></td>
<td><p><span data-ttu-id="26b32-140">1000</span><span class="sxs-lookup"><span data-stu-id="26b32-140">1000</span></span></p></td>
<td><p><span data-ttu-id="26b32-141">200</span><span class="sxs-lookup"><span data-stu-id="26b32-141">200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26b32-142">服务：中型</span><span class="sxs-lookup"><span data-stu-id="26b32-142">Service: Medium</span></span></p></td>
<td><p><span data-ttu-id="26b32-143">需要更多用户订阅对象状态的应用程序的策略。</span><span class="sxs-lookup"><span data-stu-id="26b32-143">Policy for applications that require more users to subscribe to the object’s presence.</span></span></p></td>
<td><p><span data-ttu-id="26b32-144">1000</span><span class="sxs-lookup"><span data-stu-id="26b32-144">1000</span></span></p></td>
<td><p><span data-ttu-id="26b32-145">0</span><span class="sxs-lookup"><span data-stu-id="26b32-145">0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

