---
title: '管理外部访问 (联合身份验证) '
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.externalaccess.overview
- seo-marvel-mar2020
description: 你的 Teams 管理员或 IT 管理员可以为其他域配置外部访问（联合身份验证），使来自这些域的用户能参与到 Teams 中。
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: ae9a198de7fa15ac77743b2477a44602e54fecb7
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421327"
---
# <a name="manage-external-access-in-microsoft-teams"></a><span data-ttu-id="8812a-103">在 Microsoft Teams 中管理外部访问</span><span class="sxs-lookup"><span data-stu-id="8812a-103">Manage external access in Microsoft Teams</span></span>

<span data-ttu-id="8812a-104">外部访问是一种供整个外部域中的 Teams 用户在 Teams 中查找、呼叫、聊天和设置会议的方式。</span><span class="sxs-lookup"><span data-stu-id="8812a-104">External access is a way for Teams users from an entire external domain to find, call, chat, and set up meetings with you in Teams.</span></span> <span data-ttu-id="8812a-105">您还可以使用外部访问来与其他组织中仍在使用 Skype for Business (online 和本地) 和 Skype (预览版) 。</span><span class="sxs-lookup"><span data-stu-id="8812a-105">You can also use external access to communicate with people from other organizations who are still using Skype for Business (online and on-premises) and Skype (in preview).</span></span>

<span data-ttu-id="8812a-106">如果希望其他组织中的人员能够访问团队和频道，来宾访问可能是更好的选择。</span><span class="sxs-lookup"><span data-stu-id="8812a-106">If you want people from other organizations to have access to teams and channels, guest access might be a better way to go.</span></span> <span data-ttu-id="8812a-107">有关外部访问和来宾访问之间的差异的详细信息，请参阅[比较外部访问和来宾访问](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。</span><span class="sxs-lookup"><span data-stu-id="8812a-107">For more information about the differences between external access and guest access, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span> 

<span data-ttu-id="8812a-108">在以下情况下使用外部访问：</span><span class="sxs-lookup"><span data-stu-id="8812a-108">Use external access when:</span></span>
  
- <span data-ttu-id="8812a-109">你拥有在不同域中需要协作的用户。</span><span class="sxs-lookup"><span data-stu-id="8812a-109">You have users in different domains who need to collaborate.</span></span> <span data-ttu-id="8812a-110">例如，Rob@contoso.com 和 Ann@northwindtraders.com 与 contoso.com 和 northwindtraders.com 域中的其他一些人协作处理某个项目。</span><span class="sxs-lookup"><span data-stu-id="8812a-110">For example, Rob@contoso.com and Ann@northwindtraders.com are working on a project together along with some others in the contoso.com and northwindtraders.com domains.</span></span>

- <span data-ttu-id="8812a-111">你希望自己组织内的人员使用 Teams 联系组织外特定企业中的人员。</span><span class="sxs-lookup"><span data-stu-id="8812a-111">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>

- <span data-ttu-id="8812a-112">你希望世界各地使用 Teams 的所有其他人都能够通过使用你的电子邮件地址找到并联系你。</span><span class="sxs-lookup"><span data-stu-id="8812a-112">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="8812a-113">若要使用 Teams 客户端与外部用户通信 (无论该用户使用的是 Teams 还是 Skype for Business) ，Teams 用户都必须位于 Skype for Business Online 中。</span><span class="sxs-lookup"><span data-stu-id="8812a-113">To use the Teams client to communicate with an external user (whether that user is using Teams or Skype for Business), the Teams user must be homed in Skype for Business Online.</span></span>

## <a name="plan-for-external-access"></a><span data-ttu-id="8812a-114">规划外部访问</span><span class="sxs-lookup"><span data-stu-id="8812a-114">Plan for external access</span></span>

<span data-ttu-id="8812a-115">默认情况下，Teams 中的外部访问处于启用状态，这意味着你的组织可以与所有外部域进行通信。</span><span class="sxs-lookup"><span data-stu-id="8812a-115">By default, external access is turned on in Teams, which means that your organization can communicate with all external domains.</span></span> <span data-ttu-id="8812a-116">如果添加阻止的域，将允许所有其他域；如果添加允许的域，将阻止所有其他域。</span><span class="sxs-lookup"><span data-stu-id="8812a-116">If you add blocked domains, all other domains will be allowed; and if you add allowed domains, all other domains will be blocked.</span></span> <span data-ttu-id="8812a-117">此规则的例外情况是允许匿名参与者参加会议。</span><span class="sxs-lookup"><span data-stu-id="8812a-117">The exception to this rule is if anonymous participants are allowed in meetings.</span></span> <span data-ttu-id="8812a-118">在 Teams 管理中心（“**组织范围的设置**” > “**外部访问**”）设置外部访问有三种情形：</span><span class="sxs-lookup"><span data-stu-id="8812a-118">There are three scenarios for setting up external access in the Teams admin center (**Org-wide settings** > **External access**):</span></span>

> [!NOTE]
> <span data-ttu-id="8812a-119">如果关闭组织中外部访问，外部用户仍可通过匿名加入加入会议。</span><span class="sxs-lookup"><span data-stu-id="8812a-119">If you turn off external access in your organization, external users can still join meetings through anonymous join.</span></span> <span data-ttu-id="8812a-120">若要了解详细信息，请参阅[管理 Teams 中的会议策略](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="8812a-120">To learn more, see [Manage meeting settings in Teams](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams).</span></span>

- <span data-ttu-id="8812a-121">**开放式联合身份验证**：这是 Teams 中的默认设置，可让你组织中的用户查找你组织外部任何域中的人员，并与这些人员进行通话、聊天和安排会议。</span><span class="sxs-lookup"><span data-stu-id="8812a-121">**Open federation**: This is the default setting in Teams, and it lets people in your organization find, call, chat, and set up meetings with people external to your organization in any domain.</span></span>

    <span data-ttu-id="8812a-122">在这种情形中，你的用户能够与符合以下条件的所有外部域进行通信：正在运行 Teams 或 Skype for Business，并且正在使用开放式联合身份验证，或者已将你的域添加到他们允许列表中。</span><span class="sxs-lookup"><span data-stu-id="8812a-122">In this scenario, your users can communicate with all external domains that are running Teams or Skype for Business AND are using open federation OR have added your domain to their allow list.</span></span>

- <span data-ttu-id="8812a-123">**允许特定域**：通过将域添加到“**允许**”列表中，将外部访问限制为仅允许的域。</span><span class="sxs-lookup"><span data-stu-id="8812a-123">**Allow specific domains**: By adding domains to an **Allow** list, you limit external access to only the allowed domains.</span></span> <span data-ttu-id="8812a-124">设置允许的域列表后，将阻止所有其他域。</span><span class="sxs-lookup"><span data-stu-id="8812a-124">Once you set up a list of allowed domains, all other domains will be blocked.</span></span> <span data-ttu-id="8812a-125">若要允许特定域，请单击“**添加域**”，添加域名，单击“**要在此域上执行的操作**”，然后选择“**已允许**”。</span><span class="sxs-lookup"><span data-stu-id="8812a-125">To allow specific domains, click **Add a domain**, add the domain name, click **Action to take on this domain**, and then select **Allowed**.</span></span>

- <span data-ttu-id="8812a-126">**阻止特定域** - 通过将域添加到“**阻止**”列表中，可与 *除阻止的域之外* 的所有外部域进行通信。</span><span class="sxs-lookup"><span data-stu-id="8812a-126">**Block specific domains** - By adding domains to a **Block** list, you can communicate with all external domains *except* the ones you've blocked.</span></span> <span data-ttu-id="8812a-127">若要阻止特定域，请单击“**添加域**”，添加域名，单击“**要在此域上执行的操作**”，然后选择“**已阻止**”。</span><span class="sxs-lookup"><span data-stu-id="8812a-127">To block specific domains, click **Add a domain**, add the domain name, click **Action to take on this domain**, and then select **Blocked**.</span></span> <span data-ttu-id="8812a-128">设置阻止的域列表后，将允许所有其他域。</span><span class="sxs-lookup"><span data-stu-id="8812a-128">Once you set up a list of blocked domains, all other domains will be allowed.</span></span>

> [!NOTE]
> <span data-ttu-id="8812a-129">允许或阻止的域仅适用于对会议的匿名访问"关闭"时的会议。</span><span class="sxs-lookup"><span data-stu-id="8812a-129">The allowed or blocked domains only apply to meetings if anonymous access to meetings is "off".</span></span>

## <a name="allow-or-block-domains"></a><span data-ttu-id="8812a-130">允许或阻止域</span><span class="sxs-lookup"><span data-stu-id="8812a-130">Allow or block domains</span></span>

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-or-skype-for-business-organizations"></a><span data-ttu-id="8812a-131">步骤 1 - 使组织能够与其他 Teams 或 Skype for Business 组织进行通信</span><span class="sxs-lookup"><span data-stu-id="8812a-131">Step 1 - Enable your organization to communicate with another Teams or Skype for Business organizations</span></span>

<span data-ttu-id="8812a-132">![显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png)  **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="8812a-132">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png)  **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="8812a-133">在左侧导航栏中，转到“**组织范围的设置**” > “**外部访问**”。</span><span class="sxs-lookup"><span data-stu-id="8812a-133">In the left navigation, go to **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="8812a-134">启用“**用户可以与其他 Skype for Business 和 Teams 用户通信**”设置。</span><span class="sxs-lookup"><span data-stu-id="8812a-134">Turn on the **Users can communicate with other Skype for Business and Teams users** setting.</span></span>

     ![已启用“用户可以与其他 Skype for Business 和 Teams 用户通信”设置的屏幕截图](media/manage-external-access-2.png)<span data-ttu-id="8812a-136">.</span><span class="sxs-lookup"><span data-stu-id="8812a-136">.</span></span>

3. <span data-ttu-id="8812a-137">如果想要允许所有 Teams 组织与你组织中的用户进行通信，请跳到步骤 5。</span><span class="sxs-lookup"><span data-stu-id="8812a-137">If you want to allow all Teams organizations to communicate with users in your organization, skip to step 5.</span></span>

4. <span data-ttu-id="8812a-138">如果想要限制可与你组织中的用户进行通信的组织，你可以允许除某些域之外的所有域，或者你可以仅允许特定域。</span><span class="sxs-lookup"><span data-stu-id="8812a-138">If you want to limit the organizations that can communicate with users in your organization, you can either allow all except some domains, or you can allow only specific domains.</span></span> 

    - <span data-ttu-id="8812a-139">若要允许除某些域之外的所有域，请单击“**添加域**”，添加要阻止的域。</span><span class="sxs-lookup"><span data-stu-id="8812a-139">To allow all except some domains, add the domains you want to block by clicking **Add domain**.</span></span> <span data-ttu-id="8812a-140">在“**添加域**”窗格中，键入域名，单击“**已阻止**”，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="8812a-140">In the **Add a domain** pane, type the domain name, click **Blocked**, and then click **Done**.</span></span> 
    - <span data-ttu-id="8812a-141">若要限制为仅与特定组织进行通信，请将这些域添加到具有“**已允许**”状态的列表中。</span><span class="sxs-lookup"><span data-stu-id="8812a-141">To limit communications to specific organizations, add those domains to the list with a status of **Allowed**.</span></span> <span data-ttu-id="8812a-142">将任何域添加到“允许”列表后，与其他组织的通信将仅限于所在域位于“允许”列表中的组织。</span><span class="sxs-lookup"><span data-stu-id="8812a-142">Once you have added any domain to the Allow list, communications with other organizations will be limited to only those organizations whose domains are in the Allow list.</span></span> 

5. <span data-ttu-id="8812a-143">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="8812a-143">Click **Save**.</span></span>

6. <span data-ttu-id="8812a-144">确保其他 Teams 组织中的管理员完成了上述相同步骤。</span><span class="sxs-lookup"><span data-stu-id="8812a-144">Make sure the admin in the other Teams organization completes these same steps.</span></span> <span data-ttu-id="8812a-145">例如，如果他们要限制可与其用户通信的组织，其管理员需要在“**允许的域**”列表中输入你企业的域。</span><span class="sxs-lookup"><span data-stu-id="8812a-145">For example, in their **allowed domains** list, their admin needs to enter the domain for your business if they limit the organizations that can communicate with their users.</span></span>

### <a name="step-2---test-it"></a><span data-ttu-id="8812a-146">步骤 2 - 测试</span><span class="sxs-lookup"><span data-stu-id="8812a-146">Step 2 - Test it</span></span>

<span data-ttu-id="8812a-147">若要测试你的设置，你需要一名不在你防火墙后方的 Teams 用户。</span><span class="sxs-lookup"><span data-stu-id="8812a-147">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
1. <span data-ttu-id="8812a-148">在你和你组织的管理员更改了“**外部访问**”设置后，应该可以继续进行操作。</span><span class="sxs-lookup"><span data-stu-id="8812a-148">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>

2. <span data-ttu-id="8812a-149">在 Teams 应用中，通过电子邮件地址搜索该用户，并发送聊天请求。</span><span class="sxs-lookup"><span data-stu-id="8812a-149">In the Teams app, search for the person by email address, and send a request to chat.</span></span>

3. <span data-ttu-id="8812a-150">让你的 Teams 联系人向你发送聊天请求。</span><span class="sxs-lookup"><span data-stu-id="8812a-150">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="8812a-151">如果未收到其请求，则问题源于你的防火墙设置（假设他们已确认他们的防火墙设置正确）。</span><span class="sxs-lookup"><span data-stu-id="8812a-151">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>

4. <span data-ttu-id="8812a-152">测试问题是否源于防火墙的另一种方法是转到一个不在你防火墙后方的 WiFi 位置。</span><span class="sxs-lookup"><span data-stu-id="8812a-152">Another way to test whether the problem is your firewall is to go to a WiFi location not behind your firewall.</span></span> <span data-ttu-id="8812a-153">例如前往某家咖啡店，然后使用 Teams 向联系人发送聊天请求。</span><span class="sxs-lookup"><span data-stu-id="8812a-153">such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="8812a-154">如果在这个 WiFi 位置可以顺利传送消息，但在你的工作地点不行，那么可以确定问题源于你的防火墙。</span><span class="sxs-lookup"><span data-stu-id="8812a-154">If the message goes through at the WiFi location, but does not when you're at work, then you know the problem is your firewall.</span></span>

> [!NOTE]
> <span data-ttu-id="8812a-155">如果你和另一名用户都启用了外部访问并允许了彼此的域，应该可以正常工作。</span><span class="sxs-lookup"><span data-stu-id="8812a-155">If you and another user both turn on external access and allow one another's domains, this will work.</span></span> <span data-ttu-id="8812a-156">如果不正常，另一名用户应确保其配置未阻止你的域。</span><span class="sxs-lookup"><span data-stu-id="8812a-156">If it doesn't work, the other user should make sure their configuration isn't blocking your domain.</span></span>


## <a name="communicate-with-skype-users-in-preview"></a><span data-ttu-id="8812a-157">与 Skype 用户进行通信（处于预览阶段）</span><span class="sxs-lookup"><span data-stu-id="8812a-157">Communicate with Skype users (in preview)</span></span>

<span data-ttu-id="8812a-158">请按照以下步骤，让你组织中的 Teams 用户与 Skype 用户聊天和通话。</span><span class="sxs-lookup"><span data-stu-id="8812a-158">Follow these steps to let Teams users in your organization chat with and call Skype users.</span></span> <span data-ttu-id="8812a-159">然后，Teams 用户可以搜索和启动与 Skype 用户之间的一次性文本对话或音频/视频通话，以及反向操作。</span><span class="sxs-lookup"><span data-stu-id="8812a-159">Teams users can then search for and start a one-on-one text-only conversation or an audio/video call with Skype users and vice versa.</span></span>

<span data-ttu-id="8812a-160">![显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png)  **使用 Microsoft Teams 管理中心**</span><span class="sxs-lookup"><span data-stu-id="8812a-160">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png)  **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="8812a-161">在左侧导航栏中，转到“**组织范围的设置**” > “**外部访问**”。</span><span class="sxs-lookup"><span data-stu-id="8812a-161">In the left navigation, go to **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="8812a-162">启用“**用户可与 Skype 用户通信**”设置。</span><span class="sxs-lookup"><span data-stu-id="8812a-162">Turn on the **Users can communicate with Skype users** setting.</span></span>

    ![已启用“用户可与 Skype 用户通信”设置的屏幕截图](media/manage-external-access-5.png)<span data-ttu-id="8812a-164">.</span><span class="sxs-lookup"><span data-stu-id="8812a-164">.</span></span>

<span data-ttu-id="8812a-165">若要深入了解 Teams 用户和 Skype 用户之间的通信方式（包括适用的限制），请参阅 [Teams 和 Skype 的互操作性](teams-skype-interop.md)。</span><span class="sxs-lookup"><span data-stu-id="8812a-165">To learn more about the ways that Teams users and Skype users can communicate, including limitations that apply, see [Teams and Skype interoperability](teams-skype-interop.md).</span></span>

## <a name="common-external-access-scenarios"></a><span data-ttu-id="8812a-166">常见外部访问情形</span><span class="sxs-lookup"><span data-stu-id="8812a-166">Common external access scenarios</span></span>

<span data-ttu-id="8812a-167">以下部分介绍如何为常见的外部访问方案启用联合，以及 TeamsUpgradePolicy 如何确定传入聊天和呼叫的传送。</span><span class="sxs-lookup"><span data-stu-id="8812a-167">The following sections describe how to enable federation for common external access scenarios, and how the TeamsUpgradePolicy determines delivery of incoming chats and calls.</span></span>

### <a name="enable-federation"></a><span data-ttu-id="8812a-168">启用联合身份验证</span><span class="sxs-lookup"><span data-stu-id="8812a-168">Enable federation</span></span>

<span data-ttu-id="8812a-169">若要使贵组织的用户能够与另一个组织中用户通信，这两个组织必须启用联合。</span><span class="sxs-lookup"><span data-stu-id="8812a-169">To enable users in your organization to communicate with users in another organization, both organizations must enable federation.</span></span> <span data-ttu-id="8812a-170">为给定组织启用联合身份验证的步骤取决于组织是纯联机、混合还是纯本地。</span><span class="sxs-lookup"><span data-stu-id="8812a-170">The steps to enable federation for a given organization depend on whether the organization is purely online, hybrid, or purely on-premises.</span></span>

|<span data-ttu-id="8812a-171">**如果你的组织**</span><span class="sxs-lookup"><span data-stu-id="8812a-171">**If your organization is**</span></span> |<span data-ttu-id="8812a-172">**按如下所示启用联合身份验证**</span><span class="sxs-lookup"><span data-stu-id="8812a-172">**Enable federation as follows**</span></span>  |
|:---------|:-----------------------|
|<span data-ttu-id="8812a-173">联机，没有本地 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="8812a-173">Online with no Skype for Business on-premises.</span></span> <span data-ttu-id="8812a-174">这包括具有 TeamsOnly 用户和/或 Skype for Business Online 用户的组织。</span><span class="sxs-lookup"><span data-stu-id="8812a-174">This includes organizations that have TeamsOnly users and/or Skype for Business Online users.</span></span>| <span data-ttu-id="8812a-175">如果使用 Teams 管理中心：</span><span class="sxs-lookup"><span data-stu-id="8812a-175">If using Teams Admin Center:</span></span> <br><span data-ttu-id="8812a-176">- 确保在外部访问中启用"用户可以与其他 **Skype for Business** 和 Teams 用户"设置进行通信。</span><span class="sxs-lookup"><span data-stu-id="8812a-176">-   Make sure the **Users can communicate with other Skype for Business and Teams users** setting is enabled in External Access.</span></span><br><span data-ttu-id="8812a-177">- 如果不使用开放联合身份验证 (允许与其他域联合) ，则向"允许"列表添加外部域。</span><span class="sxs-lookup"><span data-stu-id="8812a-177">- If you are not using open federation (which allows federation with any other domain), then add the external domain to the Allowed list.</span></span><br><br><span data-ttu-id="8812a-178">如果使用 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="8812a-178">If using PowerShell:</span></span><br><span data-ttu-id="8812a-179">- 确保租户已启用联合身份验证： `Get-CsTenantFederationConfiguration` 必须显示 `AllowFederatedUsers=true` 。</span><span class="sxs-lookup"><span data-stu-id="8812a-179">- Ensure the tenant is enabled for federation: `Get-CsTenantFederationConfiguration` must show `AllowFederatedUsers=true`.</span></span> <br><span data-ttu-id="8812a-180">- 确保用户的有效值为 `CsExternalAccessPolicy` `EnableFederationAccess=true` has。</span><span class="sxs-lookup"><span data-stu-id="8812a-180">- Ensure the user’s effective value of `CsExternalAccessPolicy` has `EnableFederationAccess=true`.</span></span><br><span data-ttu-id="8812a-181">- 如果不使用开放联合身份验证，请确保目标域列在 `AllowedDomains` `CsTenantFederationConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="8812a-181">- If you are not using open federation, ensure the target domain is listed in `AllowedDomains` of `CsTenantFederationConfiguration`.</span></span> |
|<span data-ttu-id="8812a-182">纯本地</span><span class="sxs-lookup"><span data-stu-id="8812a-182">Pure on-premises</span></span> | <span data-ttu-id="8812a-183">在本地工具中：</span><span class="sxs-lookup"><span data-stu-id="8812a-183">In on-premises tools:</span></span> <br><span data-ttu-id="8812a-184">- 确保在 中启用联合 `CsAccessEdgeConfiguration` 身份验证。</span><span class="sxs-lookup"><span data-stu-id="8812a-184">- Ensure federation is enabled in `CsAccessEdgeConfiguration`.</span></span><br><span data-ttu-id="8812a-185">- 确保通过全局策略、 (策略或用户分配的策略来启用用户 `ExternalAccessPolicy`) 。</span><span class="sxs-lookup"><span data-stu-id="8812a-185">- Ensure federation for the user is enabled through `ExternalAccessPolicy` (either through the global policy, site policy, or user assigned policy).</span></span> <br> <span data-ttu-id="8812a-186">- 如果不使用开放联合身份验证，请确保目标域列在 `AllowedDomains` .</span><span class="sxs-lookup"><span data-stu-id="8812a-186">- If you are not using open federation, ensure the target domain is listed in `AllowedDomains`.</span></span> |
|<span data-ttu-id="8812a-187">在 Skype for Business (Teams (与某些在线用户进行混合) 以及在本地使用某些用户。</span><span class="sxs-lookup"><span data-stu-id="8812a-187">Hybrid with some users online (in either Skype for Business or Teams) and some users on-premises.</span></span> | <span data-ttu-id="8812a-188">为联机和本地组织执行上述步骤。</span><span class="sxs-lookup"><span data-stu-id="8812a-188">Follow above steps for both online and on-premises organizations.</span></span> |

### <a name="delivery-of-incoming-chats-and-calls"></a><span data-ttu-id="8812a-189">传入聊天和呼叫的传送</span><span class="sxs-lookup"><span data-stu-id="8812a-189">Delivery of incoming chats and calls</span></span> 

<span data-ttu-id="8812a-190">来自联合组织的传入聊天和呼叫将进入用户的 Teams 或 Skype for Business 客户端，具体取决于 TeamsUpgradePolicy 中的接收用户模式。</span><span class="sxs-lookup"><span data-stu-id="8812a-190">Incoming chats and calls from a federation organization will land in the user’s Teams or Skype for Business client depending on the recipient user’s mode in TeamsUpgradePolicy.</span></span>

|<span data-ttu-id="8812a-191">**如果要**</span><span class="sxs-lookup"><span data-stu-id="8812a-191">**If you want to**</span></span> |<span data-ttu-id="8812a-192">**执行此操作：**</span><span class="sxs-lookup"><span data-stu-id="8812a-192">**Do this:**</span></span>  |
|:---------|:-----------------------|
| <span data-ttu-id="8812a-193">确保传入的联合聊天和呼叫到达用户的 Teams 客户端：</span><span class="sxs-lookup"><span data-stu-id="8812a-193">Ensure incoming federated chats and calls arrive in the user’s Teams client:</span></span> | <span data-ttu-id="8812a-194">将用户配置为 TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="8812a-194">Configure your users to be TeamsOnly.</span></span>
| <span data-ttu-id="8812a-195">确保传入的联合聊天和呼叫到达用户的 Skype for Business 客户端</span><span class="sxs-lookup"><span data-stu-id="8812a-195">Ensure incoming federated chats and calls arrive in the user’s Skype for Business client</span></span> | <span data-ttu-id="8812a-196">将用户配置为除 TeamsOnly 外的任何模式。</span><span class="sxs-lookup"><span data-stu-id="8812a-196">Configure your users to be in any mode other than TeamsOnly.</span></span> |


### <a name="enable-federation-between-users-in-your-organization-and-consumer-users-of-skype"></a><span data-ttu-id="8812a-197">在组织中用户与 Skype 使用者用户之间启用联合</span><span class="sxs-lookup"><span data-stu-id="8812a-197">Enable federation between users in your organization and consumer users of Skype</span></span>

<span data-ttu-id="8812a-198">若要在组织中用户与 Skype 使用者用户之间启用联合，</span><span class="sxs-lookup"><span data-stu-id="8812a-198">To enable federation between users in your organization and consumer users of Skype:</span></span>

|<span data-ttu-id="8812a-199">**如果你的组织**</span><span class="sxs-lookup"><span data-stu-id="8812a-199">**If your organization is**</span></span> |<span data-ttu-id="8812a-200">**按如下所示启用使用者联合**</span><span class="sxs-lookup"><span data-stu-id="8812a-200">**Enable consumer federation as follows**</span></span>  |
|:---------|:-----------------------|
| <span data-ttu-id="8812a-201">纯在线，没有本地 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="8812a-201">Pure online with no Skype for Business on-premises.</span></span>  <span data-ttu-id="8812a-202">这包括具有 TeamsOnly 用户和/或 Skype for Business Online 用户的组织。</span><span class="sxs-lookup"><span data-stu-id="8812a-202">This includes organizations that have TeamsOnly users and/or Skype for Business Online users.</span></span> | <span data-ttu-id="8812a-203">如果使用 Teams 管理中心：</span><span class="sxs-lookup"><span data-stu-id="8812a-203">If using Teams Admin Center:</span></span> <br><span data-ttu-id="8812a-204">-确保在 **外部访问中启用用户可以与 Skype** 用户通信。</span><span class="sxs-lookup"><span data-stu-id="8812a-204">-Make sure **Users can communicate with Skype users** is enabled in External Access.</span></span><br><br><span data-ttu-id="8812a-205">如果使用 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="8812a-205">If using PowerShell:</span></span> <br><span data-ttu-id="8812a-206">-确保租户已启用联合身份验证： `Get-CsTenantFederationConfiguration` 必须显示 `AllowPublicUsers=true` 。</span><span class="sxs-lookup"><span data-stu-id="8812a-206">-Ensure the tenant is enabled for federation: `Get-CsTenantFederationConfiguration` must show `AllowPublicUsers=true`.</span></span> <br> <span data-ttu-id="8812a-207">- 确保用户的有效值为 `CsExternalAccessPolicy` `EnablePublicCloudAccess=true` has。</span><span class="sxs-lookup"><span data-stu-id="8812a-207">- Ensure the user’s effective value of `CsExternalAccessPolicy` has `EnablePublicCloudAccess=true`.</span></span> |
| <span data-ttu-id="8812a-208">纯本地</span><span class="sxs-lookup"><span data-stu-id="8812a-208">Pure on-premises</span></span> | <span data-ttu-id="8812a-209">在本地工具中：</span><span class="sxs-lookup"><span data-stu-id="8812a-209">In on-premises tools:</span></span> <br> <span data-ttu-id="8812a-210">- 确保 Skype 作为联合合作伙伴启用。</span><span class="sxs-lookup"><span data-stu-id="8812a-210">- Ensure Skype is enabled as a federated partner.</span></span> <br> <span data-ttu-id="8812a-211">- `EnablePublicCloudAccess=true` 通过全局策略、 (策略或用户分配的策略，确保用户 `ExternalAccessPolicy`) 。</span><span class="sxs-lookup"><span data-stu-id="8812a-211">- Ensure `EnablePublicCloudAccess=true` for the user through `ExternalAccessPolicy` (either via global policy, site policy, or user assigned policy).</span></span>|
| <span data-ttu-id="8812a-212">在 Skype for Business (Teams (与某些在线用户进行混合) 以及在本地使用某些用户。</span><span class="sxs-lookup"><span data-stu-id="8812a-212">Hybrid with some users online (in either Skype for Business or Teams) and some users on-premises.</span></span>| <span data-ttu-id="8812a-213">为联机和本地组织执行上述步骤。</span><span class="sxs-lookup"><span data-stu-id="8812a-213">Follow above steps for both online and on-premises organizations.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="8812a-214">你无需添加任何 **Skype 域** 作为允许的域，就可以使 Teams 或 Skype for Business Online 用户与你组织内部或外部的 Skype 用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="8812a-214">You don't have to add any **Skype domains** as allowed domains in order to enable Teams or Skype for Business Online users to communicate with Skype users inside or outside your organization.</span></span> <span data-ttu-id="8812a-215">允许 **所有 Skype** 域。</span><span class="sxs-lookup"><span data-stu-id="8812a-215">All **Skype domains** are allowed.</span></span>

## <a name="how-does-external-access-compare-with-guest-access"></a><span data-ttu-id="8812a-216">外部访问与来宾访问有何不同？</span><span class="sxs-lookup"><span data-stu-id="8812a-216">How does external access compare with guest access?</span></span>

<span data-ttu-id="8812a-217">若要了解外部访问和来宾访问之间的区别，请参阅[与其他组织的用户通信](communicate-with-users-from-other-organizations.md)。</span><span class="sxs-lookup"><span data-stu-id="8812a-217">To learn about the difference between external access and guest access, read [Communicate with users from other organizations](communicate-with-users-from-other-organizations.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8812a-218">相关主题</span><span class="sxs-lookup"><span data-stu-id="8812a-218">Related topics</span></span>

- [<span data-ttu-id="8812a-219">外部（联合身份验证）用户的本机聊天体验</span><span class="sxs-lookup"><span data-stu-id="8812a-219">Native chat experience for external (federated) users</span></span>](native-chat-for-external-users.md)
