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
ms.openlocfilehash: ad435a812191cc8f7b9061ac5fba2bbe626b908e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886058"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="7eccc-103">在 Microsoft Teams 中管理资源帐户</span><span class="sxs-lookup"><span data-stu-id="7eccc-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="7eccc-104">资源帐户也称为 Azure Active Directory 中的已禁用的用户对象，可以用于通常表示资源。</span><span class="sxs-lookup"><span data-stu-id="7eccc-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="7eccc-105">在 Exchange 它可能用于表示会议室，例如，并允许有一个电话号码。</span><span class="sxs-lookup"><span data-stu-id="7eccc-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="7eccc-106">在 Microsoft 365 或本地的企业服务器，使用 Skype 可托管资源帐户并使用 Powershell 命令创建这些帐户。</span><span class="sxs-lookup"><span data-stu-id="7eccc-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business server, and these accounts are created using Powershell commands.</span></span>

<span data-ttu-id="7eccc-107">在 Microsoft 团队或 Skype 业务联机，每个呼叫队列或自动助理需要具有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="7eccc-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="7eccc-108">资源帐户是否需要分配的电话号码将取决于打算使用的关联的呼叫队列或自动助理。</span><span class="sxs-lookup"><span data-stu-id="7eccc-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="7eccc-109">引用上调用队列的文章和自动助理电话号码分配给资源帐户之前底部这篇文章的链接。</span><span class="sxs-lookup"><span data-stu-id="7eccc-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="7eccc-110">本文同时适用于 Microsoft 团队和 Skype 业务 online。</span><span class="sxs-lookup"><span data-stu-id="7eccc-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a><span data-ttu-id="7eccc-111">若要将电话号码分配给资源帐户的先决条件</span><span class="sxs-lookup"><span data-stu-id="7eccc-111">Prerequisites to assign a phone number to a resource account</span></span>

<span data-ttu-id="7eccc-112">若要开始非常重要记住几件事：</span><span class="sxs-lookup"><span data-stu-id="7eccc-112">To get started it's important to remember a few things:</span></span>
  
- <span data-ttu-id="7eccc-113">您需要将电话系统许可证分配给与您的自动助理或呼叫队列关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="7eccc-113">You need to assign a Phone System license to a resource account that will be associated with your auto attendant or call queue.</span></span> <span data-ttu-id="7eccc-114">若要了解有关授权的详细信息，请参阅[Microsoft 团队加载项授权](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="7eccc-114">To learn more about licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    

    > [!NOTE]
    > <span data-ttu-id="7eccc-115">要重定向呼叫的人员在组织中联机，它们必须具有**电话系统**许可证和启用了企业语音或其 Office 365 调用计划。</span><span class="sxs-lookup"><span data-stu-id="7eccc-115">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="7eccc-116">请参阅[分配的 Microsoft 团队许可证](assign-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="7eccc-116">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="7eccc-117">要为他们启用企业语音，可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="7eccc-117">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="7eccc-118">例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="7eccc-118">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="7eccc-119">您可以直接路由混合数字分配资源帐户。</span><span class="sxs-lookup"><span data-stu-id="7eccc-119">You can assign a Direct Routing Hybrid number to your resource account.</span></span>  <span data-ttu-id="7eccc-120">有关详细信息，请参阅[规划直接路由](direct-routing-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="7eccc-120">See [Plan Direct Routing](direct-routing-plan.md) for details.</span></span>
- <span data-ttu-id="7eccc-121">对于 Microsoft 调用计划，您可以仅分配收费和免费电话服务电话号码的**Microsoft 团队管理中心**中获得或从另一个服务提供商转接到的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="7eccc-121">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to a resource account.</span></span> <span data-ttu-id="7eccc-122">若要获取并使用免费电话号码，则需要设置通信点数。</span><span class="sxs-lookup"><span data-stu-id="7eccc-122">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

> [!NOTE]
> <span data-ttu-id="7eccc-123">用户 （订阅服务器） 的电话号码不能分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="7eccc-123">User (subscriber) phone numbers can't be assigned to a resource account.</span></span> <span data-ttu-id="7eccc-124">可以使用只有服务收费电话或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="7eccc-124">Only service toll or toll-free phone numbers can be used.</span></span>

<span data-ttu-id="7eccc-125">若要将电话号码分配给资源帐户，您需要用于获取或转移您现有的收费电话或免费电话服务号码。</span><span class="sxs-lookup"><span data-stu-id="7eccc-125">To assign a phone number to a resource account, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="7eccc-126">获得收费电话或免费电话服务电话号码后，他们会显示在**Microsoft 团队管理中心** > **语音** > **电话号码**，以及被列为**Service-免费电话\*\*\*\*号码类型**列出将。</span><span class="sxs-lookup"><span data-stu-id="7eccc-126">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="7eccc-127">若要获取服务号码，请参阅[Getting 服务电话号码](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)或如果您想要传输的现有服务号码，请参阅[传输到 Office 365 的电话号码](transfer-phone-numbers-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="7eccc-127">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7eccc-128">如果您在美国以外，您无法使用的 Microsoft 团队管理中心获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="7eccc-128">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="7eccc-129">转到[管理您的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)而是以了解如何执行从美国的外部。</span><span class="sxs-lookup"><span data-stu-id="7eccc-129">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="7eccc-130">在 Powershell 中创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="7eccc-130">Create a resource account in Powershell</span></span>

 <span data-ttu-id="7eccc-131">您可以通过根据 （对于一个或多个资源帐户），需要运行相应 Powershell cmdlet 创建资源帐户，并为每个命名，依此类推。</span><span class="sxs-lookup"><span data-stu-id="7eccc-131">You would create a resource account by running the appropriate Powershell cmdlet as needed (for one or more resource accounts), and give each one a name and so on.</span></span> <span data-ttu-id="7eccc-132">当前没有在 Microsoft 团队管理中心中创建资源帐户的选项，但您可以编辑电话号码和更改的呼叫队列或自动助理分配资源帐户。</span><span class="sxs-lookup"><span data-stu-id="7eccc-132">There is currently no option for creating a resource account in the Microsoft Teams admin center, but you can edit phone numbers and change the call queue or auto attendant assignments for a resource account.</span></span>

<span data-ttu-id="7eccc-133">根据您的电话号码是否位于联机或本地，您需要连接到相应的 Powershell 提示符处，具有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="7eccc-133">Depending on whether your phone number is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="7eccc-134">混合实现 （号码号码驻留在直接路由、 OPCH 和 CCE） 将使用[新建 CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)创建驻留在本地资源帐户。</span><span class="sxs-lookup"><span data-stu-id="7eccc-134">Hybrid implementations (numbers numbers homed on Direct Routing, OPCH and CCE) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) to create a resource account that is homed on premises.</span></span>  
- <span data-ttu-id="7eccc-135">联机仅实现将使用[新建 CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps)具有联机驻留的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="7eccc-135">Online only implementations will use [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to have a resource account that is homed online.</span></span>

<span data-ttu-id="7eccc-136">以下是创建资源帐户的 online 环境示例：</span><span class="sxs-lookup"><span data-stu-id="7eccc-136">The following is an online environment example of creating a resource account:</span></span>

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
$resacct=Get-MsolUser -UserPrincipalName testra1@contoso.com
```

<span data-ttu-id="7eccc-137">在此命令的详细信息，请参阅[新建 CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="7eccc-137">See [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="7eccc-138">是最容易设置 online 的电话号码使用的 Microsoft 团队管理中心下, 一节中所述。</span><span class="sxs-lookup"><span data-stu-id="7eccc-138">It's easiest to set the online phone number using the Microsoft Teams admin center, as described in the next section.</span></span> <span data-ttu-id="7eccc-139">您还可以使用`Set-CsOnlineVoiceApplicationInstance`命令分配到的资源帐户电话号码其首次创建后所示：</span><span class="sxs-lookup"><span data-stu-id="7eccc-139">You can also use the `Set-CsOnlineVoiceApplicationInstance` command to a assign a phone number to the resource account after its initial creation as shown:</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity $resacct.ObjectId
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber 19294450177
```

<span data-ttu-id="7eccc-140">在此命令的详细信息，请参阅[设置 CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="7eccc-140">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="7eccc-141">管理资源的 Microsoft 团队管理中心中的帐户设置</span><span class="sxs-lookup"><span data-stu-id="7eccc-141">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="7eccc-142">若要管理资源帐户设置的 Microsoft 团队管理中心中，导航到**组织范围的设置**  > **资源帐户**和选择资源帐户所需更改设置，然后单击**编辑**按钮。</span><span class="sxs-lookup"><span data-stu-id="7eccc-142">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="7eccc-143">在**编辑资源帐户**屏幕中，您都将能够更改:</span><span class="sxs-lookup"><span data-stu-id="7eccc-143">in the **Edit resource account** screen, you will be able to change the:</span></span>

- <span data-ttu-id="7eccc-144">该帐户的**显示名称**</span><span class="sxs-lookup"><span data-stu-id="7eccc-144">**Display name** for the account</span></span>
- <span data-ttu-id="7eccc-145">呼叫队列或自动助理使用的帐户</span><span class="sxs-lookup"><span data-stu-id="7eccc-145">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="7eccc-146">分配给该帐户的电话号码</span><span class="sxs-lookup"><span data-stu-id="7eccc-146">Phone number assigned to the account</span></span>

<span data-ttu-id="7eccc-147">完成后，单击在**保存**。</span><span class="sxs-lookup"><span data-stu-id="7eccc-147">When finished, click on **Save**.</span></span>

## <a name="related-information"></a><span data-ttu-id="7eccc-148">相关的信息</span><span class="sxs-lookup"><span data-stu-id="7eccc-148">Related Information</span></span>

<span data-ttu-id="7eccc-149">为实现的混合与 Skype 的业务服务器：</span><span class="sxs-lookup"><span data-stu-id="7eccc-149">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="7eccc-150">规划云自动助理</span><span class="sxs-lookup"><span data-stu-id="7eccc-150">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="7eccc-151">配置云自动助理</span><span class="sxs-lookup"><span data-stu-id="7eccc-151">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="7eccc-152">对于业务 online 团队或 Skype 中实现：</span><span class="sxs-lookup"><span data-stu-id="7eccc-152">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="7eccc-153">什么是电话系统自动助理？</span><span class="sxs-lookup"><span data-stu-id="7eccc-153">What are Phone System auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="7eccc-154">设置电话系统自动助理</span><span class="sxs-lookup"><span data-stu-id="7eccc-154">Set up a Phone System auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="7eccc-155">小型企业示例 - 设置自动助理</span><span class="sxs-lookup"><span data-stu-id="7eccc-155">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[<span data-ttu-id="7eccc-156">创建电话系统呼叫队列</span><span class="sxs-lookup"><span data-stu-id="7eccc-156">Create a Phone System call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="7eccc-157">新 CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="7eccc-157">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="7eccc-158">新 CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="7eccc-158">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
