---
title: Lync Server 2013： PSTN 用法记录
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60700070c5426d4df4d1957367ccfd743a5ba44b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042029"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="eb5fa-102">Lync Server 2013 中的 PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="eb5fa-102">PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb5fa-103">_**上次修改的主题：** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="eb5fa-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="eb5fa-p101">规划 PSTN 用法记录的主要任务是列出当前在贵组织中对从 CEO 到临时工、顾问在内的所有员工实施的所有呼叫权限。此过程还提供了一个重新检查现有呼叫权限并进行修改的机会。可以只为那些应用于预期企业语音用户的呼叫权限创建 PSTN 用法记录，但是，更好的长期解决方案可能是为所有呼叫权限创建 PSTN 用法记录，而无论其中的某些权限当前是否应用于要为企业语音启用的用户组。如果呼叫权限发生变化或者添加了具有不同呼叫权限的新用户，会创建所需的 PSTN 用法记录。</span><span class="sxs-lookup"><span data-stu-id="eb5fa-p101">Planning PSTN usage records consists mainly of listing all the call permissions that are currently in force in your organization, from the CEO to temporary workers, consultants, and contingent staff. This process also provides an opportunity to reexamine existing call permissions and revise them. You can create PSTN usage records only for those call permissions that apply to your anticipated Enterprise Voice users, but a better long-range solution might be to create PSTN usage records for all call permissions, regardless of whether some may not currently apply to the group of users to be enabled for Enterprise Voice. If call permissions change or new users with different call permissions are added, you will have already created the required PSTN usage records.</span></span>

<span data-ttu-id="eb5fa-108">下表显示了典型的 PSTN 用法表。</span><span class="sxs-lookup"><span data-stu-id="eb5fa-108">The following table shows a typical PSTN usage table.</span></span>

### <a name="pstn-usage-records"></a><span data-ttu-id="eb5fa-109">PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="eb5fa-109">PSTN Usage Records</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb5fa-110">电话属性</span><span class="sxs-lookup"><span data-stu-id="eb5fa-110">Phone attribute</span></span></th>
<th><span data-ttu-id="eb5fa-111">说明</span><span class="sxs-lookup"><span data-stu-id="eb5fa-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb5fa-112">Local</span><span class="sxs-lookup"><span data-stu-id="eb5fa-112">Local</span></span></p></td>
<td><p><span data-ttu-id="eb5fa-113">本地电话</span><span class="sxs-lookup"><span data-stu-id="eb5fa-113">Local calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb5fa-114">远距离</span><span class="sxs-lookup"><span data-stu-id="eb5fa-114">Long-Distance</span></span></p></td>
<td><p><span data-ttu-id="eb5fa-115">长途电话</span><span class="sxs-lookup"><span data-stu-id="eb5fa-115">Long distance calls</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb5fa-116">International</span><span class="sxs-lookup"><span data-stu-id="eb5fa-116">International</span></span></p></td>
<td><p><span data-ttu-id="eb5fa-117">国际电话</span><span class="sxs-lookup"><span data-stu-id="eb5fa-117">International calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb5fa-118">德里</span><span class="sxs-lookup"><span data-stu-id="eb5fa-118">Delhi</span></span></p></td>
<td><p><span data-ttu-id="eb5fa-119">德里全职员工</span><span class="sxs-lookup"><span data-stu-id="eb5fa-119">Delhi full-time employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb5fa-120">雷蒙德</span><span class="sxs-lookup"><span data-stu-id="eb5fa-120">Redmond</span></span></p></td>
<td><p><span data-ttu-id="eb5fa-121">雷德蒙德全职员工</span><span class="sxs-lookup"><span data-stu-id="eb5fa-121">Redmond full-time employees</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb5fa-122">RedmondTemps</span><span class="sxs-lookup"><span data-stu-id="eb5fa-122">RedmondTemps</span></span></p></td>
<td><p><span data-ttu-id="eb5fa-123">雷德蒙德临时员工</span><span class="sxs-lookup"><span data-stu-id="eb5fa-123">Redmond temporary employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb5fa-124">苏黎世</span><span class="sxs-lookup"><span data-stu-id="eb5fa-124">Zurich</span></span></p></td>
<td><p><span data-ttu-id="eb5fa-125">苏黎世全职员工</span><span class="sxs-lookup"><span data-stu-id="eb5fa-125">Zurich full-time employees</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="eb5fa-p102">PSTN 用法记录本身不执行任何操作。为了使它们正常工作，必须执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="eb5fa-p102">By themselves, PSTN usage records do not do anything. For them to work, you must associate them with the following:</span></span>

  - <span data-ttu-id="eb5fa-128">将它们与分配给用户的语音策略相关联。</span><span class="sxs-lookup"><span data-stu-id="eb5fa-128">Voice policies, which are assigned to users.</span></span>

  - <span data-ttu-id="eb5fa-129">将它们与分配给电话号码的路由相关联。</span><span class="sxs-lookup"><span data-stu-id="eb5fa-129">Routes, which are assigned to phone numbers.</span></span>

<span data-ttu-id="eb5fa-130">有关语音策略和路由的详细信息，请参阅 lync server [2013 中的语音策略](lync-server-2013-voice-policies.md)和[lync server 2013 中的语音路由](lync-server-2013-voice-routes.md)。</span><span class="sxs-lookup"><span data-stu-id="eb5fa-130">For details about voice policies and routes, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md) and [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span> <span data-ttu-id="eb5fa-131">有关如何创建和配置这些设置的详细信息，请参阅[在 Lync Server 2013 中配置出站呼叫的语音路由](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)。</span><span class="sxs-lookup"><span data-stu-id="eb5fa-131">For details about how to create and configure them, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

