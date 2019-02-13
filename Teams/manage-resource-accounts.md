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
ms.collection: Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: 管理资源中的 Microsoft 团队的帐户
ms.openlocfilehash: 3bab9f4c76a7bc5b0baf534b17ca3f5abaf11478
ms.sourcegitcommit: 327fe807b461aff18b06449f06b9e51ce393c4bc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2019
ms.locfileid: "29964407"
---
# <a name="manage-resource-accounts-in-teams"></a><span data-ttu-id="8c236-103">管理团队中的资源帐户</span><span class="sxs-lookup"><span data-stu-id="8c236-103">Manage resource accounts in Teams</span></span> 

<span data-ttu-id="8c236-104">资源帐户也称为 Azure Active Directory 中的已禁用的用户对象，可以用于通常表示资源。</span><span class="sxs-lookup"><span data-stu-id="8c236-104">A Resource Account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="8c236-105">在 Exchange 它可能用于表示会议室，例如，并允许有一个电话号码。</span><span class="sxs-lookup"><span data-stu-id="8c236-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="8c236-106">在 Microsoft 365 或本地的企业服务器，使用 Skype 可托管资源帐户并使用 Powershell 命令创建这些帐户。</span><span class="sxs-lookup"><span data-stu-id="8c236-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business server, and these accounts are created using Powershell commands.</span></span>

<span data-ttu-id="8c236-107">在 Microsoft 团队 os Skype 业务联机，每个呼叫队列或自动助理需要具有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="8c236-107">In Microsoft Teams os Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="8c236-108">资源帐户是否需要分配的电话号码将取决于打算使用的关联的呼叫队列或自动助理。</span><span class="sxs-lookup"><span data-stu-id="8c236-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="8c236-109">引用上调用队列的文章和自动助理电话号码分配给资源帐户之前底部这篇文章的链接。</span><span class="sxs-lookup"><span data-stu-id="8c236-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a><span data-ttu-id="8c236-110">若要将电话号码分配给资源帐户的先决条件</span><span class="sxs-lookup"><span data-stu-id="8c236-110">Prerequisites to assign a phone number to a resource account</span></span>

<span data-ttu-id="8c236-111">若要开始非常重要记住几件事：</span><span class="sxs-lookup"><span data-stu-id="8c236-111">To get started it's important to remember a few things:</span></span>
  
- <span data-ttu-id="8c236-112">企业版 E3 以及**电话系统**的许可证或企业 E5 许可证，您的组织必须 （最低要求）。</span><span class="sxs-lookup"><span data-stu-id="8c236-112">Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license.</span></span> <span data-ttu-id="8c236-113">已分配的**电话系统**用户许可证数影响服务号码可用于资源帐户分配给队列或自动助理呼叫的号码。</span><span class="sxs-lookup"><span data-stu-id="8c236-113">The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for resource accounts assigned to call queues or auto attendants.</span></span> <span data-ttu-id="8c236-114">取决于您的组织中分配的**电话系统**和**音频会议**的许可证数量的资源帐户，您可以数。</span><span class="sxs-lookup"><span data-stu-id="8c236-114">The number of resource accounts you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization.</span></span> <span data-ttu-id="8c236-115">若要了解有关授权的详细信息，请参阅[业务和 Microsoft 团队授权加载项的 Skype](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)。</span><span class="sxs-lookup"><span data-stu-id="8c236-115">To learn more about licensing, see [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span></span>

    > [!NOTE]
    > <span data-ttu-id="8c236-116">要重定向呼叫的人员在组织中联机，它们必须具有**电话系统**许可证和启用了企业语音或其 Office 365 调用计划。</span><span class="sxs-lookup"><span data-stu-id="8c236-116">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="8c236-117">请参阅[业务和 Microsoft 团队许可证分配 Skype](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="8c236-117">See [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> <span data-ttu-id="8c236-118">要为他们启用企业语音，可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="8c236-118">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="8c236-119">例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="8c236-119">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="8c236-120">若要了解有关 Office 365 通话套餐的详细信息，请参阅 [Office 365 中有哪些通话套餐？](/microsoftteams/what-are-calling-plans-in-office-365) 和 [Office 365 的通话套餐](/microsoftteams/calling-plans-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="8c236-120">To learn more about Office 365 Calling Plans, see [What are Calling Plans in Office 365?](/microsoftteams/what-are-calling-plans-in-office-365) and [Calling Plans for Office 365](/microsoftteams/calling-plans-for-office-365).</span></span>
- <span data-ttu-id="8c236-121">您可以仅分配收费和免费电话服务电话号码的**Microsoft 团队管理中心**中获得或从另一个服务提供商转接到的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="8c236-121">You can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to a resource account.</span></span> <span data-ttu-id="8c236-122">若要获取并使用免费电话号码，则需要设置通信点数。</span><span class="sxs-lookup"><span data-stu-id="8c236-122">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

> [!NOTE]
> <span data-ttu-id="8c236-123">用户 （订阅服务器） 的电话号码不能分配给资源帐户-可以使用仅服务收费电话或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="8c236-123">User (subscriber) phone numbers can't be assigned to a resource account - only service toll or toll-free phone numbers can be used.</span></span>

<span data-ttu-id="8c236-124">若要将电话号码分配给资源帐户，您需要用于获取或转移您现有的收费电话或免费电话服务号码。</span><span class="sxs-lookup"><span data-stu-id="8c236-124">To assign a phone number to a resource account, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="8c236-125">获得收费电话或免费电话服务电话号码后，他们会显示在**Microsoft 团队管理中心** > **语音** > **电话号码**，以及被列为**Service-免费电话\*\*\*\*号码类型**列出将。</span><span class="sxs-lookup"><span data-stu-id="8c236-125">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="8c236-126">若要获取服务号码，请参阅[Getting 服务电话号码](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md)或如果您希望进行传输和现有服务号码，请参阅[传输到 Office 365 的电话号码](/microsoftteams/transfer-phone-numbers-to-office-365)。</span><span class="sxs-lookup"><span data-stu-id="8c236-126">To get your service numbers, see [Getting service phone numbers](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8c236-127">如果您在美国以外，您无法使用的 Microsoft 团队管理中心获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="8c236-127">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="8c236-128">转到[管理您的组织的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization)而是以了解如何执行从美国的外部。</span><span class="sxs-lookup"><span data-stu-id="8c236-128">Go to [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="8c236-129">在 Powershell 中创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="8c236-129">Create a resource account in Powershell</span></span>

 <span data-ttu-id="8c236-130">您可以通过根据 （对于一个或多个资源帐户），需要运行相应 Powershell cmdlet 创建资源帐户，并为每个命名，依此类推。</span><span class="sxs-lookup"><span data-stu-id="8c236-130">You would create a resource account by running the appropriate Powershell cmdlet as needed (for one or more resource accounts), and give each one a name and so on.</span></span> <span data-ttu-id="8c236-131">当前没有在 Microsoft 团队管理中心中创建资源帐户的选项，但您可以编辑电话号码和更改的呼叫队列或自动助理分配资源帐户。</span><span class="sxs-lookup"><span data-stu-id="8c236-131">There is currently no option for creating a resource account in the Microsoft Teams admin center, but you can edit phone numbers and change the call queue or auto attendant assignments for a resource account.</span></span>

<span data-ttu-id="8c236-132">根据您的电话号码是否位于联机或本地，您需要连接到相应的 Powershell 提示符处，具有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="8c236-132">Depending on whether your phone number is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="8c236-133">混合实现 （号码号码驻留在直接路由、 OPCH 和 CCE） 将使用[新建 CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)创建驻留在本地资源帐户。</span><span class="sxs-lookup"><span data-stu-id="8c236-133">Hybrid implementations (numbers numbers homed on Direct Routing, OPCH and CCE) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) to create a resource account that is homed on premises.</span></span>  
- <span data-ttu-id="8c236-134">联机仅实现将使用[新建 CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps)具有联机驻留的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="8c236-134">Online only implementations will use [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to have a resource account that is homed online.</span></span>

<span data-ttu-id="8c236-135">以下是创建资源帐户的 online 环境示例：</span><span class="sxs-lookup"><span data-stu-id="8c236-135">The following is an online environment example of creating a resource account:</span></span>

``` Powershell
New-CsOnlineApplicationInstance -DisplayName Node1 -SipAddress sip:node1@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
```

<span data-ttu-id="8c236-136">在此命令的详细信息，请参阅[新建 CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="8c236-136">See [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="8c236-137">是最容易设置电话号码使用的 Microsoft 团队管理中心下, 一节中所述。</span><span class="sxs-lookup"><span data-stu-id="8c236-137">It's easiest to set the phone number using the Microsoft Teams admin center, as described in the next section.</span></span> <span data-ttu-id="8c236-138">您还可以使用`Set-CsOnlineApplicationInstance`命令分配到的资源帐户电话号码其首次创建后所示：</span><span class="sxs-lookup"><span data-stu-id="8c236-138">You can also use the `Set-CsOnlineApplicationInstance` command to a assign a phone number to the resource account after its initial creation as shown:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity "CN={4f6c99fe-7999-4088-ac4d-e88e0b3d3820},OU=Redmond,DC=litwareinc,DC=com" -DisplayName Node1 -LineURI tel:+14255550100
```

<span data-ttu-id="8c236-139">在此命令的详细信息，请参阅[设置 CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlineapplicationinstance?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="8c236-139">See [Set-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlineapplicationinstance?view=skype-ps) for more details on this command.</span></span>

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="8c236-140">管理资源的 Microsoft 团队管理中心中的帐户设置</span><span class="sxs-lookup"><span data-stu-id="8c236-140">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="8c236-141">若要管理资源帐户设置的 Microsoft 团队管理中心中，导航到**组织范围的设置**  > **资源帐户**和选择资源帐户所需更改设置，然后单击**编辑**按钮。</span><span class="sxs-lookup"><span data-stu-id="8c236-141">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="8c236-142">在**编辑资源帐户**屏幕中，您都将能够更改:</span><span class="sxs-lookup"><span data-stu-id="8c236-142">in the **Edit resource account** screen, you will be able to change the:</span></span>

- <span data-ttu-id="8c236-143">该帐户的**显示名称**</span><span class="sxs-lookup"><span data-stu-id="8c236-143">**Display name** for the account</span></span>
- <span data-ttu-id="8c236-144">呼叫队列或自动助理使用的帐户</span><span class="sxs-lookup"><span data-stu-id="8c236-144">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="8c236-145">分配给该帐户的电话号码</span><span class="sxs-lookup"><span data-stu-id="8c236-145">Phone number assigned to the account</span></span>

<span data-ttu-id="8c236-146">完成后，单击在**保存**。</span><span class="sxs-lookup"><span data-stu-id="8c236-146">When finished, click on **Save**.</span></span>

## <a name="related-information"></a><span data-ttu-id="8c236-147">相关的信息</span><span class="sxs-lookup"><span data-stu-id="8c236-147">Related Information</span></span>

<span data-ttu-id="8c236-148">为实现的混合与 Skype 的业务服务器：</span><span class="sxs-lookup"><span data-stu-id="8c236-148">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="8c236-149">规划云自动助理</span><span class="sxs-lookup"><span data-stu-id="8c236-149">Plan Cloud auto attendant</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="8c236-150">配置云自动助理</span><span class="sxs-lookup"><span data-stu-id="8c236-150">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="8c236-151">对于业务 online 团队或 Skype 中实现：</span><span class="sxs-lookup"><span data-stu-id="8c236-151">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="8c236-152">什么是电话系统自动助理？</span><span class="sxs-lookup"><span data-stu-id="8c236-152">What are Phone System auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="8c236-153">设置电话系统自动助理</span><span class="sxs-lookup"><span data-stu-id="8c236-153">Set up a Phone System auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="8c236-154">小型企业示例-设置的自动助理</span><span class="sxs-lookup"><span data-stu-id="8c236-154">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[<span data-ttu-id="8c236-155">创建电话系统呼叫队列</span><span class="sxs-lookup"><span data-stu-id="8c236-155">Create a Phone System call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="8c236-156">新 CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="8c236-156">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="8c236-157">新 CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="8c236-157">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
