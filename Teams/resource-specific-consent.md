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
ms.openlocfilehash: d6267f4b42890716ca31fd1b44de435af50ad6ae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815672"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a><span data-ttu-id="4569d-103">Microsoft Teams 中特定于资源的同意</span><span class="sxs-lookup"><span data-stu-id="4569d-103">Resource-specific consent in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="4569d-104">Microsoft Teams 中特定于资源的同意可让团队所有者同意应用访问团队数据。</span><span class="sxs-lookup"><span data-stu-id="4569d-104">Resource-specific consent in Microsoft Teams lets team owners give consent to apps to access team data.</span></span> <span data-ttu-id="4569d-105">此类访问的示例包括读取频道消息、创建和删除频道以及创建和删除频道选项卡的功能。</span><span class="sxs-lookup"><span data-stu-id="4569d-105">Examples of such access include the ability to read channel messages, create and delete channels, and create and remove channel tabs.</span></span>

<span data-ttu-id="4569d-106">作为管理员，你可以控制你的组织的团队所有者是否可以通过使用 Azure Active Directory (Azure AD) PowerShell 模块或 Azure 门户和 Microsoft Teams 管理中心配置的设置来表示同意。</span><span class="sxs-lookup"><span data-stu-id="4569d-106">As an admin, you control whether team owners in your organization can give consent through settings that you configure by using the Azure Active Directory (Azure AD) PowerShell module or the Azure portal and the Microsoft Teams admin center.</span></span>  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a><span data-ttu-id="4569d-107">设置团队所有者是否可以许可应用</span><span class="sxs-lookup"><span data-stu-id="4569d-107">Set whether team owners can give consent to apps</span></span>

<span data-ttu-id="4569d-108">下面是必须设置以控制团队所有者是否可以许可应用的设置。</span><span class="sxs-lookup"><span data-stu-id="4569d-108">Here are the settings that you must set to control whether team owners can give consent to apps.</span></span> <span data-ttu-id="4569d-109">请务必查看以下所有设置。</span><span class="sxs-lookup"><span data-stu-id="4569d-109">Be sure to review all the following settings.</span></span>

### <a name="settings-in-azure-ad"></a><span data-ttu-id="4569d-110">Azure AD 中的设置</span><span class="sxs-lookup"><span data-stu-id="4569d-110">Settings in Azure AD</span></span>

<span data-ttu-id="4569d-111">以下两个设置确定团队所有者是否可以许可应用。</span><span class="sxs-lookup"><span data-stu-id="4569d-111">The following two settings determine whether team owners can give consent to apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4569d-112">更改这些设置不会影响已授予许可的应用的数据访问。</span><span class="sxs-lookup"><span data-stu-id="4569d-112">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="4569d-113">例如，如果将这些设置配置为防止团队所有者表示许可，这些更改不会删除已授予的数据访问。</span><span class="sxs-lookup"><span data-stu-id="4569d-113">For example, if you configure these settings to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a><span data-ttu-id="4569d-114">"用户可以同意应用代表他们访问公司数据"设置</span><span class="sxs-lookup"><span data-stu-id="4569d-114">The "Users can consent to apps accessing company data on their behalf" setting</span></span>

<span data-ttu-id="4569d-115">此设置控制您的组织中的用户是否可以代表他们许可应用。</span><span class="sxs-lookup"><span data-stu-id="4569d-115">This setting controls whether users in your organization can consent to apps on their behalf.</span></span> <span data-ttu-id="4569d-116">若要使团队所有者能够表示同意，必须将此设置设置为 **"是"。**</span><span class="sxs-lookup"><span data-stu-id="4569d-116">To enable team owners to give consent, this setting must be set to **Yes**.</span></span> <span data-ttu-id="4569d-117">若要管理此设置，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="4569d-117">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="4569d-118">在 Azure 门户中，转到 **"企业应用程序**  >  **用户设置"。**</span><span class="sxs-lookup"><span data-stu-id="4569d-118">In the Azure portal, go to **Enterprise applications** > **User settings**.</span></span>
2. <span data-ttu-id="4569d-119">在 **"企业应用程序**"**下，将"用户可以同意** 代表用户访问公司数据的应用"设置为"**否**"或"**是"。**</span><span class="sxs-lookup"><span data-stu-id="4569d-119">Under **Enterprise applications**, set **Users can consent to apps accessing company data on their behalf** to **No** or **Yes**.</span></span>

<span data-ttu-id="4569d-120">也可使用 PowerShell 管理此设置。</span><span class="sxs-lookup"><span data-stu-id="4569d-120">You can also manage this setting using PowerShell.</span></span> <span data-ttu-id="4569d-121">若要了解有关详细信息，请参阅"[为应用程序配置用户内容"。](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)</span><span class="sxs-lookup"><span data-stu-id="4569d-121">To learn more, see [Configure user content to applications](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).</span></span>

#### <a name="the-enablegroupspecificconsent-setting"></a><span data-ttu-id="4569d-122">"EnableGroupSpecificConsent"设置</span><span class="sxs-lookup"><span data-stu-id="4569d-122">The "EnableGroupSpecificConsent" setting</span></span>

<span data-ttu-id="4569d-123">此设置控制您的组织中的用户是否可以同意应用访问他们拥有组的公司数据。</span><span class="sxs-lookup"><span data-stu-id="4569d-123">This setting controls whether users in your organization can consent to apps accessing company data for the groups that they own.</span></span> <span data-ttu-id="4569d-124">必须启用此设置，团队所有者才能表示同意。</span><span class="sxs-lookup"><span data-stu-id="4569d-124">This setting must be enabled for team owners to give consent.</span></span> <span data-ttu-id="4569d-125">有关如何使用 PowerShell 管理此设置的步骤，请参阅"配置组所有者同意[访问组数据的应用"。](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)</span><span class="sxs-lookup"><span data-stu-id="4569d-125">For steps on how to manage this setting by using PowerShell, see [Configure group owner consent to apps accessing group data](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).</span></span>

### <a name="settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="4569d-126">Microsoft Teams 管理中心中的设置</span><span class="sxs-lookup"><span data-stu-id="4569d-126">Settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="4569d-127">除了 Azure AD 中的设置[](manage-apps.md#manage-org-wide-app-settings)外，"管理应用"页面上[](manage-apps.md)的组织范围应用设置、应用在"管理应用"页面上是[](manage-apps.md#allow-and-block-apps)被阻止还是允许，以及分配给团队所有者的应用权限策略决定了团队所有者是否可以同意。 [](teams-app-permission-policies.md)</span><span class="sxs-lookup"><span data-stu-id="4569d-127">In addition to settings in Azure AD, [org-wide app settings](manage-apps.md#manage-org-wide-app-settings) on the [Manage apps](manage-apps.md) page, whether an app is blocked or allowed on the [Manage apps](manage-apps.md#allow-and-block-apps) page, and the [app permission policy](teams-app-permission-policies.md) assigned to the team owner determine whether a team owner can give consent.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4569d-128">更改这些设置不会影响已授予许可的应用的数据访问。</span><span class="sxs-lookup"><span data-stu-id="4569d-128">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="4569d-129">例如，如果在组织范围内禁用第三方应用，或者阻止特定应用以防止团队所有者同意，这些更改不会删除已授予的数据访问权限。</span><span class="sxs-lookup"><span data-stu-id="4569d-129">For example, if you disable third-party apps org-wide or if you block specific apps to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a><span data-ttu-id="4569d-130">组织范围应用设置中的"允许第三方应用"设置</span><span class="sxs-lookup"><span data-stu-id="4569d-130">The "Allow third party apps" setting in org-wide app settings</span></span>

<span data-ttu-id="4569d-131">此组织范围内的应用设置控制组织中的用户是否可以使用第三方应用。</span><span class="sxs-lookup"><span data-stu-id="4569d-131">This org-wide app setting controls whether users in your organization can use third-party apps.</span></span> <span data-ttu-id="4569d-132">必须启用此设置，团队所有者才能表示同意。</span><span class="sxs-lookup"><span data-stu-id="4569d-132">This setting must be on to enable team owners to give consent.</span></span> <span data-ttu-id="4569d-133">若要管理此设置，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="4569d-133">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="4569d-134">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用** 管理应用"，然后单击"  >  **组织范围的应用设置"。**</span><span class="sxs-lookup"><span data-stu-id="4569d-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
2. <span data-ttu-id="4569d-135">在第 **三方应用下**，关闭或打开"允许 **第三方应用"。**</span><span class="sxs-lookup"><span data-stu-id="4569d-135">Under **Third party apps**, turn off or turn on **Allow third party apps**.</span></span>

    !["允许 Teams 中的第三方应用"设置的屏幕截图](media/resource-specific-consent-org-wide-setting.png)

<span data-ttu-id="4569d-137">最长可能需要等待 24 小时，更改才会生效。</span><span class="sxs-lookup"><span data-stu-id="4569d-137">You may have to wait up to 24 hours for your changes to take effect.</span></span>

#### <a name="allow-or-block-the-app-at-the-org-level"></a><span data-ttu-id="4569d-138">在组织级别允许或阻止应用</span><span class="sxs-lookup"><span data-stu-id="4569d-138">Allow or block the app at the org level</span></span>

<span data-ttu-id="4569d-139">当你在"管理应用"页面上阻止或[](manage-apps.md#allow-and-block-apps)允许应用时，将阻止或允许你组织中所有用户使用该应用。</span><span class="sxs-lookup"><span data-stu-id="4569d-139">When you block or allow an app on the [Manage apps](manage-apps.md#allow-and-block-apps) page, that app is blocked or allowed for all users in your organization.</span></span> <span data-ttu-id="4569d-140">如果允许应用，团队所有者只能同意应用。</span><span class="sxs-lookup"><span data-stu-id="4569d-140">Team owners can only give consent to an app if the app is allowed.</span></span> <span data-ttu-id="4569d-141">若要在组织级别允许或阻止应用，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="4569d-141">To allow or block an app at the org level, do the following:</span></span>

1. <span data-ttu-id="4569d-142">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **管理应用"。**</span><span class="sxs-lookup"><span data-stu-id="4569d-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="4569d-143">在"管理应用"页面上，选择应用，然后单击"阻止"以阻止它 **或单击"** 允许"以允许它。</span><span class="sxs-lookup"><span data-stu-id="4569d-143">On the Manage apps page, select the app, and then click **Block** to block it or click **Allow** to allow it.</span></span>

    ![组织范围内设置中阻止的应用的屏幕截图](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a><span data-ttu-id="4569d-145">分配给团队所有者的应用权限策略</span><span class="sxs-lookup"><span data-stu-id="4569d-145">App permission policy assigned to the team owner</span></span>

<span data-ttu-id="4569d-146">团队所有者只能同意应用其应用权限策略允许其运行。</span><span class="sxs-lookup"><span data-stu-id="4569d-146">Team owners can only give consent to apps that their app permission policy allows them to run.</span></span> <span data-ttu-id="4569d-147">若要查看和管理分配给团队所有者的应用权限策略，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="4569d-147">To view and manage the app permission policy that's assigned to a team owner, do the following:</span></span>

1. <span data-ttu-id="4569d-148">在 Microsoft Teams 管理中心的左侧导航中，转到"**用户"。**</span><span class="sxs-lookup"><span data-stu-id="4569d-148">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="4569d-149">双击团队显示名称，然后单击"策略 **"。**</span><span class="sxs-lookup"><span data-stu-id="4569d-149">Double-click the display name of the team owner, and then click **Policies**.</span></span>
3. <span data-ttu-id="4569d-150">分配给团队所有者的策略列在应用权限 **策略下**。</span><span class="sxs-lookup"><span data-stu-id="4569d-150">The policy assigned to the team owner is listed under **App permission policy**.</span></span>
    - <span data-ttu-id="4569d-151">若要分配其他策略，请单击"编辑"，然后选择要分配的策略。</span><span class="sxs-lookup"><span data-stu-id="4569d-151">To assign a different policy, click **Edit**, and then select the policy that you want to assign.</span></span>
    - <span data-ttu-id="4569d-152">若要编辑分配给团队所有者的策略设置，请单击策略名称，然后进行想要的更改。</span><span class="sxs-lookup"><span data-stu-id="4569d-152">To edit the settings of the policy that's assigned to the team owner, click the policy name, and then make the changes that you want.</span></span>  

## <a name="uploading-custom-apps"></a><span data-ttu-id="4569d-153">上传自定义应用</span><span class="sxs-lookup"><span data-stu-id="4569d-153">Uploading custom apps</span></span>

<span data-ttu-id="4569d-154">在将自定义应用 (也) 资源特定许可的旁加载应用时，应用必须来自它要安装到的租户。</span><span class="sxs-lookup"><span data-stu-id="4569d-154">When uploading a custom app (also known sideloading) that uses resource-specific consent, the app must come from the tenant that it's being installed to.</span></span> <span data-ttu-id="4569d-155">换句话说，Azure AD 应用注册必须来自此租户。</span><span class="sxs-lookup"><span data-stu-id="4569d-155">In other words, the Azure AD app registration must be from this tenant.</span></span> <span data-ttu-id="4569d-156">全局管理员不受此限制限制，可以直接将自定义应用从任何租户上传到团队 (旁加载) 或租户应用目录。</span><span class="sxs-lookup"><span data-stu-id="4569d-156">Global admins are exempted from this restriction, and can upload custom apps from any tenant, either directly to a team (sideloading) or to the tenant app catalog.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4569d-157">相关主题</span><span class="sxs-lookup"><span data-stu-id="4569d-157">Related topics</span></span>

- [<span data-ttu-id="4569d-158">可用的 RSC 权限</span><span class="sxs-lookup"><span data-stu-id="4569d-158">Available RSC permissions</span></span>](https://aka.ms/teams-rsc)
- [<span data-ttu-id="4569d-159">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="4569d-159">Microsoft Graph</span></span>](https://developer.microsoft.com/graph)
- [<span data-ttu-id="4569d-160">在 Microsoft Teams 管理中心管理应用</span><span class="sxs-lookup"><span data-stu-id="4569d-160">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="4569d-161">在 Teams 中管理应用权限策略</span><span class="sxs-lookup"><span data-stu-id="4569d-161">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
