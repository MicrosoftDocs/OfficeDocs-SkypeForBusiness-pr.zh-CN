---
title: 在 Microsoft Teams 管理中心查看应用权限并授予管理员许可
author: cichur
ms.author: v-cichur
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在 Microsoft Teams 管理中心的"管理应用"页面上查看应用请求的权限并授予应用管理员许可。
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6ec41760a7edd7de52d15995f39365b300cd797e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827532"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="8dfae-103">在 Microsoft Teams 管理中心查看应用权限并授予管理员许可</span><span class="sxs-lookup"><span data-stu-id="8dfae-103">View app permissions and grant admin consent in the Microsoft Teams admin center</span></span>

<span data-ttu-id="8dfae-104">在 [Microsoft](manage-apps.md) Teams 管理中心的"管理应用"页中，可以查看和管理组织的所有 Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="8dfae-104">The [Manage apps](manage-apps.md) page in the Microsoft Teams admin center is where you view and manage all Teams apps for your organization.</span></span> <span data-ttu-id="8dfae-105">例如，可以看到应用的组织级状态和属性、批准新的自定义应用或将其上载到组织的应用商店、在组织级别阻止或允许应用，以及管理组织范围内的应用设置。</span><span class="sxs-lookup"><span data-stu-id="8dfae-105">For example, you can see the org-level status and properties of apps, approve or upload new custom apps to your organization's app store, block or allow apps at the org level, and manage org-wide app settings.</span></span>

<span data-ttu-id="8dfae-106">在这里，还可以向请求数据访问权限的应用授予组织范围的管理员许可，以及查看 RSC (资源) 权限。</span><span class="sxs-lookup"><span data-stu-id="8dfae-106">Here, you can also grant org-wide admin consent to apps that request permissions to access data and view resource-specific consent (RSC) permissions for apps.</span></span>

## <a name="grant-org-wide-admin-consent-to-an-app"></a><span data-ttu-id="8dfae-107">向应用授予组织范围的管理员许可</span><span class="sxs-lookup"><span data-stu-id="8dfae-107">Grant org-wide admin consent to an app</span></span>

<span data-ttu-id="8dfae-108">如果你是全局管理员，你可以查看并许可代表组织中所有用户请求权限的应用。</span><span class="sxs-lookup"><span data-stu-id="8dfae-108">If you're a global admin, you can review and grant consent to apps that request permissions on behalf of all users in your organization.</span></span> <span data-ttu-id="8dfae-109">这样做是让用户在启动应用时不必查看并接受应用请求的权限。</span><span class="sxs-lookup"><span data-stu-id="8dfae-109">You do this so that users don't have to review and accept the permissions requested by the app when they start the app.</span></span> <span data-ttu-id="8dfae-110">此外，根据 Azure Active [](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) Directory (Azure AD) 中的用户同意设置，可能不允许某些用户向访问公司数据的应用授予许可。</span><span class="sxs-lookup"><span data-stu-id="8dfae-110">Additionally, depending on the user's [consent settings](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) in Azure Active Directory (Azure AD), some users may not be allowed to grant consent to apps that access company data.</span></span>

<span data-ttu-id="8dfae-111">应用请求的权限示例包括读取团队中存储的信息、读取用户的个人资料以及代表用户发送电子邮件的能力。</span><span class="sxs-lookup"><span data-stu-id="8dfae-111">Examples of permissions requested by apps include the ability to read information stored in a team, read a user's profile, and send an email on behalf of users.</span></span> <span data-ttu-id="8dfae-112">若要了解有关详细信息，请参阅 Microsoft 标识平台终结点 [中的权限和许可](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)。</span><span class="sxs-lookup"><span data-stu-id="8dfae-112">To learn more, see [Permissions and consent in the Microsoft identity platform endpoint](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent).</span></span> 

<span data-ttu-id="8dfae-113">" **权限"** 列指示应用是否具有需要许可的权限。</span><span class="sxs-lookup"><span data-stu-id="8dfae-113">The **Permissions** column indicates whether an app has permissions that need consent.</span></span> <span data-ttu-id="8dfae-114">对于在 Azure  AD 中注册并拥有需要许可的权限的每个应用，你将看到"查看详细信息"链接。</span><span class="sxs-lookup"><span data-stu-id="8dfae-114">You'll see a **View details** link for each app registered in Azure AD that has permissions that need consent.</span></span> <span data-ttu-id="8dfae-115">请记住，这仅适用于自定义和第三方应用。</span><span class="sxs-lookup"><span data-stu-id="8dfae-115">Keep in mind that this applies only to custom and third-party apps.</span></span> <span data-ttu-id="8dfae-116">你不会看到此链接，也不需要授予 Microsoft 发布的应用的管理员许可。</span><span class="sxs-lookup"><span data-stu-id="8dfae-116">You won't see this link or need to grant admin consent for apps published by Microsoft.</span></span>

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text=""管理应用"页面上"权限"列的屏幕截图":::

<span data-ttu-id="8dfae-118">若要向应用授予组织范围许可，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="8dfae-118">To grant org-wide consent to an app, follow these steps:</span></span>

1. <span data-ttu-id="8dfae-119">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **管理应用"。**</span><span class="sxs-lookup"><span data-stu-id="8dfae-119">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="8dfae-120">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="8dfae-120">Do one of the following:</span></span>
    - <span data-ttu-id="8dfae-121">搜索所需的应用，单击应用名称转到应用详细信息页，然后选择" **权限"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8dfae-121">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
    - <span data-ttu-id="8dfae-122">按降 **序对"** 权限"列进行排序以查找应用，然后选择"**查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="8dfae-122">Sort the **Permissions** column in descending order to find the app, and then select **View details**.</span></span> <span data-ttu-id="8dfae-123">执行此操作会你将访问 **应用详细信息** 页的"权限"选项卡。</span><span class="sxs-lookup"><span data-stu-id="8dfae-123">Doing this takes you to the **Permissions** tab of the app details page.</span></span>

3. <span data-ttu-id="8dfae-124">在 **组织范围的权限下**，选择 **"审阅权限和许可"。**</span><span class="sxs-lookup"><span data-stu-id="8dfae-124">Under **Org-wide permissions**, select **Review permissions and consent**.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="应用"权限"选项卡上组织范围内权限的屏幕截图":::

    <span data-ttu-id="8dfae-126">只有全局管理员才能这样做。</span><span class="sxs-lookup"><span data-stu-id="8dfae-126">You must be a global admin to do this.</span></span> <span data-ttu-id="8dfae-127">此选项对 Teams 服务管理员不可用。</span><span class="sxs-lookup"><span data-stu-id="8dfae-127">This option isn't available to Teams service admins.</span></span>

4. <span data-ttu-id="8dfae-128">在 **"权限"** 选项卡上，查看应用请求的权限。</span><span class="sxs-lookup"><span data-stu-id="8dfae-128">On the **Permissions** tab, review the permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="应用请求的权限的屏幕截图":::

    > [!IMPORTANT]
    > <span data-ttu-id="8dfae-130">向应用授予组织范围许可允许应用访问组织的数据。</span><span class="sxs-lookup"><span data-stu-id="8dfae-130">Granting org-wide consent to an app allows the app to access your organization's data.</span></span> <span data-ttu-id="8dfae-131">在授予许可之前，请仔细查看应用请求的权限。</span><span class="sxs-lookup"><span data-stu-id="8dfae-131">Carefully review the permissions requested by the app before you grant consent.</span></span>
5. <span data-ttu-id="8dfae-132">如果你同意应用请求的权限，请单击"接受 **"以授予** 同意。</span><span class="sxs-lookup"><span data-stu-id="8dfae-132">If you agree with the permissions requested by the app, click **Accept** to grant consent.</span></span> <span data-ttu-id="8dfae-133">页面顶部临时显示一个横幅，告知你为应用授予了请求的权限。</span><span class="sxs-lookup"><span data-stu-id="8dfae-133">A banner temporarily appears at the top of the page to let you know that the requested permissions have been granted for the app.</span></span> <span data-ttu-id="8dfae-134">应用现在有权访问组织中所有用户的指定资源，系统不会提示其他人查看权限。</span><span class="sxs-lookup"><span data-stu-id="8dfae-134">The app now has access to the specified resources for all users in your organization and no one else will be prompted to review the permissions.</span></span>

<span data-ttu-id="8dfae-135">接受权限后，应用详细信息页上的"组织范围权限"下会显示一条消息，告知你已授予许可。</span><span class="sxs-lookup"><span data-stu-id="8dfae-135">After you accept the permissions, you'll see a message under **Org-wide permissions** on the app details page to let you know that consent was granted.</span></span> <span data-ttu-id="8dfae-136">若要查看有关应用权限的详细信息，请单击 **Azure Active Directory** 链接以转到 Azure AD 门户中的应用页面。</span><span class="sxs-lookup"><span data-stu-id="8dfae-136">To view details about the app's permissions, click the **Azure Active Directory** link to go to the app's page in the Azure AD portal.</span></span>

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="授予许可时显示的消息的屏幕截图":::

<span data-ttu-id="8dfae-138">如果允许组织中用户授予许可，并且一个或多个用户授予了对特定应用的同意，则还会看到相同的消息，告知你已授予许可，Azure Active Directory 链接到 Azure AD 门户中的应用页面。</span><span class="sxs-lookup"><span data-stu-id="8dfae-138">If users in your organization are allowed to grant consent and if one or more users granted consent to a particular app, you'll also see the same message to let you know that consent was granted and the Azure Active Directory link to the app's page in the Azure AD portal.</span></span>

> [!NOTE]
> <span data-ttu-id="8dfae-139">虽然 Teams服务管理员无法查看"审阅"权限和许可选项，并且他们无法向应用授予组织范围的管理员许可，但 Teams 服务管理员可以查看应用"权限"选项卡上的内容。 </span><span class="sxs-lookup"><span data-stu-id="8dfae-139">Although, the **Review permissions and consent** option isn't available to Teams service admins and they can't grant org-wide admin consent to apps, Teams service admins can view the content on the **Permissions** tab for an app.</span></span> <span data-ttu-id="8dfae-140">例如，Teams 服务管理员可以单击 Azure **Active Directory** 链接，在 Azure AD 门户中查看应用权限详细信息。</span><span class="sxs-lookup"><span data-stu-id="8dfae-140">For example, a Teams service admin can click the **Azure Active Directory** link to view app permissions details in the Azure AD portal.</span></span> 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a><span data-ttu-id="8dfae-141">查看应用的特定于资源的许可权限</span><span class="sxs-lookup"><span data-stu-id="8dfae-141">View resource-specific consent permissions of an app</span></span>

<span data-ttu-id="8dfae-142">RSC 权限允许团队所有者授予应用访问和修改团队数据的许可。</span><span class="sxs-lookup"><span data-stu-id="8dfae-142">RSC permissions let team owners grant consent for an app to access and modify a team's data.</span></span> <span data-ttu-id="8dfae-143">RSC 权限是特定于团队的粒度权限，用于定义应用可在特定团队中执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="8dfae-143">RSC permissions are granular, Teams-specific permissions that define what an app can do in a specific team.</span></span> <span data-ttu-id="8dfae-144">RSC 权限的示例包括创建和删除频道、获取团队设置以及创建和删除频道选项卡的功能。</span><span class="sxs-lookup"><span data-stu-id="8dfae-144">Examples of RSC permissions include the ability to create and delete channels, get the settings for a team, and create and remove channel tabs.</span></span> 

<span data-ttu-id="8dfae-145">RSC 权限在应用清单中定义，而不是在 Azure AD 中定义。</span><span class="sxs-lookup"><span data-stu-id="8dfae-145">RSC permissions are defined in the app manifest and not in Azure AD.</span></span> <span data-ttu-id="8dfae-146">将应用添加到团队时，即表示你同意 RSC 权限。</span><span class="sxs-lookup"><span data-stu-id="8dfae-146">You grant consent to RSC permissions when you add the app to a team.</span></span> <span data-ttu-id="8dfae-147">若要了解有关详细信息，请参阅[RSC (资源) 。 ](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)</span><span class="sxs-lookup"><span data-stu-id="8dfae-147">To learn more, see [Resource-specific consent (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent).</span></span>

<span data-ttu-id="8dfae-148">全局管理员和 Teams 服务管理员可以在应用详细信息页的"权限"选项卡上查看应用的 RSC 权限。</span><span class="sxs-lookup"><span data-stu-id="8dfae-148">Global admins and Teams service admin can view RSC permissions for an app on the **Permissions** tab of the app details page.</span></span> 

<span data-ttu-id="8dfae-149">若要查看应用的 RSC 权限，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="8dfae-149">To view RSC permissions for an app, follow these steps:</span></span>

1. <span data-ttu-id="8dfae-150">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **管理应用"。**</span><span class="sxs-lookup"><span data-stu-id="8dfae-150">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="8dfae-151">搜索所需的应用，单击应用名称转到应用详细信息页，然后选择" **权限"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8dfae-151">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
3. <span data-ttu-id="8dfae-152">在 **Microsoft Graph 资源特定的许可 (RSC**) 权限下，查看应用请求的 RSC 权限。</span><span class="sxs-lookup"><span data-stu-id="8dfae-152">Under **Microsoft Graph resource-specific consent (RSC) permissions**, review the RSC permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="应用的 RSC 权限屏幕截图":::

## <a name="known-issues"></a><span data-ttu-id="8dfae-154">已知问题</span><span class="sxs-lookup"><span data-stu-id="8dfae-154">Known issues</span></span>

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a><span data-ttu-id="8dfae-155">某些请求权限的第三方应用的"权限"列中不显示"查看详细信息"链接</span><span class="sxs-lookup"><span data-stu-id="8dfae-155">The "View details" link isn't displayed in the Permissions column for some third-party apps that request permissions</span></span>

<span data-ttu-id="8dfae-156">目前，在 Azure AD 中注册的所有请求权限的第三方应用无法查看权限和授予许可。</span><span class="sxs-lookup"><span data-stu-id="8dfae-156">Currently, the ability to review permissions and grant consent isn't available for all third-party apps registered in Azure AD that request permissions.</span></span> <span data-ttu-id="8dfae-157">你将在 **"权限** "列中看到"查看 **--** 详细信息 **"链接，而不是"查看详细信息"** 链接。</span><span class="sxs-lookup"><span data-stu-id="8dfae-157">Instead of the **View details** link, you'll see **--** in the **Permissions** column.</span></span> <span data-ttu-id="8dfae-158">我们正在与 ISV 合作，为应用启用此功能。</span><span class="sxs-lookup"><span data-stu-id="8dfae-158">We're working with ISVs to enable this feature for their apps.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8dfae-159">相关主题</span><span class="sxs-lookup"><span data-stu-id="8dfae-159">Related topics</span></span>

- [<span data-ttu-id="8dfae-160">在 Microsoft Teams 管理中心管理应用</span><span class="sxs-lookup"><span data-stu-id="8dfae-160">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="8dfae-161">Microsoft 标识平台终结点中的权限和许可</span><span class="sxs-lookup"><span data-stu-id="8dfae-161">Permissions and consent in the Microsoft identity platform endpoint</span></span>](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [<span data-ttu-id="8dfae-162">Teams 中特定于资源的同意</span><span class="sxs-lookup"><span data-stu-id="8dfae-162">Resource-specific consent in Teams</span></span>](resource-specific-consent.md)
- [<span data-ttu-id="8dfae-163">RSC (特定于资源) </span><span class="sxs-lookup"><span data-stu-id="8dfae-163">Resource-specific consent (RSC)</span></span>](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- <span data-ttu-id="8dfae-164">[在 Ignite](https://aka.ms/PR132) 2020 会话 (Teams 应用生命周期) </span><span class="sxs-lookup"><span data-stu-id="8dfae-164">[Navigating the Teams app lifecycle](https://aka.ms/PR132) (Ignite 2020 session)</span></span>


