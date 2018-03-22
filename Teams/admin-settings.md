---
title: Microsoft Teams 中适用于应用的管理设置
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: 了解如何在 Microsoft Teams 中允许和启用应用，包括侧向加载外部应用。
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58fb8598f8e63aa3e8abc943dcffde64452da462
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="319cc-103">Microsoft Teams 中适用于应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="319cc-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="319cc-104">应用是第三方服务提供的选项卡、连接器或聊天机器人或这三者的任意组合。</span><span class="sxs-lookup"><span data-stu-id="319cc-104">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service.</span></span> <span data-ttu-id="319cc-105">可以在 Office 365 管理中心配置 Teams 管理策略来控制允许哪些外部第三方应用。</span><span class="sxs-lookup"><span data-stu-id="319cc-105">There are Teams admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed.</span></span> <span data-ttu-id="319cc-106">通过这些策略可以指定允许和不允许哪些应用、新的外部应用行为以及是否允许侧向加载应用。</span><span class="sxs-lookup"><span data-stu-id="319cc-106">These policies let you specify which apps are allowed and disallowed, new external App behavior, and whether side-loading apps is allowed.</span></span>

> [!NOTE]
> <span data-ttu-id="319cc-107">要管理 Teams 中的应用的管理员设置，请转到 Office 365 管理中心并打开“**设置**” > “**服务和外接程序**”，然后选择“**Microsoft Teams**”。</span><span class="sxs-lookup"><span data-stu-id="319cc-107">To manage admin settings for apps in Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="319cc-108">如果你已使用 Office 365 管理员身份登录，点击此链接应该能实现此操作：</span><span class="sxs-lookup"><span data-stu-id="319cc-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span>
> 
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

<span data-ttu-id="319cc-109">要了解有关应用的管理员设置的详细信息，请观看以下视频：</span><span class="sxs-lookup"><span data-stu-id="319cc-109">To learn more about admin settings for apps, see the following video:</span></span> 
 
|  |  |
|---------|---------|
| <span data-ttu-id="319cc-110">管理 Microsoft Teams 中的应用体验</span><span class="sxs-lookup"><span data-stu-id="319cc-110">Managing the App Experience in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/CHnpw1O7EgM" frameborder="0" allowfullscreen></iframe>     | 

## <a name="allow-external-apps-in-teams"></a><span data-ttu-id="319cc-111">在 Teams 中允许外部应用</span><span class="sxs-lookup"><span data-stu-id="319cc-111">Allow external apps in Teams</span></span>

<span data-ttu-id="319cc-112">默认情况下，启用“**在 Microsoft Teams 中允许外部应用**”，并选中所有应用。</span><span class="sxs-lookup"><span data-stu-id="319cc-112">By default, **Allow external apps in Microsoft Teams** is turned on, with all apps selected.</span></span>  <span data-ttu-id="319cc-113">如果关闭此开关，则禁用所有外部第三方应用。</span><span class="sxs-lookup"><span data-stu-id="319cc-113">If you turn off this switch, all external third-party apps are disabled.</span></span> 

## <a name="enable-new-external-apps-by-default"></a><span data-ttu-id="319cc-114">默认启用新的外部应用</span><span class="sxs-lookup"><span data-stu-id="319cc-114">Enable new external apps by default</span></span>

#### <a name="trophy-best-practice-manage-external-apps-individually"></a><span data-ttu-id="319cc-115">:trophy: 最佳实践：单独管理外部应用</span><span class="sxs-lookup"><span data-stu-id="319cc-115">:trophy: Best practice: Manage external apps individually</span></span> 
 
<span data-ttu-id="319cc-116">要开启一些应用（并关闭其他应用），请关闭“**允许侧向加载外部应用**”。</span><span class="sxs-lookup"><span data-stu-id="319cc-116">To turn on some apps (and turn off others), turn off **Allow sideloading of external apps**.</span></span> <span data-ttu-id="319cc-117">然后关闭你不希望用户使用的任何应用。</span><span class="sxs-lookup"><span data-stu-id="319cc-117">Then turn off any apps you don't want your users to use.</span></span> <span data-ttu-id="319cc-118">可选：关闭“**默认启用新的外部应用**”（如果你希望控制新应用）。</span><span class="sxs-lookup"><span data-stu-id="319cc-118">Optional: Turn off **Enable new external apps by default** (if you want to control new apps).</span></span> 

<span data-ttu-id="319cc-119">打开此开关后，用户可以在新应用添加到 Teams 应用目录后立即激活它们。</span><span class="sxs-lookup"><span data-stu-id="319cc-119">When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="319cc-120">要打开 Teams 应用目录，单击 Teams 底部的“**应用商店**”，然后单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="319cc-120">To open the Teams app catalog, click **Store** at the bottom of Teams, then click **Apps**.</span></span> <span data-ttu-id="319cc-121">如果你希望控制提供哪些应用，请关闭此开关。</span><span class="sxs-lookup"><span data-stu-id="319cc-121">If you want to control which apps are available, turn this switch off.</span></span> <span data-ttu-id="319cc-122">当然，如果你关闭此开关，必须记得定期查看新应用，以免贵组织错过酷炫的新应用。</span><span class="sxs-lookup"><span data-stu-id="319cc-122">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

<span data-ttu-id="319cc-123">侧向加载是你通过直接将 zip 文件上载到团队来向 Teams 添加应用的方式。</span><span class="sxs-lookup"><span data-stu-id="319cc-123">Sideloading is how you add an app to Teams by uploading a zip file directly to a team.</span></span> <span data-ttu-id="319cc-124">利用侧向加载可以在开发应用时对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="319cc-124">Sideloading lets you test an app as it's being developed.</span></span> <span data-ttu-id="319cc-125">利用它还可以构建仅限内部使用的应用并与你的团队共享该应用，而无需将其提交至 Office 应用商店中的 Teams 应用目录。</span><span class="sxs-lookup"><span data-stu-id="319cc-125">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Office Store.</span></span> 

<span data-ttu-id="319cc-126">仅团队所有者或获得权限的成员可以向 Teams 中侧向加载应用。</span><span class="sxs-lookup"><span data-stu-id="319cc-126">Only team owners, or members who are granted permissions, can sideload apps into Teams.</span></span>  

![展开的应用程序部分租户范围设置中的屏幕快照。](media/Admin_settings_for_apps_in_Microsoft_Teams_image2.png)


## <a name="creating-and-uploading-app-packages"></a><span data-ttu-id="319cc-128">创建和上载应用包</span><span class="sxs-lookup"><span data-stu-id="319cc-128">Creating and uploading app packages</span></span> 

<span data-ttu-id="319cc-129">要了解关于应用的详细信息，请阅读[开发适用于 Teams 的应用](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview)。</span><span class="sxs-lookup"><span data-stu-id="319cc-129">To learn more about apps, read [Develop apps for Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span></span> 



