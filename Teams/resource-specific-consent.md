---
title: Microsoft Teams 中特定于资源的同意
author: cichur
ms.author: v-cichur
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解需要配置的设置，以控制组织中团队所有者是否可以同意应用。
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7b9379db7760fa8ef03440c24b93cb0223b4bee
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117620"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a><span data-ttu-id="18046-103">Microsoft Teams 中特定于资源的同意</span><span class="sxs-lookup"><span data-stu-id="18046-103">Resource-specific consent in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="18046-104">Microsoft Teams 中特定于资源的同意允许团队所有者同意应用访问团队数据。</span><span class="sxs-lookup"><span data-stu-id="18046-104">Resource-specific consent in Microsoft Teams lets team owners give consent to apps to access team data.</span></span> <span data-ttu-id="18046-105">此类访问的示例包括读取通道消息、创建和删除通道以及创建和删除通道选项卡的功能。</span><span class="sxs-lookup"><span data-stu-id="18046-105">Examples of such access include the ability to read channel messages, create and delete channels, and create and remove channel tabs.</span></span>

<span data-ttu-id="18046-106">作为管理员，你可以控制你的组织中团队所有者是否可以通过使用 Azure Active Directory (Azure AD) PowerShell 模块或 Azure 门户和 Microsoft Teams 管理中心配置的设置来表示同意。</span><span class="sxs-lookup"><span data-stu-id="18046-106">As an admin, you control whether team owners in your organization can give consent through settings that you configure by using the Azure Active Directory (Azure AD) PowerShell module or the Azure portal and the Microsoft Teams admin center.</span></span>  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a><span data-ttu-id="18046-107">设置团队所有者是否可以许可应用</span><span class="sxs-lookup"><span data-stu-id="18046-107">Set whether team owners can give consent to apps</span></span>

<span data-ttu-id="18046-108">下面是必须设置的设置，用于控制团队所有者是否可以许可应用。</span><span class="sxs-lookup"><span data-stu-id="18046-108">Here are the settings that you must set to control whether team owners can give consent to apps.</span></span> <span data-ttu-id="18046-109">请务必查看以下所有设置。</span><span class="sxs-lookup"><span data-stu-id="18046-109">Be sure to review all the following settings.</span></span>

### <a name="settings-in-azure-ad"></a><span data-ttu-id="18046-110">Azure AD 中的设置</span><span class="sxs-lookup"><span data-stu-id="18046-110">Settings in Azure AD</span></span>

<span data-ttu-id="18046-111">以下两个设置确定团队所有者是否可以许可应用。</span><span class="sxs-lookup"><span data-stu-id="18046-111">The following two settings determine whether team owners can give consent to apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18046-112">更改这些设置中的任一设置不会影响已授予许可的应用的数据访问。</span><span class="sxs-lookup"><span data-stu-id="18046-112">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="18046-113">例如，如果将这些设置配置为防止团队所有者同意，这些更改不会删除已授予的数据访问权限。</span><span class="sxs-lookup"><span data-stu-id="18046-113">For example, if you configure these settings to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a><span data-ttu-id="18046-114">"用户可以同意应用代表他们访问公司数据"设置</span><span class="sxs-lookup"><span data-stu-id="18046-114">The "Users can consent to apps accessing company data on their behalf" setting</span></span>

<span data-ttu-id="18046-115">此设置控制您的组织中的用户是否可以代表他们许可应用。</span><span class="sxs-lookup"><span data-stu-id="18046-115">This setting controls whether users in your organization can consent to apps on their behalf.</span></span> <span data-ttu-id="18046-116">若要使团队所有者能够表示同意，必须将此设置设置为"**是"。**</span><span class="sxs-lookup"><span data-stu-id="18046-116">To enable team owners to give consent, this setting must be set to **Yes**.</span></span> <span data-ttu-id="18046-117">若要管理此设置，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="18046-117">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="18046-118">在 Azure 门户中，转到"**企业应用程序用户**  >  **设置"。**</span><span class="sxs-lookup"><span data-stu-id="18046-118">In the Azure portal, go to **Enterprise applications** > **User settings**.</span></span>
2. <span data-ttu-id="18046-119">在 **"企业应用程序\*\*\*\*"下**，将"用户可以同意代表他们访问公司数据的应用"设置为"**否**"或"**是"。**</span><span class="sxs-lookup"><span data-stu-id="18046-119">Under **Enterprise applications**, set **Users can consent to apps accessing company data on their behalf** to **No** or **Yes**.</span></span>

<span data-ttu-id="18046-120">也可使用 PowerShell 管理此设置。</span><span class="sxs-lookup"><span data-stu-id="18046-120">You can also manage this setting using PowerShell.</span></span> <span data-ttu-id="18046-121">有关详细信息，请参阅 [将用户内容配置为应用程序](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)。</span><span class="sxs-lookup"><span data-stu-id="18046-121">To learn more, see [Configure user content to applications](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).</span></span>

#### <a name="the-enablegroupspecificconsent-setting"></a><span data-ttu-id="18046-122">"EnableGroupSpecificConsent"设置</span><span class="sxs-lookup"><span data-stu-id="18046-122">The "EnableGroupSpecificConsent" setting</span></span>

<span data-ttu-id="18046-123">此设置控制您的组织中的用户是否可以同意应用访问他们拥有组的公司数据。</span><span class="sxs-lookup"><span data-stu-id="18046-123">This setting controls whether users in your organization can consent to apps accessing company data for the groups that they own.</span></span> <span data-ttu-id="18046-124">必须启用此设置，团队所有者才能表示同意。</span><span class="sxs-lookup"><span data-stu-id="18046-124">This setting must be enabled for team owners to give consent.</span></span> <span data-ttu-id="18046-125">有关如何使用 PowerShell 管理此设置的步骤，请参阅 [配置组所有者对访问组数据的应用的同意](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)。</span><span class="sxs-lookup"><span data-stu-id="18046-125">For steps on how to manage this setting by using PowerShell, see [Configure group owner consent to apps accessing group data](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).</span></span>

### <a name="settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="18046-126">Microsoft Teams 管理中心中的设置</span><span class="sxs-lookup"><span data-stu-id="18046-126">Settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="18046-127">除了 Azure AD 中的设置[](manage-apps.md#manage-org-wide-app-settings)外，"管理应用"页上[](manage-apps.md)的"组织范围"应用设置、在"管理应用"页上[](manage-apps.md#allow-and-block-apps)是阻止还是允许应用，以及分配给团队所有者的应用权限策略决定了团队所有者是否可以同意。 [](teams-app-permission-policies.md)</span><span class="sxs-lookup"><span data-stu-id="18046-127">In addition to settings in Azure AD, [org-wide app settings](manage-apps.md#manage-org-wide-app-settings) on the [Manage apps](manage-apps.md) page, whether an app is blocked or allowed on the [Manage apps](manage-apps.md#allow-and-block-apps) page, and the [app permission policy](teams-app-permission-policies.md) assigned to the team owner determine whether a team owner can give consent.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18046-128">更改这些设置中的任一设置不会影响已授予许可的应用的数据访问。</span><span class="sxs-lookup"><span data-stu-id="18046-128">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="18046-129">例如，如果在组织范围内禁用第三方应用，或者阻止特定应用以防止团队所有者同意，这些更改不会删除已授予的数据访问权限。</span><span class="sxs-lookup"><span data-stu-id="18046-129">For example, if you disable third-party apps org-wide or if you block specific apps to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a><span data-ttu-id="18046-130">组织范围应用设置中的"允许第三方应用"设置</span><span class="sxs-lookup"><span data-stu-id="18046-130">The "Allow third party apps" setting in org-wide app settings</span></span>

<span data-ttu-id="18046-131">此组织范围内的应用设置控制组织中的用户是否可以使用第三方应用。</span><span class="sxs-lookup"><span data-stu-id="18046-131">This org-wide app setting controls whether users in your organization can use third-party apps.</span></span> <span data-ttu-id="18046-132">必须启用此设置，团队所有者才能表示同意。</span><span class="sxs-lookup"><span data-stu-id="18046-132">This setting must be on to enable team owners to give consent.</span></span> <span data-ttu-id="18046-133">若要管理此设置，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="18046-133">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="18046-134">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **""管理应用**"，然后单击"**组织范围的应用设置"。**</span><span class="sxs-lookup"><span data-stu-id="18046-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
2. <span data-ttu-id="18046-135">在 **"第三方应用"** 下，关闭或打开"**允许第三方应用"。**</span><span class="sxs-lookup"><span data-stu-id="18046-135">Under **Third party apps**, turn off or turn on **Allow third party apps**.</span></span>

    !["允许在 Teams 中允许第三方应用"设置的屏幕截图](media/resource-specific-consent-org-wide-setting.png)

<span data-ttu-id="18046-137">最长可能需要等待 24 小时，更改才会生效。</span><span class="sxs-lookup"><span data-stu-id="18046-137">You may have to wait up to 24 hours for your changes to take effect.</span></span>

#### <a name="allow-or-block-the-app-at-the-org-level"></a><span data-ttu-id="18046-138">在组织级别允许或阻止应用</span><span class="sxs-lookup"><span data-stu-id="18046-138">Allow or block the app at the org level</span></span>

<span data-ttu-id="18046-139">在"管理应用"页面上阻止或允许[](manage-apps.md#allow-and-block-apps)应用时，将阻止或允许组织中所有用户使用该应用。</span><span class="sxs-lookup"><span data-stu-id="18046-139">When you block or allow an app on the [Manage apps](manage-apps.md#allow-and-block-apps) page, that app is blocked or allowed for all users in your organization.</span></span> <span data-ttu-id="18046-140">只有在允许应用的情况下，团队所有者才能许可应用。</span><span class="sxs-lookup"><span data-stu-id="18046-140">Team owners can only give consent to an app if the app is allowed.</span></span> <span data-ttu-id="18046-141">若要在组织级别允许或阻止应用，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="18046-141">To allow or block an app at the org level, do the following:</span></span>

1. <span data-ttu-id="18046-142">在 Microsoft Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**管理应用**”。</span><span class="sxs-lookup"><span data-stu-id="18046-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="18046-143">在"管理应用"页面上，选择应用，然后单击"阻止"以阻止它 **或单击"** 允许"以允许它。</span><span class="sxs-lookup"><span data-stu-id="18046-143">On the Manage apps page, select the app, and then click **Block** to block it or click **Allow** to allow it.</span></span>

    ![组织范围内设置中阻止的应用的屏幕截图](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a><span data-ttu-id="18046-145">分配给团队所有者的应用权限策略</span><span class="sxs-lookup"><span data-stu-id="18046-145">App permission policy assigned to the team owner</span></span>

<span data-ttu-id="18046-146">团队所有者只能同意应用其应用权限策略允许其运行。</span><span class="sxs-lookup"><span data-stu-id="18046-146">Team owners can only give consent to apps that their app permission policy allows them to run.</span></span> <span data-ttu-id="18046-147">若要查看和管理分配给团队所有者的应用权限策略，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="18046-147">To view and manage the app permission policy that's assigned to a team owner, do the following:</span></span>

1. <span data-ttu-id="18046-148">在 Microsoft Teams 管理中心的左侧导航栏中，转到"用户 **"。**</span><span class="sxs-lookup"><span data-stu-id="18046-148">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="18046-149">双击团队所有者显示名称，然后单击"策略 **"。**</span><span class="sxs-lookup"><span data-stu-id="18046-149">Double-click the display name of the team owner, and then click **Policies**.</span></span>
3. <span data-ttu-id="18046-150">分配给团队所有者的策略列在"应用权限 **策略"下**。</span><span class="sxs-lookup"><span data-stu-id="18046-150">The policy assigned to the team owner is listed under **App permission policy**.</span></span>
    - <span data-ttu-id="18046-151">若要分配其他策略，请单击" **编辑**"，然后选择要分配的策略。</span><span class="sxs-lookup"><span data-stu-id="18046-151">To assign a different policy, click **Edit**, and then select the policy that you want to assign.</span></span>
    - <span data-ttu-id="18046-152">若要编辑分配给团队所有者的策略设置，请单击策略名称，然后进行您需要的更改。</span><span class="sxs-lookup"><span data-stu-id="18046-152">To edit the settings of the policy that's assigned to the team owner, click the policy name, and then make the changes that you want.</span></span>  

## <a name="uploading-custom-apps"></a><span data-ttu-id="18046-153">上传自定义应用</span><span class="sxs-lookup"><span data-stu-id="18046-153">Uploading custom apps</span></span>

<span data-ttu-id="18046-154">上传自定义应用 (使用特定于资源) 的旁加载应用时，应用必须来自它要安装到的租户。</span><span class="sxs-lookup"><span data-stu-id="18046-154">When uploading a custom app (also known sideloading) that uses resource-specific consent, the app must come from the tenant that it's being installed to.</span></span> <span data-ttu-id="18046-155">换句话说，Azure AD 应用注册必须来自此租户。</span><span class="sxs-lookup"><span data-stu-id="18046-155">In other words, the Azure AD app registration must be from this tenant.</span></span> <span data-ttu-id="18046-156">全局管理员不受此限制，可以直接将自定义应用从任何租户上传到团队 (旁加载) 或租户应用目录。</span><span class="sxs-lookup"><span data-stu-id="18046-156">Global admins are exempted from this restriction, and can upload custom apps from any tenant, either directly to a team (sideloading) or to the tenant app catalog.</span></span>

## <a name="related-topics"></a><span data-ttu-id="18046-157">相关主题</span><span class="sxs-lookup"><span data-stu-id="18046-157">Related topics</span></span>

- [<span data-ttu-id="18046-158">可用的 RSC 权限</span><span class="sxs-lookup"><span data-stu-id="18046-158">Available RSC permissions</span></span>](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [<span data-ttu-id="18046-159">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="18046-159">Microsoft Graph</span></span>](https://developer.microsoft.com/graph)
- [<span data-ttu-id="18046-160">在 Microsoft Teams 管理中心管理应用</span><span class="sxs-lookup"><span data-stu-id="18046-160">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="18046-161">在 Teams 中管理应用权限策略</span><span class="sxs-lookup"><span data-stu-id="18046-161">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)