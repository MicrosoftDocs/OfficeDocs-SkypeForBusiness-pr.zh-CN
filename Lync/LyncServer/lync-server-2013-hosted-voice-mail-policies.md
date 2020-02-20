---
title: Lync Server 2013：托管的语音邮件策略
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
ms.openlocfilehash: 16570331d0d7e154388c51ecb11be591bf3bbd05
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="3f0f6-102">Lync Server 2013 中的托管语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="3f0f6-102">Hosted voice mail policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f0f6-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="3f0f6-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="3f0f6-104">*托管的语音邮件策略*向 Lync Server 2013 ExUM 路由应用程序提供有关邮箱位于托管 Exchange 服务上的用户的路由呼叫的位置的信息。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-104">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3f0f6-105">仅在与托管 Exchange UM 集成 Lync Server 2013 时，才需要托管语音邮件策略。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-105">Hosted voice mail policies are required only for Lync Server 2013 integration with hosted Exchange UM.</span></span> <span data-ttu-id="3f0f6-106">与本地 Exchange UM 的集成不需要它们。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-106">They are not needed for integration with on-premises Exchange UM.</span></span>



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a><span data-ttu-id="3f0f6-107">托管的语音邮件策略作用域</span><span class="sxs-lookup"><span data-stu-id="3f0f6-107">Hosted Voice Mail Policy Scope</span></span>

<span data-ttu-id="3f0f6-108">托管语音邮件策略作用域确定策略适用的层次结构级别。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-108">Hosted voice mail policy scope determines the hierarchical level at which the policy applies.</span></span> <span data-ttu-id="3f0f6-109">您可以配置具有以下范围级别的托管语音邮件策略：</span><span class="sxs-lookup"><span data-stu-id="3f0f6-109">You can configure hosted voice mail policies with the following scope levels:</span></span>

  - <span data-ttu-id="3f0f6-110">*全局*策略可能会影响 Lync Server 2013 部署中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-110">The *global* policy can potentially affect all users in the Lync Server 2013 deployment.</span></span> <span data-ttu-id="3f0f6-111">如果为用户启用了托管 Exchange UM 访问且尚未分配每用户策略，且尚未向用户的网站分配网站策略，则应用全局策略。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-111">If a user is enabled for hosted Exchange UM access and has not been assigned a per-user policy, and if a site policy has not been assigned to the user’s site, the global policy applies.</span></span> <span data-ttu-id="3f0f6-112">已使用 Lync Server 2013 安装全局策略。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-112">The global policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="3f0f6-113">可以根据需要修改该策略，但不能重命名或删除它。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-113">You can modify it to meet your needs, but you cannot rename or delete it.</span></span>

  - <span data-ttu-id="3f0f6-114">*网站*策略可能会影响托管在为其定义策略的网站上的所有用户。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-114">A *site* policy can affect all users that are homed on the site for which the policy is defined.</span></span> <span data-ttu-id="3f0f6-115">如果为用户配置了托管 Exchange UM 访问且尚未分配每用户策略，则会应用站点策略。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-115">If a user is configured for hosted Exchange UM access and has not been assigned a per-user policy, the site policy applies.</span></span>

  - <span data-ttu-id="3f0f6-116">*每用户*策略只能影响单个用户或组。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-116">A *per-user* policy can affect only individual users or groups.</span></span> <span data-ttu-id="3f0f6-117">若要强制实施每用户策略，您必须将策略明确分配给各个用户、组和联系人对象。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-117">To enforce a per-user policy, you must explicitly assign the policy to individual users, groups, and contact objects.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3f0f6-118">在大多数情况下，只需要一个托管的语音邮件策略。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-118">In most cases, only one hosted voice mail policy is required.</span></span> <span data-ttu-id="3f0f6-119">您通常可以修改全局策略以满足您的所有需求。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-119">You can often modify the global policy to meet all your needs.</span></span> <span data-ttu-id="3f0f6-120">如果您部署多个托管的语音邮件策略，则所有此类策略都具有每用户作用域。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-120">If you deploy multiple hosted voice mail policies, all such policies have per-user scope.</span></span>



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a><span data-ttu-id="3f0f6-121">托管的语音邮件策略属性</span><span class="sxs-lookup"><span data-stu-id="3f0f6-121">Hosted Voice Mail Policy Attributes</span></span>

<span data-ttu-id="3f0f6-122">语音邮件策略定义了 Lync Server 2013 ExUM 路由应用程序在发送到托管 Exchange UM 实现的邀请邮件的请求 URI 中插入的两个属性：</span><span class="sxs-lookup"><span data-stu-id="3f0f6-122">A voice mail policy defines two attributes that the Lync Server 2013 ExUM Routing application inserts in the request URI of an INVITE message that is sent to the hosted Exchange UM implementation:</span></span>

  - <span data-ttu-id="3f0f6-123">**目标：** 托管 Exchange UM 服务的完全限定的域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-123">**Destination:** The fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="3f0f6-124">本地 Lync Server 边缘服务器使用此值进行路由。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-124">This value is used by the on-premises Lync Server Edge Server for routing purposes.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3f0f6-125">Exchange Online 的 FQDN 为 exap.um.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-125">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

    
    </div>

  - <span data-ttu-id="3f0f6-126">**组织：** 承载 Lync Server 2013 用户邮箱的托管 Exchange UM 服务上的租户的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-126">**Organization:** The FQDN of the tenant on the hosted Exchange UM service that homes your Lync Server 2013 users’ mailboxes.</span></span> <span data-ttu-id="3f0f6-127">语音邮件策略可以包含多个组织。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-127">A voice mail policy can contain multiple organizations.</span></span> <span data-ttu-id="3f0f6-128">如果策略中包含多个组织，则此属性必须是主你的 Lync Server 2013 用户邮箱的 Exchange Server 租户的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-128">If more than one organization is included in the policy, this attribute must be a comma-separated list of the Exchange Server tenants that home your Lync Server 2013 user mailboxes.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3f0f6-129">托管 Exchange UM 服务的租户管理员将为您的目标和组织属性设置提供必要的值。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-129">The tenant administrator of your hosted Exchange UM service will provide the necessary values for your Destination and Organization attribute settings.</span></span> <span data-ttu-id="3f0f6-130">若要配置策略，您必须运行 CsHostedVoicemailPolicy cmdlet 或使用 CsHostedVoicemailPolicy cmdlet 修改存在的项（例如，全局策略）。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-130">To configure your policy, you must run the New-CsHostedVoicemailPolicy cmdlet or use the Set-CsHostedVoicemailPolicy cmdlet to modify one that exists (for example, the global policy).</span></span>



</div>

<span data-ttu-id="3f0f6-131">有关管理托管的语音邮件策略的详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3f0f6-131">For details about managing hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="3f0f6-132">新 CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="3f0f6-132">New-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="3f0f6-133">CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="3f0f6-133">Set-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="3f0f6-134">CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="3f0f6-134">Get-CsHostedVoicemailPolicy</span></span>

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a><span data-ttu-id="3f0f6-135">每用户语音邮件策略分配</span><span class="sxs-lookup"><span data-stu-id="3f0f6-135">Per-User Voice Mail Policy Assignment</span></span>

<span data-ttu-id="3f0f6-136">如果托管的语音邮件策略是使用每用户作用域定义的，则必须显式分配它。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-136">If your hosted voice mail policy is defined with per-user scope, you must explicitly assign it.</span></span> <span data-ttu-id="3f0f6-137">您可以运行 CsHostedVoicemailPolicy cmdlet，将策略分配给单个用户或组。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-137">You can run the Grant-CsHostedVoicemailPolicy cmdlet to assign the policy to individual users or groups.</span></span>

<span data-ttu-id="3f0f6-138">有关分配或删除每用户托管语音邮件策略的详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3f0f6-138">For details about assigning or removing a per-user hosted voice mail policy, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="3f0f6-139">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="3f0f6-139">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="3f0f6-140">CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="3f0f6-140">Remove-CsHostedVoicemailPolicy</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

