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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: 了解如何管理中的 Microsoft 团队资源帐户
ms.openlocfilehash: dea4a154e25c719ddabc572ba26ddb7d25c43d71
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835415"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="cf825-103">在 Microsoft Teams 中管理资源帐户</span><span class="sxs-lookup"><span data-stu-id="cf825-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="cf825-104">资源帐户也称为 Azure Active Directory 中的已禁用的用户对象，可以用于通常表示资源。</span><span class="sxs-lookup"><span data-stu-id="cf825-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="cf825-105">在 Exchange 它可能用于表示会议室，例如，并允许有一个电话号码。</span><span class="sxs-lookup"><span data-stu-id="cf825-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="cf825-106">在 Microsoft 365 或本地的企业服务器，使用 Skype 可托管资源帐户并使用 Powershell 命令创建这些帐户。</span><span class="sxs-lookup"><span data-stu-id="cf825-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business server, and these accounts are created using Powershell commands.</span></span>

<span data-ttu-id="cf825-107">在 Microsoft 团队或 Skype 业务联机，每个呼叫队列或自动助理需要具有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="cf825-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="cf825-108">资源帐户是否需要分配的电话号码将取决于打算使用的关联的呼叫队列或自动助理。</span><span class="sxs-lookup"><span data-stu-id="cf825-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="cf825-109">引用上调用队列的文章和自动助理电话号码分配给资源帐户之前底部这篇文章的链接。</span><span class="sxs-lookup"><span data-stu-id="cf825-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="cf825-110">本文同时适用于 Microsoft 团队和 Skype 业务 online。</span><span class="sxs-lookup"><span data-stu-id="cf825-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a><span data-ttu-id="cf825-111">若要将电话号码分配给资源帐户的先决条件</span><span class="sxs-lookup"><span data-stu-id="cf825-111">Prerequisites to assign a phone number to a resource account</span></span>

<span data-ttu-id="cf825-112">若要开始非常重要记住几件事：</span><span class="sxs-lookup"><span data-stu-id="cf825-112">To get started it's important to remember a few things:</span></span>
  
- <span data-ttu-id="cf825-113">自动助理或呼叫队列需要具有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="cf825-113">An auto attendant or call queue is required to have an associated resource account.</span></span> <span data-ttu-id="cf825-114">有关资源帐户的详细信息，请参阅[团队中的管理资源帐户](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="cf825-114">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="cf825-115">如果您打算分配一个直接路由号，则需要获取并将以下许可证分配给资源帐户\(Office 365 企业版 E1、 E3 或 E5，与电话系统加载项\)。</span><span class="sxs-lookup"><span data-stu-id="cf825-115">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="cf825-116">如果要改用分配 Microsoft 服务号码，您需要获取并将以下许可证分配给资源帐户\(Office 365 企业版 E1、 E3 或 E5，与电话系统加载项调用规划\)。</span><span class="sxs-lookup"><span data-stu-id="cf825-116">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>
- <span data-ttu-id="cf825-117">您只需使用的电话号码分配给他们许可资源帐户。</span><span class="sxs-lookup"><span data-stu-id="cf825-117">You only need to license the resource accounts with a phone number assigned to them.</span></span> <span data-ttu-id="cf825-118">在嵌套的自动助理或呼叫队列中，您不需要许可证自动助理的其余部分或呼叫队列，如果没有与其关联的电话号码</span><span class="sxs-lookup"><span data-stu-id="cf825-118">In a nested auto attendant or call queue, you do not need to license the rest of the auto attendants or call queues if they do not have phone numbers associated with them</span></span>

> [!NOTE] 
> <span data-ttu-id="cf825-119">Microsoft 团队用户和代理仅支持直接路由服务号码的自动助理和呼叫的队列。</span><span class="sxs-lookup"><span data-stu-id="cf825-119">Direct Routing service numbers for auto attendant and call queues is supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE] 
> <span data-ttu-id="cf825-120">现在您需要使用用户授权模型，Microsoft 的协作的应用程序云自动助理和呼叫的队列，如适当许可模型中。</span><span class="sxs-lookup"><span data-stu-id="cf825-120">Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cf825-121">要重定向呼叫的人员在组织中联机，它们必须具有**电话系统**许可证和启用了企业语音或其 Office 365 调用计划。</span><span class="sxs-lookup"><span data-stu-id="cf825-121">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="cf825-122">请参阅[分配的 Microsoft 团队许可证](assign-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="cf825-122">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="cf825-123">要为他们启用企业语音，可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="cf825-123">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="cf825-124">例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="cf825-124">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="cf825-125">您可以直接路由混合数字分配资源帐户。</span><span class="sxs-lookup"><span data-stu-id="cf825-125">You can assign a Direct Routing Hybrid number to your resource account.</span></span>  <span data-ttu-id="cf825-126">有关详细信息，请参阅[规划直接路由](direct-routing-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="cf825-126">See [Plan Direct Routing](direct-routing-plan.md) for details.</span></span>
- <span data-ttu-id="cf825-127">对于 Microsoft 调用计划，您可以仅分配收费和免费电话服务电话号码的**Microsoft 团队管理中心**中获得或端口从另一个服务提供商的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="cf825-127">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or ported from another service provider to a resource account.</span></span> <span data-ttu-id="cf825-128">若要获取并使用免费电话号码，则需要设置通信点数。</span><span class="sxs-lookup"><span data-stu-id="cf825-128">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

> [!NOTE]
> <span data-ttu-id="cf825-129">用户 （订阅服务器） 的电话号码不能分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="cf825-129">User (subscriber) phone numbers can't be assigned to a resource account.</span></span> <span data-ttu-id="cf825-130">可以使用只有服务收费电话或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="cf825-130">Only service toll or toll-free phone numbers can be used.</span></span>

<span data-ttu-id="cf825-131">若要将电话号码分配给资源帐户，您需要用于获取或您现有的收费电话或免费电话服务的端口号。</span><span class="sxs-lookup"><span data-stu-id="cf825-131">To assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="cf825-132">获得收费电话或免费电话服务电话号码后，他们会显示在**Microsoft 团队管理中心** > **语音** > **电话号码**，以及被列为**Service-免费电话\*\*\*\*号码类型**列出将。</span><span class="sxs-lookup"><span data-stu-id="cf825-132">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="cf825-133">若要获取服务号码，请参阅[Getting 服务电话号码](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)或如果您想要传输的现有服务号码，请参阅[传输到 Office 365 的电话号码](transfer-phone-numbers-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="cf825-133">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cf825-134">如果您在美国以外，您无法使用的 Microsoft 团队管理中心获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="cf825-134">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="cf825-135">转到[管理您的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)而是以了解如何执行从美国的外部。</span><span class="sxs-lookup"><span data-stu-id="cf825-135">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="cf825-136">在 Microsoft 团队管理中心创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="cf825-136">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="cf825-137">在 Microsoft 团队管理中心中，导航到**组织范围的设置** > **资源帐户**。</span><span class="sxs-lookup"><span data-stu-id="cf825-137">In Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**.</span></span> 

![asd](media/r-a-master.png)

![1 号](media/sfbcallout1.png)

<span data-ttu-id="cf825-140">若要创建新的资源帐户，单击 **+ 新帐户**。</span><span class="sxs-lookup"><span data-stu-id="cf825-140">To create a new resource account click **+ New account**.</span></span> <span data-ttu-id="cf825-141">在弹出窗口中，填写的显示名称和用户名 （域名应自动填充） 的资源帐户然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="cf825-141">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![资源帐户](media/res-acct.png)

<span data-ttu-id="cf825-143">接下来，您将需要许可证于资源帐户后，[将对业务的 Office 365 中的用户的许可证分配](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)中所述</span><span class="sxs-lookup"><span data-stu-id="cf825-143">Next, you will  need to apply a license to the resource account, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span></span>

<span data-ttu-id="cf825-144">![3 号](media/sfbcallout3.png)一旦您已创建资源帐户并分配许可证，您可以在上**分配/取消分配**要调用规划服务号码分配资源帐户后，单击或将资源帐户分配给自动助理或呼叫队列已存在。</span><span class="sxs-lookup"><span data-stu-id="cf825-144">![number 3](media/sfbcallout3.png) Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a Calling Plan service number to the resource account, or assign the resource account to an auto attendant or call queue that already exists.</span></span> <span data-ttu-id="cf825-145">可以完成分配直接路由号码仅使用 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cf825-145">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="cf825-146">如果您呼叫的队列或自动助理仍需要创建，您创建它时，您可以将链接的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="cf825-146">If your call queue or auto attendant still needs to be created, you can link the resource account while you create it.</span></span> <span data-ttu-id="cf825-147">完成后，请单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="cf825-147">Click **Save** when you are done.</span></span>

![资源帐户分配](media/r-a-assign.png)

<span data-ttu-id="cf825-149">![2 号](media/sfbcallout2.png)可以编辑使用**编辑**选项的资源帐户显示名称。</span><span class="sxs-lookup"><span data-stu-id="cf825-149">![number 2](media/sfbcallout2.png) You can edit the resource account display name using the **Edit** option.</span></span>  <span data-ttu-id="cf825-150">完成后，请单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="cf825-150">Click **Save** when you are done.</span></span>
<span data-ttu-id="cf825-151">![编辑资源帐户](media/r-a-edit.png)</span><span class="sxs-lookup"><span data-stu-id="cf825-151">![edit resource account](media/r-a-edit.png)</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="cf825-152">在 Powershell 中创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="cf825-152">Create a resource account in Powershell</span></span>

<span data-ttu-id="cf825-153">对于 Microsoft 调用计划，您可以仅分配收费和免费电话服务电话号码的**Microsoft 团队管理中心**中获得或端口从另一个服务提供商的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="cf825-153">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or ported from another service provider to a resource account.</span></span> <span data-ttu-id="cf825-154">若要获取并使用免费电话号码，则需要设置通信点数。</span><span class="sxs-lookup"><span data-stu-id="cf825-154">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

<span data-ttu-id="cf825-155">根据您的资源帐户是否位于联机或本地，您需要连接到相应的 Powershell 提示符处，具有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="cf825-155">Depending on whether your resource account is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span> 
- <span data-ttu-id="cf825-156">下面的 Powershell cmdlet 示例假定联机托管资源帐户使用[新建 CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps)创建联机托管资源帐户。</span><span class="sxs-lookup"><span data-stu-id="cf825-156">The following Powershell cmdlet examples presume the resource account is homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to create a resource account that is homed online.</span></span>

- <span data-ttu-id="cf825-157">资源帐户驻留在内部部署中 Skype 的业务服务器 2019 可以用于云呼叫的队列和云自动助理，请参阅[配置云呼叫队列](/skypeforbusiness/SfbHybrid/hybrid/configure-call-queue.md)或[配置云自动助理](/skypeforbusiness/SfbHybrid/hybrid/configure-cloud-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="cf825-157">For resource accounts homed on-premises in Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Configure Cloud Call Queues](/skypeforbusiness/SfbHybrid/hybrid/configure-call-queue.md) or [Configure Cloud Auto Attendants](/skypeforbusiness/SfbHybrid/hybrid/configure-cloud-auto-attendant.md).</span></span> <span data-ttu-id="cf825-158">混合实现 （号码驻留在直接路由） 将使用[新建 CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="cf825-158">Hybrid implementations (numbers homed on Direct Routing) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span></span>

<span data-ttu-id="cf825-159">应用程序 ID 需要创建的应用程序实例时使用：</span><span class="sxs-lookup"><span data-stu-id="cf825-159">The application ID's that you need to use while creating the application instances are:</span></span>
- <span data-ttu-id="cf825-160">**自动助理：** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="cf825-160">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="cf825-161">**呼叫队列：** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="cf825-161">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="cf825-162">如果您希望呼叫队列或自动助理可由内部用户，应创建您资源帐户内部，因为不向 Active Directory 同步联机资源帐户。</span><span class="sxs-lookup"><span data-stu-id="cf825-162">If you want the call queue or auto attendant to be searchable by on-premise users, you should create your resource accounts on-premise, since online resource accounts are not synced down to Active Directory.</span></span>

1. <span data-ttu-id="cf825-163">若要创建资源帐户为使用自动助理，使用与下面的命令。</span><span class="sxs-lookup"><span data-stu-id="cf825-163">To create a resource account online for use with an auto attendant, use the following command.</span></span>  

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. <span data-ttu-id="cf825-164">您将不能使用资源帐户，直到对其应用许可证。</span><span class="sxs-lookup"><span data-stu-id="cf825-164">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="cf825-165">有关如何将许可证应用于 O365 管理中心中的帐户，请参阅[分配对业务的 Office 365 中的用户的许可证](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user)以及[业务许可证分配 Skype](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)。</span><span class="sxs-lookup"><span data-stu-id="cf825-165">For how to apply a license to an account in the O365 admin center, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="cf825-166">（可选）一旦正确的许可证适用于资源帐户可以将电话号码设置为资源帐户，如下所示。</span><span class="sxs-lookup"><span data-stu-id="cf825-166">(Optional) Once the correct license is applied to the resource account you can  set a phone number to the resource account as shown below.</span></span> <span data-ttu-id="cf825-167">并非所有资源帐户将都需要一个电话号码。</span><span class="sxs-lookup"><span data-stu-id="cf825-167">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="cf825-168">如果您未对资源帐户应用许可证，将失败的电话号码分配。</span><span class="sxs-lookup"><span data-stu-id="cf825-168">If you did not apply a license to the resource account, the phone number assignment will fail.</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

<span data-ttu-id="cf825-169">在此命令的详细信息，请参阅[设置 CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="cf825-169">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="cf825-170">是最容易设置 online 的电话号码使用的 Microsoft 团队管理中心中，如前面所述。</span><span class="sxs-lookup"><span data-stu-id="cf825-170">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="cf825-171">管理资源的 Microsoft 团队管理中心中的帐户设置</span><span class="sxs-lookup"><span data-stu-id="cf825-171">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="cf825-172">若要管理资源帐户设置的 Microsoft 团队管理中心中，导航到**组织范围的设置**  > **资源帐户**和选择资源帐户所需更改设置，然后单击**编辑**按钮。</span><span class="sxs-lookup"><span data-stu-id="cf825-172">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="cf825-173">在**编辑资源帐户**屏幕中，您将能够更改这些设置：</span><span class="sxs-lookup"><span data-stu-id="cf825-173">in the **Edit resource account** screen, you will be able to change these settings:</span></span>

- <span data-ttu-id="cf825-174">该帐户的**显示名称**</span><span class="sxs-lookup"><span data-stu-id="cf825-174">**Display name** for the account</span></span>
- <span data-ttu-id="cf825-175">呼叫队列或自动助理使用的帐户</span><span class="sxs-lookup"><span data-stu-id="cf825-175">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="cf825-176">分配给该帐户的电话号码</span><span class="sxs-lookup"><span data-stu-id="cf825-176">Phone number assigned to the account</span></span>

<span data-ttu-id="cf825-177">完成后，单击在**保存**。</span><span class="sxs-lookup"><span data-stu-id="cf825-177">When finished, click on **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="cf825-178">删除资源帐户</span><span class="sxs-lookup"><span data-stu-id="cf825-178">Delete a resource account</span></span>

<span data-ttu-id="cf825-179">请确保删除它，以避免获取挂起的模式滞留在您服务号码之前中解除关联的电话号码从资源帐户。</span><span class="sxs-lookup"><span data-stu-id="cf825-179">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="cf825-180">您可以使用以下 commandlet:</span><span class="sxs-lookup"><span data-stu-id="cf825-180">You can do that using the following commandlet:</span></span> 

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```
                
<span data-ttu-id="cf825-181">一旦您这样做，可以从 O365 管理门户，用户选项卡中删除资源帐户。</span><span class="sxs-lookup"><span data-stu-id="cf825-181">Once you do that, you can delete the resource account from the O365 admin portal, under Users tab.</span></span>


## <a name="related-information"></a><span data-ttu-id="cf825-182">相关的信息</span><span class="sxs-lookup"><span data-stu-id="cf825-182">Related Information</span></span>

<span data-ttu-id="cf825-183">为实现的混合与 Skype 的业务服务器：</span><span class="sxs-lookup"><span data-stu-id="cf825-183">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="cf825-184">规划云自动助理</span><span class="sxs-lookup"><span data-stu-id="cf825-184">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="cf825-185">配置云自动助理</span><span class="sxs-lookup"><span data-stu-id="cf825-185">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="cf825-186">对于业务 online 团队或 Skype 中实现：</span><span class="sxs-lookup"><span data-stu-id="cf825-186">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="cf825-187">什么是云自动助理？</span><span class="sxs-lookup"><span data-stu-id="cf825-187">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="cf825-188">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="cf825-188">Set up a Cloud auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="cf825-189">小型企业示例 - 设置自动助理</span><span class="sxs-lookup"><span data-stu-id="cf825-189">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[<span data-ttu-id="cf825-190">创建云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="cf825-190">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="cf825-191">新 CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="cf825-191">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="cf825-192">新 CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="cf825-192">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
