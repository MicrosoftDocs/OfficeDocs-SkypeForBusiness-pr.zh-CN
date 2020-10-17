---
title: Lync Server 2013： Lync 2013 中的客户端互操作性
description: Lync Server 2013： Lync 2013 中的客户端互操作性。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ea6e90d9479f03dd6d946787e70a2b3cc078699
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549608"
---
# <a name="client-interoperability-in-lync-2013"></a><span data-ttu-id="77bba-103">Lync 2013 中的客户端互操作性</span><span class="sxs-lookup"><span data-stu-id="77bba-103">Client interoperability in Lync 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77bba-104">_**上次修改的主题：** 2016-03-04_</span><span class="sxs-lookup"><span data-stu-id="77bba-104">_**Topic Last Modified:** 2016-03-04_</span></span>

<span data-ttu-id="77bba-105">本主题讨论 Microsoft Lync Server 2013 客户端与早期版本的 Lync Server 和 Office 通信服务器之间共存并与客户端进行交互的能力。</span><span class="sxs-lookup"><span data-stu-id="77bba-105">This topic discusses the ability of Microsoft Lync Server 2013 clients to coexist and interact with clients from earlier versions of Lync Server and Office Communications Server.</span></span>

<div>

## <a name="server-and-client-compatibility"></a><span data-ttu-id="77bba-106">服务器和客户端兼容性</span><span class="sxs-lookup"><span data-stu-id="77bba-106">Server and Client Compatibility</span></span>

<span data-ttu-id="77bba-107">下表显示受支持的客户端版本和服务器版本的组合。</span><span class="sxs-lookup"><span data-stu-id="77bba-107">The following table shows the supported combinations of client versions and server versions.</span></span> <span data-ttu-id="77bba-108">此表指示客户端尝试连接到指示的服务器时是否支持登录。</span><span class="sxs-lookup"><span data-stu-id="77bba-108">This table indicates whether sign-in is supported when the client attempts to connect to the server indicated.</span></span> <span data-ttu-id="77bba-109">Lync Server 2013 支持以前的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="77bba-109">Lync Server 2013 supports the previous client version.</span></span> <span data-ttu-id="77bba-110">此外，与以前的版本不同的是，Lync Server 2010 支持新的 Lync 2013 客户端。</span><span class="sxs-lookup"><span data-stu-id="77bba-110">Also, unlike previous releases, Lync Server 2010 supports the new Lync 2013 clients.</span></span> <span data-ttu-id="77bba-111">这使得从 Lync Server 2010 升级的组织可以独立于 Lync Server 升级来部署新的客户端。</span><span class="sxs-lookup"><span data-stu-id="77bba-111">This allows organizations who are upgrading from Lync Server 2010 to roll out new clients independent of Lync Server upgrades.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="77bba-112">客户端</span><span class="sxs-lookup"><span data-stu-id="77bba-112">Client</span></span></th>
<th><span data-ttu-id="77bba-113">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77bba-113">Lync Server 2013</span></span></th>
<th><span data-ttu-id="77bba-114">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="77bba-114">Lync Server 2010</span></span></th>
<th><span data-ttu-id="77bba-115">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="77bba-115">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77bba-116">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="77bba-116">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="77bba-117">支持</span><span class="sxs-lookup"><span data-stu-id="77bba-117">Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-118">Supported5</span><span class="sxs-lookup"><span data-stu-id="77bba-118">Supported5</span></span></p></td>
<td><p><span data-ttu-id="77bba-119">不支持</span><span class="sxs-lookup"><span data-stu-id="77bba-119">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77bba-120">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="77bba-120">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="77bba-121">支持</span><span class="sxs-lookup"><span data-stu-id="77bba-121">Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-122">支持</span><span class="sxs-lookup"><span data-stu-id="77bba-122">Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-123">不支持</span><span class="sxs-lookup"><span data-stu-id="77bba-123">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77bba-124">Lync Web App 2013</span><span class="sxs-lookup"><span data-stu-id="77bba-124">Lync Web App 2013</span></span></p></td>
<td><p><span data-ttu-id="77bba-125">支持</span><span class="sxs-lookup"><span data-stu-id="77bba-125">Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-126">不支持</span><span class="sxs-lookup"><span data-stu-id="77bba-126">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-127">不支持</span><span class="sxs-lookup"><span data-stu-id="77bba-127">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77bba-128">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="77bba-128">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="77bba-129">支持</span><span class="sxs-lookup"><span data-stu-id="77bba-129">Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-130">支持</span><span class="sxs-lookup"><span data-stu-id="77bba-130">Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-131">不支持</span><span class="sxs-lookup"><span data-stu-id="77bba-131">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77bba-132">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="77bba-132">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="77bba-133">支持</span><span class="sxs-lookup"><span data-stu-id="77bba-133">Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-134">支持</span><span class="sxs-lookup"><span data-stu-id="77bba-134">Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-135">不支持</span><span class="sxs-lookup"><span data-stu-id="77bba-135">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77bba-136">Lync 2010 组聊天</span><span class="sxs-lookup"><span data-stu-id="77bba-136">Lync 2010 Group Chat</span></span></p></td>
<td><p><span data-ttu-id="77bba-137">Supported1</span><span class="sxs-lookup"><span data-stu-id="77bba-137">Supported1</span></span></p></td>
<td><p><span data-ttu-id="77bba-138">Supported2</span><span class="sxs-lookup"><span data-stu-id="77bba-138">Supported2</span></span></p></td>
<td><p><span data-ttu-id="77bba-139">不适用</span><span class="sxs-lookup"><span data-stu-id="77bba-139">Not Applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77bba-140">Lync Web App 2010</span><span class="sxs-lookup"><span data-stu-id="77bba-140">Lync Web App 2010</span></span></p></td>
<td><p><span data-ttu-id="77bba-141">不支持</span><span class="sxs-lookup"><span data-stu-id="77bba-141">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-142">支持</span><span class="sxs-lookup"><span data-stu-id="77bba-142">Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-143">不支持</span><span class="sxs-lookup"><span data-stu-id="77bba-143">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77bba-144">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="77bba-144">Lync 2010 Attendee</span></span></p></td>
<td><p><span data-ttu-id="77bba-145">不 Supported3</span><span class="sxs-lookup"><span data-stu-id="77bba-145">Not Supported3</span></span></p></td>
<td><p><span data-ttu-id="77bba-146">支持</span><span class="sxs-lookup"><span data-stu-id="77bba-146">Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-147">不支持</span><span class="sxs-lookup"><span data-stu-id="77bba-147">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77bba-148">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="77bba-148">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="77bba-149">Interoperable4</span><span class="sxs-lookup"><span data-stu-id="77bba-149">Interoperable4</span></span></p></td>
<td><p><span data-ttu-id="77bba-150">支持</span><span class="sxs-lookup"><span data-stu-id="77bba-150">Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-151">支持</span><span class="sxs-lookup"><span data-stu-id="77bba-151">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77bba-152">Microsoft Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="77bba-152">Microsoft Office Communications Server 2007 R2 Attendant</span></span></p></td>
<td><p><span data-ttu-id="77bba-153">不支持</span><span class="sxs-lookup"><span data-stu-id="77bba-153">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-154">支持</span><span class="sxs-lookup"><span data-stu-id="77bba-154">Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-155">支持</span><span class="sxs-lookup"><span data-stu-id="77bba-155">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77bba-156">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="77bba-156">Office Communicator 2007</span></span></p></td>
<td><p><span data-ttu-id="77bba-157">不支持</span><span class="sxs-lookup"><span data-stu-id="77bba-157">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-158">支持</span><span class="sxs-lookup"><span data-stu-id="77bba-158">Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-159">支持</span><span class="sxs-lookup"><span data-stu-id="77bba-159">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77bba-160">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="77bba-160">Office Live Meeting 2007</span></span></p></td>
<td><p><span data-ttu-id="77bba-161">不支持</span><span class="sxs-lookup"><span data-stu-id="77bba-161">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-162">支持</span><span class="sxs-lookup"><span data-stu-id="77bba-162">Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-163">支持</span><span class="sxs-lookup"><span data-stu-id="77bba-163">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77bba-164">Lync Windows 应用商店应用</span><span class="sxs-lookup"><span data-stu-id="77bba-164">Lync Windows Store app</span></span></p></td>
<td><p><span data-ttu-id="77bba-165">支持</span><span class="sxs-lookup"><span data-stu-id="77bba-165">Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-166">支持</span><span class="sxs-lookup"><span data-stu-id="77bba-166">Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-167">不支持</span><span class="sxs-lookup"><span data-stu-id="77bba-167">Not Supported</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="77bba-168">1For 详细信息，请参阅 [从 Lync server 2010、组聊天或 Office 通信服务器 2007 R2 组聊天迁移到 Lync server 2013、持久聊天服务器](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="77bba-168">1For details, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="77bba-169">2In Microsoft Lync Server 2010，组聊天功能可用于 Lync Server 2010 的第三方受信任应用程序的组聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="77bba-169">2In Microsoft Lync Server 2010, group chat functionality was available with Group Chat Server, a third-party trusted application for Lync Server 2010.</span></span> <span data-ttu-id="77bba-170">Lync 2013 客户端与 Lync Server 2010、组聊天不兼容。</span><span class="sxs-lookup"><span data-stu-id="77bba-170">Lync 2013 clients are not compatible with Lync Server 2010, Group Chat.</span></span>

<span data-ttu-id="77bba-171">3Lync Web App 2013 现在提供了完整的会议体验，包括计算机音频和视频，并被视为 Lync 2010 与会者的替代项。</span><span class="sxs-lookup"><span data-stu-id="77bba-171">3Lync Web App 2013 now provides a full in-meeting experience, including computer audio and video, and is considered the replacement for Lync 2010 Attendee.</span></span> <span data-ttu-id="77bba-172">仅当您使用不受支持的浏览器 (Internet Explorer 6 或 Internet Explorer 7) 和 Windows XP 时，lync 2010 与会者才会连接到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="77bba-172">Lync 2010 Attendee will connect to Lync Server 2013 only when you are using an unsupported browser (Internet Explorer 6 or Internet Explorer 7) and Windows XP.</span></span>

<span data-ttu-id="77bba-173">Office Communicator 2007 R2 中的4The 状态和 IM 功能与 Lync Server 2013 兼容，但会议功能不兼容。</span><span class="sxs-lookup"><span data-stu-id="77bba-173">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="77bba-174">从 Office 通信服务器 2007 R2 迁移过程中，Office Communicator 2007 R2 适用于状态和 IM 互操作性，但用户应使用 Lync Web App 2013 加入 Lync Server 2013 会议。</span><span class="sxs-lookup"><span data-stu-id="77bba-174">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

<span data-ttu-id="77bba-175">5有关限制，请参阅本主题后面的 "在 Lync Server 2010 会议中为 Lync 2013 客户端提供会议功能支持"。</span><span class="sxs-lookup"><span data-stu-id="77bba-175">5 For limitations, see "Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings" later in this topic.</span></span>

</div>

<div>

## <a name="interoperability-among-clients"></a><span data-ttu-id="77bba-176">客户端之间的互操作性</span><span class="sxs-lookup"><span data-stu-id="77bba-176">Interoperability among Clients</span></span>

<span data-ttu-id="77bba-177">在 Lync Server 2013 版本中，各种客户端版本可以在对等和会议方案中无缝交互。</span><span class="sxs-lookup"><span data-stu-id="77bba-177">With the Lync Server 2013 release, various client versions can interact seamlessly in both peer-to-peer and conferencing scenarios.</span></span> <span data-ttu-id="77bba-178">本部分讨论当用户与使用不同版本的客户端和服务器的其他用户进行交互时的功能可用性。</span><span class="sxs-lookup"><span data-stu-id="77bba-178">This section discusses feature availability when users interact with other users who are using different versions of clients and servers.</span></span>

<div>

## <a name="peer-to-peer-feature-support"></a><span data-ttu-id="77bba-179">对等功能支持</span><span class="sxs-lookup"><span data-stu-id="77bba-179">Peer-to-Peer Feature Support</span></span>

<span data-ttu-id="77bba-180">对于驻留在不同版本的服务器上的用户以及使用不同客户端版本的用户，支持对等功能。</span><span class="sxs-lookup"><span data-stu-id="77bba-180">Peer-to-peer features are supported for users who are homed on different versions of the server and who are using different client versions.</span></span> <span data-ttu-id="77bba-181">最终用户体验和可用功能与用户客户端的功能和用户登录到的服务器版本一致。</span><span class="sxs-lookup"><span data-stu-id="77bba-181">The end-user experience and available features are consistent with the capabilities of the user’s client and the version of the server the user is signed in to.</span></span> <span data-ttu-id="77bba-182">换言之：</span><span class="sxs-lookup"><span data-stu-id="77bba-182">In other words:</span></span>

  - <span data-ttu-id="77bba-183">如果用户使用旧版客户端登录到 Lync Server 2013，则用户将拥有自己使用的相同体验。</span><span class="sxs-lookup"><span data-stu-id="77bba-183">If a user is signed in to Lync Server 2013 with an older client, the user will have the same experience he or she is used to.</span></span> <span data-ttu-id="77bba-184">在升级用户的客户端之前，Lync Server 2013 中引入的所有新功能均不可用。</span><span class="sxs-lookup"><span data-stu-id="77bba-184">None of the new features introduced in Lync Server 2013 will be available until the user’s client is upgraded.</span></span> <span data-ttu-id="77bba-185">示例包括视频库视图、HD 视频、更新的 PowerPoint 共享以及在会议进入时将所有与会者音频和视频设为静音的选项。</span><span class="sxs-lookup"><span data-stu-id="77bba-185">Examples include video gallery view, HD video, updated PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="77bba-186">[Lync server 2013 的新会议功能](lync-server-2013-new-conferencing-features.md)中概述了新功能，以及[lync server 2013 中客户端的新增](lync-server-2013-what-s-new-for-clients.md)功能。</span><span class="sxs-lookup"><span data-stu-id="77bba-186">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

  - <span data-ttu-id="77bba-187">如果用户使用 Lync 2013 客户端登录到 Lync Server 2010，则在用户移动到 Lync Server 2013 之前，Lync Server 2010 不支持的任何新功能将不可用。</span><span class="sxs-lookup"><span data-stu-id="77bba-187">If a user is signed in to Lync Server 2010 with a Lync 2013 client, any new features not supported by Lync Server 2010 will be unavailable until the user is moved to Lync Server 2013.</span></span>

<span data-ttu-id="77bba-188">下表比较了客户端登录到 Lync Server 2013 或 Lync Server 2010 的对等会话中的功能可用性。</span><span class="sxs-lookup"><span data-stu-id="77bba-188">The following table compares feature availability in peer-to-peer sessions where the client is signed in to either Lync Server 2013 or Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77bba-189">Lync Web App 和 Lync 2010 与会者是仅会议客户端，不包括在此表中。</span><span class="sxs-lookup"><span data-stu-id="77bba-189">Lync Web App and Lync 2010 Attendee are meeting-only clients and aren’t included in this table.</span></span>



</div>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="77bba-190">客户端</span><span class="sxs-lookup"><span data-stu-id="77bba-190">Client</span></span></th>
<th><span data-ttu-id="77bba-191">即时消息</span><span class="sxs-lookup"><span data-stu-id="77bba-191">Instant Messaging</span></span></th>
<th><span data-ttu-id="77bba-192">状态</span><span class="sxs-lookup"><span data-stu-id="77bba-192">Presence</span></span></th>
<th><span data-ttu-id="77bba-193">语音</span><span class="sxs-lookup"><span data-stu-id="77bba-193">Voice</span></span></th>
<th><span data-ttu-id="77bba-194">视频</span><span class="sxs-lookup"><span data-stu-id="77bba-194">Video</span></span></th>
<th><span data-ttu-id="77bba-195">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="77bba-195">Application Sharing</span></span></th>
<th><span data-ttu-id="77bba-196">文件传输</span><span class="sxs-lookup"><span data-stu-id="77bba-196">File Transfer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77bba-197">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="77bba-197">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="77bba-198">是</span><span class="sxs-lookup"><span data-stu-id="77bba-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-199">是</span><span class="sxs-lookup"><span data-stu-id="77bba-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-200">是</span><span class="sxs-lookup"><span data-stu-id="77bba-200">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-201">是</span><span class="sxs-lookup"><span data-stu-id="77bba-201">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-202">是</span><span class="sxs-lookup"><span data-stu-id="77bba-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-203">是</span><span class="sxs-lookup"><span data-stu-id="77bba-203">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77bba-204">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="77bba-204">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="77bba-205">是</span><span class="sxs-lookup"><span data-stu-id="77bba-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-206">是</span><span class="sxs-lookup"><span data-stu-id="77bba-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-207">是</span><span class="sxs-lookup"><span data-stu-id="77bba-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-208">是</span><span class="sxs-lookup"><span data-stu-id="77bba-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-209">是</span><span class="sxs-lookup"><span data-stu-id="77bba-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-210">是</span><span class="sxs-lookup"><span data-stu-id="77bba-210">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77bba-211">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="77bba-211">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="77bba-212">是</span><span class="sxs-lookup"><span data-stu-id="77bba-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-213">是</span><span class="sxs-lookup"><span data-stu-id="77bba-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-214">是</span><span class="sxs-lookup"><span data-stu-id="77bba-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-215">是</span><span class="sxs-lookup"><span data-stu-id="77bba-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-216">是</span><span class="sxs-lookup"><span data-stu-id="77bba-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-217">是</span><span class="sxs-lookup"><span data-stu-id="77bba-217">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77bba-218">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="77bba-218">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="77bba-219">是</span><span class="sxs-lookup"><span data-stu-id="77bba-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-220">是</span><span class="sxs-lookup"><span data-stu-id="77bba-220">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-221">是</span><span class="sxs-lookup"><span data-stu-id="77bba-221">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77bba-222">Lync 2010 Mobile</span><span class="sxs-lookup"><span data-stu-id="77bba-222">Lync 2010 Mobile</span></span></p></td>
<td><p><span data-ttu-id="77bba-223">是</span><span class="sxs-lookup"><span data-stu-id="77bba-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-224">是</span><span class="sxs-lookup"><span data-stu-id="77bba-224">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77bba-225">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="77bba-225">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="77bba-226">是</span><span class="sxs-lookup"><span data-stu-id="77bba-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-227">是</span><span class="sxs-lookup"><span data-stu-id="77bba-227">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-228">是</span><span class="sxs-lookup"><span data-stu-id="77bba-228">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77bba-229">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="77bba-229">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="77bba-230">是</span><span class="sxs-lookup"><span data-stu-id="77bba-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-231">是</span><span class="sxs-lookup"><span data-stu-id="77bba-231">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-232">是</span><span class="sxs-lookup"><span data-stu-id="77bba-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-233">是</span><span class="sxs-lookup"><span data-stu-id="77bba-233">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-234">是1</span><span class="sxs-lookup"><span data-stu-id="77bba-234">Yes1</span></span></p></td>
<td><p><span data-ttu-id="77bba-235">是</span><span class="sxs-lookup"><span data-stu-id="77bba-235">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77bba-236">公共 IM (AOL、Yahoo！ ) </span><span class="sxs-lookup"><span data-stu-id="77bba-236">Public IM (AOL, Yahoo!)</span></span></p></td>
<td><p><span data-ttu-id="77bba-237">是</span><span class="sxs-lookup"><span data-stu-id="77bba-237">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-238">是</span><span class="sxs-lookup"><span data-stu-id="77bba-238">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77bba-239">公共 IM (MSN、Windows Live Messenger) </span><span class="sxs-lookup"><span data-stu-id="77bba-239">Public IM (MSN, Windows Live Messenger)</span></span></p></td>
<td><p><span data-ttu-id="77bba-240">是</span><span class="sxs-lookup"><span data-stu-id="77bba-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-241">是</span><span class="sxs-lookup"><span data-stu-id="77bba-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-242">是</span><span class="sxs-lookup"><span data-stu-id="77bba-242">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-243">是</span><span class="sxs-lookup"><span data-stu-id="77bba-243">Yes</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="77bba-244">从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证 (PIC USL) 不再可用于购买新的或更新的协议。</span><span class="sxs-lookup"><span data-stu-id="77bba-244">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="77bba-245">拥有主动许可证的客户将能够继续与 Yahoo！联合联合</span><span class="sxs-lookup"><span data-stu-id="77bba-245">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="77bba-246">信使，直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="77bba-246">Messenger until the service shutdown date.</span></span> <span data-ttu-id="77bba-247">AOL 和 Yahoo！的生命周期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="77bba-247">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="77bba-248">已宣布。</span><span class="sxs-lookup"><span data-stu-id="77bba-248">has been announced.</span></span> <span data-ttu-id="77bba-249">有关详细信息，请参阅 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时消息连接</A>。。</span><span class="sxs-lookup"><span data-stu-id="77bba-249">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>..</span></span></P>
> <LI>
> <P><span data-ttu-id="77bba-250">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每用户、每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="77bba-250">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="77bba-251">Messenger.</span><span class="sxs-lookup"><span data-stu-id="77bba-251">Messenger.</span></span> <span data-ttu-id="77bba-252">Microsoft 提供此服务的能力因 Yahoo！中的支持而异，将不会续订的底层协议。</span><span class="sxs-lookup"><span data-stu-id="77bba-252">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="77bba-253">Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。</span><span class="sxs-lookup"><span data-stu-id="77bba-253">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="77bba-254">与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="77bba-254">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="77bba-255">Skype 联盟将添加到此列表中，使 Lync 用户能够通过即时消息和语音访问数百个人。</span><span class="sxs-lookup"><span data-stu-id="77bba-255">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="77bba-256">1在 Office Communicator 2007 R2 中，仅有桌面共享 (，不能使用程序共享) 。</span><span class="sxs-lookup"><span data-stu-id="77bba-256">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77bba-257">如果强制实施 Skype for Business 2015 客户端用户界面，则无法从较新的客户端启动 Office Communicator 2007 R2 和 Skype for Business 2015 之间的桌面共享。</span><span class="sxs-lookup"><span data-stu-id="77bba-257">Desktop sharing between Office Communicator 2007 R2 and Skype for Business 2015 cannot be initiated from the newer client when the Skype for Business 2015 client user interface is enforced.</span></span>



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a><span data-ttu-id="77bba-258">Lync Server 2010 会议中 Lync 2013 客户端的会议功能支持</span><span class="sxs-lookup"><span data-stu-id="77bba-258">Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings</span></span>

<span data-ttu-id="77bba-259">当用户使用 Lync 2013 客户端加入 Lync Server 2010 会议时，他们可以访问 Lync 2013 客户端功能，但有以下例外：</span><span class="sxs-lookup"><span data-stu-id="77bba-259">When users join Lync Server 2010 meetings with a Lync 2013 client, they have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="77bba-260">在 **参与者** 管理选项（可通过指向会议窗口中的 "人员" 图标访问）中，" **无会议即时消息** " 选项不起作用。</span><span class="sxs-lookup"><span data-stu-id="77bba-260">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="77bba-261">库视图在视频会议中不起作用。</span><span class="sxs-lookup"><span data-stu-id="77bba-261">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="77bba-262">用户仅看到活动的扬声器，而不是所有扬声器。</span><span class="sxs-lookup"><span data-stu-id="77bba-262">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="77bba-263">在 " **选取布局** " 选项列表中，" **库视图** " 不可用</span><span class="sxs-lookup"><span data-stu-id="77bba-263">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="77bba-264">默认情况下，参与者列表在视频会议中显示。</span><span class="sxs-lookup"><span data-stu-id="77bba-264">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="77bba-265">右键单击 "参与者" 列表中的用户时，" **锁定视频焦点** 并 **固定到库** 参与者管理" 选项不可用。</span><span class="sxs-lookup"><span data-stu-id="77bba-265">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a><span data-ttu-id="77bba-266">Lync Server 2013 会议中的会议功能支持</span><span class="sxs-lookup"><span data-stu-id="77bba-266">Conferencing Feature Support in Lync Server 2013 Meetings</span></span>

<span data-ttu-id="77bba-267">Lync Server 2013 提供新的会议功能，这些功能在其帐户移动到 Lync Server 2013 并使用 Lync 2013 客户端登录后可供用户使用。</span><span class="sxs-lookup"><span data-stu-id="77bba-267">Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="77bba-268">示例包括视频库视图、HD 视频、PowerPoint 共享，以及在会议进入时将所有与会者音频和视频设为静音的选项。</span><span class="sxs-lookup"><span data-stu-id="77bba-268">Examples include video gallery view, HD video, PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="77bba-269">[Lync server 2013 的新会议功能](lync-server-2013-new-conferencing-features.md)中概述了新功能，以及[lync server 2013 中客户端的新增](lync-server-2013-what-s-new-for-clients.md)功能。</span><span class="sxs-lookup"><span data-stu-id="77bba-269">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="77bba-270">在 Lync Server 2013 会议中，某些会议功能对于驻留在不同版本的服务器上的用户以及使用不同客户端和客户端版本的用户都受支持。</span><span class="sxs-lookup"><span data-stu-id="77bba-270">In Lync Server 2013 meetings, certain conferencing features are supported for users who are homed on different versions of the server and who are using different clients and client versions.</span></span> <span data-ttu-id="77bba-271">当客户端加入 Lync Server 2013 会议时，用户可以访问此表中所示的特性和功能。</span><span class="sxs-lookup"><span data-stu-id="77bba-271">When clients join a Lync Server 2013 meeting, users have access to the features and capabilities shown in this table.</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="77bba-272">客户端</span><span class="sxs-lookup"><span data-stu-id="77bba-272">Client</span></span></th>
<th><span data-ttu-id="77bba-273">对等 IM</span><span class="sxs-lookup"><span data-stu-id="77bba-273">Peer-to-peer IM</span></span></th>
<th><span data-ttu-id="77bba-274">语音</span><span class="sxs-lookup"><span data-stu-id="77bba-274">Voice</span></span></th>
<th><span data-ttu-id="77bba-275">视频</span><span class="sxs-lookup"><span data-stu-id="77bba-275">Video</span></span></th>
<th><span data-ttu-id="77bba-276">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="77bba-276">Application Sharing</span></span></th>
<th><span data-ttu-id="77bba-277">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="77bba-277">PowerPoint</span></span></th>
<th><span data-ttu-id="77bba-278">文件传输</span><span class="sxs-lookup"><span data-stu-id="77bba-278">File Transfer</span></span></th>
<th><span data-ttu-id="77bba-279">Whiteboard</span><span class="sxs-lookup"><span data-stu-id="77bba-279">Whiteboard</span></span></th>
<th><span data-ttu-id="77bba-280">轮询</span><span class="sxs-lookup"><span data-stu-id="77bba-280">Polling</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77bba-281">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="77bba-281">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="77bba-282">是</span><span class="sxs-lookup"><span data-stu-id="77bba-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-283">是</span><span class="sxs-lookup"><span data-stu-id="77bba-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-284">是</span><span class="sxs-lookup"><span data-stu-id="77bba-284">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-285">是</span><span class="sxs-lookup"><span data-stu-id="77bba-285">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-286">是</span><span class="sxs-lookup"><span data-stu-id="77bba-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-287">是</span><span class="sxs-lookup"><span data-stu-id="77bba-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-288">是</span><span class="sxs-lookup"><span data-stu-id="77bba-288">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-289">是</span><span class="sxs-lookup"><span data-stu-id="77bba-289">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77bba-290">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="77bba-290">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="77bba-291">是</span><span class="sxs-lookup"><span data-stu-id="77bba-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-292">是</span><span class="sxs-lookup"><span data-stu-id="77bba-292">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-293">是</span><span class="sxs-lookup"><span data-stu-id="77bba-293">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-294">是</span><span class="sxs-lookup"><span data-stu-id="77bba-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-295">是</span><span class="sxs-lookup"><span data-stu-id="77bba-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-296">是</span><span class="sxs-lookup"><span data-stu-id="77bba-296">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-297">是</span><span class="sxs-lookup"><span data-stu-id="77bba-297">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-298">是</span><span class="sxs-lookup"><span data-stu-id="77bba-298">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77bba-299">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="77bba-299">Lync Web App</span></span></p></td>
<td><p><span data-ttu-id="77bba-300">是</span><span class="sxs-lookup"><span data-stu-id="77bba-300">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-301">是</span><span class="sxs-lookup"><span data-stu-id="77bba-301">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-302">是</span><span class="sxs-lookup"><span data-stu-id="77bba-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-303">是</span><span class="sxs-lookup"><span data-stu-id="77bba-303">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-304">是2</span><span class="sxs-lookup"><span data-stu-id="77bba-304">Yes2</span></span></p></td>
<td><p><span data-ttu-id="77bba-305">是</span><span class="sxs-lookup"><span data-stu-id="77bba-305">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-306">是</span><span class="sxs-lookup"><span data-stu-id="77bba-306">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-307">是</span><span class="sxs-lookup"><span data-stu-id="77bba-307">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77bba-308">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="77bba-308">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="77bba-309">是</span><span class="sxs-lookup"><span data-stu-id="77bba-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-310">是</span><span class="sxs-lookup"><span data-stu-id="77bba-310">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-311">是</span><span class="sxs-lookup"><span data-stu-id="77bba-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-312">是</span><span class="sxs-lookup"><span data-stu-id="77bba-312">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-313">是3</span><span class="sxs-lookup"><span data-stu-id="77bba-313">Yes3</span></span></p></td>
<td><p><span data-ttu-id="77bba-314">是</span><span class="sxs-lookup"><span data-stu-id="77bba-314">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-315">是</span><span class="sxs-lookup"><span data-stu-id="77bba-315">Yes</span></span></p></td>
<td><p><span data-ttu-id="77bba-316">是</span><span class="sxs-lookup"><span data-stu-id="77bba-316">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77bba-317">Office Communicator 2007 R2 4</span><span class="sxs-lookup"><span data-stu-id="77bba-317">Office Communicator 2007 R2 4</span></span></p></td>
<td><p><span data-ttu-id="77bba-318">是</span><span class="sxs-lookup"><span data-stu-id="77bba-318">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="77bba-319">1在 Office Communicator 2007 R2 中，仅有桌面共享 (，不能使用程序共享) 。</span><span class="sxs-lookup"><span data-stu-id="77bba-319">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<span data-ttu-id="77bba-320">2 Lync Server 2013 使用更新的机制来上载 PowerPoint 文件。</span><span class="sxs-lookup"><span data-stu-id="77bba-320">2 Lync Server 2013 uses an updated mechanism for uploading PowerPoint files.</span></span> <span data-ttu-id="77bba-321">加入最初在 Lync Server 2010 上安排的会议的 Lync Web App 用户可以查看和导航 PowerPoint 演示文稿，但不能上载 PowerPoint 文件。</span><span class="sxs-lookup"><span data-stu-id="77bba-321">Lync Web App users who join a meeting that was originally scheduled on Lync Server 2010 can view and navigate PowerPoint presentations, but cannot upload PowerPoint files.</span></span>

<span data-ttu-id="77bba-322">3如果会议是在 Lync Server 2013 上安排的，并且 PowerPoint 幻灯片已由 Lync 2013 客户端上载，Lync 2010 用户可以仅查看对幻灯片的访问权限。</span><span class="sxs-lookup"><span data-stu-id="77bba-322">3 If the meeting was scheduled on Lync Server 2013 and PowerPoint slides were uploaded by a Lync 2013 client, Lync 2010 users have view-only access to the slides.</span></span> <span data-ttu-id="77bba-323">相反，如果由 Lync 2010 用户上载 PowerPoint 幻灯片，Lync Server 2013 用户将能够查看和幻灯片，如果配置了 Office Web Apps Server，则可以访问新的功能，例如更高分辨率的显示、动画、幻灯片切换和嵌入的视频。</span><span class="sxs-lookup"><span data-stu-id="77bba-323">Conversely, if the PowerPoint slides were uploaded by a Lync 2010 user, Lync Server 2013 users will be able to view and slides and, if Office Web Apps Server is configured, access new capabilities such as higher resolution display, animations, slide transitions, and embedded video.</span></span> <span data-ttu-id="77bba-324">有关详细信息，请参阅 [配置与 Office Web Apps Server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="77bba-324">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="77bba-325">Office Communicator 2007 R2 中的4The 状态和 IM 功能与 Lync Server 2013 兼容，但会议功能不兼容。</span><span class="sxs-lookup"><span data-stu-id="77bba-325">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="77bba-326">从 Office 通信服务器 2007 R2 迁移过程中，Office Communicator 2007 R2 适用于状态和 IM 互操作性，但用户应使用 Lync Web App 2013 加入 Lync Server 2013 会议。</span><span class="sxs-lookup"><span data-stu-id="77bba-326">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a><span data-ttu-id="77bba-327">计划加载项支持</span><span class="sxs-lookup"><span data-stu-id="77bba-327">Scheduling Add-in Support</span></span>

<span data-ttu-id="77bba-328">对各种计划外接程序的服务器支持与服务器和客户端版本的兼容性一致。</span><span class="sxs-lookup"><span data-stu-id="77bba-328">Server support for the various scheduling add-ins is consistent with server and client version compatibility.</span></span> <span data-ttu-id="77bba-329">通常情况下，以下计划外接程序在 Lync Server 2013 上受支持。</span><span class="sxs-lookup"><span data-stu-id="77bba-329">In general, the following scheduling add-ins are supported on Lync Server 2013.</span></span> <span data-ttu-id="77bba-330">但是，早期版本的外接程序不提供新的 Lync 2013 外接程序功能，例如，在会议进入时将所有与会者音频和视频设为静音的选项。</span><span class="sxs-lookup"><span data-stu-id="77bba-330">However, previous versions of add-ins do not provide new Lync 2013 add-in features, such as the option to mute all attendee audio and video upon meeting entry.</span></span>

  - <span data-ttu-id="77bba-331">**Lync 2013**     的联机会议外接程序提供与 Lync 2010 的联机会议外接程序相同的功能，并添加了与会者静音控件，使会议组织者可以计划默认情况下为与会者音频和视频静音的会议。</span><span class="sxs-lookup"><span data-stu-id="77bba-331">**Online Meeting Add-in for Lync 2013**   Provides the same features as the Online Meeting Add-in for Lync 2010, with the addition of attendee mute controls, which allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span> <span data-ttu-id="77bba-332">管理员还可以通过添加自定义徽标、支持 URL、合法免责声明 URL 或自定义页脚文本来自定义组织的会议邀请。</span><span class="sxs-lookup"><span data-stu-id="77bba-332">Administrators can also customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span>

  - <span data-ttu-id="77bba-333">**Lync 2010**     的联机会议外接程序为 Lync 会议提供计划，并删除安排 Office Live 会议会议的功能。</span><span class="sxs-lookup"><span data-stu-id="77bba-333">**Online Meeting Add-in for Lync 2010**   Provides scheduling for Lync meetings and removes the capability to schedule Office Live Meeting conferences.</span></span>

  - <span data-ttu-id="77bba-334">**Office Communicator 2007 R2 会议加载项**    提供 Office Live Meeting 会议和 Office Communicator 2007 R2 会议的日程安排。</span><span class="sxs-lookup"><span data-stu-id="77bba-334">**Office Communicator 2007 R2 Conferencing Add-in**   Provides scheduling for both Office Live Meeting conferences and Office Communicator 2007 R2 conferences.</span></span> 

<div>


> [!NOTE]  
> <span data-ttu-id="77bba-335">无法在 Lync Server 2013 上计划 Live Meeting 会议。</span><span class="sxs-lookup"><span data-stu-id="77bba-335">Live Meeting conferences cannot be scheduled on Lync Server 2013.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="77bba-336">计划客户端</span><span class="sxs-lookup"><span data-stu-id="77bba-336">Scheduling Client</span></span></th>
<th><span data-ttu-id="77bba-337">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77bba-337">Lync Server 2013</span></span></th>
<th><span data-ttu-id="77bba-338">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="77bba-338">Lync Server 2010</span></span></th>
<th><span data-ttu-id="77bba-339">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="77bba-339">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77bba-340">适用于 Lync 2013 的联机会议外接程序 (可用于 Office 2013、Outlook 2010 和 Outlook 2007) </span><span class="sxs-lookup"><span data-stu-id="77bba-340">Online Meeting Add-in for Lync 2013 (can be used with Office 2013, Outlook 2010, and Outlook 2007)</span></span></p></td>
<td><p><span data-ttu-id="77bba-341">支持</span><span class="sxs-lookup"><span data-stu-id="77bba-341">Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-342">支持的 (新加载项功能不可用) </span><span class="sxs-lookup"><span data-stu-id="77bba-342">Supported (new add-in features not available)</span></span></p></td>
<td><p><span data-ttu-id="77bba-343">不支持</span><span class="sxs-lookup"><span data-stu-id="77bba-343">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77bba-344">Lync 2013 Web 计划程序</span><span class="sxs-lookup"><span data-stu-id="77bba-344">Lync 2013 Web Scheduler</span></span></p></td>
<td><p><span data-ttu-id="77bba-345">支持</span><span class="sxs-lookup"><span data-stu-id="77bba-345">Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-346">不支持</span><span class="sxs-lookup"><span data-stu-id="77bba-346">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-347">不支持</span><span class="sxs-lookup"><span data-stu-id="77bba-347">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77bba-348">Online Meeting Add-in for Lync 2010 － Lync 2010 联机会议外接程序</span><span class="sxs-lookup"><span data-stu-id="77bba-348">Online Meeting Add-in for Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="77bba-349">支持</span><span class="sxs-lookup"><span data-stu-id="77bba-349">Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-350">支持</span><span class="sxs-lookup"><span data-stu-id="77bba-350">Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-351">不支持</span><span class="sxs-lookup"><span data-stu-id="77bba-351">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77bba-352">Office Communicator 2007 R2 会议加载项</span><span class="sxs-lookup"><span data-stu-id="77bba-352">Office Communicator 2007 R2 Conferencing Add-in</span></span></p></td>
<td><p><span data-ttu-id="77bba-353">不支持</span><span class="sxs-lookup"><span data-stu-id="77bba-353">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-354">支持</span><span class="sxs-lookup"><span data-stu-id="77bba-354">Supported</span></span></p></td>
<td><p><span data-ttu-id="77bba-355">支持</span><span class="sxs-lookup"><span data-stu-id="77bba-355">Supported</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a><span data-ttu-id="77bba-356">支持加入会议</span><span class="sxs-lookup"><span data-stu-id="77bba-356">Support for Joining Meetings</span></span>

<span data-ttu-id="77bba-357">允许 Lync Server 2013 支持的所有客户端加入 Lync 2013 会议。</span><span class="sxs-lookup"><span data-stu-id="77bba-357">All of the clients that Lync Server 2013 supports are allowed to join Lync 2013 meetings.</span></span> <span data-ttu-id="77bba-358">由于 Lync web App 是服务器的 Web 组件，因此，如果使用 Lync Web App 加入 Lync Server 2013 会议，则始终使用最新版本的 Lync Web App。</span><span class="sxs-lookup"><span data-stu-id="77bba-358">Because Lync Web App is a web component of the server, in cases where Lync Web App is used to join a Lync Server 2013 meeting, the newer version of Lync Web App is always used.</span></span>

<span data-ttu-id="77bba-359">Lync 2013 客户端可以加入在 Lync 2010 上托管的会议和 Office 通信服务器 2007 R2 （向下扩展功能）。</span><span class="sxs-lookup"><span data-stu-id="77bba-359">Lync 2013 clients can join meetings hosted on Lync 2010 and Office Communications Server 2007 R2 with scaled-down functionality.</span></span> <span data-ttu-id="77bba-360">会议中的功能受托管会议的服务器版本的限制。</span><span class="sxs-lookup"><span data-stu-id="77bba-360">In-meeting features are limited by the version of the server on which the meeting is hosted.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="77bba-361">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77bba-361">See Also</span></span>


[<span data-ttu-id="77bba-362">Lync Server 2013 的 lync Windows 应用商店应用程序要求</span><span class="sxs-lookup"><span data-stu-id="77bba-362">Lync Windows Store app requirements for Lync Server 2013</span></span>](lync-server-2013-lync-windows-store-app-requirements.md)  
[<span data-ttu-id="77bba-363">Lync Server 2013 中的新会议功能</span><span class="sxs-lookup"><span data-stu-id="77bba-363">New conferencing features in Lync Server 2013</span></span>](lync-server-2013-new-conferencing-features.md)  
[<span data-ttu-id="77bba-364">Lync Server 2013 中客户端的新增功能</span><span class="sxs-lookup"><span data-stu-id="77bba-364">What's new for clients in Lync Server 2013</span></span>](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

