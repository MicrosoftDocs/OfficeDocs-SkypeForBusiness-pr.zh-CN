---
title: 查看应用权限并授予 Microsoft 团队管理中心的管理员同意
author: LanaChin
ms.author: v-lanac
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何查看应用请求的权限，并向 Microsoft 团队管理中心的 "管理应用" 页面上的应用授予管理员同意。
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 104dab27af75d346af990369ee78fc2fb1f0a77d
ms.sourcegitcommit: fd7d5ba09ef30cf4594e352c36f62b950e0e41a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2020
ms.locfileid: "48336839"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="37211-103">查看应用权限并授予 Microsoft 团队管理中心的管理员同意</span><span class="sxs-lookup"><span data-stu-id="37211-103">View app permissions and grant admin consent in the Microsoft Teams admin center</span></span>

<span data-ttu-id="37211-104">Microsoft 团队管理中心中的 " [管理应用](manage-apps.md) " 页面是你查看和管理你的组织的所有团队应用的位置。</span><span class="sxs-lookup"><span data-stu-id="37211-104">The [Manage apps](manage-apps.md) page in the Microsoft Teams admin center is where you view and manage all Teams apps for your organization.</span></span> <span data-ttu-id="37211-105">例如，你可以查看应用的组织级别状态和属性、批准或将新的自定义应用上载到你的组织的应用商店、阻止或允许组织级别的应用，以及管理组织范围内的应用设置。</span><span class="sxs-lookup"><span data-stu-id="37211-105">For example, you can see the org-level status and properties of apps, approve or upload new custom apps to your organization's app store, block or allow apps at the org level, and manage org-wide app settings.</span></span>

<span data-ttu-id="37211-106">在此处，你还可以授予组织范围内管理员同意请求访问数据的权限的应用，并查看特定于资源的同意 (RSC) 应用的权限。</span><span class="sxs-lookup"><span data-stu-id="37211-106">Here, you can also grant org-wide admin consent to apps that request permissions to access data and view resource-specific consent (RSC) permissions for apps.</span></span>

## <a name="grant-org-wide-admin-consent-to-an-app"></a><span data-ttu-id="37211-107">向应用程序授予组织范围内管理员许可</span><span class="sxs-lookup"><span data-stu-id="37211-107">Grant org-wide admin consent to an app</span></span>

<span data-ttu-id="37211-108">如果您是全局管理员，您可以查看并同意代表您组织中的所有用户请求权限的应用。</span><span class="sxs-lookup"><span data-stu-id="37211-108">If you're a global admin, you can review and grant consent to apps that request permissions on behalf of all users in your organization.</span></span> <span data-ttu-id="37211-109">这样做的目的是，用户在启动应用时不必查看和接受应用请求的权限。</span><span class="sxs-lookup"><span data-stu-id="37211-109">You do this so that users don't have to review and accept the permissions requested by the app when they start the app.</span></span> <span data-ttu-id="37211-110">此外，根据用户在 Azure Active Directory (Azure AD) 中的 [同意设置](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) ，某些用户可能不允许向访问公司数据的应用授予许可。</span><span class="sxs-lookup"><span data-stu-id="37211-110">Additionally, depending on the user's [consent settings](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) in Azure Active Directory (Azure AD), some users may not be allowed to grant consent to apps that access company data.</span></span>

<span data-ttu-id="37211-111">应用程序请求的权限的示例包括读取存储在团队中的信息、读取用户的配置文件以及代表用户发送电子邮件的功能。</span><span class="sxs-lookup"><span data-stu-id="37211-111">Examples of permissions requested by apps include the ability to read information stored in a team, read a user's profile, and send an email on behalf of users.</span></span> <span data-ttu-id="37211-112">若要了解详细信息，请参阅 [Microsoft 标识平台终结点中的权限和同意](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)。</span><span class="sxs-lookup"><span data-stu-id="37211-112">To learn more, see [Permissions and consent in the Microsoft identity platform endpoint](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent).</span></span> 

<span data-ttu-id="37211-113">" **权限** " 列指示应用是否具有需要同意的权限。</span><span class="sxs-lookup"><span data-stu-id="37211-113">The **Permissions** column indicates whether an app has permissions that need consent.</span></span> <span data-ttu-id="37211-114">你将看到在 Azure AD 中注册的每个应用的 " **查看详细信息** " 链接，该链接具有需要同意的权限。</span><span class="sxs-lookup"><span data-stu-id="37211-114">You'll see a **View details** link for each app registered in Azure AD that has permissions that need consent.</span></span> <span data-ttu-id="37211-115">请记住，这仅适用于自定义应用程序和第三方应用和。</span><span class="sxs-lookup"><span data-stu-id="37211-115">Keep in mind that this applies only to custom and third-party apps and.</span></span> <span data-ttu-id="37211-116">您将看不到此链接，也不需要授予由 Microsoft 发布的应用的管理员同意。</span><span class="sxs-lookup"><span data-stu-id="37211-116">You won't see this link or need to grant admin consent for apps published by Microsoft.</span></span>

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text=""管理应用" 页面上的 "权限" 列的屏幕截图":::

<span data-ttu-id="37211-118">若要向应用授予组织范围内同意，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="37211-118">To grant org-wide consent to an app, follow these steps:</span></span>

1. <span data-ttu-id="37211-119">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **管理应用**"。</span><span class="sxs-lookup"><span data-stu-id="37211-119">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="37211-120">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="37211-120">Do one of the following:</span></span>
    - <span data-ttu-id="37211-121">搜索所需的应用，单击应用名称转到 "应用详细信息" 页面，然后选择 " **权限** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="37211-121">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
    - <span data-ttu-id="37211-122">按降序对 " **权限** " 列进行排序以查找应用，然后选择 " **查看详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="37211-122">Sort the **Permissions** column in descending order to find the app, and then select **View details**.</span></span> <span data-ttu-id="37211-123">执行此操作将转到 "应用详细信息" 页面的 " **权限** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="37211-123">Doing this takes you to the **Permissions** tab of the app details page.</span></span>

3. <span data-ttu-id="37211-124">在 " **组织范围的权限**" 下，选择 " **审阅权限和同意**"。</span><span class="sxs-lookup"><span data-stu-id="37211-124">Under **Org-wide permissions**, select **Review permissions and consent**.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="应用的 "权限" 选项卡上组织范围权限的屏幕截图":::

    <span data-ttu-id="37211-126">只有全局管理员才能执行此操作。</span><span class="sxs-lookup"><span data-stu-id="37211-126">You must be a global admin to do this.</span></span> <span data-ttu-id="37211-127">团队服务管理员无法使用此选项。</span><span class="sxs-lookup"><span data-stu-id="37211-127">This option isn't available to Teams service admins.</span></span>

4. <span data-ttu-id="37211-128">在 " **权限** " 选项卡上，查看应用请求的权限。</span><span class="sxs-lookup"><span data-stu-id="37211-128">On the **Permissions** tab, review the permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="应用请求的权限的屏幕截图":::

    > [!IMPORTANT]
    > <span data-ttu-id="37211-130">授予应用的组织范围同意允许应用访问你的组织的数据。</span><span class="sxs-lookup"><span data-stu-id="37211-130">Granting org-wide consent to an app allows the app to access your organization's data.</span></span> <span data-ttu-id="37211-131">在授予同意之前，请仔细查看该应用请求的权限。</span><span class="sxs-lookup"><span data-stu-id="37211-131">Carefully review the permissions requested by the app before you grant consent.</span></span>
5. <span data-ttu-id="37211-132">如果你同意应用请求的权限，请单击 " **接受** " 以授予同意。</span><span class="sxs-lookup"><span data-stu-id="37211-132">If you agree with the permissions requested by the app, click **Accept** to grant consent.</span></span> <span data-ttu-id="37211-133">标题会暂时显示在页面顶部，让你知道所请求的权限已被授予应用。</span><span class="sxs-lookup"><span data-stu-id="37211-133">A banner temporarily appears at the top of the page to let you know that the requested permissions have been granted for the app.</span></span> <span data-ttu-id="37211-134">应用现在可以访问组织中所有用户的指定资源，并且不会提示任何其他人查看权限。</span><span class="sxs-lookup"><span data-stu-id="37211-134">The app now has access to the specified resources for all users in your organization and no one else will be prompted to review the permissions.</span></span>

<span data-ttu-id="37211-135">接受权限后，你将在 "应用详细信息" 页面上的 " **组织范围的权限** " 下看到一条消息，告知已授予同意。</span><span class="sxs-lookup"><span data-stu-id="37211-135">After you accept the permissions, you'll see a message under **Org-wide permissions** on the app details page to let you know that consent was granted.</span></span> <span data-ttu-id="37211-136">若要查看有关应用权限的详细信息，请单击 **Azure Active Directory** 链接以转到 Azure AD 门户中的应用页面。</span><span class="sxs-lookup"><span data-stu-id="37211-136">To view details about the app's permissions, click the **Azure Active Directory** link to go to the app's page in the Azure AD portal.</span></span>

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="已授予同意时显示的消息的屏幕截图":::

<span data-ttu-id="37211-138">如果你的组织中的用户允许授予同意，并且如果一个或多个用户授予了特定应用的同意，你还将看到相同的消息，告知你同意已授予同意，并且 Azure Active Directory 链接指向 Azure AD 门户中的应用页面。</span><span class="sxs-lookup"><span data-stu-id="37211-138">If users in your organization are allowed to grant consent and if one or more users granted consent to a particular app, you'll also see the same message to let you know that consent was granted and the Azure Active Directory link to the app's page in the Azure AD portal.</span></span>

> [!NOTE]
> <span data-ttu-id="37211-139">尽管 " **审阅权限和同意** " 选项对于团队服务管理员不可用，并且不能授予组织范围内管理员同意应用的权限，但团队服务管理员可以查看应用的 " **权限** " 选项卡上的内容。</span><span class="sxs-lookup"><span data-stu-id="37211-139">Although, the **Review permissions and consent** option isn't available to Teams service admins and they can't grant org-wide admin consent to apps, Teams service admins can view the content on the **Permissions** tab for an app.</span></span> <span data-ttu-id="37211-140">例如，团队服务管理员可以单击 **Azure Active Directory** 链接以在 azure AD 门户中查看应用权限详细信息。</span><span class="sxs-lookup"><span data-stu-id="37211-140">For example, a Teams service admin can click the **Azure Active Directory** link to view app permissions details in the Azure AD portal.</span></span> 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a><span data-ttu-id="37211-141">查看应用的特定于资源的同意权限</span><span class="sxs-lookup"><span data-stu-id="37211-141">View resource-specific consent permissions of an app</span></span>

<span data-ttu-id="37211-142">RSC 权限允许团队所有者授予应用访问和修改团队数据的同意。</span><span class="sxs-lookup"><span data-stu-id="37211-142">RSC permissions let team owners grant consent for an app to access and modify a team's data.</span></span> <span data-ttu-id="37211-143">RSC 权限是特定于团队的权限，用于定义应用在特定团队中可以执行的操作。</span><span class="sxs-lookup"><span data-stu-id="37211-143">RSC permissions are granular, Teams-specific permissions that define what an app can do in a specific team.</span></span> <span data-ttu-id="37211-144">RSC 权限的示例包括创建和删除频道、获取团队设置以及创建和删除频道选项卡的功能。</span><span class="sxs-lookup"><span data-stu-id="37211-144">Examples of RSC permissions include the ability to create and delete channels, get the settings for a team, and create and remove channel tabs.</span></span> 

<span data-ttu-id="37211-145">RSC 权限在应用清单中定义，而不是在 Azure AD 中定义。</span><span class="sxs-lookup"><span data-stu-id="37211-145">RSC permissions are defined in the app manifest and not in Azure AD.</span></span> <span data-ttu-id="37211-146">将应用添加到团队时，应授予对 RSC 权限的同意。</span><span class="sxs-lookup"><span data-stu-id="37211-146">You grant consent to RSC permissions when you add the app to a team.</span></span> <span data-ttu-id="37211-147">若要了解详细信息，请参阅 [特定于资源的同意 (RSC) ](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)。</span><span class="sxs-lookup"><span data-stu-id="37211-147">To learn more, see [Resource-specific consent (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent).</span></span>

<span data-ttu-id="37211-148">全局管理员和团队服务管理员可以在应用详细信息页面的 " **权限** " 选项卡上查看应用的 RSC 权限。</span><span class="sxs-lookup"><span data-stu-id="37211-148">Global admins and Teams service admin can view RSC permissions for an app on the **Permissions** tab of the app details page.</span></span> 

<span data-ttu-id="37211-149">若要查看应用的 RSC 权限，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="37211-149">To view RSC permissions for an app, follow these steps:</span></span>

1. <span data-ttu-id="37211-150">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **管理应用**"。</span><span class="sxs-lookup"><span data-stu-id="37211-150">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="37211-151">搜索所需的应用，单击应用名称转到 "应用详细信息" 页面，然后选择 " **权限** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="37211-151">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
3. <span data-ttu-id="37211-152">在 " **Microsoft Graph 特定于资源的同意" (RSC) 权限**中，查看应用请求的 RSC 权限。</span><span class="sxs-lookup"><span data-stu-id="37211-152">Under **Microsoft Graph resource-specific consent (RSC) permissions**, review the RSC permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="应用的 RSC 权限的屏幕截图":::

## <a name="known-issues"></a><span data-ttu-id="37211-154">已知问题</span><span class="sxs-lookup"><span data-stu-id="37211-154">Known issues</span></span>

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a><span data-ttu-id="37211-155">在请求权限的某些第三方应用的 "权限" 列中不显示 "查看详细信息" 链接</span><span class="sxs-lookup"><span data-stu-id="37211-155">The "View details" link isn't displayed in the Permissions column for some third-party apps that request permissions</span></span>

<span data-ttu-id="37211-156">目前，在 Azure AD 中注册权限的所有第三方应用都无法使用查看权限和授权许可的功能。</span><span class="sxs-lookup"><span data-stu-id="37211-156">Currently, the ability to review permissions and grant consent isn't available for all third-party apps registered in Azure AD that request permissions.</span></span> <span data-ttu-id="37211-157">您将在 "权限" 列中看到，而不是 "**查看详细信息**" 链接 **--** **Permissions** 。</span><span class="sxs-lookup"><span data-stu-id="37211-157">Instead of the **View details** link, you'll see **--** in the **Permissions** column.</span></span> <span data-ttu-id="37211-158">我们正在使用 Isv 为其应用启用此功能。</span><span class="sxs-lookup"><span data-stu-id="37211-158">We're working with ISVs to enable this feature for their apps.</span></span>

## <a name="related-topics"></a><span data-ttu-id="37211-159">相关主题</span><span class="sxs-lookup"><span data-stu-id="37211-159">Related topics</span></span>

- [<span data-ttu-id="37211-160">在 Microsoft 团队管理中心中管理你的应用</span><span class="sxs-lookup"><span data-stu-id="37211-160">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="37211-161">Microsoft 标识平台终结点中的权限和同意</span><span class="sxs-lookup"><span data-stu-id="37211-161">Permissions and consent in the Microsoft identity platform endpoint</span></span>](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [<span data-ttu-id="37211-162">团队中特定于资源的同意</span><span class="sxs-lookup"><span data-stu-id="37211-162">Resource-specific consent in Teams</span></span>](resource-specific-consent.md)
- [<span data-ttu-id="37211-163">特定于资源的同意 (RSC) </span><span class="sxs-lookup"><span data-stu-id="37211-163">Resource-specific consent (RSC)</span></span>](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)


