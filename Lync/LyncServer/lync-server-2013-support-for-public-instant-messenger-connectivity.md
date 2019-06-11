---
title: Lync Server 2013 支持公共即时消息连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Support for public instant messenger connectivity
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59170234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c89cc911411095034385f7b8ebbe01edddcd20c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a><span data-ttu-id="75491-102">Lync Server 2013 中的公共即时消息连接支持</span><span class="sxs-lookup"><span data-stu-id="75491-102">Support for public instant messenger connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75491-103">_**主题上次修改时间:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="75491-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a><span data-ttu-id="75491-104">对公共即时消息连接的支持</span><span class="sxs-lookup"><span data-stu-id="75491-104">Support for Public Instant Messenger Connectivity</span></span>

<span data-ttu-id="75491-105">本文提供有关公共 IM 连接 (PIC) 的支持信息。</span><span class="sxs-lookup"><span data-stu-id="75491-105">This article provides information about support for Public IM Connectivity (PIC).</span></span> <span data-ttu-id="75491-106">PIC 是 Microsoft Lync 的一项功能, 允许组织使其 Lync 用户能够通过其 Lync 客户端和标识与特定公共即时消息 (IM) 服务的用户进行连接。</span><span class="sxs-lookup"><span data-stu-id="75491-106">PIC is a feature of Microsoft Lync that allows organizations to enable their Lync users to connect with users of certain public instant messaging (IM) services through their Lync clients and identities.</span></span>

<span data-ttu-id="75491-107">最终用户可以通过其条款与客户、合作伙伴和供应商联系, 从而获益。</span><span class="sxs-lookup"><span data-stu-id="75491-107">End-users benefit from being able to connect with customers, partners, and vendors on their terms.</span></span> <span data-ttu-id="75491-108">在保持 Lync 的控制、合规性和存档功能的同时支持单个实时通信客户端的好处。</span><span class="sxs-lookup"><span data-stu-id="75491-108">IT benefits from supporting a single real-time communications client while maintaining the control, compliance, and archiving features of Lync.</span></span> <span data-ttu-id="75491-109">Lync-Skype 连接 ([可在5月2013公开推出](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx)) 依赖于 Lync/Office 通信服务器 (OCS)/Live 通信服务器 (LCS), 该服务器首先在连接到 MSN/Windows LIVE、AOL 和 Yahoo 时与 PIC 建立的通信服务器 (LCS)。</span><span class="sxs-lookup"><span data-stu-id="75491-109">Lync-Skype connectivity, [publicly available in May 2013](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), relies on the legacy that Lync/Office Communications Server (OCS)/Live Communications Server (LCS) first established with PIC in connecting to MSN/Windows Live, AOL, and Yahoo.</span></span><span data-ttu-id="75491-110">有关 Lync-Skype 连接的详细信息, 请参阅[Lync-skype 连接](http://office.microsoft.com/en-us/lync/lync-skype-connectivity-fx103789635.aspx)。</span><span class="sxs-lookup"><span data-stu-id="75491-110">  For more information on Lync-Skype connectivity, see the [Lync-Skype connectivity](http://office.microsoft.com/en-us/lync/lync-skype-connectivity-fx103789635.aspx).</span></span> <span data-ttu-id="75491-111">与 Windows Live、AOL 和 Yahoo 的联盟, 每个都在一条路线上的生命周期结束。</span><span class="sxs-lookup"><span data-stu-id="75491-111">Federation with Windows Live, AOL, and Yahoo are each on a path towards end-of-life.</span></span><span data-ttu-id="75491-112">此页面记录每个服务的状态。</span><span class="sxs-lookup"><span data-stu-id="75491-112"> This page documents the status of each service.</span></span>

<span data-ttu-id="75491-113">若要使用 PIC, 客户必须为每个公共 IM 服务提供商激活该服务。</span><span class="sxs-lookup"><span data-stu-id="75491-113">To use PIC, customers have been required to activate the service for each public IM service provider.</span></span> <span data-ttu-id="75491-114">如何执行此操作的要求和详细信息取决于 IM 服务提供商和客户的基础许可计划。</span><span class="sxs-lookup"><span data-stu-id="75491-114">The requirements and details for how to do this are dependent upon the IM service provider and the customer's underlying licensing program.</span></span>

<div>

## <a name="windows-live-messenger"></a><span data-ttu-id="75491-115">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="75491-115">Windows Live Messenger</span></span>

<span data-ttu-id="75491-116">Microsoft 将 Windows Live Messenger 和 Skype 一起引入。</span><span class="sxs-lookup"><span data-stu-id="75491-116">Microsoft brought Windows Live Messenger and Skype together.</span></span> <span data-ttu-id="75491-117">2013年4月, 在登录时, Messenger 用户已迁移到 Skype。</span><span class="sxs-lookup"><span data-stu-id="75491-117">In April 2013, Messenger users were migrated to Skype upon sign-in.</span></span> <span data-ttu-id="75491-118">即使在这些联系人更新到 Skype 后, 依赖联盟的 Lync 客户仍然能够与他们的 Messenger 联系人进行通信。</span><span class="sxs-lookup"><span data-stu-id="75491-118">Lync customers who rely on federation with Messenger will continue to be able to communicate with their Messenger contacts, even after those contacts update to Skype.</span></span> <span data-ttu-id="75491-119">Lync 管理员或 Lync 最终用户无需执行此操作来维护服务的连续性, 并且 Lync 中的此功能的管理与 Messenger 的通信方式相同。</span><span class="sxs-lookup"><span data-stu-id="75491-119">There is nothing that Lync administrators or Lync end-users need to do to maintain continuity of service, and management of this capability within Lync remains the same as it has been for communications with Messenger.</span></span> 

<span data-ttu-id="75491-120">当 Messenger 用户使用其 Microsoft 帐户 (即 Messenger 使用的相同凭据) 登录到 Skype 时, 其所有 Messenger 联系人 (包括联合 Lync 联系人) 都使用 Skype。</span><span class="sxs-lookup"><span data-stu-id="75491-120">When Messenger users sign into Skype using their Microsoft accounts (i.e., the same credentials used for Messenger) all of their Messenger contacts - including federated Lync contacts - follow them into Skype.</span></span> <span data-ttu-id="75491-121">可使用 Skype 和 Lync 之间的联机状态共享和即时消息功能。</span><span class="sxs-lookup"><span data-stu-id="75491-121">Presence sharing and instant messaging between Skype and Lync for these contacts is available.</span></span> 

<span data-ttu-id="75491-122">Lync-Skype 连接-联系人在 Lync 和 Skype 用户之间的添加、状态共享、即时消息和音频呼叫现在也可供所有 Lync 客户使用。</span><span class="sxs-lookup"><span data-stu-id="75491-122">Lync-Skype connectivity - contact adding, presence sharing, instant messaging, and audio calling between Lync and Skype users - is also now available to all Lync customers.</span></span>

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a><span data-ttu-id="75491-123">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="75491-123">Yahoo\!</span></span> <span data-ttu-id="75491-124">和 AOL 即时消息</span><span class="sxs-lookup"><span data-stu-id="75491-124">and AOL Instant Messenger</span></span>

<span data-ttu-id="75491-125">与 Yahoo 的联盟\!</span><span class="sxs-lookup"><span data-stu-id="75491-125">Federation with Yahoo\!</span></span> <span data-ttu-id="75491-126">AOL (和 Office 通信服务器) 的客户可以通过路径获得 AOL。</span><span class="sxs-lookup"><span data-stu-id="75491-126">and AOL are both on a path toward end-of-life for customers of Lync (and Office Communications Server).</span></span> <span data-ttu-id="75491-127">Microsoft 提供每项服务的能力已被从 Yahoo 提供支持\!</span><span class="sxs-lookup"><span data-stu-id="75491-127">Microsoft’s ability to provide each of these services has been contingent upon support from Yahoo\!</span></span> <span data-ttu-id="75491-128">和 AOL, 并向下缠绕这些协议的基础协议。</span><span class="sxs-lookup"><span data-stu-id="75491-128">and AOL, and the underlying agreements of these are winding down.</span></span> <span data-ttu-id="75491-129">对于这两个 Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="75491-129">For both Yahoo\!</span></span> <span data-ttu-id="75491-130">并且 AOL 的服务将继续至2014年6月。</span><span class="sxs-lookup"><span data-stu-id="75491-130">and AOL, service will continue through June 2014.</span></span>

  - <span data-ttu-id="75491-131">**Yahoo** -服务将在2014年6月后继续, 并且客户将继续使用 Microsoft LYNC 公共 IM 连接用户订阅许可证 ("PIC USL") 获得许可。</span><span class="sxs-lookup"><span data-stu-id="75491-131">**Yahoo** - Service will continue through June 2014, and customers continue to need to be licensed with the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”).</span></span><span data-ttu-id="75491-132">从2012年9月1日起, PIC USL 不能再购买新的或续订协议。</span><span class="sxs-lookup"><span data-stu-id="75491-132">  As of September 1st, 2012, the PIC USL, is no longer available for purchase for new or renewing agreements.</span></span><span data-ttu-id="75491-133">在此日期之前购买许可证的客户将能够继续与 Yahoo 进行联盟\!</span><span class="sxs-lookup"><span data-stu-id="75491-133">  Customers with licenses purchased prior to this date will be able to continue to federate with Yahoo\!</span></span> <span data-ttu-id="75491-134">直到较早的服务关闭日期或许可证过期。</span><span class="sxs-lookup"><span data-stu-id="75491-134">until the earlier of the service shut down date or their license expiration.</span></span><span data-ttu-id="75491-135">阅读 Lync 团队博客上[的公告](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx)。</span><span class="sxs-lookup"><span data-stu-id="75491-135"> Read [the announcement](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) on the Lync Team Blog.</span></span><span data-ttu-id="75491-136">如果客户的许可证在2014年6月30日之前过期, 则将按与年6月30日到2014之间的时间段的付款金额为比例, 获得点数。</span><span class="sxs-lookup"><span data-stu-id="75491-136"> Customers who have PIC licenses on agreements that extend past June 30, 2014 will receive a credit in proportion to the amount of the payments covering the time period following June 30, 2014.</span></span>

  - <span data-ttu-id="75491-137">**AOL** -在2014年6月30日, LYNC 的 IM 连接 ("PIC") 服务将不再可用。</span><span class="sxs-lookup"><span data-stu-id="75491-137">**AOL** - On June 30, 2014, Lync's IM connectivity ("PIC") service will no longer be available.</span></span><span data-ttu-id="75491-138">为了在服务结束时限制客户中断, 我们已停止设置其他客户域。</span><span class="sxs-lookup"><span data-stu-id="75491-138"> In order to limit customer disruption when the service ends, we have discontinued the provisioning of additional customer domains.</span></span> <span data-ttu-id="75491-139">在2014年6月30日之前, 客户无需执行任何操作即可继续支持与目标的联盟通信。</span><span class="sxs-lookup"><span data-stu-id="75491-139">Until June 30, 2014, customers do not need to do anything to continue to support federated communications with AIM.</span></span> <span data-ttu-id="75491-140">除了此日期 (或对于想要在以后预配其他域的客户), 可直接从 AOL 获取替代服务。</span><span class="sxs-lookup"><span data-stu-id="75491-140">Beyond this date (or for customers that would like to provision additional domains in the meantime), a substitute service is available directly from AOL.</span></span> <span data-ttu-id="75491-141">有关 AOL 新服务的详细信息, 请参阅[建立与 AIM](http://aimenterprise.aol.com/pic.php)  的直接联盟 (在 AOL.com 上打开新页面)。</span><span class="sxs-lookup"><span data-stu-id="75491-141">For more information on AOL's new service, see [Establishing Direct Federation with AIM](http://aimenterprise.aol.com/pic.php)  (opens new page on AOL.com).</span></span>  

</div>

<div>

## <a name="public-im-provider-summary"></a><span data-ttu-id="75491-142">公共 IM 提供商摘要</span><span class="sxs-lookup"><span data-stu-id="75491-142">Public IM Provider Summary</span></span>

<span data-ttu-id="75491-143">下表提供了公用 IM 服务提供商、与 Lync 的联盟功能以及授权要求的摘要。</span><span class="sxs-lookup"><span data-stu-id="75491-143">The following table provides a summary of the Public IM service providers, federation capabilities with Lync, and licensing requirements.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75491-144">公用 IM 服务提供商</span><span class="sxs-lookup"><span data-stu-id="75491-144">Public IM Service Provider</span></span></th>
<th><span data-ttu-id="75491-145">联合功能</span><span class="sxs-lookup"><span data-stu-id="75491-145">Federated Capabilities</span></span></th>
<th><span data-ttu-id="75491-146">许可要求</span><span class="sxs-lookup"><span data-stu-id="75491-146">Licensing Requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75491-147">Skype</span><span class="sxs-lookup"><span data-stu-id="75491-147">Skype</span></span></p></td>
<td><p><span data-ttu-id="75491-148">即时消息、状态、音频</span><span class="sxs-lookup"><span data-stu-id="75491-148">IM, Presence, Audio</span></span></p></td>
<td><p><span data-ttu-id="75491-149">Lync Server 客户端访问许可证, Lync Online 计划1/2/3</span><span class="sxs-lookup"><span data-stu-id="75491-149">Lync Server Client Access Licenses, Lync Online Plan 1/2/3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75491-150">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="75491-150">Windows Live Messenger</span></span></p></td>
<td><p><span data-ttu-id="75491-151">即时消息、状态、音频/视频</span><span class="sxs-lookup"><span data-stu-id="75491-151">IM, Presence, Audio/Video</span></span></p></td>
<td><p><span data-ttu-id="75491-152">Lync Server 客户端访问许可证 (受支持的时间为 WLM 的市场)</span><span class="sxs-lookup"><span data-stu-id="75491-152">Lync Server Client Access Licenses (supported as long as WLM is in market)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75491-153">AOL</span><span class="sxs-lookup"><span data-stu-id="75491-153">AOL</span></span></p></td>
<td><p><span data-ttu-id="75491-154">即时消息、状态</span><span class="sxs-lookup"><span data-stu-id="75491-154">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="75491-155">Lync Server 客户端访问许可证;支持的现有客户2014年6月。</span><span class="sxs-lookup"><span data-stu-id="75491-155">Lync Server Client Access Licenses; supported through June 2014 for existing customers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75491-156">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="75491-156">Yahoo!</span></span></p></td>
<td><p><span data-ttu-id="75491-157">即时消息、状态</span><span class="sxs-lookup"><span data-stu-id="75491-157">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="75491-158">除了 Lync Server 客户端访问许可证之外, 还需要其他 Microsoft Lync 公共 IM 连接用户订阅许可证 ("PIC USL")。</span><span class="sxs-lookup"><span data-stu-id="75491-158">Requires additional Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) in addition to Lync Server Client Access Licences.</span></span> <span data-ttu-id="75491-159">从2012年9月的价目表中, PIC USL 不能再购买。</span><span class="sxs-lookup"><span data-stu-id="75491-159">As of the September 2012 Price List, the PIC USL is no longer available for purchase.</span></span> <span data-ttu-id="75491-160">具有活动许可证的客户可以继续与 Yahoo! 进行联盟</span><span class="sxs-lookup"><span data-stu-id="75491-160">Customers with active licenses are able to continue to federate with Yahoo!</span></span> <span data-ttu-id="75491-161">Messenger, 直到服务在2014年6月30日的关闭日期。</span><span class="sxs-lookup"><span data-stu-id="75491-161">Messenger until the service shut down date on June 30, 2014.</span></span></p></td>
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

