---
title: Lync Server 2013 支持公共即时消息连接
description: Lync Server 2013 支持公共即时消息连接。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for public instant messenger connectivity
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59170234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4a58d71eb23012da960cf4505f1a55fd08df32c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573248"
---
# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a><span data-ttu-id="3874c-103">Lync Server 2013 中的公共即时消息连接支持</span><span class="sxs-lookup"><span data-stu-id="3874c-103">Support for public instant messenger connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3874c-104">_**上次修改的主题：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="3874c-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a><span data-ttu-id="3874c-105">对公共即时消息连接的支持</span><span class="sxs-lookup"><span data-stu-id="3874c-105">Support for Public Instant Messenger Connectivity</span></span>

<span data-ttu-id="3874c-106">本文提供了有关 (PIC) 的公共 IM 连接支持的信息。</span><span class="sxs-lookup"><span data-stu-id="3874c-106">This article provides information about support for Public IM Connectivity (PIC).</span></span> <span data-ttu-id="3874c-107">PIC 是 Microsoft Lync 的一项功能，它允许组织使其 Lync 用户能够通过其 Lync 客户端和标识与特定的公共即时消息 (IM) 服务的用户进行连接。</span><span class="sxs-lookup"><span data-stu-id="3874c-107">PIC is a feature of Microsoft Lync that allows organizations to enable their Lync users to connect with users of certain public instant messaging (IM) services through their Lync clients and identities.</span></span>

<span data-ttu-id="3874c-108">最终用户可以在其条款中与客户、合作伙伴和供应商联系，从而获益。</span><span class="sxs-lookup"><span data-stu-id="3874c-108">End-users benefit from being able to connect with customers, partners, and vendors on their terms.</span></span> <span data-ttu-id="3874c-109">通过支持单个实时通信客户端，同时保持 Lync 的控制、合规性和存档功能，提供了 IT 优势。</span><span class="sxs-lookup"><span data-stu-id="3874c-109">IT benefits from supporting a single real-time communications client while maintaining the control, compliance, and archiving features of Lync.</span></span> <span data-ttu-id="3874c-110">Lync-Skype 互连 [在5月2013的公开提供](https://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx)，依赖旧版的 Lync/Office 通信服务器 (OCS) /Live 通信服务器 (LCS) 首先与 PIC 建立与 MSN/Windows LIVE、AOL 和 Yahoo 的连接。</span><span class="sxs-lookup"><span data-stu-id="3874c-110">Lync-Skype connectivity, [publicly available in May 2013](https://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), relies on the legacy that Lync/Office Communications Server (OCS)/Live Communications Server (LCS) first established with PIC in connecting to MSN/Windows Live, AOL, and Yahoo.</span></span><span data-ttu-id="3874c-111">有关 Lync-Skype 连接性的详细信息，请参阅 [Lync-Skype 连接](https://office.microsoft.com/lync/lync-skype-connectivity-fx103789635.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3874c-111">  For more information on Lync-Skype connectivity, see the [Lync-Skype connectivity](https://office.microsoft.com/lync/lync-skype-connectivity-fx103789635.aspx).</span></span> <span data-ttu-id="3874c-112">与 Windows Live、AOL 和 Yahoo 的联盟都在路径上朝向生命期结束。</span><span class="sxs-lookup"><span data-stu-id="3874c-112">Federation with Windows Live, AOL, and Yahoo are each on a path towards end-of-life.</span></span><span data-ttu-id="3874c-113">此页面记录每个服务的状态。</span><span class="sxs-lookup"><span data-stu-id="3874c-113"> This page documents the status of each service.</span></span>

<span data-ttu-id="3874c-114">若要使用 PIC，客户需要为每个公共 IM 服务提供商激活服务。</span><span class="sxs-lookup"><span data-stu-id="3874c-114">To use PIC, customers have been required to activate the service for each public IM service provider.</span></span> <span data-ttu-id="3874c-115">有关如何执行此操作的要求和详细信息取决于 IM 服务提供商和客户的基础许可计划。</span><span class="sxs-lookup"><span data-stu-id="3874c-115">The requirements and details for how to do this are dependent upon the IM service provider and the customer's underlying licensing program.</span></span>

<div>

## <a name="windows-live-messenger"></a><span data-ttu-id="3874c-116">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="3874c-116">Windows Live Messenger</span></span>

<span data-ttu-id="3874c-117">Microsoft 将 Windows Live Messenger 和 Skype 放在一起。</span><span class="sxs-lookup"><span data-stu-id="3874c-117">Microsoft brought Windows Live Messenger and Skype together.</span></span> <span data-ttu-id="3874c-118">在4月2013，信使用户在登录时迁移到 Skype。</span><span class="sxs-lookup"><span data-stu-id="3874c-118">In April 2013, Messenger users were migrated to Skype upon sign-in.</span></span> <span data-ttu-id="3874c-119">依赖联盟和 Messenger 的 Lync 客户将继续能够与其 Messenger 联系人通信，即使这些联系人更新到 Skype 也是如此。</span><span class="sxs-lookup"><span data-stu-id="3874c-119">Lync customers who rely on federation with Messenger will continue to be able to communicate with their Messenger contacts, even after those contacts update to Skype.</span></span> <span data-ttu-id="3874c-120">Lync 管理员或 Lync 最终用户不需要执行此操作来维护服务的连续性，并且 Lync 中的此功能的管理仍保持不变，与信使通信一样。</span><span class="sxs-lookup"><span data-stu-id="3874c-120">There is nothing that Lync administrators or Lync end-users need to do to maintain continuity of service, and management of this capability within Lync remains the same as it has been for communications with Messenger.</span></span> 

<span data-ttu-id="3874c-121">当 Messenger 用户使用其 Microsoft 帐户登录到 Skype 时 (也就是说，用于 Messenger 的相同凭据) 其所有 Messenger 联系人-包括联合 Lync 联系人-将其添加到 Skype 中。</span><span class="sxs-lookup"><span data-stu-id="3874c-121">When Messenger users sign into Skype using their Microsoft accounts (i.e., the same credentials used for Messenger) all of their Messenger contacts - including federated Lync contacts - follow them into Skype.</span></span> <span data-ttu-id="3874c-122">这些联系人的 Skype 和 Lync 之间的状态共享和即时消息可用。</span><span class="sxs-lookup"><span data-stu-id="3874c-122">Presence sharing and instant messaging between Skype and Lync for these contacts is available.</span></span> 

<span data-ttu-id="3874c-123">Lync-Skype 连接-联系人在 Lync 和 Skype 用户之间添加、状态共享、即时消息和音频呼叫-现在也适用于所有 Lync 客户。</span><span class="sxs-lookup"><span data-stu-id="3874c-123">Lync-Skype connectivity - contact adding, presence sharing, instant messaging, and audio calling between Lync and Skype users - is also now available to all Lync customers.</span></span>

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a><span data-ttu-id="3874c-124">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="3874c-124">Yahoo\!</span></span> <span data-ttu-id="3874c-125">和 AOL 即时信使</span><span class="sxs-lookup"><span data-stu-id="3874c-125">and AOL Instant Messenger</span></span>

<span data-ttu-id="3874c-126">与 Yahoo 的联盟\!</span><span class="sxs-lookup"><span data-stu-id="3874c-126">Federation with Yahoo\!</span></span> <span data-ttu-id="3874c-127">AOL (和 Office 通信服务器) 的客户在使用寿命结束的路径上。</span><span class="sxs-lookup"><span data-stu-id="3874c-127">and AOL are both on a path toward end-of-life for customers of Lync (and Office Communications Server).</span></span> <span data-ttu-id="3874c-128">Microsoft 提供每项服务的能力因 Yahoo 的支持而受到\!</span><span class="sxs-lookup"><span data-stu-id="3874c-128">Microsoft’s ability to provide each of these services has been contingent upon support from Yahoo\!</span></span> <span data-ttu-id="3874c-129">和 AOL 以及这些条款的底层协议将向下缠绕。</span><span class="sxs-lookup"><span data-stu-id="3874c-129">and AOL, and the underlying agreements of these are winding down.</span></span> <span data-ttu-id="3874c-130">对于这两个 Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="3874c-130">For both Yahoo\!</span></span> <span data-ttu-id="3874c-131">和 AOL，服务将继续到2014年6月。</span><span class="sxs-lookup"><span data-stu-id="3874c-131">and AOL, service will continue through June 2014.</span></span>

  - <span data-ttu-id="3874c-132">**Yahoo** -服务将持续到2014年6月，客户继续需要使用 Microsoft LYNC 公共 IM 连接用户订阅许可证 ( "PIC USL" ) 获得许可。</span><span class="sxs-lookup"><span data-stu-id="3874c-132">**Yahoo** - Service will continue through June 2014, and customers continue to need to be licensed with the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”).</span></span><span data-ttu-id="3874c-133">从9月1日起，2012，PIC USL 不再可用于购买新的或续订的协议。</span><span class="sxs-lookup"><span data-stu-id="3874c-133">  As of September 1st, 2012, the PIC USL, is no longer available for purchase for new or renewing agreements.</span></span><span data-ttu-id="3874c-134">在此日期之前购买许可证的客户将能够继续与 Yahoo 进行联盟\!</span><span class="sxs-lookup"><span data-stu-id="3874c-134">  Customers with licenses purchased prior to this date will be able to continue to federate with Yahoo\!</span></span> <span data-ttu-id="3874c-135">在之前的服务关闭日期或其许可证过期之前。</span><span class="sxs-lookup"><span data-stu-id="3874c-135">until the earlier of the service shut down date or their license expiration.</span></span><span data-ttu-id="3874c-136">阅读 Lync 团队博客上 [的通知](https://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="3874c-136"> Read [the announcement](https://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) on the Lync Team Blog.</span></span><span data-ttu-id="3874c-137">如果客户的许可证的使用期限在6月30日之前延长的协议，则2014将按与支付30年6月 30 2014 日之后的时间段的付款金额成比例显示积分。</span><span class="sxs-lookup"><span data-stu-id="3874c-137"> Customers who have PIC licenses on agreements that extend past June 30, 2014 will receive a credit in proportion to the amount of the payments covering the time period following June 30, 2014.</span></span>

  - <span data-ttu-id="3874c-138">**AOL** -在2014年6月30日，LYNC 的 IM 连接 ( "PIC" ) 服务将不再可用。</span><span class="sxs-lookup"><span data-stu-id="3874c-138">**AOL** - On June 30, 2014, Lync's IM connectivity ("PIC") service will no longer be available.</span></span><span data-ttu-id="3874c-139">为了在服务结束时限制客户的中断，我们已停止对其他客户域的设置。</span><span class="sxs-lookup"><span data-stu-id="3874c-139"> In order to limit customer disruption when the service ends, we have discontinued the provisioning of additional customer domains.</span></span> <span data-ttu-id="3874c-140">在2014年6月30日之前，客户无需执行任何操作即可继续支持与 AIM 的联合通信。</span><span class="sxs-lookup"><span data-stu-id="3874c-140">Until June 30, 2014, customers do not need to do anything to continue to support federated communications with AIM.</span></span> <span data-ttu-id="3874c-141">除了此日期 (或对于想要在同一时间内预配其他域的客户) ，可直接从 AOL 获取替代服务。</span><span class="sxs-lookup"><span data-stu-id="3874c-141">Beyond this date (or for customers that would like to provision additional domains in the meantime), a substitute service is available directly from AOL.</span></span> <span data-ttu-id="3874c-142">有关 AOL 新服务的详细信息，请参阅[使用 AIM 建立直接联盟](http://aimenterprise.aol.com/pic.php)    (在 AOL.com) 上打开新页面。</span><span class="sxs-lookup"><span data-stu-id="3874c-142">For more information on AOL's new service, see [Establishing Direct Federation with AIM](http://aimenterprise.aol.com/pic.php)  (opens new page on AOL.com).</span></span>  

</div>

<div>

## <a name="public-im-provider-summary"></a><span data-ttu-id="3874c-143">公共 IM 提供商摘要</span><span class="sxs-lookup"><span data-stu-id="3874c-143">Public IM Provider Summary</span></span>

<span data-ttu-id="3874c-144">下表提供了公用 IM 服务提供商的摘要、与 Lync 的联合功能以及许可要求。</span><span class="sxs-lookup"><span data-stu-id="3874c-144">The following table provides a summary of the Public IM service providers, federation capabilities with Lync, and licensing requirements.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3874c-145">公共 IM 服务提供商</span><span class="sxs-lookup"><span data-stu-id="3874c-145">Public IM Service Provider</span></span></th>
<th><span data-ttu-id="3874c-146">联合功能</span><span class="sxs-lookup"><span data-stu-id="3874c-146">Federated Capabilities</span></span></th>
<th><span data-ttu-id="3874c-147">许可要求</span><span class="sxs-lookup"><span data-stu-id="3874c-147">Licensing Requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3874c-148">Skype</span><span class="sxs-lookup"><span data-stu-id="3874c-148">Skype</span></span></p></td>
<td><p><span data-ttu-id="3874c-149">即时消息、状态、音频</span><span class="sxs-lookup"><span data-stu-id="3874c-149">IM, Presence, Audio</span></span></p></td>
<td><p><span data-ttu-id="3874c-150">Lync Server 客户端访问许可证，Lync Online 计划1/2/3</span><span class="sxs-lookup"><span data-stu-id="3874c-150">Lync Server Client Access Licenses, Lync Online Plan 1/2/3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3874c-151">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="3874c-151">Windows Live Messenger</span></span></p></td>
<td><p><span data-ttu-id="3874c-152">即时消息、状态、音频/视频</span><span class="sxs-lookup"><span data-stu-id="3874c-152">IM, Presence, Audio/Video</span></span></p></td>
<td><p><span data-ttu-id="3874c-153"> (支持 Lync Server 客户端访问许可证，只要 WLM 处于市场) </span><span class="sxs-lookup"><span data-stu-id="3874c-153">Lync Server Client Access Licenses (supported as long as WLM is in market)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3874c-154">寻求</span><span class="sxs-lookup"><span data-stu-id="3874c-154">AOL</span></span></p></td>
<td><p><span data-ttu-id="3874c-155">即时消息、状态</span><span class="sxs-lookup"><span data-stu-id="3874c-155">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="3874c-156">Lync Server 客户端访问许可证;为现有客户提供6月2014的支持。</span><span class="sxs-lookup"><span data-stu-id="3874c-156">Lync Server Client Access Licenses; supported through June 2014 for existing customers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3874c-157">Yahoo！</span><span class="sxs-lookup"><span data-stu-id="3874c-157">Yahoo!</span></span></p></td>
<td><p><span data-ttu-id="3874c-158">即时消息、状态</span><span class="sxs-lookup"><span data-stu-id="3874c-158">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="3874c-159">除了 Lync Server 客户端访问许可外，还需要其他 Microsoft Lync 公共 IM 连接用户订阅许可证 ( "PIC USL" ) 。</span><span class="sxs-lookup"><span data-stu-id="3874c-159">Requires additional Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) in addition to Lync Server Client Access Licences.</span></span> <span data-ttu-id="3874c-160">从2012年9月发布的价目表中，PIC USL 无法再用于购买。</span><span class="sxs-lookup"><span data-stu-id="3874c-160">As of the September 2012 Price List, the PIC USL is no longer available for purchase.</span></span> <span data-ttu-id="3874c-161">具有有效许可证的客户可以继续与 Yahoo！联合</span><span class="sxs-lookup"><span data-stu-id="3874c-161">Customers with active licenses are able to continue to federate with Yahoo!</span></span> <span data-ttu-id="3874c-162">在2014年6月30日的服务关闭前，一直向信使。</span><span class="sxs-lookup"><span data-stu-id="3874c-162">Messenger until the service shut down date on June 30, 2014.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

