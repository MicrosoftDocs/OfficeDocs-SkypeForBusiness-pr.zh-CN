---
title: 在 Skype for Business Server 2019 中配置资源帐户
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 为 Skype for business Server 2019 设置资源帐户。
ms.openlocfilehash: 33211f7dcd56e402167a3c810343947d4dfe0954
ms.sourcegitcommit: 868db85f0126e8f56d711ea590ad44acce8f96f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2019
ms.locfileid: "36160468"
---
# <a name="configure-resource-accounts"></a><span data-ttu-id="7b222-103">配置资源帐户</span><span class="sxs-lookup"><span data-stu-id="7b222-103">Configure resource accounts</span></span>

<span data-ttu-id="7b222-104">Skype for Business Server 2019 混合实施仅使用电话系统提供的用于统一消息的云服务, 不与 Exchange Online 集成。</span><span class="sxs-lookup"><span data-stu-id="7b222-104">Skype for Business Server 2019 hybrid implementations only use Cloud services provided by Phone System for unified messaging and do not integrate with Exchange Online.</span></span> <span data-ttu-id="7b222-105">在 Skype for Business Server 2019 中, 你现在可以使用[Office 365 中的电话系统获取](/MicrosoftTeams/here-s-what-you-get-with-phone-system)的云呼叫队列和自动助理。</span><span class="sxs-lookup"><span data-stu-id="7b222-105">In Skype for Business Server 2019 you are now able to use the Cloud call queues and auto attendants described in [Here's what you get with Phone System in Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).</span></span>

<span data-ttu-id="7b222-106">若要将这些电话系统服务与 Skype for Business Server 2019 一起使用, 您需要创建充当应用程序终结点且可分配电话号码的资源帐户, 然后使用联机团队管理中心配置呼叫队列或自动助理。</span><span class="sxs-lookup"><span data-stu-id="7b222-106">To use these Phone System services with Skype for Business Server 2019, you will need to create resource accounts that act as application endpoints and can be assigned phone numbers, then use the online Teams admin center to configure the call queue or auto attendant.</span></span> <span data-ttu-id="7b222-107">此资源帐户可以联机 (请参阅[在 Microsoft 团队中管理资源帐户](/MicrosoftTeams/manage-resource-accounts)以创建驻留在联机状态的资源帐户) 或本地, 如本文中所述。</span><span class="sxs-lookup"><span data-stu-id="7b222-107">This resource account can be homed online (see [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) to create resource accounts homed online) or on premise as described in this article.</span></span> <span data-ttu-id="7b222-108">通常会有多个电话系统服务节点, 每个节点都映射到可联机或在 Skype for Business Server 2019 中的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="7b222-108">Typically you will have multiple Phone System service nodes, each of which is mapped to a resource accounts, which can be homed online or in Skype for Business Server 2019.</span></span>

<span data-ttu-id="7b222-109">如果你有一个现有的 Exchange UM 自动助理和呼叫队列系统, 则在切换到 Exchange Server 2019 或 Exchange online 之前, 你需要手动记录详细信息, 然后使用团队管理中心实施全新的系统.</span><span class="sxs-lookup"><span data-stu-id="7b222-109">If you have an existing Exchange UM auto attendant and call queue system, before you switch to Exchange Server 2019 or Exchange online you will need to manually record the details as described below and then implement a completely new system using the Teams admin center.</span></span>

## <a name="overview"></a><span data-ttu-id="7b222-110">概述</span><span class="sxs-lookup"><span data-stu-id="7b222-110">Overview</span></span>

<span data-ttu-id="7b222-111">如果您的电话系统服务需要服务号码, 则可以按以下顺序满足各种依存关系:</span><span class="sxs-lookup"><span data-stu-id="7b222-111">If your Phone System service will need a service number, the various dependencies can be met in the following sequence:</span></span>

1. <span data-ttu-id="7b222-112">获取服务号码</span><span class="sxs-lookup"><span data-stu-id="7b222-112">Obtain a service number</span></span>
2. <span data-ttu-id="7b222-113">购买电话系统许可证</span><span class="sxs-lookup"><span data-stu-id="7b222-113">Buy a Phone System license</span></span>
3. <span data-ttu-id="7b222-114">创建资源帐户。</span><span class="sxs-lookup"><span data-stu-id="7b222-114">Create the resource account.</span></span> <span data-ttu-id="7b222-115">自动助理或呼叫队列必须具有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="7b222-115">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="7b222-116">在联机和本地之间等待 active directory 同步</span><span class="sxs-lookup"><span data-stu-id="7b222-116">Wait for an active directory sync between online and on premise</span></span>
5. <span data-ttu-id="7b222-117">将电话系统许可证分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="7b222-117">Assign the Phone System license to the resource account.</span></span>
6. <span data-ttu-id="7b222-118">向资源帐户分配服务号码。</span><span class="sxs-lookup"><span data-stu-id="7b222-118">Assign a service number to the resource account.</span></span>
7. <span data-ttu-id="7b222-119">创建电话系统服务 (呼叫队列或自动助理)</span><span class="sxs-lookup"><span data-stu-id="7b222-119">Create a Phone System service (a call queue or auto attendant)</span></span>
8. <span data-ttu-id="7b222-120">将资源帐户与服务关联: (CsApplicationInstanceAssociation)</span><span class="sxs-lookup"><span data-stu-id="7b222-120">Associate the resource account with a service: (New-CsApplicationInstanceAssociation)</span></span>

<span data-ttu-id="7b222-121">如果自动助理或呼叫队列嵌套在顶级自动助理下, 则关联的资源帐户只需要一个电话号码, 如果您希望将多个点输入到自动助理和呼叫队列的结构中。</span><span class="sxs-lookup"><span data-stu-id="7b222-121">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="7b222-122">若要将呼叫重定向到组织中已联机的人员, 他们必须具有**电话系统**许可证并启用企业语音或拥有 Office 365 通话套餐。</span><span class="sxs-lookup"><span data-stu-id="7b222-122">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="7b222-123">请参阅[分配 Microsoft 团队许可证](/MicrosoftTeams/assign-teams-licenses)。</span><span class="sxs-lookup"><span data-stu-id="7b222-123">See [Assign Microsoft Teams licenses](/MicrosoftTeams/assign-teams-licenses).</span></span> <span data-ttu-id="7b222-124">若要为企业语音启用它们, 可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="7b222-124">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="7b222-125">例如, 运行:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="7b222-125">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

<span data-ttu-id="7b222-126">如果要创建的电话系统服务将嵌套, 并且不需要电话号码, 则该过程为:</span><span class="sxs-lookup"><span data-stu-id="7b222-126">If the Phone system service you're creating will be nested and will not need a phone number, the process is:</span></span>

1. <span data-ttu-id="7b222-127">创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="7b222-127">Create the resource account</span></span>  
2. <span data-ttu-id="7b222-128">在联机和本地之间等待 active directory 同步</span><span class="sxs-lookup"><span data-stu-id="7b222-128">Wait for an active directory sync between online and on premise</span></span>
3. <span data-ttu-id="7b222-129">创建电话系统服务</span><span class="sxs-lookup"><span data-stu-id="7b222-129">Create a Phone System service</span></span>
4. <span data-ttu-id="7b222-130">将资源帐户与电话系统服务关联</span><span class="sxs-lookup"><span data-stu-id="7b222-130">Associate the resource account with a Phone System service</span></span>

## <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="7b222-131">创建具有电话号码的资源帐户</span><span class="sxs-lookup"><span data-stu-id="7b222-131">Create a resource account with a phone number</span></span>

<span data-ttu-id="7b222-132">若要创建使用电话号码的资源帐户, 需要按以下顺序执行以下任务:</span><span class="sxs-lookup"><span data-stu-id="7b222-132">Creating a resource account that uses a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="7b222-133">端口或获取收费或免费服务号码。</span><span class="sxs-lookup"><span data-stu-id="7b222-133">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="7b222-134">该号码不能分配给任何其他语音服务或资源帐户。</span><span class="sxs-lookup"><span data-stu-id="7b222-134">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="7b222-135">在向资源帐户分配电话号码之前, 需要获取或移植现有收费或免费服务号码。</span><span class="sxs-lookup"><span data-stu-id="7b222-135">Before you assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="7b222-136">获取收费或免费服务电话号码后, 它们将显示在**Microsoft 团队管理中心** > **的语音** > **电话号码**中, 并且列出的**号码类型**将列为 "**服务-免费**"。</span><span class="sxs-lookup"><span data-stu-id="7b222-136">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="7b222-137">若要获取服务号码, 请参阅[获取服务电话号码](/MicrosoftTeams/getting-service-phone-numbers); 如果要转移现有服务号码, 请参阅[将电话号码转移到 Office 365](/MicrosoftTeams/transfer-phone-numbers-to-office-365)。</span><span class="sxs-lookup"><span data-stu-id="7b222-137">To get your service numbers, see [Getting service phone numbers](/MicrosoftTeams/getting-service-phone-numbers) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](/MicrosoftTeams/transfer-phone-numbers-to-office-365).</span></span>

   <span data-ttu-id="7b222-138">如果你在美国之外, 则无法使用 Microsoft 团队管理中心获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="7b222-138">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="7b222-139">转到 "[管理你的组织的电话号码](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)", 以了解如何从美国以外的地区执行此操作。</span><span class="sxs-lookup"><span data-stu-id="7b222-139">Go to [Manage phone numbers for your organization](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.</span></span>

2. <span data-ttu-id="7b222-140">购买电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="7b222-140">Buy a Phone System license.</span></span> <span data-ttu-id="7b222-141">请参阅：</span><span class="sxs-lookup"><span data-stu-id="7b222-141">See:</span></span>  
   - [<span data-ttu-id="7b222-142">Office 365 企业版 E1 和 E3</span><span class="sxs-lookup"><span data-stu-id="7b222-142">Office 365 Enterprise E1 and E3</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [<span data-ttu-id="7b222-143">Office 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="7b222-143">Office 365 Enterprise E5</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [<span data-ttu-id="7b222-144">Office 365 企业版 E5 商业版软件</span><span class="sxs-lookup"><span data-stu-id="7b222-144">Office 365 Enterprise E5 Business Software</span></span>](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. <span data-ttu-id="7b222-145">通过对每个电话系统服务运行`New-CsHybridApplicationEndpoint` cmdlet 来创建本地资源帐户, 并为每个帐户分配一个名称、sip 地址等。</span><span class="sxs-lookup"><span data-stu-id="7b222-145">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System service, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="7b222-146">有关此命令的更多详细信息, 请参阅[CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="7b222-146">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

4. <span data-ttu-id="7b222-147">Optional创建资源帐户后, 您可以等待 AD 在联机和本地之间同步, 或者强制进行同步并继续进行电话系统服务的联机配置。</span><span class="sxs-lookup"><span data-stu-id="7b222-147">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premise, or force a sync and proceed to online configuration of Phone System services.</span></span> <span data-ttu-id="7b222-148">若要强制进行同步, 请在运行 AAD 连接的计算机上运行以下命令 (如果尚未执行此操作, 则需要加载`import-module adsync`才能运行该命令):</span><span class="sxs-lookup"><span data-stu-id="7b222-148">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="7b222-149">有关此命令的更多详细信息, 请参阅[ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 。</span><span class="sxs-lookup"><span data-stu-id="7b222-149">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

5. <span data-ttu-id="7b222-150">将电话系统许可证分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="7b222-150">Assign the Phone System license to the resource account.</span></span> <span data-ttu-id="7b222-151">请参阅[分配 Microsoft 团队许可证](/MicrosoftTeams/assign-teams-licenses)和[将许可证分配给一个用户](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user)。</span><span class="sxs-lookup"><span data-stu-id="7b222-151">See [Assign Microsoft Teams licenses](/MicrosoftTeams/assign-teams-licenses) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>

    <span data-ttu-id="7b222-152">如果要将电话号码分配给资源帐户, 现在可以使用免费电话系统虚拟用户许可证。</span><span class="sxs-lookup"><span data-stu-id="7b222-152">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="7b222-153">这样可以在组织级别为电话号码提供电话系统功能, 并允许您创建自动助理和呼叫队列功能。</span><span class="sxs-lookup"><span data-stu-id="7b222-153">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>


6. <span data-ttu-id="7b222-154">向资源帐户分配服务号码。</span><span class="sxs-lookup"><span data-stu-id="7b222-154">Assign the service number to the resource account.</span></span> <span data-ttu-id="7b222-155">使用`Set-CsHybridApplicationEndpoint`命令将电话号码 (带有-LineURI 选项) 分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="7b222-155">Use the `Set-CsHybridApplicationEndpoint` command to a assign a phone number (with the -LineURI option) to the resource account.</span></span>

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    <span data-ttu-id="7b222-156">有关此命令的详细信息, 请参阅[CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="7b222-156">See [Set-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

    <span data-ttu-id="7b222-157">若要向资源帐户分配直接路由或混合号码, 请使用以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7b222-157">To assign a direct routing or hybrid number to  a resource account, use the following cmdlet:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

<span data-ttu-id="7b222-158">如果资源帐户将分配给顶级自动助理或呼叫队列, 则该帐户将需要已分配的电话号码。</span><span class="sxs-lookup"><span data-stu-id="7b222-158">The resource account will need an assigned phone number if it will be assigned to a top level auto attendant or call queue.</span></span> <span data-ttu-id="7b222-159">无法将用户 (订阅者) 电话号码分配给资源帐户, 只能使用服务收费或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="7b222-159">User (subscriber) phone numbers can't be assigned to a resource account, only service toll or toll-free phone numbers can be used.</span></span>

    You can assign a Direct Routing Hybrid number to your resource account.  See [Plan Direct Routing](direct-routing-plan) for details.

    > [!NOTE]
    > Direct Routing service numbers assigned to resource accounts for auto attendant and call queues are supported for Microsoft Teams users and agents only.

    > [!NOTE]
    > Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.

7. <span data-ttu-id="7b222-160">创建电话系统服务。</span><span class="sxs-lookup"><span data-stu-id="7b222-160">Create the Phone system service.</span></span> <span data-ttu-id="7b222-161">请查看下列内容之一：</span><span class="sxs-lookup"><span data-stu-id="7b222-161">See one of the following:</span></span>

   - [<span data-ttu-id="7b222-162">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="7b222-162">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="7b222-163">创建云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="7b222-163">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. <span data-ttu-id="7b222-164">将资源帐户与以前选择的电话系统服务相关联。</span><span class="sxs-lookup"><span data-stu-id="7b222-164">Associate the resource account with the Phone system service you chose previously.</span></span>

<span data-ttu-id="7b222-165">小型企业版实施的示例在小型企业版中提供示例[-设置自动助理](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml)和[小型企业示例-设置呼叫队列](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml)。</span><span class="sxs-lookup"><span data-stu-id="7b222-165">An example of a small business implementation is available in  [Small business example - Set up an auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) and [Small business example - Set up a call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).</span></span>

## <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="7b222-166">创建不带电话号码的资源帐户</span><span class="sxs-lookup"><span data-stu-id="7b222-166">Create a resource account without a phone number</span></span>

<span data-ttu-id="7b222-167">本节讨论如何创建驻留在本地的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="7b222-167">This section discusses creating a resource account that is homed on premise.</span></span> <span data-ttu-id="7b222-168">在[Microsoft 团队中的 "管理资源帐户" 中](/MicrosoftTeams/manage-resource-accounts)讨论了如何创建驻留在联机状态的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="7b222-168">Creating a resource account that is homed online is discussed at [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).</span></span>

<span data-ttu-id="7b222-169">无论您是创建全新的电话系统服务系统, 还是在 Exchange UM 中最初创建的结构重建, 都必须执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="7b222-169">These steps are necessary whether you are creating a brand new Phone System service system, or rebuilding structure originally created in Exchange UM.</span></span>

<span data-ttu-id="7b222-170">登录到 Skype for Business 前端服务器并运行以下 PowerShell cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7b222-170">Log in to the Skype for Business front end server and run the following PowerShell cmdlets:</span></span>

1. <span data-ttu-id="7b222-171">通过对每个电话系统服务运行`New-CsHybridApplicationEndpoint` cmdlet 来创建本地资源帐户, 并为每个帐户分配一个名称、sip 地址等。</span><span class="sxs-lookup"><span data-stu-id="7b222-171">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System service, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="7b222-172">有关此命令的更多详细信息, 请参阅[CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="7b222-172">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

2. <span data-ttu-id="7b222-173">Optional创建资源帐户后, 您可以等待 AD 在联机和本地之间同步, 或者强制进行同步并继续进行电话系统服务的联机配置。</span><span class="sxs-lookup"><span data-stu-id="7b222-173">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premise, or force a sync and proceed to online configuration of Phone System services.</span></span> <span data-ttu-id="7b222-174">若要强制进行同步, 请在运行 AAD 连接的计算机上运行以下命令 (如果尚未执行此操作, 则需要加载`import-module adsync`才能运行该命令):</span><span class="sxs-lookup"><span data-stu-id="7b222-174">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="7b222-175">有关此命令的更多详细信息, 请参阅[ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 。</span><span class="sxs-lookup"><span data-stu-id="7b222-175">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

3. <span data-ttu-id="7b222-176">创建电话系统服务。</span><span class="sxs-lookup"><span data-stu-id="7b222-176">Create the Phone system service.</span></span> <span data-ttu-id="7b222-177">请查看下列内容之一：</span><span class="sxs-lookup"><span data-stu-id="7b222-177">See one of the following:</span></span>
   - [<span data-ttu-id="7b222-178">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="7b222-178">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="7b222-179">创建云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="7b222-179">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. <span data-ttu-id="7b222-180">关联以前选择的资源帐户和电话系统服务。</span><span class="sxs-lookup"><span data-stu-id="7b222-180">Associate the resource account and the Phone System service you chose previously.</span></span>

<span data-ttu-id="7b222-181">小型企业版实施的示例在小型企业版中提供示例[-设置自动助理](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml)和[小型企业示例-设置呼叫队列](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml)。</span><span class="sxs-lookup"><span data-stu-id="7b222-181">An example of a small business implementation is available in  [Small business example - Set up an auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) and [Small business example - Set up a call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).</span></span>

## <a name="test-the-implementation"></a><span data-ttu-id="7b222-182">测试实现</span><span class="sxs-lookup"><span data-stu-id="7b222-182">Test the implementation</span></span>

<span data-ttu-id="7b222-183">测试实现的最佳方式是调用为电话系统服务配置的号码, 并连接到其中一个代理或菜单。</span><span class="sxs-lookup"><span data-stu-id="7b222-183">The best way to test the implementation is to call the number configured for a Phone System service and connect to one of the agents or menus.</span></span> <span data-ttu-id="7b222-184">您还可以通过使用管理中心操作窗格中的 "**测试" 按钮**来快速发出测试呼叫。</span><span class="sxs-lookup"><span data-stu-id="7b222-184">You can also quickly place a test call by using the **Test button** in the admin center Action pane.</span></span> <span data-ttu-id="7b222-185">如果要对电话系统服务进行更改, 请选择它, 然后在操作窗格中单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="7b222-185">If you want to make changes to a Phone System service, select it and then in the Action pane click **Edit**.</span></span>

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a><span data-ttu-id="7b222-186">将 Exchange UM 自动助理或呼叫队列移动到电话系统</span><span class="sxs-lookup"><span data-stu-id="7b222-186">Moving an Exchange UM auto attendant or call queue to Phone System</span></span>

<span data-ttu-id="7b222-187">从 Exchange UM 迁移到电话系统将需要重新创建呼叫队列和自动助理结构, 而不支持直接从一个迁移到另一个。</span><span class="sxs-lookup"><span data-stu-id="7b222-187">Migration from Exchange UM to Phone System will require recreating the call queue and auto attendant structure, directly migrating from one to the other is not supported.</span></span> <span data-ttu-id="7b222-188">若要重新实现一组呼叫队列和自动助理, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="7b222-188">To re-implement a set of call queues and auto attendants:</span></span>

1. <span data-ttu-id="7b222-189">在以管理员身份登录时, 通过在 Exchange 2013 或2016系统上运行以下命令来获取所有 Exchange UM 自动助理和呼叫队列的列表:</span><span class="sxs-lookup"><span data-stu-id="7b222-189">Get a list of all Exchange UM auto attendants and call queues by running the following command on the Exchange 2013 or 2016 system while logged in as admin:</span></span>

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. <span data-ttu-id="7b222-190">对于每个列出的 Exchange UM 呼叫队列或自动助理, 请注意其在结构中的位置、设置, 以及获取关联的声音或文本到语音转换文件的副本 (输出中的 guid 将是存储文件的文件夹的名称)。</span><span class="sxs-lookup"><span data-stu-id="7b222-190">For each listed Exchange UM call queue or auto attendant, note its place in the structure, settings, and get copies of associated sound or text-to-speech files (the guid in the output will be the name of a folder where the files are stored).</span></span> <span data-ttu-id="7b222-191">可以通过运行以下命令获取这些详细信息:</span><span class="sxs-lookup"><span data-stu-id="7b222-191">You can get these details by running the command:</span></span>

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    <span data-ttu-id="7b222-192">有关此命令的详细信息, 请参阅[get-umautoattendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) 。</span><span class="sxs-lookup"><span data-stu-id="7b222-192">See [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) for more details on this command.</span></span> <span data-ttu-id="7b222-193">您可能需要捕获的选项的完整列表是在[get-umautoattendant 成员](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx)处, 但要注意的最重要的选项是:</span><span class="sxs-lookup"><span data-stu-id="7b222-193">A complete list of options you might need to capture is at [UMAutoAttendant members](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) but the most important options to note down are:</span></span>

    - <span data-ttu-id="7b222-194">营业时间</span><span class="sxs-lookup"><span data-stu-id="7b222-194">Business hours</span></span>
    - <span data-ttu-id="7b222-195">非工作时间</span><span class="sxs-lookup"><span data-stu-id="7b222-195">Non-business hours</span></span>
    - <span data-ttu-id="7b222-196">Language</span><span class="sxs-lookup"><span data-stu-id="7b222-196">Language</span></span>
    - <span data-ttu-id="7b222-197">假日日程安排</span><span class="sxs-lookup"><span data-stu-id="7b222-197">Holiday schedule</span></span>

3. <span data-ttu-id="7b222-198">按照前面所述, 创建新的本地终结点。</span><span class="sxs-lookup"><span data-stu-id="7b222-198">Create new on-premises endpoints as previously described.</span></span>
   <span data-ttu-id="7b222-199">为顶级自动助理分配一个用于测试目的的临时编号。</span><span class="sxs-lookup"><span data-stu-id="7b222-199">Assign the top-level auto attendant a temporary number for testing purposes.</span></span>

4. <span data-ttu-id="7b222-200">配置使用前面所述的终结点的电话系统服务。</span><span class="sxs-lookup"><span data-stu-id="7b222-200">Configure a Phone system service that uses the endpoints as previously described.</span></span>

   <span data-ttu-id="7b222-201">您可能会发现, 在教程中使用标题为 "小型企业版" 的练习,[设置自动助理](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml), 以创建旧 Exchange UM 系统中的层次结构的逻辑地图。</span><span class="sxs-lookup"><span data-stu-id="7b222-201">You may find it useful to use the exercises in the tutorial titled [Small business example - Set up an auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) to create a logical map of the hierarchies in your old Exchange UM system.</span></span>
5. <span data-ttu-id="7b222-202">测试电话系统服务。</span><span class="sxs-lookup"><span data-stu-id="7b222-202">Test the Phone System service.</span></span>
6. <span data-ttu-id="7b222-203">将链接到 Exchange UM 呼叫队列或自动助理的电话号码重新分配给相应的电话系统服务。</span><span class="sxs-lookup"><span data-stu-id="7b222-203">Reassign the phone number linked to the Exchange UM call queue or auto attendant to the corresponding Phone system service.</span></span>  

   <span data-ttu-id="7b222-204">在这种情况下, 如果您已经迁移了 UM 语音邮件, 则应在迁移到 Exchange Server 2019 的位置。</span><span class="sxs-lookup"><span data-stu-id="7b222-204">At this point, if you have already migrated UM Voicemail, you should be in a position to migrate to Exchange Server 2019.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b222-205">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b222-205">See Also</span></span>

[<span data-ttu-id="7b222-206">创建云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="7b222-206">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)

[<span data-ttu-id="7b222-207">什么是云自动助理？</span><span class="sxs-lookup"><span data-stu-id="7b222-207">What are Cloud auto attendants?</span></span>](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[<span data-ttu-id="7b222-208">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="7b222-208">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[<span data-ttu-id="7b222-209">规划云自动助理</span><span class="sxs-lookup"><span data-stu-id="7b222-209">Plan Cloud auto attendants</span></span>](plan-cloud-auto-attendant.md)

[<span data-ttu-id="7b222-210">规划云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="7b222-210">Plan Cloud call queues</span></span>](plan-call-queue.md)

[<span data-ttu-id="7b222-211">为本地用户规划云语音邮件服务</span><span class="sxs-lookup"><span data-stu-id="7b222-211">Plan Cloud Voicemail service for on-premises users</span></span>](plan-cloud-voicemail.md)

[<span data-ttu-id="7b222-212">新 CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="7b222-212">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="7b222-213">新 CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="7b222-213">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

<span data-ttu-id="7b222-214">[在 Microsoft 团队](/MicrosoftTeams/manage-resource-accounts) - \(中管理资源帐户以创建托管联机的资源帐户\)</span><span class="sxs-lookup"><span data-stu-id="7b222-214">[Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \(to create resource accounts homed online\)</span></span>
