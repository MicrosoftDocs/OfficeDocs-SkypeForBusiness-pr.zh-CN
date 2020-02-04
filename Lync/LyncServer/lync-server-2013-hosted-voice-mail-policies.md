---
title: Lync Server 2013：托管语音邮件策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 811f975868dad7bc0fcf6d5a2867ca2f3b81cd59
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="100b3-102">Lync Server 2013 中的托管语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="100b3-102">Hosted voice mail policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="100b3-103">_**主题上次修改时间：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="100b3-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="100b3-104">*托管语音邮件策略*向 Lync Server 2013 ExUM 路由应用程序提供有关邮箱位于托管 Exchange 服务上的用户的路由位置的信息。</span><span class="sxs-lookup"><span data-stu-id="100b3-104">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="100b3-105">仅在与托管 Exchange UM 的 Lync Server 2013 集成中需要托管语音邮件策略。</span><span class="sxs-lookup"><span data-stu-id="100b3-105">Hosted voice mail policies are required only for Lync Server 2013 integration with hosted Exchange UM.</span></span> <span data-ttu-id="100b3-106">它们不是与本地 Exchange UM 集成所必需的。</span><span class="sxs-lookup"><span data-stu-id="100b3-106">They are not needed for integration with on-premises Exchange UM.</span></span>



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a><span data-ttu-id="100b3-107">托管语音邮件策略作用域</span><span class="sxs-lookup"><span data-stu-id="100b3-107">Hosted Voice Mail Policy Scope</span></span>

<span data-ttu-id="100b3-108">托管语音邮件策略范围确定策略适用的层次结构级别。</span><span class="sxs-lookup"><span data-stu-id="100b3-108">Hosted voice mail policy scope determines the hierarchical level at which the policy applies.</span></span> <span data-ttu-id="100b3-109">你可以配置具有以下范围级别的托管语音邮件策略：</span><span class="sxs-lookup"><span data-stu-id="100b3-109">You can configure hosted voice mail policies with the following scope levels:</span></span>

  - <span data-ttu-id="100b3-110">*全局*策略可能会影响 Lync Server 2013 部署中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="100b3-110">The *global* policy can potentially affect all users in the Lync Server 2013 deployment.</span></span> <span data-ttu-id="100b3-111">如果用户已启用托管 Exchange UM 访问，并且尚未分配每用户策略，并且尚未向用户的网站分配网站策略，则应用全局策略。</span><span class="sxs-lookup"><span data-stu-id="100b3-111">If a user is enabled for hosted Exchange UM access and has not been assigned a per-user policy, and if a site policy has not been assigned to the user’s site, the global policy applies.</span></span> <span data-ttu-id="100b3-112">全局策略随 Lync Server 2013 一起安装。</span><span class="sxs-lookup"><span data-stu-id="100b3-112">The global policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="100b3-113">你可以对其进行修改以满足你的需求，但不能重命名或删除它。</span><span class="sxs-lookup"><span data-stu-id="100b3-113">You can modify it to meet your needs, but you cannot rename or delete it.</span></span>

  - <span data-ttu-id="100b3-114">*网站*策略可能会影响托管在定义了该策略的网站上的所有用户。</span><span class="sxs-lookup"><span data-stu-id="100b3-114">A *site* policy can affect all users that are homed on the site for which the policy is defined.</span></span> <span data-ttu-id="100b3-115">如果用户已配置为托管 Exchange UM 访问，并且尚未分配每用户策略，则应用网站策略。</span><span class="sxs-lookup"><span data-stu-id="100b3-115">If a user is configured for hosted Exchange UM access and has not been assigned a per-user policy, the site policy applies.</span></span>

  - <span data-ttu-id="100b3-116">*每用户*策略只能影响单个用户或组。</span><span class="sxs-lookup"><span data-stu-id="100b3-116">A *per-user* policy can affect only individual users or groups.</span></span> <span data-ttu-id="100b3-117">若要强制执行每用户策略，必须将策略显式分配给单个用户、组和联系人对象。</span><span class="sxs-lookup"><span data-stu-id="100b3-117">To enforce a per-user policy, you must explicitly assign the policy to individual users, groups, and contact objects.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="100b3-118">在大多数情况下，只需要一个托管语音邮件策略。</span><span class="sxs-lookup"><span data-stu-id="100b3-118">In most cases, only one hosted voice mail policy is required.</span></span> <span data-ttu-id="100b3-119">你可以经常修改全局策略以满足你的所有需求。</span><span class="sxs-lookup"><span data-stu-id="100b3-119">You can often modify the global policy to meet all your needs.</span></span> <span data-ttu-id="100b3-120">如果你部署多个托管语音邮件策略，则所有此类策略都具有每用户范围。</span><span class="sxs-lookup"><span data-stu-id="100b3-120">If you deploy multiple hosted voice mail policies, all such policies have per-user scope.</span></span>



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a><span data-ttu-id="100b3-121">托管语音邮件策略属性</span><span class="sxs-lookup"><span data-stu-id="100b3-121">Hosted Voice Mail Policy Attributes</span></span>

<span data-ttu-id="100b3-122">语音邮件策略定义 Lync Server 2013 ExUM 路由应用程序在发送到托管 Exchange UM 实现的邀请邮件的请求 URI 中插入的两个属性：</span><span class="sxs-lookup"><span data-stu-id="100b3-122">A voice mail policy defines two attributes that the Lync Server 2013 ExUM Routing application inserts in the request URI of an INVITE message that is sent to the hosted Exchange UM implementation:</span></span>

  - <span data-ttu-id="100b3-123">**目标：** 托管 Exchange UM 服务的完全限定的域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="100b3-123">**Destination:** The fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="100b3-124">此值由本地 Lync Server Edge 服务器用于路由用途。</span><span class="sxs-lookup"><span data-stu-id="100b3-124">This value is used by the on-premises Lync Server Edge Server for routing purposes.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="100b3-125">Exchange Online 的 FQDN 为 exap.um.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="100b3-125">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

    
    </div>

  - <span data-ttu-id="100b3-126">**组织：** 寄存 Lync Server 2013 用户邮箱的托管 Exchange UM 服务上的租户的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="100b3-126">**Organization:** The FQDN of the tenant on the hosted Exchange UM service that homes your Lync Server 2013 users’ mailboxes.</span></span> <span data-ttu-id="100b3-127">语音邮件策略可以包含多个组织。</span><span class="sxs-lookup"><span data-stu-id="100b3-127">A voice mail policy can contain multiple organizations.</span></span> <span data-ttu-id="100b3-128">如果策略中包含多个组织，则此属性必须为主 Lync Server 2013 用户邮箱的 Exchange Server 租户的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="100b3-128">If more than one organization is included in the policy, this attribute must be a comma-separated list of the Exchange Server tenants that home your Lync Server 2013 user mailboxes.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="100b3-129">托管 Exchange UM 服务的租户管理员将为目标和组织属性设置提供必要的值。</span><span class="sxs-lookup"><span data-stu-id="100b3-129">The tenant administrator of your hosted Exchange UM service will provide the necessary values for your Destination and Organization attribute settings.</span></span> <span data-ttu-id="100b3-130">若要配置你的策略，你必须运行 CsHostedVoicemailPolicy cmdlet 或使用 CsHostedVoicemailPolicy cmdlet 修改存在的（例如，全局策略）。</span><span class="sxs-lookup"><span data-stu-id="100b3-130">To configure your policy, you must run the New-CsHostedVoicemailPolicy cmdlet or use the Set-CsHostedVoicemailPolicy cmdlet to modify one that exists (for example, the global policy).</span></span>



</div>

<span data-ttu-id="100b3-131">有关管理托管语音邮件策略的详细信息，请参阅以下 cmdlet 的 Lync Server Management Shell 文档：</span><span class="sxs-lookup"><span data-stu-id="100b3-131">For details about managing hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="100b3-132">新-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="100b3-132">New-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="100b3-133">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="100b3-133">Set-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="100b3-134">CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="100b3-134">Get-CsHostedVoicemailPolicy</span></span>

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a><span data-ttu-id="100b3-135">每用户语音邮件策略分配</span><span class="sxs-lookup"><span data-stu-id="100b3-135">Per-User Voice Mail Policy Assignment</span></span>

<span data-ttu-id="100b3-136">如果托管语音邮件策略是使用每用户范围定义的，则必须显式分配它。</span><span class="sxs-lookup"><span data-stu-id="100b3-136">If your hosted voice mail policy is defined with per-user scope, you must explicitly assign it.</span></span> <span data-ttu-id="100b3-137">你可以运行 CsHostedVoicemailPolicy cmdlet，将策略分配给单个用户或组。</span><span class="sxs-lookup"><span data-stu-id="100b3-137">You can run the Grant-CsHostedVoicemailPolicy cmdlet to assign the policy to individual users or groups.</span></span>

<span data-ttu-id="100b3-138">有关分配或删除每用户托管语音邮件策略的详细信息，请参阅以下 cmdlet 的 Lync Server Management Shell 文档：</span><span class="sxs-lookup"><span data-stu-id="100b3-138">For details about assigning or removing a per-user hosted voice mail policy, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="100b3-139">授权-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="100b3-139">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="100b3-140">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="100b3-140">Remove-CsHostedVoicemailPolicy</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

