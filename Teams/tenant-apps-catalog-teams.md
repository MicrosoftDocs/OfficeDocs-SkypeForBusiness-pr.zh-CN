---
title: 将应用程序发布到 Microsoft 团队租户的应用程序目录
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/02/2018
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: 面向 Microsoft 团队租户的应用程序目录中发布应用程序的指南。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 655a9da3670a7894e581cd2e6adebd02ef22706b
ms.sourcegitcommit: d619e44d685e2109b995ffd67ff4b98e5647c8ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/02/2018
ms.locfileid: "21762932"
---
<a name="publish-apps-to-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="0c10d-103">将应用程序发布到 Microsoft 团队租户的应用程序目录</span><span class="sxs-lookup"><span data-stu-id="0c10d-103">Publish apps to the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

<span data-ttu-id="0c10d-104">您可以使用 Microsoft 团队租户的应用程序目录以测试和分发到您的组织的业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="0c10d-104">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span> 

<span data-ttu-id="0c10d-105">团队租户的应用程序目录允许您分发您生成专门针对您的组织的业务线应用程序和所依赖的完成向用户的关键业务功能。</span><span class="sxs-lookup"><span data-stu-id="0c10d-105">The Teams Tenant Apps Catalog lets you distribute your line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions to your users.</span></span> 
 
<span data-ttu-id="0c10d-106">您可以直接从团队客户端团队租户的应用程序目录发布应用程序。</span><span class="sxs-lookup"><span data-stu-id="0c10d-106">You can publish apps to the Teams Tenant Apps Catalog directly from the Teams client.</span></span>

## <a name="publish-an-app-to-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="0c10d-107">从工作组客户端租户的应用程序目录发布应用程序</span><span class="sxs-lookup"><span data-stu-id="0c10d-107">Publish an app to the Tenant Apps Catalog from the Teams client</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="0c10d-108">获取团队应用程序包</span><span class="sxs-lookup"><span data-stu-id="0c10d-108">Get a Teams app package</span></span>

<span data-ttu-id="0c10d-109">使用[团队应用程序 Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)创建团队应用程序包。</span><span class="sxs-lookup"><span data-stu-id="0c10d-109">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="0c10d-110">在应用程序包后，您可以将其添加到企业应用程序目录。</span><span class="sxs-lookup"><span data-stu-id="0c10d-110">Once you have the app package, you can add it to enterprise app catalog.</span></span> <span data-ttu-id="0c10d-111">时为租户中的所有用户视图应用程序目录，当前仅全局管理员可以发布和管理它的功能。</span><span class="sxs-lookup"><span data-stu-id="0c10d-111">While all users in the tenant can view the app catalog, currently only global admins have the ability to publish and manage it.</span></span> <span data-ttu-id="0c10d-112">（最终，团队 admins 都将能够执行此操作以及。）</span><span class="sxs-lookup"><span data-stu-id="0c10d-112">(Eventually, Teams admins will be able to do this as well.)</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="0c10d-113">转到租户的应用程序目录</span><span class="sxs-lookup"><span data-stu-id="0c10d-113">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="0c10d-114">从 Microsoft 团队存储区中，选择用于组织特定 （在此示例中为 Contoso） 的名为新建部分。</span><span class="sxs-lookup"><span data-stu-id="0c10d-114">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="0c10d-115">您的组织中的用户可以在目录中查看应用程序，并安装到团队的成员。</span><span class="sxs-lookup"><span data-stu-id="0c10d-115">Users in your organization can view apps in the catalog and install them to teams of which they are a member.</span></span> 

![显示屏幕截图团队应用程序商店的应用程序目录。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="0c10d-117">将应用程序添加到租户的应用程序目录</span><span class="sxs-lookup"><span data-stu-id="0c10d-117">Add an app to the Tenant Apps Catalog</span></span>

<span data-ttu-id="0c10d-118">从存储区中，选择**上载自定义应用程序** > **上载 contoso**。</span><span class="sxs-lookup"><span data-stu-id="0c10d-118">From the Store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

![显示屏幕截图团队应用程序商店的应用程序目录。](media/private-app-store-teams-image02.png)

<span data-ttu-id="0c10d-120">（您还可以选择**上载我或我的团队**，该数据库称为 sideloading，使应用程序仅适用于您或您的所选团队。）</span><span class="sxs-lookup"><span data-stu-id="0c10d-120">(You can also choose **Upload for me or my teams**, which is called sideloading, that makes the app available only to your or your selected teams.)</span></span> 

<span data-ttu-id="0c10d-121">导航到应用程序包并选择它。</span><span class="sxs-lookup"><span data-stu-id="0c10d-121">Navigate to the app package and select it.</span></span>

![显示屏幕截图团队应用程序商店的应用程序目录。](media/private-app-store-teams-image03.png)

<span data-ttu-id="0c10d-123">当您返回到您的租户的应用程序目录中时，就有新的企业应用程序。</span><span class="sxs-lookup"><span data-stu-id="0c10d-123">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="0c10d-124">请记住，只有您和您的组织的成员有权访问此应用程序目录。</span><span class="sxs-lookup"><span data-stu-id="0c10d-124">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="0c10d-125">更新应用程序中租户的应用程序目录</span><span class="sxs-lookup"><span data-stu-id="0c10d-125">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="0c10d-126">从租户的应用程序目录，选择"**...**"</span><span class="sxs-lookup"><span data-stu-id="0c10d-126">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="0c10d-127">在右上您要更新的应用程序。</span><span class="sxs-lookup"><span data-stu-id="0c10d-127">on top right of the app you want to update.</span></span>
2. <span data-ttu-id="0c10d-128">导航到更新的应用程序包并选择它。</span><span class="sxs-lookup"><span data-stu-id="0c10d-128">Navigate to the updated app package and select it.</span></span>

![显示屏幕截图团队应用程序商店的应用程序目录。](media/private-app-store-teams-image04.png)

<span data-ttu-id="0c10d-130">应用程序将为版本 2.0 进行了修订。</span><span class="sxs-lookup"><span data-stu-id="0c10d-130">The app will be revised to version 2.0.</span></span> <span data-ttu-id="0c10d-131">您还可以从该菜单整个公司的删除应用程序。</span><span class="sxs-lookup"><span data-stu-id="0c10d-131">You also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="0c10d-132">使用 Office 365 管理门户管理租户的应用程序目录</span><span class="sxs-lookup"><span data-stu-id="0c10d-132">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="0c10d-133">如果您有需要 bug 修补程序的应用程序，您可以临时禁用通过 Office 365 管理门户的应用程序。</span><span class="sxs-lookup"><span data-stu-id="0c10d-133">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="0c10d-134">除了前面的设置是，现在有部分专用于贵公司的应用程序。</span><span class="sxs-lookup"><span data-stu-id="0c10d-134">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="0c10d-135">您可以选择您想要启用或禁用的应用程序。</span><span class="sxs-lookup"><span data-stu-id="0c10d-135">You can choose which apps you want to enable or disable.</span></span>

![显示屏幕截图团队应用程序商店的应用程序目录。](media/private-app-store-teams-image05.png)

<span data-ttu-id="0c10d-137">这会阻止用户从与该应用程序，而不完全删除应用程序进行交互。</span><span class="sxs-lookup"><span data-stu-id="0c10d-137">This blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="0c10d-138">这些控件为管理员提供更大的灵活性和控制时您企业中的应用程序的管理。</span><span class="sxs-lookup"><span data-stu-id="0c10d-138">These controls give admins additional flexibility and control when governance of apps in your enterprise.</span></span> 


