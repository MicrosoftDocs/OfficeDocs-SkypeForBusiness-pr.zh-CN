---
title: 在 Skype for Business Server 2019 中配置资源帐户
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 为 Skype for business Server 2019 设置资源帐户。
ms.openlocfilehash: b5397a1d179ade5e9d70d6c9cf857bae9319d155
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221132"
---
# <a name="configure-resource-accounts"></a><span data-ttu-id="f2857-103">配置资源帐户</span><span class="sxs-lookup"><span data-stu-id="f2857-103">Configure resource accounts</span></span>

<span data-ttu-id="f2857-104">Skype for Business Server 2019 混合实施仅使用电话系统提供的用于统一消息的云服务，不与 Exchange Online 集成。</span><span class="sxs-lookup"><span data-stu-id="f2857-104">Skype for Business Server 2019 hybrid implementations only use Cloud services provided by Phone System for unified messaging and do not integrate with Exchange Online.</span></span> <span data-ttu-id="f2857-105">在 Skype for Business Server 2019 中，你现在可以使用此处介绍的云呼叫队列和自动助理，这些[是 Microsoft 365 或 Office 365 中的电话系统获取的内容](/MicrosoftTeams/here-s-what-you-get-with-phone-system)。</span><span class="sxs-lookup"><span data-stu-id="f2857-105">In Skype for Business Server 2019 you are now able to use the Cloud call queues and auto attendants described in [Here's what you get with Phone System in Microsoft 365 or Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).</span></span>

<span data-ttu-id="f2857-106">若要将电话系统自动助理或呼叫队列与 Skype for Business Server 2019 一起使用，您需要创建充当应用程序终结点且可分配电话号码的资源帐户，然后使用联机团队管理中心配置呼叫队列或自动助理。</span><span class="sxs-lookup"><span data-stu-id="f2857-106">To use an Phone System auto attendant or call queue with Skype for Business Server 2019, you will need to create resource accounts that act as application endpoints and can be assigned phone numbers, then use the online Teams admin center to configure the call queue or auto attendant.</span></span> <span data-ttu-id="f2857-107">此资源帐户可以联机（请参阅[在 Microsoft 团队中管理资源帐户](/MicrosoftTeams/manage-resource-accounts)以创建托管资源帐户）或本地部署，如本文中所述。</span><span class="sxs-lookup"><span data-stu-id="f2857-107">This resource account can be homed online (see [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) to create resource accounts homed online) or on premises as described in this article.</span></span> <span data-ttu-id="f2857-108">通常，您将具有多个电话系统自动助理或呼叫队列节点，每个节点都映射到可联机或在 Skype for business Server 2019 中的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="f2857-108">Typically you will have multiple Phone System auto attendant or call queue nodes, each of which is mapped to a resource accounts, which can be homed online or in Skype for Business Server 2019.</span></span>

<span data-ttu-id="f2857-109">如果你有一个现有的 Exchange UM 自动助理和呼叫队列系统，则在切换到 Exchange Server 2019 或 Exchange online 之前，你需要手动记录详细信息，然后使用团队管理中心实施全新的系统。</span><span class="sxs-lookup"><span data-stu-id="f2857-109">If you have an existing Exchange UM auto attendant and call queue system, before you switch to Exchange Server 2019 or Exchange online you will need to manually record the details as described below and then implement a completely new system using the Teams admin center.</span></span>

## <a name="overview"></a><span data-ttu-id="f2857-110">概述</span><span class="sxs-lookup"><span data-stu-id="f2857-110">Overview</span></span>

<span data-ttu-id="f2857-111">如果电话系统自动助理或呼叫队列将需要服务号码，则可以按以下顺序满足各种相关性：</span><span class="sxs-lookup"><span data-stu-id="f2857-111">If your Phone System auto attendant or call queue will need a service number, the various dependencies can be met in the following sequence:</span></span>

1. <span data-ttu-id="f2857-112">获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="f2857-112">Obtain a service number.</span></span>
2. <span data-ttu-id="f2857-113">获取免费的电话系统-[虚拟用户许可证](/MicrosoftTeams/teams-add-on-licensing/virtual-user)或付费电话系统许可证以与资源帐户一起使用。</span><span class="sxs-lookup"><span data-stu-id="f2857-113">Obtain a free Phone System - [Virtual User license](/MicrosoftTeams/teams-add-on-licensing/virtual-user) or a paid Phone System license to use with the resource account.</span></span>
3. <span data-ttu-id="f2857-114">创建资源帐户。</span><span class="sxs-lookup"><span data-stu-id="f2857-114">Create the resource account.</span></span> <span data-ttu-id="f2857-115">自动助理或呼叫队列必须具有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="f2857-115">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="f2857-116">在联机和本地之间等待 active directory 同步。</span><span class="sxs-lookup"><span data-stu-id="f2857-116">Wait for an active directory sync between online and on premises.</span></span>
5. <span data-ttu-id="f2857-117">将电话系统许可证分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="f2857-117">Assign the Phone System license to the resource account.</span></span>
6. <span data-ttu-id="f2857-118">向资源帐户分配服务号码。</span><span class="sxs-lookup"><span data-stu-id="f2857-118">Assign a service number to the resource account.</span></span>
7. <span data-ttu-id="f2857-119">创建电话系统呼叫队列或自动助理。</span><span class="sxs-lookup"><span data-stu-id="f2857-119">Create a Phone System call queue or auto attendant.</span></span>
8. <span data-ttu-id="f2857-120">将资源帐户与自动助理或呼叫队列关联：（CsApplicationInstanceAssociation）。</span><span class="sxs-lookup"><span data-stu-id="f2857-120">Associate the resource account with an auto attendant or call queue: (New-CsApplicationInstanceAssociation).</span></span>

<span data-ttu-id="f2857-121">如果自动助理或呼叫队列嵌套在顶级自动助理下，则关联的资源帐户只需要一个电话号码，如果您希望将多个点输入到自动助理和呼叫队列的结构中。</span><span class="sxs-lookup"><span data-stu-id="f2857-121">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="f2857-122">若要将呼叫重定向到组织中已联机的人员，他们必须具有**电话系统**许可证并启用企业语音或拥有 Microsoft 365 或 Office 365 通话套餐。</span><span class="sxs-lookup"><span data-stu-id="f2857-122">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Microsoft 365 or Office 365 Calling Plans.</span></span> <span data-ttu-id="f2857-123">请参阅[分配 Microsoft 团队许可证](/MicrosoftTeams/assign-teams-licenses)。</span><span class="sxs-lookup"><span data-stu-id="f2857-123">See [Assign Microsoft Teams licenses](/MicrosoftTeams/assign-teams-licenses).</span></span> <span data-ttu-id="f2857-124">若要为企业语音启用它们，可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="f2857-124">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="f2857-125">例如，运行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="f2857-125">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

<span data-ttu-id="f2857-126">如果要创建的电话系统自动助理或呼叫队列将嵌套，并且不需要电话号码，则该过程为：</span><span class="sxs-lookup"><span data-stu-id="f2857-126">If the Phone system auto attendant or call queue you're creating will be nested and will not need a phone number, the process is:</span></span>

1. <span data-ttu-id="f2857-127">创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="f2857-127">Create the resource account</span></span>  
2. <span data-ttu-id="f2857-128">在联机和本地之间等待 active directory 同步</span><span class="sxs-lookup"><span data-stu-id="f2857-128">Wait for an active directory sync between online and on premises</span></span>
3. <span data-ttu-id="f2857-129">创建电话系统自动助理或呼叫队列</span><span class="sxs-lookup"><span data-stu-id="f2857-129">Create a Phone System auto attendant or call queue</span></span>
4. <span data-ttu-id="f2857-130">将资源帐户与电话系统自动助理或呼叫队列关联</span><span class="sxs-lookup"><span data-stu-id="f2857-130">Associate the resource account with a Phone System auto attendant or call queue</span></span>

## <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="f2857-131">创建具有电话号码的资源帐户</span><span class="sxs-lookup"><span data-stu-id="f2857-131">Create a resource account with a phone number</span></span>

<span data-ttu-id="f2857-132">若要创建使用电话号码的资源帐户，需要按以下顺序执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="f2857-132">Creating a resource account that uses a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="f2857-133">端口或获取收费或免费服务号码。</span><span class="sxs-lookup"><span data-stu-id="f2857-133">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="f2857-134">该号码不能分配给任何其他语音服务或资源帐户。</span><span class="sxs-lookup"><span data-stu-id="f2857-134">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="f2857-135">在向资源帐户分配电话号码之前，需要获取或移植现有收费或免费服务号码。</span><span class="sxs-lookup"><span data-stu-id="f2857-135">Before you assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="f2857-136">获取收费或免费服务电话号码后，它们将显示在**Microsoft 团队管理中心**的  >  **语音**  >  **电话号码**中，并且列出的**号码类型**将列为 "**服务-免费**"。</span><span class="sxs-lookup"><span data-stu-id="f2857-136">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="f2857-137">若要获取服务号码，请参阅[获取服务电话号码](/MicrosoftTeams/getting-service-phone-numbers); 如果要转移现有服务号码，请参阅[将电话号码转移给团队](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams)。</span><span class="sxs-lookup"><span data-stu-id="f2857-137">To get your service numbers, see [Getting service phone numbers](/MicrosoftTeams/getting-service-phone-numbers) or if you want to transfer an existing service number, see [Transfer phone numbers to Teams](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams).</span></span>

   <span data-ttu-id="f2857-138">如果你在美国之外，则无法使用 Microsoft 团队管理中心获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="f2857-138">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="f2857-139">转到 "[管理你的组织的电话号码](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)"，以了解如何从美国以外的地区执行此操作。</span><span class="sxs-lookup"><span data-stu-id="f2857-139">Go to [Manage phone numbers for your organization](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.</span></span>

2. <span data-ttu-id="f2857-140">购买电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="f2857-140">Buy a Phone System license.</span></span> <span data-ttu-id="f2857-141">请参阅：</span><span class="sxs-lookup"><span data-stu-id="f2857-141">See:</span></span>  
   - [<span data-ttu-id="f2857-142">电话系统–虚拟用户许可证</span><span class="sxs-lookup"><span data-stu-id="f2857-142">Phone System–Virtual User license</span></span>](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [<span data-ttu-id="f2857-143">Office 365 企业版（E1 和 E3）</span><span class="sxs-lookup"><span data-stu-id="f2857-143">Office 365 Enterprise E1 and E3</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [<span data-ttu-id="f2857-144">Office 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="f2857-144">Office 365 Enterprise E5</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [<span data-ttu-id="f2857-145">Office 365 企业版 E5 商业版软件</span><span class="sxs-lookup"><span data-stu-id="f2857-145">Office 365 Enterprise E5 Business Software</span></span>](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. <span data-ttu-id="f2857-146">通过对 `New-CsHybridApplicationEndpoint` 每个电话系统自动助理或呼叫队列运行 cmdlet 来创建本地资源帐户，并为每个电话系统自动助理或呼叫队列分配一个名称、sip 地址等。</span><span class="sxs-lookup"><span data-stu-id="f2857-146">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System auto attendant or call queue, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="f2857-147">有关此命令的更多详细信息，请参阅[CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="f2857-147">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

4. <span data-ttu-id="f2857-148">Optional创建资源帐户后，您可以等待 AD 在联机和内部部署之间同步，或者强制进行同步并继续进行电话系统自动助理或呼叫队列的联机配置。</span><span class="sxs-lookup"><span data-stu-id="f2857-148">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premises, or force a sync and proceed to online configuration of Phone System auto attendant or call queues.</span></span> <span data-ttu-id="f2857-149">若要强制进行同步，请在运行 AAD 连接的计算机上运行以下命令（如果尚未执行此操作，则需要加载 `import-module adsync` 才能运行该命令）：</span><span class="sxs-lookup"><span data-stu-id="f2857-149">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="f2857-150">有关此命令的更多详细信息，请参阅[ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 。</span><span class="sxs-lookup"><span data-stu-id="f2857-150">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

5. <span data-ttu-id="f2857-151">将电话系统-虚拟用户或电话系统许可证分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="f2857-151">Assign the Phone System - Virtual User or Phone System license to the resource account.</span></span> <span data-ttu-id="f2857-152">请参阅[分配 Microsoft 团队附加许可证](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses)和[将许可证分配给一个用户](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user)。</span><span class="sxs-lookup"><span data-stu-id="f2857-152">See [Assign Microsoft Teams add-on licenses](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>

   <span data-ttu-id="f2857-153">如果要将电话号码分配给资源帐户，现在可以使用免费电话系统-虚拟用户许可证。</span><span class="sxs-lookup"><span data-stu-id="f2857-153">If you are assigning a phone number to a resource account you can now use the cost-free Phone System - Virtual User license.</span></span> <span data-ttu-id="f2857-154">这样可以在组织级别为电话号码提供电话系统功能，并允许您创建自动助理和呼叫队列功能。</span><span class="sxs-lookup"><span data-stu-id="f2857-154">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>


6. <span data-ttu-id="f2857-155">向资源帐户分配服务号码。</span><span class="sxs-lookup"><span data-stu-id="f2857-155">Assign the service number to the resource account.</span></span> <span data-ttu-id="f2857-156">使用 `Set-CsHybridApplicationEndpoint` 命令将电话号码（带有-LineURI 选项）分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="f2857-156">Use the `Set-CsHybridApplicationEndpoint` command to a assign a phone number (with the -LineURI option) to the resource account.</span></span>

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    <span data-ttu-id="f2857-157">有关此命令的详细信息，请参阅[CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="f2857-157">See [Set-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

    <span data-ttu-id="f2857-158">若要向资源帐户分配直接路由或混合号码，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f2857-158">To assign a Direct Routing or hybrid number to  a resource account, use the following cmdlet:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   <span data-ttu-id="f2857-159">如果资源帐户将分配给顶级自动助理或呼叫队列，则该帐户将需要已分配的电话号码。</span><span class="sxs-lookup"><span data-stu-id="f2857-159">The resource account will need an assigned phone number if it will be assigned to a top level auto attendant or call queue.</span></span> <span data-ttu-id="f2857-160">无法将用户（订阅者）电话号码分配给资源帐户，只能使用服务收费或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="f2857-160">User (subscriber) phone numbers can't be assigned to a resource account, only service toll or toll-free phone numbers can be used.</span></span>

     <span data-ttu-id="f2857-161">您可以为您的资源帐户分配直接路由或混合号码。</span><span class="sxs-lookup"><span data-stu-id="f2857-161">You can assign a Direct Routing or hybrid number to your resource account.</span></span> <span data-ttu-id="f2857-162">有关详细信息，请参阅[规划直接路由](/MicrosoftTeams/direct-routing-plan)和[规划云自动助理](plan-cloud-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="f2857-162">For details, see [Plan Direct Routing](/MicrosoftTeams/direct-routing-plan) and [Plan Cloud auto attendants](plan-cloud-auto-attendant.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="f2857-163">仅为 Microsoft 团队用户和代理支持分配给自动助理和呼叫队列的资源帐户的直接路由服务号码。</span><span class="sxs-lookup"><span data-stu-id="f2857-163">Direct Routing service numbers assigned to resource accounts for auto attendant and call queues are supported for Microsoft Teams users and agents only.</span></span>

7. <span data-ttu-id="f2857-164">创建电话系统自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="f2857-164">Create the Phone System auto attendant or call queue.</span></span> <span data-ttu-id="f2857-165">请查看下列内容之一：</span><span class="sxs-lookup"><span data-stu-id="f2857-165">See one of the following:</span></span>

   - [<span data-ttu-id="f2857-166">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="f2857-166">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="f2857-167">创建云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="f2857-167">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. <span data-ttu-id="f2857-168">将资源帐户与以前选择的电话系统自动助理或呼叫队列关联。</span><span class="sxs-lookup"><span data-stu-id="f2857-168">Associate the resource account with the Phone System auto attendant or call queue you chose previously.</span></span>

<span data-ttu-id="f2857-169">小型企业版实施的示例在小型企业版中提供示例[-设置自动助理](/microsoftteams/tutorial-org-aa)和[小型企业示例-设置呼叫队列](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq)。</span><span class="sxs-lookup"><span data-stu-id="f2857-169">An example of a small business implementation is available in  [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) and [Small business example - Set up a call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq).</span></span>

## <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="f2857-170">创建不带电话号码的资源帐户</span><span class="sxs-lookup"><span data-stu-id="f2857-170">Create a resource account without a phone number</span></span>

<span data-ttu-id="f2857-171">本节讨论如何创建驻留在本地的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="f2857-171">This section discusses creating a resource account that is homed on premises.</span></span> <span data-ttu-id="f2857-172">在[Microsoft 团队中的 "管理资源帐户" 中](/MicrosoftTeams/manage-resource-accounts)讨论了如何创建驻留在联机状态的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="f2857-172">Creating a resource account that is homed online is discussed at [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).</span></span>

<span data-ttu-id="f2857-173">无论是创建全新的电话系统自动助理或呼叫队列结构，还是在 Exchange UM 中最初创建的结构重建，都必须执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="f2857-173">These steps are necessary whether you are creating a brand new Phone System auto attendant or call queue structure, or rebuilding structure originally created in Exchange UM.</span></span>

<span data-ttu-id="f2857-174">登录到 Skype for Business 前端服务器并运行以下 PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f2857-174">Log in to the Skype for Business front end server and run the following PowerShell cmdlets:</span></span>

1. <span data-ttu-id="f2857-175">通过对 `New-CsHybridApplicationEndpoint` 每个电话系统自动助理或呼叫队列运行 cmdlet 来创建本地资源帐户，并为每个电话系统自动助理或呼叫队列分配一个名称、sip 地址等。</span><span class="sxs-lookup"><span data-stu-id="f2857-175">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System auto attendant or call queue, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="f2857-176">有关此命令的更多详细信息，请参阅[CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="f2857-176">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

2. <span data-ttu-id="f2857-177">Optional创建资源帐户后，您可以等待 AD 在联机和内部部署之间同步，或者强制进行同步并继续进行电话系统自动助理或呼叫队列的联机配置。</span><span class="sxs-lookup"><span data-stu-id="f2857-177">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premises, or force a sync and proceed to online configuration of Phone System auto attendant or call queues.</span></span> <span data-ttu-id="f2857-178">若要强制进行同步，请在运行 AAD 连接的计算机上运行以下命令（如果尚未执行此操作，则需要加载 `import-module adsync` 才能运行该命令）：</span><span class="sxs-lookup"><span data-stu-id="f2857-178">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="f2857-179">有关此命令的更多详细信息，请参阅[ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 。</span><span class="sxs-lookup"><span data-stu-id="f2857-179">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

3. <span data-ttu-id="f2857-180">创建电话系统自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="f2857-180">Create the Phone System auto attendant or call queue.</span></span> <span data-ttu-id="f2857-181">请查看下列内容之一：</span><span class="sxs-lookup"><span data-stu-id="f2857-181">See one of the following:</span></span>
   - [<span data-ttu-id="f2857-182">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="f2857-182">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="f2857-183">创建云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="f2857-183">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. <span data-ttu-id="f2857-184">关联以前选择的资源帐户和电话系统自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="f2857-184">Associate the resource account and the Phone System auto attendant or call queue you chose previously.</span></span>

<span data-ttu-id="f2857-185">小型企业版实施的示例在小型企业版中提供示例[-设置自动助理](/microsoftteams/tutorial-org-aa)和[小型企业示例-设置呼叫队列](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq)。</span><span class="sxs-lookup"><span data-stu-id="f2857-185">An example of a small business implementation is available in  [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) and [Small business example - Set up a call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq).</span></span>

## <a name="test-the-implementation"></a><span data-ttu-id="f2857-186">测试实现</span><span class="sxs-lookup"><span data-stu-id="f2857-186">Test the implementation</span></span>

<span data-ttu-id="f2857-187">测试实现的最佳方式是呼叫为电话系统自动助理或呼叫队列配置的号码，并连接到其中一个代理或菜单。</span><span class="sxs-lookup"><span data-stu-id="f2857-187">The best way to test the implementation is to call the number configured for a Phone System auto attendant or call queue and connect to one of the agents or menus.</span></span> <span data-ttu-id="f2857-188">您还可以通过使用管理中心操作窗格中的 "**测试" 按钮**来快速发出测试呼叫。</span><span class="sxs-lookup"><span data-stu-id="f2857-188">You can also quickly place a test call by using the **Test button** in the admin center Action pane.</span></span> <span data-ttu-id="f2857-189">如果要对电话系统自动助理或呼叫队列进行更改，请选择它，然后在操作窗格中单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="f2857-189">If you want to make changes to a Phone System auto attendant or call queue, select it and then in the Action pane click **Edit**.</span></span> 

> [!TIP]
> <span data-ttu-id="f2857-190">如果您的资源帐户在分配给呼叫队列或自动助理时遇到困难，请参阅 Microsoft 团队博客中的[已知问题 "Microsoft 团队](/MicrosoftTeams/Known-issues#phone-system)和[如何修复我的混合应用程序实例](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)" 部分。</span><span class="sxs-lookup"><span data-stu-id="f2857-190">If your resource account has difficulties with being assigned to a call queue or auto attendant, see [Known issues for Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system) and the [How to fix my hybrid application instances](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) section in the Microsoft Teams Blog.</span></span>

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a><span data-ttu-id="f2857-191">将 Exchange UM 自动助理或呼叫队列移动到电话系统</span><span class="sxs-lookup"><span data-stu-id="f2857-191">Moving an Exchange UM auto attendant or call queue to Phone System</span></span>

<span data-ttu-id="f2857-192">从 Exchange UM 迁移到电话系统将需要重新创建呼叫队列和自动助理结构，而不支持直接从一个迁移到另一个。</span><span class="sxs-lookup"><span data-stu-id="f2857-192">Migration from Exchange UM to Phone System will require recreating the call queue and auto attendant structure, directly migrating from one to the other is not supported.</span></span> <span data-ttu-id="f2857-193">若要重新实现一组呼叫队列和自动助理，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f2857-193">To re-implement a set of call queues and auto attendants:</span></span>

1. <span data-ttu-id="f2857-194">在以管理员身份登录时，通过在 Exchange 2013 或2016系统上运行以下命令来获取所有 Exchange UM 自动助理和呼叫队列的列表：</span><span class="sxs-lookup"><span data-stu-id="f2857-194">Get a list of all Exchange UM auto attendants and call queues by running the following command on the Exchange 2013 or 2016 system while logged in as admin:</span></span>

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. <span data-ttu-id="f2857-195">对于每个列出的 Exchange UM 呼叫队列或自动助理，请注意其在结构中的位置、设置，以及获取关联的声音或文本到语音转换文件的副本（输出中的 guid 将是存储文件的文件夹的名称）。</span><span class="sxs-lookup"><span data-stu-id="f2857-195">For each listed Exchange UM call queue or auto attendant, note its place in the structure, settings, and get copies of associated sound or text-to-speech files (the guid in the output will be the name of a folder where the files are stored).</span></span> <span data-ttu-id="f2857-196">可以通过运行以下命令获取这些详细信息：</span><span class="sxs-lookup"><span data-stu-id="f2857-196">You can get these details by running the command:</span></span>

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    <span data-ttu-id="f2857-197">有关此命令的详细信息，请参阅[get-umautoattendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) 。</span><span class="sxs-lookup"><span data-stu-id="f2857-197">See [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) for more details on this command.</span></span> <span data-ttu-id="f2857-198">您可能需要捕获的选项的完整列表是在[get-umautoattendant 成员](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx)处，但要注意的最重要的选项是：</span><span class="sxs-lookup"><span data-stu-id="f2857-198">A complete list of options you might need to capture is at [UMAutoAttendant members](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) but the most important options to note down are:</span></span>

    - <span data-ttu-id="f2857-199">营业时间</span><span class="sxs-lookup"><span data-stu-id="f2857-199">Business hours</span></span>
    - <span data-ttu-id="f2857-200">非工作时间</span><span class="sxs-lookup"><span data-stu-id="f2857-200">Non-business hours</span></span>
    - <span data-ttu-id="f2857-201">语言</span><span class="sxs-lookup"><span data-stu-id="f2857-201">Language</span></span>
    - <span data-ttu-id="f2857-202">假日日程安排</span><span class="sxs-lookup"><span data-stu-id="f2857-202">Holiday schedule</span></span>

3. <span data-ttu-id="f2857-203">按照前面所述，创建新的本地终结点。</span><span class="sxs-lookup"><span data-stu-id="f2857-203">Create new on-premises endpoints as previously described.</span></span>
   <span data-ttu-id="f2857-204">为顶级自动助理分配一个用于测试目的的临时编号。</span><span class="sxs-lookup"><span data-stu-id="f2857-204">Assign the top-level auto attendant a temporary number for testing purposes.</span></span>

4. <span data-ttu-id="f2857-205">按照前面所述，配置使用终结点的电话系统自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="f2857-205">Configure a Phone System auto attendant or call queue that uses the endpoints as previously described.</span></span>

   <span data-ttu-id="f2857-206">您可能会发现，在教程中使用标题为 "小型企业版" 的练习，[设置自动助理](/microsoftteams/tutorial-org-aa)，以创建旧 Exchange UM 系统中的层次结构的逻辑地图。</span><span class="sxs-lookup"><span data-stu-id="f2857-206">You may find it useful to use the exercises in the tutorial titled [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) to create a logical map of the hierarchies in your old Exchange UM system.</span></span>
5. <span data-ttu-id="f2857-207">测试电话系统自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="f2857-207">Test the Phone System auto attendant or call queue.</span></span>
6. <span data-ttu-id="f2857-208">将链接到 Exchange UM 呼叫队列或自动助理的电话号码重新分配给相应的电话系统自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="f2857-208">Reassign the phone number linked to the Exchange UM call queue or auto attendant to the corresponding Phone System auto attendant or call queue.</span></span>  

   <span data-ttu-id="f2857-209">在这种情况下，如果您已经迁移了 UM 语音邮件，则应在迁移到 Exchange Server 2019 的位置。</span><span class="sxs-lookup"><span data-stu-id="f2857-209">At this point, if you have already migrated UM Voicemail, you should be in a position to migrate to Exchange Server 2019.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2857-210">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2857-210">See Also</span></span>

[<span data-ttu-id="f2857-211">创建云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="f2857-211">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)

[<span data-ttu-id="f2857-212">什么是云自动助理？</span><span class="sxs-lookup"><span data-stu-id="f2857-212">What are Cloud auto attendants?</span></span>](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[<span data-ttu-id="f2857-213">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="f2857-213">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[<span data-ttu-id="f2857-214">规划云自动助理</span><span class="sxs-lookup"><span data-stu-id="f2857-214">Plan Cloud auto attendants</span></span>](plan-cloud-auto-attendant.md)

[<span data-ttu-id="f2857-215">规划云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="f2857-215">Plan Cloud call queues</span></span>](plan-call-queue.md)

[<span data-ttu-id="f2857-216">为本地用户规划云语音邮件服务</span><span class="sxs-lookup"><span data-stu-id="f2857-216">Plan Cloud Voicemail service for on-premises users</span></span>](plan-cloud-voicemail.md)

[<span data-ttu-id="f2857-217">新 CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="f2857-217">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="f2857-218">新 CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="f2857-218">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

<span data-ttu-id="f2857-219">[在 Microsoft 团队](/MicrosoftTeams/manage-resource-accounts)  -  \( 中管理资源帐户创建驻留在网上的资源帐户\)</span><span class="sxs-lookup"><span data-stu-id="f2857-219">[Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \(to create resource accounts homed online\)</span></span>
