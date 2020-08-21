---
title: 在 Microsoft Teams 管理中心查看应用权限并授予管理员许可
author: LanaChin
ms.author: v-lanac
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何查看应用请求的权限，以及在 Microsoft Teams 管理中心的"管理应用"页面上向应用授予管理员许可。
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 6aafd5cbdd1ae44844f69b78234f10a54abe7b85
ms.sourcegitcommit: bb5229c9f7999358dcf0ba185ecfd7c881627a38
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46824903"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="bcfc2-103">在 Microsoft Teams 管理中心查看应用权限并授予管理员许可</span><span class="sxs-lookup"><span data-stu-id="bcfc2-103">View app permissions and grant admin consent in the Microsoft Teams admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="bcfc2-104">在 Microsoft Teams [管理](manage-apps.md) 中心内的"管理应用"页面，你可在其中查看和管理组织的所有 Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-104">The [Manage apps](manage-apps.md) page in the Microsoft Teams admin center is where you view and manage all Teams apps for your organization.</span></span> <span data-ttu-id="bcfc2-105">例如，你可以查看应用的组织级别状态和属性、批准或上传新的自定义应用、在组织级别阻止或允许应用，以及管理组织范围内的应用设置。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-105">For example, you can see the org-level status and properties of apps, approve or upload new custom apps to your organization's app store, block or allow apps at the org level, and manage org-wide app settings.</span></span>

<span data-ttu-id="bcfc2-106">在这里，也可向组织范围的管理员同意请求访问数据的应用，并查看应用的 (RSC) 用户。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-106">Here, you can also grant org-wide admin consent to apps that request permissions to access data and view resource-specific consent (RSC) permissions for apps.</span></span>

## <a name="grant-org-wide-admin-consent-to-an-app"></a><span data-ttu-id="bcfc2-107">向组织范围的管理员同意应用</span><span class="sxs-lookup"><span data-stu-id="bcfc2-107">Grant org-wide admin consent to an app</span></span>

<span data-ttu-id="bcfc2-108">如果您是全局管理员，则可以审阅并授予这些应用，这些应用代表全部用户请求权限。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-108">If you're a global admin, you can review and grant consent to apps that request permissions on behalf of all users in your organization.</span></span> <span data-ttu-id="bcfc2-109">这样做是为了使用户不必审阅并接受应用在启动应用时所请求的权限。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-109">You do this so that users don't have to review and accept the permissions requested by the app when they start the app.</span></span> <span data-ttu-id="bcfc2-110">此外，根据 Azure Active Directory (Azure AD) 的用户许可设置，可能不允许某些用户获得有关访问公司数据的应用的许可。 [consent settings](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent)</span><span class="sxs-lookup"><span data-stu-id="bcfc2-110">Additionally, depending on the user's [consent settings](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) in Azure Active Directory (Azure AD), some users may not be allowed to grant consent to apps that access company data.</span></span>

<span data-ttu-id="bcfc2-111">应用请求的权限示例包括读取团队中存储的信息、阅读用户的配置文件以及代表用户发送电子邮件的能力。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-111">Examples of permissions requested by apps include the ability to read information stored in a team, read a user's profile, and send an email on behalf of users.</span></span> <span data-ttu-id="bcfc2-112">若要了解详细信息，请参阅 Microsoft 身 [份平台终结点中的权限和许可](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-112">To learn more, see [Permissions and consent in the Microsoft identity platform endpoint](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent).</span></span> 

<span data-ttu-id="bcfc2-113">**"权限**"列指示应用是否具有需要同意的权限。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-113">The **Permissions** column indicates whether an app has permissions that need consent.</span></span> <span data-ttu-id="bcfc2-114">你将看到在 Azure AD **中** 注册的每个应用的视图详细信息链接，该应用中包含需要许可的权限。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-114">You'll see a **View details** link for each app registered in Azure AD that has permissions that need consent.</span></span> <span data-ttu-id="bcfc2-115">请记住这仅适用于自定义和第三方应用和应用。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-115">Keep in mind that this applies only to custom and third-party apps and.</span></span> <span data-ttu-id="bcfc2-116">您不会看到此链接，或者需要授予管理员许可，让 Microsoft 发布的应用使用。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-116">You won't see this link or need to grant admin consent for apps published by Microsoft.</span></span>

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text=""管理应用"页面上的"权限"列的屏幕截图":::

<span data-ttu-id="bcfc2-118">若要向应用授予组织范围许可，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="bcfc2-118">To grant org-wide consent to an app, follow these steps:</span></span>

1. <span data-ttu-id="bcfc2-119">在 Microsoft Teams 管理中心的左侧导航中，转到**Teams 应用**  >  **管理应用**。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-119">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="bcfc2-120">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="bcfc2-120">Do one of the following:</span></span>
    - <span data-ttu-id="bcfc2-121">搜索所需的应用，单击该应用名称转到应用详细信息页面上，然后选择"权限 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-121">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
    - <span data-ttu-id="bcfc2-122">按 **降序** 对"权限"列进行排序以查找应用程序，然后选择" **查看详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-122">Sort the **Permissions** column in descending order to find the app, and then select **View details**.</span></span> <span data-ttu-id="bcfc2-123">这样可以使你进入应用 **详细信息** 页面的"权限"选项卡。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-123">Doing this takes you to the **Permissions** tab of the app details page.</span></span>

3. <span data-ttu-id="bcfc2-124">在**组织范围内的权限下**，选择 **"审阅"权限并同同。**</span><span class="sxs-lookup"><span data-stu-id="bcfc2-124">Under **Org-wide permissions**, select **Review permissions and consent**.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="应用程序的"权限"选项卡上组织范围的权限的屏幕截图":::

    <span data-ttu-id="bcfc2-126">只有全局管理员才能执行此操作。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-126">You must be a global admin to do this.</span></span> <span data-ttu-id="bcfc2-127">Teams 服务管理员不能使用此选项。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-127">This option isn't available to Teams service admins.</span></span>

4. <span data-ttu-id="bcfc2-128">在 **"权限** "选项卡上，查看应用请求的权限。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-128">On the **Permissions** tab, review the permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="应用请求的权限的屏幕截图":::

    > [!IMPORTANT]
    > <span data-ttu-id="bcfc2-130">向应用授予组织范围的同意可使应用访问你所在组织的数据。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-130">Granting org-wide consent to an app allows the app to access your organization's data.</span></span> <span data-ttu-id="bcfc2-131">在授予许可之前，仔细查看应用请求的权限。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-131">Carefully review the permissions requested by the app before you grant consent.</span></span>
5. <span data-ttu-id="bcfc2-132">如果您相当意识到应用请求的权限 **，请单击"** 接受"以授予许可。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-132">If you agree with the permissions requested by the app, click **Accept** to grant consent.</span></span> <span data-ttu-id="bcfc2-133">页面顶部暂时显示一个标题，可以让你知道已被请求的权限授予了该应用。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-133">A banner temporarily appears at the top of the page to let you know that the requested permissions have been granted for the app.</span></span> <span data-ttu-id="bcfc2-134">该应用现在具有针对组织中所有用户的指定资源的访问权限，而其他任何用户都不会提示您审阅权限。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-134">The app now has access to the specified resources for all users in your organization and no one else will be prompted to review the permissions.</span></span>

<span data-ttu-id="bcfc2-135">接受权限后，你将在 **应用详细信息页面上的"组织** 范围"权限下看到一条消息，告诉你同意被授予。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-135">After you accept the permissions, you'll see a message under **Org-wide permissions** on the app details page to let you know that consent was granted.</span></span> <span data-ttu-id="bcfc2-136">要查看有关应用的权限的详细信息，请单击 Azure Active **Directory 链接** 以转到 Azure AD 门户中的应用页面。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-136">To view details about the app's permissions, click the **Azure Active Directory** link to go to the app's page in the Azure AD portal.</span></span>

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="取确授予时显示的消息的屏幕截图":::

<span data-ttu-id="bcfc2-138">如果允许你授予同意，并且一个或多个用户同意特定应用同意，你还将看到同意消息，以通知你同意，并且 Azure AD 门户中该应用页面的 Azure Active Directory 链接。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-138">If users in your organization are allowed to grant consent and if one or more users granted consent to a particular app, you'll also see the same message to let you know that consent was granted and the Azure Active Directory link to the app's page in the Azure AD portal.</span></span>

> [!NOTE]
> <span data-ttu-id="bcfc2-139">虽然 Teams **服务管理员** 无法使用"审阅"权限和同意选项，并且不能向应用授予组织范围的管理员同意，Teams 服务管理员可查看应用 **的"权限"** 选项卡上的内容。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-139">Although, the **Review permissions and consent** option isn't available to Teams service admins and they can't grant org-wide admin consent to apps, Teams service admins can view the content on the **Permissions** tab for an app.</span></span> <span data-ttu-id="bcfc2-140">例如，Teams 服务管理员可以单击 **Azure Active Directory 链接** 以在 Azure AD 门户中查看应用权限详细信息。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-140">For example, a Teams service admin can click the **Azure Active Directory** link to view app permissions details in the Azure AD portal.</span></span> 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a><span data-ttu-id="bcfc2-141">查看应用的特定于资源的许可权限</span><span class="sxs-lookup"><span data-stu-id="bcfc2-141">View resource-specific consent permissions of an app</span></span>

<span data-ttu-id="bcfc2-142">RSC 权限允许团队所有者同意应用访问和修改工作组的数据。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-142">RSC permissions let team owners grant consent for an app to access and modify a team's data.</span></span> <span data-ttu-id="bcfc2-143">RSC 权限是授予但特定于 Teams 的权限，用于定义应用在特定团队中可以执行的操作。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-143">RSC permissions are granular, Teams-specific permissions that define what an app can do in a specific team.</span></span> <span data-ttu-id="bcfc2-144">RSC 权限示例包括创建和删除频道、获取团队设置以及创建和删除频道选项卡的功能。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-144">Examples of RSC permissions include the ability to create and delete channels, get the settings for a team, and create and remove channel tabs.</span></span> 

<span data-ttu-id="bcfc2-145">RSC 权限在应用清单（而非 Azure AD）中定义。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-145">RSC permissions are defined in the app manifest and not in Azure AD.</span></span> <span data-ttu-id="bcfc2-146">当您向团队添加应用时，您授予对 RSC 权限的许可。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-146">You grant consent to RSC permissions when you add the app to a team.</span></span> <span data-ttu-id="bcfc2-147">要了解详细信息，[请参阅特定于资源的同 () 。 ](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)</span><span class="sxs-lookup"><span data-stu-id="bcfc2-147">To learn more, see [Resource-specific consent (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent).</span></span>

<span data-ttu-id="bcfc2-148">全局管理员和 Teams 服务管理员可在应用详细信息页的"权限 **"** 选项卡上查看应用的 RSC 权限。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-148">Global admins and Teams service admin can view RSC permissions for an app on the **Permissions** tab of the app details page.</span></span> 

<span data-ttu-id="bcfc2-149">若要查看应用的 RSC 权限，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="bcfc2-149">To view RSC permissions for an app, follow these steps:</span></span>

1. <span data-ttu-id="bcfc2-150">在 Microsoft Teams 管理中心的左侧导航中，转到**Teams 应用**  >  **管理应用**。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-150">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="bcfc2-151">搜索所需的应用，单击该应用名称转到应用详细信息页面上，然后选择"权限 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-151">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
3. <span data-ttu-id="bcfc2-152">在 **Microsoft Graph 资源 (特定的许) 可的) ，** 查看应用请求的 RSC 权限。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-152">Under **Microsoft Graph resource-specific consent (RSC) permissions**, review the RSC permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="应用的 RSC 权限的屏幕截图":::

## <a name="known-issues"></a><span data-ttu-id="bcfc2-154">已知问题</span><span class="sxs-lookup"><span data-stu-id="bcfc2-154">Known issues</span></span>

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a><span data-ttu-id="bcfc2-155">"查看详细信息"链接未显示在请求权限的某些第三方应用的权限列中</span><span class="sxs-lookup"><span data-stu-id="bcfc2-155">The "View details" link isn't displayed in the Permissions column for some third-party apps that request permissions</span></span>

<span data-ttu-id="bcfc2-156">目前，对于在 Azure AD 中注册了请求权限的所有第三方应用而来，审阅权限和授予许可功能不可访问。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-156">Currently, the ability to review permissions and grant consent isn't available for all third-party apps registered in Azure AD that request permissions.</span></span> <span data-ttu-id="bcfc2-157">您将在 **"权限"列** 中看到"查看 **--** 详细信息"列（而不是 **查看详细信息链接** ）。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-157">Instead of the **View details** link, you'll see **--** in the **Permissions** column.</span></span> <span data-ttu-id="bcfc2-158">我们正在使用 ISV 来为其应用启用此功能。</span><span class="sxs-lookup"><span data-stu-id="bcfc2-158">We're working with ISVs to enable this feature for their apps.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bcfc2-159">相关主题</span><span class="sxs-lookup"><span data-stu-id="bcfc2-159">Related topics</span></span>

- [<span data-ttu-id="bcfc2-160">在 Microsoft Teams 管理中心中管理应用</span><span class="sxs-lookup"><span data-stu-id="bcfc2-160">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="bcfc2-161">Microsoft 身份平台终结点中的权限和许可</span><span class="sxs-lookup"><span data-stu-id="bcfc2-161">Permissions and consent in the Microsoft identity platform endpoint</span></span>](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [<span data-ttu-id="bcfc2-162">Teams 中资源特定的一定</span><span class="sxs-lookup"><span data-stu-id="bcfc2-162">Resource-specific consent in Teams</span></span>](resource-specific-consent.md)
- [<span data-ttu-id="bcfc2-163">特定于资源的同 (RSC) </span><span class="sxs-lookup"><span data-stu-id="bcfc2-163">Resource-specific consent (RSC)</span></span>](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)


