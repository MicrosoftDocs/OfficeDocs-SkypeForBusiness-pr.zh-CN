---
title: 在 Teams 中管理资源帐户
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: 在本文中，你将了解如何在 Microsoft 团队中创建、编辑和管理资源帐户。
ms.openlocfilehash: 07f6f15f3ed3fc1e115ae672ef1eac89b5eab12f
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905004"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="455db-103">在 Microsoft Teams 中管理资源帐户</span><span class="sxs-lookup"><span data-stu-id="455db-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="455db-104">资源帐户也称为 Azure AD 中*已禁用的用户对象*，可用于表示常规资源。</span><span class="sxs-lookup"><span data-stu-id="455db-104">A resource account is also known as a *disabled user object* in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="455db-105">例如，在 Exchange 中，它可能用于表示会议室，并允许他们拥有电话号码。</span><span class="sxs-lookup"><span data-stu-id="455db-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="455db-106">资源帐户可以使用 Skype for Business Server 2019 托管于 Microsoft 365 或本地。</span><span class="sxs-lookup"><span data-stu-id="455db-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="455db-107">在 Microsoft 团队或 Skype for business Online 中，每个电话系统呼叫队列或自动助理都必须至少有一个关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="455db-107">In Microsoft Teams or Skype for Business Online, each Phone System call queue or auto attendant is required to have at least one associated resource account.</span></span> <span data-ttu-id="455db-108">资源帐户是否需要分配的电话号码将取决于关联呼叫队列或自动助理的预期用途，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="455db-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant, as shown in the following diagram.</span></span> <span data-ttu-id="455db-109">在将电话号码分配给资源帐户之前，还可以参阅本文底部的 "呼叫队列" 和 "自动助理" 中链接的文章。</span><span class="sxs-lookup"><span data-stu-id="455db-109">You can also refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

![资源帐户和用户许可证的示例](media/resource-account.png)

> [!NOTE]
> <span data-ttu-id="455db-111">本文适用于 Microsoft 团队和 Skype for business Online。</span><span class="sxs-lookup"><span data-stu-id="455db-111">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="455db-112">对于驻留在 Skype for business Server 2019 上的资源帐户，请参阅[配置资源帐户](/SkypeForBusiness/hybrid/configure-onprem-ra)。</span><span class="sxs-lookup"><span data-stu-id="455db-112">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>

## <a name="assign-a-phone-number-to-a-phone-system-call-queue"></a><span data-ttu-id="455db-113">将电话号码分配给电话系统呼叫队列</span><span class="sxs-lookup"><span data-stu-id="455db-113">Assign a phone number to a Phone System call queue</span></span>

<span data-ttu-id="455db-114">如果您的组织已使用至少一个电话系统许可证，要向电话系统呼叫队列分配电话号码，该过程如下所示：</span><span class="sxs-lookup"><span data-stu-id="455db-114">If your organization is already using at least one Phone System license, to assign a phone number to a Phone System call queue the process is:</span></span>

1. <span data-ttu-id="455db-115">获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="455db-115">Obtain a service number.</span></span>
2. <span data-ttu-id="455db-116">获取免费电话系统-[虚拟用户许可证](teams-add-on-licensing/virtual-user.md)或付费电话系统许可证，以便与资源帐户或电话系统许可证配合使用。</span><span class="sxs-lookup"><span data-stu-id="455db-116">Obtain a free Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or a paid Phone System license to use with the resource account or a Phone System license.</span></span>
3. <span data-ttu-id="455db-117">创建资源帐户。</span><span class="sxs-lookup"><span data-stu-id="455db-117">Create the resource account.</span></span> <span data-ttu-id="455db-118">需要使用自动助理或呼叫队列才能拥有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="455db-118">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="455db-119">为资源帐户分配电话系统或电话系统-虚拟用户许可证。</span><span class="sxs-lookup"><span data-stu-id="455db-119">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span>
5. <span data-ttu-id="455db-120">将服务电话号码分配给您刚向其分配许可证的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="455db-120">Assign a service phone number to the resource account you just assigned licenses to.</span></span>
6. <span data-ttu-id="455db-121">创建电话系统呼叫队列或自动助理</span><span class="sxs-lookup"><span data-stu-id="455db-121">Create a Phone System call queue or auto attendant</span></span>
7. <span data-ttu-id="455db-122">将资源帐户与呼叫队列或自动助理链接。</span><span class="sxs-lookup"><span data-stu-id="455db-122">Link the resource account with a call queue or auto attendant.</span></span>

<!-- Auto attendants created after November 1st, 2019 also create a new resource account that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available. -->

<span data-ttu-id="455db-123">如果自动助理或呼叫队列嵌套在顶级自动助理下方，并且如果你希望将多个点输入到自动助理的结构中并调用队列，则关联的资源帐户仅需要电话号码。</span><span class="sxs-lookup"><span data-stu-id="455db-123">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="455db-124">若要将呼叫重定向到您的组织中联机的人员，他们必须具有**电话系统**许可证并启用企业语音或拥有 Office 365 通话计划。</span><span class="sxs-lookup"><span data-stu-id="455db-124">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="455db-125">请参阅[分配 Microsoft 团队许可证](assign-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="455db-125">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="455db-126">To enable them for Enterprise Voice, you can use Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="455db-126">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="455db-127">例如，运行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="455db-127">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

> [!WARNING]
> <span data-ttu-id="455db-128">为了避免资源帐户出现问题，请按照此顺序执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="455db-128">In order to avoid problems with the resource account, follow these steps in this order.</span></span>

<span data-ttu-id="455db-129">如果您正在创建的电话系统呼叫队列或自动助理将被嵌套，并且不需要电话号码，则流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="455db-129">If the Phone System call queue or auto attendant you're creating will be nested and won't need a phone number, the process is:</span></span>

1. <span data-ttu-id="455db-130">创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="455db-130">Create the resource account</span></span>
2. <span data-ttu-id="455db-131">创建电话系统呼叫队列或自动助理</span><span class="sxs-lookup"><span data-stu-id="455db-131">Create a Phone System call queue or auto attendant</span></span>
3. <span data-ttu-id="455db-132">将资源帐户与电话系统呼叫队列或自动助理相关联</span><span class="sxs-lookup"><span data-stu-id="455db-132">Associate the resource account with a Phone System call queue or auto attendant</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="455db-133">使用电话号码创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="455db-133">Create a resource account with a phone number</span></span>

<span data-ttu-id="455db-134"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="455db-134"><a name="phonenumber"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="455db-135">电话号码不会直接分配给自动助理或呼叫队列，而是与自动助理或呼叫队列相关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="455db-135">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>

<span data-ttu-id="455db-136">顶级自动助理或呼叫队列将要求将电话号码链接到其自动助理。</span><span class="sxs-lookup"><span data-stu-id="455db-136">A top-level auto attendant or call queue will require a phone number be linked to its auto attendant.</span></span> <span data-ttu-id="455db-137">若要创建使用电话号码的资源帐户，该过程如下所示：</span><span class="sxs-lookup"><span data-stu-id="455db-137">To create a resource account that uses a phone number, the process is:</span></span>

1. <span data-ttu-id="455db-138">或获取收费或免费服务号码。</span><span class="sxs-lookup"><span data-stu-id="455db-138">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="455db-139">该号码不能分配给任何其他语音服务或资源帐户。</span><span class="sxs-lookup"><span data-stu-id="455db-139">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="455db-140">将电话号码分配给资源帐户之前，您需要购买或移植您现有的收费或免费服务号码。</span><span class="sxs-lookup"><span data-stu-id="455db-140">Before you assign a phone number to a resource account, you need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="455db-141">获得收费或免费服务电话号码后，这些电话号码将显示在**Microsoft 团队管理中心** > **的语音** > **电话号码**中，**号码类型**将列为 "**服务-** 免费"。</span><span class="sxs-lookup"><span data-stu-id="455db-141">After you get the toll or toll-free service phone numbers, they show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type**  will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="455db-142">若要获取你的服务号码，请参阅[获取服务电话号码](getting-service-phone-numbers.md)或要转移现有服务号码，请参阅[将电话号码转移到团队](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="455db-142">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

   <span data-ttu-id="455db-143">如果您要为资源帐户分配电话号码，您现在可以使用免费的电话系统虚拟用户许可证。</span><span class="sxs-lookup"><span data-stu-id="455db-143">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="455db-144">这将为组织级别的电话号码提供电话系统功能，并允许你创建自动助理和呼叫队列功能。</span><span class="sxs-lookup"><span data-stu-id="455db-144">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

2. <span data-ttu-id="455db-145">获取电话系统虚拟用户许可证或普通的电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="455db-145">Obtain a Phone System Virtual User license or a regular Phone System license.</span></span>

   <span data-ttu-id="455db-146">若要获取虚拟用户许可证，从 Microsoft 365 管理中心开始，请转到**帐单** > **购买服务** > **附加订阅**并滚动到 "结束"，您将看到 "电话系统-虚拟用户" 许可证。</span><span class="sxs-lookup"><span data-stu-id="455db-146">To get the Virtual User license, starting from the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see "Phone System - Virtual User" license.</span></span> <span data-ttu-id="455db-147">选择 "**立即购买**"。</span><span class="sxs-lookup"><span data-stu-id="455db-147">Select **Buy now**.</span></span> <span data-ttu-id="455db-148">成本不为零，但仍需按照这些步骤获取许可证。</span><span class="sxs-lookup"><span data-stu-id="455db-148">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>
3. <span data-ttu-id="455db-149">创建新的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="455db-149">Create a new resource account.</span></span> <span data-ttu-id="455db-150">请参阅[在 Microsoft 团队管理中心创建资源帐户](#create-a-resource-account-in-microsoft-teams-admin-center)或[在 Powershell 中创建资源帐户](#create-a-resource-account-in-powershell)。</span><span class="sxs-lookup"><span data-stu-id="455db-150">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell).</span></span>
4. <span data-ttu-id="455db-151">为资源帐户分配电话系统-[虚拟用户许可证](teams-add-on-licensing/virtual-user.md)或电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="455db-151">Assign a Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or Phone System License to the resource account.</span></span> <span data-ttu-id="455db-152">请参阅[分配 Microsoft 团队许可证](assign-teams-licenses.md)和[将许可证分配给一个用户](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user)。</span><span class="sxs-lookup"><span data-stu-id="455db-152">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>
5. <span data-ttu-id="455db-153">将服务号码分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="455db-153">Assign the service number to the resource account.</span></span> <span data-ttu-id="455db-154">请参阅[分配/取消分配电话号码和服务](#assignunassign-phone-numbers-and-services)。</span><span class="sxs-lookup"><span data-stu-id="455db-154">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
6. <span data-ttu-id="455db-155">设置下列内容之一：</span><span class="sxs-lookup"><span data-stu-id="455db-155">Set up one of the following:</span></span>
   - [<span data-ttu-id="455db-156">云自动助理</span><span class="sxs-lookup"><span data-stu-id="455db-156">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="455db-157">云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="455db-157">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
7. <span data-ttu-id="455db-158">将资源帐户链接到自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="455db-158">Link the resource account to the auto attendant or call queue.</span></span> <span data-ttu-id="455db-159">请参阅[分配/取消分配电话号码和服务](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="455db-159">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

<span data-ttu-id="455db-160">创建自动助理时创建资源帐户时，将自动应用许可证。</span><span class="sxs-lookup"><span data-stu-id="455db-160">When you create a resource account while creating an auto attendant, the licenses are applied automatically.</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="455db-161">创建不带电话号码的资源帐户</span><span class="sxs-lookup"><span data-stu-id="455db-161">Create a resource account without a phone number</span></span>

<span data-ttu-id="455db-162">嵌套的自动助理或呼叫队列将需要资源帐户，但在许多情况下，相应的资源帐户不需要电话号码和支持电话号码所需的许可。</span><span class="sxs-lookup"><span data-stu-id="455db-162">A nested auto attendant or call queue will require a resource account, but in many cases the corresponding resource account will not need a phone number and the licensing required to support a phone number.</span></span> <span data-ttu-id="455db-163">创建不需要电话号码的资源帐户需要按以下顺序执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="455db-163">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="455db-164">创建新的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="455db-164">Create a new resource account.</span></span> <span data-ttu-id="455db-165">请参阅[在 Microsoft 团队管理中心创建资源帐户](#create-a-resource-account-in-microsoft-teams-admin-center)或[在 Powershell 中创建资源帐户](#create-a-resource-account-in-powershell)。</span><span class="sxs-lookup"><span data-stu-id="455db-165">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell).</span></span>
2. <span data-ttu-id="455db-166">设置下列内容之一：</span><span class="sxs-lookup"><span data-stu-id="455db-166">Set up one of the following:</span></span>
   - [<span data-ttu-id="455db-167">云自动助理</span><span class="sxs-lookup"><span data-stu-id="455db-167">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="455db-168">云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="455db-168">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
3. <span data-ttu-id="455db-169">将资源帐户分配给呼叫队列或自动助理。</span><span class="sxs-lookup"><span data-stu-id="455db-169">Assign the resource account to the call queue or auto attendant.</span></span> <span data-ttu-id="455db-170">请参阅[分配/取消分配电话号码和服务](#assignunassign-phone-numbers-and-services)。</span><span class="sxs-lookup"><span data-stu-id="455db-170">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>


## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="455db-171">在 Microsoft 团队管理中心中创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="455db-171">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="455db-172">购买电话系统许可证后，使用 Microsoft 团队管理中心导航到**组织范围的设置** > **资源帐户**。</span><span class="sxs-lookup"><span data-stu-id="455db-172">After you've bought a Phone System license, using Microsoft Teams admin center navigate to **Org-wide settings** > **Resource accounts**.</span></span>

!["资源帐户" 页面的屏幕截图](media/r-a-master.png)

![数字1的图标，引用上一个屏幕截图中的标注](media/teamscallout1.png)

<span data-ttu-id="455db-175">若要创建新的资源帐户，请单击 " **+ 添加**"。</span><span class="sxs-lookup"><span data-stu-id="455db-175">To create a new resource account click **+ Add**.</span></span> <span data-ttu-id="455db-176">在弹出窗口中，填写 "**显示名称**"、"**用户名**" （域名应自动填充）和资源帐户**类型**。</span><span class="sxs-lookup"><span data-stu-id="455db-176">In the pop-up, fill out the **Display name**, **Username** (the domain name should populate automatically), and **Resource account type**  for the resource account.</span></span> <span data-ttu-id="455db-177">资源帐户类型可以是**自动助理**或**呼叫队列**，具体取决于你想要关联到资源帐户的应用。</span><span class="sxs-lookup"><span data-stu-id="455db-177">Resource account type can be either **Auto attendant** or **Call queue** depending on the app you intend to associate to the resource account.</span></span> <span data-ttu-id="455db-178">准备就绪后，单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="455db-178">When you are ready,  click **Save**.</span></span>

![新资源帐户选项的屏幕截图](media/res-acct.png)

<span data-ttu-id="455db-180">接下来，按照在[Office 365 for business 中向用户分配许可证](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)中所述，将许可证应用于 O365 管理中心中的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="455db-180">Next, apply a license to the resource account in the O365 Admin center, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide).</span></span>

### <a name="edit-resource-account"></a><span data-ttu-id="455db-181">编辑资源帐户</span><span class="sxs-lookup"><span data-stu-id="455db-181">Edit resource account</span></span> 

<span data-ttu-id="455db-182">![](media/teamscallout2.png)数字2的图标，引用上一个屏幕截图中的标注，您可以使用 "**编辑**" 选项编辑资源帐户的 "**显示名称**" 和 "**资源帐户**" 类型。</span><span class="sxs-lookup"><span data-stu-id="455db-182">![Icon of the number 2, referencing a callout in the previous screenshot](media/teamscallout2.png) You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="455db-183">完成后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="455db-183">Click **Save** when you are done.</span></span>

!["编辑资源帐户" 选项的屏幕截图](media/r-a-edit.png)

<span data-ttu-id="455db-185"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="455db-185"><a name="phonenumber"> </a></span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="455db-186">分配/取消分配电话号码和服务</span><span class="sxs-lookup"><span data-stu-id="455db-186">Assign/Unassign phone numbers and services</span></span>

<span data-ttu-id="455db-187">![数字3的图标在以前的屏幕截图](media/teamscallout3.png)中引用标注一旦创建了资源帐户并分配了许可证，您可以单击 "**分配/取消**分配" 以将服务编号分配给资源帐户、设置电话号码类型或将资源帐户分配给已存在的特定自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="455db-187">![Icon of the number 3, referencing a callout in the previous screenshot](media/teamscallout3.png) Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, set the phone number type, or assign the resource account to a specific auto attendant or call queue that already exists.</span></span> <span data-ttu-id="455db-188">分配直接路由号码只能使用 Cmdlet 完成。</span><span class="sxs-lookup"><span data-stu-id="455db-188">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="455db-189">如果尚未创建要与资源帐户关联的呼叫队列或自动助理，请将该字段留空。</span><span class="sxs-lookup"><span data-stu-id="455db-189">If you haven't yet created the  call queue or auto attendant you will associate to the resource account,leave that field blank.</span></span> <span data-ttu-id="455db-190">你可以在创建资源帐户时将其链接到该帐户。</span><span class="sxs-lookup"><span data-stu-id="455db-190">You can link the resource account while you create it.</span></span> <span data-ttu-id="455db-191">完成后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="455db-191">Click **Save** when you are done.</span></span>

<span data-ttu-id="455db-192">**电话号码类型**选项包括：</span><span class="sxs-lookup"><span data-stu-id="455db-192">Options for the **Phone number type** are:</span></span>

- <span data-ttu-id="455db-193">无</span><span class="sxs-lookup"><span data-stu-id="455db-193">None</span></span>
- <span data-ttu-id="455db-194">Online</span><span class="sxs-lookup"><span data-stu-id="455db-194">Online</span></span>
- <span data-ttu-id="455db-195">免费</span><span class="sxs-lookup"><span data-stu-id="455db-195">Toll-free</span></span>
- <span data-ttu-id="455db-196">本地部署</span><span class="sxs-lookup"><span data-stu-id="455db-196">On-premises</span></span>

!["分配/取消分配" 选项的屏幕截图](media/r-a-assign.png)

<span data-ttu-id="455db-198">若要将直接路由或混合号码分配给资源帐户，您需要使用 PowerShell，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="455db-198">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="455db-199">如果你的资源帐户没有有效的许可证，则当你尝试将电话号码分配给资源帐户时，内部检查将导致失败。</span><span class="sxs-lookup"><span data-stu-id="455db-199">If your resource account doesn't have a valid license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="455db-200">您无法分配号码或将资源帐户与呼叫队列或自动助理相关联。</span><span class="sxs-lookup"><span data-stu-id="455db-200">You won't be able to assign the number or associate the resource account with a call queue or auto attendant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="455db-201">电话号码不会直接分配给自动助理或呼叫队列，而是与自动助理或呼叫队列相关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="455db-201">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>



## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="455db-202">更改现有资源帐户以使用虚拟用户许可证</span><span class="sxs-lookup"><span data-stu-id="455db-202">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="455db-203">如果你决定将现有资源帐户上的许可证从电话系统许可证切换到虚拟用户许可证，你将需要获取免费的虚拟用户许可证，然后按照 Microsoft 365 管理中心中的链接步骤[将用户移动到其他订阅](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription)。</span><span class="sxs-lookup"><span data-stu-id="455db-203">If you decide to switch the licenses on your existing resource account from a Phone system license to a Virtual User license, you'll need to acquire the free Virtual User license, then follow the linked steps in the Microsoft 365 Admin center to [Move users to a different subscription](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span></span> 

> [!WARNING]
> <span data-ttu-id="455db-204">始终删除完整的电话系统许可证，并在同一许可证活动中分配虚拟用户许可证。</span><span class="sxs-lookup"><span data-stu-id="455db-204">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="455db-205">如果删除旧许可证，请保存帐户更改，添加新许可证，然后再次保存帐户设置，资源帐户可能不再按预期运行。</span><span class="sxs-lookup"><span data-stu-id="455db-205">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="455db-206">如果发生这种情况，我们建议你为虚拟用户许可证创建新的资源帐户，并删除断开的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="455db-206">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span> 

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="455db-207">在 Powershell 中创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="455db-207">Create a resource account in Powershell</span></span>

<span data-ttu-id="455db-208">你需要通过管理员权限连接到相应的 Powershell 提示，具体取决于你的资源帐户是联机还是位于 Skype for business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="455db-208">Depending on whether your resource account is located online or on Skype for Business Server 2019, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="455db-209">以下 Powershell cmdlet 示例显示如何使用[CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps)创建联机的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="455db-209">The following Powershell cmdlet examples show creating a resource account homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps).</span></span> 

- <span data-ttu-id="455db-210">对于驻留在可与云呼叫队列和云自动助理一起使用的 Skype For business Server 2019 上的资源帐户，请参阅[计划云呼叫队列](/SkypeforBusiness/hybrid/plan-call-queue)或[计划云自动助理](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)。</span><span class="sxs-lookup"><span data-stu-id="455db-210">For resource accounts homed on Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span></span> <span data-ttu-id="455db-211">混合实现（以直接路由方式托管的号码）使用本地 Skype for business Server 2019 服务器上的[CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) cmdlet 进行配置。</span><span class="sxs-lookup"><span data-stu-id="455db-211">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="455db-212">创建应用程序实例时需要使用的应用程序 ID 如下：</span><span class="sxs-lookup"><span data-stu-id="455db-212">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="455db-213">**自动助理：** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="455db-213">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="455db-214">**呼叫队列：** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="455db-214">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="455db-215">如果您希望呼叫队列或自动助理可由 Skype For Business Server 2019 用户搜索，则应在 Skype For business Server 2019 上创建资源帐户，因为联机资源帐户未同步到 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="455db-215">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="455db-216">当 sipfederationtls 的 DNS SRV 记录解析到 Skype for business Server 2019 时，**必须**使用 SfB Management shell 并同步到 ONLINE Azure AD，在 Skype For business server 2019 上创建资源帐户。</span><span class="sxs-lookup"><span data-stu-id="455db-216">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to online Azure AD.</span></span>

 

1. <span data-ttu-id="455db-217">若要创建联机的资源帐户以与自动助理配合使用，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="455db-217">To create a resource account online for use with an auto attendant, use the following command:</span></span>

    ``` Powershell
    New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
    ```

2. <span data-ttu-id="455db-218">你将无法使用资源帐户，直到你向其应用许可证。</span><span class="sxs-lookup"><span data-stu-id="455db-218">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="455db-219">有关如何将许可证应用到 O365 管理中心中的帐户，请参阅[在 Office 365 for business 中向用户分配许可证](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user)以及[分配 Skype for business 许可证](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)。</span><span class="sxs-lookup"><span data-stu-id="455db-219">For how to apply a license to an account in the O365 admin center, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="455db-220">可选将正确的许可证应用到资源帐户后，您可以为资源帐户分配一个电话号码，如下所示。</span><span class="sxs-lookup"><span data-stu-id="455db-220">(Optional) Once the correct license is applied to the resource account you can assign a phone number to the resource account as shown below.</span></span> <span data-ttu-id="455db-221">并非所有资源帐户都需要电话号码。</span><span class="sxs-lookup"><span data-stu-id="455db-221">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="455db-222">如果未对资源帐户应用许可证，则电话号码分配将失败。</span><span class="sxs-lookup"><span data-stu-id="455db-222">If you did not apply a license to the resource account, the phone number assignment will fail.</span></span>

   ``` Powershell
   Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
   Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
   ```

   <span data-ttu-id="455db-223">有关此命令的详细信息，请参阅[Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="455db-223">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

   > [!NOTE]
   > <span data-ttu-id="455db-224">最简单的方法是使用 Microsoft 团队管理中心设置在线电话号码，如上文所述。</span><span class="sxs-lookup"><span data-stu-id="455db-224">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

   <span data-ttu-id="455db-225">若要将直接路由电话号码分配给资源帐户（在 Microsoft 团队或 Skype For business Server 2019 中托管），请使用适用于 Skype for business Online Powershell 的以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="455db-225">To assign a direct routing phone number to a resource account (homed either in Microsoft Teams or Skype For Business Server 2019), use the following cmdlet for Skype for Business Online Powershell:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="455db-226">在 Microsoft 团队管理中心中管理资源帐户设置</span><span class="sxs-lookup"><span data-stu-id="455db-226">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="455db-227">若要在 Microsoft 团队管理中心中管理资源帐户设置，请导航到 "**组织范围的设置** > "**资源帐户**，选择要更改其设置所需的资源帐户，然后单击 "**编辑**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="455db-227">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="455db-228">在 "**编辑资源帐户**" 屏幕中，你将能够更改这些设置：</span><span class="sxs-lookup"><span data-stu-id="455db-228">in the **Edit resource account** screen, you will be able to change these settings:</span></span>

- <span data-ttu-id="455db-229">帐户的**显示名称**</span><span class="sxs-lookup"><span data-stu-id="455db-229">**Display name** for the account</span></span>
- <span data-ttu-id="455db-230">呼叫队列或使用该帐户的自动助理</span><span class="sxs-lookup"><span data-stu-id="455db-230">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="455db-231">分配给帐户的电话号码</span><span class="sxs-lookup"><span data-stu-id="455db-231">Phone number assigned to the account</span></span>

<span data-ttu-id="455db-232">完成后，单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="455db-232">When finished, click on **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="455db-233">删除资源帐户</span><span class="sxs-lookup"><span data-stu-id="455db-233">Delete a resource account</span></span>

<span data-ttu-id="455db-234">请确保在删除之前将电话号码与资源帐户取消关联，以避免让你的服务号码滞留在挂起模式下。</span><span class="sxs-lookup"><span data-stu-id="455db-234">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="455db-235">你可以使用以下 commandlet 执行此操作：</span><span class="sxs-lookup"><span data-stu-id="455db-235">You can do that using the following commandlet:</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="455db-236">执行此操作后，您可以从 O365 管理门户删除资源帐户，在 "用户" 选项卡下。</span><span class="sxs-lookup"><span data-stu-id="455db-236">Once you do that, you can delete the resource account from the O365 admin portal, under Users tab.</span></span>

<span data-ttu-id="455db-237">若要解除直接路由电话号码与资源帐户的关联，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="455db-237">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

## <a name="troubleshooting"></a><span data-ttu-id="455db-238">故障排除</span><span class="sxs-lookup"><span data-stu-id="455db-238">Troubleshooting</span></span>

<span data-ttu-id="455db-239">如果您没有看到分配给团队管理中心中的资源帐户的电话号码，并且您无法分配该号码，请检查以下事项：</span><span class="sxs-lookup"><span data-stu-id="455db-239">In case you do not see the phone number assigned to the resource account on the Teams Admin Center and you are unable to assign the number from there, please check the following:</span></span>

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="455db-240">如果 "部门" 属性显示 Skype for Business 应用程序终结点，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="455db-240">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below:</span></span>

``` Powershell
Set-MsolUser -ObjectId -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> <span data-ttu-id="455db-241">在运行 cmldet 后刷新团队管理中心网页，您应该能够正确分配号码。</span><span class="sxs-lookup"><span data-stu-id="455db-241">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

## <a name="related-information"></a><span data-ttu-id="455db-242">相关信息</span><span class="sxs-lookup"><span data-stu-id="455db-242">Related Information</span></span>

<span data-ttu-id="455db-243">对于与 Skype for business 服务器混合的实现：</span><span class="sxs-lookup"><span data-stu-id="455db-243">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="455db-244">规划云自动助理</span><span class="sxs-lookup"><span data-stu-id="455db-244">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="455db-245">规划云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="455db-245">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="455db-246">配置本地资源帐户</span><span class="sxs-lookup"><span data-stu-id="455db-246">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


<span data-ttu-id="455db-247">对于团队或 Skype for Business Online 中的实施：</span><span class="sxs-lookup"><span data-stu-id="455db-247">For implementations in Teams or Skype for Business Online:</span></span>

   [<span data-ttu-id="455db-248">什么是云自动助理？</span><span class="sxs-lookup"><span data-stu-id="455db-248">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

   [<span data-ttu-id="455db-249">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="455db-249">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

   [<span data-ttu-id="455db-250">小型企业示例 - 设置自动助理</span><span class="sxs-lookup"><span data-stu-id="455db-250">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

   [<span data-ttu-id="455db-251">创建云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="455db-251">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="455db-252">新-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="455db-252">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="455db-253">新-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="455db-253">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[<span data-ttu-id="455db-254">电话系统-虚拟用户许可证</span><span class="sxs-lookup"><span data-stu-id="455db-254">Phone System - Virtual User license</span></span>](teams-add-on-licensing/virtual-user.md)
