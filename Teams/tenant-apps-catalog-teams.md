---
title: 在 Microsoft 团队租户应用目录中发布应用
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/20/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: 有关在 Microsoft 团队租户应用目录中发布应用的指南。
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5affe464ac300d0084916ad8ec0044ca74f8fa6b
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570076"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="b8351-103">在 Microsoft 团队租户应用目录中发布应用</span><span class="sxs-lookup"><span data-stu-id="b8351-103">Publish apps in the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

<span data-ttu-id="b8351-104">你可以使用 Microsoft 团队租户应用目录来测试和分配业务线应用程序到你的组织。</span><span class="sxs-lookup"><span data-stu-id="b8351-104">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span>

<span data-ttu-id="b8351-105">"团队租户应用" 目录使你可以分配专为你的组织构建的业务线应用程序，以及你依赖于完成关键业务功能的业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="b8351-105">The Teams Tenant Apps Catalog lets you distribute line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions.</span></span>

<span data-ttu-id="b8351-106">若要为你的组织发布应用，请使用具有全局管理员或团队服务管理员角色的帐户登录团队客户端，然后按照下面的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="b8351-106">To publish apps for your organization, sign in to your Teams client using an account with the global admin or teams service admin roles and then follow the instructions below.</span></span>

## <a name="publish-an-app-in-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="b8351-107">从团队客户端发布租户应用目录中的应用</span><span class="sxs-lookup"><span data-stu-id="b8351-107">Publish an app in the Tenant Apps Catalog from the Teams client</span></span>

> [!NOTE]
> <span data-ttu-id="b8351-108">你需要使用已启用全局管理员或团队服务管理员角色的帐户登录到 Microsoft 团队客户端，以便为你的组织发布应用。</span><span class="sxs-lookup"><span data-stu-id="b8351-108">You need to be signed in to the Microsoft Teams client with an account that has either the global admin or teams service admin role enabled to publish apps for your organization.</span></span> <span data-ttu-id="b8351-109">了解有关[使用管理员角色管理团队](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b8351-109">Learn more about [using administrator roles to manage Teams](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles).</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="b8351-110">获取团队应用包</span><span class="sxs-lookup"><span data-stu-id="b8351-110">Get a Teams app package</span></span>

<span data-ttu-id="b8351-111">团队应用包是使用[团队应用 Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)创建的。</span><span class="sxs-lookup"><span data-stu-id="b8351-111">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="b8351-112">拥有应用程序包后，即可将其添加到企业应用目录。</span><span class="sxs-lookup"><span data-stu-id="b8351-112">Once you have the app package, you can add it to the enterprise app catalog.</span></span> <span data-ttu-id="b8351-113">虽然租户中的所有用户都可以查看应用程序目录，但只有全局管理员和团队服务管理员有权发布和管理它。</span><span class="sxs-lookup"><span data-stu-id="b8351-113">While all users in the tenant can view the app catalog, only global admins and teams service admins have the ability to publish and manage it.</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="b8351-114">转到租户应用目录</span><span class="sxs-lookup"><span data-stu-id="b8351-114">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="b8351-115">启动 Microsoft 团队客户端并使用全局或团队服务管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="b8351-115">Start the Microsoft Teams client and sign in using your global or teams service admin credentials.</span></span> <span data-ttu-id="b8351-116">从 "Microsoft 团队存储" 中，选择为特定组织（在本例中为 "Contoso"）指定的新分区。</span><span class="sxs-lookup"><span data-stu-id="b8351-116">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="b8351-117">您的组织中的用户可以查看目录中的应用，并为他们所属的团队安装这些应用。</span><span class="sxs-lookup"><span data-stu-id="b8351-117">Users in your organization can view apps in the catalog and install them for teams of which they are a member.</span></span>

![显示应用程序目录的团队应用商店的屏幕截图。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="b8351-119">将应用添加到租户应用目录</span><span class="sxs-lookup"><span data-stu-id="b8351-119">Add an app to the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="b8351-120">在应用商店中，选择 "上载**适用于 Contoso**的**自定义应用** > 上传"。</span><span class="sxs-lookup"><span data-stu-id="b8351-120">From the store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

    ![显示应用程序目录的团队应用商店的屏幕截图。](media/private-app-store-teams-image02.png)

    <span data-ttu-id="b8351-122">（您也可以选择 **"向我上载" 或 "我的团队**" （称为*旁加载*）。</span><span class="sxs-lookup"><span data-stu-id="b8351-122">(You can also choose **Upload for me or my teams**, which is called *sideloading*.</span></span> <span data-ttu-id="b8351-123">旁加载使应用仅可供你的团队或你选择的团队使用。）</span><span class="sxs-lookup"><span data-stu-id="b8351-123">Sideloading makes the app available only to your teams or to teams you select.)</span></span>

2. <span data-ttu-id="b8351-124">导航到应用包并将其选中，然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="b8351-124">Navigate to the app package and select it, and then click **Open**.</span></span>

    ![显示应用程序目录的团队应用商店的屏幕截图。](media/private-app-store-teams-image03.png)

<span data-ttu-id="b8351-126">当你返回到租户应用目录时，新的企业应用将位于此处。</span><span class="sxs-lookup"><span data-stu-id="b8351-126">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="b8351-127">请记住，只有你和你的组织的成员才有权访问此应用程序目录。</span><span class="sxs-lookup"><span data-stu-id="b8351-127">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="b8351-128">更新租户应用目录中的应用</span><span class="sxs-lookup"><span data-stu-id="b8351-128">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="b8351-129">从租户应用目录中，选择 "**...**"</span><span class="sxs-lookup"><span data-stu-id="b8351-129">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="b8351-130">在要更新的应用的右上角。</span><span class="sxs-lookup"><span data-stu-id="b8351-130">on the top right of the app you want to update.</span></span>

2. <span data-ttu-id="b8351-131">导航到已更新的应用包并将其选中，然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="b8351-131">Navigate to the updated app package and select it, and then click **Open**.</span></span>

    ![显示应用程序目录的团队应用商店的屏幕截图。](media/private-app-store-teams-image04.png)

<span data-ttu-id="b8351-133">该应用将被修改为版本2.0。</span><span class="sxs-lookup"><span data-stu-id="b8351-133">The app will be revised to version 2.0.</span></span> <span data-ttu-id="b8351-134">您也可以从此菜单中删除整个公司的应用。</span><span class="sxs-lookup"><span data-stu-id="b8351-134">You can also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="b8351-135">使用 Office 365 管理门户管理租户应用目录</span><span class="sxs-lookup"><span data-stu-id="b8351-135">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="b8351-136">如果你有需要 bug 修复的应用，你可以通过 Office 365 管理门户暂时禁用应用。</span><span class="sxs-lookup"><span data-stu-id="b8351-136">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="b8351-137">选择 "**设置** > **服务" & 加载项** > **Microsoft 团队**。</span><span class="sxs-lookup"><span data-stu-id="b8351-137">Select **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> <span data-ttu-id="b8351-138">除了以前的设置，现在还有一个专用于贵公司的应用的部分。</span><span class="sxs-lookup"><span data-stu-id="b8351-138">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="b8351-139">你可以选择要启用或禁用的应用。</span><span class="sxs-lookup"><span data-stu-id="b8351-139">You can choose which apps you want to enable or disable.</span></span>

![显示应用程序目录的团队应用商店的屏幕截图。](media/private-app-store-teams-image05.png)

<span data-ttu-id="b8351-141">禁用应用将阻止用户与应用交互，而无需完全删除应用。</span><span class="sxs-lookup"><span data-stu-id="b8351-141">Disabling an app will block users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="b8351-142">在企业中管理应用时，这些控件可为你提供额外的灵活性和控制。</span><span class="sxs-lookup"><span data-stu-id="b8351-142">These controls give you additional flexibility and control when managing apps in your enterprise.</span></span>
