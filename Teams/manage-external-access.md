---
title: 在 Microsoft Teams 中管理外部访问权限（联合身份验证）
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.externalaccess.overview
description: 你的团队或 IT 管理员可以为其他域（联盟）配置外部访问，以使来自这些域的用户参与团队。
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: e6eb1cab6503c443d3fb312769f9f1e0255c294a
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925043"
---
<a name="manage-external-access-in-microsoft-teams"></a><span data-ttu-id="32e44-103">管理 Microsoft 团队中的外部访问</span><span class="sxs-lookup"><span data-stu-id="32e44-103">Manage external access in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="32e44-104">外部访问是来自整个域的外部团队用户在团队中查找、呼叫、聊天和设置会议的一种方式。</span><span class="sxs-lookup"><span data-stu-id="32e44-104">External access is a way for external Teams users from an entire domain to find, call, chat, and set up meetings with you in Teams.</span></span> <span data-ttu-id="32e44-105">您也可以使用外部访问与仍在使用 Skype for Business （联机和本地）和 Skype （即将在2020中推出）的外部用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="32e44-105">You can also use external access to communicate with external users who are still using Skype for Business (online and on premises) and Skype (coming in early 2020).</span></span>

<span data-ttu-id="32e44-106">如果希望外部用户拥有访问团队和频道的权限，则选择使用来宾访问可能是更好的方法。</span><span class="sxs-lookup"><span data-stu-id="32e44-106">If you want external users to have access to teams and channels, guest access might be a better way to go.</span></span> <span data-ttu-id="32e44-107">有关外部访问和来宾访问之间的差异的详细信息，请参阅[比较外部访问和来宾访问](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。</span><span class="sxs-lookup"><span data-stu-id="32e44-107">For more information about the differences between external access and guest access, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span> 

<span data-ttu-id="32e44-108">在以下情况中使用外部访问：</span><span class="sxs-lookup"><span data-stu-id="32e44-108">Use external access when:</span></span>
  
- <span data-ttu-id="32e44-109">您在不同的域中拥有需要协作的用户。</span><span class="sxs-lookup"><span data-stu-id="32e44-109">You have users in different domains who need to collaborate.</span></span> <span data-ttu-id="32e44-110">例如，Rob@contoso.com 和 Ann@northwindtraders.com 正在与 contoso.com 和 northwindtraders.com 域中的其他人一起处理项目。</span><span class="sxs-lookup"><span data-stu-id="32e44-110">For example, Rob@contoso.com and Ann@northwindtraders.com are working on a project together along with some others in the contoso.com and northwindtraders.com domains.</span></span>

- <span data-ttu-id="32e44-111">您希望组织中的人员可以使用团队与组织外部的特定企业中的人员联系。</span><span class="sxs-lookup"><span data-stu-id="32e44-111">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>

- <span data-ttu-id="32e44-112">您希望世界上任何其他使用团队的人都能够使用您的电子邮件地址查找和与您联系。</span><span class="sxs-lookup"><span data-stu-id="32e44-112">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> 




> [!IMPORTANT]
> <span data-ttu-id="32e44-113">当前，若要将 Microsoft 团队应用内的外部用户联合到你的组织外部的外部用户（当前不是 Azure Active Directory （Azure AD）或租户的来宾），你必须为混合正确设置，并将其移动到 Skype for business Online。</span><span class="sxs-lookup"><span data-stu-id="32e44-113">Currently, to federate within the Microsoft Teams app to an external user outside of your organization who's not currently a guest of your Azure Active Directory (Azure AD) or tenant, you must be correctly set up for hybrid and moved to Skype for Business Online.</span></span> <span data-ttu-id="32e44-114">从2019年2月25日起，团队不支持不带 SIP 档案用户在 Skype for business Online 中托管的本机联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="32e44-114">As of February 25, 2019, Teams doesn't support native federation without the user of the SIP profile being homed in Skype for Business Online.</span></span> <span data-ttu-id="32e44-115">有关设置混合帐户和迁移到团队的详细信息，请参阅将[Skype For business 混合部署升级到团队](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid)。</span><span class="sxs-lookup"><span data-stu-id="32e44-115">For more on setting up your account for hybrid and then moving to Teams, see [Upgrade Skype for Business hybrid deployment to Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).</span></span>






## <a name="plan-for-external-access"></a><span data-ttu-id="32e44-116">规划外部访问</span><span class="sxs-lookup"><span data-stu-id="32e44-116">Plan for external access</span></span>

<span data-ttu-id="32e44-117">默认情况下，在团队中启用外部访问，这意味着你的组织可以与所有外部域通信。</span><span class="sxs-lookup"><span data-stu-id="32e44-117">By default, external access is turned on in Teams, which means that your organization can communicate with all external domains.</span></span> <span data-ttu-id="32e44-118">如果添加被阻止的域，则允许所有其他域;如果您添加允许的域，所有其他域都将被阻止。</span><span class="sxs-lookup"><span data-stu-id="32e44-118">If you add blocked domains, all other domains will be allowed; and if you add allowed domains, all other domains will be blocked.</span></span> <span data-ttu-id="32e44-119">在团队管理中心中设置外部访问有三种方案（**组织范围设置** > **外部访问**）：</span><span class="sxs-lookup"><span data-stu-id="32e44-119">There are three scenarios for setting up external access in the Teams admin center (**Org-wide settings** > **External access**):</span></span>

- <span data-ttu-id="32e44-120">**打开联盟**：这是团队中的默认设置，可让你的组织中的人员查找、呼叫、聊天和设置与你的组织外部的人员在任何域中的会议。</span><span class="sxs-lookup"><span data-stu-id="32e44-120">**Open federation**: This is the default setting in Teams, and it lets people in your organization find, call, chat, and set up meetings with people external to your organization in any domain.</span></span>

    <span data-ttu-id="32e44-121">在此方案中，你的用户可以与运行团队或 Skype for business 的所有外部域进行通信，并且使用开放联盟或已将你的域添加到其允许列表。</span><span class="sxs-lookup"><span data-stu-id="32e44-121">In this scenario, your users can communicate with all external domains that are running Teams or Skype for Business AND are using open federation OR have added your domain to their allow list.</span></span>

- <span data-ttu-id="32e44-122">**允许特定域**：通过将域添加到 "**允许**" 列表，你可以将外部访问限制为仅允许的域。</span><span class="sxs-lookup"><span data-stu-id="32e44-122">**Allow specific domains**: By adding domains to an **Allow** list, you limit external access to only the allowed domains.</span></span> <span data-ttu-id="32e44-123">设置允许域的列表后，所有其他域都将被阻止。</span><span class="sxs-lookup"><span data-stu-id="32e44-123">Once you set up a list of allowed domains, all other domains will be blocked.</span></span> <span data-ttu-id="32e44-124">若要允许特定域，请单击 "**添加域**"，添加域名，单击 "**操作" 以在此域上执行操作**，然后选择 "**允许**"。</span><span class="sxs-lookup"><span data-stu-id="32e44-124">To allow specific domains, click **Add a domain**, add the domain name, click **Action to take on this domain**, and then select **Allowed**.</span></span>

- <span data-ttu-id="32e44-125">**阻止特定域**-通过将域添加到**阻止**列表，您可以与除已阻止的外部域*之外*的所有外部域进行通信。</span><span class="sxs-lookup"><span data-stu-id="32e44-125">**Block specific domains** - By adding domains to a **Block** list, you can communicate with all external domains *except* the ones you've blocked.</span></span> <span data-ttu-id="32e44-126">若要阻止特定域，请单击 "**添加域**"，添加域名，单击 "**操作" 以在此域上执行操作**，然后选择 "**阻止**"。</span><span class="sxs-lookup"><span data-stu-id="32e44-126">To block specific domains, click **Add a domain**, add the domain name, click **Action to take on this domain**, and then select **Blocked**.</span></span> <span data-ttu-id="32e44-127">设置被阻止域的列表后，将允许所有其他域。</span><span class="sxs-lookup"><span data-stu-id="32e44-127">Once you set up a list of blocked domains, all other domains will be allowed.</span></span>

## <a name="allow-or-block-domains"></a><span data-ttu-id="32e44-128">允许或阻止域</span><span class="sxs-lookup"><span data-stu-id="32e44-128">Allow or block domains</span></span>

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-organization"></a><span data-ttu-id="32e44-129">步骤 1-使你的组织能够与另一个团队组织通信</span><span class="sxs-lookup"><span data-stu-id="32e44-129">Step 1 - Enable your organization to communicate with another Teams organization</span></span>

<span data-ttu-id="32e44-130">![](media/teams-logo-30x30.png)**使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标  </span><span class="sxs-lookup"><span data-stu-id="32e44-130">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png)  **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="32e44-131">在左侧导航中，转到 "**组织范围的设置** > **外部访问**"。</span><span class="sxs-lookup"><span data-stu-id="32e44-131">In the left navigation, go to **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="32e44-132">切换**用户可以与 Skype For business 和团队用户进行通信，** 切换到 **"打开"**。</span><span class="sxs-lookup"><span data-stu-id="32e44-132">Toggle the **Users can communicate with Skype for Business and Teams users** switch to **On**.</span></span>

     ![打开了外部访问切换器的屏幕截图](media/manage-external-access-2.png)<span data-ttu-id="32e44-134">.</span><span class="sxs-lookup"><span data-stu-id="32e44-134"></span></span>

3. <span data-ttu-id="32e44-135">如果你希望允许所有团队组织与你的组织中的用户进行通信，请跳至步骤5。</span><span class="sxs-lookup"><span data-stu-id="32e44-135">If you want to allow all Teams organizations to communicate with users in your organization, skip to step 5.</span></span>

4. <span data-ttu-id="32e44-136">如果你想要限制可与组织中的用户进行通信的组织，你可以允许除某些域之外的所有域，或者你只能允许特定的域。</span><span class="sxs-lookup"><span data-stu-id="32e44-136">If you want to limit the organizations that can communicate with users in your organization, you can either allow all except some domains, or you can allow only specific domains.</span></span> 

    - <span data-ttu-id="32e44-137">若要允许除某些域之外的所有域，请单击 "**添加域**" 以添加要阻止的域。</span><span class="sxs-lookup"><span data-stu-id="32e44-137">To allow all except some domains, add the domains you want to block by clicking **Add domain**.</span></span> <span data-ttu-id="32e44-138">在 "**添加域**" 窗格中，键入域名，单击 "已**阻止**"，然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="32e44-138">In the **Add a domain** pane, type the domain name, click **Blocked**, and then click **Done**.</span></span> 
    - <span data-ttu-id="32e44-139">若要限制特定组织的通信，请将这些域添加到状态为 "**允许**" 的列表中。</span><span class="sxs-lookup"><span data-stu-id="32e44-139">To limit communications to specific organizations, add those domains to the list with a status of **Allowed**.</span></span> <span data-ttu-id="32e44-140">将任何域添加到 "允许" 列表后，与其他组织的通信将仅限于其域位于 "允许" 列表中的组织。</span><span class="sxs-lookup"><span data-stu-id="32e44-140">Once you have added any domain to the Allow list, communications with other organizations will be limited to only those organizations whose domains are in the Allow list.</span></span> 

5. <span data-ttu-id="32e44-141">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="32e44-141">Click **Save**.</span></span>

6. <span data-ttu-id="32e44-142">请确保其他团队组织中的管理员完成这些相同步骤。</span><span class="sxs-lookup"><span data-stu-id="32e44-142">Make sure the admin in the other Teams organization completes these same steps.</span></span> <span data-ttu-id="32e44-143">例如，在 "**允许的域**" 列表中，他们的管理员需要为您的企业输入域，前提是他们限制了可以与他们的用户进行通信的组织。</span><span class="sxs-lookup"><span data-stu-id="32e44-143">For example, in their **allowed domains** list, their admin needs to enter the domain for your business if they limit the organizations that can communicate with their users.</span></span>

### <a name="step-2---test-it"></a><span data-ttu-id="32e44-144">步骤 2-测试</span><span class="sxs-lookup"><span data-stu-id="32e44-144">Step 2 - Test it</span></span>

<span data-ttu-id="32e44-145">若要测试你的设置，你需要一个不在防火墙后面的团队用户。</span><span class="sxs-lookup"><span data-stu-id="32e44-145">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
1. <span data-ttu-id="32e44-146">当您和组织的管理员更改了**外部访问**设置后，您应该可以继续。</span><span class="sxs-lookup"><span data-stu-id="32e44-146">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>

2. <span data-ttu-id="32e44-147">在 "团队" 应用中，按电子邮件地址搜索人员，然后发送聊天请求。</span><span class="sxs-lookup"><span data-stu-id="32e44-147">In the Teams app, search for the person by email address, and send a request to chat.</span></span>

3. <span data-ttu-id="32e44-148">让您的团队联系人向您发送聊天请求。</span><span class="sxs-lookup"><span data-stu-id="32e44-148">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="32e44-149">如果你未收到其请求，那么你的防火墙有问题（假设他们已确认其防火墙设置正确）。</span><span class="sxs-lookup"><span data-stu-id="32e44-149">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>

4. <span data-ttu-id="32e44-150">测试问题是否是你的防火墙的另一种方法是转到不在防火墙后面的 WiFi 位置。</span><span class="sxs-lookup"><span data-stu-id="32e44-150">Another way to test whether the problem is your firewall is to go to a WiFi location not behind your firewall.</span></span> <span data-ttu-id="32e44-151">例如咖啡店，使用团队将请求发送给您的联系人进行聊天。</span><span class="sxs-lookup"><span data-stu-id="32e44-151">such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="32e44-152">如果邮件通过 WiFi 位置，但未在工作，则您知道问题是您的防火墙。</span><span class="sxs-lookup"><span data-stu-id="32e44-152">If the message goes through at the WiFi location, but does not when you're at work, then you know the problem is your firewall.</span></span>

> [!NOTE]
> <span data-ttu-id="32e44-153">如果您和其他用户都启用了外部访问并允许另一个用户的域，这将起作用。</span><span class="sxs-lookup"><span data-stu-id="32e44-153">If you and another user both turn on external access and allow one another's domains, this will work.</span></span> <span data-ttu-id="32e44-154">如果不起作用，则其他用户应确保其配置未阻止您的域。</span><span class="sxs-lookup"><span data-stu-id="32e44-154">If it doesn't work, the other user should make sure their configuration isn't blocking your domain.</span></span>

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a><span data-ttu-id="32e44-155">与 Skype for Business Online 组织中的用户进行通信</span><span class="sxs-lookup"><span data-stu-id="32e44-155">Communicate with users in a Skype for Business Online organization</span></span>

<span data-ttu-id="32e44-156">如果你要设置外部访问权限，以便你的团队用户在 Skype for Business 组织中查找和联系用户以限制谁可以联系他们的用户，请按照以下步骤设置从你的域到其他组织的域的外部访问。</span><span class="sxs-lookup"><span data-stu-id="32e44-156">If you're setting up external access to let your Teams users find and contact users in a Skype for Business organization that limits who can contact their users, follow the steps to set up external access from your domain to the other organization's domain.</span></span> <span data-ttu-id="32e44-157">然后，让其他组织中的管理员按照以下步骤配置 Skype for business Online 的外部访问。</span><span class="sxs-lookup"><span data-stu-id="32e44-157">Then ask the admin in the other organization to follow the steps below to configure external access for Skype for Business Online.</span></span> 

<span data-ttu-id="32e44-158">有关常见 Skype for Business Online 方案的特定指导，请参阅下面的[常见外部访问方案](#common-external-access-scenarios)。</span><span class="sxs-lookup"><span data-stu-id="32e44-158">For specific guidance on common Skype for Business Online scenarios, see [Common external access scenarios](#common-external-access-scenarios) below.</span></span>

<span data-ttu-id="32e44-159">![](media/sfb-logo-30x30.png) **使用 skype for business 管理中心**显示 skype for business 徽标的图标</span><span class="sxs-lookup"><span data-stu-id="32e44-159">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="32e44-160">让该组织中的管理员执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="32e44-160">Have the admin in that organization do these steps:</span></span>

1. <span data-ttu-id="32e44-161">在 Microsoft 365 管理中心，转到 "**管理中心** > "**团队 & Skype** > **旧版门户**。</span><span class="sxs-lookup"><span data-stu-id="32e44-161">In the Microsoft 365 admin center, go to **Admin Centers** > **Teams & Skype** > **Legacy portal**.</span></span>
  
2. <span data-ttu-id="32e44-162">在 **Skype for Business 管理中心**，选择“**组织**” > “**外部通信**”。</span><span class="sxs-lookup"><span data-stu-id="32e44-162">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>

3. <span data-ttu-id="32e44-163">若要设置与特定企业或与其他域中的用户的通信，请在下拉框中选择 **"仅针对允许的域"**。</span><span class="sxs-lookup"><span data-stu-id="32e44-163">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>

    <span data-ttu-id="32e44-164">或者，如果他们想要与世界上的所有其他人（具有打开的 Skype for Business 策略）进行通信，请选择 **"开" （阻止的域除外**）。</span><span class="sxs-lookup"><span data-stu-id="32e44-164">OR, if they want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="32e44-165">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="32e44-165">This is the default setting.</span></span>

4. <span data-ttu-id="32e44-166">在 "已**阻止或允许**的**+** 域" 下，选择，然后添加要允许的域的名称。</span><span class="sxs-lookup"><span data-stu-id="32e44-166">Under **Blocked or allowed domains**, choose **+**, and then add the name of the domain you want to allow.</span></span>

## <a name="common-external-access-scenarios"></a><span data-ttu-id="32e44-167">常见的外部访问方案</span><span class="sxs-lookup"><span data-stu-id="32e44-167">Common external access scenarios</span></span>

|<span data-ttu-id="32e44-168">**如果需要 .。。**</span><span class="sxs-lookup"><span data-stu-id="32e44-168">**If you want to....**</span></span>  |<span data-ttu-id="32e44-169">**执行此操作**</span><span class="sxs-lookup"><span data-stu-id="32e44-169">**Do this**</span></span>  |
|---------|-----------------------|
|<span data-ttu-id="32e44-170">让你的组织中的**团队用户**与另一个（外部）组织中的**团队用户**通信。</span><span class="sxs-lookup"><span data-stu-id="32e44-170">Let **Teams users** in your organization communicate with **Teams users** in another (external) organization.</span></span>|<span data-ttu-id="32e44-171">在 "外部访问" 中，将外部域添加到 "允许列表" 或 "使用开放联盟"。</span><span class="sxs-lookup"><span data-stu-id="32e44-171">In External Access, add the external domain to the Allowed list or use open federation.</span></span> <span data-ttu-id="32e44-172">然后让其他团队组织中的管理员执行相同操作。</span><span class="sxs-lookup"><span data-stu-id="32e44-172">Then have the administrator in the other Teams organization do the same thing.</span></span>      |
|<span data-ttu-id="32e44-173">让你的组织中的**团队用户**与同一组织中的**Skype for business Online 用户**通信。</span><span class="sxs-lookup"><span data-stu-id="32e44-173">Let **Teams users**  in your organization  communicate with **Skype for Business Online users**  in the same organization.</span></span>  |<span data-ttu-id="32e44-174">启用共存模式或选择 "孤岛" 升级模式以支持组织中的 Skype for business 用户。</span><span class="sxs-lookup"><span data-stu-id="32e44-174">Enable Coexistence mode or choose the Islands upgrade mode to support Skype for Business users in your organization.</span></span>   |
|<span data-ttu-id="32e44-175">让你的组织中的**团队用户**与另一个（外部）组织中的**Skype for business Online 用户**通信。</span><span class="sxs-lookup"><span data-stu-id="32e44-175">Let **Teams users** in your organization communicate with **Skype for Business Online users** in another (external) organization.</span></span>      |<span data-ttu-id="32e44-176">在 "外部访问" 中，将外部域添加到 "允许列表" 或 "使用开放联盟"。</span><span class="sxs-lookup"><span data-stu-id="32e44-176">In External Access, add the external domain to the Allowed list or use open federation.</span></span> <br><br><span data-ttu-id="32e44-177">打开**用户可与 Skype For business 和团队用户进行通信**在外部访问中设置。</span><span class="sxs-lookup"><span data-stu-id="32e44-177">Turn on **Users can communicate with Skype for Business and Teams users** setting in External Access.</span></span> <span data-ttu-id="32e44-178">然后让其他团队组织中的管理员执行相同操作。</span><span class="sxs-lookup"><span data-stu-id="32e44-178">Then have the administrator in the other Teams organization do the same thing.</span></span> <br><br><span data-ttu-id="32e44-179">**注意**：具有 Skype for business 用户的外部域必须启用共存模式，或者选择 "孤岛" 升级模式以支持该组织中的 Skype for business 用户。</span><span class="sxs-lookup"><span data-stu-id="32e44-179">**NOTE**: The external domain with Skype for Business users must enable Coexistence mode or choose the Islands upgrade mode to support Skype for Business users in that organization.</span></span>|
|<span data-ttu-id="32e44-180">让你的组织中的**团队用户**与你的组织内部或外部的**Skype**用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="32e44-180">Let **Teams users** in your organization  communicate with **Skype** users from inside or outside your organization.</span></span>   | <span data-ttu-id="32e44-181">此方案即将推出。</span><span class="sxs-lookup"><span data-stu-id="32e44-181">This scenario is coming soon.</span></span> <br><br><span data-ttu-id="32e44-182">**重要提示**：你的团队用户无法与 Skype 用户进行通信，但你的 Skype for business 用户可以继续与组织内部或外部的 skype 用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="32e44-182">**IMPORTANT**: Your Teams users are not able to communicate with Skype users yet, but your Skype for Business users can continue to communicate with Skype users inside or outside your organization.</span></span> <span data-ttu-id="32e44-183">打开**用户可与 skype For business 和团队用户通信**，并且**skype for business 用户可以与外部 Access 中的 skype 用户进行通信**。</span><span class="sxs-lookup"><span data-stu-id="32e44-183">Turn on the  **Users can communicate with Skype for Business and Teams users** and **Skype for Business users can communicate with Skype users** settings in External Access.</span></span> |
|<span data-ttu-id="32e44-184">让**Skype For Business Online 用户**与其他 Office 365 组织中的**团队用户**通信。</span><span class="sxs-lookup"><span data-stu-id="32e44-184">Let your **Skype for Business Online users** communicate with **Teams users** in another Office 365 organization.</span></span>| <span data-ttu-id="32e44-185">如果你的用户处于以下升级模式之一，则你的 Skype for Business Online 用户可以与其他组织中的团队用户进行通信： SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings;其他组织的团队用户处于 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="32e44-185">Your Skype for Business Online users can communicate with Teams users in another organization if your users are in one of the following upgrade modes: Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings; and the other organization's Teams users are in TeamsOnly mode.</span></span> <br><br><span data-ttu-id="32e44-186">打开**用户可与 Skype For business 和团队用户进行通信**在外部访问中设置。</span><span class="sxs-lookup"><span data-stu-id="32e44-186">Turn on the **Users can communicate with Skype for Business and Teams users** setting in External Access.</span></span> <span data-ttu-id="32e44-187">然后让其他团队组织中的管理员执行相同操作。</span><span class="sxs-lookup"><span data-stu-id="32e44-187">Then have the administrator in the other Teams organization do the same things.</span></span>|
|<span data-ttu-id="32e44-188">让**skype For Business online 用户**与其他 Office 365 组织中的**Skype for business online 用户**通信。</span><span class="sxs-lookup"><span data-stu-id="32e44-188">Let your **Skype for Business Online users** communicate with **Skype for Business Online users** from another Office 365 organization.</span></span>    | <span data-ttu-id="32e44-189">如果你的用户处于以下升级模式之一，则你的 Skype for Business Online 用户可以与其他组织中的 Skype for business Online 用户通信： SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings;其他组织的 Skype for Business Online 用户处于以下升级模式之一： SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings。</span><span class="sxs-lookup"><span data-stu-id="32e44-189">Your Skype for Business Online users can communicate with Skype for Business Online users in another organization if your users are in one of the following upgrade modes: Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings; and the other organization's Skype for Business Online users are in one of the following upgrade modes: Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings.</span></span><br><br><span data-ttu-id="32e44-190">打开**用户可与 Skype For business 和团队用户进行通信**在外部访问中设置。</span><span class="sxs-lookup"><span data-stu-id="32e44-190">Turn on the **Users can communicate with Skype for Business and Teams users** setting in External Access.</span></span> <span data-ttu-id="32e44-191">然后让其他团队组织中的管理员执行相同操作。</span><span class="sxs-lookup"><span data-stu-id="32e44-191">Then have the administrator in the other Teams organization do the same things.</span></span>|
|<span data-ttu-id="32e44-192">让**skype For Business Online 用户**与本地组织中的**skype for business 用户**进行通信。</span><span class="sxs-lookup"><span data-stu-id="32e44-192">Let your **Skype for Business Online users** communicate with **Skype for Business users** from an on-premises organization.</span></span>     |<span data-ttu-id="32e44-193">如果你的用户处于以下升级模式之一，则你的 Skype for Business Online 用户可以与本地组织中的 Skype for business 用户进行通信： SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings;其他组织的 Skype for Business Online 用户处于以下升级模式之一： SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings。</span><span class="sxs-lookup"><span data-stu-id="32e44-193">Your Skype for Business Online users can communicate with Skype for Business users from an on-premises organization if your users are in one of the following upgrade modes: Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings; and the other organization's Skype for Business Online users are in one of the following upgrade modes: Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings.</span></span><br><br><span data-ttu-id="32e44-194">打开**用户可与 Skype For business 和团队用户进行通信**在外部访问中设置。</span><span class="sxs-lookup"><span data-stu-id="32e44-194">Turn on the **Users can communicate with Skype for Business and Teams users** setting in External Access.</span></span> <span data-ttu-id="32e44-195">然后让其他团队组织中的管理员执行相同操作。</span><span class="sxs-lookup"><span data-stu-id="32e44-195">Then have the administrator in the other Teams organization do the same things.</span></span>|
|<span data-ttu-id="32e44-196">让**skype For Business Online 用户**与**skype 用户**通信（在您的组织内部或外部）。</span><span class="sxs-lookup"><span data-stu-id="32e44-196">Let your **Skype for Business Online users** communicate with **Skype users** (inside or outside your organization).</span></span>   |<span data-ttu-id="32e44-197">打开**skype For business 用户可以在外部访问中与 skype 用户进行通信**。</span><span class="sxs-lookup"><span data-stu-id="32e44-197">Turn on the **Skype for Business users can communicate with Skype users** setting in External Access.</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="32e44-198">您不必将任何**Skype 域**添加为 "允许的域"，以便让团队或 Skype For business Online 用户能够与组织内部或外部的 skype 用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="32e44-198">You don't have to add any **Skype domains** as allowed domains in order to enable Teams or Skype for Business Online users to communicate with Skype users inside or outside your organization.</span></span> <span data-ttu-id="32e44-199">所有**Skype 域**均为白名单，这意味着所有这些域均被视为允许。</span><span class="sxs-lookup"><span data-stu-id="32e44-199">All **Skype domains** are whitelisted, which means all of these domains are considered ALLOWED.</span></span>



## <a name="how-does-external-access-compare-with-guest-access"></a><span data-ttu-id="32e44-200">外部访问与来宾访问的比较情况如何？</span><span class="sxs-lookup"><span data-stu-id="32e44-200">How does external access compare with guest access?</span></span>

<span data-ttu-id="32e44-201">若要了解外部访问和来宾访问之间的区别，请阅读[与其他组织中的用户进行通信](communicate-with-users-from-other-organizations.md)。</span><span class="sxs-lookup"><span data-stu-id="32e44-201">To learn about the difference between external access and guest access, read [Communicate with users from other organizations](communicate-with-users-from-other-organizations.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="32e44-202">相关主题</span><span class="sxs-lookup"><span data-stu-id="32e44-202">Related topics</span></span>

[<span data-ttu-id="32e44-203">外部（联合）用户的本机聊天体验</span><span class="sxs-lookup"><span data-stu-id="32e44-203">Native chat experience for external (federated) users</span></span>](native-chat-for-external-users.md)
