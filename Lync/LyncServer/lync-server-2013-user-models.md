---
title: Lync Server 2013：用户模型
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 user models
ms:assetid: c551371c-d740-4372-bada-f0d713ec0d33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398811(v=OCS.15)
ms:contentKeyID: 49733811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cec912d84859baf77363764851d7abd1592b2760
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029433"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-models-in-lync-server-2013"></a><span data-ttu-id="36521-102">Lync Server 2013 中的用户模型</span><span class="sxs-lookup"><span data-stu-id="36521-102">User models in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36521-103">_**上次修改的主题：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="36521-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="36521-104">此处介绍的用户模型为[使用用户模型的 Lync Server 2013 容量规划](lync-server-2013-capacity-planning-using-the-user-models.md)中所述的容量规划度量和建议提供了基础。</span><span class="sxs-lookup"><span data-stu-id="36521-104">The user models described here provide the basis for the capacity planning measurements and recommendations described in [Capacity planning for Lync Server 2013 using the user models](lync-server-2013-capacity-planning-using-the-user-models.md).</span></span>

<div>

## <a name="lync-server-2013-user-models"></a><span data-ttu-id="36521-105">Lync Server 2013 用户模型</span><span class="sxs-lookup"><span data-stu-id="36521-105">Lync Server 2013 User Models</span></span>

<span data-ttu-id="36521-106">下表介绍了用于 Lync Server 2013 的注册、联系人、即时消息（IM）和状态的用户模型。</span><span class="sxs-lookup"><span data-stu-id="36521-106">The following table describes the user model for registration, contacts, instant messaging (IM), and presence for Lync Server 2013.</span></span>

### <a name="environment-and-registration-user-model"></a><span data-ttu-id="36521-107">环境和注册用户模型</span><span class="sxs-lookup"><span data-stu-id="36521-107">Environment and Registration User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36521-108">类别</span><span class="sxs-lookup"><span data-stu-id="36521-108">Category</span></span></th>
<th><span data-ttu-id="36521-109">说明</span><span class="sxs-lookup"><span data-stu-id="36521-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36521-110">部署大小和通讯组</span><span class="sxs-lookup"><span data-stu-id="36521-110">Deployment size and distribution</span></span></p></td>
<td><p><span data-ttu-id="36521-111">我们对含有三个中央站点（每个站点有一个前端池）的大型部署进行了建模。</span><span class="sxs-lookup"><span data-stu-id="36521-111">We model a large deployment with three central sites, with one Front End pool per site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36521-112">Active Directory 用户的百分比</span><span class="sxs-lookup"><span data-stu-id="36521-112">Percentage of Active Directory users</span></span></p></td>
<td><p><span data-ttu-id="36521-113">我们假定组织中所有 Active Directory 用户的70% 为 Lync Server 启用。</span><span class="sxs-lookup"><span data-stu-id="36521-113">We assume that 70% of all Active Directory users in the organization are enabled for Lync Server.</span></span> <span data-ttu-id="36521-114">每个已启用用户的80% 每天都登录到 Lync Server （80% 并发）。</span><span class="sxs-lookup"><span data-stu-id="36521-114">80% of those enabled users are logged on to Lync Server each day (80% concurrency).</span></span> <span data-ttu-id="36521-115">本节下文中的数字都以并发用户为基础。</span><span class="sxs-lookup"><span data-stu-id="36521-115">The concurrent users are the basis for the numbers in the rest of this section.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36521-116">Active Directory 更改</span><span class="sxs-lookup"><span data-stu-id="36521-116">Active Directory changes</span></span></p></td>
<td><p><span data-ttu-id="36521-117">我们假定每周在 Active Directory 中为 Lync 创建和启用了总用户数的0.5%，并且每周从 Active Directory 和 Lync 禁用了总用户数的0.5%。</span><span class="sxs-lookup"><span data-stu-id="36521-117">We assume that 0.5% of total users are created and enabled for Lync in Active Directory each week, and that 0.5% of total users are disabled from Active Directory and from Lync each week.</span></span> <span data-ttu-id="36521-118">5% 的用户每周至少更改了一个 Active Directory 属性。</span><span class="sxs-lookup"><span data-stu-id="36521-118">5% of users have at least one Active Directory attribute changed each week.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36521-119">Active Directory 通讯组</span><span class="sxs-lookup"><span data-stu-id="36521-119">Active Directory distribution groups</span></span></p></td>
<td><p><span data-ttu-id="36521-p103">我们假定，组织的 Active Directory 通讯组数是 Active Directory 所有用户数的三倍。通讯组的大小如下：</span><span class="sxs-lookup"><span data-stu-id="36521-p103">We assume that the number of Active Directory distribution groups in the organization is equal to three times the number of all users in Active Directory. The distribution groups have the following sizes:</span></span></p>
<ul>
<li><p><span data-ttu-id="36521-122">64% 具有 2-30 个用户</span><span class="sxs-lookup"><span data-stu-id="36521-122">64% have 2-30 users</span></span></p></li>
<li><p><span data-ttu-id="36521-123">13% 具有 31-50 个用户</span><span class="sxs-lookup"><span data-stu-id="36521-123">13% have 31-50 users</span></span></p></li>
<li><p><span data-ttu-id="36521-124">10% 具有 51-100 个用户</span><span class="sxs-lookup"><span data-stu-id="36521-124">10% have 51-100 users</span></span></p></li>
<li><p><span data-ttu-id="36521-125">13% 具有 101-500 个用户</span><span class="sxs-lookup"><span data-stu-id="36521-125">13% have 101-500 users</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36521-126">IP 语音 (VoIP) 用户</span><span class="sxs-lookup"><span data-stu-id="36521-126">Voice over IP (VoIP) users</span></span></p></td>
<td><p><span data-ttu-id="36521-127">60% 的 Lync Server 用户启用了统一通信（UC）（即，其电话号码归 Lync Server 所有）。</span><span class="sxs-lookup"><span data-stu-id="36521-127">60% of Lync Server users are enabled for unified communications (UC) (that is, their phone numbers are owned by Lync Server).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36521-128">注册的客户端分布</span><span class="sxs-lookup"><span data-stu-id="36521-128">Registered client distribution</span></span></p></td>
<td><p><span data-ttu-id="36521-129">65% 的客户端运行 Lync 2013 软件，包括 Lync 和 Lync Phone Edition。</span><span class="sxs-lookup"><span data-stu-id="36521-129">65% of clients run Lync 2013 software, including Lync and Lync Phone Edition.</span></span></p>
<p><span data-ttu-id="36521-130">从以前版本的 Lync 运行客户端软件的客户端为30%。</span><span class="sxs-lookup"><span data-stu-id="36521-130">30% of clients running client software from a previous version of Lync.</span></span></p>
<p><span data-ttu-id="36521-131">5% 的客户端使用 Lync Web App。</span><span class="sxs-lookup"><span data-stu-id="36521-131">5% of clients using Lync Web App.</span></span></p>
<p><span data-ttu-id="36521-132">如果启用了移动功能，我们将假定40% 的用户正在与其他先前引用的已注册客户端选项同时使用移动性。</span><span class="sxs-lookup"><span data-stu-id="36521-132">If mobility is enabled, we assume that 40% of users are using mobility concurrently with the other previously cited registered client options.</span></span> <span data-ttu-id="36521-133">在这种情况下，客户端的多重状态点（MPOP）比率为1：1.9。</span><span class="sxs-lookup"><span data-stu-id="36521-133">In this case the client multiple point of presence (MPOP) ratio is 1:1.9.</span></span> <span data-ttu-id="36521-134">如果禁用移动，MPOP 比率为1:1.5。</span><span class="sxs-lookup"><span data-stu-id="36521-134">If mobility is disabled, the MPOP ratio is 1:1.5.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36521-135">远程用户分布</span><span class="sxs-lookup"><span data-stu-id="36521-135">Remote user distribution</span></span></p></td>
<td><p><span data-ttu-id="36521-136">70% 的用户从内部连接。</span><span class="sxs-lookup"><span data-stu-id="36521-136">70% of users connecting internally.</span></span></p>
<p><span data-ttu-id="36521-137">30% 的用户通过边缘服务器和控制器连接。</span><span class="sxs-lookup"><span data-stu-id="36521-137">30% of users connecting through an Edge Server and a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36521-138">联系人分布</span><span class="sxs-lookup"><span data-stu-id="36521-138">Contact distribution</span></span></p></td>
<td><p><span data-ttu-id="36521-p105">一个用户拥有的最大联系人数为 1,000。拥有 1,000 个联系人的用户低于 1%。拥有 100 个或更多联系人的用户低于 25%。</span><span class="sxs-lookup"><span data-stu-id="36521-p105">The maximum number of contacts a user has is 1,000. Less than 1% of users have 1,000 contacts. Less than 25% of users have 100 or more contacts.</span></span></p>
<p><span data-ttu-id="36521-p106">使用公共云连接的用户平均拥有 80 个联系人。在这些用户中：</span><span class="sxs-lookup"><span data-stu-id="36521-p106">Average of 80 contacts for users with public cloud connectivity. Of these users:</span></span></p>
<ul>
<li><p><span data-ttu-id="36521-p107">50% 的联系人在组织内。这些用户中的 10% 为远程用户，从防火墙以外连接。</span><span class="sxs-lookup"><span data-stu-id="36521-p107">50% of the contacts are within the organization. 10% of those users are remote users, connecting from outside the firewall.</span></span></p></li>
<li><p><span data-ttu-id="36521-146">40% 的联系人为公共云用户（例如 AOL、Yahoo! 、MSN 或 Google Talk 用户）。</span><span class="sxs-lookup"><span data-stu-id="36521-146">40% of the contacts are public cloud users (such as users of AOL, Yahoo!, MSN, or Google Talk).</span></span></p></li>
<li><p><span data-ttu-id="36521-147">10% 的联系人来自联盟伙伴。</span><span class="sxs-lookup"><span data-stu-id="36521-147">10% of the contacts are from federated partners.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="36521-148">从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或更新的协议。</span><span class="sxs-lookup"><span data-stu-id="36521-148">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="36521-149">拥有主动许可证的客户将能够继续与 Yahoo！联合联合</span><span class="sxs-lookup"><span data-stu-id="36521-149">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="36521-150">信使，直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="36521-150">Messenger until the service shut down date.</span></span> <span data-ttu-id="36521-151">AOL 和 Yahoo！的生命周期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="36521-151">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="36521-152">已宣布。</span><span class="sxs-lookup"><span data-stu-id="36521-152">has been announced.</span></span> <span data-ttu-id="36521-153">有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</span><span class="sxs-lookup"><span data-stu-id="36521-153">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="36521-154">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个用户每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="36521-154">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="36521-155">Messenger.</span><span class="sxs-lookup"><span data-stu-id="36521-155">Messenger.</span></span> <span data-ttu-id="36521-156">Microsoft 提供此服务的能力因 Yahoo！中的支持而受到了支持，其下凸的底层协议。</span><span class="sxs-lookup"><span data-stu-id="36521-156">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="36521-157">Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。</span><span class="sxs-lookup"><span data-stu-id="36521-157">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="36521-158">与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="36521-158">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="36521-159">Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。</span><span class="sxs-lookup"><span data-stu-id="36521-159">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
</ul>
<p><span data-ttu-id="36521-p111">未使用公共云连接的用户平均拥有 50 个联系人。在这些用户中：</span><span class="sxs-lookup"><span data-stu-id="36521-p111">Average of 50 contacts for users without public cloud connectivity. Of these users:</span></span></p>
<ul>
<li><p><span data-ttu-id="36521-p112">80% 的联系人在组织内。这些用户中的 10% 为远程用户，从防火墙以外连接。</span><span class="sxs-lookup"><span data-stu-id="36521-p112">80% of the contacts are within the organization. 10% of those users are remote users, connecting from outside the firewall.</span></span></p></li>
<li><p><span data-ttu-id="36521-164">20% 的联系人来自联盟伙伴。</span><span class="sxs-lookup"><span data-stu-id="36521-164">20% of the contacts are from federated partners.</span></span></p>
<p><span data-ttu-id="36521-p113">每个用户在其联系人列表中都有一个通讯组。为了进行性能测试，我们假设通讯组始终是展开的。</span><span class="sxs-lookup"><span data-stu-id="36521-p113">Each user has 1 distribution group in their contact list. For performance testing, we assume that distribution groups are always expanded.</span></span></p></li>
</ul>
<p><span data-ttu-id="36521-167">25% 的用户联系人使用 XMPP。</span><span class="sxs-lookup"><span data-stu-id="36521-167">25% of a user’s contacts use XMPP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36521-168">会话时间</span><span class="sxs-lookup"><span data-stu-id="36521-168">Session time</span></span></p></td>
<td><p><span data-ttu-id="36521-p114">平均用户登录会话持续 12 个小时。所有用户在会话开始后的 120 分钟内登录。</span><span class="sxs-lookup"><span data-stu-id="36521-p114">The average user logon session lasts 12 hours. All users log on within 120 minutes of the start of the session.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="im-and-presence-user-model"></a><span data-ttu-id="36521-171">IM 和状态用户模型</span><span class="sxs-lookup"><span data-stu-id="36521-171">IM and Presence User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36521-172">类别</span><span class="sxs-lookup"><span data-stu-id="36521-172">Category</span></span></th>
<th><span data-ttu-id="36521-173">说明</span><span class="sxs-lookup"><span data-stu-id="36521-173">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36521-174">对等 IM 会话</span><span class="sxs-lookup"><span data-stu-id="36521-174">Peer-to-peer IM sessions</span></span></p></td>
<td><p><span data-ttu-id="36521-175">平均每个用户每天发起六个对等 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="36521-175">Each user averages six peer-to-peer IM sessions per day.</span></span></p>
<p><span data-ttu-id="36521-176">每个会话 10 条即时消息。</span><span class="sxs-lookup"><span data-stu-id="36521-176">10 instant messages per session.</span></span></p>
<p><span data-ttu-id="36521-177">每封邮件都通过两个 SIP 信息邮件和2个 SIP 200 OK 邮件进行匹配（针对状态指示器&lt;，&gt;如 "名称为键入"）</span><span class="sxs-lookup"><span data-stu-id="36521-177">Each message is matched by two SIP INFO messages and 2 SIP 200 OK messages (for the status indicators such as “&lt;Name&gt; is Typing”)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36521-178">状态轮询</span><span class="sxs-lookup"><span data-stu-id="36521-178">Presence polling</span></span></p></td>
<td><p><span data-ttu-id="36521-p115">总体上讲，假设状态轮询为平均每个用户每小时 60 次轮询。对于每个用户，假设平均：</span><span class="sxs-lookup"><span data-stu-id="36521-p115">Overall, we assume presence polling at an average of 60 polls per user per hour. For each user, assume an average of:</span></span></p>
<ul>
<li><p><span data-ttu-id="36521-p116">在用户的组织选项卡（而非联系人列表）中每天一次用户状态轮询。用户的组织选项卡中非联系人的平均数为 15 个用户。每天执行两次联系人卡片查看操作。</span><span class="sxs-lookup"><span data-stu-id="36521-p116">One poll per day of the presence of users in the user’s organization tab (but not Contacts list). Average number of non-contacts in the user’s organization tab is 15 users. Two contact card viewing operations per day.</span></span></p></li>
<li><p><span data-ttu-id="36521-184">每次用户单击其他用户以开始对话时发生一次状态轮询，预计为每小时一次。</span><span class="sxs-lookup"><span data-stu-id="36521-184">One presence poll every time the user clicks another user to start a conversation, estimated at once per hour.</span></span></p></li>
<li><p><span data-ttu-id="36521-p117">每小时六次用户搜索。每次执行搜索时，都会针对搜索结果列表中的每个人发送批轮询。假设搜索结果的平均大小为 20。如果搜索结果停留在屏幕上，则每 5 分钟就会刷新一次批轮询；假设每小时将进行两次这样的刷新。</span><span class="sxs-lookup"><span data-stu-id="36521-p117">Six user searches per hour. Every time a search is performed, a batch poll is sent for everyone in the search result list. We assume the average size of search results is 20. If the search results stay on screen, the batch poll is refreshed every 5 minutes; we assume that there will be two such refreshes per hour.</span></span></p></li>
<li><p><span data-ttu-id="36521-189">当用户在 Outlook 中打开或预览电子邮件时，电子邮件的“收件人:”和“抄送:”字段中将发生一次用户状态轮询，预计为每小时五封电子邮件、每封电子邮件四个用户。</span><span class="sxs-lookup"><span data-stu-id="36521-189">When the user opens or previews an email in Outlook, a poll of the presence of users in the To: and CC: fields of the email, estimated at five emails per hour and four users per email.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36521-190">状态订阅</span><span class="sxs-lookup"><span data-stu-id="36521-190">Presence subscriptions</span></span></p></td>
<td><p><span data-ttu-id="36521-p118">当用户将其他用户添加为联系人时，第一个用户将“订阅”<em></em>第二个用户的五类信息。这些类别的信息的更新会自动发送给第一个用户。</span><span class="sxs-lookup"><span data-stu-id="36521-p118">When one user adds another as a contact, the first user is <em>subscribing</em> to five categories of information about the second user. Updates of these categories of information are automatically sent to the first user.</span></span></p>
<p><span data-ttu-id="36521-193">针对每个客户端，会发送单个订阅请求以获取平均 40 个联系人状态，以及发送其他 40 个对话以获取联盟联系人状态。</span><span class="sxs-lookup"><span data-stu-id="36521-193">For each client, a single batch subscription request is sent to obtain the presence state of an average of 40 contacts, with an additional 40 dialogs to obtain presence for federated contacts.</span></span></p>
<p><span data-ttu-id="36521-194">扩展通讯组成员的状态可通过持久状态订阅（而非轮询）进行查找，并建模为每个用户每两小时一次扩展。</span><span class="sxs-lookup"><span data-stu-id="36521-194">Presence for members of an expanded distribution group is found through persistent presence subscriptions, not polling, and is modeled as 1 expansion per user for each 2 hours.</span></span></p>
<p><span data-ttu-id="36521-p119">在以下情况下会发生<em>短期订阅</em>：某位用户登录，针对所有用户联系人存在批订阅，然后该用户很快注销。假设每个用户每小时有 6 个短期订阅，其中每个订阅持续 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="36521-p119"><em>Short subscriptions</em> happen when a user logs in, there is a batch subscription for all the user’s contacts, and then the user soon logs off. We assume 6 short subscriptions per user per hour, where each subscription lasts 10 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36521-197">状态发布</span><span class="sxs-lookup"><span data-stu-id="36521-197">Presence Publication</span></span></p></td>
<td><p><span data-ttu-id="36521-198">平均每个用户每小时发布状态 4 次，最多每个用户每小时发布 6 次。</span><span class="sxs-lookup"><span data-stu-id="36521-198">Presence state is published at an average of 4 publications per user per hour, with a maximum 6 per user per hour.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36521-199">状态文档大小</span><span class="sxs-lookup"><span data-stu-id="36521-199">Presence Document Size</span></span></p></td>
<td><p><span data-ttu-id="36521-200">假设完整状态文档的平均大小为 4K，最大为 25K。</span><span class="sxs-lookup"><span data-stu-id="36521-200">The average size of a complete presence document is assumed to be 4K, with a maximum of 25K.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="36521-201">下表介绍了通讯簿使用用户模型。</span><span class="sxs-lookup"><span data-stu-id="36521-201">The following table describes the user model for address book use.</span></span>

### <a name="address-book-usage-user-model"></a><span data-ttu-id="36521-202">通讯簿使用用户模型</span><span class="sxs-lookup"><span data-stu-id="36521-202">Address Book Usage User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36521-203">通讯簿搜索模式</span><span class="sxs-lookup"><span data-stu-id="36521-203">Address Book search mode</span></span></th>
<th><span data-ttu-id="36521-204">用法</span><span class="sxs-lookup"><span data-stu-id="36521-204">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36521-205">仅通讯簿 Web 查询（通讯簿 Web 查询服务执行的所有查询）</span><span class="sxs-lookup"><span data-stu-id="36521-205">Address Book Web Query only (all queries performed by Address Book Web Query service)</span></span></p></td>
<td><p><span data-ttu-id="36521-206">每个用户每天四次前缀查询。</span><span class="sxs-lookup"><span data-stu-id="36521-206">Four prefix queries per user per day.</span></span></p>
<p><span data-ttu-id="36521-p120">每个用户每天 60 次精确搜索查询。在这些查询中，40% 为批处理查询，平均每次查询 20 个联系人。剩余的 60% 为单个联系人查询。</span><span class="sxs-lookup"><span data-stu-id="36521-p120">60 exact search queries per user per day. 40% of those are batched, with an average of 20 contacts per query. The other 60% of the queries are for a single contact.</span></span></p>
<p><span data-ttu-id="36521-p121">每个用户每天 25 次照片查询。其中 24 次为单张照片查询，另外一次为批处理查询，平均查询 20 个联系人。</span><span class="sxs-lookup"><span data-stu-id="36521-p121">25 photo queries per user per day. 24 are for a single photo, the other is a batch query with an average of 20 contacts.</span></span></p>
<p><span data-ttu-id="36521-212">每个用户每天一次彻底的组织搜索查询。</span><span class="sxs-lookup"><span data-stu-id="36521-212">One total organization search query per user per day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36521-p122">混合模式，结合使用通讯簿文件和 Web 查询。这是默认模式。</span><span class="sxs-lookup"><span data-stu-id="36521-p122">Mixed mode, both address book file and web queries used. This is the default mode.</span></span></p></td>
<td><p><span data-ttu-id="36521-215">只有两种查询会连接到网络，即照片查询和彻底的组织搜索查询。</span><span class="sxs-lookup"><span data-stu-id="36521-215">Only two types of queries go to the network, the photo and total organizational search queries.</span></span></p>
<p><span data-ttu-id="36521-p123">每个用户每天 25 次照片查询。其中 24 次为单张照片查询，另外一次为批处理查询，平均查询 20 个联系人。</span><span class="sxs-lookup"><span data-stu-id="36521-p123">25 photo queries per user per day. 24 are for a single photo, the other is a batch query with an average of 20 contacts.</span></span></p>
<p><span data-ttu-id="36521-218">每个用户每天一次彻底的组织搜索查询。</span><span class="sxs-lookup"><span data-stu-id="36521-218">One total organization search query per user per day.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="36521-219">下表介绍了会议模型。</span><span class="sxs-lookup"><span data-stu-id="36521-219">The following table describes the conferencing model.</span></span>

### <a name="conferencing-model"></a><span data-ttu-id="36521-220">会议模型</span><span class="sxs-lookup"><span data-stu-id="36521-220">Conferencing Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36521-221">类别</span><span class="sxs-lookup"><span data-stu-id="36521-221">Category</span></span></th>
<th><span data-ttu-id="36521-222">说明</span><span class="sxs-lookup"><span data-stu-id="36521-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36521-223">安排的会议&quot;与 "&quot;立即开会" 会议</span><span class="sxs-lookup"><span data-stu-id="36521-223">Scheduled meetings versus &quot;Meet now&quot; meetings</span></span></p></td>
<td><p><span data-ttu-id="36521-224">60% 计划内会议，40% 计划外会议。</span><span class="sxs-lookup"><span data-stu-id="36521-224">60% scheduled, 40% unscheduled.</span></span></p>
<p><span data-ttu-id="36521-225">在已安排的会议当中，假设其中 80% 是定期发生的分配会议；10% 是一次性公开会议；8% 是一次性匿名会议，以及 2% 是一次性非公开性会议。</span><span class="sxs-lookup"><span data-stu-id="36521-225">Of the scheduled meetings, we assume that 80% are assigned conferences, which are occurences of recurring conferences; 10% are one-time open meetings; 8% are one-time anonymous meetings, and 2% are one-time closed meetings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36521-226">会议客户端分布</span><span class="sxs-lookup"><span data-stu-id="36521-226">Conferencing client distribution</span></span></p></td>
<td><p><span data-ttu-id="36521-227">对于计划内会议：</span><span class="sxs-lookup"><span data-stu-id="36521-227">For scheduled meetings:</span></span></p>
<ul>
<li><p><span data-ttu-id="36521-228">65% 的会议用户使用 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="36521-228">65% of conferencing users use Lync 2013.</span></span></p></li>
<li><p><span data-ttu-id="36521-229">5% 的会议用户使用 Microsoft Lync Web App。</span><span class="sxs-lookup"><span data-stu-id="36521-229">5% of conferencing users use Microsoft Lync Web App.</span></span></p></li>
<li><p><span data-ttu-id="36521-230">30% 的会议用户使用早期版本的客户端，包括 Microsoft Lync 2010、Office Communicator 2007 R2、Office Communicator 2007 和 Microsoft Office Communicator Web Access （2007发布）。</span><span class="sxs-lookup"><span data-stu-id="36521-230">30% of conferencing users use earlier clients, including Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, and Microsoft Office Communicator Web Access (2007 release).</span></span></p></li>
</ul>
<p><span data-ttu-id="36521-231">对于计划外会议：</span><span class="sxs-lookup"><span data-stu-id="36521-231">For unscheduled meetings:</span></span></p>
<ul>
<li><p><span data-ttu-id="36521-232">70% 的会议用户使用 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="36521-232">70% of conferencing users use Lync 2013.</span></span></p></li>
<li><p><span data-ttu-id="36521-233">30% 的会议用户使用早期版本的客户端，包括 Microsoft Lync 2010、Office Communicator 2007 R2、Office Communicator 2007 和 Microsoft Office Communicator Web Access （2007发布）。</span><span class="sxs-lookup"><span data-stu-id="36521-233">30% of conferencing users use earlier clients, including Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, and Microsoft Office Communicator Web Access (2007 release).</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36521-234">会议并发</span><span class="sxs-lookup"><span data-stu-id="36521-234">Meeting concurrency</span></span></p></td>
<td><p><span data-ttu-id="36521-p124">5% 的用户将在工作时间参加会议。因此，在一个有 80,000 个用户的池中，在任何时候都可能有多达 4,000 个用户参加会议。</span><span class="sxs-lookup"><span data-stu-id="36521-p124">5% of users will be in conferences during working hours. Thus, in an 80,000-user pool, as many as 4,000 users might be in conferences at any one time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36521-237">会议音频分布</span><span class="sxs-lookup"><span data-stu-id="36521-237">Meeting audio distribution</span></span></p></td>
<td><p><span data-ttu-id="36521-238">40% VoIP 音频和电话拨入式混合会议，VoIP 用户和电话拨入用户的比率为 3:1。</span><span class="sxs-lookup"><span data-stu-id="36521-238">40% mixed VoIP audio and dial-in conferencing, with a 3:1 ratio of VoIP users to dial-in users.</span></span></p>
<p><span data-ttu-id="36521-239">35% 仅 VoIP 音频。</span><span class="sxs-lookup"><span data-stu-id="36521-239">35% VoIP audio only.</span></span></p>
<p><span data-ttu-id="36521-240">15% 仅电话拨入式会议音频。</span><span class="sxs-lookup"><span data-stu-id="36521-240">15% dial-in conferencing audio only.</span></span></p>
<p><span data-ttu-id="36521-241">10% 无音频（仅 IM 会议，平均每个用户发出 5 条消息）。</span><span class="sxs-lookup"><span data-stu-id="36521-241">10% no audio (IM-only conferences, with an average of five messages sent per user).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36521-242">会议媒体混合</span><span class="sxs-lookup"><span data-stu-id="36521-242">Media mix for conferences</span></span></p></td>
<td><p><span data-ttu-id="36521-243">75% 的会议为 Web 会议，其中包括音频以及一些其他协作形式。</span><span class="sxs-lookup"><span data-stu-id="36521-243">75% of conferences are web conferences, which include audio plus some other collaboration modalities.</span></span></p>
<p><span data-ttu-id="36521-244">这些会议的其他协作方式如下：</span><span class="sxs-lookup"><span data-stu-id="36521-244">For these conferences, the other collaboration methods are as follows:</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="36521-245">这些数字合计达 100% 以上，因为一个会议可以有多种协作方式。</span><span class="sxs-lookup"><span data-stu-id="36521-245">These numbers add up to more than 100% because one conference can have multiple collaboration methods.</span></span>


</div>
<ul>
<li><p><span data-ttu-id="36521-p125">50% 添加应用程序共享。假设一个用户以每秒 1.1 MB 的峰值发送数据。</span><span class="sxs-lookup"><span data-stu-id="36521-p125">50% add application sharing. We assume one users sends data at a peak of 1.1 MB per second.</span></span></p></li>
<li><p><span data-ttu-id="36521-248">50% 添加即时消息（平均每个用户两条消息）。</span><span class="sxs-lookup"><span data-stu-id="36521-248">50% add instant messaging (with an average of 2 messages per user).</span></span></p></li>
<li><p><span data-ttu-id="36521-p126">20% 添加数据协作，包括 PowerPoint 或白板。其中，平均每次会议使用两个 PowerPoint 文件，文件平均大小为 10 MB（不含嵌入式视频）或 30 MB（含嵌入式视频）。平均每个白板 20 个批注。</span><span class="sxs-lookup"><span data-stu-id="36521-p126">20% add data collaboration, including PowerPoint or whiteboard In these, an average of 2 PowerPoint files presented per conference, with an average PowerPoint file size of 10 MB (without embedded video) or 30 MB (with embedded video). Average of 20 annotations per whiteboard.</span></span></p></li>
<li><p><span data-ttu-id="36521-p127">20% 添加视频。在这些用户当中，70% 的用户参加启用了多视图视频的会议，其中每个用户会收到 2-3 个视频流。</span><span class="sxs-lookup"><span data-stu-id="36521-p127">20% add video. Of these users, 70% are in conferences enabled for multiview video, where each user receives 2-3 video streams.</span></span></p></li>
<li><p><span data-ttu-id="36521-253">15% 添加共享便笺。</span><span class="sxs-lookup"><span data-stu-id="36521-253">15% add shared notes.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36521-254">会议参与者分布</span><span class="sxs-lookup"><span data-stu-id="36521-254">Meeting participant distribution</span></span></p></td>
<td><p><span data-ttu-id="36521-255">50% 为经过身份验证的内部用户。</span><span class="sxs-lookup"><span data-stu-id="36521-255">50% internal, authenticated users.</span></span></p>
<p><span data-ttu-id="36521-256">25% 为经过身份验证的远程访问用户。</span><span class="sxs-lookup"><span data-stu-id="36521-256">25% remote access, authenticated users.</span></span></p>
<p><span data-ttu-id="36521-257">15% 为匿名用户。</span><span class="sxs-lookup"><span data-stu-id="36521-257">15% anonymous users.</span></span></p>
<p><span data-ttu-id="36521-258">10% 为联盟用户。</span><span class="sxs-lookup"><span data-stu-id="36521-258">10% federated users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36521-259">与会分布</span><span class="sxs-lookup"><span data-stu-id="36521-259">Meeting join distribution</span></span></p></td>
<td><p><span data-ttu-id="36521-260">用户被模拟为在前 5 分钟内加入会议。</span><span class="sxs-lookup"><span data-stu-id="36521-260">Users are simulated as joining the meeting within the first 5 minutes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="36521-261">在常规前端池中，Lync Server 2013 的受支持的最大会议大小为250个用户。</span><span class="sxs-lookup"><span data-stu-id="36521-261">In regular Front End pools, Lync Server 2013 has a maximum supported meeting size of 250 users.</span></span> <span data-ttu-id="36521-262">每个池一次可承载一个 250 个用户的会议。</span><span class="sxs-lookup"><span data-stu-id="36521-262">Each pool can host one 250-user meeting at a time.</span></span> <span data-ttu-id="36521-263">召开这样的大型会议的同时，池还可以承载其他较小的会议。</span><span class="sxs-lookup"><span data-stu-id="36521-263">While this large meeting is occurring, the pool can also host other smaller conferences.</span></span> <span data-ttu-id="36521-264">另外，通过设置专用池承载这些会议，可以支持多达 1000 位用户的会议。</span><span class="sxs-lookup"><span data-stu-id="36521-264">Additionally, you can support meetings of up to 1000 users by setting up a dedicated pool to host these meetings.</span></span> <span data-ttu-id="36521-265">有关详细信息，请参阅[Lync Server 2013 中的 "对大型会议的支持](lync-server-2013-support-for-large-meetings.md)"。</span><span class="sxs-lookup"><span data-stu-id="36521-265">For details, see [Support for large meetings in Lync Server 2013](lync-server-2013-support-for-large-meetings.md).</span></span>

<span data-ttu-id="36521-266">模拟会议的方式如下：</span><span class="sxs-lookup"><span data-stu-id="36521-266">Conferences were simulated as follows:</span></span>

  - <span data-ttu-id="36521-267">85% 的会议有 4 个参与者。</span><span class="sxs-lookup"><span data-stu-id="36521-267">85% of conferences had four participants.</span></span>

  - <span data-ttu-id="36521-268">10% 的会议有 6 个参与者。</span><span class="sxs-lookup"><span data-stu-id="36521-268">10% of conferences had six participants.</span></span>

  - <span data-ttu-id="36521-269">5% 的会议有 11 个参与者。</span><span class="sxs-lookup"><span data-stu-id="36521-269">5% of conferences had 11 participants.</span></span>

  - <span data-ttu-id="36521-270">用户数为 250 的一次大型会议。</span><span class="sxs-lookup"><span data-stu-id="36521-270">One large conference of 250 users.</span></span>

<span data-ttu-id="36521-271">下表详细说明了涉及电话拨入用户的会议的用户模型。</span><span class="sxs-lookup"><span data-stu-id="36521-271">The following table provides details about the user model for conferences involving dial-in users.</span></span>

### <a name="dial-in-conferencing-user-model"></a><span data-ttu-id="36521-272">电话拨入式会议用户模型</span><span class="sxs-lookup"><span data-stu-id="36521-272">Dial-In Conferencing User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36521-273">类别</span><span class="sxs-lookup"><span data-stu-id="36521-273">Category</span></span></th>
<th><span data-ttu-id="36521-274">说明</span><span class="sxs-lookup"><span data-stu-id="36521-274">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36521-275">已通过身份验证/匿名</span><span class="sxs-lookup"><span data-stu-id="36521-275">Authenticated/anonymous</span></span></p></td>
<td><p><span data-ttu-id="36521-p129">70% 的呼叫者通过匿名加入，并提示输入记录的名称。30% 经过身份验证加入。</span><span class="sxs-lookup"><span data-stu-id="36521-p129">70% of callers join as anonymous and are prompted for a recorded name. 30% join as authenticated users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36521-278">呼叫持续时间和保持音乐</span><span class="sxs-lookup"><span data-stu-id="36521-278">Call duration and music on hold</span></span></p></td>
<td><p><span data-ttu-id="36521-279">不包括保持音乐的平均呼叫持续时间：50 秒。</span><span class="sxs-lookup"><span data-stu-id="36521-279">Average call duration without music on hold: 50 seconds.</span></span></p>
<p><span data-ttu-id="36521-280">50% 的电话拨入用户会听到保持音乐，平均持续 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="36521-280">50% of call-in users hear music on hold, for an average of 5 minutes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36521-281">双音多频 (DTMF)</span><span class="sxs-lookup"><span data-stu-id="36521-281">Dual-tone multifrequency (DTMF)</span></span></p></td>
<td><p><span data-ttu-id="36521-p130">15% 的仅电话拨入式会议有电话领导。10% 包含电话拨入用户的混合会议也有电话领导。</span><span class="sxs-lookup"><span data-stu-id="36521-p130">15% of conferences that are dial-in only have phone leaders. 10% of mixed conferences that include dial-in users also have phone leaders.</span></span></p>
<p><span data-ttu-id="36521-284">20% 的电话领导在每次会议中使用 2 个 DTMF 命令。</span><span class="sxs-lookup"><span data-stu-id="36521-284">20% of phone leaders use 2 DTMF commands per conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36521-285">通知语言</span><span class="sxs-lookup"><span data-stu-id="36521-285">Announcement languages</span></span></p></td>
<td><p><span data-ttu-id="36521-286">模拟使用英语作为通知语言。</span><span class="sxs-lookup"><span data-stu-id="36521-286">Simulations use English as the announcement language.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="36521-287">下表详细说明了会议厅的用户模型。</span><span class="sxs-lookup"><span data-stu-id="36521-287">The following table provides details about the user model for conference lobbies.</span></span>

### <a name="conference-lobby-user-model"></a><span data-ttu-id="36521-288">会议厅用户模型</span><span class="sxs-lookup"><span data-stu-id="36521-288">Conference Lobby User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36521-289">类别</span><span class="sxs-lookup"><span data-stu-id="36521-289">Category</span></span></th>
<th><span data-ttu-id="36521-290">说明</span><span class="sxs-lookup"><span data-stu-id="36521-290">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36521-291">会议厅中的用户数量</span><span class="sxs-lookup"><span data-stu-id="36521-291">Number of users in lobby</span></span></p></td>
<td><p><span data-ttu-id="36521-292">5% 的电话拨入用户通过会议厅，25% 其他用户通过会议厅</span><span class="sxs-lookup"><span data-stu-id="36521-292">5% of dial-in users go through the lobby, and 25% of other users go through the lobby</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36521-293">从会议厅加入</span><span class="sxs-lookup"><span data-stu-id="36521-293">Admitting from lobby</span></span></p></td>
<td><p><span data-ttu-id="36521-294">在模拟中，所有用户在客户端超时之前由演示者许可加入。</span><span class="sxs-lookup"><span data-stu-id="36521-294">In simulations, all users were admitted by the presenter before client timeout.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="36521-295">下表说明了其他对等会话的用户模型。</span><span class="sxs-lookup"><span data-stu-id="36521-295">The following table describes the user model for other peer-to-peer sessions.</span></span>

### <a name="peer-to-peer-sessions-user-model"></a><span data-ttu-id="36521-296">对等会话用户模型</span><span class="sxs-lookup"><span data-stu-id="36521-296">Peer-to-Peer Sessions User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36521-297">类别</span><span class="sxs-lookup"><span data-stu-id="36521-297">Category</span></span></th>
<th><span data-ttu-id="36521-298">说明</span><span class="sxs-lookup"><span data-stu-id="36521-298">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36521-299">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="36521-299">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="36521-300">每个用户每个月参加 5 个对等应用程序共享会话，平均每天参加 0.25 个会话。</span><span class="sxs-lookup"><span data-stu-id="36521-300">Each user participates in 5 peer-to-peer application sharing sessions per month, for an average of 0.25 sessions per day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36521-301">文件传输</span><span class="sxs-lookup"><span data-stu-id="36521-301">File transfer</span></span></p></td>
<td><p><span data-ttu-id="36521-p131">每个用户每个月参加 1 个对等文件传输会话（IM 会话的一部分），平均每天参加 0.05 个会话。传输的会话文件平均大小为 1 MB。</span><span class="sxs-lookup"><span data-stu-id="36521-p131">Each user participates in 1 peer-to-peer file transfer session per month (as part of an IM session), for an average of 0.05 sessions per day. The average session file size transferred is 1 MB.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="36521-304">下表介绍了用于策略的用户模型。</span><span class="sxs-lookup"><span data-stu-id="36521-304">The following table describes the user model for policies.</span></span>

### <a name="policies-user-model"></a><span data-ttu-id="36521-305">策略用户模型</span><span class="sxs-lookup"><span data-stu-id="36521-305">Policies User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36521-306">类别</span><span class="sxs-lookup"><span data-stu-id="36521-306">Category</span></span></th>
<th><span data-ttu-id="36521-307">说明</span><span class="sxs-lookup"><span data-stu-id="36521-307">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36521-308">会议、状态和存档策略</span><span class="sxs-lookup"><span data-stu-id="36521-308">Conferencing, Presence, and Archiving Policies</span></span></p></td>
<td><p><span data-ttu-id="36521-309">假设有一个全局策略、10 个标记会议策略、4 个存档策略和 10 个标记状态策略。</span><span class="sxs-lookup"><span data-stu-id="36521-309">We assume that there is one global policy, 10 tag conferencing policies, 4 Archiving policies, and 10 tag presence policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36521-310">语音策略</span><span class="sxs-lookup"><span data-stu-id="36521-310">Voice Policy</span></span></p></td>
<td><p><span data-ttu-id="36521-311">假设每个站点有一个全局策略和 2 个标记策略。</span><span class="sxs-lookup"><span data-stu-id="36521-311">We assume that there is one global policy and 2 tag policies per site.</span></span> <span data-ttu-id="36521-312">100% 的站点都有站点策略，并为 30% 的用户分配每用户策略。</span><span class="sxs-lookup"><span data-stu-id="36521-312">100% of sites have a site policy, and 30% of users have a per-user policy assigned.</span></span> <span data-ttu-id="36521-313">假设每个站点有一个拨号计划和两个路由。</span><span class="sxs-lookup"><span data-stu-id="36521-313">We assume one dial plan per site and two routes per site.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="busy-hour"></a><span data-ttu-id="36521-314">忙时</span><span class="sxs-lookup"><span data-stu-id="36521-314">Busy Hour</span></span>

<span data-ttu-id="36521-p133">对于对等会话，使用忙时呼叫尝试 (BHCA) 计算峰值负载。此语音行业术语假设将在 20% 的时间内完成一天中 50% 的呼叫。可使用以下公式进行计算：</span><span class="sxs-lookup"><span data-stu-id="36521-p133">For peer-to-peer sessions, peak load is calculated using busy hour call attempts (BHCA). This voice industry term assumes that 50% of all calls for the day will be completed in 20% of the time. It is calculated using the following formula:</span></span>

`BHCA=(total calls * 0.5) / 1.6`

<span data-ttu-id="36521-318">通过运行 VoIP 模拟忙时的性能测试和每天至少 1.6 小时的忙时负载的其他对等会话。</span><span class="sxs-lookup"><span data-stu-id="36521-318">Performance testing simulated busy hour by running VoIP and other peer-to-peer sessions at a busy hour load for at least 1.6 hours per day.</span></span>

<span data-ttu-id="36521-p134">会议峰值负载假设在 4 小时的高峰时间内发生 8 小时工作日 75% 的会议。这些高峰时间的负载是平均会议负载的 1.5 倍。</span><span class="sxs-lookup"><span data-stu-id="36521-p134">Conferencing peak load assumes that 75% of all conferences for an eight-hour day happen in 4 peak time hours. Those peak hours have 1.5 times the average conferencing load.</span></span>

</div>

<div>

## <a name="enterprise-voice-to-pstn-calls"></a><span data-ttu-id="36521-321">企业语音到 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="36521-321">Enterprise Voice to PSTN Calls</span></span>

<span data-ttu-id="36521-322">以下假设适用于企业语音呼叫：</span><span class="sxs-lookup"><span data-stu-id="36521-322">The following assumptions apply to Enterprise Voice calls:</span></span>

  - <span data-ttu-id="36521-323">50% 的用户启用了企业语音，而这些用户的60% 启用了 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="36521-323">50% of users are enabled for Enterprise Voice, and 60% of these users are enabled for PSTN calling.</span></span>

  - <span data-ttu-id="36521-p135">启用了 PSTN 呼叫的其中每一位用户在忙碌时段都发出 4 个 PSTN 呼叫。每个呼叫的持续时间为 3 分钟。</span><span class="sxs-lookup"><span data-stu-id="36521-p135">Each of these users enabled for PSTN calling makes 4 PSTN calls during the busy hour. Each call duration is 3 minutes.</span></span>

  - <span data-ttu-id="36521-326">其中 65% 的 PSTN 语音呼叫使用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="36521-326">65% of these PSTN voice calls use media bypass.</span></span>

</div>

<div>

## <a name="mobility"></a><span data-ttu-id="36521-327">移动性</span><span class="sxs-lookup"><span data-stu-id="36521-327">Mobility</span></span>

<span data-ttu-id="36521-p136">假设为 40% 的注册用户启用了移动。对于启用了移动的每一位用户，假设移动客户端的活动是在该用户其他 MPOP 实例活动的基础上进行增加，但会议交互除外，对其而言，移动客户端只是可用来参与会议的另一种客户端类型。</span><span class="sxs-lookup"><span data-stu-id="36521-p136">40% of registered users are assumed to be enabled for Mobility. For each user that has mobility enabled, we assume that the activity of the mobile client is additive to that of the other MPOP instances for that user, with the exception of conferencing interactions, for which the mobility client is just another client type that can be used to participate in conferences.</span></span>

</div>

<div>

## <a name="persistent-chat"></a><span data-ttu-id="36521-330">持久聊天</span><span class="sxs-lookup"><span data-stu-id="36521-330">Persistent Chat</span></span>

<span data-ttu-id="36521-331">假设 25% 的注册用户将参与到持久聊天会话中，并具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="36521-331">We assume that 25% of registered users will be involved in Persistent chat sessions, with the following characteristics:</span></span>

  - <span data-ttu-id="36521-332">每个用户平均 1.5 个聊天室</span><span class="sxs-lookup"><span data-stu-id="36521-332">An average of 1.5 chat rooms per user</span></span>

  - <span data-ttu-id="36521-333">每个聊天室每小时将产生 12 个轮询请求，每个轮询请求平均针对 10 个用户</span><span class="sxs-lookup"><span data-stu-id="36521-333">Each chat room results in 12 polling requests per hour, targeting an average of 10 users each</span></span>

</div>

<div>

## <a name="response-group-and-call-park"></a><span data-ttu-id="36521-334">响应组和呼叫驻留</span><span class="sxs-lookup"><span data-stu-id="36521-334">Response Group and Call Park</span></span>

<span data-ttu-id="36521-p137">假设 0.15% 的注册用户属于响应组。假设 0.02% 的注册用户在任何给定的时间点都有驻留呼叫。</span><span class="sxs-lookup"><span data-stu-id="36521-p137">We assume that 0.15% of registered users belong to response groups. We assume that 0.02% of registered users have parked calls at any given point of time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

