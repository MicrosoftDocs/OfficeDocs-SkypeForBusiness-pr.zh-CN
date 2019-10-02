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
ms.openlocfilehash: 0508408fbf5bde620cefe9233df4aa62ecf880df
ms.sourcegitcommit: e89c2234fc5aa8f7eeef66ba1ae093a0f7beda85
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "37349259"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="c5b74-103">在 Microsoft Teams 中管理资源帐户</span><span class="sxs-lookup"><span data-stu-id="c5b74-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="c5b74-104"><a name="bk">电话号码</a></span><span class="sxs-lookup"><span data-stu-id="c5b74-104"><a name="bk">phonenumber</a></span></span>

<span data-ttu-id="c5b74-105">资源帐户也称为 Azure AD 中*已禁用的用户对象*，可用于表示常规资源。</span><span class="sxs-lookup"><span data-stu-id="c5b74-105">A resource account is also known as a *disabled user object* in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="c5b74-106">例如，在 Exchange 中，它可能用于表示会议室，并允许他们拥有电话号码。</span><span class="sxs-lookup"><span data-stu-id="c5b74-106">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="c5b74-107">资源帐户可以使用 Skype for Business Server 2019 托管于 Microsoft 365 或本地。</span><span class="sxs-lookup"><span data-stu-id="c5b74-107">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="c5b74-108">在 Microsoft 团队或 Skype for business Online 中，每个电话系统呼叫队列或自动助理都必须具有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="c5b74-108">In Microsoft Teams or Skype for Business Online, each Phone System call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="c5b74-109">资源帐户是否需要分配的电话号码将取决于关联呼叫队列或自动助理的预期用途，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="c5b74-109">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant, as shown in the following diagram.</span></span> <span data-ttu-id="c5b74-110">在将电话号码分配给资源帐户之前，还可以参阅本文底部的 "呼叫队列" 和 "自动助理" 中链接的文章。</span><span class="sxs-lookup"><span data-stu-id="c5b74-110">You can also refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5b74-111">电话号码不会直接分配给自动助理或呼叫队列，而是与自动助理或呼叫队列相关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="c5b74-111">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>

![资源帐户和用户许可证的示例](media/resource-account.png)

> [!NOTE]
> <span data-ttu-id="c5b74-113">本文适用于 Microsoft 团队和 Skype for business Online。</span><span class="sxs-lookup"><span data-stu-id="c5b74-113">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="c5b74-114">对于驻留在 Skype for business Server 2019 上的资源帐户，请参阅[配置资源帐户](/SkypeForBusiness/hybrid/configure-onprem-ra)。</span><span class="sxs-lookup"><span data-stu-id="c5b74-114">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>


## <a name="overview"></a><span data-ttu-id="c5b74-115">概述</span><span class="sxs-lookup"><span data-stu-id="c5b74-115">Overview</span></span>

<span data-ttu-id="c5b74-116">如果您的组织已使用至少一个电话系统许可证，要向电话系统呼叫队列或自动助理分配电话号码，该过程如下所示：</span><span class="sxs-lookup"><span data-stu-id="c5b74-116">If your organization is already using at least one Phone System license, to assign a phone number to a Phone System call queue or auto attendant the process is:</span></span>

1. <span data-ttu-id="c5b74-117">获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="c5b74-117">Obtain a service number.</span></span>
2. <span data-ttu-id="c5b74-118">获取免费电话系统-[虚拟用户许可证](teams-add-on-licensing/virtual-user.md)或付费电话系统许可证，以便与资源帐户或电话系统许可证配合使用。</span><span class="sxs-lookup"><span data-stu-id="c5b74-118">Obtain a free Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or a paid Phone System license to use with the resource account or a Phone System license.</span></span>
3. <span data-ttu-id="c5b74-119">创建资源帐户。</span><span class="sxs-lookup"><span data-stu-id="c5b74-119">Create the resource account.</span></span> <span data-ttu-id="c5b74-120">需要使用自动助理或呼叫队列才能拥有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="c5b74-120">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="c5b74-121">为资源帐户分配电话系统或电话系统-虚拟用户许可证。</span><span class="sxs-lookup"><span data-stu-id="c5b74-121">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span>
5. <span data-ttu-id="c5b74-122">将服务电话号码分配给您刚向其分配许可证的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="c5b74-122">Assign a service phone number to the resource account you just assigned licenses to.</span></span> 
6. <span data-ttu-id="c5b74-123">创建电话系统呼叫队列或自动助理</span><span class="sxs-lookup"><span data-stu-id="c5b74-123">Create a Phone System call queue or auto attendant</span></span>
7. <span data-ttu-id="c5b74-124">将资源帐户与呼叫队列或自动助理链接。</span><span class="sxs-lookup"><span data-stu-id="c5b74-124">Link the resource account with a call queue or auto attendant.</span></span>

<span data-ttu-id="c5b74-125">如果自动助理或呼叫队列嵌套在顶级自动助理下方，并且如果你希望将多个点输入到自动助理的结构中并调用队列，则关联的资源帐户仅需要电话号码。</span><span class="sxs-lookup"><span data-stu-id="c5b74-125">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="c5b74-126">若要将呼叫重定向到您的组织中联机的人员，他们必须具有**电话系统**许可证并启用企业语音或拥有 Office 365 通话计划。</span><span class="sxs-lookup"><span data-stu-id="c5b74-126">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="c5b74-127">请参阅[分配 Microsoft 团队许可证](assign-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="c5b74-127">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="c5b74-128">To enable them for Enterprise Voice, you can use Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5b74-128">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="c5b74-129">例如，运行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="c5b74-129">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

> [!WARNING]
> <span data-ttu-id="c5b74-130">为了避免资源帐户出现问题，请按照此顺序执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="c5b74-130">In order to avoid problems with the resource account, follow these steps in this order.</span></span>

<span data-ttu-id="c5b74-131">如果您正在创建的电话系统呼叫队列或自动助理将被嵌套，并且不需要电话号码，则流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="c5b74-131">If the Phone System call queue or auto attendant you're creating will be nested and won't need a phone number, the process is:</span></span>

1. <span data-ttu-id="c5b74-132">创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="c5b74-132">Create the resource account</span></span> 
2. <span data-ttu-id="c5b74-133">创建电话系统呼叫队列或自动助理</span><span class="sxs-lookup"><span data-stu-id="c5b74-133">Create a Phone System call queue or auto attendant</span></span>
3. <span data-ttu-id="c5b74-134">将资源帐户与电话系统呼叫队列或自动助理相关联</span><span class="sxs-lookup"><span data-stu-id="c5b74-134">Associate the resource account with a Phone System call queue or auto attendant</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="c5b74-135">使用电话号码创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="c5b74-135">Create a resource account with a phone number</span></span>

<span data-ttu-id="c5b74-136">顶级自动助理或呼叫队列将要求将电话号码链接到其自动助理。</span><span class="sxs-lookup"><span data-stu-id="c5b74-136">A top-level auto attendant or call queue will require a phone number be linked to its auto attendant.</span></span> <span data-ttu-id="c5b74-137">若要创建使用电话号码的资源帐户，该过程如下所示：</span><span class="sxs-lookup"><span data-stu-id="c5b74-137">To create a resource account that uses a phone number, the process is:</span></span>

1. <span data-ttu-id="c5b74-138">或获取收费或免费服务号码。</span><span class="sxs-lookup"><span data-stu-id="c5b74-138">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="c5b74-139">该号码不能分配给任何其他语音服务或资源帐户。</span><span class="sxs-lookup"><span data-stu-id="c5b74-139">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="c5b74-140">将电话号码分配给资源帐户之前，您需要购买或移植您现有的收费或免费服务号码。</span><span class="sxs-lookup"><span data-stu-id="c5b74-140">Before you assign a phone number to a resource account, you need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="c5b74-141">获得收费或免费服务电话号码后，这些电话号码将显示在**Microsoft 团队管理中心** > **的语音** > **电话号码**中，**号码类型**将列为 "**服务-** 免费"。</span><span class="sxs-lookup"><span data-stu-id="c5b74-141">After you get the toll or toll-free service phone numbers, they show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type**  will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="c5b74-142">若要获取你的服务号码，请参阅[获取服务电话号码](getting-service-phone-numbers.md)或要转移现有服务号码，请参阅[将电话号码转移到 Office 365](transfer-phone-numbers-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="c5b74-142">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>

   <span data-ttu-id="c5b74-143">如果您要为资源帐户分配电话号码，您现在可以使用免费的电话系统虚拟用户许可证。</span><span class="sxs-lookup"><span data-stu-id="c5b74-143">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="c5b74-144">这将为组织级别的电话号码提供电话系统功能，并允许你创建自动助理和呼叫队列功能。</span><span class="sxs-lookup"><span data-stu-id="c5b74-144">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

2. <span data-ttu-id="c5b74-145">获取电话系统虚拟用户许可证或普通的电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="c5b74-145">Obtain a Phone System Virtual User license or a regular Phone System license.</span></span> 

   <span data-ttu-id="c5b74-146">若要获取虚拟用户许可证，从 Microsoft 365 管理中心开始，请转到**帐单** > **购买服务** > **附加订阅**并滚动到 "结束"，您将看到 "电话系统-虚拟用户" 许可证。</span><span class="sxs-lookup"><span data-stu-id="c5b74-146">To get the Virtual User license, starting from the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see "Phone System - Virtual User" license.</span></span> <span data-ttu-id="c5b74-147">选择 "**立即购买**"。</span><span class="sxs-lookup"><span data-stu-id="c5b74-147">Select **Buy now**.</span></span> <span data-ttu-id="c5b74-148">成本不为零，但仍需按照这些步骤获取许可证。</span><span class="sxs-lookup"><span data-stu-id="c5b74-148">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>
3. <span data-ttu-id="c5b74-149">创建新的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="c5b74-149">Create a new resource account.</span></span> <span data-ttu-id="c5b74-150">请参阅[在 Microsoft 团队管理中心创建资源帐户](#create-a-resource-account-in-microsoft-teams-admin-center)或[在 Powershell 中创建资源帐户](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="c5b74-150">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
4. <span data-ttu-id="c5b74-151">为资源帐户分配电话系统-[虚拟用户许可证](teams-add-on-licensing/virtual-user.md)或电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="c5b74-151">Assign a Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or Phone System License to the resource account.</span></span> <span data-ttu-id="c5b74-152">请参阅[分配 Microsoft 团队许可证](assign-teams-licenses.md)和[将许可证分配给一个用户](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user)。</span><span class="sxs-lookup"><span data-stu-id="c5b74-152">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>
5. <span data-ttu-id="c5b74-153">将服务号码分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="c5b74-153">Assign the service number to the resource account.</span></span> <span data-ttu-id="c5b74-154">请参阅[分配/取消分配电话号码和服务](#assignunassign-phone-numbers-and-services)。</span><span class="sxs-lookup"><span data-stu-id="c5b74-154">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
6. <span data-ttu-id="c5b74-155">设置下列内容之一：</span><span class="sxs-lookup"><span data-stu-id="c5b74-155">Set up one of the following:</span></span>
   - [<span data-ttu-id="c5b74-156">云自动助理</span><span class="sxs-lookup"><span data-stu-id="c5b74-156">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="c5b74-157">云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="c5b74-157">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
7. <span data-ttu-id="c5b74-158">将资源帐户链接到自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="c5b74-158">Link the resource account to the auto attendant or call queue.</span></span> <span data-ttu-id="c5b74-159">请参阅[分配/取消分配电话号码和服务](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="c5b74-159">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="c5b74-160">创建不带电话号码的资源帐户</span><span class="sxs-lookup"><span data-stu-id="c5b74-160">Create a resource account without a phone number</span></span>

<span data-ttu-id="c5b74-161">嵌套的自动助理或呼叫队列将需要资源帐户，但在许多情况下，相应的资源帐户不需要电话号码和支持电话号码所需的许可。</span><span class="sxs-lookup"><span data-stu-id="c5b74-161">A nested auto attendant or call queue will require a resource account, but in many cases the corresponding resource account will not need a phone number and the licensing required to support a phone number.</span></span> <span data-ttu-id="c5b74-162">创建不需要电话号码的资源帐户需要按以下顺序执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="c5b74-162">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="c5b74-163">创建新的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="c5b74-163">Create a new resource account.</span></span> <span data-ttu-id="c5b74-164">请参阅[在 Microsoft 团队管理中心创建资源帐户](#create-a-resource-account-in-microsoft-teams-admin-center)或[在 Powershell 中创建资源帐户](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="c5b74-164">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
2. <span data-ttu-id="c5b74-165">设置下列内容之一：</span><span class="sxs-lookup"><span data-stu-id="c5b74-165">Set up one of the following:</span></span>
   - [<span data-ttu-id="c5b74-166">云自动助理</span><span class="sxs-lookup"><span data-stu-id="c5b74-166">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="c5b74-167">云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="c5b74-167">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
3. <span data-ttu-id="c5b74-168">将资源帐户分配给呼叫队列或自动助理。</span><span class="sxs-lookup"><span data-stu-id="c5b74-168">Assign the resource account to the call queue or auto attendant.</span></span> <span data-ttu-id="c5b74-169">请参阅[分配/取消分配电话号码和服务](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="c5b74-169">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>


## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="c5b74-170">在 Microsoft 团队管理中心中创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="c5b74-170">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="c5b74-171">购买电话系统许可证后，使用 Microsoft 团队管理中心导航到**组织范围的设置** > **资源帐户**。</span><span class="sxs-lookup"><span data-stu-id="c5b74-171">After you've bought a Phone System license, using Microsoft Teams admin center navigate to **Org-wide settings** > **Resource accounts**.</span></span>

!["资源帐户" 页面的屏幕截图](media/r-a-master.png)

![数字1的图标，引用上一个屏幕截图中的标注](media/sfbcallout1.png)

<span data-ttu-id="c5b74-174">若要创建新的资源帐户，请单击 " **+ 新建帐户**"。</span><span class="sxs-lookup"><span data-stu-id="c5b74-174">To create a new resource account click **+ New account**.</span></span> <span data-ttu-id="c5b74-175">在弹出窗口中，填写资源帐户的 "显示名称" 和 "用户名" （域名应自动填充），然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="c5b74-175">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![新资源帐户选项的屏幕截图](media/res-acct.png)

<span data-ttu-id="c5b74-177">接下来，在 O365 管理中心中对资源帐户应用许可证，如在[Office 365 for business 中向用户分配许可证](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)中所述。</span><span class="sxs-lookup"><span data-stu-id="c5b74-177">Next, apply a license to the resource account in the O365 Admin center, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span></span>

### <a name="edit-resource-account-name"></a><span data-ttu-id="c5b74-178">编辑资源帐户名称</span><span class="sxs-lookup"><span data-stu-id="c5b74-178">Edit resource account name</span></span>

<span data-ttu-id="c5b74-179">![数字2的图标，引用上一个屏幕截图](media/sfbcallout2.png)中的标注，您可以使用 "**编辑**" 选项编辑资源帐户的显示名称。</span><span class="sxs-lookup"><span data-stu-id="c5b74-179">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png) You can edit the resource account display name using the **Edit** option.</span></span> <span data-ttu-id="c5b74-180">完成后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="c5b74-180">Click **Save** when you are done.</span></span>
<span data-ttu-id="c5b74-181">!["编辑资源帐户" 选项的屏幕截图](media/r-a-edit.png)</span><span class="sxs-lookup"><span data-stu-id="c5b74-181">![Screenshot of the Edit resource account option](media/r-a-edit.png)</span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="c5b74-182">分配/取消分配电话号码和服务</span><span class="sxs-lookup"><span data-stu-id="c5b74-182">Assign/Unassign phone numbers and services</span></span>

<span data-ttu-id="c5b74-183">![数字3的图标，在以前的屏幕截图](media/sfbcallout3.png)中引用标注一旦创建了资源帐户并分配了许可证，您可以单击 "**分配/取消**分配" 以将服务编号分配给资源帐户，或分配资源帐户到已存在的自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="c5b74-183">![Icon of the number 3, referencing a callout in the previous screenshot](media/sfbcallout3.png) Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, or assign the resource account to an auto attendant or call queue that already exists.</span></span> <span data-ttu-id="c5b74-184">分配直接路由号码只能使用 Cmdlet 完成。</span><span class="sxs-lookup"><span data-stu-id="c5b74-184">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="c5b74-185">如果您的通话队列或自动助理仍需创建，则可以在创建资源帐户时将其链接在一起。</span><span class="sxs-lookup"><span data-stu-id="c5b74-185">If your call queue or auto attendant still needs to be created, you can link the resource account while you create it.</span></span> <span data-ttu-id="c5b74-186">完成后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="c5b74-186">Click **Save** when you are done.</span></span>

<span data-ttu-id="c5b74-187">若要将直接路由或混合号码分配给资源帐户，您需要使用 PowerShell，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="c5b74-187">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5b74-188">如果你的资源帐户没有有效的许可证，则当你尝试将电话号码分配给资源帐户时，内部检查将导致失败。</span><span class="sxs-lookup"><span data-stu-id="c5b74-188">If your resource account doesn't have a valid license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="c5b74-189">您无法分配号码或将资源帐户与呼叫队列或自动助理相关联。</span><span class="sxs-lookup"><span data-stu-id="c5b74-189">You won't be able to assign the number or associate the resource account with a call queue or auto attendant.</span></span>

!["分配/取消分配" 选项的屏幕截图](media/r-a-assign.png)

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="c5b74-191">更改现有资源帐户以使用虚拟用户许可证</span><span class="sxs-lookup"><span data-stu-id="c5b74-191">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="c5b74-192">如果你决定将现有资源帐户上的许可证从电话系统许可证切换到虚拟用户许可证，你将需要获取免费虚拟用户许可证，然后按照 Microsoft 365 管理中心中的链接步骤[将用户移动到不同的订阅](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription)。</span><span class="sxs-lookup"><span data-stu-id="c5b74-192">If you decide to switch the licenses on your existing resource account from a Phone system license to a Virtual User license, you'll need to acquire the free Virtual User license, then follow the linked steps in the Microsoft 365 Admin center to [Move users to a different subscription](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span></span> 

> [!WARNING]
> <span data-ttu-id="c5b74-193">始终删除完整的电话系统许可证，并在同一许可证活动中分配虚拟用户许可证。</span><span class="sxs-lookup"><span data-stu-id="c5b74-193">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="c5b74-194">如果删除旧许可证，请保存帐户更改，添加新许可证，然后再次保存帐户设置，资源帐户可能不再按预期运行。</span><span class="sxs-lookup"><span data-stu-id="c5b74-194">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="c5b74-195">如果发生这种情况，我们建议你为虚拟用户许可证创建新的资源帐户，并删除断开的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="c5b74-195">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span> 

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="c5b74-196">在 Powershell 中创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="c5b74-196">Create a resource account in Powershell</span></span>

<span data-ttu-id="c5b74-197">你需要通过管理员权限连接到相应的 Powershell 提示，具体取决于你的资源帐户是否位于联机或本地。</span><span class="sxs-lookup"><span data-stu-id="c5b74-197">Depending on whether your resource account is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="c5b74-198">以下 Powershell cmdlet 示例显示如何使用[CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps)创建联机的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="c5b74-198">The following Powershell cmdlet examples show creating a resource account homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps).</span></span> 

- <span data-ttu-id="c5b74-199">对于驻留在 Skype For business Server 2019 （可与云呼叫队列和云自动助理配合使用）的本地资源帐户，请参阅[配置云呼叫队列](/skypeforbusiness/hybrid/configure-call-queue.md)或[配置云自动助理](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="c5b74-199">For resource accounts homed on-premises in Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Configure Cloud Call Queues](/skypeforbusiness/hybrid/configure-call-queue.md) or [Configure Cloud Auto Attendants](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span></span> <span data-ttu-id="c5b74-200">混合实现（直接路由上的号码）将使用[CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="c5b74-200">Hybrid implementations (numbers homed on Direct Routing) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span></span>

<span data-ttu-id="c5b74-201">创建应用程序实例时需要使用的应用程序 ID 如下：</span><span class="sxs-lookup"><span data-stu-id="c5b74-201">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="c5b74-202">**自动助理：** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="c5b74-202">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="c5b74-203">**呼叫队列：** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="c5b74-203">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="c5b74-204">如果希望呼叫队列或自动助理可由本地用户搜索，您应该在本地创建资源帐户，因为联机资源帐户未同步到 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="c5b74-204">If you want the call queue or auto attendant to be searchable by on-premises users, you should create your resource accounts on-premise, since online resource accounts are not synced down to Active Directory.</span></span>

1. <span data-ttu-id="c5b74-205">若要创建联机的资源帐户以与自动助理配合使用，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="c5b74-205">To create a resource account online for use with an auto attendant, use the following command:</span></span>

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. <span data-ttu-id="c5b74-206">你将无法使用资源帐户，直到你向其应用许可证。</span><span class="sxs-lookup"><span data-stu-id="c5b74-206">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="c5b74-207">有关如何将许可证应用到 O365 管理中心中的帐户，请参阅[在 Office 365 for business 中向用户分配许可证](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user)以及[分配 Skype for business 许可证](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)。</span><span class="sxs-lookup"><span data-stu-id="c5b74-207">For how to apply a license to an account in the O365 admin center, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="c5b74-208">可选将正确的许可证应用到资源帐户后，您可以为资源帐户分配一个电话号码，如下所示。</span><span class="sxs-lookup"><span data-stu-id="c5b74-208">(Optional) Once the correct license is applied to the resource account you can assign a phone number to the resource account as shown below.</span></span> <span data-ttu-id="c5b74-209">并非所有资源帐户都需要电话号码。</span><span class="sxs-lookup"><span data-stu-id="c5b74-209">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="c5b74-210">如果未对资源帐户应用许可证，则电话号码分配将失败。</span><span class="sxs-lookup"><span data-stu-id="c5b74-210">If you did not apply a license to the resource account, the phone number assignment will fail.</span></span>

   ``` Powershell
   Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
   Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
   ```

   <span data-ttu-id="c5b74-211">有关此命令的详细信息，请参阅[Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="c5b74-211">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c5b74-212">最简单的方法是使用 Microsoft 团队管理中心设置在线电话号码，如上文所述。</span><span class="sxs-lookup"><span data-stu-id="c5b74-212">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

   <span data-ttu-id="c5b74-213">若要将直接路由电话号码分配给资源帐户（通过联机或本地托管），请使用以下适用于 Skype for Business Online Powershell 的 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c5b74-213">To assign a direct routing phone number to a resource account (homed either online or on-premises), use the following cmdlet for Skype for Business Online Powershell:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="c5b74-214">在 Microsoft 团队管理中心中管理资源帐户设置</span><span class="sxs-lookup"><span data-stu-id="c5b74-214">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="c5b74-215">若要在 Microsoft 团队管理中心中管理资源帐户设置，请导航到 "**组织范围的设置** > "**资源帐户**，选择要更改其设置所需的资源帐户，然后单击 "**编辑**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="c5b74-215">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="c5b74-216">在 "**编辑资源帐户**" 屏幕中，你将能够更改这些设置：</span><span class="sxs-lookup"><span data-stu-id="c5b74-216">in the **Edit resource account** screen, you will be able to change these settings:</span></span>

- <span data-ttu-id="c5b74-217">帐户的**显示名称**</span><span class="sxs-lookup"><span data-stu-id="c5b74-217">**Display name** for the account</span></span>
- <span data-ttu-id="c5b74-218">呼叫队列或使用该帐户的自动助理</span><span class="sxs-lookup"><span data-stu-id="c5b74-218">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="c5b74-219">分配给帐户的电话号码</span><span class="sxs-lookup"><span data-stu-id="c5b74-219">Phone number assigned to the account</span></span>

<span data-ttu-id="c5b74-220">完成后，单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="c5b74-220">When finished, click on **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="c5b74-221">删除资源帐户</span><span class="sxs-lookup"><span data-stu-id="c5b74-221">Delete a resource account</span></span>

<span data-ttu-id="c5b74-222">请确保在删除之前将电话号码与资源帐户取消关联，以避免让你的服务号码滞留在挂起模式下。</span><span class="sxs-lookup"><span data-stu-id="c5b74-222">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="c5b74-223">你可以使用以下 commandlet 执行此操作：</span><span class="sxs-lookup"><span data-stu-id="c5b74-223">You can do that using the following commandlet:</span></span>

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="c5b74-224">执行此操作后，您可以从 O365 管理门户删除资源帐户，在 "用户" 选项卡下。</span><span class="sxs-lookup"><span data-stu-id="c5b74-224">Once you do that, you can delete the resource account from the O365 admin portal, under Users tab.</span></span>

<span data-ttu-id="c5b74-225">若要解除直接路由电话号码与资源帐户的关联，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c5b74-225">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

## <a name="troubleshooting"></a><span data-ttu-id="c5b74-226">疑难解答</span><span class="sxs-lookup"><span data-stu-id="c5b74-226">Troubleshooting</span></span>

<span data-ttu-id="c5b74-227">如果您没有看到分配给团队管理中心中的资源帐户的电话号码，并且您无法分配该号码，请检查以下事项：</span><span class="sxs-lookup"><span data-stu-id="c5b74-227">In case you do not see the phone number assigned to the resource account on the Teams Admin Center and you are unable to assign the number from there, please check the following:</span></span>

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="c5b74-228">如果 "部门" 属性显示 Skype for Business 应用程序终结点，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c5b74-228">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below :</span></span>

``` Powershell
Set-MsolUser -ObjectId -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> <span data-ttu-id="c5b74-229">在运行 cmldet 后刷新团队管理中心网页，您应该能够正确分配号码。</span><span class="sxs-lookup"><span data-stu-id="c5b74-229">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

## <a name="related-information"></a><span data-ttu-id="c5b74-230">相关信息</span><span class="sxs-lookup"><span data-stu-id="c5b74-230">Related Information</span></span>

<span data-ttu-id="c5b74-231">对于与 Skype for business 服务器混合的实现：</span><span class="sxs-lookup"><span data-stu-id="c5b74-231">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="c5b74-232">规划云自动助理</span><span class="sxs-lookup"><span data-stu-id="c5b74-232">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="c5b74-233">规划云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="c5b74-233">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="c5b74-234">配置本地资源帐户</span><span class="sxs-lookup"><span data-stu-id="c5b74-234">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


<span data-ttu-id="c5b74-235">对于团队或 Skype for Business Online 中的实施：</span><span class="sxs-lookup"><span data-stu-id="c5b74-235">For implementations in Teams or Skype for Business Online:</span></span>

   [<span data-ttu-id="c5b74-236">什么是云自动助理？</span><span class="sxs-lookup"><span data-stu-id="c5b74-236">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

   [<span data-ttu-id="c5b74-237">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="c5b74-237">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

   [<span data-ttu-id="c5b74-238">小型企业示例 - 设置自动助理</span><span class="sxs-lookup"><span data-stu-id="c5b74-238">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

   [<span data-ttu-id="c5b74-239">创建云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="c5b74-239">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="c5b74-240">新-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="c5b74-240">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="c5b74-241">新-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="c5b74-241">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[<span data-ttu-id="c5b74-242">电话系统-虚拟用户许可证</span><span class="sxs-lookup"><span data-stu-id="c5b74-242">Phone System - Virtual User license</span></span>](teams-add-on-licensing/virtual-user.md)
