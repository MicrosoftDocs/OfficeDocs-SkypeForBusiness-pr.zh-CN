---
title: Lync Server 2013：准备和部署 Lync Server 混合环境的步骤
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Steps to prepare and deploy Lync Server 2013 hybrid environment
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205157(v=OCS.15)
ms:contentKeyID: 48185060
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3326db7ce62279c4295bc13ec262a5a553ca5e62
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="steps-to-prepare-and-deploy-lync-server-2013-hybrid-environment"></a><span data-ttu-id="b2c9f-102">准备和部署 Lync Server 2013 混合环境的步骤</span><span class="sxs-lookup"><span data-stu-id="b2c9f-102">Steps to prepare and deploy Lync Server 2013 hybrid environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2c9f-103">_**上次修改的主题：** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="b2c9f-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="b2c9f-104">下表列出了为具有 Skype for Business Online 和 Microsoft Office 365 的混合部署准备环境所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="b2c9f-104">The following table lists the steps required to prepare your environment for a hybrid deployment with Skype for Business Online and Microsoft Office 365.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2c9f-105">已完成？</span><span class="sxs-lookup"><span data-stu-id="b2c9f-105">Completed?</span></span></th>
<th><span data-ttu-id="b2c9f-106">步骤</span><span class="sxs-lookup"><span data-stu-id="b2c9f-106">Step</span></span></th>
<th><span data-ttu-id="b2c9f-107">说明</span><span class="sxs-lookup"><span data-stu-id="b2c9f-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="b2c9f-108">为 Office 365 创建租户帐户并启用 Lync Online</span><span class="sxs-lookup"><span data-stu-id="b2c9f-108">Create a tenant account for Office 365 and enable Lync Online</span></span></p></td>
<td><p><span data-ttu-id="b2c9f-109">了解 office 365 和 Lync Online （位于<a href="https://go.microsoft.com/fwlink/p/?linkid=254980">office 365</a>）。</span><span class="sxs-lookup"><span data-stu-id="b2c9f-109">Learn about Office 365 and Lync Online at <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">Office 365</a>.</span></span></p>
<p><span data-ttu-id="b2c9f-110">若要确保你的环境已准备好适用于 Office 365，请参阅<a href="https://go.microsoft.com/fwlink/p/?linkid=401408">系统要求</a>。</span><span class="sxs-lookup"><span data-stu-id="b2c9f-110">To make sure that your environment is ready for Office 365, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">System Requirements</a>.</span></span></p>
<p><span data-ttu-id="b2c9f-111">有关设置 Office 365 的详细信息，请参阅<a href="https://go.microsoft.com/fwlink/p/?linkid=254982">office 365 入门</a>和<a href="http://go.microsoft.com/fwlink/p/?linkid=254979">设置 Office 365</a>。</span><span class="sxs-lookup"><span data-stu-id="b2c9f-111">For details about setting up Office 365, see <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">Getting Started with Office 365</a> and <a href="http://go.microsoft.com/fwlink/p/?linkid=254979">Set Up Office 365</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="b2c9f-112">添加域并验证所有权</span><span class="sxs-lookup"><span data-stu-id="b2c9f-112">Add your domain and verify ownership</span></span></p></td>
<td><p><span data-ttu-id="b2c9f-113">有时，您的域也称为您的<em>虚域</em>。</span><span class="sxs-lookup"><span data-stu-id="b2c9f-113">Your domain is sometimes also referred to as your <em>vanity domain</em>.</span></span> <span data-ttu-id="b2c9f-114">您必须将您的域添加到 Office 365 租户，然后按照这些步骤使用 Office 365 验证域。</span><span class="sxs-lookup"><span data-stu-id="b2c9f-114">You must add your domain to your Office 365 tenant, and then follow the steps to validate the domain with Office 365.</span></span> <span data-ttu-id="b2c9f-115">这是为了确认您是域的所有者。</span><span class="sxs-lookup"><span data-stu-id="b2c9f-115">This is to confirm that you are the owner of the domain.</span></span></p>
<p><span data-ttu-id="b2c9f-116">若要将你的域添加到 Office 365 租户，请按照<a href="https://go.microsoft.com/fwlink/p/?linkid=254983">将域添加到 office 365</a>中所述的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="b2c9f-116">To add your domain to your Office 365 tenant, follow the steps described at <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">Add your domain to Office 365</a>.</span></span></p>
<p><span data-ttu-id="b2c9f-117">完成主题的每一节中的所有步骤，包括&quot;编辑 Office 365 服务的 DNS 记录。&quot;</span><span class="sxs-lookup"><span data-stu-id="b2c9f-117">Complete all of the steps in each section in the topic, including &quot;Edit DNS records for your Office 365 services.&quot;</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="b2c9f-118">确认环境准备就绪</span><span class="sxs-lookup"><span data-stu-id="b2c9f-118">Verify environment readiness</span></span></p></td>
<td><p><span data-ttu-id="b2c9f-119">您可以使用 Office 365 安装助理来帮助您部署 Office 365。</span><span class="sxs-lookup"><span data-stu-id="b2c9f-119">You can use the Office 365 Setup Assistant to help you deploy Office 365.</span></span> <span data-ttu-id="b2c9f-120">有关详细信息，请参阅<a href="https://go.microsoft.com/fwlink/p/?linkid=254985">使用 Setup Assistant 确定 Office 365 就绪</a>状态。</span><span class="sxs-lookup"><span data-stu-id="b2c9f-120">For more information, see <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">Use Setup Assistant to determine Office 365 readiness</a>.</span></span></p>
<p><span data-ttu-id="b2c9f-121">有关使用此工具和部署 Office 365 的详细信息，请参阅<a href="https://go.microsoft.com/fwlink/p/?linkid=257337">office 365 部署指南</a>。</span><span class="sxs-lookup"><span data-stu-id="b2c9f-121">For details about using the tool and deploying Office 365, see <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Office 365 deployment guide</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="b2c9f-122">准备 Active Directory 同步</span><span class="sxs-lookup"><span data-stu-id="b2c9f-122">Prepare for Active Directory synchronization</span></span></p></td>
<td><p><span data-ttu-id="b2c9f-123">Active Directory 同步可使您的本地 Active Directory 持续与 Office 365 保持同步。</span><span class="sxs-lookup"><span data-stu-id="b2c9f-123">Active Directory synchronization keeps your on-premises Active Directory continuously synchronized with Office 365.</span></span> <span data-ttu-id="b2c9f-124">这样，您就可以创建每个用户帐户和组的同步版本，也可以将全局地址列表（GAL）同步从您的本地 Microsoft Exchange Server 环境同步到 Microsoft Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="b2c9f-124">This lets you create synchronized versions of each user account and group, and also enables global address list (GAL) synchronization from your local Microsoft Exchange Server environment to Microsoft Exchange Online.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="b2c9f-125">您需要在内部部署和联机 Lync 部署之间同步组织中所有 Lync 用户的 AD 帐户，即使用户未移动到 Lync Online 也是如此。</span><span class="sxs-lookup"><span data-stu-id="b2c9f-125">You need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="b2c9f-126">如果不同步所有用户，组织中的内部部署用户和联机用户之间的通信可能无法按预期工作。</span><span class="sxs-lookup"><span data-stu-id="b2c9f-126">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>


</div>
<p><span data-ttu-id="b2c9f-127">若要为您的环境准备 Active Directory 同步，请按照<a href="https://go.microsoft.com/fwlink/p/?linkid=254988">目录同步路线图</a>中所述的步骤进行操作，包括设置单一登录。</span><span class="sxs-lookup"><span data-stu-id="b2c9f-127">To prepare your environment for Active Directory synchronization, follow the steps described in <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">Directory synchronization Roadmap</a>, including setting up single sign-on.</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="b2c9f-128">为 Active Directory 联合身份验证服务（AD FS）创建证书</span><span class="sxs-lookup"><span data-stu-id="b2c9f-128">Create certificates for Active Directory Federation Services (AD FS)</span></span></p></td>
<td><p><span data-ttu-id="b2c9f-129">您将需要创建用于与 Office 365 联合身份验证的证书。</span><span class="sxs-lookup"><span data-stu-id="b2c9f-129">You will need to create the certificates that are used for identity federation with Office 365.</span></span> <span data-ttu-id="b2c9f-130">有关详细信息，请参阅规划和部署 AD FS 以与单一登录主题一起使用的检查表中的 "联合身份验证服务器证书" 部分<a href="https://go.microsoft.com/fwlink/p/?linkid=285376">：使用 AD fs 实现和管理单一登录</a>。</span><span class="sxs-lookup"><span data-stu-id="b2c9f-130">For more information, see the “Federation server certificates” section of the Plan for and deploy AD FS for use with single sign-on topic at <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">Checklist: Use AD FS to implement and manage single sign-on</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="b2c9f-131">为 AD FS 分配证书</span><span class="sxs-lookup"><span data-stu-id="b2c9f-131">Assign certificates for AD FS</span></span></p></td>
<td><p><span data-ttu-id="b2c9f-132">在创建用于与 Office 365 联合身份验证的证书之后，您必须安装和分配这些证书。</span><span class="sxs-lookup"><span data-stu-id="b2c9f-132">After you create the certificates that are used for identity federation with Office 365, you must install and assign them.</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="b2c9f-133">将试点用户移动到 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b2c9f-133">Move pilot users to Skype for Business Online</span></span></p></td>
<td><p><span data-ttu-id="b2c9f-134">在完成了为 Skype for business Online 准备和配置环境的步骤之后，可以开始将试点用户移动到 Lync Online。</span><span class="sxs-lookup"><span data-stu-id="b2c9f-134">After you have completed the steps to prepare and configure your environment for Skype for Business Online, you can start moving pilot users to Lync Online.</span></span></p>
<p><span data-ttu-id="b2c9f-135">请参阅<a href="lync-server-2013-move-users-to-lync-online.md">Lync Server 2013 中的将用户移动到 Lync Online</a>。</span><span class="sxs-lookup"><span data-stu-id="b2c9f-135">See <a href="lync-server-2013-move-users-to-lync-online.md">Move users to Lync Online in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="b2c9f-136">在混合部署中管理用户</span><span class="sxs-lookup"><span data-stu-id="b2c9f-136">Administering users in a hybrid deployment</span></span></p></td>
<td><p><span data-ttu-id="b2c9f-137">有关如何在混合部署中管理用户的详细信息，请参阅<a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">在混合 Lync Server 2013 部署中管理用户</a>。</span><span class="sxs-lookup"><span data-stu-id="b2c9f-137">For details about how to administer users in a hybrid deployment, see <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

