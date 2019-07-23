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
ms.openlocfilehash: ddea11e7aa3bc9287313b02db27d095c49528718
ms.sourcegitcommit: 6d30a0b0eb51a20aef93833bb7c0e466f015b3c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2019
ms.locfileid: "35818213"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="3478b-103">在 Microsoft Teams 中管理资源帐户</span><span class="sxs-lookup"><span data-stu-id="3478b-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="3478b-104">资源帐户在 Azure Active Directory 中也称为*已禁用的用户对象*, 并且可用于表示常规资源。</span><span class="sxs-lookup"><span data-stu-id="3478b-104">A resource account is also known as a *disabled user object* in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="3478b-105">例如, 在 Exchange 中, 它可能用于表示会议室, 并允许他们拥有电话号码。</span><span class="sxs-lookup"><span data-stu-id="3478b-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="3478b-106">资源帐户可以使用 Skype for Business Server 2019 托管于 Microsoft 365 或本地。</span><span class="sxs-lookup"><span data-stu-id="3478b-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="3478b-107">在 Microsoft 团队或 Skype for business Online 中, 每个电话系统呼叫队列或自动助理都必须具有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="3478b-107">In Microsoft Teams or Skype for Business Online, each Phone System call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="3478b-108">资源帐户是否需要分配的电话号码取决于关联呼叫队列或自动助理的预期用途。</span><span class="sxs-lookup"><span data-stu-id="3478b-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="3478b-109">在将电话号码分配给资源帐户之前, 请参阅本文底部的 "呼叫队列" 和 "自动助理" 中链接的文章。</span><span class="sxs-lookup"><span data-stu-id="3478b-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="3478b-110">本文适用于 Microsoft 团队和 Skype for business Online。</span><span class="sxs-lookup"><span data-stu-id="3478b-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="3478b-111">对于驻留在 Skype for business Server 2019 上的资源帐户, 请参阅[配置资源帐户](/SkypeForBusiness/hybrid/configure-onprem-ra)。</span><span class="sxs-lookup"><span data-stu-id="3478b-111">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>


## <a name="overview"></a><span data-ttu-id="3478b-112">概述</span><span class="sxs-lookup"><span data-stu-id="3478b-112">Overview</span></span>

<span data-ttu-id="3478b-113">假设您的组织至少使用一个电话系统许可证, 若要为电话号码分配电话号码, 您需要按以下顺序解决各种相关性:</span><span class="sxs-lookup"><span data-stu-id="3478b-113">Assuming that your organization is using at least one Phone System License, to assigning a Phone System service a phone number, you will need to address the various dependencies in the following sequence:</span></span>

1. <span data-ttu-id="3478b-114">获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="3478b-114">Obtain a service number.</span></span>
2. <span data-ttu-id="3478b-115">获取用于资源帐户的电话系统[虚拟用户许可证](teams-add-on-licensing/virtual-user.md)或普通电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="3478b-115">Obtain a Phone System [Virtual user license](teams-add-on-licensing/virtual-user.md) or a regular Phone System license to use with the resource account.</span></span>
3. <span data-ttu-id="3478b-116">创建资源帐户。</span><span class="sxs-lookup"><span data-stu-id="3478b-116">Create the resource account.</span></span> <span data-ttu-id="3478b-117">需要使用自动助理或呼叫队列才能拥有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="3478b-117">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="3478b-118">将电话系统或电话系统虚拟用户许可证分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="3478b-118">Assign the Phone System or a Phone System Virtual user license to the resource account.</span></span>
5. <span data-ttu-id="3478b-119">将服务电话号码分配给您刚向其分配许可证的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="3478b-119">Assign a service phone number to the resource account you just assigned licenses to.</span></span>
6. <span data-ttu-id="3478b-120">创建电话系统服务 (呼叫队列或自动助理)。</span><span class="sxs-lookup"><span data-stu-id="3478b-120">Create a Phone System service (a call queue or auto attendant).</span></span>
7. <span data-ttu-id="3478b-121">将资源帐户与服务链接。</span><span class="sxs-lookup"><span data-stu-id="3478b-121">Link the resource account with a service.</span></span>

<span data-ttu-id="3478b-122">如果自动助理或呼叫队列嵌套在顶级自动助理下方, 并且如果你希望将多个点输入到自动助理的结构中并调用队列, 则关联的资源帐户仅需要电话号码。</span><span class="sxs-lookup"><span data-stu-id="3478b-122">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="3478b-123">若要将呼叫重定向到您的组织中联机的人员, 他们必须具有**电话系统**许可证并启用企业语音或拥有 Office 365 通话计划。</span><span class="sxs-lookup"><span data-stu-id="3478b-123">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="3478b-124">请参阅[分配 Microsoft 团队许可证](assign-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="3478b-124">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="3478b-125">要为他们启用企业语音，可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3478b-125">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="3478b-126">例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="3478b-126">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

> [!WARNING]
> <span data-ttu-id="3478b-127">为了避免资源帐户出现问题, 请按照此顺序执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="3478b-127">In order to avoid problems with the resource account, follow these steps in this order.</span></span>

<span data-ttu-id="3478b-128">如果你要创建的电话系统服务将嵌套, 并且不需要电话号码, 则过程如下:</span><span class="sxs-lookup"><span data-stu-id="3478b-128">If the Phone System service you're creating will be nested and will not need a phone number, the process is:</span></span>

1. <span data-ttu-id="3478b-129">创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="3478b-129">Create the resource account</span></span>  
2. <span data-ttu-id="3478b-130">创建电话系统服务</span><span class="sxs-lookup"><span data-stu-id="3478b-130">Create a Phone System service</span></span>
3. <span data-ttu-id="3478b-131">将资源帐户与电话系统服务相关联</span><span class="sxs-lookup"><span data-stu-id="3478b-131">Associate the resource account with a Phone System service</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="3478b-132">使用电话号码创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="3478b-132">Create a resource account with a phone number</span></span>

<span data-ttu-id="3478b-133">创建使用电话号码的资源帐户需要按以下顺序执行以下任务:</span><span class="sxs-lookup"><span data-stu-id="3478b-133">Creating a resource account that uses a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="3478b-134">或获取收费或免费服务号码。</span><span class="sxs-lookup"><span data-stu-id="3478b-134">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="3478b-135">该号码不能分配给任何其他语音服务或资源帐户。</span><span class="sxs-lookup"><span data-stu-id="3478b-135">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="3478b-136">将电话号码分配给资源帐户之前, 您需要购买或移植您现有的收费或免费服务号码。</span><span class="sxs-lookup"><span data-stu-id="3478b-136">Before you assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="3478b-137">获得收费或免费服务电话号码后, 这些电话号码将显示在**Microsoft 团队管理中心** > **的语音** > **电话号码**中, 并且列出的**号码类型**将按**服务免费**列出。</span><span class="sxs-lookup"><span data-stu-id="3478b-137">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="3478b-138">若要获取你的服务号码, 请参阅[获取服务电话号码](getting-service-phone-numbers.md)或要转移现有服务号码, 请参阅[将电话号码转移到 Office 365](transfer-phone-numbers-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="3478b-138">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>

   <span data-ttu-id="3478b-139">如果您要为资源帐户分配电话号码, 您现在可以使用免费的电话系统虚拟用户许可证。</span><span class="sxs-lookup"><span data-stu-id="3478b-139">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="3478b-140">这将为组织级别的电话号码提供电话系统功能, 并允许你创建自动助理和呼叫队列功能。</span><span class="sxs-lookup"><span data-stu-id="3478b-140">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

2. <span data-ttu-id="3478b-141">获取电话系统虚拟用户许可证或普通的电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="3478b-141">Obtain a Phone System Virtual User license or a regular Phone System license.</span></span> 

   <span data-ttu-id="3478b-142">若要获取虚拟许可证, 请从 Microsoft 365 管理中心转到**帐单** > **购买服务** > **附加订阅**并滚动到 "结束", 你将看到 "电话系统-虚拟用户" 许可证。</span><span class="sxs-lookup"><span data-stu-id="3478b-142">To get the virtual license, from the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see "Phone System - Virtual User" license.</span></span> <span data-ttu-id="3478b-143">选择 "**立即购买**"。</span><span class="sxs-lookup"><span data-stu-id="3478b-143">Select **Buy now**.</span></span> <span data-ttu-id="3478b-144">成本不为零, 但仍需按照这些步骤获取许可证。</span><span class="sxs-lookup"><span data-stu-id="3478b-144">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>
3. <span data-ttu-id="3478b-145">创建新的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="3478b-145">Create a new resource account.</span></span> <span data-ttu-id="3478b-146">请参阅[在 Microsoft 团队管理中心创建资源帐户](#create-a-resource-account-in-microsoft-teams-admin-center)或[在 Powershell 中创建资源帐户](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="3478b-146">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
4. <span data-ttu-id="3478b-147">将[虚拟用户许可证](teams-add-on-licensing/virtual-user.md)或电话系统许可证分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="3478b-147">Assign  [Virtual User license](teams-add-on-licensing/virtual-user.md) or Phone System License to the resource account.</span></span> <span data-ttu-id="3478b-148">请参阅[分配 Microsoft 团队许可证](assign-teams-licenses.md)和[将许可证分配给一个用户](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user)。</span><span class="sxs-lookup"><span data-stu-id="3478b-148">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>
5. <span data-ttu-id="3478b-149">将服务号码分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="3478b-149">Assign the service number to the resource account.</span></span> <span data-ttu-id="3478b-150">请参阅[分配/取消分配电话号码和服务](#assignunassign-phone-numbers-and-services)。</span><span class="sxs-lookup"><span data-stu-id="3478b-150">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
6. <span data-ttu-id="3478b-151">设置下列内容之一:</span><span class="sxs-lookup"><span data-stu-id="3478b-151">Set up one of the following:</span></span>
   - [<span data-ttu-id="3478b-152">云自动助理</span><span class="sxs-lookup"><span data-stu-id="3478b-152">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="3478b-153">云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="3478b-153">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
7. <span data-ttu-id="3478b-154">将资源帐户链接到自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="3478b-154">Link the resource account to the auto attendant or call queue.</span></span> <span data-ttu-id="3478b-155">请参阅[分配/取消分配电话号码和服务](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="3478b-155">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="3478b-156">创建不带电话号码的资源帐户</span><span class="sxs-lookup"><span data-stu-id="3478b-156">Create a resource account without a phone number</span></span>

<span data-ttu-id="3478b-157">创建不需要电话号码的资源帐户需要按以下顺序执行以下任务:</span><span class="sxs-lookup"><span data-stu-id="3478b-157">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="3478b-158">创建新的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="3478b-158">Create a new resource account.</span></span> <span data-ttu-id="3478b-159">请参阅[在 Microsoft 团队管理中心创建资源帐户](#create-a-resource-account-in-microsoft-teams-admin-center)或[在 Powershell 中创建资源帐户](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="3478b-159">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
2. <span data-ttu-id="3478b-160">设置下列内容之一:</span><span class="sxs-lookup"><span data-stu-id="3478b-160">Set up one of the following:</span></span>
   - [<span data-ttu-id="3478b-161">云自动助理</span><span class="sxs-lookup"><span data-stu-id="3478b-161">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="3478b-162">云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="3478b-162">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
3. <span data-ttu-id="3478b-163">将资源帐户分配给服务。</span><span class="sxs-lookup"><span data-stu-id="3478b-163">Assign the resource account to the service.</span></span> <span data-ttu-id="3478b-164">请参阅[分配/取消分配电话号码和服务](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="3478b-164">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="3478b-165">在 Microsoft 团队管理中心中创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="3478b-165">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="3478b-166">购买电话系统许可证后, 使用 Microsoft 团队管理中心导航到**组织范围的设置** > **资源帐户**。</span><span class="sxs-lookup"><span data-stu-id="3478b-166">After you've bought a Phone System license, using Microsoft Teams admin center navigate to **Org-wide settings** > **Resource accounts**.</span></span>

!["资源帐户" 页面的屏幕截图](media/r-a-master.png)

![数字1的图标, 引用上一个屏幕截图中的标注](media/sfbcallout1.png)

<span data-ttu-id="3478b-169">若要创建新的资源帐户, 请单击 " **+ 新建帐户**"。</span><span class="sxs-lookup"><span data-stu-id="3478b-169">To create a new resource account click **+ New account**.</span></span> <span data-ttu-id="3478b-170">在弹出窗口中, 填写资源帐户的 "显示名称" 和 "用户名" (域名应自动填充), 然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="3478b-170">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![新资源帐户选项的屏幕截图](media/res-acct.png)

<span data-ttu-id="3478b-172">接下来, 在 O365 管理中心中对资源帐户应用许可证, 如在[Office 365 for business 中向用户分配许可证](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)中所述。</span><span class="sxs-lookup"><span data-stu-id="3478b-172">Next, apply a license to the resource account in the O365 Admin center, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span></span>

### <a name="edit-resource-account-name"></a><span data-ttu-id="3478b-173">编辑资源帐户名称</span><span class="sxs-lookup"><span data-stu-id="3478b-173">Edit resource account name</span></span>

<span data-ttu-id="3478b-174">![数字2的图标, 引用上一个屏幕截图](media/sfbcallout2.png)中的标注, 您可以使用 "**编辑**" 选项编辑资源帐户的显示名称。</span><span class="sxs-lookup"><span data-stu-id="3478b-174">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png) You can edit the resource account display name using the **Edit** option.</span></span>  <span data-ttu-id="3478b-175">完成后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="3478b-175">Click **Save** when you are done.</span></span>
<span data-ttu-id="3478b-176">!["编辑资源帐户" 选项的屏幕截图](media/r-a-edit.png)</span><span class="sxs-lookup"><span data-stu-id="3478b-176">![Screen shot of the Edit resource account option](media/r-a-edit.png)</span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="3478b-177">分配/取消分配电话号码和服务</span><span class="sxs-lookup"><span data-stu-id="3478b-177">Assign/Unassign phone numbers and services</span></span>

<span data-ttu-id="3478b-178">![数字3的图标, 在以前的屏幕截图](media/sfbcallout3.png)中引用标注一旦创建了资源帐户并分配了许可证, 您可以单击 "**分配/取消**分配" 以将服务编号分配给资源帐户, 或分配资源帐户到已存在的自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="3478b-178">![Icon of the number 3, referencing a callout in the previous screenshot](media/sfbcallout3.png) Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, or assign the resource account to an auto attendant or call queue that already exists.</span></span> <span data-ttu-id="3478b-179">分配直接路由号码只能使用 Cmdlet 完成。</span><span class="sxs-lookup"><span data-stu-id="3478b-179">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="3478b-180">如果您的通话队列或自动助理仍需创建, 则可以在创建资源帐户时将其链接在一起。</span><span class="sxs-lookup"><span data-stu-id="3478b-180">If your call queue or auto attendant still needs to be created, you can link the resource account while you create it.</span></span> <span data-ttu-id="3478b-181">完成后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="3478b-181">Click **Save** when you are done.</span></span>

<span data-ttu-id="3478b-182">若要将直接路由或混合号码分配给资源帐户, 您需要使用 PowerShell, 请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="3478b-182">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3478b-183">如果你的资源帐户没有虚拟用户或电话系统许可证, 则当你尝试将电话号码分配给资源帐户时, 内部检查将导致失败。</span><span class="sxs-lookup"><span data-stu-id="3478b-183">If your resource account doesn't have a Virtual User or Phone System license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="3478b-184">您无法分配该号码或将资源帐户与服务相关联。</span><span class="sxs-lookup"><span data-stu-id="3478b-184">You won't be able to assign the number or associate the resource account with a service.</span></span>

!["分配/取消分配" 选项的屏幕截图](media/r-a-assign.png)

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="3478b-186">更改现有资源帐户以使用虚拟用户许可证</span><span class="sxs-lookup"><span data-stu-id="3478b-186">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="3478b-187">如果你决定将现有资源帐户上的许可证从电话系统许可证切换到虚拟用户许可证, 你需要 aquire "免费虚拟用户" 许可证, 然后按照 Microsoft 365 管理中心中的链接步骤[将用户移动到不同的订阅](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription)。</span><span class="sxs-lookup"><span data-stu-id="3478b-187">If you decide to switch the licenses on your existing resource account from a Phone system license to a Virtual User license, you'll need to  aquire the free Virtual User license, then follow the linked steps in the Microsoft 365 Admin center to [Move users to a different subscription](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span></span> 

> [!WARNING]
> <span data-ttu-id="3478b-188">始终删除完整的电话系统许可证, 并在同一许可证活动中分配虚拟用户许可证。</span><span class="sxs-lookup"><span data-stu-id="3478b-188">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="3478b-189">如果删除旧许可证, 请保存帐户更改, 添加新许可证, 然后再次保存帐户设置, 资源帐户可能不再按预期运行。</span><span class="sxs-lookup"><span data-stu-id="3478b-189">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="3478b-190">如果发生这种情况, 我们建议你为虚拟用户许可证创建新的资源帐户, 并删除断开的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="3478b-190">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span> 

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="3478b-191">在 Powershell 中创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="3478b-191">Create a resource account in Powershell</span></span>

<span data-ttu-id="3478b-192">你需要通过管理员权限连接到相应的 Powershell 提示, 具体取决于你的资源帐户是否位于联机或本地。</span><span class="sxs-lookup"><span data-stu-id="3478b-192">Depending on whether your resource account is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="3478b-193">以下 Powershell cmdlet 示例假定资源帐户使用[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps)进行联机托管, 以创建联机的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="3478b-193">The following Powershell cmdlet examples presume the resource account is homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to create a resource account that is homed online.</span></span>

- <span data-ttu-id="3478b-194">对于驻留在 Skype For business Server 2019 (可与云呼叫队列和云自动助理配合使用) 的本地资源帐户, 请参阅[配置云呼叫队列](/skypeforbusiness/hybrid/configure-call-queue.md)或[配置云自动助理](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="3478b-194">For resource accounts homed on-premises in Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Configure Cloud Call Queues](/skypeforbusiness/hybrid/configure-call-queue.md) or [Configure Cloud Auto Attendants](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span></span> <span data-ttu-id="3478b-195">混合实现 (直接路由上的号码) 将使用[CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="3478b-195">Hybrid implementations (numbers homed on Direct Routing) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span></span>

<span data-ttu-id="3478b-196">创建应用程序实例时需要使用的应用程序 ID 如下:</span><span class="sxs-lookup"><span data-stu-id="3478b-196">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="3478b-197">**自动助理:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="3478b-197">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="3478b-198">**呼叫队列:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="3478b-198">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="3478b-199">如果您希望呼叫队列或自动助理可由本地用户搜索, 您应该在本地创建资源帐户, 因为联机资源帐户没有同步到 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="3478b-199">If you want the call queue or auto attendant to be searchable by on-premise users, you should create your resource accounts on-premise, since online resource accounts are not synced down to Active Directory.</span></span>

1. <span data-ttu-id="3478b-200">若要创建联机的资源帐户以与自动助理配合使用, 请使用以下命令。</span><span class="sxs-lookup"><span data-stu-id="3478b-200">To create a resource account online for use with an auto attendant, use the following command.</span></span>  

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. <span data-ttu-id="3478b-201">你将无法使用资源帐户, 直到你向其应用许可证。</span><span class="sxs-lookup"><span data-stu-id="3478b-201">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="3478b-202">有关如何将许可证应用到 O365 管理中心中的帐户, 请参阅[在 Office 365 for business 中向用户分配许可证](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user)以及[分配 Skype for business 许可证](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)。</span><span class="sxs-lookup"><span data-stu-id="3478b-202">For how to apply a license to an account in the O365 admin center, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="3478b-203">可选将正确的许可证应用到资源帐户后, 您可以将电话号码设置为资源帐户, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="3478b-203">(Optional) Once the correct license is applied to the resource account you can  set a phone number to the resource account as shown below.</span></span> <span data-ttu-id="3478b-204">并非所有资源帐户都需要电话号码。</span><span class="sxs-lookup"><span data-stu-id="3478b-204">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="3478b-205">如果未对资源帐户应用许可证, 则电话号码分配将失败。</span><span class="sxs-lookup"><span data-stu-id="3478b-205">If you did not apply a license to the resource account, the phone number assignment will fail.</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

<span data-ttu-id="3478b-206">有关此命令的详细信息, 请参阅[Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="3478b-206">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="3478b-207">最简单的方法是使用 Microsoft 团队管理中心设置在线电话号码, 如上文所述。</span><span class="sxs-lookup"><span data-stu-id="3478b-207">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

<span data-ttu-id="3478b-208">若要将直接路由或混合号码分配给资源帐户, 请使用以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3478b-208">To assign a direct routing or hybrid number to  a resource account, use the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="3478b-209">在 Microsoft 团队管理中心中管理资源帐户设置</span><span class="sxs-lookup"><span data-stu-id="3478b-209">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="3478b-210">若要在 Microsoft 团队管理中心中管理资源帐户设置, 请导航到 "**组织范围的设置**  > "**资源帐户**, 选择要更改其设置所需的资源帐户, 然后单击 "**编辑**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="3478b-210">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="3478b-211">在 "**编辑资源帐户**" 屏幕中, 你将能够更改这些设置:</span><span class="sxs-lookup"><span data-stu-id="3478b-211">in the **Edit resource account** screen, you will be able to change these settings:</span></span>

- <span data-ttu-id="3478b-212">帐户的**显示名称**</span><span class="sxs-lookup"><span data-stu-id="3478b-212">**Display name** for the account</span></span>
- <span data-ttu-id="3478b-213">呼叫队列或使用该帐户的自动助理</span><span class="sxs-lookup"><span data-stu-id="3478b-213">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="3478b-214">分配给帐户的电话号码</span><span class="sxs-lookup"><span data-stu-id="3478b-214">Phone number assigned to the account</span></span>

<span data-ttu-id="3478b-215">完成后, 单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="3478b-215">When finished, click on **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="3478b-216">删除资源帐户</span><span class="sxs-lookup"><span data-stu-id="3478b-216">Delete a resource account</span></span>

<span data-ttu-id="3478b-217">请确保在删除之前将电话号码与资源帐户取消关联, 以避免让你的服务号码滞留在挂起模式下。</span><span class="sxs-lookup"><span data-stu-id="3478b-217">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="3478b-218">你可以使用以下 commandlet 执行此操作:</span><span class="sxs-lookup"><span data-stu-id="3478b-218">You can do that using the following commandlet:</span></span>

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="3478b-219">执行此操作后, 您可以从 O365 管理门户删除资源帐户, 在 "用户" 选项卡下。</span><span class="sxs-lookup"><span data-stu-id="3478b-219">Once you do that, you can delete the resource account from the O365 admin portal, under Users tab.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="3478b-220">疑难解答</span><span class="sxs-lookup"><span data-stu-id="3478b-220">Troubleshooting</span></span>

<span data-ttu-id="3478b-221">如果您没有看到分配给团队管理中心中的资源帐户的电话号码, 并且您无法分配该号码, 请检查以下事项:</span><span class="sxs-lookup"><span data-stu-id="3478b-221">In case you do not see the phone number assigned to the resource account on the Teams Admin Center and you are unable to assign the number from there, please check the following:</span></span>

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="3478b-222">如果 "部门" 属性显示 Skype for Business 应用程序终结点, 请运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3478b-222">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below :</span></span>

``` Powershell
Set-MsolUser -ObjectId  -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> <span data-ttu-id="3478b-223">在运行 cmldet 后刷新团队管理中心网页, 您应该能够正确分配号码。</span><span class="sxs-lookup"><span data-stu-id="3478b-223">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

## <a name="related-information"></a><span data-ttu-id="3478b-224">相关信息</span><span class="sxs-lookup"><span data-stu-id="3478b-224">Related Information</span></span>

<span data-ttu-id="3478b-225">对于与 Skype for business 服务器混合的实现:</span><span class="sxs-lookup"><span data-stu-id="3478b-225">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="3478b-226">规划云自动助理</span><span class="sxs-lookup"><span data-stu-id="3478b-226">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="3478b-227">规划云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="3478b-227">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue.md)
   
   [<span data-ttu-id="3478b-228">配置本地资源帐户</span><span class="sxs-lookup"><span data-stu-id="3478b-228">Configure onprem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra.md)


<span data-ttu-id="3478b-229">对于团队或 Skype for Business Online 中的实施:</span><span class="sxs-lookup"><span data-stu-id="3478b-229">For implementations in Teams or Skype for Business Online:</span></span>

   [<span data-ttu-id="3478b-230">什么是云自动助理？</span><span class="sxs-lookup"><span data-stu-id="3478b-230">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

   [<span data-ttu-id="3478b-231">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="3478b-231">Set up a Cloud auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

   [<span data-ttu-id="3478b-232">小型企业示例 - 设置自动助理</span><span class="sxs-lookup"><span data-stu-id="3478b-232">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

   [<span data-ttu-id="3478b-233">创建云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="3478b-233">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="3478b-234">新-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="3478b-234">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="3478b-235">新-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="3478b-235">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[<span data-ttu-id="3478b-236">虚拟用户许可证</span><span class="sxs-lookup"><span data-stu-id="3478b-236">Virtual User license</span></span>](teams-add-on-licensing/virtual-user.md)
