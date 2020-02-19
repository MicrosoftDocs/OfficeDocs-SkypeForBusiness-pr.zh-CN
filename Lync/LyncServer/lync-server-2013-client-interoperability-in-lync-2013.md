---
title: Lync Server 2013： Lync 2013 中的客户端互操作性
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
ms.openlocfilehash: 69a4616cbe9519a8196ce78e35f21c673a0d2c95
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134068"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a><span data-ttu-id="27780-102">Lync 2013 中的客户端互操作性</span><span class="sxs-lookup"><span data-stu-id="27780-102">Client interoperability in Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27780-103">_**上次修改的主题：** 2016-03-04_</span><span class="sxs-lookup"><span data-stu-id="27780-103">_**Topic Last Modified:** 2016-03-04_</span></span>

<span data-ttu-id="27780-104">本主题讨论 Microsoft Lync Server 2013 客户端与早期版本的 Lync Server 和 Office 通信服务器之间共存并与客户端进行交互的能力。</span><span class="sxs-lookup"><span data-stu-id="27780-104">This topic discusses the ability of Microsoft Lync Server 2013 clients to coexist and interact with clients from earlier versions of Lync Server and Office Communications Server.</span></span>

<div>

## <a name="server-and-client-compatibility"></a><span data-ttu-id="27780-105">服务器和客户端兼容性</span><span class="sxs-lookup"><span data-stu-id="27780-105">Server and Client Compatibility</span></span>

<span data-ttu-id="27780-106">下表显示受支持的客户端版本和服务器版本的组合。</span><span class="sxs-lookup"><span data-stu-id="27780-106">The following table shows the supported combinations of client versions and server versions.</span></span> <span data-ttu-id="27780-107">此表指示客户端尝试连接到指示的服务器时是否支持登录。</span><span class="sxs-lookup"><span data-stu-id="27780-107">This table indicates whether sign-in is supported when the client attempts to connect to the server indicated.</span></span> <span data-ttu-id="27780-108">Lync Server 2013 支持以前的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="27780-108">Lync Server 2013 supports the previous client version.</span></span> <span data-ttu-id="27780-109">此外，与以前的版本不同的是，Lync Server 2010 支持新的 Lync 2013 客户端。</span><span class="sxs-lookup"><span data-stu-id="27780-109">Also, unlike previous releases, Lync Server 2010 supports the new Lync 2013 clients.</span></span> <span data-ttu-id="27780-110">这使得从 Lync Server 2010 升级的组织可以独立于 Lync Server 升级来部署新的客户端。</span><span class="sxs-lookup"><span data-stu-id="27780-110">This allows organizations who are upgrading from Lync Server 2010 to roll out new clients independent of Lync Server upgrades.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27780-111">Client</span><span class="sxs-lookup"><span data-stu-id="27780-111">Client</span></span></th>
<th><span data-ttu-id="27780-112">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27780-112">Lync Server 2013</span></span></th>
<th><span data-ttu-id="27780-113">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="27780-113">Lync Server 2010</span></span></th>
<th><span data-ttu-id="27780-114">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="27780-114">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27780-115">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="27780-115">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="27780-116">支持</span><span class="sxs-lookup"><span data-stu-id="27780-116">Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-117">Supported5</span><span class="sxs-lookup"><span data-stu-id="27780-117">Supported5</span></span></p></td>
<td><p><span data-ttu-id="27780-118">不支持</span><span class="sxs-lookup"><span data-stu-id="27780-118">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27780-119">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="27780-119">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="27780-120">支持</span><span class="sxs-lookup"><span data-stu-id="27780-120">Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-121">支持</span><span class="sxs-lookup"><span data-stu-id="27780-121">Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-122">不支持</span><span class="sxs-lookup"><span data-stu-id="27780-122">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27780-123">Lync Web App 2013</span><span class="sxs-lookup"><span data-stu-id="27780-123">Lync Web App 2013</span></span></p></td>
<td><p><span data-ttu-id="27780-124">支持</span><span class="sxs-lookup"><span data-stu-id="27780-124">Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-125">不支持</span><span class="sxs-lookup"><span data-stu-id="27780-125">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-126">不支持</span><span class="sxs-lookup"><span data-stu-id="27780-126">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27780-127">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="27780-127">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="27780-128">支持</span><span class="sxs-lookup"><span data-stu-id="27780-128">Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-129">支持</span><span class="sxs-lookup"><span data-stu-id="27780-129">Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-130">不支持</span><span class="sxs-lookup"><span data-stu-id="27780-130">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27780-131">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="27780-131">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="27780-132">支持</span><span class="sxs-lookup"><span data-stu-id="27780-132">Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-133">支持</span><span class="sxs-lookup"><span data-stu-id="27780-133">Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-134">不支持</span><span class="sxs-lookup"><span data-stu-id="27780-134">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27780-135">Lync 2010 组聊天</span><span class="sxs-lookup"><span data-stu-id="27780-135">Lync 2010 Group Chat</span></span></p></td>
<td><p><span data-ttu-id="27780-136">Supported1</span><span class="sxs-lookup"><span data-stu-id="27780-136">Supported1</span></span></p></td>
<td><p><span data-ttu-id="27780-137">Supported2</span><span class="sxs-lookup"><span data-stu-id="27780-137">Supported2</span></span></p></td>
<td><p><span data-ttu-id="27780-138">不适用</span><span class="sxs-lookup"><span data-stu-id="27780-138">Not Applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27780-139">Lync Web App 2010</span><span class="sxs-lookup"><span data-stu-id="27780-139">Lync Web App 2010</span></span></p></td>
<td><p><span data-ttu-id="27780-140">不支持</span><span class="sxs-lookup"><span data-stu-id="27780-140">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-141">支持</span><span class="sxs-lookup"><span data-stu-id="27780-141">Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-142">不支持</span><span class="sxs-lookup"><span data-stu-id="27780-142">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27780-143">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="27780-143">Lync 2010 Attendee</span></span></p></td>
<td><p><span data-ttu-id="27780-144">不 Supported3</span><span class="sxs-lookup"><span data-stu-id="27780-144">Not Supported3</span></span></p></td>
<td><p><span data-ttu-id="27780-145">支持</span><span class="sxs-lookup"><span data-stu-id="27780-145">Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-146">不支持</span><span class="sxs-lookup"><span data-stu-id="27780-146">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27780-147">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="27780-147">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="27780-148">Interoperable4</span><span class="sxs-lookup"><span data-stu-id="27780-148">Interoperable4</span></span></p></td>
<td><p><span data-ttu-id="27780-149">支持</span><span class="sxs-lookup"><span data-stu-id="27780-149">Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-150">支持</span><span class="sxs-lookup"><span data-stu-id="27780-150">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27780-151">Microsoft Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="27780-151">Microsoft Office Communications Server 2007 R2 Attendant</span></span></p></td>
<td><p><span data-ttu-id="27780-152">不支持</span><span class="sxs-lookup"><span data-stu-id="27780-152">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-153">支持</span><span class="sxs-lookup"><span data-stu-id="27780-153">Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-154">支持</span><span class="sxs-lookup"><span data-stu-id="27780-154">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27780-155">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="27780-155">Office Communicator 2007</span></span></p></td>
<td><p><span data-ttu-id="27780-156">不支持</span><span class="sxs-lookup"><span data-stu-id="27780-156">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-157">支持</span><span class="sxs-lookup"><span data-stu-id="27780-157">Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-158">支持</span><span class="sxs-lookup"><span data-stu-id="27780-158">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27780-159">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="27780-159">Office Live Meeting 2007</span></span></p></td>
<td><p><span data-ttu-id="27780-160">不支持</span><span class="sxs-lookup"><span data-stu-id="27780-160">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-161">支持</span><span class="sxs-lookup"><span data-stu-id="27780-161">Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-162">支持</span><span class="sxs-lookup"><span data-stu-id="27780-162">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27780-163">Lync Windows 应用商店应用</span><span class="sxs-lookup"><span data-stu-id="27780-163">Lync Windows Store app</span></span></p></td>
<td><p><span data-ttu-id="27780-164">支持</span><span class="sxs-lookup"><span data-stu-id="27780-164">Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-165">支持</span><span class="sxs-lookup"><span data-stu-id="27780-165">Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-166">不支持</span><span class="sxs-lookup"><span data-stu-id="27780-166">Not Supported</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="27780-167">1For 详细信息，请参阅[从 Lync server 2010、组聊天或 Office 通信服务器 2007 R2 组聊天迁移到 Lync server 2013、持久聊天服务器](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="27780-167">1For details, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="27780-168">2In Microsoft Lync Server 2010，组聊天功能可用于 Lync Server 2010 的第三方受信任应用程序的组聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="27780-168">2In Microsoft Lync Server 2010, group chat functionality was available with Group Chat Server, a third-party trusted application for Lync Server 2010.</span></span> <span data-ttu-id="27780-169">Lync 2013 客户端与 Lync Server 2010、组聊天不兼容。</span><span class="sxs-lookup"><span data-stu-id="27780-169">Lync 2013 clients are not compatible with Lync Server 2010, Group Chat.</span></span>

<span data-ttu-id="27780-170">3Lync Web App 2013 现在提供了完整的会议体验，包括计算机音频和视频，并被视为 Lync 2010 与会者的替代项。</span><span class="sxs-lookup"><span data-stu-id="27780-170">3Lync Web App 2013 now provides a full in-meeting experience, including computer audio and video, and is considered the replacement for Lync 2010 Attendee.</span></span> <span data-ttu-id="27780-171">仅当您使用不受支持的浏览器（Internet Explorer 6 或 Internet Explorer 7）和 Windows XP 时，lync 2010 与会者才会连接到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="27780-171">Lync 2010 Attendee will connect to Lync Server 2013 only when you are using an unsupported browser (Internet Explorer 6 or Internet Explorer 7) and Windows XP.</span></span>

<span data-ttu-id="27780-172">Office Communicator 2007 R2 中的4The 状态和 IM 功能与 Lync Server 2013 兼容，但会议功能不兼容。</span><span class="sxs-lookup"><span data-stu-id="27780-172">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="27780-173">从 Office 通信服务器 2007 R2 迁移过程中，Office Communicator 2007 R2 适用于状态和 IM 互操作性，但用户应使用 Lync Web App 2013 加入 Lync Server 2013 会议。</span><span class="sxs-lookup"><span data-stu-id="27780-173">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

<span data-ttu-id="27780-174">5有关限制，请参阅本主题后面的 "在 Lync Server 2010 会议中为 Lync 2013 客户端提供会议功能支持"。</span><span class="sxs-lookup"><span data-stu-id="27780-174">5 For limitations, see "Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings" later in this topic.</span></span>

</div>

<div>

## <a name="interoperability-among-clients"></a><span data-ttu-id="27780-175">客户端之间的互操作性</span><span class="sxs-lookup"><span data-stu-id="27780-175">Interoperability among Clients</span></span>

<span data-ttu-id="27780-176">在 Lync Server 2013 版本中，各种客户端版本可以在对等和会议方案中无缝交互。</span><span class="sxs-lookup"><span data-stu-id="27780-176">With the Lync Server 2013 release, various client versions can interact seamlessly in both peer-to-peer and conferencing scenarios.</span></span> <span data-ttu-id="27780-177">本部分讨论当用户与使用不同版本的客户端和服务器的其他用户进行交互时的功能可用性。</span><span class="sxs-lookup"><span data-stu-id="27780-177">This section discusses feature availability when users interact with other users who are using different versions of clients and servers.</span></span>

<div>

## <a name="peer-to-peer-feature-support"></a><span data-ttu-id="27780-178">对等功能支持</span><span class="sxs-lookup"><span data-stu-id="27780-178">Peer-to-Peer Feature Support</span></span>

<span data-ttu-id="27780-179">对于驻留在不同版本的服务器上的用户以及使用不同客户端版本的用户，支持对等功能。</span><span class="sxs-lookup"><span data-stu-id="27780-179">Peer-to-peer features are supported for users who are homed on different versions of the server and who are using different client versions.</span></span> <span data-ttu-id="27780-180">最终用户体验和可用功能与用户客户端的功能和用户登录到的服务器版本一致。</span><span class="sxs-lookup"><span data-stu-id="27780-180">The end-user experience and available features are consistent with the capabilities of the user’s client and the version of the server the user is signed in to.</span></span> <span data-ttu-id="27780-181">换言之：</span><span class="sxs-lookup"><span data-stu-id="27780-181">In other words:</span></span>

  - <span data-ttu-id="27780-182">如果用户使用旧版客户端登录到 Lync Server 2013，则用户将拥有自己使用的相同体验。</span><span class="sxs-lookup"><span data-stu-id="27780-182">If a user is signed in to Lync Server 2013 with an older client, the user will have the same experience he or she is used to.</span></span> <span data-ttu-id="27780-183">在升级用户的客户端之前，Lync Server 2013 中引入的所有新功能均不可用。</span><span class="sxs-lookup"><span data-stu-id="27780-183">None of the new features introduced in Lync Server 2013 will be available until the user’s client is upgraded.</span></span> <span data-ttu-id="27780-184">示例包括视频库视图、HD 视频、更新的 PowerPoint 共享以及在会议进入时将所有与会者音频和视频设为静音的选项。</span><span class="sxs-lookup"><span data-stu-id="27780-184">Examples include video gallery view, HD video, updated PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="27780-185">[Lync server 2013 的新会议功能](lync-server-2013-new-conferencing-features.md)中概述了新功能，以及[lync server 2013 中客户端的新增](lync-server-2013-what-s-new-for-clients.md)功能。</span><span class="sxs-lookup"><span data-stu-id="27780-185">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

  - <span data-ttu-id="27780-186">如果用户使用 Lync 2013 客户端登录到 Lync Server 2010，则在用户移动到 Lync Server 2013 之前，Lync Server 2010 不支持的任何新功能将不可用。</span><span class="sxs-lookup"><span data-stu-id="27780-186">If a user is signed in to Lync Server 2010 with a Lync 2013 client, any new features not supported by Lync Server 2010 will be unavailable until the user is moved to Lync Server 2013.</span></span>

<span data-ttu-id="27780-187">下表比较了客户端登录到 Lync Server 2013 或 Lync Server 2010 的对等会话中的功能可用性。</span><span class="sxs-lookup"><span data-stu-id="27780-187">The following table compares feature availability in peer-to-peer sessions where the client is signed in to either Lync Server 2013 or Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="27780-188">Lync Web App 和 Lync 2010 与会者是仅会议客户端，不包括在此表中。</span><span class="sxs-lookup"><span data-stu-id="27780-188">Lync Web App and Lync 2010 Attendee are meeting-only clients and aren’t included in this table.</span></span>



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
<th><span data-ttu-id="27780-189">Client</span><span class="sxs-lookup"><span data-stu-id="27780-189">Client</span></span></th>
<th><span data-ttu-id="27780-190">即时消息</span><span class="sxs-lookup"><span data-stu-id="27780-190">Instant Messaging</span></span></th>
<th><span data-ttu-id="27780-191">状态</span><span class="sxs-lookup"><span data-stu-id="27780-191">Presence</span></span></th>
<th><span data-ttu-id="27780-192">语音</span><span class="sxs-lookup"><span data-stu-id="27780-192">Voice</span></span></th>
<th><span data-ttu-id="27780-193">视频</span><span class="sxs-lookup"><span data-stu-id="27780-193">Video</span></span></th>
<th><span data-ttu-id="27780-194">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="27780-194">Application Sharing</span></span></th>
<th><span data-ttu-id="27780-195">文件传输</span><span class="sxs-lookup"><span data-stu-id="27780-195">File Transfer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27780-196">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="27780-196">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="27780-197">是</span><span class="sxs-lookup"><span data-stu-id="27780-197">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-198">是</span><span class="sxs-lookup"><span data-stu-id="27780-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-199">是</span><span class="sxs-lookup"><span data-stu-id="27780-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-200">是</span><span class="sxs-lookup"><span data-stu-id="27780-200">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-201">是</span><span class="sxs-lookup"><span data-stu-id="27780-201">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-202">是</span><span class="sxs-lookup"><span data-stu-id="27780-202">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27780-203">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="27780-203">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="27780-204">是</span><span class="sxs-lookup"><span data-stu-id="27780-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-205">是</span><span class="sxs-lookup"><span data-stu-id="27780-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-206">是</span><span class="sxs-lookup"><span data-stu-id="27780-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-207">是</span><span class="sxs-lookup"><span data-stu-id="27780-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-208">是</span><span class="sxs-lookup"><span data-stu-id="27780-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-209">是</span><span class="sxs-lookup"><span data-stu-id="27780-209">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27780-210">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="27780-210">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="27780-211">是</span><span class="sxs-lookup"><span data-stu-id="27780-211">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-212">是</span><span class="sxs-lookup"><span data-stu-id="27780-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-213">是</span><span class="sxs-lookup"><span data-stu-id="27780-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-214">是</span><span class="sxs-lookup"><span data-stu-id="27780-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-215">是</span><span class="sxs-lookup"><span data-stu-id="27780-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-216">是</span><span class="sxs-lookup"><span data-stu-id="27780-216">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27780-217">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="27780-217">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="27780-218">是</span><span class="sxs-lookup"><span data-stu-id="27780-218">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-219">是</span><span class="sxs-lookup"><span data-stu-id="27780-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-220">是</span><span class="sxs-lookup"><span data-stu-id="27780-220">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27780-221">Lync 2010 Mobile</span><span class="sxs-lookup"><span data-stu-id="27780-221">Lync 2010 Mobile</span></span></p></td>
<td><p><span data-ttu-id="27780-222">是</span><span class="sxs-lookup"><span data-stu-id="27780-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-223">是</span><span class="sxs-lookup"><span data-stu-id="27780-223">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27780-224">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="27780-224">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="27780-225">是</span><span class="sxs-lookup"><span data-stu-id="27780-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-226">是</span><span class="sxs-lookup"><span data-stu-id="27780-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-227">是</span><span class="sxs-lookup"><span data-stu-id="27780-227">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27780-228">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="27780-228">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="27780-229">是</span><span class="sxs-lookup"><span data-stu-id="27780-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-230">是</span><span class="sxs-lookup"><span data-stu-id="27780-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-231">是</span><span class="sxs-lookup"><span data-stu-id="27780-231">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-232">是</span><span class="sxs-lookup"><span data-stu-id="27780-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-233">Yes1</span><span class="sxs-lookup"><span data-stu-id="27780-233">Yes1</span></span></p></td>
<td><p><span data-ttu-id="27780-234">是</span><span class="sxs-lookup"><span data-stu-id="27780-234">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27780-235">公共 IM （AOL、Yahoo！）</span><span class="sxs-lookup"><span data-stu-id="27780-235">Public IM (AOL, Yahoo!)</span></span></p></td>
<td><p><span data-ttu-id="27780-236">是</span><span class="sxs-lookup"><span data-stu-id="27780-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-237">是</span><span class="sxs-lookup"><span data-stu-id="27780-237">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27780-238">公共 IM （MSN、Windows Live Messenger）</span><span class="sxs-lookup"><span data-stu-id="27780-238">Public IM (MSN, Windows Live Messenger)</span></span></p></td>
<td><p><span data-ttu-id="27780-239">是</span><span class="sxs-lookup"><span data-stu-id="27780-239">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-240">是</span><span class="sxs-lookup"><span data-stu-id="27780-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-241">是</span><span class="sxs-lookup"><span data-stu-id="27780-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-242">是</span><span class="sxs-lookup"><span data-stu-id="27780-242">Yes</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="27780-243">从9月1日起，2012，Microsoft Lync 公共 IM 连接用户订阅许可证（PIC USL）不再可用于购买新的或续订的协议。</span><span class="sxs-lookup"><span data-stu-id="27780-243">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="27780-244">拥有主动许可证的客户将能够继续与 Yahoo！联合联合</span><span class="sxs-lookup"><span data-stu-id="27780-244">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="27780-245">信使，直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="27780-245">Messenger until the service shutdown date.</span></span> <span data-ttu-id="27780-246">AOL 和 Yahoo！的生命周期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="27780-246">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="27780-247">已宣布。</span><span class="sxs-lookup"><span data-stu-id="27780-247">has been announced.</span></span> <span data-ttu-id="27780-248">有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时消息连接</A>。。</span><span class="sxs-lookup"><span data-stu-id="27780-248">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>..</span></span></P>
> <LI>
> <P><span data-ttu-id="27780-249">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每用户、每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="27780-249">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="27780-250">Messenger.</span><span class="sxs-lookup"><span data-stu-id="27780-250">Messenger.</span></span> <span data-ttu-id="27780-251">Microsoft 提供此服务的能力因 Yahoo！中的支持而异，将不会续订的底层协议。</span><span class="sxs-lookup"><span data-stu-id="27780-251">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="27780-252">Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。</span><span class="sxs-lookup"><span data-stu-id="27780-252">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="27780-253">与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="27780-253">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="27780-254">Skype 联盟将添加到此列表中，使 Lync 用户能够通过即时消息和语音访问数百个人。</span><span class="sxs-lookup"><span data-stu-id="27780-254">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="27780-255">1在 Office Communicator 2007 R2 中，仅有桌面共享（而非程序共享）可用。</span><span class="sxs-lookup"><span data-stu-id="27780-255">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="27780-256">如果强制实施 Skype for Business 2015 客户端用户界面，则无法从较新的客户端启动 Office Communicator 2007 R2 和 Skype for Business 2015 之间的桌面共享。</span><span class="sxs-lookup"><span data-stu-id="27780-256">Desktop sharing between Office Communicator 2007 R2 and Skype for Business 2015 cannot be initiated from the newer client when the Skype for Business 2015 client user interface is enforced.</span></span>



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a><span data-ttu-id="27780-257">Lync Server 2010 会议中 Lync 2013 客户端的会议功能支持</span><span class="sxs-lookup"><span data-stu-id="27780-257">Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings</span></span>

<span data-ttu-id="27780-258">当用户使用 Lync 2013 客户端加入 Lync Server 2010 会议时，他们可以访问 Lync 2013 客户端功能，但有以下例外：</span><span class="sxs-lookup"><span data-stu-id="27780-258">When users join Lync Server 2010 meetings with a Lync 2013 client, they have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="27780-259">在**参与者**管理选项（可通过指向会议窗口中的 "人员" 图标访问）中，"**无会议即时消息**" 选项不起作用。</span><span class="sxs-lookup"><span data-stu-id="27780-259">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="27780-260">库视图在视频会议中不起作用。</span><span class="sxs-lookup"><span data-stu-id="27780-260">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="27780-261">用户仅看到活动的扬声器，而不是所有扬声器。</span><span class="sxs-lookup"><span data-stu-id="27780-261">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="27780-262">在 "**选取布局**" 选项列表中，"**库视图**" 不可用</span><span class="sxs-lookup"><span data-stu-id="27780-262">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="27780-263">默认情况下，参与者列表在视频会议中显示。</span><span class="sxs-lookup"><span data-stu-id="27780-263">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="27780-264">右键单击 "参与者" 列表中的用户时，"**锁定视频焦点**并**固定到库**参与者管理" 选项不可用。</span><span class="sxs-lookup"><span data-stu-id="27780-264">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a><span data-ttu-id="27780-265">Lync Server 2013 会议中的会议功能支持</span><span class="sxs-lookup"><span data-stu-id="27780-265">Conferencing Feature Support in Lync Server 2013 Meetings</span></span>

<span data-ttu-id="27780-266">Lync Server 2013 提供新的会议功能，这些功能在其帐户移动到 Lync Server 2013 并使用 Lync 2013 客户端登录后可供用户使用。</span><span class="sxs-lookup"><span data-stu-id="27780-266">Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="27780-267">示例包括视频库视图、HD 视频、PowerPoint 共享，以及在会议进入时将所有与会者音频和视频设为静音的选项。</span><span class="sxs-lookup"><span data-stu-id="27780-267">Examples include video gallery view, HD video, PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="27780-268">[Lync server 2013 的新会议功能](lync-server-2013-new-conferencing-features.md)中概述了新功能，以及[lync server 2013 中客户端的新增](lync-server-2013-what-s-new-for-clients.md)功能。</span><span class="sxs-lookup"><span data-stu-id="27780-268">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="27780-269">在 Lync Server 2013 会议中，某些会议功能对于驻留在不同版本的服务器上的用户以及使用不同客户端和客户端版本的用户都受支持。</span><span class="sxs-lookup"><span data-stu-id="27780-269">In Lync Server 2013 meetings, certain conferencing features are supported for users who are homed on different versions of the server and who are using different clients and client versions.</span></span> <span data-ttu-id="27780-270">当客户端加入 Lync Server 2013 会议时，用户可以访问此表中所示的特性和功能。</span><span class="sxs-lookup"><span data-stu-id="27780-270">When clients join a Lync Server 2013 meeting, users have access to the features and capabilities shown in this table.</span></span>


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
<th><span data-ttu-id="27780-271">Client</span><span class="sxs-lookup"><span data-stu-id="27780-271">Client</span></span></th>
<th><span data-ttu-id="27780-272">对等 IM</span><span class="sxs-lookup"><span data-stu-id="27780-272">Peer-to-peer IM</span></span></th>
<th><span data-ttu-id="27780-273">语音</span><span class="sxs-lookup"><span data-stu-id="27780-273">Voice</span></span></th>
<th><span data-ttu-id="27780-274">视频</span><span class="sxs-lookup"><span data-stu-id="27780-274">Video</span></span></th>
<th><span data-ttu-id="27780-275">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="27780-275">Application Sharing</span></span></th>
<th><span data-ttu-id="27780-276">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="27780-276">PowerPoint</span></span></th>
<th><span data-ttu-id="27780-277">文件传输</span><span class="sxs-lookup"><span data-stu-id="27780-277">File Transfer</span></span></th>
<th><span data-ttu-id="27780-278">Whiteboard</span><span class="sxs-lookup"><span data-stu-id="27780-278">Whiteboard</span></span></th>
<th><span data-ttu-id="27780-279">轮询</span><span class="sxs-lookup"><span data-stu-id="27780-279">Polling</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27780-280">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="27780-280">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="27780-281">是</span><span class="sxs-lookup"><span data-stu-id="27780-281">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-282">是</span><span class="sxs-lookup"><span data-stu-id="27780-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-283">是</span><span class="sxs-lookup"><span data-stu-id="27780-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-284">是</span><span class="sxs-lookup"><span data-stu-id="27780-284">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-285">是</span><span class="sxs-lookup"><span data-stu-id="27780-285">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-286">是</span><span class="sxs-lookup"><span data-stu-id="27780-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-287">是</span><span class="sxs-lookup"><span data-stu-id="27780-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-288">是</span><span class="sxs-lookup"><span data-stu-id="27780-288">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27780-289">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="27780-289">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="27780-290">是</span><span class="sxs-lookup"><span data-stu-id="27780-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-291">是</span><span class="sxs-lookup"><span data-stu-id="27780-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-292">是</span><span class="sxs-lookup"><span data-stu-id="27780-292">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-293">是</span><span class="sxs-lookup"><span data-stu-id="27780-293">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-294">是</span><span class="sxs-lookup"><span data-stu-id="27780-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-295">是</span><span class="sxs-lookup"><span data-stu-id="27780-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-296">是</span><span class="sxs-lookup"><span data-stu-id="27780-296">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-297">是</span><span class="sxs-lookup"><span data-stu-id="27780-297">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27780-298">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="27780-298">Lync Web App</span></span></p></td>
<td><p><span data-ttu-id="27780-299">是</span><span class="sxs-lookup"><span data-stu-id="27780-299">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-300">是</span><span class="sxs-lookup"><span data-stu-id="27780-300">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-301">是</span><span class="sxs-lookup"><span data-stu-id="27780-301">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-302">是</span><span class="sxs-lookup"><span data-stu-id="27780-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-303">是2</span><span class="sxs-lookup"><span data-stu-id="27780-303">Yes2</span></span></p></td>
<td><p><span data-ttu-id="27780-304">是</span><span class="sxs-lookup"><span data-stu-id="27780-304">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-305">是</span><span class="sxs-lookup"><span data-stu-id="27780-305">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-306">是</span><span class="sxs-lookup"><span data-stu-id="27780-306">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27780-307">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="27780-307">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="27780-308">是</span><span class="sxs-lookup"><span data-stu-id="27780-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-309">是</span><span class="sxs-lookup"><span data-stu-id="27780-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-310">是</span><span class="sxs-lookup"><span data-stu-id="27780-310">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-311">是</span><span class="sxs-lookup"><span data-stu-id="27780-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-312">Yes3</span><span class="sxs-lookup"><span data-stu-id="27780-312">Yes3</span></span></p></td>
<td><p><span data-ttu-id="27780-313">是</span><span class="sxs-lookup"><span data-stu-id="27780-313">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-314">是</span><span class="sxs-lookup"><span data-stu-id="27780-314">Yes</span></span></p></td>
<td><p><span data-ttu-id="27780-315">是</span><span class="sxs-lookup"><span data-stu-id="27780-315">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27780-316">Office Communicator 2007 R2 4</span><span class="sxs-lookup"><span data-stu-id="27780-316">Office Communicator 2007 R2 4</span></span></p></td>
<td><p><span data-ttu-id="27780-317">是</span><span class="sxs-lookup"><span data-stu-id="27780-317">Yes</span></span></p></td>
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


<span data-ttu-id="27780-318">1在 Office Communicator 2007 R2 中，仅有桌面共享（而非程序共享）可用。</span><span class="sxs-lookup"><span data-stu-id="27780-318">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<span data-ttu-id="27780-319">2 Lync Server 2013 使用更新的机制来上载 PowerPoint 文件。</span><span class="sxs-lookup"><span data-stu-id="27780-319">2 Lync Server 2013 uses an updated mechanism for uploading PowerPoint files.</span></span> <span data-ttu-id="27780-320">加入最初在 Lync Server 2010 上安排的会议的 Lync Web App 用户可以查看和导航 PowerPoint 演示文稿，但不能上载 PowerPoint 文件。</span><span class="sxs-lookup"><span data-stu-id="27780-320">Lync Web App users who join a meeting that was originally scheduled on Lync Server 2010 can view and navigate PowerPoint presentations, but cannot upload PowerPoint files.</span></span>

<span data-ttu-id="27780-321">3如果会议是在 Lync Server 2013 上安排的，并且 PowerPoint 幻灯片已由 Lync 2013 客户端上载，Lync 2010 用户可以仅查看对幻灯片的访问权限。</span><span class="sxs-lookup"><span data-stu-id="27780-321">3 If the meeting was scheduled on Lync Server 2013 and PowerPoint slides were uploaded by a Lync 2013 client, Lync 2010 users have view-only access to the slides.</span></span> <span data-ttu-id="27780-322">相反，如果 Lync 2010 用户上传了 PowerPoint 幻灯片，Lync Server 2013 用户将能够查看和幻灯片，如果配置了 Office Web Apps Server，则可以访问新的功能，例如更高分辨率的显示、动画、幻灯片切换和嵌入的视频。</span><span class="sxs-lookup"><span data-stu-id="27780-322">Conversely, if the PowerPoint slides were uploaded by a Lync 2010 user, Lync Server 2013 users will be able to view and slides and, if Office Web Apps Server is configured, access new capabilities such as higher resolution display, animations, slide transitions, and embedded video.</span></span> <span data-ttu-id="27780-323">有关详细信息，请参阅[配置与 Office Web Apps Server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="27780-323">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="27780-324">Office Communicator 2007 R2 中的4The 状态和 IM 功能与 Lync Server 2013 兼容，但会议功能不兼容。</span><span class="sxs-lookup"><span data-stu-id="27780-324">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="27780-325">从 Office 通信服务器 2007 R2 迁移过程中，Office Communicator 2007 R2 适用于状态和 IM 互操作性，但用户应使用 Lync Web App 2013 加入 Lync Server 2013 会议。</span><span class="sxs-lookup"><span data-stu-id="27780-325">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a><span data-ttu-id="27780-326">计划加载项支持</span><span class="sxs-lookup"><span data-stu-id="27780-326">Scheduling Add-in Support</span></span>

<span data-ttu-id="27780-327">对各种计划外接程序的服务器支持与服务器和客户端版本的兼容性一致。</span><span class="sxs-lookup"><span data-stu-id="27780-327">Server support for the various scheduling add-ins is consistent with server and client version compatibility.</span></span> <span data-ttu-id="27780-328">通常情况下，以下计划外接程序在 Lync Server 2013 上受支持。</span><span class="sxs-lookup"><span data-stu-id="27780-328">In general, the following scheduling add-ins are supported on Lync Server 2013.</span></span> <span data-ttu-id="27780-329">但是，早期版本的外接程序不提供新的 Lync 2013 外接程序功能，例如，在会议进入时将所有与会者音频和视频设为静音的选项。</span><span class="sxs-lookup"><span data-stu-id="27780-329">However, previous versions of add-ins do not provide new Lync 2013 add-in features, such as the option to mute all attendee audio and video upon meeting entry.</span></span>

  - <span data-ttu-id="27780-330">**Lync 2013**   的联机会议外接程序提供了与 lync 2010 的联机会议外接程序相同的功能，并添加了 "与会者静音" 控件，使会议组织者可以计划默认情况下为与会者音频和视频静音的会议。</span><span class="sxs-lookup"><span data-stu-id="27780-330">**Online Meeting Add-in for Lync 2013**   Provides the same features as the Online Meeting Add-in for Lync 2010, with the addition of attendee mute controls, which allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span> <span data-ttu-id="27780-331">管理员还可以通过添加自定义徽标、支持 URL、合法免责声明 URL 或自定义页脚文本来自定义组织的会议邀请。</span><span class="sxs-lookup"><span data-stu-id="27780-331">Administrators can also customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span>

  - <span data-ttu-id="27780-332">**Lync 2010**   的联机会议外接程序为 lync 会议提供了计划，并删除了安排 Office Live 会议会议的功能。</span><span class="sxs-lookup"><span data-stu-id="27780-332">**Online Meeting Add-in for Lync 2010**   Provides scheduling for Lync meetings and removes the capability to schedule Office Live Meeting conferences.</span></span>

  - <span data-ttu-id="27780-333">**Office communicator 2007 r2 会议外接程序**   为 Office Live Meeting 会议和 office Communicator 2007 R2 会议提供计划。</span><span class="sxs-lookup"><span data-stu-id="27780-333">**Office Communicator 2007 R2 Conferencing Add-in**   Provides scheduling for both Office Live Meeting conferences and Office Communicator 2007 R2 conferences.</span></span> 

<div>


> [!NOTE]  
> <span data-ttu-id="27780-334">无法在 Lync Server 2013 上计划 Live Meeting 会议。</span><span class="sxs-lookup"><span data-stu-id="27780-334">Live Meeting conferences cannot be scheduled on Lync Server 2013.</span></span>



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
<th><span data-ttu-id="27780-335">计划客户端</span><span class="sxs-lookup"><span data-stu-id="27780-335">Scheduling Client</span></span></th>
<th><span data-ttu-id="27780-336">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27780-336">Lync Server 2013</span></span></th>
<th><span data-ttu-id="27780-337">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="27780-337">Lync Server 2010</span></span></th>
<th><span data-ttu-id="27780-338">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="27780-338">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27780-339">适用于 Lync 2013 的联机会议外接程序（可与 Office 2013、Outlook 2010 和 Outlook 2007 一起使用）</span><span class="sxs-lookup"><span data-stu-id="27780-339">Online Meeting Add-in for Lync 2013 (can be used with Office 2013, Outlook 2010, and Outlook 2007)</span></span></p></td>
<td><p><span data-ttu-id="27780-340">支持</span><span class="sxs-lookup"><span data-stu-id="27780-340">Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-341">支持（新加载项功能不可用）</span><span class="sxs-lookup"><span data-stu-id="27780-341">Supported (new add-in features not available)</span></span></p></td>
<td><p><span data-ttu-id="27780-342">不支持</span><span class="sxs-lookup"><span data-stu-id="27780-342">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27780-343">Lync 2013 Web 计划程序</span><span class="sxs-lookup"><span data-stu-id="27780-343">Lync 2013 Web Scheduler</span></span></p></td>
<td><p><span data-ttu-id="27780-344">支持</span><span class="sxs-lookup"><span data-stu-id="27780-344">Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-345">不支持</span><span class="sxs-lookup"><span data-stu-id="27780-345">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-346">不支持</span><span class="sxs-lookup"><span data-stu-id="27780-346">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27780-347">Online Meeting Add-in for Lync 2010 － Lync 2010 联机会议外接程序</span><span class="sxs-lookup"><span data-stu-id="27780-347">Online Meeting Add-in for Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="27780-348">支持</span><span class="sxs-lookup"><span data-stu-id="27780-348">Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-349">支持</span><span class="sxs-lookup"><span data-stu-id="27780-349">Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-350">不支持</span><span class="sxs-lookup"><span data-stu-id="27780-350">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27780-351">Office Communicator 2007 R2 会议加载项</span><span class="sxs-lookup"><span data-stu-id="27780-351">Office Communicator 2007 R2 Conferencing Add-in</span></span></p></td>
<td><p><span data-ttu-id="27780-352">不支持</span><span class="sxs-lookup"><span data-stu-id="27780-352">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-353">支持</span><span class="sxs-lookup"><span data-stu-id="27780-353">Supported</span></span></p></td>
<td><p><span data-ttu-id="27780-354">支持</span><span class="sxs-lookup"><span data-stu-id="27780-354">Supported</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a><span data-ttu-id="27780-355">支持加入会议</span><span class="sxs-lookup"><span data-stu-id="27780-355">Support for Joining Meetings</span></span>

<span data-ttu-id="27780-356">允许 Lync Server 2013 支持的所有客户端加入 Lync 2013 会议。</span><span class="sxs-lookup"><span data-stu-id="27780-356">All of the clients that Lync Server 2013 supports are allowed to join Lync 2013 meetings.</span></span> <span data-ttu-id="27780-357">由于 Lync web App 是服务器的 Web 组件，因此，如果使用 Lync Web App 加入 Lync Server 2013 会议，则始终使用最新版本的 Lync Web App。</span><span class="sxs-lookup"><span data-stu-id="27780-357">Because Lync Web App is a web component of the server, in cases where Lync Web App is used to join a Lync Server 2013 meeting, the newer version of Lync Web App is always used.</span></span>

<span data-ttu-id="27780-358">Lync 2013 客户端可以加入在 Lync 2010 上托管的会议和 Office 通信服务器 2007 R2 （向下扩展功能）。</span><span class="sxs-lookup"><span data-stu-id="27780-358">Lync 2013 clients can join meetings hosted on Lync 2010 and Office Communications Server 2007 R2 with scaled-down functionality.</span></span> <span data-ttu-id="27780-359">会议中的功能受托管会议的服务器版本的限制。</span><span class="sxs-lookup"><span data-stu-id="27780-359">In-meeting features are limited by the version of the server on which the meeting is hosted.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="27780-360">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27780-360">See Also</span></span>


[<span data-ttu-id="27780-361">Lync Server 2013 的 lync Windows 应用商店应用程序要求</span><span class="sxs-lookup"><span data-stu-id="27780-361">Lync Windows Store app requirements for Lync Server 2013</span></span>](lync-server-2013-lync-windows-store-app-requirements.md)  
[<span data-ttu-id="27780-362">Lync Server 2013 中的新会议功能</span><span class="sxs-lookup"><span data-stu-id="27780-362">New conferencing features in Lync Server 2013</span></span>](lync-server-2013-new-conferencing-features.md)  
[<span data-ttu-id="27780-363">Lync Server 2013 中客户端的新增功能</span><span class="sxs-lookup"><span data-stu-id="27780-363">What's new for clients in Lync Server 2013</span></span>](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

