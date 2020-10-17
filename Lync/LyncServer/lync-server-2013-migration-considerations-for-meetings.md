---
title: Lync Server 2013：会议的迁移注意事项
description: Lync Server 2013：会议的迁移注意事项。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration considerations for meetings
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61097556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e238405acf7bc2a96fd2efd4cca761c1f1f258fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560938"
---
# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a><span data-ttu-id="d72f1-103">Lync Server 2013 中的会议的迁移注意事项</span><span class="sxs-lookup"><span data-stu-id="d72f1-103">Migration considerations for meetings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d72f1-104">_**上次修改的主题：** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="d72f1-104">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="d72f1-105">本节讨论下列主题：</span><span class="sxs-lookup"><span data-stu-id="d72f1-105">The following topics are discussed in this section:</span></span>

  - <span data-ttu-id="d72f1-106">在 Microsoft Lync Server 2013 中对会议所做的更改</span><span class="sxs-lookup"><span data-stu-id="d72f1-106">Changes to meetings in Microsoft Lync Server 2013</span></span>

  - <span data-ttu-id="d72f1-107">根据会议需要迁移用户</span><span class="sxs-lookup"><span data-stu-id="d72f1-107">Migrating users based on their conferencing needs</span></span>

  - <span data-ttu-id="d72f1-108">迁移现有会议和会议内容</span><span class="sxs-lookup"><span data-stu-id="d72f1-108">Migrating existing meetings and meeting content</span></span>

  - <span data-ttu-id="d72f1-109">Lync Server 2010 迁移期间的用户体验</span><span class="sxs-lookup"><span data-stu-id="d72f1-109">User experience during Lync Server 2010 migration</span></span>

  - <span data-ttu-id="d72f1-110">Office 通信服务器 2007 R2 迁移期间的用户体验</span><span class="sxs-lookup"><span data-stu-id="d72f1-110">User Experience during Office Communications Server 2007 R2 migration</span></span>

  - <span data-ttu-id="d72f1-111">Microsoft Lync 2013 与早期版本的服务器上的会议兼容性</span><span class="sxs-lookup"><span data-stu-id="d72f1-111">Microsoft Lync 2013 compatibility with meetings on earlier server versions</span></span>

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a><span data-ttu-id="d72f1-112">对 Lync Server 2013 中的会议所做的更改</span><span class="sxs-lookup"><span data-stu-id="d72f1-112">Changes to Meetings in Lync Server 2013</span></span>

<span data-ttu-id="d72f1-113">**Lync Server 2013 功能。**    Lync Server 2013 提供新的会议功能，这些功能在其帐户移动到 Lync Server 2013 并使用 Lync 2013 客户端登录后可供用户使用。</span><span class="sxs-lookup"><span data-stu-id="d72f1-113">**Lync Server 2013 features.**   Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="d72f1-114">[Lync server 2013 的新会议功能](lync-server-2013-new-conferencing-features.md)中概述了新功能，以及[lync server 2013 中客户端的新增](lync-server-2013-what-s-new-for-clients.md)功能。</span><span class="sxs-lookup"><span data-stu-id="d72f1-114">New features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="d72f1-115">**会议 URL。**    与在 Lync Server 2010 中一样，Lync Server 2013 中的所有新安排的会议都具有 URL 前缀 https://和现有会议与用户帐户一起迁移。</span><span class="sxs-lookup"><span data-stu-id="d72f1-115">**Meeting URL.**   As in Lync Server 2010, all newly scheduled meetings in Lync Server 2013 have a URL prefix of https:// and existing meetings migrate along with user accounts.</span></span> <span data-ttu-id="d72f1-116">但是，Lync Server 2013 不支持 Office 通信服务器 2007 R2 会议呼叫 (conf://URL 前缀) 或 web 会议 (meet://URL 前缀) 。</span><span class="sxs-lookup"><span data-stu-id="d72f1-116">However, Lync Server 2013 does not support the Office Communications Server 2007 R2 conference call (conf:// URL prefix) or web conference (meet:// URL prefix).</span></span> <span data-ttu-id="d72f1-117">有关详细信息，请参阅本主题后面部分中的 "从 Office 通信服务器 2007 R2 迁移会议"。</span><span class="sxs-lookup"><span data-stu-id="d72f1-117">See “Migrating Meetings from Office Communications Server 2007 R2” later in this topic for more information.</span></span>

<span data-ttu-id="d72f1-118">**客户端支持。**    与 Lync Server 2010 不同，Lync Server 2013 不支持用于会议的 Office Communicator 客户端。</span><span class="sxs-lookup"><span data-stu-id="d72f1-118">**Client support.**   Unlike Lync Server 2010, Lync Server 2013 does not support Office Communicator clients for conferencing.</span></span> <span data-ttu-id="d72f1-119">您不能使用以下客户端加入通过 Lync 2013 的联机会议外接程序安排的会议：</span><span class="sxs-lookup"><span data-stu-id="d72f1-119">You cannot use the following clients to join meetings scheduled through the Online Meeting Add-in for Lync 2013:</span></span>

  - <span data-ttu-id="d72f1-120">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="d72f1-120">Office Communicator 2007 R2</span></span>

  - <span data-ttu-id="d72f1-121">Microsoft Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="d72f1-121">Microsoft Office Communications Server 2007 R2 Attendant</span></span>

  - <span data-ttu-id="d72f1-122">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="d72f1-122">Office Communicator 2007</span></span>

  - <span data-ttu-id="d72f1-123">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="d72f1-123">Office Live Meeting 2007</span></span>

<span data-ttu-id="d72f1-124">在迁移过程中，Office Communicator 2007 R2 用户应使用 Lync Web App 2013 加入 Lync Server 2013 会议，直到他们的客户端升级。</span><span class="sxs-lookup"><span data-stu-id="d72f1-124">During migration, Office Communicator 2007 R2 users should use Lync Web App 2013 to join Lync Server 2013 meetings until their clients are upgraded.</span></span> <span data-ttu-id="d72f1-125">请注意，Office Communicator 2007 R2 用户可以继续对 Lync Server 2013 使用其现有客户端，了解状态和 IM 功能，但不支持会议功能。</span><span class="sxs-lookup"><span data-stu-id="d72f1-125">Note that Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a><span data-ttu-id="d72f1-126">根据会议需要迁移用户</span><span class="sxs-lookup"><span data-stu-id="d72f1-126">Migrating Users Based on Their Conferencing Needs</span></span>

<span data-ttu-id="d72f1-127">**会议组织者频繁。**    请考虑在该过程的早期阶段迁移频繁的会议组织者，以便他们能够利用[lync server 2013 的新会议功能](lync-server-2013-new-conferencing-features.md)中概述的新 Lync server 2013 和 lync 2013 功能，以及[lync server 2013 中的客户端的新增](lync-server-2013-what-s-new-for-clients.md)功能。</span><span class="sxs-lookup"><span data-stu-id="d72f1-127">**Frequent meeting organizers.**   Consider migrating frequent meeting organizers early in the process so that they can take advantage of the new Lync Server 2013 and Lync 2013 features outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="d72f1-128">**Live Meeting 用户。**    如果要从 Office 通信服务器 2007 R2 进行迁移，并且您的用户需要特定于 Live Meeting 的 web 会议功能，尤其是对大型会议和出在会议室的支持，您可以选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="d72f1-128">**Live Meeting users.**   If you are migrating from Office Communications Server 2007 R2 and you have users who need web conferencing features specific to Live Meeting—particularly support for large meetings and break-out rooms—you have the following options:</span></span>

  - <span data-ttu-id="d72f1-129">建议组织者使用 Live Meeting 服务（如果在组织中可用）。</span><span class="sxs-lookup"><span data-stu-id="d72f1-129">Advise organizers to use the Live Meeting service, if available in your organization.</span></span>

  - <span data-ttu-id="d72f1-130">让组织者驻留在 Office 通信服务器的早期版本上，以便他们可以继续安排基于服务器的 Live Meeting web 会议。</span><span class="sxs-lookup"><span data-stu-id="d72f1-130">Leave the organizers homed on the earlier version of Office Communications Server, so they can continue to schedule server-based Live Meeting web conferences.</span></span>

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a><span data-ttu-id="d72f1-131">迁移现有会议和会议内容</span><span class="sxs-lookup"><span data-stu-id="d72f1-131">Migrating Existing Meetings and Meeting Content</span></span>

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a><span data-ttu-id="d72f1-132">从 Lync Server 2010 迁移会议</span><span class="sxs-lookup"><span data-stu-id="d72f1-132">Migrating Meetings from Lync Server 2010</span></span>

<span data-ttu-id="d72f1-133">将用户从 Lync Server 2010 移动到 Lync Server 2013 时，以下信息将随用户帐户一起移动：</span><span class="sxs-lookup"><span data-stu-id="d72f1-133">When you move a user from Lync Server 2010 to Lync Server 2013, the following information moves with the user’s account:</span></span>

  - <span data-ttu-id="d72f1-134">先前由用户安排的会议。</span><span class="sxs-lookup"><span data-stu-id="d72f1-134">Meetings already scheduled by the user.</span></span> <span data-ttu-id="d72f1-135">这包括会议目录和会议数据。</span><span class="sxs-lookup"><span data-stu-id="d72f1-135">This includes conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="d72f1-136">用户的个人标识号 (PIN)。</span><span class="sxs-lookup"><span data-stu-id="d72f1-136">The user’s personal identification number (PIN).</span></span> <span data-ttu-id="d72f1-137">用户的当前 PIN 在到期或用户请求新 PIN 之前仍然有效。</span><span class="sxs-lookup"><span data-stu-id="d72f1-137">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="d72f1-138">但是，以下用户帐户信息不会移动到新服务器：</span><span class="sxs-lookup"><span data-stu-id="d72f1-138">However, the following user account information does not move to the new server:</span></span>

  - <span data-ttu-id="d72f1-139">会议内容，例如 PowerPoint 演示文稿、白板内容和轮询数据</span><span class="sxs-lookup"><span data-stu-id="d72f1-139">Meeting content, for example PowerPoint presentations, whiteboard content, and poll data</span></span>

<span data-ttu-id="d72f1-140">若要移动会议中已共享的内容，请使用 Move-CsUser cmdlet 的 MoveMeetingContent 参数。</span><span class="sxs-lookup"><span data-stu-id="d72f1-140">To move the content that has been shared in meetings, use the MoveMeetingContent parameter of the Move-CsUser cmdlet.</span></span> <span data-ttu-id="d72f1-141">有关使用此 cmdlet 的详细信息，请参阅 Lync Server 2013 cmdlet 文档中的 [get-csuser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) 。</span><span class="sxs-lookup"><span data-stu-id="d72f1-141">For details about using this cmdlet, see [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) in the Lync Server 2013 cmdlets documentation.</span></span>

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a><span data-ttu-id="d72f1-142">从 Office 通信服务器 2007 R2 迁移会议</span><span class="sxs-lookup"><span data-stu-id="d72f1-142">Migrating Meetings from Office Communications Server 2007 R2</span></span>

<span data-ttu-id="d72f1-143">Office 通信服务器 2007 R2 会议可以是会议呼叫 (conf://URL 前缀) 或 web 会议 (meet://URL 前缀) 。</span><span class="sxs-lookup"><span data-stu-id="d72f1-143">Office Communications Server 2007 R2 meetings are either conference calls (conf:// URL prefix) or web conferences (meet:// URL prefix).</span></span> <span data-ttu-id="d72f1-144">Lync Server 2013 不支持这些早期的 conf://和 meet://会议，它们不会与用户帐户一起迁移。</span><span class="sxs-lookup"><span data-stu-id="d72f1-144">Lync Server 2013 does not support these earlier conf:// and meet:// conferences, and they are not migrated along with the user account.</span></span> <span data-ttu-id="d72f1-145">迁移后，应指示用户为他们安排的任何联机会议更新链接。</span><span class="sxs-lookup"><span data-stu-id="d72f1-145">After migration, you should instruct users to update the links for any online meetings they have scheduled.</span></span> <span data-ttu-id="d72f1-146">在安装 Lync 2013 客户端后，他们可以通过打开计划会议邀请（更新会议 URL）并将邀请重新发送给参与者来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d72f1-146">They can do this after installing the Lync 2013 client by opening a scheduled meeting invitation—which updates the meeting URL—and resending the invitation to participants.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a><span data-ttu-id="d72f1-147">Lync Server 2010 迁移期间的用户体验</span><span class="sxs-lookup"><span data-stu-id="d72f1-147">User Experience during Lync Server 2010 Migration</span></span>

<span data-ttu-id="d72f1-148">本节提供从 Lync 2010 迁移时用户的会议体验的摘要。</span><span class="sxs-lookup"><span data-stu-id="d72f1-148">This section provides a summary of users’ conferencing experience when migrating from Lync 2010.</span></span> <span data-ttu-id="d72f1-149">有关 Lync Server 2013 客户端如何共存以及如何与以前的客户端和服务器版本交互的详细信息，请参阅 [Lync 2013 中的客户端互操作性](lync-server-2013-client-interoperability-in-lync-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="d72f1-149">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a><span data-ttu-id="d72f1-150">将 Lync Server 2010 会议与 Lync 2013 客户端加入</span><span class="sxs-lookup"><span data-stu-id="d72f1-150">Joining Lync Server 2010 Meetings with a Lync 2013 Client</span></span>

<span data-ttu-id="d72f1-151">在从 Lync Server 2010 迁移过程中，当用户加入 lync Server 2010 会议和 Lync 2013 客户端时，可能会有一段共存时间。</span><span class="sxs-lookup"><span data-stu-id="d72f1-151">During migration from Lync Server 2010, there may be a period of coexistence when users join Lync Server 2010 meetings with a Lync 2013 client.</span></span> <span data-ttu-id="d72f1-152">这些用户有权访问 Lync 2013 客户端功能，但有以下例外：</span><span class="sxs-lookup"><span data-stu-id="d72f1-152">These users have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="d72f1-153">在 **参与者** 管理选项（可通过指向会议窗口中的 "人员" 图标访问）中，" **无会议即时消息** " 选项不起作用。</span><span class="sxs-lookup"><span data-stu-id="d72f1-153">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="d72f1-154">库视图在视频会议中不起作用。</span><span class="sxs-lookup"><span data-stu-id="d72f1-154">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="d72f1-155">用户仅看到活动的扬声器，而不是所有扬声器。</span><span class="sxs-lookup"><span data-stu-id="d72f1-155">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="d72f1-156">在 " **选取布局** " 选项列表中，" **库视图** " 不可用</span><span class="sxs-lookup"><span data-stu-id="d72f1-156">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="d72f1-157">默认情况下，参与者列表在视频会议中显示。</span><span class="sxs-lookup"><span data-stu-id="d72f1-157">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="d72f1-158">右键单击 "参与者" 列表中的用户时，" **锁定视频焦点** 并 **固定到库** 参与者管理" 选项不可用。</span><span class="sxs-lookup"><span data-stu-id="d72f1-158">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a><span data-ttu-id="d72f1-159">Office 通信服务器 2007 R2 迁移期间的用户体验</span><span class="sxs-lookup"><span data-stu-id="d72f1-159">User Experience during Office Communications Server 2007 R2 Migration</span></span>

<span data-ttu-id="d72f1-160">本部分提供了在安装 Lync 2013 之前和之后从 Office 通信服务器 2007 R2 迁移时用户的会议体验摘要。</span><span class="sxs-lookup"><span data-stu-id="d72f1-160">This section provides a summary of users’ conferencing experience when migrating from Office Communications Server 2007 R2, both before and after Lync 2013 is installed.</span></span> <span data-ttu-id="d72f1-161">有关 Lync Server 2013 客户端如何共存以及如何与以前的客户端和服务器版本交互的详细信息，请参阅 [Lync 2013 中的客户端互操作性](lync-server-2013-client-interoperability-in-lync-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="d72f1-161">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a><span data-ttu-id="d72f1-162">在迁移用户帐户之后，安装 Lync 2013 之前</span><span class="sxs-lookup"><span data-stu-id="d72f1-162">After User Account is Migrated, Before Lync 2013 Is Installed</span></span>

<span data-ttu-id="d72f1-163">将用户迁移到 Lync Server 2013 服务器，但在安装新客户端之前，Office Communicator 2007 R2 用户可以继续使用其现有客户端，使其与 Lync Server 2013 相关的状态和 IM 功能，但不支持会议功能。</span><span class="sxs-lookup"><span data-stu-id="d72f1-163">After a user is migrated to the Lync Server 2013 server, but before new clients are installed, Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a><span data-ttu-id="d72f1-164">在迁移用户帐户后，安装 Lync 2013 之后</span><span class="sxs-lookup"><span data-stu-id="d72f1-164">After User Account is Migrated, After Lync 2013 Is Installed</span></span>

<span data-ttu-id="d72f1-165">当已迁移的用户安装 Lync 2013 时，将同时安装 Lync 2013 的联机会议外接程序。</span><span class="sxs-lookup"><span data-stu-id="d72f1-165">When a migrated user installs Lync 2013, the Online Meeting Add-in for Lync 2013 is installed too.</span></span> <span data-ttu-id="d72f1-166">这具有以下效果：</span><span class="sxs-lookup"><span data-stu-id="d72f1-166">This has the following effects:</span></span>

  - <span data-ttu-id="d72f1-167">以后安排的所有会议都使用新会议格式，即使用 https:// 地址，而不是旧 meet:// Live Meeting 地址。</span><span class="sxs-lookup"><span data-stu-id="d72f1-167">All subsequently scheduled meetings use the new meeting format, which uses an https:// address instead of the legacy meet:// Live Meeting address.</span></span>

  - <span data-ttu-id="d72f1-168">在 Lync 2013 的 IT 托管部署中，管理员可以选择卸载 Microsoft Office Outlook 的会议外接程序，该外接程序用于安排 Live Meeting 服务器和基于服务的会议。</span><span class="sxs-lookup"><span data-stu-id="d72f1-168">In an IT-managed deployment of Lync 2013, the administrator has the option of uninstalling the Conferencing Add-in for Microsoft Office Outlook, which is used to schedule Live Meeting server and service-based meetings.</span></span> <span data-ttu-id="d72f1-169">然而，您的用户可能需要继续安排 Live Meeting 服务会议。</span><span class="sxs-lookup"><span data-stu-id="d72f1-169">However, you may have users who need to continue to schedule Live Meeting service meetings.</span></span> <span data-ttu-id="d72f1-170">在这种情况下，您可以允许两个外接程序共存。</span><span class="sxs-lookup"><span data-stu-id="d72f1-170">In this case, you can allow both add-ins to coexist.</span></span>

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a><span data-ttu-id="d72f1-171">与使用早期客户端的联盟组织召开的会议</span><span class="sxs-lookup"><span data-stu-id="d72f1-171">Meetings with Federated Organizations that Use Previous Clients</span></span>

<span data-ttu-id="d72f1-172">联合组织中使用 Microsoft Office Communicator 2007 的用户无法加入组织中的 Lync Server 2013 会议（如果组织已锁定这些会议）。</span><span class="sxs-lookup"><span data-stu-id="d72f1-172">Users in federated organizations who are using Microsoft Office Communicator 2007 cannot join Lync Server 2013 meetings in your organization if those meetings are locked by the organizer.</span></span> <span data-ttu-id="d72f1-173">您必须在 Lync Server 2013 中重新安排这些会议，以便在联合参与者使用新的 https://会议 URL 加入会议时，他们可以使用 Lync Web App。</span><span class="sxs-lookup"><span data-stu-id="d72f1-173">You have to reschedule these meetings in Lync Server 2013 so when federated participants join the meeting by using the new https:// meeting URL, they can use Lync Web App.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

