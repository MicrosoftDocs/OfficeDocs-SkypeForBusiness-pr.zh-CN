---
title: 在管理中心查看应用权限Microsoft Teams管理员许可
author: cichur
ms.author: v-cichur
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在管理中心的"管理应用"页面上查看应用请求的权限并授予Microsoft Teams许可。
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2833a548ccf66b327d9feb71155f1ed33a671f1c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094654"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="fc29c-103">在管理中心查看应用权限Microsoft Teams管理员许可</span><span class="sxs-lookup"><span data-stu-id="fc29c-103">View app permissions and grant admin consent in the Microsoft Teams admin center</span></span>

<span data-ttu-id="fc29c-104">管理[中心中的](manage-apps.md)"Microsoft Teams"页面是查看和管理组织Teams应用的地方。</span><span class="sxs-lookup"><span data-stu-id="fc29c-104">The [Manage apps](manage-apps.md) page in the Microsoft Teams admin center is where you view and manage all Teams apps for your organization.</span></span> <span data-ttu-id="fc29c-105">例如，可以看到应用的组织级状态和属性、批准新的自定义应用或将其上载到组织的应用商店、在组织级别阻止或允许应用，以及管理组织范围内的应用设置。</span><span class="sxs-lookup"><span data-stu-id="fc29c-105">For example, you can see the org-level status and properties of apps, approve or upload new custom apps to your organization's app store, block or allow apps at the org level, and manage org-wide app settings.</span></span>

<span data-ttu-id="fc29c-106">在此处，还可以向请求访问数据和查看资源特定许可权限的应用授予组织范围的管理员许可， (RSC) 权限。</span><span class="sxs-lookup"><span data-stu-id="fc29c-106">Here, you can also grant org-wide admin consent to apps that request permissions to access data and view resource-specific consent (RSC) permissions for apps.</span></span>

## <a name="grant-org-wide-admin-consent-to-an-app"></a><span data-ttu-id="fc29c-107">向应用授予组织范围的管理员许可</span><span class="sxs-lookup"><span data-stu-id="fc29c-107">Grant org-wide admin consent to an app</span></span>

<span data-ttu-id="fc29c-108">如果你是全局管理员，你可以查看并许可代表组织中所有用户请求权限的应用。</span><span class="sxs-lookup"><span data-stu-id="fc29c-108">If you're a global admin, you can review and grant consent to apps that request permissions on behalf of all users in your organization.</span></span> <span data-ttu-id="fc29c-109">你这样做，以便用户不必在启动应用时查看并接受应用请求的权限。</span><span class="sxs-lookup"><span data-stu-id="fc29c-109">You do this so that users don't have to review and accept the permissions requested by the app when they start the app.</span></span> <span data-ttu-id="fc29c-110">此外，根据 Azure AD [](/azure/active-directory/manage-apps/configure-user-consent) Azure Active Directory (中的用户) ，某些用户可能无法向访问公司数据的应用授予许可。</span><span class="sxs-lookup"><span data-stu-id="fc29c-110">Additionally, depending on the user's [consent settings](/azure/active-directory/manage-apps/configure-user-consent) in Azure Active Directory (Azure AD), some users may not be allowed to grant consent to apps that access company data.</span></span>

<span data-ttu-id="fc29c-111">应用请求的权限示例包括读取团队中存储的信息、读取用户的个人资料以及代表用户发送电子邮件的能力。</span><span class="sxs-lookup"><span data-stu-id="fc29c-111">Examples of permissions requested by apps include the ability to read information stored in a team, read a user's profile, and send an email on behalf of users.</span></span> <span data-ttu-id="fc29c-112">有关详细信息，请参阅终结点 中[的权限Microsoft 标识平台许可](/azure/active-directory/develop/v2-permissions-and-consent)。</span><span class="sxs-lookup"><span data-stu-id="fc29c-112">To learn more, see [Permissions and consent in the Microsoft identity platform endpoint](/azure/active-directory/develop/v2-permissions-and-consent).</span></span> 

<span data-ttu-id="fc29c-113">" **权限"** 列指示应用是否具有需要许可的权限。</span><span class="sxs-lookup"><span data-stu-id="fc29c-113">The **Permissions** column indicates whether an app has permissions that need consent.</span></span> <span data-ttu-id="fc29c-114">对于在 Azure  AD 中注册并拥有需要许可的权限的每个应用，你将看到"查看详细信息"链接。</span><span class="sxs-lookup"><span data-stu-id="fc29c-114">You'll see a **View details** link for each app registered in Azure AD that has permissions that need consent.</span></span> <span data-ttu-id="fc29c-115">请记住，这仅适用于自定义和第三方应用。</span><span class="sxs-lookup"><span data-stu-id="fc29c-115">Keep in mind that this applies only to custom and third-party apps.</span></span> <span data-ttu-id="fc29c-116">你不会看到此链接，也不需要为 Microsoft 发布的应用授予管理员许可。</span><span class="sxs-lookup"><span data-stu-id="fc29c-116">You won't see this link or need to grant admin consent for apps published by Microsoft.</span></span>

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="管理应用页面上权限列的屏幕截图":::

<span data-ttu-id="fc29c-118">若要向应用授予组织范围许可，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="fc29c-118">To grant org-wide consent to an app, follow these steps:</span></span>

1. <span data-ttu-id="fc29c-119">在 Microsoft Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**管理应用**”。</span><span class="sxs-lookup"><span data-stu-id="fc29c-119">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="fc29c-120">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="fc29c-120">Do one of the following:</span></span>
    - <span data-ttu-id="fc29c-121">搜索所需的应用，单击应用名称转到应用详细信息页，然后选择" **权限"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="fc29c-121">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
    - <span data-ttu-id="fc29c-122">按降 **序对**"权限"列进行排序以查找应用，然后选择"**查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="fc29c-122">Sort the **Permissions** column in descending order to find the app, and then select **View details**.</span></span> <span data-ttu-id="fc29c-123">执行此操作会你将访问 **应用详细信息页** 的"权限"选项卡。</span><span class="sxs-lookup"><span data-stu-id="fc29c-123">Doing this takes you to the **Permissions** tab of the app details page.</span></span>

3. <span data-ttu-id="fc29c-124">在 **"组织范围的权限"下**，选择 **"审阅权限和同意"。**</span><span class="sxs-lookup"><span data-stu-id="fc29c-124">Under **Org-wide permissions**, select **Review permissions and consent**.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="应用权限选项卡上组织范围内权限的屏幕截图":::

    <span data-ttu-id="fc29c-126">只有全局管理员才能这样做。</span><span class="sxs-lookup"><span data-stu-id="fc29c-126">You must be a global admin to do this.</span></span> <span data-ttu-id="fc29c-127">此选项对服务管理员Teams可用。</span><span class="sxs-lookup"><span data-stu-id="fc29c-127">This option isn't available to Teams service admins.</span></span>

4. <span data-ttu-id="fc29c-128">在 **"权限"** 选项卡上，查看应用请求的权限。</span><span class="sxs-lookup"><span data-stu-id="fc29c-128">On the **Permissions** tab, review the permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="应用请求的权限的屏幕截图":::

    > [!IMPORTANT]
    > <span data-ttu-id="fc29c-130">向应用授予组织范围同意允许应用访问组织的数据。</span><span class="sxs-lookup"><span data-stu-id="fc29c-130">Granting org-wide consent to an app allows the app to access your organization's data.</span></span> <span data-ttu-id="fc29c-131">在授予许可之前，请仔细查看应用请求的权限。</span><span class="sxs-lookup"><span data-stu-id="fc29c-131">Carefully review the permissions requested by the app before you grant consent.</span></span>
5. <span data-ttu-id="fc29c-132">如果你同意应用请求的权限，请单击" **接受"以** 授予同意。</span><span class="sxs-lookup"><span data-stu-id="fc29c-132">If you agree with the permissions requested by the app, click **Accept** to grant consent.</span></span> <span data-ttu-id="fc29c-133">页面顶部临时显示一个横幅，告知你已授予应用所请求的权限。</span><span class="sxs-lookup"><span data-stu-id="fc29c-133">A banner temporarily appears at the top of the page to let you know that the requested permissions have been granted for the app.</span></span> <span data-ttu-id="fc29c-134">应用现在有权访问组织中所有用户的指定资源，系统不会提示任何其他用户查看权限。</span><span class="sxs-lookup"><span data-stu-id="fc29c-134">The app now has access to the specified resources for all users in your organization and no one else will be prompted to review the permissions.</span></span>

<span data-ttu-id="fc29c-135">接受权限后，应用详细信息页面上的" **组织** 范围权限"下会显示一条消息，告知你已授予许可。</span><span class="sxs-lookup"><span data-stu-id="fc29c-135">After you accept the permissions, you'll see a message under **Org-wide permissions** on the app details page to let you know that consent was granted.</span></span> <span data-ttu-id="fc29c-136">若要查看有关应用权限的详细信息，请单击"Azure Active Directory"链接以转到Azure AD 门户中应用的页面。</span><span class="sxs-lookup"><span data-stu-id="fc29c-136">To view details about the app's permissions, click the **Azure Active Directory** link to go to the app's page in the Azure AD portal.</span></span>

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="授予许可时显示的消息的屏幕截图":::

<span data-ttu-id="fc29c-138">如果允许组织中用户授予许可，并且如果一个或多个用户授予了对特定应用的同意，则还会看到相同的消息，告知你已授予许可，以及 Azure AD 门户中该应用页面的 Azure Active Directory 链接。</span><span class="sxs-lookup"><span data-stu-id="fc29c-138">If users in your organization are allowed to grant consent and if one or more users granted consent to a particular app, you'll also see the same message to let you know that consent was granted and the Azure Active Directory link to the app's page in the Azure AD portal.</span></span>

> [!NOTE]
> <span data-ttu-id="fc29c-139">尽管"审阅权限和许可"选项不可用于 Teams 服务管理员，并且他们无法向应用授予组织范围的管理员许可，但 Teams 服务管理员可以在应用的"权限"选项卡上查看内容。 </span><span class="sxs-lookup"><span data-stu-id="fc29c-139">Although, the **Review permissions and consent** option isn't available to Teams service admins and they can't grant org-wide admin consent to apps, Teams service admins can view the content on the **Permissions** tab for an app.</span></span> <span data-ttu-id="fc29c-140">例如，Teams服务管理员可以单击"Azure Active Directory"链接，在Azure AD 门户中查看应用权限详细信息。</span><span class="sxs-lookup"><span data-stu-id="fc29c-140">For example, a Teams service admin can click the **Azure Active Directory** link to view app permissions details in the Azure AD portal.</span></span> 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a><span data-ttu-id="fc29c-141">查看应用的资源特定许可权限</span><span class="sxs-lookup"><span data-stu-id="fc29c-141">View resource-specific consent permissions of an app</span></span>

<span data-ttu-id="fc29c-142">RSC 权限允许团队所有者授予应用访问和修改团队数据的许可。</span><span class="sxs-lookup"><span data-stu-id="fc29c-142">RSC permissions let team owners grant consent for an app to access and modify a team's data.</span></span> <span data-ttu-id="fc29c-143">RSC 权限是Teams特定权限，用于定义应用可在特定团队中执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="fc29c-143">RSC permissions are granular, Teams-specific permissions that define what an app can do in a specific team.</span></span> <span data-ttu-id="fc29c-144">RSC 权限的示例包括创建和删除频道、获取团队设置以及创建和删除频道选项卡的功能。</span><span class="sxs-lookup"><span data-stu-id="fc29c-144">Examples of RSC permissions include the ability to create and delete channels, get the settings for a team, and create and remove channel tabs.</span></span> 

<span data-ttu-id="fc29c-145">RSC 权限在应用清单中定义，而不是在 Azure AD 中定义。</span><span class="sxs-lookup"><span data-stu-id="fc29c-145">RSC permissions are defined in the app manifest and not in Azure AD.</span></span> <span data-ttu-id="fc29c-146">将应用添加到团队时，需要授予对 RSC 权限的许可。</span><span class="sxs-lookup"><span data-stu-id="fc29c-146">You grant consent to RSC permissions when you add the app to a team.</span></span> <span data-ttu-id="fc29c-147">有关详细信息，请参阅 [RSC ](/microsoftteams/platform/graph-api/rsc/resource-specific-consent) (资源) 。</span><span class="sxs-lookup"><span data-stu-id="fc29c-147">To learn more, see [Resource-specific consent (RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent).</span></span>

<span data-ttu-id="fc29c-148">全局管理员Teams服务管理员可以在应用详细信息页的"权限"选项卡上查看应用的 RSC权限。</span><span class="sxs-lookup"><span data-stu-id="fc29c-148">Global admins and Teams service admin can view RSC permissions for an app on the **Permissions** tab of the app details page.</span></span> 

<span data-ttu-id="fc29c-149">若要查看应用的 RSC 权限，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="fc29c-149">To view RSC permissions for an app, follow these steps:</span></span>

1. <span data-ttu-id="fc29c-150">在 Microsoft Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**管理应用**”。</span><span class="sxs-lookup"><span data-stu-id="fc29c-150">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="fc29c-151">搜索所需的应用，单击应用名称转到应用详细信息页，然后选择" **权限"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="fc29c-151">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
3. <span data-ttu-id="fc29c-152">在 **"Microsoft Graph RSC** (许可) 下，查看应用请求的 RSC 权限。</span><span class="sxs-lookup"><span data-stu-id="fc29c-152">Under **Microsoft Graph resource-specific consent (RSC) permissions**, review the RSC permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="应用的 RSC 权限屏幕截图":::

## <a name="known-issues"></a><span data-ttu-id="fc29c-154">已知问题</span><span class="sxs-lookup"><span data-stu-id="fc29c-154">Known issues</span></span>

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a><span data-ttu-id="fc29c-155">某些请求权限的第三方应用的"权限"列中不显示"查看详细信息"链接</span><span class="sxs-lookup"><span data-stu-id="fc29c-155">The "View details" link isn't displayed in the Permissions column for some third-party apps that request permissions</span></span>

<span data-ttu-id="fc29c-156">目前，在 Azure AD 中注册的所有请求权限的第三方应用无法查看权限和授予许可。</span><span class="sxs-lookup"><span data-stu-id="fc29c-156">Currently, the ability to review permissions and grant consent isn't available for all third-party apps registered in Azure AD that request permissions.</span></span> <span data-ttu-id="fc29c-157">你将在 **"权限"** 列中看到，而不是" **--** 查看 **详细信息"** 链接。</span><span class="sxs-lookup"><span data-stu-id="fc29c-157">Instead of the **View details** link, you'll see **--** in the **Permissions** column.</span></span> <span data-ttu-id="fc29c-158">我们正在与 ISV 合作，为应用启用此功能。</span><span class="sxs-lookup"><span data-stu-id="fc29c-158">We're working with ISVs to enable this feature for their apps.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fc29c-159">相关主题</span><span class="sxs-lookup"><span data-stu-id="fc29c-159">Related topics</span></span>

- [<span data-ttu-id="fc29c-160">在管理中心内Microsoft Teams应用</span><span class="sxs-lookup"><span data-stu-id="fc29c-160">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="fc29c-161">终结点中的权限Microsoft 标识平台许可</span><span class="sxs-lookup"><span data-stu-id="fc29c-161">Permissions and consent in the Microsoft identity platform endpoint</span></span>](/azure/active-directory/develop/v2-permissions-and-consent)
- [<span data-ttu-id="fc29c-162">资源特定的许可Teams</span><span class="sxs-lookup"><span data-stu-id="fc29c-162">Resource-specific consent in Teams</span></span>](resource-specific-consent.md)
- [<span data-ttu-id="fc29c-163">RSC (特定于资源) </span><span class="sxs-lookup"><span data-stu-id="fc29c-163">Resource-specific consent (RSC)</span></span>](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- <span data-ttu-id="fc29c-164">[在](https://aka.ms/PR132)Ignite 2020 Teams应用生命周期 (导航) </span><span class="sxs-lookup"><span data-stu-id="fc29c-164">[Navigating the Teams app lifecycle](https://aka.ms/PR132) (Ignite 2020 session)</span></span>