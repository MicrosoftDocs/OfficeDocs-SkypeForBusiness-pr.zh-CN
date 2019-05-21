---
title: 在 Teams 中管理资源帐户
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: 了解有关在 Microsoft 团队中管理资源帐户的信息
ms.openlocfilehash: d8f3e2893962524c09340ef80ccf13376733d4d4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291505"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="32d5d-103">在 Microsoft Teams 中管理资源帐户</span><span class="sxs-lookup"><span data-stu-id="32d5d-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="32d5d-104">资源帐户在 Azure Active Directory 中也称为已禁用的用户对象, 并且可用于表示常规资源。</span><span class="sxs-lookup"><span data-stu-id="32d5d-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="32d5d-105">例如, 在 Exchange 中, 它可能用于表示会议室, 并允许他们拥有电话号码。</span><span class="sxs-lookup"><span data-stu-id="32d5d-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="32d5d-106">资源帐户可以托管在 Microsoft 365 中, 也可以在本地使用 Skype for Business 服务器托管, 这些帐户使用 Powershell 命令创建。</span><span class="sxs-lookup"><span data-stu-id="32d5d-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business server, and these accounts are created using Powershell commands.</span></span>

<span data-ttu-id="32d5d-107">在 Microsoft 团队或 Skype for business Online 中, 每个呼叫队列或自动助理都必须具有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="32d5d-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="32d5d-108">资源帐户是否需要分配的电话号码取决于关联呼叫队列或自动助理的预期用途。</span><span class="sxs-lookup"><span data-stu-id="32d5d-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="32d5d-109">在将电话号码分配给资源帐户之前, 请参阅本文底部的 "呼叫队列" 和 "自动助理" 中链接的文章。</span><span class="sxs-lookup"><span data-stu-id="32d5d-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="32d5d-110">本文适用于 Microsoft 团队和 Skype for business Online。</span><span class="sxs-lookup"><span data-stu-id="32d5d-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="32d5d-111">对于驻留在 Skype for business Server 2019 上的资源帐户, 请参阅[配置云自动助理](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)。</span><span class="sxs-lookup"><span data-stu-id="32d5d-111">For resource accounts homed on Skype for Business Server 2019, see [Configure Cloud auto attendants](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant).</span></span>

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a><span data-ttu-id="32d5d-112">将电话号码分配给资源帐户的先决条件</span><span class="sxs-lookup"><span data-stu-id="32d5d-112">Prerequisites to assign a phone number to a resource account</span></span>

<span data-ttu-id="32d5d-113">若要开始使用, 请务必记住以下几点:</span><span class="sxs-lookup"><span data-stu-id="32d5d-113">To get started it's important to remember a few things:</span></span>
  
- <span data-ttu-id="32d5d-114">需要使用自动助理或呼叫队列才能拥有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="32d5d-114">An auto attendant or call queue is required to have an associated resource account.</span></span> 
- <span data-ttu-id="32d5d-115">如果资源帐户将分配给顶层自动助理或呼叫队列, 则该帐户将需要已分配的电话号码。</span><span class="sxs-lookup"><span data-stu-id="32d5d-115">The resource account will need an assigned phone number if it will be assigned to a top level auto attendant or call queue.</span></span> 
- <span data-ttu-id="32d5d-116">如果自动助理或呼叫队列嵌套在顶级自动助理下方, 并且如果你希望将多个点输入到自动助理的结构中并调用队列, 则关联的资源帐户仅需要电话号码。</span><span class="sxs-lookup"><span data-stu-id="32d5d-116">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>
- <span data-ttu-id="32d5d-117">您只需向分配了电话号码的资源帐户授予许可证。</span><span class="sxs-lookup"><span data-stu-id="32d5d-117">You only need to license the resource accounts with a phone number assigned to them.</span></span> <span data-ttu-id="32d5d-118">在嵌套的自动助理或呼叫队列中, 如果自动助理或呼叫队列没有与之关联的电话号码, 则无需向其授予许可证。</span><span class="sxs-lookup"><span data-stu-id="32d5d-118">In a nested auto attendant or call queue, you do not need to license the rest of the auto attendants or call queues if they do not have phone numbers associated with them.</span></span>
- <span data-ttu-id="32d5d-119">如果您分配的电话号码与直接路由一起使用, 并且您有企业版 E1 或 E3 许可证, 则必须购买并向您分配电话系统许可证, 您就是要使用的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="32d5d-119">If you are assigning a phone number that is used with Direct Routing and you have an Enterprise E1 or E3 licenses you must buy and assign a Phone System license to your the resource account that you will be using.</span></span> <span data-ttu-id="32d5d-120">如果您有企业版 E5 许可证, 则电话系统已包含, 因此无需购买一个。</span><span class="sxs-lookup"><span data-stu-id="32d5d-120">If you have an Enterprise E5 license, Phone System is already included so there's no need to buy one.</span></span> 
- <span data-ttu-id="32d5d-121">如果你改为分配 Microsoft 服务号码, 你需要使用手机系统加载项和呼叫计划\(\)获取并将以下许可证分配给你的资源帐户 Office 365 企业版 E1、E3 或 E5。</span><span class="sxs-lookup"><span data-stu-id="32d5d-121">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>
- <span data-ttu-id="32d5d-122">您可以为您的资源帐户分配直接路由混合号码。</span><span class="sxs-lookup"><span data-stu-id="32d5d-122">You can assign a Direct Routing Hybrid number to your resource account.</span></span>  <span data-ttu-id="32d5d-123">有关详细信息, 请参阅[规划直接路由](direct-routing-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="32d5d-123">See [Plan Direct Routing](direct-routing-plan.md) for details.</span></span>
- <span data-ttu-id="32d5d-124">对于 Microsoft 通话计划, 您只能将您在**Microsoft 团队管理中心**或从其他服务提供商移植到资源帐户的收费电话号码和免费服务电话号码分配给您。</span><span class="sxs-lookup"><span data-stu-id="32d5d-124">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or ported from another service provider to a resource account.</span></span> <span data-ttu-id="32d5d-125">若要获取并使用免费电话号码，则需要设置通信点数。</span><span class="sxs-lookup"><span data-stu-id="32d5d-125">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

> [!NOTE]
> <span data-ttu-id="32d5d-126">仅为 Microsoft 团队用户和代理支持分配给自动助理和呼叫队列的资源帐户的直接路由服务号码。</span><span class="sxs-lookup"><span data-stu-id="32d5d-126">Direct Routing service numbers assigned to resource accounts for auto attendant and call queues is supported for Microsoft Teams users and agents only.</span></span>
>
> <span data-ttu-id="32d5d-127">Microsoft 正在为应用程序 (如云自动助理和呼叫队列) 处理合适的许可模型, 现在你需要使用用户许可模型。</span><span class="sxs-lookup"><span data-stu-id="32d5d-127">Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>
>
> <span data-ttu-id="32d5d-128">若要将呼叫重定向到您的组织中联机的人员, 他们必须具有**电话系统**许可证并启用企业语音或拥有 Office 365 通话计划。</span><span class="sxs-lookup"><span data-stu-id="32d5d-128">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="32d5d-129">请参阅[分配 Microsoft 团队许可证](assign-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="32d5d-129">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="32d5d-130">要为他们启用企业语音，可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="32d5d-130">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="32d5d-131">例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="32d5d-131">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
>
> <span data-ttu-id="32d5d-132">用户 (订阅者) 电话号码不能分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="32d5d-132">User (subscriber) phone numbers can't be assigned to a resource account.</span></span> <span data-ttu-id="32d5d-133">仅可使用收费电话或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="32d5d-133">Only service toll or toll-free phone numbers can be used.</span></span>
>
> <span data-ttu-id="32d5d-134">如果您在美国以外, 则不能使用 Microsoft 团队管理中心获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="32d5d-134">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="32d5d-135">转到 "[管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)" 以了解如何从美国以外的国家进行管理。</span><span class="sxs-lookup"><span data-stu-id="32d5d-135">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

### <a name="phone-numbers"></a><span data-ttu-id="32d5d-136">电话号码</span><span class="sxs-lookup"><span data-stu-id="32d5d-136">Phone numbers</span></span>

<span data-ttu-id="32d5d-137">创建使用电话号码的资源帐户需要按以下顺序执行以下任务:</span><span class="sxs-lookup"><span data-stu-id="32d5d-137">Creating a resource account that uses a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="32d5d-138">转接或获取收费或免费服务号码。</span><span class="sxs-lookup"><span data-stu-id="32d5d-138">Transfer or get a toll or toll-free service number.</span></span> <span data-ttu-id="32d5d-139">该号码不能分配给任何其他语音服务或资源帐户。</span><span class="sxs-lookup"><span data-stu-id="32d5d-139">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="32d5d-140">将电话号码分配给资源帐户之前, 您需要购买或移植您现有的收费或免费服务号码。</span><span class="sxs-lookup"><span data-stu-id="32d5d-140">Before you assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="32d5d-141">获得收费或免费服务电话号码后, 这些电话号码将显示在**Microsoft 团队管理中心** > **的语音** > **电话号码**中, 并且列出的**号码类型**将按**服务免费**列出。</span><span class="sxs-lookup"><span data-stu-id="32d5d-141">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="32d5d-142">若要获取你的服务号码, 请参阅[获取服务电话号码](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)或要转移现有服务号码, 请参阅[将电话号码转移到 Office 365](transfer-phone-numbers-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="32d5d-142">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>

2. <span data-ttu-id="32d5d-143">购买电话系统许可证和通话计划。</span><span class="sxs-lookup"><span data-stu-id="32d5d-143">Buy a Phone System license and a Calling Plan.</span></span> <span data-ttu-id="32d5d-144">参阅</span><span class="sxs-lookup"><span data-stu-id="32d5d-144">See:</span></span>  
   - [<span data-ttu-id="32d5d-145">Office 365 企业版（E1 和 E3）</span><span class="sxs-lookup"><span data-stu-id="32d5d-145">Office 365 Enterprise E1 and E3</span></span>](teams-add-on-licensing/office-365-enterprise-e1-e3.md)
   - [<span data-ttu-id="32d5d-146">Office 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="32d5d-146">Office 365 Enterprise E5</span></span>](teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing.md)
   - <span data-ttu-id="32d5d-147">[Office 365 企业版 E5 Business 软件](https://products.office.com/business/office-365-enterprise-e5-business-software)- [通话计划 (适用于 office 365](calling-plans-for-office-365.md) )</span><span class="sxs-lookup"><span data-stu-id="32d5d-147">[Office 365 Enterprise E5 Business Software](https://products.office.com/business/office-365-enterprise-e5-business-software)- [Calling Plans for Office 365](calling-plans-for-office-365.md)</span></span>

3. <span data-ttu-id="32d5d-148">创建新的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="32d5d-148">Create a new resource account.</span></span> <span data-ttu-id="32d5d-149">请参阅[在 Microsoft 团队管理中心创建资源帐户](#create-a-resource-account-in-microsoft-teams-admin-center)或[在 Powershell 中创建资源帐户](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="32d5d-149">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
4. <span data-ttu-id="32d5d-150">将电话系统许可证和呼叫计划分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="32d5d-150">Assign the Phone System license and the Calling Plan to the resource account.</span></span> <span data-ttu-id="32d5d-151">请参阅[分配 Microsoft 团队许可证](assign-teams-licenses.md)和[将许可证分配给一个用户](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user)。</span><span class="sxs-lookup"><span data-stu-id="32d5d-151">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>
5. <span data-ttu-id="32d5d-152">将服务号码分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="32d5d-152">Assign the service number to the resource account.</span></span> <span data-ttu-id="32d5d-153">请参阅[分配/取消分配电话号码和服务](#assignunassign-phone-numbers-and-services)。</span><span class="sxs-lookup"><span data-stu-id="32d5d-153">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>

<span data-ttu-id="32d5d-154">不需要电话号码的资源帐户可以忽略步骤1、2和5。</span><span class="sxs-lookup"><span data-stu-id="32d5d-154">A resource account that doesn't require a phone number can omit steps 1,2, and 5.</span></span>

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="32d5d-155">在 Microsoft 团队管理中心中创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="32d5d-155">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="32d5d-156">购买电话系统许可证和呼叫计划之后, 使用 Microsoft 团队管理中心, 导航到**组织范围的设置** > **资源帐户**。</span><span class="sxs-lookup"><span data-stu-id="32d5d-156">After you've bought a Phone System license and a Calling Plan, using Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**.</span></span> 

![.asd](media/r-a-master.png)

![数字1](media/sfbcallout1.png)

<span data-ttu-id="32d5d-159">若要创建新的资源帐户, 请单击 " **+ 新建帐户**"。</span><span class="sxs-lookup"><span data-stu-id="32d5d-159">To create a new resource account click **+ New account**.</span></span> <span data-ttu-id="32d5d-160">在弹出窗口中, 填写资源帐户的 "显示名称" 和 "用户名" (域名应自动填充), 然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="32d5d-160">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![资源帐户](media/res-acct.png)

<span data-ttu-id="32d5d-162">接下来, 在 O365 管理中心中对资源帐户应用许可证, 如在[Office 365 for business 中向用户分配许可证](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)中所述。</span><span class="sxs-lookup"><span data-stu-id="32d5d-162">Next, apply a license to the resource account in the O365 Admin center, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="32d5d-163">分配/取消分配电话号码和服务</span><span class="sxs-lookup"><span data-stu-id="32d5d-163">Assign/Unassign phone numbers and services</span></span>

<span data-ttu-id="32d5d-164">![编号 3](media/sfbcallout3.png)创建资源帐户并分配许可证后, 您可以单击 "**分配/取消**分配" 将呼叫计划服务编号分配给资源帐户, 或者将资源帐户分配给指定的自动助理或呼叫队列已存在。</span><span class="sxs-lookup"><span data-stu-id="32d5d-164">![number 3](media/sfbcallout3.png) Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a Calling Plan service number to the resource account, or assign the resource account to an auto attendant or call queue that already exists.</span></span> <span data-ttu-id="32d5d-165">分配直接路由号码只能使用 Cmdlet 完成。</span><span class="sxs-lookup"><span data-stu-id="32d5d-165">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="32d5d-166">如果您的通话队列或自动助理仍需创建, 则可以在创建资源帐户时将其链接在一起。</span><span class="sxs-lookup"><span data-stu-id="32d5d-166">If your call queue or auto attendant still needs to be created, you can link the resource account while you create it.</span></span> <span data-ttu-id="32d5d-167">完成后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="32d5d-167">Click **Save** when you are done.</span></span>

<span data-ttu-id="32d5d-168">使用以下 cmdlet 分配直接路由号码:</span><span class="sxs-lookup"><span data-stu-id="32d5d-168">Use the following cmdlet to assign a direct routing number:</span></span> 
``` Powershell
Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber tel:+14250000000
```

> [!IMPORTANT]
> <span data-ttu-id="32d5d-169">如果你的租户尚未购买电话系统许可证和呼叫计划, 则当你尝试将电话号码分配给资源帐户时, 内部检查将导致失败。</span><span class="sxs-lookup"><span data-stu-id="32d5d-169">If your tenant hasn't bought a Phone System license and a Calling Plan, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="32d5d-170">您无法分配该号码或将资源帐户与服务相关联。</span><span class="sxs-lookup"><span data-stu-id="32d5d-170">You won't be able to assign the number or associate the resource account with a service.</span></span>

![资源帐户分配](media/r-a-assign.png)

<span data-ttu-id="32d5d-172">![数字 2](media/sfbcallout2.png)您可以使用 "**编辑**" 选项编辑资源帐户的显示名称。</span><span class="sxs-lookup"><span data-stu-id="32d5d-172">![number 2](media/sfbcallout2.png) You can edit the resource account display name using the **Edit** option.</span></span>  <span data-ttu-id="32d5d-173">完成后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="32d5d-173">Click **Save** when you are done.</span></span>
<span data-ttu-id="32d5d-174">![编辑资源帐户](media/r-a-edit.png)</span><span class="sxs-lookup"><span data-stu-id="32d5d-174">![edit resource account](media/r-a-edit.png)</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="32d5d-175">在 Powershell 中创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="32d5d-175">Create a resource account in Powershell</span></span>

<span data-ttu-id="32d5d-176">对于 Microsoft 通话计划, 您只能将您在**Microsoft 团队管理中心**或从其他服务提供商移植到资源帐户的收费电话号码和免费服务电话号码分配给您。</span><span class="sxs-lookup"><span data-stu-id="32d5d-176">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or ported from another service provider to a resource account.</span></span> <span data-ttu-id="32d5d-177">若要获取并使用免费电话号码，则需要设置通信点数。</span><span class="sxs-lookup"><span data-stu-id="32d5d-177">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

<span data-ttu-id="32d5d-178">你需要通过管理员权限连接到相应的 Powershell 提示, 具体取决于你的资源帐户是否位于联机或本地。</span><span class="sxs-lookup"><span data-stu-id="32d5d-178">Depending on whether your resource account is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span> 
- <span data-ttu-id="32d5d-179">以下 Powershell cmdlet 示例假定资源帐户使用[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps)进行联机托管, 以创建联机的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="32d5d-179">The following Powershell cmdlet examples presume the resource account is homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to create a resource account that is homed online.</span></span>

- <span data-ttu-id="32d5d-180">对于驻留在 Skype For business Server 2019 (可与云呼叫队列和云自动助理配合使用) 的本地资源帐户, 请参阅[配置云呼叫队列](/skypeforbusiness/SfbHybrid/hybrid/configure-call-queue.md)或[配置云自动助理](/skypeforbusiness/SfbHybrid/hybrid/configure-cloud-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="32d5d-180">For resource accounts homed on-premises in Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Configure Cloud Call Queues](/skypeforbusiness/SfbHybrid/hybrid/configure-call-queue.md) or [Configure Cloud Auto Attendants](/skypeforbusiness/SfbHybrid/hybrid/configure-cloud-auto-attendant.md).</span></span> <span data-ttu-id="32d5d-181">混合实现 (直接路由上的号码) 将使用[CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="32d5d-181">Hybrid implementations (numbers homed on Direct Routing) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span></span>

<span data-ttu-id="32d5d-182">创建应用程序实例时需要使用的应用程序 ID 如下:</span><span class="sxs-lookup"><span data-stu-id="32d5d-182">The application ID's that you need to use while creating the application instances are:</span></span>
- <span data-ttu-id="32d5d-183">**自动助理:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="32d5d-183">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="32d5d-184">**呼叫队列:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="32d5d-184">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="32d5d-185">如果您希望呼叫队列或自动助理可由本地用户搜索, 您应该在本地创建资源帐户, 因为联机资源帐户没有同步到 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="32d5d-185">If you want the call queue or auto attendant to be searchable by on-premise users, you should create your resource accounts on-premise, since online resource accounts are not synced down to Active Directory.</span></span>

1. <span data-ttu-id="32d5d-186">若要创建联机的资源帐户以与自动助理配合使用, 请使用以下命令。</span><span class="sxs-lookup"><span data-stu-id="32d5d-186">To create a resource account online for use with an auto attendant, use the following command.</span></span>  

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. <span data-ttu-id="32d5d-187">你将无法使用资源帐户, 直到你向其应用许可证。</span><span class="sxs-lookup"><span data-stu-id="32d5d-187">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="32d5d-188">有关如何将许可证应用到 O365 管理中心中的帐户, 请参阅[在 Office 365 for business 中向用户分配许可证](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user)以及[分配 Skype for business 许可证](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)。</span><span class="sxs-lookup"><span data-stu-id="32d5d-188">For how to apply a license to an account in the O365 admin center, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="32d5d-189">可选将正确的许可证应用到资源帐户后, 您可以将电话号码设置为资源帐户, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="32d5d-189">(Optional) Once the correct license is applied to the resource account you can  set a phone number to the resource account as shown below.</span></span> <span data-ttu-id="32d5d-190">并非所有资源帐户都需要电话号码。</span><span class="sxs-lookup"><span data-stu-id="32d5d-190">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="32d5d-191">如果未对资源帐户应用许可证, 则电话号码分配将失败。</span><span class="sxs-lookup"><span data-stu-id="32d5d-191">If you did not apply a license to the resource account, the phone number assignment will fail.</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

<span data-ttu-id="32d5d-192">有关此命令的详细信息, 请参阅[Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="32d5d-192">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="32d5d-193">最简单的方法是使用 Microsoft 团队管理中心设置在线电话号码, 如上文所述。</span><span class="sxs-lookup"><span data-stu-id="32d5d-193">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="32d5d-194">在 Microsoft 团队管理中心中管理资源帐户设置</span><span class="sxs-lookup"><span data-stu-id="32d5d-194">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="32d5d-195">若要在 Microsoft 团队管理中心中管理资源帐户设置, 请导航到 "**组织范围的设置**  > "**资源帐户**, 选择要更改其设置所需的资源帐户, 然后单击 "**编辑**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="32d5d-195">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="32d5d-196">在 "**编辑资源帐户**" 屏幕中, 你将能够更改这些设置:</span><span class="sxs-lookup"><span data-stu-id="32d5d-196">in the **Edit resource account** screen, you will be able to change these settings:</span></span>

- <span data-ttu-id="32d5d-197">帐户的**显示名称**</span><span class="sxs-lookup"><span data-stu-id="32d5d-197">**Display name** for the account</span></span>
- <span data-ttu-id="32d5d-198">呼叫队列或使用该帐户的自动助理</span><span class="sxs-lookup"><span data-stu-id="32d5d-198">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="32d5d-199">分配给帐户的电话号码</span><span class="sxs-lookup"><span data-stu-id="32d5d-199">Phone number assigned to the account</span></span>

<span data-ttu-id="32d5d-200">完成后, 单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="32d5d-200">When finished, click on **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="32d5d-201">删除资源帐户</span><span class="sxs-lookup"><span data-stu-id="32d5d-201">Delete a resource account</span></span>

<span data-ttu-id="32d5d-202">请确保在删除之前将电话号码与资源帐户取消关联, 以避免让你的服务号码滞留在挂起模式下。</span><span class="sxs-lookup"><span data-stu-id="32d5d-202">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="32d5d-203">你可以使用以下 commandlet 执行此操作:</span><span class="sxs-lookup"><span data-stu-id="32d5d-203">You can do that using the following commandlet:</span></span> 

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="32d5d-204">执行此操作后, 您可以从 O365 管理门户删除资源帐户, 在 "用户" 选项卡下。</span><span class="sxs-lookup"><span data-stu-id="32d5d-204">Once you do that, you can delete the resource account from the O365 admin portal, under Users tab.</span></span>

## <a name="related-information"></a><span data-ttu-id="32d5d-205">相关信息</span><span class="sxs-lookup"><span data-stu-id="32d5d-205">Related Information</span></span>

<span data-ttu-id="32d5d-206">对于与 Skype for business 服务器混合的实现:</span><span class="sxs-lookup"><span data-stu-id="32d5d-206">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="32d5d-207">规划云自动助理</span><span class="sxs-lookup"><span data-stu-id="32d5d-207">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="32d5d-208">配置云自动助理</span><span class="sxs-lookup"><span data-stu-id="32d5d-208">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="32d5d-209">对于团队或 Skype for Business Online 中的实施:</span><span class="sxs-lookup"><span data-stu-id="32d5d-209">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="32d5d-210">什么是云自动助理？</span><span class="sxs-lookup"><span data-stu-id="32d5d-210">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="32d5d-211">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="32d5d-211">Set up a Cloud auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="32d5d-212">小型企业示例 - 设置自动助理</span><span class="sxs-lookup"><span data-stu-id="32d5d-212">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

[<span data-ttu-id="32d5d-213">创建云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="32d5d-213">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="32d5d-214">新-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="32d5d-214">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="32d5d-215">新-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="32d5d-215">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
