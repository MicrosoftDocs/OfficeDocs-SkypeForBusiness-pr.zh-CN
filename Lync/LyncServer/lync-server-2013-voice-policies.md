---
title: Lync Server 2013：语音策略
description: Lync Server 2013：语音策略。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice policies
ms:assetid: b7433c62-9d8c-48af-89a0-19f0d34806ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412891(v=OCS.15)
ms:contentKeyID: 48185223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b85e69c83a8f964d9114a83abe6978f040f044d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549828"
---
# <a name="voice-policies-in-lync-server-2013"></a><span data-ttu-id="d601f-103">Lync Server 2013 中的语音策略</span><span class="sxs-lookup"><span data-stu-id="d601f-103">Voice policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d601f-104">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d601f-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d601f-105">Lync Server *语音策略* 为分配了策略的每个用户、站点或组织定义以下各项：</span><span class="sxs-lookup"><span data-stu-id="d601f-105">Lync Server *voice policies* define the following for each user, site, or organization that is assigned the policy:</span></span>

  - <span data-ttu-id="d601f-106">一组可以启用或禁用的呼叫功能，以确定用户可使用的企业语音功能。</span><span class="sxs-lookup"><span data-stu-id="d601f-106">A set of calling features that can be enabled or disabled to determine the Enterprise Voice functionality available to users.</span></span>

  - <span data-ttu-id="d601f-107">一组公用电话交换网 (PSTN) 用法记录，可定义授权的呼叫类型。</span><span class="sxs-lookup"><span data-stu-id="d601f-107">A set of public switched telephone network (PSTN) usage records that define what types of calls are authorized.</span></span>

<div>

## <a name="planning-for-voice-policies"></a><span data-ttu-id="d601f-108">规划语音策略</span><span class="sxs-lookup"><span data-stu-id="d601f-108">Planning for Voice Policies</span></span>

<span data-ttu-id="d601f-109">以下步骤将帮助您规划您的企业语音部署所需的语音策略：</span><span class="sxs-lookup"><span data-stu-id="d601f-109">The following steps will help you plan the voice policies that you will need for your Enterprise Voice deployment:</span></span>

  - <span data-ttu-id="d601f-110">确定将如何配置全局语音策略（随产品一起安装的默认语音策略）。</span><span class="sxs-lookup"><span data-stu-id="d601f-110">Determine how you will configure your global voice policy (the default voice policy that is installed with the product).</span></span> <span data-ttu-id="d601f-111">此策略将应用于未明确分配站点级别或每用户策略的所有企业语音用户。</span><span class="sxs-lookup"><span data-stu-id="d601f-111">This policy will apply to all Enterprise Voice users who are not explicitly assigned a site-level or per-user policy.</span></span>

  - <span data-ttu-id="d601f-112">标识您可能需要的任何站点级别语音策略。</span><span class="sxs-lookup"><span data-stu-id="d601f-112">Identify any site-level voice policies that you might need.</span></span>

  - <span data-ttu-id="d601f-113">标识您可能需要的任何每用户语音策略。</span><span class="sxs-lookup"><span data-stu-id="d601f-113">Identify any per-user voice policies that you might need.</span></span>

  - <span data-ttu-id="d601f-114">确定要为每个语音策略启用的呼叫功能。</span><span class="sxs-lookup"><span data-stu-id="d601f-114">Decide which call features to enable for each voice policy.</span></span>

  - <span data-ttu-id="d601f-115">确定要为每个语音策略配置的 PSTN 用法记录。</span><span class="sxs-lookup"><span data-stu-id="d601f-115">Determine what PSTN usage records to configure for each voice policy.</span></span>

<div>

## <a name="voice-policy-scope"></a><span data-ttu-id="d601f-116">语音策略作用域</span><span class="sxs-lookup"><span data-stu-id="d601f-116">Voice Policy Scope</span></span>

<span data-ttu-id="d601f-117">*语音策略作用域* 确定可以应用策略的层次级别。</span><span class="sxs-lookup"><span data-stu-id="d601f-117">*Voice policy scope* determines the hierarchical level at which the policy can be applied.</span></span> <span data-ttu-id="d601f-118">在 Lync Server 中，可以使用从最具体到最常规的) 列出的以下范围级别 (配置语音策略。</span><span class="sxs-lookup"><span data-stu-id="d601f-118">In Lync Server, you can configure voice policies with the following scope levels (listed from the most specific to the most general).</span></span>

  - <span data-ttu-id="d601f-p103">**用户语音策略**：可分配给各个用户、组或联系人对象。这是最低级别的策略。可以部署用户语音策略，以便为某个站点上的特定用户或组启用某些功能，但不会为同一站点中的其他人启用这些功能。例如，您可能希望对某些员工禁用长途拨号。为了分配语音策略，会将联系人对象视为单个用户。</span><span class="sxs-lookup"><span data-stu-id="d601f-p103">**User voice policy** can be assigned to individual users, groups, or contact objects. This is the lowest level policy. User voice policies can be deployed to enable features for certain users or groups at a site, but not for others in the same site. For example, you may want to disable long distance dialing for some employees. For the purpose of assigning a voice policy, a contact object is treated as an individual user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d601f-124">我们建议您为在中央站点部署中注册的分支站点企业语音用户（或在 Survivable 分支机构上注册的用户）部署用户语音策略。</span><span class="sxs-lookup"><span data-stu-id="d601f-124">We recommend that you deploy a user voice policy for branch site Enterprise Voice users who are registered with the central site deployment, or users who are registered on a Survivable Branch Appliance.</span></span>

    
    </div>

  - <span data-ttu-id="d601f-p104">**站点语音策略**：应用于整个站点，但分配有用户语音策略的任何用户、组或联系人对象除外。要定义站点语音策略，必须指定应用此策略的站点。如果未分配用户语音策略，则将使用站点语音策略。</span><span class="sxs-lookup"><span data-stu-id="d601f-p104">**Site voice policy** applies to an entire site, except for any users, groups, or contact objects that are assigned a user voice policy. To define a site voice policy, you must specify the site to which the policy applies. If a user voice policy is not assigned, the site voice policy is used.</span></span>

  - <span data-ttu-id="d601f-128">**全局语音策略**：是随产品安装的默认语音策略。</span><span class="sxs-lookup"><span data-stu-id="d601f-128">**Global voice policy** is the default voice policy that is installed with the product.</span></span> <span data-ttu-id="d601f-129">您可以编辑全局语音策略来满足组织的特定需求，但不能重命名或删除此策略。</span><span class="sxs-lookup"><span data-stu-id="d601f-129">You can edit the global voice policy to meet the specific needs of your organization, but you cannot rename or delete it.</span></span> <span data-ttu-id="d601f-130">此语音策略适用于部署中的所有企业语音用户、组和联系人对象，除非您使用更具体的作用域配置和分配语音策略。</span><span class="sxs-lookup"><span data-stu-id="d601f-130">This voice policy applies to all Enterprise Voice users, groups, and contact objects in your deployment unless you configure and assign a voice policy with more specific scope.</span></span> <span data-ttu-id="d601f-131">如果要完全禁用此策略，请确保已将自定义策略分配给所有站点和用户。</span><span class="sxs-lookup"><span data-stu-id="d601f-131">If you want to disable this policy entirely, be sure that all sites and users have custom policies assigned to them.</span></span>

</div>

<div>

## <a name="call-features"></a><span data-ttu-id="d601f-132">呼叫功能</span><span class="sxs-lookup"><span data-stu-id="d601f-132">Call Features</span></span>

<span data-ttu-id="d601f-133">可以为每个语音策略启用或禁用以下呼叫功能：</span><span class="sxs-lookup"><span data-stu-id="d601f-133">You can enable or disable the following call features for each voice policy:</span></span>

  - <span data-ttu-id="d601f-p106">通过**呼叫转接**，用户可以将呼叫转接到其他电话或客户端设备。默认为启用。</span><span class="sxs-lookup"><span data-stu-id="d601f-p106">**Call forwarding** enables users to forward calls to other phones and client devices. Enabled by default.</span></span>

  - <span data-ttu-id="d601f-p107">通过**委派**，用户可以指定其他用户代表他们发送和接收呼叫。默认为启用。</span><span class="sxs-lookup"><span data-stu-id="d601f-p107">**Delegation** enables users to specify other users to send and receive calls on their behalf. Enabled by default.</span></span>

  - <span data-ttu-id="d601f-p108">通过**呼叫转移**，用户可以将呼叫转移到其他用户。默认为启用。</span><span class="sxs-lookup"><span data-stu-id="d601f-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>

  - <span data-ttu-id="d601f-p109">通过**呼叫寄存**，用户可以寄存呼叫，然后从其他电话或客户端接听呼叫。默认为禁用。</span><span class="sxs-lookup"><span data-stu-id="d601f-p109">**Call park** enables users to park calls and then pick up the call from a different phone or client. Disabled by default.</span></span>

  - <span data-ttu-id="d601f-p110">**同时响铃**使传入呼叫可以在其他电话（例如，移动电话）或其他终结点设备上响铃。默认为启用。</span><span class="sxs-lookup"><span data-stu-id="d601f-p110">**Simultaneous ringing** enables incoming calls to ring on an additional phone (for example, a mobile phone) or other endpoint devices. Enabled by default.</span></span>

  - <span data-ttu-id="d601f-p111">通过**团队呼叫**，指定团队中的用户可以为团队中的其他成员应答呼叫。默认为启用。</span><span class="sxs-lookup"><span data-stu-id="d601f-p111">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>

  - <span data-ttu-id="d601f-p112">**PSTN 重新路由**可以在 WAN 拥堵或不可用时在公用电话交换网 (PSTN) 上重新路由分配有此策略的用户向其他企业用户发出的呼叫。默认为启用。</span><span class="sxs-lookup"><span data-stu-id="d601f-p112">**PSTN reroute** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable. Enabled by default.</span></span>

  - <span data-ttu-id="d601f-p113">通过**带宽策略覆盖**，管理员可以覆盖特定用户的呼叫允许控制策略决策。默认为禁用。</span><span class="sxs-lookup"><span data-stu-id="d601f-p113">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user. Disabled by default.</span></span>

  - <span data-ttu-id="d601f-150">通过**恶意呼叫跟踪**，用户可以使用 Lync 客户端报告恶意呼叫，然后在呼叫详细信息记录中标记此类呼叫。</span><span class="sxs-lookup"><span data-stu-id="d601f-150">**Malicious call tracing** enables users to report malicious calls by using the Lync client, and then flags such calls in the call detail records.</span></span> <span data-ttu-id="d601f-151">默认为禁用。</span><span class="sxs-lookup"><span data-stu-id="d601f-151">Disabled by default.</span></span>

  - <span data-ttu-id="d601f-152">当配置同时响铃，电话关机、没有电或不在服务区，以及基于计时器值时，**语音邮件转义**可防止将呼叫立即路由到用户的移动电话语音邮件系统。</span><span class="sxs-lookup"><span data-stu-id="d601f-152">**Voicemail escape** prevents calls from being immediately routed to the user’s mobile phone voicemail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range, and is based on a timer value.</span></span> <span data-ttu-id="d601f-153">此设置会启用和禁用计时器，并设置计时器的值。</span><span class="sxs-lookup"><span data-stu-id="d601f-153">This setting enables and disables the timer and sets the value of the timer.</span></span> <span data-ttu-id="d601f-154">只能使用 Lync Server 命令行管理程序进行配置。</span><span class="sxs-lookup"><span data-stu-id="d601f-154">It can be configured only by using the Lync Server Management Shell.</span></span> <span data-ttu-id="d601f-155">默认情况下处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="d601f-155">Disabled by default.</span></span>

  - <span data-ttu-id="d601f-p116">通过**呼叫转接和同时响铃 PSTN 用法**，管理员可以指定与用于呼叫转接和同时响铃的语音策略相同的 PSTN 用法，将呼叫转接和同时响铃仅限制为内部 Lync 用户，或指定与语音策略的 PSTN 用法有所不同的自定义 PSTN 用法。默认情况下会使用与用于呼叫转接和同时响铃的语音策略相同的 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="d601f-p116">**Call forwarding and simultaneous ringing PSTN usages** enables administrators to specify the same PSTN usage as the voice policy for call forwarding and simultaneous ringing, restrict call forwarding and simultaneous ringing to internal Lync users only, or specify a custom PSTN usage that is different from the voice policy’s PSTN usage. The default is to use the same PSTN usage as the voice policy for call forwarding and simultaneous ringing.</span></span>

</div>

<div>

## <a name="pstn-usage-records"></a><span data-ttu-id="d601f-158">PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="d601f-158">PSTN Usage Records</span></span>

<span data-ttu-id="d601f-159">每个语音策略应具有一条或多条关联的 PSTN 用法记录。</span><span class="sxs-lookup"><span data-stu-id="d601f-159">Each voice policy should have one or more associated PSTN usage records.</span></span> <span data-ttu-id="d601f-160">PSTN 用法可以与语音策略相关联，以仅用于同时响铃和呼叫转接。</span><span class="sxs-lookup"><span data-stu-id="d601f-160">PSTN usages can be associated with a voice policy for the purpose of simultaneous ringing and call forwarding only.</span></span> <span data-ttu-id="d601f-161">有关规划 PSTN 用法记录的详细信息，请参阅 [Lync Server 2013 中的 pstn 用法记录](lync-server-2013-pstn-usage-records.md)。</span><span class="sxs-lookup"><span data-stu-id="d601f-161">For details about planning PSTN usage records, see [PSTN usage records in Lync Server 2013](lync-server-2013-pstn-usage-records.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d601f-p118">PSTN 用法顺序至关重要，因为在将用户与路由相匹配时，出站路由功能会从上到下比较 PSTN 用法。如果第一个用法与呼叫路由相匹配，则会使用该路由。如果不匹配，则出站路由功能会查看列表中的下一个 PSTN 用法，一直持续到找到匹配项为止。实际上，如果列表中的第一个 PSTN 用法不可用，则后续的 PSTN 用法将提供备份。</span><span class="sxs-lookup"><span data-stu-id="d601f-p118">PSTN usage order is critical because in matching users to routes, the outbound routing functionality compares PSTN usages from top to bottom. If the first usage matches the call route, that route is used. If not, the outbound routing functionality looks at the next PSTN usage on the list and continues until a match is found. In effect, the subsequent PSTN usages provide backup if the first one on the list is unavailable.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

