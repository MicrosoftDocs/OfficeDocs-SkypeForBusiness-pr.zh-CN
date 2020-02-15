---
title: Lync Server 2013：分配每用户状态策略
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
ms.openlocfilehash: 618ab1b18f92d19f65084d321b71219cc0fafb06
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030025"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a><span data-ttu-id="cd76b-102">在 Lync Server 2013 中分配每用户状态策略</span><span class="sxs-lookup"><span data-stu-id="cd76b-102">Assigning per-user presence policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd76b-103">_**上次修改的主题：** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="cd76b-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="cd76b-104">状态策略是一组影响状态的限制和限制。</span><span class="sxs-lookup"><span data-stu-id="cd76b-104">A presence policy is a set of limits and restrictions that affect presence.</span></span> <span data-ttu-id="cd76b-105">下表描述了 Lync Server 2013 中可用的状态策略设置。</span><span class="sxs-lookup"><span data-stu-id="cd76b-105">The following table describes the presence policy settings available in Lync Server 2013.</span></span>

### <a name="presence-policy-settings"></a><span data-ttu-id="cd76b-106">状态策略设置</span><span class="sxs-lookup"><span data-stu-id="cd76b-106">Presence Policy Settings</span></span>

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
<th><span data-ttu-id="cd76b-107">XML 名称</span><span class="sxs-lookup"><span data-stu-id="cd76b-107">XML name</span></span></th>
<th><span data-ttu-id="cd76b-108">显示名</span><span class="sxs-lookup"><span data-stu-id="cd76b-108">Display name</span></span></th>
<th><span data-ttu-id="cd76b-109">说明</span><span class="sxs-lookup"><span data-stu-id="cd76b-109">Description</span></span></th>
<th><span data-ttu-id="cd76b-110">类型</span><span class="sxs-lookup"><span data-stu-id="cd76b-110">Type</span></span></th>
<th><span data-ttu-id="cd76b-111">值</span><span class="sxs-lookup"><span data-stu-id="cd76b-111">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cd76b-112">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="cd76b-112">CategorySubscriptions</span></span></p></td>
<td><p><span data-ttu-id="cd76b-113">订阅者类别订阅的最大数量</span><span class="sxs-lookup"><span data-stu-id="cd76b-113">Maximum Number of Subscriber Category Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="cd76b-114">限制订阅者类别订阅的数量。</span><span class="sxs-lookup"><span data-stu-id="cd76b-114">Limits the number of subscriber category subscriptions.</span></span> <span data-ttu-id="cd76b-115">例如，当 Communicator 订阅用户的状态时，它会获取每个联系人卡片、日历数据、便笺、服务和状态类别的类别订阅。</span><span class="sxs-lookup"><span data-stu-id="cd76b-115">For example, when Communicator subscribes to a user’s presence, it obtains a category subscription for each of the contact card, calendar data, notes, services, and state categories.</span></span></p>
<p><span data-ttu-id="cd76b-116">设置为0表示用户或联系人对象不能由其他人订阅。</span><span class="sxs-lookup"><span data-stu-id="cd76b-116">A setting of 0 means that the user or contact object cannot be subscribed to by others.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="cd76b-117">如果将此设置设置为较高的数值，则此设置可能会对性能产生重大影响，并且一般用户有大量订阅他或她的状态的用户。</span><span class="sxs-lookup"><span data-stu-id="cd76b-117">This setting can have a significant impact on performance if it is set to a high number, and the average user has a large number of users subscribing to his or her presence.</span></span>


</div></td>
<td><p><span data-ttu-id="cd76b-118">整数</span><span class="sxs-lookup"><span data-stu-id="cd76b-118">Integer</span></span></p></td>
<td><p><span data-ttu-id="cd76b-119">0-3000</span><span class="sxs-lookup"><span data-stu-id="cd76b-119">0-3000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd76b-120">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="cd76b-120">PromptedSubscribers</span></span></p></td>
<td><p><span data-ttu-id="cd76b-121">排队状态订阅警报的最大数量</span><span class="sxs-lookup"><span data-stu-id="cd76b-121">Maximum Number of Queued Presence Subscription Alerts</span></span></p></td>
<td><p><span data-ttu-id="cd76b-122">限制 "提示订阅者" 表中的条目数。</span><span class="sxs-lookup"><span data-stu-id="cd76b-122">Limits the number of entries in the prompted subscribers table.</span></span> <span data-ttu-id="cd76b-123">此设置确定可为给定用户排队的最大提示数。</span><span class="sxs-lookup"><span data-stu-id="cd76b-123">This setting determines the maximum number of prompts that can be queued for a given user.</span></span> <span data-ttu-id="cd76b-124">例如，当用户 A 订阅用户 B 的状态时，用户 B 会收到一条提示，指明用户 A 现在已订阅用户 B，并在用户 B 的 "提示订阅者" 表中创建确认提示。</span><span class="sxs-lookup"><span data-stu-id="cd76b-124">For example, when user A subscribes to user B’s presence, user B receives a prompt that user A is now subscribed to user B, and an acknowledgement prompt is created in user B’s prompted subscribers table.</span></span> <span data-ttu-id="cd76b-125">在用户 B 接受（或确认）订阅后，将从用户 B 的 "提示订阅者" 表中删除确认提示。</span><span class="sxs-lookup"><span data-stu-id="cd76b-125">After user B accepts, or acknowledges, the subscription, the acknowledgement prompt is removed from user B’s prompted subscribers table.</span></span></p>
<p><span data-ttu-id="cd76b-126">设置为0表示当有人订阅他或她的状态时不会提示用户。</span><span class="sxs-lookup"><span data-stu-id="cd76b-126">A setting of 0 means that the user is not prompted when someone subscribes to his or her presence.</span></span></p></td>
<td><p><span data-ttu-id="cd76b-127">Integer 或 Token</span><span class="sxs-lookup"><span data-stu-id="cd76b-127">Integer or Token</span></span></p></td>
<td><p><span data-ttu-id="cd76b-128">0-500</span><span class="sxs-lookup"><span data-stu-id="cd76b-128">0-500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cd76b-129">默认情况下，在您部署 Lync Server 时，会安装 "**默认策略**和**服务：中等**状态策略"。</span><span class="sxs-lookup"><span data-stu-id="cd76b-129">By default, the **Default Policy** and **Service: Medium** presence policies are installed when you deploy Lync Server.</span></span> <span data-ttu-id="cd76b-130">下表介绍了这两种状态策略的特定设置。</span><span class="sxs-lookup"><span data-stu-id="cd76b-130">The following table describes the specific settings of the two presence policies.</span></span>

### <a name="presence-policies"></a><span data-ttu-id="cd76b-131">状态策略</span><span class="sxs-lookup"><span data-stu-id="cd76b-131">Presence Policies</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cd76b-132">策略名称</span><span class="sxs-lookup"><span data-stu-id="cd76b-132">Policy name</span></span></th>
<th><span data-ttu-id="cd76b-133">说明</span><span class="sxs-lookup"><span data-stu-id="cd76b-133">Description</span></span></th>
<th><span data-ttu-id="cd76b-134">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="cd76b-134">CategorySubscriptions</span></span></th>
<th><span data-ttu-id="cd76b-135">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="cd76b-135">PromptedSubscribers</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cd76b-136">默认策略</span><span class="sxs-lookup"><span data-stu-id="cd76b-136">Default Policy</span></span></p></td>
<td><p><span data-ttu-id="cd76b-137">典型用户的策略。</span><span class="sxs-lookup"><span data-stu-id="cd76b-137">Policy for typical users.</span></span> <span data-ttu-id="cd76b-138">这是默认的状态策略。</span><span class="sxs-lookup"><span data-stu-id="cd76b-138">This is the default presence policy.</span></span></p></td>
<td><p><span data-ttu-id="cd76b-139">1000</span><span class="sxs-lookup"><span data-stu-id="cd76b-139">1000</span></span></p></td>
<td><p><span data-ttu-id="cd76b-140">200</span><span class="sxs-lookup"><span data-stu-id="cd76b-140">200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd76b-141">服务：中型</span><span class="sxs-lookup"><span data-stu-id="cd76b-141">Service: Medium</span></span></p></td>
<td><p><span data-ttu-id="cd76b-142">需要更多用户订阅对象状态的应用程序的策略。</span><span class="sxs-lookup"><span data-stu-id="cd76b-142">Policy for applications that require more users to subscribe to the object’s presence.</span></span></p></td>
<td><p><span data-ttu-id="cd76b-143">1000</span><span class="sxs-lookup"><span data-stu-id="cd76b-143">1000</span></span></p></td>
<td><p><span data-ttu-id="cd76b-144">0</span><span class="sxs-lookup"><span data-stu-id="cd76b-144">0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

