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
ms.openlocfilehash: f3a9166f6e1bb9659a7fb43b9e7c35dba673f176
ms.sourcegitcommit: 32023931b607542cffadef74383e3ecd47db4ab6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868681"
---
# <a name="configure-resource-accounts"></a><span data-ttu-id="f6b4f-103">配置资源帐户</span><span class="sxs-lookup"><span data-stu-id="f6b4f-103">Configure resource accounts</span></span>

<span data-ttu-id="f6b4f-104">Skype for Business Server 2019 混合实施仅使用电话系统提供的用于统一消息的云服务，不与 Exchange Online 集成。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-104">Skype for Business Server 2019 hybrid implementations only use Cloud services provided by Phone System for unified messaging and do not integrate with Exchange Online.</span></span> <span data-ttu-id="f6b4f-105">在 Skype for Business Server 2019 中，你现在可以使用此处介绍的云呼叫队列和自动助理，这些 [是 Microsoft 365 或 Office 365 中的电话系统获取的内容](/MicrosoftTeams/here-s-what-you-get-with-phone-system)。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-105">In Skype for Business Server 2019 you are now able to use the Cloud call queues and auto attendants described in [Here's what you get with Phone System in Microsoft 365 or Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).</span></span>

<span data-ttu-id="f6b4f-106">若要将电话系统自动助理或呼叫队列与 Skype for Business Server 2019 一起使用，您需要创建充当应用程序终结点且可分配电话号码的资源帐户，然后使用联机团队管理中心配置呼叫队列或自动助理。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-106">To use an Phone System auto attendant or call queue with Skype for Business Server 2019, you will need to create resource accounts that act as application endpoints and can be assigned phone numbers, then use the online Teams admin center to configure the call queue or auto attendant.</span></span> <span data-ttu-id="f6b4f-107">此资源帐户可以托管联机 (请参阅 [在 Microsoft 团队中管理资源帐户](/MicrosoftTeams/manage-resource-accounts) ，以创建托管联机) 或本地的资源帐户，如本文中所述。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-107">This resource account can be homed online (see [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) to create resource accounts homed online) or on premises as described in this article.</span></span> <span data-ttu-id="f6b4f-108">通常，您将具有多个电话系统自动助理或呼叫队列节点，每个节点都映射到可联机或在 Skype for business Server 2019 中的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-108">Typically you will have multiple Phone System auto attendant or call queue nodes, each of which is mapped to a resource accounts, which can be homed online or in Skype for Business Server 2019.</span></span>

<span data-ttu-id="f6b4f-109">如果你有一个现有的 Exchange UM 自动助理和呼叫队列系统，则在切换到 Exchange Server 2019 或 Exchange online 之前，你需要手动记录详细信息，然后使用团队管理中心实施全新的系统。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-109">If you have an existing Exchange UM auto attendant and call queue system, before you switch to Exchange Server 2019 or Exchange online you will need to manually record the details as described below and then implement a completely new system using the Teams admin center.</span></span>

## <a name="overview"></a><span data-ttu-id="f6b4f-110">概述</span><span class="sxs-lookup"><span data-stu-id="f6b4f-110">Overview</span></span>

<span data-ttu-id="f6b4f-111">如果电话系统自动助理或呼叫队列将需要服务号码，则可以按以下顺序满足各种相关性：</span><span class="sxs-lookup"><span data-stu-id="f6b4f-111">If your Phone System auto attendant or call queue will need a service number, the various dependencies can be met in the following sequence:</span></span>

1. <span data-ttu-id="f6b4f-112">获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-112">Obtain a service number.</span></span>
2. <span data-ttu-id="f6b4f-113">获取免费的电话系统- [虚拟用户许可证](/MicrosoftTeams/teams-add-on-licensing/virtual-user) 或付费电话系统许可证以与资源帐户一起使用。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-113">Obtain a free Phone System - [Virtual User license](/MicrosoftTeams/teams-add-on-licensing/virtual-user) or a paid Phone System license to use with the resource account.</span></span>
3. <span data-ttu-id="f6b4f-114">创建资源帐户。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-114">Create the resource account.</span></span> <span data-ttu-id="f6b4f-115">自动助理或呼叫队列必须具有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-115">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="f6b4f-116">在联机和本地之间等待 active directory 同步。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-116">Wait for an active directory sync between online and on premises.</span></span>
5. <span data-ttu-id="f6b4f-117">将电话系统许可证分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-117">Assign the Phone System license to the resource account.</span></span>
6. <span data-ttu-id="f6b4f-118">向资源帐户分配服务号码。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-118">Assign a service number to the resource account.</span></span>
7. <span data-ttu-id="f6b4f-119">创建电话系统呼叫队列或自动助理。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-119">Create a Phone System call queue or auto attendant.</span></span>
8. <span data-ttu-id="f6b4f-120">将资源帐户与自动助理或呼叫队列关联： (CsApplicationInstanceAssociation) 。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-120">Associate the resource account with an auto attendant or call queue: (New-CsApplicationInstanceAssociation).</span></span>

<span data-ttu-id="f6b4f-121">如果自动助理或呼叫队列嵌套在顶级自动助理下，则关联的资源帐户只需要一个电话号码，如果您希望将多个点输入到自动助理和呼叫队列的结构中。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-121">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="f6b4f-122">若要将呼叫重定向到组织中已联机的人员，他们必须具有 **电话系统** 许可证并启用企业语音或拥有 Microsoft 365 或 Office 365 通话套餐。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-122">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Microsoft 365 or Office 365 Calling Plans.</span></span> <span data-ttu-id="f6b4f-123">请参阅 [分配 Microsoft 团队许可证](/MicrosoftTeams/assign-teams-licenses)。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-123">See [Assign Microsoft Teams licenses](/MicrosoftTeams/assign-teams-licenses).</span></span> <span data-ttu-id="f6b4f-124">若要为企业语音启用它们，可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-124">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="f6b4f-125">例如，运行：  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="f6b4f-125">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

<span data-ttu-id="f6b4f-126">如果要创建的电话系统自动助理或呼叫队列将嵌套，并且不需要电话号码，则该过程为：</span><span class="sxs-lookup"><span data-stu-id="f6b4f-126">If the Phone system auto attendant or call queue you're creating will be nested and will not need a phone number, the process is:</span></span>

1. <span data-ttu-id="f6b4f-127">创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="f6b4f-127">Create the resource account</span></span>  
2. <span data-ttu-id="f6b4f-128">在联机和本地之间等待 active directory 同步</span><span class="sxs-lookup"><span data-stu-id="f6b4f-128">Wait for an active directory sync between online and on premises</span></span>
3. <span data-ttu-id="f6b4f-129">创建电话系统自动助理或呼叫队列</span><span class="sxs-lookup"><span data-stu-id="f6b4f-129">Create a Phone System auto attendant or call queue</span></span>
4. <span data-ttu-id="f6b4f-130">将资源帐户与电话系统自动助理或呼叫队列关联</span><span class="sxs-lookup"><span data-stu-id="f6b4f-130">Associate the resource account with a Phone System auto attendant or call queue</span></span>

## <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="f6b4f-131">创建具有电话号码的资源帐户</span><span class="sxs-lookup"><span data-stu-id="f6b4f-131">Create a resource account with a phone number</span></span>

<span data-ttu-id="f6b4f-132">若要创建使用电话号码的资源帐户，需要按以下顺序执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="f6b4f-132">Creating a resource account that uses a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="f6b4f-133">端口或获取收费或免费服务号码。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-133">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="f6b4f-134">该号码不能分配给任何其他语音服务或资源帐户。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-134">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="f6b4f-135">在向资源帐户分配电话号码之前，需要获取或移植现有收费或免费服务号码。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-135">Before you assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="f6b4f-136">获取收费或免费服务电话号码后，它们将显示在**Microsoft 团队管理中心**的  >  **语音**  >  **电话号码**中，并且列出的**号码类型**将列为 "**服务-免费**"。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-136">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="f6b4f-137">若要获取服务号码，请参阅 [获取服务电话号码](/MicrosoftTeams/getting-service-phone-numbers) ; 如果要转移现有服务号码，请参阅 [将电话号码转移给团队](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams)。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-137">To get your service numbers, see [Getting service phone numbers](/MicrosoftTeams/getting-service-phone-numbers) or if you want to transfer an existing service number, see [Transfer phone numbers to Teams](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams).</span></span>

   <span data-ttu-id="f6b4f-138">如果你在美国之外，则无法使用 Microsoft 团队管理中心获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-138">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="f6b4f-139">转到 " [管理你的组织的电话号码](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) "，以了解如何从美国以外的地区执行此操作。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-139">Go to [Manage phone numbers for your organization](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.</span></span>

2. <span data-ttu-id="f6b4f-140">购买电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-140">Buy a Phone System license.</span></span> <span data-ttu-id="f6b4f-141">请参阅：</span><span class="sxs-lookup"><span data-stu-id="f6b4f-141">See:</span></span>  
   - [<span data-ttu-id="f6b4f-142">电话系统–虚拟用户许可证</span><span class="sxs-lookup"><span data-stu-id="f6b4f-142">Phone System–Virtual User license</span></span>](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [<span data-ttu-id="f6b4f-143">Office 365 企业版（E1 和 E3）</span><span class="sxs-lookup"><span data-stu-id="f6b4f-143">Office 365 Enterprise E1 and E3</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [<span data-ttu-id="f6b4f-144">Office 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="f6b4f-144">Office 365 Enterprise E5</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [<span data-ttu-id="f6b4f-145">Office 365 企业版 E5 商业版软件</span><span class="sxs-lookup"><span data-stu-id="f6b4f-145">Office 365 Enterprise E5 Business Software</span></span>](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. <span data-ttu-id="f6b4f-146">通过对 `New-CsHybridApplicationEndpoint` 每个电话系统自动助理或呼叫队列运行 cmdlet 来创建本地资源帐户，并为每个电话系统自动助理或呼叫队列分配一个名称、sip 地址等。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-146">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System auto attendant or call queue, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="f6b4f-147">有关此命令的更多详细信息，请参阅 [CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-147">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

4. <span data-ttu-id="f6b4f-148"> (可选) 创建资源帐户后，您可以等待 AD 在联机和内部部署之间同步，或者强制进行同步并继续进行电话系统自动助理或呼叫队列的联机配置。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-148">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premises, or force a sync and proceed to online configuration of Phone System auto attendant or call queues.</span></span> <span data-ttu-id="f6b4f-149">若要强制进行同步，请在运行 AAD Connect (的计算机上运行以下命令。如果尚未执行此操作，则需要进行加载， `import-module adsync` 以运行命令) ：</span><span class="sxs-lookup"><span data-stu-id="f6b4f-149">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="f6b4f-150">有关此命令的更多详细信息，请参阅 [ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-150">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>
    
    <span data-ttu-id="f6b4f-151">注意-此时，帐户可能已同步，但设置可能不完整。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-151">Note-at this point, the account may have synced, but provisioning may not be complete.</span></span>  <span data-ttu-id="f6b4f-152">检查 [CsOnlineApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/get-csonlineapplicationendpoint)的输出。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-152">Check the output of [Get-CsOnlineApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/get-csonlineapplicationendpoint).</span></span>  <span data-ttu-id="f6b4f-153">如果同步的终结点尚未完成预配，则它将不会显示在此处。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-153">If the synced endpoint has not completed provisioning yet, then it will not appear here.</span></span>  <span data-ttu-id="f6b4f-154">您可以在 " [团队设置状态](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning)" 下的 M365 门户中检查预配请求的状态。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-154">You can check the status of the provisioning requests in the M365 portal under [Teams Setup Status](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning).</span></span>  <span data-ttu-id="f6b4f-155">此设置阶段最长可能需要24小时。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-155">This provisioning phase can take up to 24 hours.</span></span>

5. <span data-ttu-id="f6b4f-156">将电话系统-虚拟用户或电话系统许可证分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-156">Assign the Phone System - Virtual User or Phone System license to the resource account.</span></span> <span data-ttu-id="f6b4f-157">请参阅 [分配 Microsoft 团队附加许可证](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) 和向 [用户分配许可证](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-157">See [Assign Microsoft Teams add-on licenses](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) and [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

   <span data-ttu-id="f6b4f-158">如果要将电话号码分配给资源帐户，现在可以使用免费电话系统-虚拟用户许可证。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-158">If you are assigning a phone number to a resource account you can now use the cost-free Phone System - Virtual User license.</span></span> <span data-ttu-id="f6b4f-159">这样可以在组织级别为电话号码提供电话系统功能，并允许您创建自动助理和呼叫队列功能。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-159">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>


6. <span data-ttu-id="f6b4f-160">向资源帐户分配服务号码。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-160">Assign the service number to the resource account.</span></span> <span data-ttu-id="f6b4f-161">使用 `Set-CsHybridApplicationEndpoint` 命令将电话号码 (使用-LineURI 选项) 分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-161">Use the `Set-CsHybridApplicationEndpoint` command to a assign a phone number (with the -LineURI option) to the resource account.</span></span>

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    <span data-ttu-id="f6b4f-162">有关此命令的详细信息，请参阅 [CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-162">See [Set-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

    <span data-ttu-id="f6b4f-163">若要向资源帐户分配直接路由或混合号码，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f6b4f-163">To assign a Direct Routing or hybrid number to  a resource account, use the following cmdlet:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   <span data-ttu-id="f6b4f-164">如果资源帐户将分配给顶级自动助理或呼叫队列，则该帐户将需要已分配的电话号码。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-164">The resource account will need an assigned phone number if it will be assigned to a top level auto attendant or call queue.</span></span> <span data-ttu-id="f6b4f-165">用户 (订阅者) 不能将电话号码分配给资源帐户，只能使用服务收费或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-165">User (subscriber) phone numbers can't be assigned to a resource account, only service toll or toll-free phone numbers can be used.</span></span>

     <span data-ttu-id="f6b4f-166">您可以为您的资源帐户分配直接路由或混合号码。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-166">You can assign a Direct Routing or hybrid number to your resource account.</span></span> <span data-ttu-id="f6b4f-167">有关详细信息，请参阅 [规划直接路由](/MicrosoftTeams/direct-routing-plan) 和 [规划云自动助理](plan-cloud-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-167">For details, see [Plan Direct Routing](/MicrosoftTeams/direct-routing-plan) and [Plan Cloud auto attendants](plan-cloud-auto-attendant.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="f6b4f-168">仅为 Microsoft 团队用户和代理支持分配给自动助理和呼叫队列的资源帐户的直接路由服务号码。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-168">Direct Routing service numbers assigned to resource accounts for auto attendant and call queues are supported for Microsoft Teams users and agents only.</span></span>

7. <span data-ttu-id="f6b4f-169">创建电话系统自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-169">Create the Phone System auto attendant or call queue.</span></span> <span data-ttu-id="f6b4f-170">请查看下列内容之一：</span><span class="sxs-lookup"><span data-stu-id="f6b4f-170">See one of the following:</span></span>

   - [<span data-ttu-id="f6b4f-171">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="f6b4f-171">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="f6b4f-172">创建云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="f6b4f-172">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. <span data-ttu-id="f6b4f-173">将资源帐户与以前选择的电话系统自动助理或呼叫队列关联。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-173">Associate the resource account with the Phone System auto attendant or call queue you chose previously.</span></span>

<span data-ttu-id="f6b4f-174">小型企业版实施的示例在小型企业版中提供示例  [-设置自动助理](/microsoftteams/tutorial-org-aa) 和 [小型企业示例-设置呼叫队列](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq)。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-174">An example of a small business implementation is available in  [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) and [Small business example - Set up a call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq).</span></span>

## <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="f6b4f-175">创建不带电话号码的资源帐户</span><span class="sxs-lookup"><span data-stu-id="f6b4f-175">Create a resource account without a phone number</span></span>

<span data-ttu-id="f6b4f-176">本节讨论如何创建驻留在本地的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-176">This section discusses creating a resource account that is homed on premises.</span></span> <span data-ttu-id="f6b4f-177">在 [Microsoft 团队中的 "管理资源帐户" 中](/MicrosoftTeams/manage-resource-accounts)讨论了如何创建驻留在联机状态的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-177">Creating a resource account that is homed online is discussed at [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).</span></span>

<span data-ttu-id="f6b4f-178">无论是创建全新的电话系统自动助理或呼叫队列结构，还是在 Exchange UM 中最初创建的结构重建，都必须执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-178">These steps are necessary whether you are creating a brand new Phone System auto attendant or call queue structure, or rebuilding structure originally created in Exchange UM.</span></span>

<span data-ttu-id="f6b4f-179">登录到 Skype for Business 前端服务器并运行以下 PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f6b4f-179">Log in to the Skype for Business front end server and run the following PowerShell cmdlets:</span></span>

1. <span data-ttu-id="f6b4f-180">通过对 `New-CsHybridApplicationEndpoint` 每个电话系统自动助理或呼叫队列运行 cmdlet 来创建本地资源帐户，并为每个电话系统自动助理或呼叫队列分配一个名称、sip 地址等。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-180">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System auto attendant or call queue, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="f6b4f-181">有关此命令的更多详细信息，请参阅 [CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-181">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

2. <span data-ttu-id="f6b4f-182"> (可选) 创建资源帐户后，您可以等待 AD 在联机和内部部署之间同步，或者强制进行同步并继续进行电话系统自动助理或呼叫队列的联机配置。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-182">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premises, or force a sync and proceed to online configuration of Phone System auto attendant or call queues.</span></span> <span data-ttu-id="f6b4f-183">若要强制进行同步，请在运行 AAD Connect (的计算机上运行以下命令。如果尚未执行此操作，则需要进行加载， `import-module adsync` 以运行命令) ：</span><span class="sxs-lookup"><span data-stu-id="f6b4f-183">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="f6b4f-184">有关此命令的更多详细信息，请参阅 [ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-184">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

3. <span data-ttu-id="f6b4f-185">创建电话系统自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-185">Create the Phone System auto attendant or call queue.</span></span> <span data-ttu-id="f6b4f-186">请查看下列内容之一：</span><span class="sxs-lookup"><span data-stu-id="f6b4f-186">See one of the following:</span></span>
   - [<span data-ttu-id="f6b4f-187">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="f6b4f-187">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="f6b4f-188">创建云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="f6b4f-188">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. <span data-ttu-id="f6b4f-189">关联以前选择的资源帐户和电话系统自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-189">Associate the resource account and the Phone System auto attendant or call queue you chose previously.</span></span>

<span data-ttu-id="f6b4f-190">小型企业版实施的示例在小型企业版中提供示例  [-设置自动助理](/microsoftteams/tutorial-org-aa) 和 [小型企业示例-设置呼叫队列](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq)。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-190">An example of a small business implementation is available in  [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) and [Small business example - Set up a call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq).</span></span>

## <a name="test-the-implementation"></a><span data-ttu-id="f6b4f-191">测试实现</span><span class="sxs-lookup"><span data-stu-id="f6b4f-191">Test the implementation</span></span>

<span data-ttu-id="f6b4f-192">测试实现的最佳方式是呼叫为电话系统自动助理或呼叫队列配置的号码，并连接到其中一个代理或菜单。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-192">The best way to test the implementation is to call the number configured for a Phone System auto attendant or call queue and connect to one of the agents or menus.</span></span> <span data-ttu-id="f6b4f-193">您还可以通过使用管理中心操作窗格中的 " **测试" 按钮** 来快速发出测试呼叫。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-193">You can also quickly place a test call by using the **Test button** in the admin center Action pane.</span></span> <span data-ttu-id="f6b4f-194">如果要对电话系统自动助理或呼叫队列进行更改，请选择它，然后在操作窗格中单击 " **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-194">If you want to make changes to a Phone System auto attendant or call queue, select it and then in the Action pane click **Edit**.</span></span> 

> [!TIP]
> <span data-ttu-id="f6b4f-195">如果您的资源帐户在分配给呼叫队列或自动助理时遇到困难，请参阅 Microsoft 团队博客中的 [已知问题 "Microsoft 团队](/MicrosoftTeams/Known-issues#phone-system) 和 [如何修复我的混合应用程序实例](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) " 部分。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-195">If your resource account has difficulties with being assigned to a call queue or auto attendant, see [Known issues for Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system) and the [How to fix my hybrid application instances](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) section in the Microsoft Teams Blog.</span></span>

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a><span data-ttu-id="f6b4f-196">将 Exchange UM 自动助理或呼叫队列移动到电话系统</span><span class="sxs-lookup"><span data-stu-id="f6b4f-196">Moving an Exchange UM auto attendant or call queue to Phone System</span></span>

<span data-ttu-id="f6b4f-197">从 Exchange UM 迁移到电话系统将需要重新创建呼叫队列和自动助理结构，而不支持直接从一个迁移到另一个。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-197">Migration from Exchange UM to Phone System will require recreating the call queue and auto attendant structure, directly migrating from one to the other is not supported.</span></span> <span data-ttu-id="f6b4f-198">若要重新实现一组呼叫队列和自动助理，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f6b4f-198">To re-implement a set of call queues and auto attendants:</span></span>

1. <span data-ttu-id="f6b4f-199">在以管理员身份登录时，通过在 Exchange 2013 或2016系统上运行以下命令来获取所有 Exchange UM 自动助理和呼叫队列的列表：</span><span class="sxs-lookup"><span data-stu-id="f6b4f-199">Get a list of all Exchange UM auto attendants and call queues by running the following command on the Exchange 2013 or 2016 system while logged in as admin:</span></span>

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. <span data-ttu-id="f6b4f-200">对于每个列出的 Exchange UM 呼叫队列或自动助理，请注意其在结构中的位置、设置，以及获取关联的声音或文本到语音转换文件的副本 (输出中的 guid 将是存储文件的文件夹的名称) 。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-200">For each listed Exchange UM call queue or auto attendant, note its place in the structure, settings, and get copies of associated sound or text-to-speech files (the guid in the output will be the name of a folder where the files are stored).</span></span> <span data-ttu-id="f6b4f-201">可以通过运行以下命令获取这些详细信息：</span><span class="sxs-lookup"><span data-stu-id="f6b4f-201">You can get these details by running the command:</span></span>

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    <span data-ttu-id="f6b4f-202">有关此命令的详细信息，请参阅 [get-umautoattendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) 。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-202">See [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) for more details on this command.</span></span> <span data-ttu-id="f6b4f-203">您可能需要捕获的选项的完整列表是在 [get-umautoattendant 成员](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) 处，但要注意的最重要的选项是：</span><span class="sxs-lookup"><span data-stu-id="f6b4f-203">A complete list of options you might need to capture is at [UMAutoAttendant members](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) but the most important options to note down are:</span></span>

    - <span data-ttu-id="f6b4f-204">营业时间</span><span class="sxs-lookup"><span data-stu-id="f6b4f-204">Business hours</span></span>
    - <span data-ttu-id="f6b4f-205">非工作时间</span><span class="sxs-lookup"><span data-stu-id="f6b4f-205">Non-business hours</span></span>
    - <span data-ttu-id="f6b4f-206">语言</span><span class="sxs-lookup"><span data-stu-id="f6b4f-206">Language</span></span>
    - <span data-ttu-id="f6b4f-207">假日日程安排</span><span class="sxs-lookup"><span data-stu-id="f6b4f-207">Holiday schedule</span></span>

3. <span data-ttu-id="f6b4f-208">按照前面所述，创建新的本地终结点。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-208">Create new on-premises endpoints as previously described.</span></span>
   <span data-ttu-id="f6b4f-209">为顶级自动助理分配一个用于测试目的的临时编号。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-209">Assign the top-level auto attendant a temporary number for testing purposes.</span></span>

4. <span data-ttu-id="f6b4f-210">按照前面所述，配置使用终结点的电话系统自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-210">Configure a Phone System auto attendant or call queue that uses the endpoints as previously described.</span></span>

   <span data-ttu-id="f6b4f-211">您可能会发现，在教程中使用标题为 "小型企业版" 的练习， [设置自动助理](/microsoftteams/tutorial-org-aa) ，以创建旧 Exchange UM 系统中的层次结构的逻辑地图。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-211">You may find it useful to use the exercises in the tutorial titled [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) to create a logical map of the hierarchies in your old Exchange UM system.</span></span>
5. <span data-ttu-id="f6b4f-212">测试电话系统自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-212">Test the Phone System auto attendant or call queue.</span></span>
6. <span data-ttu-id="f6b4f-213">将链接到 Exchange UM 呼叫队列或自动助理的电话号码重新分配给相应的电话系统自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-213">Reassign the phone number linked to the Exchange UM call queue or auto attendant to the corresponding Phone System auto attendant or call queue.</span></span>  

   <span data-ttu-id="f6b4f-214">在这种情况下，如果您已经迁移了 UM 语音邮件，则应在迁移到 Exchange Server 2019 的位置。</span><span class="sxs-lookup"><span data-stu-id="f6b4f-214">At this point, if you have already migrated UM Voicemail, you should be in a position to migrate to Exchange Server 2019.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6b4f-215">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6b4f-215">See Also</span></span>

[<span data-ttu-id="f6b4f-216">创建云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="f6b4f-216">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)

[<span data-ttu-id="f6b4f-217">什么是云自动助理？</span><span class="sxs-lookup"><span data-stu-id="f6b4f-217">What are Cloud auto attendants?</span></span>](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[<span data-ttu-id="f6b4f-218">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="f6b4f-218">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[<span data-ttu-id="f6b4f-219">规划云自动助理</span><span class="sxs-lookup"><span data-stu-id="f6b4f-219">Plan Cloud auto attendants</span></span>](plan-cloud-auto-attendant.md)

[<span data-ttu-id="f6b4f-220">规划云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="f6b4f-220">Plan Cloud call queues</span></span>](plan-call-queue.md)

[<span data-ttu-id="f6b4f-221">为本地用户规划云语音邮件服务</span><span class="sxs-lookup"><span data-stu-id="f6b4f-221">Plan Cloud Voicemail service for on-premises users</span></span>](plan-cloud-voicemail.md)

[<span data-ttu-id="f6b4f-222">新 CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="f6b4f-222">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="f6b4f-223">新 CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="f6b4f-223">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

<span data-ttu-id="f6b4f-224">[在 Microsoft 团队](/MicrosoftTeams/manage-resource-accounts)  -  \( 中管理资源帐户创建驻留在网上的资源帐户\)</span><span class="sxs-lookup"><span data-stu-id="f6b4f-224">[Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \(to create resource accounts homed online\)</span></span>
