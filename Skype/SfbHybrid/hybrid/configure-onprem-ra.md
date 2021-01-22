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
description: 为 Skype for Business Server 2019 设置资源帐户。
ms.openlocfilehash: 1d8294eb717982b5ac68df06a5370059e83a62c5
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "49919008"
---
# <a name="configure-resource-accounts"></a><span data-ttu-id="2fe83-103">配置资源帐户</span><span class="sxs-lookup"><span data-stu-id="2fe83-103">Configure resource accounts</span></span>

<span data-ttu-id="2fe83-104">Skype for Business Server 2019 混合实现仅将电话系统提供的云服务用于统一消息，不与 Exchange Online 集成。</span><span class="sxs-lookup"><span data-stu-id="2fe83-104">Skype for Business Server 2019 hybrid implementations only use Cloud services provided by Phone System for unified messaging and do not integrate with Exchange Online.</span></span> <span data-ttu-id="2fe83-105">在 Skype for Business Server 2019 中，你现在可以使用 Microsoft [365 或 Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)中的电话系统功能中所述的云呼叫队列和自动助理。</span><span class="sxs-lookup"><span data-stu-id="2fe83-105">In Skype for Business Server 2019 you are now able to use the Cloud call queues and auto attendants described in [Here's what you get with Phone System in Microsoft 365 or Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).</span></span>

<span data-ttu-id="2fe83-106">若要将电话系统自动助理或呼叫队列与 Skype for Business Server 2019 一同使用，你需要创建充当应用程序终结点的资源帐户，并可以分配电话号码，然后使用联机 Teams 管理中心配置呼叫队列或自动助理。</span><span class="sxs-lookup"><span data-stu-id="2fe83-106">To use an Phone System auto attendant or call queue with Skype for Business Server 2019, you will need to create resource accounts that act as application endpoints and can be assigned phone numbers, then use the online Teams admin center to configure the call queue or auto attendant.</span></span> <span data-ttu-id="2fe83-107">此资源帐户可以联机 ([在 Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) 中管理资源帐户，以创建联机或本地) 资源帐户，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="2fe83-107">This resource account can be homed online (see [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) to create resource accounts homed online) or on premises as described in this article.</span></span> <span data-ttu-id="2fe83-108">通常，你将具有多个电话系统自动助理或呼叫队列节点，每个节点都映射到可联机或位于 Skype for Business Server 2019 中的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="2fe83-108">Typically you will have multiple Phone System auto attendant or call queue nodes, each of which is mapped to a resource accounts, which can be homed online or in Skype for Business Server 2019.</span></span>

<span data-ttu-id="2fe83-109">如果您有现有的 Exchange UM 自动助理和呼叫队列系统，在切换到 Exchange Server 2019 或 Exchange Online 之前，您需要手动记录详细信息，如下所述，然后使用 Teams 管理中心实现全新的系统。</span><span class="sxs-lookup"><span data-stu-id="2fe83-109">If you have an existing Exchange UM auto attendant and call queue system, before you switch to Exchange Server 2019 or Exchange online you will need to manually record the details as described below and then implement a completely new system using the Teams admin center.</span></span>

## <a name="overview"></a><span data-ttu-id="2fe83-110">概述</span><span class="sxs-lookup"><span data-stu-id="2fe83-110">Overview</span></span>

<span data-ttu-id="2fe83-111">如果电话系统自动助理或呼叫队列需要服务号码，可以按以下顺序满足各种依赖关系：</span><span class="sxs-lookup"><span data-stu-id="2fe83-111">If your Phone System auto attendant or call queue will need a service number, the various dependencies can be met in the following sequence:</span></span>

1. <span data-ttu-id="2fe83-112">获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="2fe83-112">Obtain a service number.</span></span>
2. <span data-ttu-id="2fe83-113">获取免费电话系统 - [虚拟用户许可证](/MicrosoftTeams/teams-add-on-licensing/virtual-user) 或付费电话系统许可证，以用于资源帐户。</span><span class="sxs-lookup"><span data-stu-id="2fe83-113">Obtain a free Phone System - [Virtual User license](/MicrosoftTeams/teams-add-on-licensing/virtual-user) or a paid Phone System license to use with the resource account.</span></span>
3. <span data-ttu-id="2fe83-114">创建资源帐户。</span><span class="sxs-lookup"><span data-stu-id="2fe83-114">Create the resource account.</span></span> <span data-ttu-id="2fe83-115">自动助理或呼叫队列需要具有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="2fe83-115">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="2fe83-116">等待联机和本地之间的 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="2fe83-116">Wait for an active directory sync between online and on premises.</span></span>
5. <span data-ttu-id="2fe83-117">将电话系统许可证分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="2fe83-117">Assign the Phone System license to the resource account.</span></span>
6. <span data-ttu-id="2fe83-118">为资源帐户分配服务号码。</span><span class="sxs-lookup"><span data-stu-id="2fe83-118">Assign a service number to the resource account.</span></span>
7. <span data-ttu-id="2fe83-119">创建电话系统呼叫队列或自动助理。</span><span class="sxs-lookup"><span data-stu-id="2fe83-119">Create a Phone System call queue or auto attendant.</span></span>
8. <span data-ttu-id="2fe83-120">将资源帐户与自动助理或呼叫队列关联： (New-CsApplicationInstanceAssociation) 。</span><span class="sxs-lookup"><span data-stu-id="2fe83-120">Associate the resource account with an auto attendant or call queue: (New-CsApplicationInstanceAssociation).</span></span>

<span data-ttu-id="2fe83-121">如果自动助理或呼叫队列嵌套在顶级自动助理下，则如果你希望自动助理和呼叫队列的结构中有多个入口点，则关联的资源帐户只需要一个电话号码。</span><span class="sxs-lookup"><span data-stu-id="2fe83-121">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="2fe83-122">若要将呼叫重定向到组织中在线用户，他们必须拥有电话系统许可证，并且必须启用企业语音 或具有 Microsoft 365 或 Office 365 通话套餐。</span><span class="sxs-lookup"><span data-stu-id="2fe83-122">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Microsoft 365 or Office 365 Calling Plans.</span></span> <span data-ttu-id="2fe83-123">请参阅 [分配 Microsoft Teams 许可证](/MicrosoftTeams/assign-teams-licenses)。</span><span class="sxs-lookup"><span data-stu-id="2fe83-123">See [Assign Microsoft Teams licenses](/MicrosoftTeams/assign-teams-licenses).</span></span> <span data-ttu-id="2fe83-124">若要为用户启用企业语音，可以使用Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="2fe83-124">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="2fe83-125">例如运行：  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="2fe83-125">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

<span data-ttu-id="2fe83-126">如果要创建的电话系统自动助理或呼叫队列将嵌套，并且不需要电话号码，则过程为：</span><span class="sxs-lookup"><span data-stu-id="2fe83-126">If the Phone system auto attendant or call queue you're creating will be nested and will not need a phone number, the process is:</span></span>

1. <span data-ttu-id="2fe83-127">创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="2fe83-127">Create the resource account</span></span>  
2. <span data-ttu-id="2fe83-128">等待联机和本地之间的 Active Directory 同步</span><span class="sxs-lookup"><span data-stu-id="2fe83-128">Wait for an active directory sync between online and on premises</span></span>
3. <span data-ttu-id="2fe83-129">创建电话系统自动助理或呼叫队列</span><span class="sxs-lookup"><span data-stu-id="2fe83-129">Create a Phone System auto attendant or call queue</span></span>
4. <span data-ttu-id="2fe83-130">将资源帐户与电话系统自动助理或呼叫队列关联</span><span class="sxs-lookup"><span data-stu-id="2fe83-130">Associate the resource account with a Phone System auto attendant or call queue</span></span>

## <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="2fe83-131">创建具有电话号码的资源帐户</span><span class="sxs-lookup"><span data-stu-id="2fe83-131">Create a resource account with a phone number</span></span>

<span data-ttu-id="2fe83-132">创建使用电话号码的资源帐户需要按以下顺序执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="2fe83-132">Creating a resource account that uses a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="2fe83-133">移植或获取收费或免费服务号码。</span><span class="sxs-lookup"><span data-stu-id="2fe83-133">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="2fe83-134">无法将号码分配给任何其他语音服务或资源帐户。</span><span class="sxs-lookup"><span data-stu-id="2fe83-134">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="2fe83-135">在将电话号码分配给资源帐户之前，你需要获取或移植现有的收费或免费服务号码。</span><span class="sxs-lookup"><span data-stu-id="2fe83-135">Before you assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="2fe83-136">获取收费或免费服务电话号码后，它们会显示在 **Microsoft Teams** 管理中心语音电话号码中，列出的号码类型将列为"服务  >    >  **- 免费"。** </span><span class="sxs-lookup"><span data-stu-id="2fe83-136">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="2fe83-137">若要获取服务号码，请参阅["获取服务电话号码](/MicrosoftTeams/getting-service-phone-numbers)"，或者如果你想要转移现有服务号码，请参阅"将电话号码转移到[Teams"。](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams)</span><span class="sxs-lookup"><span data-stu-id="2fe83-137">To get your service numbers, see [Getting service phone numbers](/MicrosoftTeams/getting-service-phone-numbers) or if you want to transfer an existing service number, see [Transfer phone numbers to Teams](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams).</span></span>

   <span data-ttu-id="2fe83-138">如果你在美国之外，则你无法使用 Microsoft Teams 管理中心获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="2fe83-138">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="2fe83-139">转到 ["管理组织的电话号码](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) "，以查看如何从美国以外的国家/地区进行管理。</span><span class="sxs-lookup"><span data-stu-id="2fe83-139">Go to [Manage phone numbers for your organization](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.</span></span>

2. <span data-ttu-id="2fe83-140">购买电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="2fe83-140">Buy a Phone System license.</span></span> <span data-ttu-id="2fe83-141">请参阅：</span><span class="sxs-lookup"><span data-stu-id="2fe83-141">See:</span></span>  
   - [<span data-ttu-id="2fe83-142">电话系统–虚拟用户许可证</span><span class="sxs-lookup"><span data-stu-id="2fe83-142">Phone System–Virtual User license</span></span>](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [<span data-ttu-id="2fe83-143">Office 365 企业版（E1 和 E3）</span><span class="sxs-lookup"><span data-stu-id="2fe83-143">Office 365 Enterprise E1 and E3</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [<span data-ttu-id="2fe83-144">Office 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="2fe83-144">Office 365 Enterprise E5</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [<span data-ttu-id="2fe83-145">Office 365 企业版 E5 商业版软件</span><span class="sxs-lookup"><span data-stu-id="2fe83-145">Office 365 Enterprise E5 Business Software</span></span>](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. <span data-ttu-id="2fe83-146">通过为每个电话系统自动助理或呼叫队列运行 cmdlet 创建本地资源帐户，并为每个帐户指定名称 `New-CsHybridApplicationEndpoint` 、sip 地址等。</span><span class="sxs-lookup"><span data-stu-id="2fe83-146">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System auto attendant or call queue, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="2fe83-147">有关[此命令的更多详细信息，请参阅 New-CsHybridApplicationEndpoint。](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="2fe83-147">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

4. <span data-ttu-id="2fe83-148"> (可选) 创建资源帐户后，可以等待 AD 在联机和本地之间同步，也可以强制同步并继续电话系统自动助理或呼叫队列的联机配置。</span><span class="sxs-lookup"><span data-stu-id="2fe83-148">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premises, or force a sync and proceed to online configuration of Phone System auto attendant or call queues.</span></span> <span data-ttu-id="2fe83-149">若要强制同步，需要在运行 AAD Connect (的计算机上运行以下命令（如果尚未执行的话）需要加载以运行此命令 `import-module adsync`) ：</span><span class="sxs-lookup"><span data-stu-id="2fe83-149">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="2fe83-150">有关[此命令的更多详细信息，请参阅 Start-ADSyncSyncCycle。](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler)</span><span class="sxs-lookup"><span data-stu-id="2fe83-150">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>
    
    <span data-ttu-id="2fe83-151">请注意，此时，帐户可能已同步，但设置可能不完整。</span><span class="sxs-lookup"><span data-stu-id="2fe83-151">Note-at this point, the account may have synced, but provisioning may not be complete.</span></span>  <span data-ttu-id="2fe83-152">检查 [Get-CsOnlineApplicationEndpoint 的输出](https://docs.microsoft.com/powershell/module/skype/get-csonlineapplicationendpoint)。</span><span class="sxs-lookup"><span data-stu-id="2fe83-152">Check the output of [Get-CsOnlineApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/get-csonlineapplicationendpoint).</span></span>  <span data-ttu-id="2fe83-153">如果同步的终结点尚未完成预配，则它将不会在此处显示。</span><span class="sxs-lookup"><span data-stu-id="2fe83-153">If the synced endpoint has not completed provisioning yet, then it will not appear here.</span></span>  <span data-ttu-id="2fe83-154">可以在"Teams 设置状态"下检查 M365 门户中的预配 [请求的状态](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning)。</span><span class="sxs-lookup"><span data-stu-id="2fe83-154">You can check the status of the provisioning requests in the M365 portal under [Teams Setup Status](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning).</span></span>  <span data-ttu-id="2fe83-155">此预配阶段最多可能需要 24 小时。</span><span class="sxs-lookup"><span data-stu-id="2fe83-155">This provisioning phase can take up to 24 hours.</span></span>

5. <span data-ttu-id="2fe83-156">将电话系统 - 虚拟用户或电话系统许可证分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="2fe83-156">Assign the Phone System - Virtual User or Phone System license to the resource account.</span></span> <span data-ttu-id="2fe83-157">请参阅["分配 Microsoft Teams 附加许可证"和](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses)["向用户分配许可证"。](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="2fe83-157">See [Assign Microsoft Teams add-on licenses](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) and [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

   <span data-ttu-id="2fe83-158">如果要将电话号码分配给资源帐户，现在可以使用免费电话系统 - 虚拟用户许可证。</span><span class="sxs-lookup"><span data-stu-id="2fe83-158">If you are assigning a phone number to a resource account you can now use the cost-free Phone System - Virtual User license.</span></span> <span data-ttu-id="2fe83-159">这将为组织级别的电话号码提供电话系统功能，并允许创建自动助理和呼叫队列功能。</span><span class="sxs-lookup"><span data-stu-id="2fe83-159">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>


6. <span data-ttu-id="2fe83-160">将服务号码分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="2fe83-160">Assign the service number to the resource account.</span></span> <span data-ttu-id="2fe83-161">使用 `Set-CsHybridApplicationEndpoint` 此命令为资源帐户分配 (-LineURI 选项) 分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="2fe83-161">Use the `Set-CsHybridApplicationEndpoint` command to a assign a phone number (with the -LineURI option) to the resource account.</span></span>

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    <span data-ttu-id="2fe83-162">有关[此命令的更多详细信息，请参阅 Set-CsHybridApplicationEndpoint。](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="2fe83-162">See [Set-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

    <span data-ttu-id="2fe83-163">若要将直接路由或混合号码分配给资源帐户，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="2fe83-163">To assign a Direct Routing or hybrid number to  a resource account, use the following cmdlet:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   <span data-ttu-id="2fe83-164">如果将资源帐户分配给顶级自动助理或呼叫队列，则该帐户将需要分配的电话号码。</span><span class="sxs-lookup"><span data-stu-id="2fe83-164">The resource account will need an assigned phone number if it will be assigned to a top level auto attendant or call queue.</span></span> <span data-ttu-id="2fe83-165">用户 (订阅者) 电话号码无法分配给资源帐户，只能使用收费或免费服务电话号码。</span><span class="sxs-lookup"><span data-stu-id="2fe83-165">User (subscriber) phone numbers can't be assigned to a resource account, only service toll or toll-free phone numbers can be used.</span></span>

     <span data-ttu-id="2fe83-166">你可以将直接路由或混合号码分配给你的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="2fe83-166">You can assign a Direct Routing or hybrid number to your resource account.</span></span> <span data-ttu-id="2fe83-167">有关详细信息，请参阅["规划直接路由"和](/MicrosoftTeams/direct-routing-plan)["规划云自动助理"。](plan-cloud-auto-attendant.md)</span><span class="sxs-lookup"><span data-stu-id="2fe83-167">For details, see [Plan Direct Routing](/MicrosoftTeams/direct-routing-plan) and [Plan Cloud auto attendants](plan-cloud-auto-attendant.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="2fe83-168">分配给自动助理和呼叫队列的资源帐户的直接路由服务号码仅受 Microsoft Teams 用户和代理支持。</span><span class="sxs-lookup"><span data-stu-id="2fe83-168">Direct Routing service numbers assigned to resource accounts for auto attendant and call queues are supported for Microsoft Teams users and agents only.</span></span>

7. <span data-ttu-id="2fe83-169">创建电话系统自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="2fe83-169">Create the Phone System auto attendant or call queue.</span></span> <span data-ttu-id="2fe83-170">请查看下列内容之一：</span><span class="sxs-lookup"><span data-stu-id="2fe83-170">See one of the following:</span></span>

   - [<span data-ttu-id="2fe83-171">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="2fe83-171">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="2fe83-172">创建云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="2fe83-172">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. <span data-ttu-id="2fe83-173">将资源帐户与之前选择的电话系统自动助理或呼叫队列关联。</span><span class="sxs-lookup"><span data-stu-id="2fe83-173">Associate the resource account with the Phone System auto attendant or call queue you chose previously.</span></span>

## <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="2fe83-174">创建没有电话号码的资源帐户</span><span class="sxs-lookup"><span data-stu-id="2fe83-174">Create a resource account without a phone number</span></span>

<span data-ttu-id="2fe83-175">本节讨论创建本地资源帐户。</span><span class="sxs-lookup"><span data-stu-id="2fe83-175">This section discusses creating a resource account that is homed on premises.</span></span> <span data-ttu-id="2fe83-176">在 Microsoft Teams 中管理资源帐户时，将讨论创建联机管理 [的资源帐户](/MicrosoftTeams/manage-resource-accounts)。</span><span class="sxs-lookup"><span data-stu-id="2fe83-176">Creating a resource account that is homed online is discussed at [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).</span></span>

<span data-ttu-id="2fe83-177">无论是创建全新的电话系统自动助理或呼叫队列结构，还是重建最初在 Exchange UM 中创建的结构，这些步骤都是必需的。</span><span class="sxs-lookup"><span data-stu-id="2fe83-177">These steps are necessary whether you are creating a brand new Phone System auto attendant or call queue structure, or rebuilding structure originally created in Exchange UM.</span></span>

<span data-ttu-id="2fe83-178">登录到 Skype for Business 前端服务器并运行以下 PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="2fe83-178">Log in to the Skype for Business front end server and run the following PowerShell cmdlets:</span></span>

1. <span data-ttu-id="2fe83-179">通过为每个电话系统自动助理或呼叫队列运行 cmdlet 创建本地资源帐户，并为每个帐户指定名称 `New-CsHybridApplicationEndpoint` 、sip 地址等。</span><span class="sxs-lookup"><span data-stu-id="2fe83-179">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System auto attendant or call queue, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="2fe83-180">有关[此命令的更多详细信息，请参阅 New-CsHybridApplicationEndpoint。](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="2fe83-180">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

2. <span data-ttu-id="2fe83-181"> (可选) 创建资源帐户后，可以等待 AD 在联机和本地之间同步，也可以强制同步并继续电话系统自动助理或呼叫队列的联机配置。</span><span class="sxs-lookup"><span data-stu-id="2fe83-181">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premises, or force a sync and proceed to online configuration of Phone System auto attendant or call queues.</span></span> <span data-ttu-id="2fe83-182">若要强制同步，需要在运行 AAD Connect (的计算机上运行以下命令（如果尚未执行的话）需要加载以运行 `import-module adsync`) ：</span><span class="sxs-lookup"><span data-stu-id="2fe83-182">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="2fe83-183">有关[此命令的更多详细信息，请参阅 Start-ADSyncSyncCycle。](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler)</span><span class="sxs-lookup"><span data-stu-id="2fe83-183">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

3. <span data-ttu-id="2fe83-184">创建电话系统自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="2fe83-184">Create the Phone System auto attendant or call queue.</span></span> <span data-ttu-id="2fe83-185">请查看下列内容之一：</span><span class="sxs-lookup"><span data-stu-id="2fe83-185">See one of the following:</span></span>
   - [<span data-ttu-id="2fe83-186">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="2fe83-186">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="2fe83-187">创建云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="2fe83-187">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. <span data-ttu-id="2fe83-188">将资源帐户与之前选择的电话系统自动助理或呼叫队列关联。</span><span class="sxs-lookup"><span data-stu-id="2fe83-188">Associate the resource account and the Phone System auto attendant or call queue you chose previously.</span></span>

## <a name="test-the-implementation"></a><span data-ttu-id="2fe83-189">测试实现</span><span class="sxs-lookup"><span data-stu-id="2fe83-189">Test the implementation</span></span>

<span data-ttu-id="2fe83-190">测试实现的最佳方法就是呼叫为电话系统自动助理或呼叫队列配置的号码，并连接到其中一个代理或菜单。</span><span class="sxs-lookup"><span data-stu-id="2fe83-190">The best way to test the implementation is to call the number configured for a Phone System auto attendant or call queue and connect to one of the agents or menus.</span></span> <span data-ttu-id="2fe83-191">您还可以使用管理中心操作窗格中的"测试"按钮快速进行测试呼叫。</span><span class="sxs-lookup"><span data-stu-id="2fe83-191">You can also quickly place a test call by using the **Test button** in the admin center Action pane.</span></span> <span data-ttu-id="2fe83-192">如果要对电话系统自动助理或呼叫队列进行更改，请选择它，然后在操作窗格中单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="2fe83-192">If you want to make changes to a Phone System auto attendant or call queue, select it and then in the Action pane click **Edit**.</span></span> 

> [!TIP]
> <span data-ttu-id="2fe83-193">如果你的资源帐户在被分配到呼叫队列或自动助理时有困难，请参阅[Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system)的已知问题和 Microsoft Teams[](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)博客中的"如何修复我的混合应用程序实例"部分。</span><span class="sxs-lookup"><span data-stu-id="2fe83-193">If your resource account has difficulties with being assigned to a call queue or auto attendant, see [Known issues for Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system) and the [How to fix my hybrid application instances](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) section in the Microsoft Teams Blog.</span></span>

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a><span data-ttu-id="2fe83-194">将 Exchange UM 自动助理或呼叫队列移动到电话系统</span><span class="sxs-lookup"><span data-stu-id="2fe83-194">Moving an Exchange UM auto attendant or call queue to Phone System</span></span>

<span data-ttu-id="2fe83-195">从 Exchange UM 迁移到电话系统需要重新创建呼叫队列和自动助理结构，不支持从一个直接迁移到另一个。</span><span class="sxs-lookup"><span data-stu-id="2fe83-195">Migration from Exchange UM to Phone System will require recreating the call queue and auto attendant structure, directly migrating from one to the other is not supported.</span></span> <span data-ttu-id="2fe83-196">重新实现一组呼叫队列和自动助理：</span><span class="sxs-lookup"><span data-stu-id="2fe83-196">To re-implement a set of call queues and auto attendants:</span></span>

1. <span data-ttu-id="2fe83-197">以管理员身份登录时，在 Exchange 2013 或 2016 系统上运行以下命令，获取所有 Exchange UM 自动助理和呼叫队列的列表：</span><span class="sxs-lookup"><span data-stu-id="2fe83-197">Get a list of all Exchange UM auto attendants and call queues by running the following command on the Exchange 2013 or 2016 system while logged in as admin:</span></span>

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. <span data-ttu-id="2fe83-198">对于每个列出的 Exchange UM 呼叫队列或自动助理，记下其在结构、设置中的位置，并获取关联声音或文本到语音到语音文件的副本 (输出中的 guid 将为存储文件的文件夹的名称) 。</span><span class="sxs-lookup"><span data-stu-id="2fe83-198">For each listed Exchange UM call queue or auto attendant, note its place in the structure, settings, and get copies of associated sound or text-to-speech files (the guid in the output will be the name of a folder where the files are stored).</span></span> <span data-ttu-id="2fe83-199">可以通过运行以下命令获取这些详细信息：</span><span class="sxs-lookup"><span data-stu-id="2fe83-199">You can get these details by running the command:</span></span>

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    <span data-ttu-id="2fe83-200">有关[此命令的更多详细信息，请参阅 Get-UMAutoAttendant。](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="2fe83-200">See [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) for more details on this command.</span></span> <span data-ttu-id="2fe83-201">可能需要捕获的选项的完整列表位于 [UMAutoAttendant](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) 成员中，但需要记下的最重要的选项是：</span><span class="sxs-lookup"><span data-stu-id="2fe83-201">A complete list of options you might need to capture is at [UMAutoAttendant members](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) but the most important options to note down are:</span></span>

    - <span data-ttu-id="2fe83-202">营业时间</span><span class="sxs-lookup"><span data-stu-id="2fe83-202">Business hours</span></span>
    - <span data-ttu-id="2fe83-203">非营业时间</span><span class="sxs-lookup"><span data-stu-id="2fe83-203">Non-business hours</span></span>
    - <span data-ttu-id="2fe83-204">语言</span><span class="sxs-lookup"><span data-stu-id="2fe83-204">Language</span></span>
    - <span data-ttu-id="2fe83-205">假日日程安排</span><span class="sxs-lookup"><span data-stu-id="2fe83-205">Holiday schedule</span></span>

3. <span data-ttu-id="2fe83-206">如前文所述创建新的本地终结点。</span><span class="sxs-lookup"><span data-stu-id="2fe83-206">Create new on-premises endpoints as previously described.</span></span>
   <span data-ttu-id="2fe83-207">为顶级自动助理分配一个临时号码以进行测试。</span><span class="sxs-lookup"><span data-stu-id="2fe83-207">Assign the top-level auto attendant a temporary number for testing purposes.</span></span>

4. <span data-ttu-id="2fe83-208">配置使用终结点的电话系统自动助理或呼叫队列，如前面所述。</span><span class="sxs-lookup"><span data-stu-id="2fe83-208">Configure a Phone System auto attendant or call queue that uses the endpoints as previously described.</span></span>

5. <span data-ttu-id="2fe83-209">测试电话系统自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="2fe83-209">Test the Phone System auto attendant or call queue.</span></span>

6. <span data-ttu-id="2fe83-210">将链接到 Exchange UM 呼叫队列或自动助理的电话号码重新分配给相应的电话系统自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="2fe83-210">Reassign the phone number linked to the Exchange UM call queue or auto attendant to the corresponding Phone System auto attendant or call queue.</span></span>  

   <span data-ttu-id="2fe83-211">此时，如果已迁移 UM 语音邮件，则应该可以迁移到 Exchange Server 2019。</span><span class="sxs-lookup"><span data-stu-id="2fe83-211">At this point, if you have already migrated UM Voicemail, you should be in a position to migrate to Exchange Server 2019.</span></span>

## <a name="see-also"></a><span data-ttu-id="2fe83-212">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2fe83-212">See Also</span></span>

[<span data-ttu-id="2fe83-213">创建云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="2fe83-213">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)

[<span data-ttu-id="2fe83-214">什么是云自动助理？</span><span class="sxs-lookup"><span data-stu-id="2fe83-214">What are Cloud auto attendants?</span></span>](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[<span data-ttu-id="2fe83-215">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="2fe83-215">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[<span data-ttu-id="2fe83-216">规划云自动助理</span><span class="sxs-lookup"><span data-stu-id="2fe83-216">Plan Cloud auto attendants</span></span>](plan-cloud-auto-attendant.md)

[<span data-ttu-id="2fe83-217">规划云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="2fe83-217">Plan Cloud call queues</span></span>](plan-call-queue.md)

[<span data-ttu-id="2fe83-218">为本地用户规划云语音邮件服务</span><span class="sxs-lookup"><span data-stu-id="2fe83-218">Plan Cloud Voicemail service for on-premises users</span></span>](plan-cloud-voicemail.md)

[<span data-ttu-id="2fe83-219">New-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="2fe83-219">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="2fe83-220">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="2fe83-220">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

<span data-ttu-id="2fe83-221">[在 Microsoft Teams 中管理资源帐户](/MicrosoftTeams/manage-resource-accounts)  -  \(创建联机管理的资源帐户\)</span><span class="sxs-lookup"><span data-stu-id="2fe83-221">[Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \(to create resource accounts homed online\)</span></span>
