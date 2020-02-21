---
title: 在 Microsoft 团队租户应用目录中发布应用
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: 有关在 Microsoft 团队租户应用程序目录中发布应用的指南。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f3d4f5937c766c1c4f6f54a6a38872e793a3825
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161611"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-app-catalog"></a><span data-ttu-id="cf9d1-103">在 Microsoft 团队租户应用目录中发布应用</span><span class="sxs-lookup"><span data-stu-id="cf9d1-103">Publish apps in the Microsoft Teams tenant app catalog</span></span>
=======================================================

<span data-ttu-id="cf9d1-104">你可以使用 Microsoft 团队租户应用目录来测试和分配业务线应用程序到你的组织。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-104">You can use the Microsoft Teams tenant app catalog to test and distribute line-of-business applications to your organization.</span></span>

<span data-ttu-id="cf9d1-105">团队租户应用程序目录允许你分配专为你的组织构建的业务线应用程序，并且你依赖于完成关键的业务功能。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-105">The Teams tenant app catalog lets you distribute line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions.</span></span>

<span data-ttu-id="cf9d1-106">若要为你的组织发布应用，请使用具有全局管理员或团队服务管理员角色的帐户登录团队客户端，然后按照下面的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-106">To publish apps for your organization, sign in to the Teams client using an account with either the global admin or teams service admin role and then follow the steps below.</span></span>

## <a name="publish-an-app-in-the-tenant-app-catalog-from-the-teams-client"></a><span data-ttu-id="cf9d1-107">从团队客户端发布租户应用目录中的应用</span><span class="sxs-lookup"><span data-stu-id="cf9d1-107">Publish an app in the tenant app catalog from the Teams client</span></span>

> [!NOTE]
> <span data-ttu-id="cf9d1-108">这些步骤介绍了如何使用团队客户端发布应用。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-108">These steps describe how to publish an app by using the Teams client.</span></span> <span data-ttu-id="cf9d1-109">你还可以在 Microsoft 团队管理中心的 "**管理应用**" 页面上发布应用。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-109">You can also publish an app on the **Manage apps** page in the Microsoft Teams admin center.</span></span> <span data-ttu-id="cf9d1-110">若要了解详细信息，请参阅[管理团队中的应用](manage-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-110">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="cf9d1-111">获取团队应用包</span><span class="sxs-lookup"><span data-stu-id="cf9d1-111">Get a Teams app package</span></span>

<span data-ttu-id="cf9d1-112">团队应用包是使用[团队应用 Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)创建的。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-112">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="cf9d1-113">拥有应用包后，即可将其添加到租户应用目录。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-113">Once you have the app package, you can add it to the tenant app catalog.</span></span> <span data-ttu-id="cf9d1-114">虽然您的组织中的所有用户都可以查看应用程序目录，但只有全局管理员和团队服务管理员能够发布和管理它。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-114">While all users in your organization can view the app catalog, only global admins and teams service admins have the ability to publish and manage it.</span></span>

### <a name="go-to-the-tenant-app-catalog"></a><span data-ttu-id="cf9d1-115">转到租户应用目录</span><span class="sxs-lookup"><span data-stu-id="cf9d1-115">Go to the tenant app catalog</span></span>

<span data-ttu-id="cf9d1-116">启动团队并使用全局或团队服务管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-116">Start Teams and sign in using your global or teams service admin credentials.</span></span> <span data-ttu-id="cf9d1-117">选择应用左侧的 "**应用**"，然后选择为特定组织指定的新分区（在本例中为 "Contoso"）。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-117">Select **Apps** on the left side of the app, and then select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="cf9d1-118">您的组织中的用户可以查看目录中的应用，并为他们所属的团队安装这些应用。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-118">Users in your organization can view apps in the catalog and install them for teams of which they are a member.</span></span>

![显示应用程序目录的团队应用商店的屏幕截图。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-app-catalog"></a><span data-ttu-id="cf9d1-120">将应用添加到租户应用目录</span><span class="sxs-lookup"><span data-stu-id="cf9d1-120">Add an app to the tenant app catalog</span></span>

1. <span data-ttu-id="cf9d1-121">在 "**应用**" 页面上，选择 "上载**适用于 Contoso**的**自定义应用** > 上传"。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-121">On the **Apps** page, select **Upload a custom app** > **Upload for Contoso**.</span></span>

    ![显示应用程序目录的团队应用商店的屏幕截图。](media/private-app-store-teams-image02.png)

    <span data-ttu-id="cf9d1-123">（您也可以选择 **"向我上载" 或 "我的团队**" （称为*旁加载*）。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-123">(You can also choose **Upload for me or my teams**, which is called *sideloading*.</span></span> <span data-ttu-id="cf9d1-124">旁加载使应用仅可供你的团队或你选择的团队使用。）</span><span class="sxs-lookup"><span data-stu-id="cf9d1-124">Sideloading makes the app available only to your teams or to teams you select.)</span></span>

2. <span data-ttu-id="cf9d1-125">导航到应用包并将其选中，然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-125">Navigate to the app package and select it, and then click **Open**.</span></span>

    ![显示应用程序目录的团队应用商店的屏幕截图。](media/private-app-store-teams-image03.png)

<span data-ttu-id="cf9d1-127">当你返回到租户应用目录时，新的企业应用将位于此处。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-127">When you go back to your tenant app catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="cf9d1-128">请记住，只有你和你的组织的成员才有权访问此应用程序目录。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-128">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-app-catalog"></a><span data-ttu-id="cf9d1-129">更新租户应用目录中的应用</span><span class="sxs-lookup"><span data-stu-id="cf9d1-129">Update an app in the tenant app catalog</span></span>

1. <span data-ttu-id="cf9d1-130">从租户应用程序目录中，选择 "**...**"</span><span class="sxs-lookup"><span data-stu-id="cf9d1-130">From your tenant app catalog, select “**…**”</span></span> <span data-ttu-id="cf9d1-131">在要更新的应用的右上角。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-131">on the top right of the app you want to update.</span></span>

2. <span data-ttu-id="cf9d1-132">导航到已更新的应用包并将其选中，然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-132">Navigate to the updated app package and select it, and then click **Open**.</span></span>

    ![显示应用程序目录的团队应用商店的屏幕截图。](media/private-app-store-teams-image04.png)

<span data-ttu-id="cf9d1-134">该应用将被修改为版本2.0。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-134">The app will be revised to version 2.0.</span></span> <span data-ttu-id="cf9d1-135">您也可以从此菜单中删除整个公司的应用。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-135">You can also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-manage-the-tenant-app-catalog"></a><span data-ttu-id="cf9d1-136">使用 Microsoft 团队管理中心管理租户应用目录</span><span class="sxs-lookup"><span data-stu-id="cf9d1-136">Use the Microsoft Teams admin center to manage the tenant app catalog</span></span>

<span data-ttu-id="cf9d1-137">如果你有需要 bug 修复的应用，你可以暂时为应用权限策略中的用户禁用应用。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-137">If you have apps that need bug fixes, you can temporarily disable apps for users in an app permission policy.</span></span>

1. <span data-ttu-id="cf9d1-138">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用** > **权限策略**"。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-138">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="cf9d1-139">选择要编辑的应用权限策略，然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-139">Select the app permission policy that you want to edit, and then click **Edit**.</span></span>
3. <span data-ttu-id="cf9d1-140">在 "**租户应用**" 下，选择 "**阻止特定应用并允许所有其他应用**"，然后添加要阻止的应用。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-140">Under **Tenant apps**, select **Block specific apps and allow all others**, and then add the apps that you want to block.</span></span>

<span data-ttu-id="cf9d1-141">禁用应用会阻止用户与应用交互，而无需完全删除应用。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-141">Disabling an app blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="cf9d1-142">在组织中管理应用时，这些控件可为你提供额外的灵活性和控制。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-142">These controls give you additional flexibility and control when managing apps in your organization.</span></span>

<span data-ttu-id="cf9d1-143">若要了解详细信息，请参阅[管理团队中的应用权限策略](teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="cf9d1-143">To learn more, see [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>