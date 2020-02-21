---
title: Lync Server 2013：会议的基于位置的路由概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing for conferencing
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56335084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b280272d17cf40734a24b553ad00a7a485547c2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="f6bc0-102">Lync Server 2013 中的会议基于位置的路由概述</span><span class="sxs-lookup"><span data-stu-id="f6bc0-102">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6bc0-103">_**上次修改的主题：** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="f6bc0-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="f6bc0-104">基于位置的路由会议应用程序为 Lync 会议提供了阻止 PSTN 收费旁路的机制。</span><span class="sxs-lookup"><span data-stu-id="f6bc0-104">The Location-Based Routing Conferencing application provides to Lync Conferences a mechanism for the prevention of PSTN toll bypass.</span></span> <span data-ttu-id="f6bc0-105">该应用程序监视活动会议，并根据所参与的 Lync 用户的位置强制实施基于位置的路由限制。</span><span class="sxs-lookup"><span data-stu-id="f6bc0-105">The application monitors active conferences and enforces Location-Based Routing restrictions based on the location of the Lync users participating.</span></span>

<span data-ttu-id="f6bc0-106">如果满足以下条件，则基于位置的路由会议应用程序将确定是否在 Lync 会议上强制实施基于位置的路由：</span><span class="sxs-lookup"><span data-stu-id="f6bc0-106">The Location-Based Routing Conferencing application determines whether Location-Based Routing is to be enforced on a Lync meeting if the following criteria are met:</span></span>

  - <span data-ttu-id="f6bc0-107">会议组织者启用了基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="f6bc0-107">The meeting organizer is enabled for Location-Based Routing.</span></span> <span data-ttu-id="f6bc0-108">基于位置的路由限制将仅应用于由启用了基于位置的路由的用户组织的会议。</span><span class="sxs-lookup"><span data-stu-id="f6bc0-108">Location-Based Routing restrictions will be applied only to conferences that are organized by users who are enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="f6bc0-109">至少有一个会议参与者是 PSTN 终结点。</span><span class="sxs-lookup"><span data-stu-id="f6bc0-109">At least one meeting participant is a PSTN endpoint.</span></span> <span data-ttu-id="f6bc0-110">基于位置的路由限制仅适用于包含 PSTN 终结点的会议。</span><span class="sxs-lookup"><span data-stu-id="f6bc0-110">Location-Based Routing restrictions are applicable only for conferences that include PSTN endpoints.</span></span>

  - <span data-ttu-id="f6bc0-111">PSTN 网关用于将会议桥接到 PSTN 的网络站点，以及组织者和参与者从中连接的网络站点。</span><span class="sxs-lookup"><span data-stu-id="f6bc0-111">The network site where the PSTN gateway used to bridge the conference to the PSTN is located as well as the network sites where the organizers and participants are connecting from.</span></span>

<span data-ttu-id="f6bc0-112">基于位置的路由会议应用程序阻止将 Lync 用户和 PSTN 终结点从不同的网络站点加入同一会议。</span><span class="sxs-lookup"><span data-stu-id="f6bc0-112">The Location-Based Routing Conferencing application prevents the participation of Lync users and PSTN endpoints from different network sites to the same conference.</span></span> <span data-ttu-id="f6bc0-113">如果为会议的组织者启用了基于位置的路由，会议应用程序将强制实施以下限制：</span><span class="sxs-lookup"><span data-stu-id="f6bc0-113">If the organizer of a meeting is enabled for Location-Based Routing, the Conferencing application enforces the following restrictions:</span></span>

  - <span data-ttu-id="f6bc0-114">可以加入 Lync 会议的终结点取决于已加入会议的终结点，并且此限制将根据联接的终结点保留，并将新的终结点加入会议进行调整。</span><span class="sxs-lookup"><span data-stu-id="f6bc0-114">The endpoints that can join a Lync meeting depend on the endpoints that already joined the conference, and this restriction adjusts as joined endpoints leave and new endpoints join the conference.</span></span> <span data-ttu-id="f6bc0-115">如果组织者和参与者从同一个网络站点加入 Lync 会议，则来自同一网络站点的另一个参与者、来自不同网络站点的另一个参与者或来自未知网络站点的参与者允许加入.</span><span class="sxs-lookup"><span data-stu-id="f6bc0-115">If organizers and participants are joining a Lync meeting from the same network site, then a PSTN endpoint, another participant from the same network site, another participant from a different network site or a participant from an unknown network site are allowed to join.</span></span>

  - <span data-ttu-id="f6bc0-116">如果组织者和参与者从不同或未知网络站点加入会议，则不允许 PSTN 终结点加入会议（如果 PSTN 呼叫 ingresses 来自 SIP 中继启用基于位置的路由）。</span><span class="sxs-lookup"><span data-stu-id="f6bc0-116">If organizers and participants are joining the meeting from different or unknown network sites, a PSTN endpoint is not allowed to join the meeting if the PSTN call ingresses from a SIP trunk enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="f6bc0-117">如果组织者和参与者都从同一个网络站点加入会议，并且有参与者加入来自 PSTN 的同一会议，则不允许来自不同网络站点的 Lync 终结点加入会议。</span><span class="sxs-lookup"><span data-stu-id="f6bc0-117">If organizers and participants are all joining the meeting from the same network site and there are participants joining the same meeting from the PSTN, a Lync endpoint from a different network site is not allowed to join the meeting.</span></span>

<span data-ttu-id="f6bc0-118">下表汇总了这些基于会议位置的路由限制。</span><span class="sxs-lookup"><span data-stu-id="f6bc0-118">These conferencing Location-Based Routing restrictions are summarized in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6bc0-119">在任意给定时刻会议中的用户</span><span class="sxs-lookup"><span data-stu-id="f6bc0-119">User(s) in a conference at any given point</span></span></p></td>
<td><p><span data-ttu-id="f6bc0-120">允许加入会议的用户</span><span class="sxs-lookup"><span data-stu-id="f6bc0-120">User(s) allowed to join the conference</span></span></p></td>
<td><p><span data-ttu-id="f6bc0-121">不允许用户加入会议</span><span class="sxs-lookup"><span data-stu-id="f6bc0-121">User(s) not allowed to join the conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6bc0-122">来自单个网络站点的 Lync VoIP 客户端用户</span><span class="sxs-lookup"><span data-stu-id="f6bc0-122">Lync VoIP client user(s) from a single network site</span></span></p></td>
<td><p><span data-ttu-id="f6bc0-123">来自相同网络站点的 Lync VoIP 客户端用户</span><span class="sxs-lookup"><span data-stu-id="f6bc0-123">Lync VoIP client user from the same network site</span></span></p>
<p><span data-ttu-id="f6bc0-124">来自不同网络站点的 Lync VoIP 客户端用户</span><span class="sxs-lookup"><span data-stu-id="f6bc0-124">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="f6bc0-125">来自未知网络站点的 Lync VoIP 客户端用户</span><span class="sxs-lookup"><span data-stu-id="f6bc0-125">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="f6bc0-126">联合 Lync VoIP 客户端用户</span><span class="sxs-lookup"><span data-stu-id="f6bc0-126">Federated Lync VoIP client user</span></span></p>
<p><span data-ttu-id="f6bc0-127">从 PSTN 终结点加入的用户</span><span class="sxs-lookup"><span data-stu-id="f6bc0-127">User joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="f6bc0-128">无</span><span class="sxs-lookup"><span data-stu-id="f6bc0-128">None</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6bc0-129">来自未知网络站点的 Lync VoIP 客户端用户</span><span class="sxs-lookup"><span data-stu-id="f6bc0-129">Lync VoIP client user(s) from an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="f6bc0-130">来自任何网站的 Lync VoIP 客户端用户</span><span class="sxs-lookup"><span data-stu-id="f6bc0-130">Lync VoIP client user from any site</span></span></p>
<p><span data-ttu-id="f6bc0-131">来自未知网站的 Lync VoIP 客户端用户</span><span class="sxs-lookup"><span data-stu-id="f6bc0-131">Lync VoIP client user from an unknown site</span></span></p>
<p><span data-ttu-id="f6bc0-132">联合 Lync VoIP 客户端用户</span><span class="sxs-lookup"><span data-stu-id="f6bc0-132">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="f6bc0-133">通过 PSTN 终结点加入的用户</span><span class="sxs-lookup"><span data-stu-id="f6bc0-133">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6bc0-134">来自不同网络站点的 Lync VoIP 客户端用户</span><span class="sxs-lookup"><span data-stu-id="f6bc0-134">Lync VoIP client users from different network sites</span></span></p></td>
<td><p><span data-ttu-id="f6bc0-135">来自任何网络站点的 Lync VoIP 客户端用户</span><span class="sxs-lookup"><span data-stu-id="f6bc0-135">Lync VoIP client user from any network site</span></span></p>
<p><span data-ttu-id="f6bc0-136">来自未知网络站点的 Lync VoIP 客户端用户</span><span class="sxs-lookup"><span data-stu-id="f6bc0-136">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="f6bc0-137">联合 Lync VoIP 客户端用户</span><span class="sxs-lookup"><span data-stu-id="f6bc0-137">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="f6bc0-138">通过 PSTN 终结点加入的用户</span><span class="sxs-lookup"><span data-stu-id="f6bc0-138">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6bc0-139">来自单个网络站点的 Lync VoIP 客户端用户和从 PSTN 终结点加入的用户</span><span class="sxs-lookup"><span data-stu-id="f6bc0-139">Lync VoIP client user(s) from a single network site and users joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="f6bc0-140">来自相同网络站点的 Lync VoIP 客户端用户</span><span class="sxs-lookup"><span data-stu-id="f6bc0-140">Lync VoIP client user from the same network site</span></span></p></td>
<td><p><span data-ttu-id="f6bc0-141">来自不同网络站点的 Lync VoIP 客户端用户</span><span class="sxs-lookup"><span data-stu-id="f6bc0-141">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="f6bc0-142">来自未知网络站点的 Lync VoIP 客户端用户</span><span class="sxs-lookup"><span data-stu-id="f6bc0-142">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="f6bc0-143">联合 Lync VoIP 客户端用户</span><span class="sxs-lookup"><span data-stu-id="f6bc0-143">Federated Lync VoIP client user</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f6bc0-144">以下是基于位置的路由会议应用程序的其他特征：</span><span class="sxs-lookup"><span data-stu-id="f6bc0-144">The following are additional characteristics of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="f6bc0-145">如果不允许用户加入会议给定的基于位置的路由限制，则对会议的用户呼叫将被拒绝，并且他的 Lync 客户端将报告呼叫未完成或已结束。</span><span class="sxs-lookup"><span data-stu-id="f6bc0-145">When a user is not allowed to join a conference given Location-Based Routing restrictions, the users call to the conference will be rejected and his Lync Client will report that the call was not completed or has ended.</span></span>

  - <span data-ttu-id="f6bc0-146">使用基于位置的路由之后加入会议的 PSTN 终结点如果终结点通过未启用基于位置的路由的中继进行联接，则不会限制加入会议的会议。</span><span class="sxs-lookup"><span data-stu-id="f6bc0-146">A PSTN endpoint joining a conference with Location-Based Routing enforcements will not be restricted to join the conference regardless of its state if the endpoint joins via a trunk that is not enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="f6bc0-147">通过 SIP 中继连接到 Mediations 服务器的 PBX 系统不会对 PSTN 进行传出呼叫，这将与在定义 SIP 中继的同一网络站点中的 Lync 用户具有相同的之后。</span><span class="sxs-lookup"><span data-stu-id="f6bc0-147">A PBX system connected to a Mediations Server over a SIP trunk that does not egress calls to the PSTN will have the same enforcements as Lync users located in the same network site where the SIP trunk is defined.</span></span> <span data-ttu-id="f6bc0-148">例如，PSTN 终结点将能够通过 PBX 用户和 Lync 用户加入会议（如果它们位于同一网络站点中）;否则，如果 PBX 用户位于与 Lync 用户不同的网络站点中，则不允许 PSTN 终结点加入会议。</span><span class="sxs-lookup"><span data-stu-id="f6bc0-148">For example, a PSTN endpoint will be able to join a conference with a PBX user and a Lync user if they are located in the same network site; otherwise, the PSTN endpoint will not be allowed to join the conference if the PBX user is in a different network site than the Lync user.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

