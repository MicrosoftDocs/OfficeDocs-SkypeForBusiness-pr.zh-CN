---
title: Lync Server 2013：准备和部署 Lync Server 混合环境的步骤
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Steps to prepare and deploy Lync Server 2013 hybrid environment
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205157(v=OCS.15)
ms:contentKeyID: 48185060
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d239d7a57be1aa96dde1f9ccf30c2965de982017
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="steps-to-prepare-and-deploy-lync-server-2013-hybrid-environment"></a><span data-ttu-id="23e79-102">准备和部署 Lync Server 2013 混合环境的步骤</span><span class="sxs-lookup"><span data-stu-id="23e79-102">Steps to prepare and deploy Lync Server 2013 hybrid environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23e79-103">_**主题上次修改时间:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="23e79-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="23e79-104">下表列出了为具有 Skype for Business Online 和 Microsoft Office 365 的混合部署准备环境所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="23e79-104">The following table lists the steps required to prepare your environment for a hybrid deployment with Skype for Business Online and Microsoft Office 365.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23e79-105">已完成？</span><span class="sxs-lookup"><span data-stu-id="23e79-105">Completed?</span></span></th>
<th><span data-ttu-id="23e79-106">步骤</span><span class="sxs-lookup"><span data-stu-id="23e79-106">Step</span></span></th>
<th><span data-ttu-id="23e79-107">说明</span><span class="sxs-lookup"><span data-stu-id="23e79-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="23e79-108">创建 Office 365 的租户帐户并启用 Lync Online</span><span class="sxs-lookup"><span data-stu-id="23e79-108">Create a tenant account for Office 365 and enable Lync Online</span></span></p></td>
<td><p><span data-ttu-id="23e79-109">在<a href="https://go.microsoft.com/fwlink/p/?linkid=254980">office 365</a>中了解 office 365 和 Lync Online。</span><span class="sxs-lookup"><span data-stu-id="23e79-109">Learn about Office 365 and Lync Online at <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">Office 365</a>.</span></span></p>
<p><span data-ttu-id="23e79-110">若要确保你的环境已准备好用于 Office 365, 请参阅<a href="https://go.microsoft.com/fwlink/p/?linkid=401408">系统要求</a>。</span><span class="sxs-lookup"><span data-stu-id="23e79-110">To make sure that your environment is ready for Office 365, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">System Requirements</a>.</span></span></p>
<p><span data-ttu-id="23e79-111">有关设置 Office 365 的详细信息, 请参阅<a href="https://go.microsoft.com/fwlink/p/?linkid=254982">office 365 入门</a>和<a href="http://go.microsoft.com/fwlink/p/?linkid=254979">设置 office 365</a>。</span><span class="sxs-lookup"><span data-stu-id="23e79-111">For details about setting up Office 365, see <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">Getting Started with Office 365</a> and <a href="http://go.microsoft.com/fwlink/p/?linkid=254979">Set Up Office 365</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="23e79-112">添加域并验证所有权</span><span class="sxs-lookup"><span data-stu-id="23e79-112">Add your domain and verify ownership</span></span></p></td>
<td><p><span data-ttu-id="23e79-p101">您的域有时也称为 <em>虚域</em>。您必须将您的域添加到 Office 365 租户中，然后按照步骤在 Office 365 中验证域。这是为了确认您是域的所有者。</span><span class="sxs-lookup"><span data-stu-id="23e79-p101">Your domain is sometimes also referred to as your <em>vanity domain</em>. You must add your domain to your Office 365 tenant, and then follow the steps to validate the domain with Office 365. This is to confirm that you are the owner of the domain.</span></span></p>
<p><span data-ttu-id="23e79-116">若要将域添加到 Office 365 租户, 请按照<a href="https://go.microsoft.com/fwlink/p/?linkid=254983">将您的域添加到 office 365</a>中所述的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="23e79-116">To add your domain to your Office 365 tenant, follow the steps described at <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">Add your domain to Office 365</a>.</span></span></p>
<p><span data-ttu-id="23e79-117">完成主题的每个部分中的所有步骤, 包括&quot;编辑 Office 365 服务的 DNS 记录。&quot;</span><span class="sxs-lookup"><span data-stu-id="23e79-117">Complete all of the steps in each section in the topic, including &quot;Edit DNS records for your Office 365 services.&quot;</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="23e79-118">验证环境准备情况</span><span class="sxs-lookup"><span data-stu-id="23e79-118">Verify environment readiness</span></span></p></td>
<td><p><span data-ttu-id="23e79-119">您可以使用 Office 365 设置助理来帮助您部署 Office 365。</span><span class="sxs-lookup"><span data-stu-id="23e79-119">You can use the Office 365 Setup Assistant to help you deploy Office 365.</span></span> <span data-ttu-id="23e79-120">有关详细信息, 请参阅<a href="https://go.microsoft.com/fwlink/p/?linkid=254985">使用设置助理确定 Office 365 准备情况</a>。</span><span class="sxs-lookup"><span data-stu-id="23e79-120">For more information, see <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">Use Setup Assistant to determine Office 365 readiness</a>.</span></span></p>
<p><span data-ttu-id="23e79-121">有关使用工具和部署 Office 365 的详细信息, 请参阅<a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Office 365 部署指南</a>。</span><span class="sxs-lookup"><span data-stu-id="23e79-121">For details about using the tool and deploying Office 365, see <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Office 365 deployment guide</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="23e79-122">准备 Active Directory 同步</span><span class="sxs-lookup"><span data-stu-id="23e79-122">Prepare for Active Directory synchronization</span></span></p></td>
<td><p><span data-ttu-id="23e79-123">Active Directory 同步使你的本地 Active Directory 持续与 Office 365 保持同步。</span><span class="sxs-lookup"><span data-stu-id="23e79-123">Active Directory synchronization keeps your on-premises Active Directory continuously synchronized with Office 365.</span></span> <span data-ttu-id="23e79-124">这样，你可以创建每个用户帐户和组的同步版本，同时实现从本地 Microsoft Exchange Server 环境到 Microsoft Exchange Online 的全局地址列表 (GAL) 同步。</span><span class="sxs-lookup"><span data-stu-id="23e79-124">This lets you create synchronized versions of each user account and group, and also enables global address list (GAL) synchronization from your local Microsoft Exchange Server environment to Microsoft Exchange Online.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="23e79-125">您需要在本地和联机 Lync 部署之间同步组织中所有 Lync 用户的广告帐户, 即使用户未移动到 Lync Online 也是如此。</span><span class="sxs-lookup"><span data-stu-id="23e79-125">You need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="23e79-126">如果未同步所有用户，则组织中本地和联机用户之间的通信可能无法按预期工作。</span><span class="sxs-lookup"><span data-stu-id="23e79-126">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>


</div>
<p><span data-ttu-id="23e79-127">若要准备您的环境以进行 Active Directory 同步, 请按照<a href="https://go.microsoft.com/fwlink/p/?linkid=254988">目录同步路线图</a>中所述的步骤进行操作, 包括设置单一登录。</span><span class="sxs-lookup"><span data-stu-id="23e79-127">To prepare your environment for Active Directory synchronization, follow the steps described in <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">Directory synchronization Roadmap</a>, including setting up single sign-on.</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="23e79-128">为 Active Directory 联合身份验证服务 (AD FS) 创建证书</span><span class="sxs-lookup"><span data-stu-id="23e79-128">Create certificates for Active Directory Federation Services (AD FS)</span></span></p></td>
<td><p><span data-ttu-id="23e79-129">你将需要创建用于与 Office 365 的联合身份验证的证书。</span><span class="sxs-lookup"><span data-stu-id="23e79-129">You will need to create the certificates that are used for identity federation with Office 365.</span></span> <span data-ttu-id="23e79-130">有关详细信息, 请参阅计划的计划和部署 AD FS 的 "联合身份验证服务器证书" 部分, 以便与清单中的单一登录主题配合使用<a href="https://go.microsoft.com/fwlink/p/?linkid=285376">: 使用 AD FS 实施和管理单一登录</a>。</span><span class="sxs-lookup"><span data-stu-id="23e79-130">For more information, see the “Federation server certificates” section of the Plan for and deploy AD FS for use with single sign-on topic at <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">Checklist: Use AD FS to implement and manage single sign-on</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="23e79-131">为广告 FS 分配证书</span><span class="sxs-lookup"><span data-stu-id="23e79-131">Assign certificates for AD FS</span></span></p></td>
<td><p><span data-ttu-id="23e79-132">创建用于与 Office 365 联合身份验证的证书后, 必须安装和分配它们。</span><span class="sxs-lookup"><span data-stu-id="23e79-132">After you create the certificates that are used for identity federation with Office 365, you must install and assign them.</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="23e79-133">将试点用户移动到 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="23e79-133">Move pilot users to Skype for Business Online</span></span></p></td>
<td><p><span data-ttu-id="23e79-134">完成准备和配置 Skype for business Online 环境的步骤后, 您可以开始将试点用户移动到 Lync Online。</span><span class="sxs-lookup"><span data-stu-id="23e79-134">After you have completed the steps to prepare and configure your environment for Skype for Business Online, you can start moving pilot users to Lync Online.</span></span></p>
<p><span data-ttu-id="23e79-135">请参阅<a href="lync-server-2013-move-users-to-lync-online.md">在 Lync Server 2013 中将用户移动到 Lync Online</a>。</span><span class="sxs-lookup"><span data-stu-id="23e79-135">See <a href="lync-server-2013-move-users-to-lync-online.md">Move users to Lync Online in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="23e79-136">管理混合部署中的用户</span><span class="sxs-lookup"><span data-stu-id="23e79-136">Administering users in a hybrid deployment</span></span></p></td>
<td><p><span data-ttu-id="23e79-137">有关如何在混合部署中管理用户的详细信息, 请参阅<a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">管理混合 Lync Server 2013 部署中的用户</a>。</span><span class="sxs-lookup"><span data-stu-id="23e79-137">For details about how to administer users in a hybrid deployment, see <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

