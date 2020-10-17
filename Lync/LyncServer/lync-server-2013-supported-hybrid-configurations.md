---
title: Lync Server 2013：支持的混合配置
description: Lync Server 2013：支持的混合配置。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported hybrid configurations
ms:assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945633(v=OCS.15)
ms:contentKeyID: 51541482
ms.date: 05/10/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a51667a9c10322b4e2503d81c8b3ddb07c17855
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550878"
---
# <a name="supported-lync-server-2013-hybrid-configurations"></a><span data-ttu-id="bd52a-103">支持的 Lync Server 2013 混合配置</span><span class="sxs-lookup"><span data-stu-id="bd52a-103">Supported Lync Server 2013 hybrid configurations</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd52a-104">_**上次修改的主题：** 2016-05-10_</span><span class="sxs-lookup"><span data-stu-id="bd52a-104">_**Topic Last Modified:** 2016-05-10_</span></span>

<span data-ttu-id="bd52a-105">你可以将 Lync Server 2013 部署配置为与 Microsoft Exchange Server 2010 和 Microsoft Exchange server 2013 和 SharePoint Server （本地和联机）集成。</span><span class="sxs-lookup"><span data-stu-id="bd52a-105">You can configure Lync Server 2013 deployments for integration with both Microsoft Exchange Server 2010 and Microsoft Exchange Server 2013 and SharePoint Server, both on-premises and online.</span></span> <span data-ttu-id="bd52a-106">除非另行指定，否则所有客户端都支持下表中列出的功能。</span><span class="sxs-lookup"><span data-stu-id="bd52a-106">The features listed in the following table are supported with all clients unless otherwise specified.</span></span> <span data-ttu-id="bd52a-107">有关客户端支持的详细信息，请参阅适用[于 skype For Business Online 客户](https://go.microsoft.com/fwlink/p/?linkid=281902)端的 Lync Server 2013 和 Skype For business online 客户端比较表[的客户端比较表](lync-server-2013-desktop-client-comparison-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="bd52a-107">For more information about client support, see [Client comparison tables for Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md) and Skype for Business Online client comparison tables at [Clients for Skype for Business Online](https://go.microsoft.com/fwlink/p/?linkid=281902).</span></span>

<div>

## <a name="integration-with-exchange-server"></a><span data-ttu-id="bd52a-108">与 Exchange Server 集成</span><span class="sxs-lookup"><span data-stu-id="bd52a-108">Integration with Exchange Server</span></span>

<span data-ttu-id="bd52a-109">下表列出了在与 Microsoft Exchange Server 集成时的混合部署中支持的功能。</span><span class="sxs-lookup"><span data-stu-id="bd52a-109">The following table lists the features supported in a hybrid deployment when integrated with Microsoft Exchange Server.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="bd52a-110">本地 Exchange</span><span class="sxs-lookup"><span data-stu-id="bd52a-110">Exchange on-premises</span></span></th>
<th><span data-ttu-id="bd52a-111">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bd52a-111">Exchange Online</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd52a-112"><strong>Lync Server 2013 本地</strong></span><span class="sxs-lookup"><span data-stu-id="bd52a-112"><strong>Lync Server 2013 on-premises</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="bd52a-113">Outlook 中的 IM/状态</span><span class="sxs-lookup"><span data-stu-id="bd52a-113">IM/Presence in Outlook</span></span></p>
<p><span data-ttu-id="bd52a-114">有关详细信息，请参阅 <a href="lync-server-2013-im-and-presence.md">Lync Server 2013 中的 IM 和状态</a></span><span class="sxs-lookup"><span data-stu-id="bd52a-114">For more information, see <a href="lync-server-2013-im-and-presence.md">IM and presence in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="bd52a-115">通过 Outlook 安排和加入联机会议</span><span class="sxs-lookup"><span data-stu-id="bd52a-115">Schedule and join online meetings through Outlook</span></span></p>
<p><span data-ttu-id="bd52a-116">有关详细信息，请参阅 <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">集成 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="bd52a-116">For more information, see <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">Integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="bd52a-117">Outlook Web App 中的 IM/状态</span><span class="sxs-lookup"><span data-stu-id="bd52a-117">IM/Presence in Outlook Web App</span></span></p>
<p><span data-ttu-id="bd52a-118">有关详细信息，请参阅 <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">在跨界环境中配置 Microsoft Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="bd52a-118">For more information, see <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">Configuring Microsoft Lync Server 2013 in a cross-premises environment</a></span></span></p></li>
<li><p><span data-ttu-id="bd52a-119">通过 Outlook Web App 安排和加入联机会议</span><span class="sxs-lookup"><span data-stu-id="bd52a-119">Schedule and join online meetings through Outlook Web App</span></span></p></li>
<li><p><span data-ttu-id="bd52a-120">移动客户端中的 IM/状态</span><span class="sxs-lookup"><span data-stu-id="bd52a-120">IM/Presence in Mobile Clients</span></span></p></li>
<li><p><span data-ttu-id="bd52a-121">在移动客户端中加入联机会议</span><span class="sxs-lookup"><span data-stu-id="bd52a-121">Join online meetings in Mobile clients</span></span></p>
<p><span data-ttu-id="bd52a-122">有关详细信息，请参阅<a href="lync-server-2013-deploying-mobility.md">在 Lync Server 2013 中部署移动</a>功能</span><span class="sxs-lookup"><span data-stu-id="bd52a-122">For more information, see <a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="bd52a-123">基于 Outlook 日历的忙/闲信息发布状态</span><span class="sxs-lookup"><span data-stu-id="bd52a-123">Publish status based on Outlook calendar free/busy information</span></span></p></li>
<li><p><span data-ttu-id="bd52a-124">通过统一联系人存储 (联系人列表) </span><span class="sxs-lookup"><span data-stu-id="bd52a-124">Contact List (via Unified Contact Store)</span></span></p>
<p><span data-ttu-id="bd52a-125">有关详细信息，请参阅 <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">配置 Microsoft Lync Server 2013 以使用统一的联系人存储库</a></span><span class="sxs-lookup"><span data-stu-id="bd52a-125">For more information, see <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Configuring Microsoft Lync Server 2013 to use the unified contact store</a></span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="bd52a-126">需要 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="bd52a-126">Requires Exchange 2013.</span></span><BR><span data-ttu-id="bd52a-127">Lync 2013 桌面客户端是必需的。</span><span class="sxs-lookup"><span data-stu-id="bd52a-127">A Lync 2013 desktop client is required.</span></span>


</div></li>
<li><p><span data-ttu-id="bd52a-128">Lync 2013 客户端和 Lync Web App 中的高分辨率联系人照片。</span><span class="sxs-lookup"><span data-stu-id="bd52a-128">High-resolution Contact Photo in Lync 2013 client and Lync Web App.</span></span></p>
<p><span data-ttu-id="bd52a-129">有关详细信息，请参阅 <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">在 Microsoft Lync Server 2013 中配置高分辨率照片的使用</a></span><span class="sxs-lookup"><span data-stu-id="bd52a-129">For more information, see <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</a></span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="bd52a-130">需要 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="bd52a-130">Requires Exchange 2013.</span></span>


</div></li>
<li><p><span data-ttu-id="bd52a-131">会议委派</span><span class="sxs-lookup"><span data-stu-id="bd52a-131">Meeting delegation</span></span></p>
<p><span data-ttu-id="bd52a-132">仅当两个用户在同一个林中托管联机，或者两者都驻留在本地时受支持。</span><span class="sxs-lookup"><span data-stu-id="bd52a-132">Supported only when both users are homed online in the same forest, or both are homed on-premises.</span></span></p></li>
<li><p><span data-ttu-id="bd52a-133">错过的对话历史记录和呼叫日志将写入用户的 exchange 邮箱</span><span class="sxs-lookup"><span data-stu-id="bd52a-133">Missed Conversations history and Call Logs are written to user’s exchange mailbox</span></span></p></li>
<li><p><span data-ttu-id="bd52a-134">将内容存档 (IM 和会议) 在 Exchange 中</span><span class="sxs-lookup"><span data-stu-id="bd52a-134">Archiving Content (IM and Meeting) in Exchange</span></span></p>
<p><span data-ttu-id="bd52a-135">有关详细信息，请参阅 <a href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 中存档的部署清单</a></span><span class="sxs-lookup"><span data-stu-id="bd52a-135">For more information, see <a href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</a></span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="bd52a-136">需要 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="bd52a-136">Requires Exchange 2013.</span></span>


</div></li>
<li><p><span data-ttu-id="bd52a-137">搜索存档的内容</span><span class="sxs-lookup"><span data-stu-id="bd52a-137">Search archived content</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="bd52a-138">需要 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="bd52a-138">Requires Exchange 2013.</span></span>


</div></li>
<li><p><span data-ttu-id="bd52a-139">语音邮件</span><span class="sxs-lookup"><span data-stu-id="bd52a-139">Voice mail</span></span></p>
<p><span data-ttu-id="bd52a-140">有关详细信息，请参阅 <a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">部署本地 EXCHANGE UM 以提供 Lync Server 2013 语音邮件</a></span><span class="sxs-lookup"><span data-stu-id="bd52a-140">For more information, see <a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail</a></span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="bd52a-141">Outlook 中的 IM/状态</span><span class="sxs-lookup"><span data-stu-id="bd52a-141">IM/Presence in Outlook</span></span></p>
<p><span data-ttu-id="bd52a-142">有关详细信息，请参阅 <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">配置本地 Lync Server 2013 与 Exchange Online 集成</a></span><span class="sxs-lookup"><span data-stu-id="bd52a-142">For more information, see <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuring on-premises Lync Server 2013 integration with Exchange Online</a></span></span></p></li>
<li><p><span data-ttu-id="bd52a-143">通过 Outlook 安排和加入联机会议</span><span class="sxs-lookup"><span data-stu-id="bd52a-143">Schedule and join online meeting through Outlook</span></span></p></li>
<li><p><span data-ttu-id="bd52a-144">OWA 中的 IM/状态</span><span class="sxs-lookup"><span data-stu-id="bd52a-144">IM/Presence in OWA</span></span></p>
<p><span data-ttu-id="bd52a-145">有关详细信息，请参阅 <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">配置本地 Lync Server 2013 与 Exchange Online 集成</a></span><span class="sxs-lookup"><span data-stu-id="bd52a-145">For more information, see <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuring on-premises Lync Server 2013 integration with Exchange Online</a></span></span></p></li>
<li><p><span data-ttu-id="bd52a-146">从 Outlook Web App 安排和加入联机会议</span><span class="sxs-lookup"><span data-stu-id="bd52a-146">Schedule and join online meeting from Outlook Web App</span></span></p>
<p><span data-ttu-id="bd52a-147">有关详细信息，请参阅 <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">配置本地 Lync Server 2013 与 Exchange Online 集成</a></span><span class="sxs-lookup"><span data-stu-id="bd52a-147">For more information, see <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuring on-premises Lync Server 2013 integration with Exchange Online</a></span></span></p></li>
<li><p><span data-ttu-id="bd52a-148">移动客户端中的 IM/状态</span><span class="sxs-lookup"><span data-stu-id="bd52a-148">IM/Presence in Mobile Clients</span></span></p></li>
<li><p><span data-ttu-id="bd52a-149">在移动客户端中加入联机会议</span><span class="sxs-lookup"><span data-stu-id="bd52a-149">Join online meeting in Mobile clients</span></span></p></li>
<li><p><span data-ttu-id="bd52a-150">基于 Outlook 日历的忙/闲信息发布状态</span><span class="sxs-lookup"><span data-stu-id="bd52a-150">Publish status based on Outlook calendar free/busy information</span></span></p></li>
<li><p><span data-ttu-id="bd52a-151">通过统一联系人存储)  (联系人列表。</span><span class="sxs-lookup"><span data-stu-id="bd52a-151">Contact List (via Unified Contact Store).</span></span> <span data-ttu-id="bd52a-152">有关详细信息，请参阅 <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">配置 Microsoft Lync Server 2013 以使用统一的联系人存储库</a></span><span class="sxs-lookup"><span data-stu-id="bd52a-152">For more information, see <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Configuring Microsoft Lync Server 2013 to use the unified contact store</a></span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="bd52a-153">仅限 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="bd52a-153">Lync Server 2013 only.</span></span> <span data-ttu-id="bd52a-154">Lync 2013 桌面客户端是必需的。</span><span class="sxs-lookup"><span data-stu-id="bd52a-154">A Lync 2013 desktop client is required.</span></span>


</div></li>
<li><p><span data-ttu-id="bd52a-155">Lync 2013 客户端和 Lync Web App 中的高分辨率联系人照片。</span><span class="sxs-lookup"><span data-stu-id="bd52a-155">High-resolution Contact Photo in Lync 2013 client and Lync Web App.</span></span></p>
<p><span data-ttu-id="bd52a-156">有关详细信息，请参阅 <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">在 Microsoft Lync Server 2013 中配置高分辨率照片的使用</a>。</span><span class="sxs-lookup"><span data-stu-id="bd52a-156">For more information, see <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</a>.</span></span></p></li>
<li><p><span data-ttu-id="bd52a-157">会议委派</span><span class="sxs-lookup"><span data-stu-id="bd52a-157">Meeting delegation</span></span></p>
<p><span data-ttu-id="bd52a-158">仅当两个用户在同一个林中托管联机，或者两者都驻留在本地时受支持。</span><span class="sxs-lookup"><span data-stu-id="bd52a-158">Supported only when both users are homed online in the same forest, or both are homed on-premises.</span></span></p></li>
<li><p><span data-ttu-id="bd52a-159">错过的对话历史记录和呼叫日志将写入用户的 exchange 邮箱</span><span class="sxs-lookup"><span data-stu-id="bd52a-159">Missed Conversations history and Call Logs are written to user’s exchange mailbox</span></span></p></li>
<li><p><span data-ttu-id="bd52a-160">将内容存档 (IM 和会议) 在 Exchange 中。</span><span class="sxs-lookup"><span data-stu-id="bd52a-160">Archiving Content (IM and Meeting) in Exchange.</span></span></p>
<p><span data-ttu-id="bd52a-161">有关详细信息，请参阅 <a href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 中存档的部署清单</a></span><span class="sxs-lookup"><span data-stu-id="bd52a-161">For more information, see <a href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="bd52a-162">搜索存档的内容。</span><span class="sxs-lookup"><span data-stu-id="bd52a-162">Search archived content.</span></span> <span data-ttu-id="bd52a-163">有关详细信息，请参阅 <a href="https://go.microsoft.com/fwlink/p/?linkid=285448">Configure Exchange For SharePoint 电子数据展示中心</a></span><span class="sxs-lookup"><span data-stu-id="bd52a-163">For more information, see at <a href="https://go.microsoft.com/fwlink/p/?linkid=285448">Configure Exchange for SharePoint eDiscovery Center</a></span></span></p></li>
<li><p><span data-ttu-id="bd52a-164">语音邮件。</span><span class="sxs-lookup"><span data-stu-id="bd52a-164">Voice mail.</span></span> <span data-ttu-id="bd52a-165">有关详细信息，请参阅 <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">在托管 EXCHANGE UM 上提供 Lync Server 2013 用户语音邮件</a></span><span class="sxs-lookup"><span data-stu-id="bd52a-165">For more information, see <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">Providing Lync Server 2013 users voice mail on hosted Exchange UM</a></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd52a-166"><strong>Lync Online</strong></span><span class="sxs-lookup"><span data-stu-id="bd52a-166"><strong>Lync Online</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="bd52a-167">Outlook 中的 IM 和状态</span><span class="sxs-lookup"><span data-stu-id="bd52a-167">IM and Presence in Outlook</span></span></p></li>
<li><p><span data-ttu-id="bd52a-168">通过 Outlook 安排和加入联机会议</span><span class="sxs-lookup"><span data-stu-id="bd52a-168">Schedule and join online meetings through Outlook</span></span></p></li>
<li><p><span data-ttu-id="bd52a-169">移动客户端中的 IM/状态</span><span class="sxs-lookup"><span data-stu-id="bd52a-169">IM/Presence in Mobile clients</span></span></p></li>
<li><p><span data-ttu-id="bd52a-170">错过的对话历史记录和呼叫日志将写入用户的 exchange 邮箱</span><span class="sxs-lookup"><span data-stu-id="bd52a-170">Missed Conversations history and Call Logs are written to user’s exchange mailbox</span></span></p></li>
<li><p><span data-ttu-id="bd52a-171">Lync 2013 客户端中的高分辨率联系人照片。</span><span class="sxs-lookup"><span data-stu-id="bd52a-171">High-resolution Contact Photo in Lync 2013 client.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="bd52a-172">需要 Microsoft Exchange Server 2013。</span><span class="sxs-lookup"><span data-stu-id="bd52a-172">Requires Microsoft Exchange Server 2013.</span></span> <span data-ttu-id="bd52a-173">当用户托管在 Skype for Business Online 中时，Lync Web App 不支持此项。</span><span class="sxs-lookup"><span data-stu-id="bd52a-173">This is not supported in Lync Web App when users are homed on Skype for Business Online.</span></span>


</div></li>
<li><p><span data-ttu-id="bd52a-174">在移动客户端中加入联机会议</span><span class="sxs-lookup"><span data-stu-id="bd52a-174">Join online meeting in Mobile clients</span></span></p></li>
<li><p><span data-ttu-id="bd52a-175">基于 Outlook 日历的忙/闲信息发布状态</span><span class="sxs-lookup"><span data-stu-id="bd52a-175">Publish status based on Outlook calendar free/busy information</span></span></p></li>
<li><p><span data-ttu-id="bd52a-176">会议委派</span><span class="sxs-lookup"><span data-stu-id="bd52a-176">Meeting delegation</span></span></p>
<p><span data-ttu-id="bd52a-177">仅当两个用户在同一个林中托管联机，或者两者都驻留在本地时受支持。</span><span class="sxs-lookup"><span data-stu-id="bd52a-177">Supported only when both users are homed online in the same forest, or both are homed on-premises.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="bd52a-178">Outlook 中的 IM/状态</span><span class="sxs-lookup"><span data-stu-id="bd52a-178">IM/Presence in Outlook</span></span></p></li>
<li><p><span data-ttu-id="bd52a-179">通过 Outlook 安排和加入联机会议</span><span class="sxs-lookup"><span data-stu-id="bd52a-179">Schedule and join online meetings through Outlook</span></span></p></li>
<li><p><span data-ttu-id="bd52a-180">Outlook Web App 中的 IM/状态</span><span class="sxs-lookup"><span data-stu-id="bd52a-180">IM/Presence in Outlook Web App</span></span></p></li>
<li><p><span data-ttu-id="bd52a-181">从 Outlook Web App 安排和加入联机会议</span><span class="sxs-lookup"><span data-stu-id="bd52a-181">Schedule and join online meeting from Outlook Web App</span></span></p></li>
<li><p><span data-ttu-id="bd52a-182">移动客户端中的 IM/状态</span><span class="sxs-lookup"><span data-stu-id="bd52a-182">IM/Presence in Mobile Clients</span></span></p></li>
<li><p><span data-ttu-id="bd52a-183">在移动客户端中加入联机会议</span><span class="sxs-lookup"><span data-stu-id="bd52a-183">Join online meeting in Mobile clients</span></span></p></li>
<li><p><span data-ttu-id="bd52a-184">基于 Outlook 日历的忙/闲信息发布状态</span><span class="sxs-lookup"><span data-stu-id="bd52a-184">Publish status based on Outlook calendar free/busy information</span></span></p></li>
<li><p><span data-ttu-id="bd52a-185">错过的对话历史记录和呼叫日志将写入用户的 exchange 邮箱</span><span class="sxs-lookup"><span data-stu-id="bd52a-185">Missed Conversations history and Call Logs are written to user’s exchange mailbox</span></span></p></li>
<li><p><span data-ttu-id="bd52a-186">通过统一联系人存储 (联系人列表) </span><span class="sxs-lookup"><span data-stu-id="bd52a-186">Contact List (via Unified Contact Store)</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="bd52a-187">Lync Server 2013 客户端必需</span><span class="sxs-lookup"><span data-stu-id="bd52a-187">Lync Server 2013 client Required</span></span>


</div></li>
<li><p><span data-ttu-id="bd52a-188">Lync 2013 客户端和 Lync Web App 中的高分辨率联系人照片</span><span class="sxs-lookup"><span data-stu-id="bd52a-188">High-resolution Contact Photo in Lync 2013 client and Lync Web App</span></span></p></li>
<li><p><span data-ttu-id="bd52a-189">会议委派</span><span class="sxs-lookup"><span data-stu-id="bd52a-189">Meeting delegation</span></span></p>
<p><span data-ttu-id="bd52a-190">仅当两个用户在同一个林中托管联机，或者两者都驻留在本地时受支持。</span><span class="sxs-lookup"><span data-stu-id="bd52a-190">Supported only when both users are homed online in the same forest, or both are homed on-premises.</span></span></p></li>
<li><p><span data-ttu-id="bd52a-191">将内容存档 (IM 和会议) 在 Exchange 中</span><span class="sxs-lookup"><span data-stu-id="bd52a-191">Archiving Content (IM and Meeting) in Exchange</span></span></p></li>
<li><p><span data-ttu-id="bd52a-192">搜索存档的内容</span><span class="sxs-lookup"><span data-stu-id="bd52a-192">Search archived content</span></span></p></li>
<li><p><span data-ttu-id="bd52a-193">语音邮件</span><span class="sxs-lookup"><span data-stu-id="bd52a-193">Voicemail</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="integration-with-sharepoint"></a><span data-ttu-id="bd52a-194">与 SharePoint 集成</span><span class="sxs-lookup"><span data-stu-id="bd52a-194">Integration with SharePoint</span></span>

<span data-ttu-id="bd52a-195">下表列出了在与 SharePoint 集成时 Lync Server 2013 混合部署中支持的功能。</span><span class="sxs-lookup"><span data-stu-id="bd52a-195">The following table lists the features supported in a Lync Server 2013 hybrid deployment when integrated with SharePoint.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="bd52a-196">SharePoint 本地部署</span><span class="sxs-lookup"><span data-stu-id="bd52a-196">SharePoint on-premises</span></span></th>
<th><span data-ttu-id="bd52a-197">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bd52a-197">SharePoint Online</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd52a-198"><strong>Lync Server 2013 本地</strong></span><span class="sxs-lookup"><span data-stu-id="bd52a-198"><strong>Lync Server 2013 on-premises</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="bd52a-199">技能搜索</span><span class="sxs-lookup"><span data-stu-id="bd52a-199">Skills search</span></span></p></li>
<li><p><span data-ttu-id="bd52a-200">SharePoint 中的状态</span><span class="sxs-lookup"><span data-stu-id="bd52a-200">Presence in SharePoint</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="bd52a-201">SharePoint 中的状态</span><span class="sxs-lookup"><span data-stu-id="bd52a-201">Presence in SharePoint</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd52a-202"><strong>Lync Online</strong></span><span class="sxs-lookup"><span data-stu-id="bd52a-202"><strong>Lync Online</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="bd52a-203">SharePoint 中的状态</span><span class="sxs-lookup"><span data-stu-id="bd52a-203">Presence in SharePoint</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="bd52a-204">SharePoint 中的状态</span><span class="sxs-lookup"><span data-stu-id="bd52a-204">Presence in SharePoint</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

