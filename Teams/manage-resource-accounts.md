---
title: 在 Teams 中管理资源帐户
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
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
ms.openlocfilehash: 2a043b608dfe311003dea26acc8a0c236460fad5
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031018"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="c50d6-103">在 Microsoft Teams 中管理资源帐户</span><span class="sxs-lookup"><span data-stu-id="c50d6-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="c50d6-104">资源帐户是 Azure AD 中已禁用的用户对象，可用于表示常规资源。</span><span class="sxs-lookup"><span data-stu-id="c50d6-104">A resource account is a disabled user object in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="c50d6-105">例如，可以在 Exchange 中使用资源帐户表示会议室，并允许他们拥有电话号码和日历。</span><span class="sxs-lookup"><span data-stu-id="c50d6-105">For example, a resource account may be used in Exchange to represent conference rooms and allow them to have a phone number and calendar.</span></span> <span data-ttu-id="c50d6-106">资源帐户可以使用 Skype for Business Server 2019 托管于 Microsoft 365 或本地。</span><span class="sxs-lookup"><span data-stu-id="c50d6-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="c50d6-107">在 Microsoft 团队中，每个自动助理或呼叫队列需要资源帐户。</span><span class="sxs-lookup"><span data-stu-id="c50d6-107">In Microsoft Teams, a resource account is required for each auto attendant or call queue.</span></span> <span data-ttu-id="c50d6-108">也可以为资源帐户分配服务电话号码。</span><span class="sxs-lookup"><span data-stu-id="c50d6-108">Resource accounts may also be assigned service telephone numbers.</span></span> <span data-ttu-id="c50d6-109">这是将电话号码分配给自动助理和呼叫队列的方式，允许来自外部团队的呼叫者到达自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="c50d6-109">This is how you assign phone numbers to auto attendants and call queues allowing callers from outside Teams to reach the auto attendant or call queue.</span></span>

<span data-ttu-id="c50d6-110">本文介绍如何创建资源帐户并准备好使用自动助理和呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="c50d6-110">This article covers how to create resource accounts and ready them for use with auto attendants and call queues.</span></span>

<span data-ttu-id="c50d6-111">在开始本文中的过程之前，请确保已完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="c50d6-111">Before you start the procedures in this article, ensure you've done the following:</span></span>

- [<span data-ttu-id="c50d6-112">获取虚拟用户许可证</span><span class="sxs-lookup"><span data-stu-id="c50d6-112">Obtain virtual user licenses</span></span>](#obtain-virtual-user-licenses)
- [<span data-ttu-id="c50d6-113">获取服务号码</span><span class="sxs-lookup"><span data-stu-id="c50d6-113">Obtain service numbers</span></span>](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="c50d6-114">获取虚拟用户许可证</span><span class="sxs-lookup"><span data-stu-id="c50d6-114">Obtain virtual user licenses</span></span>

<span data-ttu-id="c50d6-115">每个资源帐户都需要许可证，才能使用自动助理和呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="c50d6-115">Each resource account requires a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="c50d6-116">您可以使用免费的 *Microsoft 365 Phone 系统虚拟用户* 许可证。</span><span class="sxs-lookup"><span data-stu-id="c50d6-116">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span> <span data-ttu-id="c50d6-117">若要获取这些许可证，请参阅 [虚拟用户许可证](teams-add-on-licensing/virtual-user.md)。</span><span class="sxs-lookup"><span data-stu-id="c50d6-117">To obtain these licenses, see [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span>

<span data-ttu-id="c50d6-118">我们将在本文的后面部分介绍如何将许可证分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="c50d6-118">We cover how to assign the license to a resource account later in this article.</span></span>

<span data-ttu-id="c50d6-119">若要获取虚拟用户许可证，请在 Microsoft 365 管理中心中，转到 " **支付**  >  **购买服务**  >  **附加订阅** "，滚动到 "结束"，您将看到 " *电话系统-虚拟用户* 许可证"。</span><span class="sxs-lookup"><span data-stu-id="c50d6-119">To get the Virtual User license, in the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see *Phone System - Virtual User* license.</span></span> <span data-ttu-id="c50d6-120">选择 " **立即购买** "。</span><span class="sxs-lookup"><span data-stu-id="c50d6-120">Select **Buy now**.</span></span> <span data-ttu-id="c50d6-121">成本不为零，但仍需按照这些步骤获取许可证。</span><span class="sxs-lookup"><span data-stu-id="c50d6-121">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>

### <a name="obtain-service-numbers"></a><span data-ttu-id="c50d6-122">获取服务号码</span><span class="sxs-lookup"><span data-stu-id="c50d6-122">Obtain service numbers</span></span>

<span data-ttu-id="c50d6-123">服务号码对于自动助理和呼叫队列是可选的，但是您至少需要一个服务编号才能让呼叫者到达您的自动助理和呼叫队列配置。</span><span class="sxs-lookup"><span data-stu-id="c50d6-123">Service numbers are optional for auto attendants and call queues, however you will need at least one service number in order for callers to reach your auto attendant and call queue configuration.</span></span> <span data-ttu-id="c50d6-124">对于您希望通过服务号码直接访问的任何自动助理或呼叫队列，您必须有一个具有相关服务号码的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="c50d6-124">For any auto attendant or call queue that you want to be reachable directly by a service number, you must have a resource account with an associated service number.</span></span>

<span data-ttu-id="c50d6-125">资源帐户可以使用收费或免费服务号码。</span><span class="sxs-lookup"><span data-stu-id="c50d6-125">Resource accounts can use either toll or toll-free service numbers.</span></span> <span data-ttu-id="c50d6-126">您可以申请新号码或从其他运营商的现有号码中移植。</span><span class="sxs-lookup"><span data-stu-id="c50d6-126">You can request new numbers or port existing numbers from another carrier.</span></span>

<span data-ttu-id="c50d6-127">若要获取新的服务号码，请参阅 [获取服务电话号码](getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="c50d6-127">To get new service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="c50d6-128">若要从另一个运营商那里移植号码，请参阅 [将电话号码转移给团队](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="c50d6-128">To port a number from another carrier, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="c50d6-129">创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="c50d6-129">Create a resource account</span></span>

<span data-ttu-id="c50d6-130">可以在 "团队管理中心" 中创建资源帐户。</span><span class="sxs-lookup"><span data-stu-id="c50d6-130">You can create a resource account in the Teams admin center.</span></span>

![添加资源帐户用户界面的屏幕截图](media/resource-account-add.png)

1. <span data-ttu-id="c50d6-132">在 "团队管理中心" 中，展开 " **组织范围的设置** "，然后单击 " **资源帐户** "。</span><span class="sxs-lookup"><span data-stu-id="c50d6-132">In the Teams admin center, expand **Org-wide settings** , and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="c50d6-133">单击“添加”。</span><span class="sxs-lookup"><span data-stu-id="c50d6-133">Click **Add**.</span></span>

3. <span data-ttu-id="c50d6-134">在 " **添加资源帐户** " 窗格中，填写 " **显示名称** "、" **用户名** " 和 " **资源帐户类型** "。</span><span class="sxs-lookup"><span data-stu-id="c50d6-134">In the **Add resource account** pane, fill out **Display name** , **Username** , and the **Resource account type**.</span></span> <span data-ttu-id="c50d6-135">资源帐户类型可以是 **自动助理** 或 **呼叫队列** ，具体取决于你打算使用此资源帐户的方式。</span><span class="sxs-lookup"><span data-stu-id="c50d6-135">The resource account type can be either **Auto attendant** or **Call queue** , depending how you intend to use this resource account.</span></span>

4. <span data-ttu-id="c50d6-136">单击“ **保存** ”。</span><span class="sxs-lookup"><span data-stu-id="c50d6-136">Click **Save**.</span></span>

![资源帐户列表的屏幕截图](media/resource-accounts-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="c50d6-138">分配许可证</span><span class="sxs-lookup"><span data-stu-id="c50d6-138">Assign a license</span></span>

<span data-ttu-id="c50d6-139">对于每个资源帐户，您必须分配一个 *Microsoft 365 电话系统-虚拟用户* 许可证或 *电话系统* 许可证。</span><span class="sxs-lookup"><span data-stu-id="c50d6-139">For each resource account, you must assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![Microsoft 365 管理中心中分配许可证用户界面的屏幕截图](media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="c50d6-141">在 "Microsoft 365 管理中心" 中，单击要为其分配许可证的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="c50d6-141">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="c50d6-142">在 " **许可证和应用** " 选项卡上的 " **许可证** " 下，选择 " **Microsoft 365 Phone System-虚拟用户** "。</span><span class="sxs-lookup"><span data-stu-id="c50d6-142">On the **Licenses and Apps** tab, under **Licenses** , select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="c50d6-143">单击 " **保存更改** "。</span><span class="sxs-lookup"><span data-stu-id="c50d6-143">Click **Save changes**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="c50d6-144">分配服务号码</span><span class="sxs-lookup"><span data-stu-id="c50d6-144">Assign a service number</span></span>

<span data-ttu-id="c50d6-145">如果你打算将资源帐户与需要服务号码的自动助理或呼叫队列结合使用，请为资源帐户分配一个号码。</span><span class="sxs-lookup"><span data-stu-id="c50d6-145">If you're planning to use the resource account with an auto attendant or call queue that requires a service number, assign a number to the resource account.</span></span>

!["分配服务号码" 用户界面的屏幕截图](media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="c50d6-147">在 "团队" 管理中心的 " **资源帐户** " 页面上，选择要为其分配服务编号的资源帐户，然后单击 " **分配/取消分配** "。</span><span class="sxs-lookup"><span data-stu-id="c50d6-147">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="c50d6-148">在 " **电话号码类型** " 下拉列表中，选择要使用的号码类型。</span><span class="sxs-lookup"><span data-stu-id="c50d6-148">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="c50d6-149">在 " **分配的电话号码** " 框中，搜索要使用的号码，然后单击 " **添加** "。</span><span class="sxs-lookup"><span data-stu-id="c50d6-149">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

4. <span data-ttu-id="c50d6-150">单击“ **保存** ”。</span><span class="sxs-lookup"><span data-stu-id="c50d6-150">Click **Save**.</span></span>


<span data-ttu-id="c50d6-151">若要为资源帐户分配直接路由或混合号码，您需要使用 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="c50d6-151">To assign a direct routing or hybrid number to a resource account you need to use PowerShell:</span></span>

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a><span data-ttu-id="c50d6-152">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c50d6-152">Next steps</span></span>

<span data-ttu-id="c50d6-153">完成资源帐户设置并根据需要分配服务号码后，您就可以将资源帐户与自动助理或呼叫队列配合使用。</span><span class="sxs-lookup"><span data-stu-id="c50d6-153">Once you've completed the resource account setup and assigning a service number if needed, you're ready to use the resource account with an auto attendant or call queue.</span></span>

<span data-ttu-id="c50d6-154">请参阅以下参考资料：</span><span class="sxs-lookup"><span data-stu-id="c50d6-154">See the following references:</span></span>

 - [<span data-ttu-id="c50d6-155">云自动助理</span><span class="sxs-lookup"><span data-stu-id="c50d6-155">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

 - [<span data-ttu-id="c50d6-156">云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="c50d6-156">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)

<span data-ttu-id="c50d6-157">可以使用 " **编辑** " 选项编辑资源帐户的 " **显示名称** " 和 " **资源帐户** " 类型。</span><span class="sxs-lookup"><span data-stu-id="c50d6-157">You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="c50d6-158">完成后单击 " **保存** "。</span><span class="sxs-lookup"><span data-stu-id="c50d6-158">Click **Save** when you are done.</span></span>

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="c50d6-159">更改现有资源帐户以使用虚拟用户许可证</span><span class="sxs-lookup"><span data-stu-id="c50d6-159">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="c50d6-160">如果你决定将现有资源帐户上的许可证从 **电话系统** 许可证切换到虚拟用户许可证，你将需要获取免费的虚拟用户许可证，然后按照 Microsoft 365 管理中心中的步骤 [将用户移动到其他订阅](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。</span><span class="sxs-lookup"><span data-stu-id="c50d6-160">If you decide to switch the licenses on your existing resource account from a **Phone System** license to a Virtual User license, you'll need to acquire the free Virtual User license, and then follow the steps in the Microsoft 365 admin center to [Move users to a different subscription](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span></span>

> [!WARNING]
> <span data-ttu-id="c50d6-161">始终删除完整的电话系统许可证，并在同一许可证活动中分配虚拟用户许可证。</span><span class="sxs-lookup"><span data-stu-id="c50d6-161">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="c50d6-162">如果删除旧许可证，请保存帐户更改，添加新许可证，然后再次保存帐户设置，资源帐户可能不再按预期运行。</span><span class="sxs-lookup"><span data-stu-id="c50d6-162">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="c50d6-163">如果发生这种情况，我们建议你为虚拟用户许可证创建新的资源帐户，并删除断开的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="c50d6-163">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span>

## <a name="skype-for-business-server-2019"></a><span data-ttu-id="c50d6-164">Skype For Business 服务器2019</span><span class="sxs-lookup"><span data-stu-id="c50d6-164">Skype For Business Server 2019</span></span>

<span data-ttu-id="c50d6-165">对于驻留在可与云呼叫队列和云自动助理一起使用的 Skype For business Server 2019 上的资源帐户，请参阅 [计划云呼叫队列](/SkypeforBusiness/hybrid/plan-call-queue) 或 [计划云自动助理](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)。</span><span class="sxs-lookup"><span data-stu-id="c50d6-165">For resource accounts homed on Skype For Business Server 2019 that can be used with cloud call queues and cloud auto attendants, see [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span></span> <span data-ttu-id="c50d6-166">在直接路由) 上 (号码的混合实现使用本地 Skype for business Server 2019 服务器上的 [CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) cmdlet 进行配置。</span><span class="sxs-lookup"><span data-stu-id="c50d6-166">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="c50d6-167">创建应用程序实例时需要使用的应用程序 Id 如下：</span><span class="sxs-lookup"><span data-stu-id="c50d6-167">The application IDs that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="c50d6-168">**自动助理：** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="c50d6-168">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="c50d6-169">**呼叫队列：** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="c50d6-169">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="c50d6-170">如果您希望呼叫队列或自动助理可由 Skype For Business Server 2019 用户搜索，则应在 Skype For business Server 2019 上创建资源帐户，因为联机资源帐户未同步到 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="c50d6-170">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="c50d6-171">当 sipfederationtls 的 DNS SRV 记录解析到 Skype for business Server 2019 时， **必须** 使用 SfB Management shell 并同步到 Azure AD，在 Skype For business server 2019 上创建资源帐户。</span><span class="sxs-lookup"><span data-stu-id="c50d6-171">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to Azure AD.</span></span>

<span data-ttu-id="c50d6-172">对于与 Skype for business 服务器混合的实现：</span><span class="sxs-lookup"><span data-stu-id="c50d6-172">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="c50d6-173">规划云自动助理</span><span class="sxs-lookup"><span data-stu-id="c50d6-173">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="c50d6-174">规划云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="c50d6-174">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="c50d6-175">配置本地资源帐户</span><span class="sxs-lookup"><span data-stu-id="c50d6-175">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a><span data-ttu-id="c50d6-176">删除资源帐户</span><span class="sxs-lookup"><span data-stu-id="c50d6-176">Delete a resource account</span></span>

<span data-ttu-id="c50d6-177">请确保在删除之前将电话号码与资源帐户取消关联，以避免让你的服务号码滞留在挂起模式下。</span><span class="sxs-lookup"><span data-stu-id="c50d6-177">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span>

<span data-ttu-id="c50d6-178">执行此操作后，您可以在 Microsoft 365 管理中心的 "用户" 选项卡下删除该资源帐户。</span><span class="sxs-lookup"><span data-stu-id="c50d6-178">After you do that, you can delete the resource account in the Microsoft 365 admin center, under the Users tab.</span></span>

<span data-ttu-id="c50d6-179">若要解除直接路由电话号码与资源帐户的关联，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c50d6-179">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```
