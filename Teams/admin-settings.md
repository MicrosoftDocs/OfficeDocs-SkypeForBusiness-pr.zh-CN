---
title: Microsoft Teams 中适用于应用的管理设置
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag
description: 了解如何在 Microsoft Teams 中允许和启用应用，包括侧向加载外部应用。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.apppolicies.adminsettings
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ad61e412bbbe0a880a279179f40124895d6e38a5
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "30568405"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="04739-103">Microsoft Teams 中适用于应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="04739-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="04739-104">应用程序是选项卡、 连接器、 自动程序或这三种，提供通过团队 （第一方应用程序和也称为应用程序默认） 或第三方 （也称为外部应用程序） 的任意组合。</span><span class="sxs-lookup"><span data-stu-id="04739-104">Apps are tabs, connectors, bots, or any combination of these three, provided by Teams (first-party apps, and also known as default apps) or by a third-party (also known as external apps).</span></span> <span data-ttu-id="04739-105">在 Microsoft 365 管理中心，您可以启用和禁用默认应用程序和配置设置来控制外部应用程序。</span><span class="sxs-lookup"><span data-stu-id="04739-105">In the Microsoft 365 admin center, you can enable and disable default apps and configure settings to control external apps.</span></span> <span data-ttu-id="04739-106">这些设置允许您指定的外部应用程序允许的和不允许，新的外部应用程序行为，以及是否允许端加载应用程序。</span><span class="sxs-lookup"><span data-stu-id="04739-106">These settings let you specify which external apps are allowed and disallowed, new external app behavior, and whether side-loading apps is allowed.</span></span>

 <span data-ttu-id="04739-107">若要管理团队中的应用程序的管理设置，请转到 Microsoft 365 管理中心，并选择**设置** > **服务 & 加载项** > **Microsoft 团队**。</span><span class="sxs-lookup"><span data-stu-id="04739-107">To manage admin settings for apps in Teams, go to the Microsoft 365 admin center and choose **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> <span data-ttu-id="04739-108">如果你已使用 Office 365 管理员身份登录，点击此链接应该能实现此操作：</span><span class="sxs-lookup"><span data-stu-id="04739-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span>

https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

<span data-ttu-id="04739-109">要了解有关应用的管理员设置的详细信息，请观看以下视频：</span><span class="sxs-lookup"><span data-stu-id="04739-109">To learn more about admin settings for apps, see the following video:</span></span> 
 
|  |  |
|---------|---------|
| <span data-ttu-id="04739-110">管理 Microsoft Teams 中的应用体验</span><span class="sxs-lookup"><span data-stu-id="04739-110">Managing the App Experience in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/CHnpw1O7EgM" frameborder="0" allowfullscreen></iframe>     | 

## <a name="allow-external-apps-in-teams"></a><span data-ttu-id="04739-111">在 Teams 中允许外部应用</span><span class="sxs-lookup"><span data-stu-id="04739-111">Allow external apps in Teams</span></span>

<span data-ttu-id="04739-112">默认情况下，启用“**在 Microsoft Teams 中允许外部应用**”，并选中所有应用。</span><span class="sxs-lookup"><span data-stu-id="04739-112">By default, **Allow external apps in Microsoft Teams** is turned on, with all apps selected.</span></span> <span data-ttu-id="04739-113">如果要关闭此设置，则会禁用所有外部第三方应用程序。</span><span class="sxs-lookup"><span data-stu-id="04739-113">If you turn off this setting, all external third-party apps are disabled.</span></span> 

## <a name="enable-new-external-apps-by-default"></a><span data-ttu-id="04739-114">默认启用新的外部应用</span><span class="sxs-lookup"><span data-stu-id="04739-114">Enable new external apps by default</span></span>

#### <a name="trophy-best-practice-manage-external-apps-individually"></a><span data-ttu-id="04739-115">:trophy: 最佳实践：单独管理外部应用</span><span class="sxs-lookup"><span data-stu-id="04739-115">:trophy: Best practice: Manage external apps individually</span></span> 
 
<span data-ttu-id="04739-116">要开启一些应用（并关闭其他应用），请关闭“**允许侧向加载外部应用**”。</span><span class="sxs-lookup"><span data-stu-id="04739-116">To turn on some apps (and turn off others), turn off **Allow sideloading of external apps**.</span></span> <span data-ttu-id="04739-117">然后关闭你不希望用户使用的任何应用。</span><span class="sxs-lookup"><span data-stu-id="04739-117">Then turn off any apps you don't want your users to use.</span></span> <span data-ttu-id="04739-118">可选：关闭“**默认启用新的外部应用**”（如果你希望控制新应用）。</span><span class="sxs-lookup"><span data-stu-id="04739-118">Optional: Turn off **Enable new external apps by default** (if you want to control new apps).</span></span> 

> [!NOTE]
> <span data-ttu-id="04739-119">默认应用程序，如构建的 Microsoft，不受**启用默认情况下的新外部应用程序**的设置。</span><span class="sxs-lookup"><span data-stu-id="04739-119">Default apps, such as those built by Microsoft, are not affected by the **Enable new external apps by default** setting.</span></span> <span data-ttu-id="04739-120">默认情况下，当 Microsoft 发布的启用了新的应用程序。</span><span class="sxs-lookup"><span data-stu-id="04739-120">New apps are enabled by default when released by Microsoft.</span></span>

<span data-ttu-id="04739-121">启用此设置后，用户可以激活新的应用程序，只要它们会添加到团队应用程序目录。</span><span class="sxs-lookup"><span data-stu-id="04739-121">When this setting is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="04739-122">要打开 Teams 应用目录，单击 Teams 底部的“**应用商店**”，然后单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="04739-122">To open the Teams app catalog, click **Store** at the bottom of Teams, then click **Apps**.</span></span> <span data-ttu-id="04739-123">如果您希望控制哪些应用程序，请关闭此设置。</span><span class="sxs-lookup"><span data-stu-id="04739-123">If you want to control which apps are available, turn off this setting.</span></span> <span data-ttu-id="04739-124">当然，如果你关闭此开关，必须记得定期查看新应用，以免贵组织错过酷炫的新应用。</span><span class="sxs-lookup"><span data-stu-id="04739-124">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

<span data-ttu-id="04739-125">侧向加载是你通过直接将 zip 文件上载到团队来向 Teams 添加应用的方式。</span><span class="sxs-lookup"><span data-stu-id="04739-125">Sideloading is how you add an app to Teams by uploading a zip file directly to a team.</span></span> <span data-ttu-id="04739-126">利用侧向加载可以在开发应用时对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="04739-126">Sideloading lets you test an app as it's being developed.</span></span> <span data-ttu-id="04739-127">利用它还可以构建仅限内部使用的应用并与你的团队共享该应用，而无需将其提交至 Office 应用商店中的 Teams 应用目录。</span><span class="sxs-lookup"><span data-stu-id="04739-127">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Office Store.</span></span> 

<span data-ttu-id="04739-128">仅团队所有者或获得权限的成员可以向 Teams 中侧向加载应用。</span><span class="sxs-lookup"><span data-stu-id="04739-128">Only team owners, or members who are granted permissions, can sideload apps into Teams.</span></span>  

<span data-ttu-id="04739-129">![扩展外部应用程序部分的屏幕截图。](media/teams-tenant-wide-settings-external-apps.png "显示外部应用程序扩展外部应用程序部分的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="04739-129">![Screen shot of the expanded External Apps section.](media/teams-tenant-wide-settings-external-apps.png "Screen shot of the expanded External Apps section showing external apps")</span></span>

## <a name="creating-and-uploading-app-packages"></a><span data-ttu-id="04739-130">创建和上载应用包</span><span class="sxs-lookup"><span data-stu-id="04739-130">Creating and uploading app packages</span></span> 

<span data-ttu-id="04739-131">若要了解有关应用程序的详细信息，请参阅[适用于团队的开发应用程序](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview)。</span><span class="sxs-lookup"><span data-stu-id="04739-131">To learn more about apps, see [Develop apps for Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span></span> 



