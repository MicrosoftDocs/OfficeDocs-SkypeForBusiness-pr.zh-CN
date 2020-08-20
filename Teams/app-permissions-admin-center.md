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
ms.openlocfilehash: 737052ba5794b221caa08fa8ccfabec0d597c3ad
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814605"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="5a439-103">在 Microsoft Teams 管理中心查看应用权限并授予管理员许可</span><span class="sxs-lookup"><span data-stu-id="5a439-103">View app permissions and grant admin consent in the Microsoft Teams admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="5a439-104">在 Microsoft Teams [管理](manage-apps.md) 中心内的"管理应用"页面，你可在其中查看和管理组织的所有 Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="5a439-104">The [Manage apps](manage-apps.md) page in the Microsoft Teams admin center is where you view and manage all Teams apps for your organization.</span></span> <span data-ttu-id="5a439-105">例如，你可以查看应用的组织级别状态和属性、批准或上传新的自定义应用、在组织级别阻止或允许应用，以及管理组织范围内的应用设置。</span><span class="sxs-lookup"><span data-stu-id="5a439-105">For example, you can see the org-level status and properties of apps, approve or upload new custom apps to your organization's app store, block or allow apps at the org level, and manage org-wide app settings.</span></span>

<span data-ttu-id="5a439-106">在这里，也可向组织范围的管理员同意请求访问数据的应用，并查看应用的 (RSC) 用户。</span><span class="sxs-lookup"><span data-stu-id="5a439-106">Here, you can also grant org-wide admin consent to apps that request permissions to access data and view resource-specific consent (RSC) permissions for apps.</span></span>

## <a name="grant-org-wide-admin-consent-to-an-app"></a><span data-ttu-id="5a439-107">向组织范围的管理员同意应用</span><span class="sxs-lookup"><span data-stu-id="5a439-107">Grant org-wide admin consent to an app</span></span>

<span data-ttu-id="5a439-108">作为管理员，您可以审阅和授予代表您组织中所有用户请求权限的应用。</span><span class="sxs-lookup"><span data-stu-id="5a439-108">As an admin, you can review and grant consent to apps that request permissions on behalf of all users in your organization.</span></span> <span data-ttu-id="5a439-109">这样做是为了使用户不必审阅并接受应用在启动应用时所请求的权限。</span><span class="sxs-lookup"><span data-stu-id="5a439-109">You do this so that users don't have to review and accept the permissions requested by the app when they start the app.</span></span> <span data-ttu-id="5a439-110">此外，根据 Azure Active Directory (Azure AD) 的用户许可设置，可能不允许某些用户获得有关访问公司数据的应用的许可。 [consent settings](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent)</span><span class="sxs-lookup"><span data-stu-id="5a439-110">Additionally, depending on the user's [consent settings](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) in Azure Active Directory (Azure AD), some users may not be allowed to grant consent to apps that access company data.</span></span>

<span data-ttu-id="5a439-111">应用请求的权限示例包括读取团队中存储的信息、阅读用户的配置文件以及代表用户发送电子邮件的能力。</span><span class="sxs-lookup"><span data-stu-id="5a439-111">Examples of permissions requested by apps include the ability to read information stored in a team, read a user's profile, and send an email on behalf of users.</span></span> <span data-ttu-id="5a439-112">若要了解详细信息，请参阅 Microsoft 身 [份平台终结点中的权限和许可](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)。</span><span class="sxs-lookup"><span data-stu-id="5a439-112">To learn more, see [Permissions and consent in the Microsoft identity platform endpoint](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent).</span></span> 

<span data-ttu-id="5a439-113">只有全局管理员才能向应用授予组织范围的同意。</span><span class="sxs-lookup"><span data-stu-id="5a439-113">You have to be a global admin to grant org-wide consent to an app.</span></span> <span data-ttu-id="5a439-114">**"权限**"列指示应用是否具有需要同意的权限。</span><span class="sxs-lookup"><span data-stu-id="5a439-114">The **Permissions** column indicates whether an app has permissions that need consent.</span></span> <span data-ttu-id="5a439-115">你将看到在 Azure AD **中** 注册的每个应用的视图详细信息链接，该应用中包含需要许可的权限。</span><span class="sxs-lookup"><span data-stu-id="5a439-115">You'll see a **View details** link for each app registered in Azure AD that has permissions that need consent.</span></span> <span data-ttu-id="5a439-116">请记住这仅适用于自定义和第三方应用和应用。</span><span class="sxs-lookup"><span data-stu-id="5a439-116">Keep in mind that this applies only to custom and third-party apps and.</span></span> <span data-ttu-id="5a439-117">您不会看到此链接，或者需要授予管理员许可，让 Microsoft 发布的应用使用。</span><span class="sxs-lookup"><span data-stu-id="5a439-117">You won't see this link or need to grant admin consent for apps published by Microsoft.</span></span>

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text=""管理应用"页面上的"权限"列的屏幕截图":::

<span data-ttu-id="5a439-119">若要向应用授予组织范围许可，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="5a439-119">To grant org-wide consent to an app, follow these steps:</span></span>

1. <span data-ttu-id="5a439-120">在 Microsoft Teams 管理中心的左侧导航中，转到**Teams 应用**  >  **管理应用**。</span><span class="sxs-lookup"><span data-stu-id="5a439-120">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="5a439-121">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="5a439-121">Do one of the following:</span></span>
    - <span data-ttu-id="5a439-122">搜索所需的应用，单击该应用名称转到应用详细信息页面上，然后选择"权限 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="5a439-122">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
    - <span data-ttu-id="5a439-123">按 **降序** 对"权限"列进行排序以查找应用程序，然后选择" **查看详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="5a439-123">Sort the **Permissions** column in descending order to find the app, and then select **View details**.</span></span> <span data-ttu-id="5a439-124">这样可以使你进入应用 **详细信息** 页面的"权限"选项卡。</span><span class="sxs-lookup"><span data-stu-id="5a439-124">Doing this takes you to the **Permissions** tab of the app details page.</span></span>

3. <span data-ttu-id="5a439-125">在**组织范围内的权限下**，选择 **"审阅"权限并同同。**</span><span class="sxs-lookup"><span data-stu-id="5a439-125">Under **Org-wide permissions**, select **Review permissions and consent**.</span></span> <span data-ttu-id="5a439-126">只有全局管理员才能执行此操作。</span><span class="sxs-lookup"><span data-stu-id="5a439-126">You must be a global admin to do this.</span></span> <span data-ttu-id="5a439-127">Teams 服务管理员不能使用此选项。</span><span class="sxs-lookup"><span data-stu-id="5a439-127">This option isn't available to Teams service admins.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="应用程序的"权限"选项卡上组织范围的权限的屏幕截图":::

4. <span data-ttu-id="5a439-129">在 **"权限** "选项卡上，查看应用请求的权限。</span><span class="sxs-lookup"><span data-stu-id="5a439-129">On the **Permissions** tab, review the permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="应用请求的权限的屏幕截图":::

    > [!IMPORTANT]
    > <span data-ttu-id="5a439-131">向应用授予组织范围的同意可使应用访问你所在组织的数据。</span><span class="sxs-lookup"><span data-stu-id="5a439-131">Granting org-wide consent to an app allows the app to access your organization's data.</span></span> <span data-ttu-id="5a439-132">在授予许可之前，仔细查看应用请求的权限。</span><span class="sxs-lookup"><span data-stu-id="5a439-132">Carefully review the permissions requested by the app before you grant consent.</span></span>
5. <span data-ttu-id="5a439-133">如果您相当意识到应用请求的权限 **，请单击"** 接受"以授予许可。</span><span class="sxs-lookup"><span data-stu-id="5a439-133">If you agree with the permissions requested by the app, click **Accept** to grant consent.</span></span> <span data-ttu-id="5a439-134">页面顶部暂时显示一个标题，可以让你知道已被请求的权限授予了该应用。</span><span class="sxs-lookup"><span data-stu-id="5a439-134">A banner temporarily appears at the top of the page to let you know that the requested permissions have been granted for the app.</span></span> <span data-ttu-id="5a439-135">该应用现在具有针对组织中所有用户的指定资源的访问权限，而其他任何用户都不会提示您审阅权限。</span><span class="sxs-lookup"><span data-stu-id="5a439-135">The app now has access to the specified resources for all users in your organization and no one else will be prompted to review the permissions.</span></span>

<span data-ttu-id="5a439-136">接受权限后，你将在 **应用详细信息页面上的"组织** 范围"权限下看到一条消息，告诉你同意被授予。</span><span class="sxs-lookup"><span data-stu-id="5a439-136">After you accept the permissions, you'll see a message under **Org-wide permissions** on the app details page to let you know that consent was granted.</span></span> <span data-ttu-id="5a439-137">要查看有关应用的权限的详细信息，请单击 Azure Active **Directory 链接** 以转到 Azure AD 门户中的应用页面。</span><span class="sxs-lookup"><span data-stu-id="5a439-137">To view details about the app's permissions, click the **Azure Active Directory** link to go to the app's page in the Azure AD portal.</span></span>

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="取确授予时显示的消息的屏幕截图":::

<span data-ttu-id="5a439-139">如果允许你组织中的用户授予许可，并且仅允许一个或多个用户授予特定应用的许可，您将只看到消息，以通知你许可是被授予并且是 Azure Active Directory 链接。</span><span class="sxs-lookup"><span data-stu-id="5a439-139">If users in your organization are allowed to grant consent and if one or more users granted consent to a particular app, you'll only see the message to let you know that consent was granted and the Azure Active Directory link.</span></span> 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a><span data-ttu-id="5a439-140">查看应用的特定于资源的许可权限</span><span class="sxs-lookup"><span data-stu-id="5a439-140">View resource-specific consent permissions of an app</span></span>

<span data-ttu-id="5a439-141">RSC 权限允许团队所有者同意应用访问和修改工作组的数据。</span><span class="sxs-lookup"><span data-stu-id="5a439-141">RSC permissions let team owners grant consent for an app to access and modify a team's data.</span></span> <span data-ttu-id="5a439-142">RSC 权限是授予但特定于 Teams 的权限，用于定义应用在特定团队中可以执行的操作。</span><span class="sxs-lookup"><span data-stu-id="5a439-142">RSC permissions are granular, Teams-specific permissions that define what an app can do in a specific team.</span></span> <span data-ttu-id="5a439-143">RSC 权限示例包括创建和删除频道、获取团队设置以及创建和删除频道选项卡的功能。</span><span class="sxs-lookup"><span data-stu-id="5a439-143">Examples of RSC permissions include the ability to create and delete channels, get the settings for a team, and create and remove channel tabs.</span></span> <span data-ttu-id="5a439-144">RSC 权限在应用清单（而非 Azure AD）中定义。</span><span class="sxs-lookup"><span data-stu-id="5a439-144">RSC permissions are defined in the app manifest and not in Azure AD.</span></span>

<span data-ttu-id="5a439-145">当您向团队添加应用时，您授予对 RSC 权限的许可。</span><span class="sxs-lookup"><span data-stu-id="5a439-145">You grant consent to RSC permissions when you add the app to a team.</span></span> <span data-ttu-id="5a439-146">要了解详细信息，请参阅 Teams [中特定于资源 (一个) ](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent) 的一 [些同意](resource-specific-consent.md)。</span><span class="sxs-lookup"><span data-stu-id="5a439-146">To learn more, see [Resource-specific consent (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent) and [Resource-specific consent in Teams](resource-specific-consent.md).</span></span>

<span data-ttu-id="5a439-147">全局管理员和 Teams 服务管理员可以查看 RSC 权限。</span><span class="sxs-lookup"><span data-stu-id="5a439-147">Global admins and Teams service admin can view RSC permissions.</span></span> <span data-ttu-id="5a439-148">若要查看应用的 RSC 权限，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="5a439-148">To view RSC permissions for an app, follow these steps:</span></span>

1. <span data-ttu-id="5a439-149">在 Microsoft Teams 管理中心的左侧导航中，转到**Teams 应用**  >  **管理应用**。</span><span class="sxs-lookup"><span data-stu-id="5a439-149">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="5a439-150">搜索所需的应用，单击该应用名称转到应用详细信息页面上，然后选择"权限 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="5a439-150">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
3. <span data-ttu-id="5a439-151">在 **Microsoft Graph 资源 (特定的许) 可的) ，** 查看应用请求的 RSC 权限。</span><span class="sxs-lookup"><span data-stu-id="5a439-151">Under **Microsoft Graph resource-specific consent (RSC) permissions**, review the RSC permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="应用的 RSC 权限的屏幕截图":::

## <a name="related-topics"></a><span data-ttu-id="5a439-153">相关主题</span><span class="sxs-lookup"><span data-stu-id="5a439-153">Related topics</span></span>

- [<span data-ttu-id="5a439-154">在 Microsoft Teams 管理中心中管理应用</span><span class="sxs-lookup"><span data-stu-id="5a439-154">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="5a439-155">Microsoft 身份平台终结点中的权限和许可</span><span class="sxs-lookup"><span data-stu-id="5a439-155">Permissions and consent in the Microsoft identity platform endpoint</span></span>](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [<span data-ttu-id="5a439-156">Teams 中资源特定的一定</span><span class="sxs-lookup"><span data-stu-id="5a439-156">Resource-specific consent in Teams</span></span>](resource-specific-consent.md)
- [<span data-ttu-id="5a439-157">特定于资源的同 (RSC) </span><span class="sxs-lookup"><span data-stu-id="5a439-157">Resource-specific consent (RSC)</span></span>](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)


