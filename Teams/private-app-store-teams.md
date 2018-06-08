---
title: 管理 Microsoft 团队专用应用程序商店
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: 用于管理中的 Microsoft 团队专用应用程序商店的应用程序的指南。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6aaa763c423d7756808856706375f96f99224b9e
ms.sourcegitcommit: d979aecf73da0ba493a0b3be1db4d8b997c6ce2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2018
ms.locfileid: "19694886"
---
<a name="publish-apps-to-the-microsoft-teams-private-app-store"></a><span data-ttu-id="db0c3-103">应用程序发布到 Microsoft 团队专用应用程序商店</span><span class="sxs-lookup"><span data-stu-id="db0c3-103">Publish Apps to the Microsoft Teams Private App Store</span></span>
============================================

> [!IMPORTANT]
> <span data-ttu-id="db0c3-104">此页介绍预发布功能，并包含在发布之前，可能下述更改的初步内容。</span><span class="sxs-lookup"><span data-stu-id="db0c3-104">This page describes a pre-release feature and contains preliminary content that might change substantially before it is released.</span></span> <span data-ttu-id="db0c3-105">任何屏幕截图的占位符和外观可能不同于您所看到的内容。</span><span class="sxs-lookup"><span data-stu-id="db0c3-105">Any screenshots are placeholders and might look different than what you see.</span></span>

<span data-ttu-id="db0c3-106">您可以使用 Microsoft 团队专用应用程序商店测试和分发到您的组织的业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="db0c3-106">You can use the Microsoft Teams Private App Store to test and distribute line-of-business applications to your organization.</span></span> 

<span data-ttu-id="db0c3-107">Microsoft 团队专用应用程序商店允许您分发您生成专门针对您的组织的业务线应用程序和所依赖的完成向用户的关键业务功能。</span><span class="sxs-lookup"><span data-stu-id="db0c3-107">The Microsoft Teams Private App Store lets you distribute your line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions to your users.</span></span> 
 
<span data-ttu-id="db0c3-108">有两种方法将发布到团队的专用应用程序商店的应用程序：</span><span class="sxs-lookup"><span data-stu-id="db0c3-108">There are two methods to publish apps to the Teams Private App Store:</span></span>
- <span data-ttu-id="db0c3-109">直接从团队客户端</span><span class="sxs-lookup"><span data-stu-id="db0c3-109">Directly from the Teams client</span></span> 
- <span data-ttu-id="db0c3-110">利用 Microsoft Graph Api （此方法尚不可用的预览。） Cmdlet</span><span class="sxs-lookup"><span data-stu-id="db0c3-110">Cmdlets that leverage Microsoft Graph APIs (This method is not yet available for preview.)</span></span>

## <a name="publish-an-app-to-the-teams-private-app-store-from-the-teams-client"></a><span data-ttu-id="db0c3-111">发布到团队的专用应用程序商店的应用程序，来自团队客户端</span><span class="sxs-lookup"><span data-stu-id="db0c3-111">Publish an App to the Teams Private App Store from the Teams client</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="db0c3-112">获取团队应用程序包</span><span class="sxs-lookup"><span data-stu-id="db0c3-112">Get a Teams app package</span></span>

<span data-ttu-id="db0c3-113">使用[团队应用程序 Studio](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/get-started-app-studio)创建团队应用程序包。</span><span class="sxs-lookup"><span data-stu-id="db0c3-113">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="db0c3-114">在应用程序包后，您可以将其添加到企业应用程序目录。</span><span class="sxs-lookup"><span data-stu-id="db0c3-114">Once you have the app package, you can add it to enterprise app catalog.</span></span> <span data-ttu-id="db0c3-115">时为租户中的所有用户都可以都查看应用程序目录，只有管理员能够管理它。</span><span class="sxs-lookup"><span data-stu-id="db0c3-115">While all users in the tenant can view the app catalog, only admins have the ability to manage it.</span></span>

### <a name="go-to-the-teams-private-app-store"></a><span data-ttu-id="db0c3-116">转到团队的专用应用程序商店</span><span class="sxs-lookup"><span data-stu-id="db0c3-116">Go to the Teams Private App Store</span></span>

<span data-ttu-id="db0c3-117">从 Microsoft 团队存储区中，选择用于组织特定 （在此示例中为 Contoso） 的名为新建部分。</span><span class="sxs-lookup"><span data-stu-id="db0c3-117">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="db0c3-118">您的组织中的用户可以在目录中查看应用程序，并安装到团队的成员。</span><span class="sxs-lookup"><span data-stu-id="db0c3-118">Users in your organization can view apps in the catalog and install them to teams of which they are a member.</span></span> 

![显示屏幕截图团队应用程序商店的应用程序目录。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-teams-private-app-store"></a><span data-ttu-id="db0c3-120">添加到团队的专用应用程序商店的应用程序</span><span class="sxs-lookup"><span data-stu-id="db0c3-120">Add an app to the Teams Private App Store</span></span>

<span data-ttu-id="db0c3-121">从存储区中，选择**上载自定义应用程序** > **上载 contoso**。</span><span class="sxs-lookup"><span data-stu-id="db0c3-121">From the Store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

![显示屏幕截图团队应用程序商店的应用程序目录。](media/private-app-store-teams-image02.png)

<span data-ttu-id="db0c3-123">（您还可以选择**上载我或我的团队**，该数据库称为 sideloading，使应用程序仅适用于您或您的所选团队。）</span><span class="sxs-lookup"><span data-stu-id="db0c3-123">(You can also choose **Upload for me or my teams**, which is called sideloading, that makes the app available only to your or your selected teams.)</span></span> 

<span data-ttu-id="db0c3-124">导航到应用程序包并选择它。</span><span class="sxs-lookup"><span data-stu-id="db0c3-124">Navigate to the app package and select it.</span></span>

![显示屏幕截图团队应用程序商店的应用程序目录。](media/private-app-store-teams-image03.png)

<span data-ttu-id="db0c3-126">当您返回到您的应用程序目录时，就有新的企业应用程序。</span><span class="sxs-lookup"><span data-stu-id="db0c3-126">When you go back to your app catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="db0c3-127">请记住，只有您和您的组织的成员有权访问此应用程序目录。</span><span class="sxs-lookup"><span data-stu-id="db0c3-127">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-teams-private-app-store"></a><span data-ttu-id="db0c3-128">更新团队专用应用程序商店中的应用程序</span><span class="sxs-lookup"><span data-stu-id="db0c3-128">Update an app in the Teams Private App Store</span></span>

1. <span data-ttu-id="db0c3-129">从您的应用程序目录中，选择"**...**"</span><span class="sxs-lookup"><span data-stu-id="db0c3-129">From your app catalog, select “**…**”</span></span> <span data-ttu-id="db0c3-130">在右上您要更新的应用程序。</span><span class="sxs-lookup"><span data-stu-id="db0c3-130">on top right of the app you want to update.</span></span>
2. <span data-ttu-id="db0c3-131">导航到更新的应用程序包并选择它。</span><span class="sxs-lookup"><span data-stu-id="db0c3-131">Navigate to the updated app package and select it.</span></span>

![显示屏幕截图团队应用程序商店的应用程序目录。](media/private-app-store-teams-image04.png)

<span data-ttu-id="db0c3-133">应用程序将为版本 2.0 进行了修订。</span><span class="sxs-lookup"><span data-stu-id="db0c3-133">The app will be revised to version 2.0.</span></span> <span data-ttu-id="db0c3-134">您还可以从该菜单整个公司的删除应用程序。</span><span class="sxs-lookup"><span data-stu-id="db0c3-134">You also delete the app for your entire company from this menu.</span></span>

## <a name="manage-the-teams-private-app-store-by-using-cmdlets-and-microsoft-graph-apis"></a><span data-ttu-id="db0c3-135">使用 cmdlet 和 Microsoft Graph Api 管理团队专用应用程序商店</span><span class="sxs-lookup"><span data-stu-id="db0c3-135">Manage the Teams Private App Store by using cmdlets and Microsoft Graph APIs</span></span>

<span data-ttu-id="db0c3-136">此方法尚不可用的预览。</span><span class="sxs-lookup"><span data-stu-id="db0c3-136">This method is not yet available for preview.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-private-apps"></a><span data-ttu-id="db0c3-137">使用 Office 365 管理门户管理专用应用程序</span><span class="sxs-lookup"><span data-stu-id="db0c3-137">Use the Office 365 admin portal to manage Private Apps</span></span>

<span data-ttu-id="db0c3-138">如果您有需要 bug 修补程序的应用程序，您可以临时禁用通过 Office 365 管理门户的应用程序。</span><span class="sxs-lookup"><span data-stu-id="db0c3-138">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="db0c3-139">除了前面的设置是，现在有部分专用于贵公司的应用程序。</span><span class="sxs-lookup"><span data-stu-id="db0c3-139">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="db0c3-140">您可以选择您想要启用或禁用的应用程序。</span><span class="sxs-lookup"><span data-stu-id="db0c3-140">You can choose which apps you want to enable or disable.</span></span>

![显示屏幕截图团队应用程序商店的应用程序目录。](media/private-app-store-teams-image05.png)

<span data-ttu-id="db0c3-142">这会阻止用户从与该应用程序，而不完全删除应用程序进行交互。</span><span class="sxs-lookup"><span data-stu-id="db0c3-142">This blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="db0c3-143">这些控件为管理员提供更大的灵活性和控制时您企业中的应用程序的管理。</span><span class="sxs-lookup"><span data-stu-id="db0c3-143">These controls give admins additional flexibility and control when governance of apps in your enterprise.</span></span> 


