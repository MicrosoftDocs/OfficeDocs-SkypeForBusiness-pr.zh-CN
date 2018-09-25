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
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5172781911a944b5fd25042260cebdd77a48ddaa
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25013864"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="cbf52-103">Microsoft Teams 中适用于应用的管理设置</span><span class="sxs-lookup"><span data-stu-id="cbf52-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="cbf52-104">应用是第三方服务提供的选项卡、连接器或聊天机器人或这三者的任意组合。</span><span class="sxs-lookup"><span data-stu-id="cbf52-104">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service.</span></span> <span data-ttu-id="cbf52-105">可以在 Office 365 管理中心配置 Teams 管理策略来控制允许哪些外部第三方应用。</span><span class="sxs-lookup"><span data-stu-id="cbf52-105">There are Teams admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed.</span></span> <span data-ttu-id="cbf52-106">这些策略允许您指定的应用程序允许的和不允许，新的外部应用程序行为，以及是否允许端加载应用程序。</span><span class="sxs-lookup"><span data-stu-id="cbf52-106">These policies let you specify which apps are allowed and disallowed, new external app behavior, and whether side-loading apps is allowed.</span></span>

> [!NOTE]
> <span data-ttu-id="cbf52-107">要管理 Teams 中的应用的管理员设置，请转到 Office 365 管理中心并打开“**设置**” > “**服务和外接程序**”，然后选择“**Microsoft Teams**”。</span><span class="sxs-lookup"><span data-stu-id="cbf52-107">To manage admin settings for apps in Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="cbf52-108">如果你已使用 Office 365 管理员身份登录，点击此链接应该能实现此操作：</span><span class="sxs-lookup"><span data-stu-id="cbf52-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span>
> 
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

<span data-ttu-id="cbf52-109">要了解有关应用的管理员设置的详细信息，请观看以下视频：</span><span class="sxs-lookup"><span data-stu-id="cbf52-109">To learn more about admin settings for apps, see the following video:</span></span> 
 
|  |  |
|---------|---------|
| <span data-ttu-id="cbf52-110">管理 Microsoft Teams 中的应用体验</span><span class="sxs-lookup"><span data-stu-id="cbf52-110">Managing the App Experience in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/CHnpw1O7EgM" frameborder="0" allowfullscreen></iframe>     | 

## <a name="allow-external-apps-in-teams"></a><span data-ttu-id="cbf52-111">在 Teams 中允许外部应用</span><span class="sxs-lookup"><span data-stu-id="cbf52-111">Allow external apps in Teams</span></span>

<span data-ttu-id="cbf52-112">默认情况下，启用“**在 Microsoft Teams 中允许外部应用**”，并选中所有应用。</span><span class="sxs-lookup"><span data-stu-id="cbf52-112">By default, **Allow external apps in Microsoft Teams** is turned on, with all apps selected.</span></span>  <span data-ttu-id="cbf52-113">如果关闭此开关，则禁用所有外部第三方应用。</span><span class="sxs-lookup"><span data-stu-id="cbf52-113">If you turn off this switch, all external third-party apps are disabled.</span></span> 

## <a name="enable-new-external-apps-by-default"></a><span data-ttu-id="cbf52-114">默认启用新的外部应用</span><span class="sxs-lookup"><span data-stu-id="cbf52-114">Enable new external apps by default</span></span>

#### <a name="trophy-best-practice-manage-external-apps-individually"></a><span data-ttu-id="cbf52-115">:trophy: 最佳实践：单独管理外部应用</span><span class="sxs-lookup"><span data-stu-id="cbf52-115">:trophy: Best practice: Manage external apps individually</span></span> 
 
<span data-ttu-id="cbf52-116">要开启一些应用（并关闭其他应用），请关闭“**允许侧向加载外部应用**”。</span><span class="sxs-lookup"><span data-stu-id="cbf52-116">To turn on some apps (and turn off others), turn off **Allow sideloading of external apps**.</span></span> <span data-ttu-id="cbf52-117">然后关闭你不希望用户使用的任何应用。</span><span class="sxs-lookup"><span data-stu-id="cbf52-117">Then turn off any apps you don't want your users to use.</span></span> <span data-ttu-id="cbf52-118">可选：关闭“**默认启用新的外部应用**”（如果你希望控制新应用）。</span><span class="sxs-lookup"><span data-stu-id="cbf52-118">Optional: Turn off **Enable new external apps by default** (if you want to control new apps).</span></span> 

> [!NOTE]
> <span data-ttu-id="cbf52-119">默认应用程序，如构建的 Microsoft，不受**启用默认情况下的新外部应用程序**的设置。</span><span class="sxs-lookup"><span data-stu-id="cbf52-119">Default apps, such as those built by Microsoft, are not affected by the **Enable new external apps by default** setting.</span></span> <span data-ttu-id="cbf52-120">默认情况下，当 Microsoft 发布的启用了新的应用程序。</span><span class="sxs-lookup"><span data-stu-id="cbf52-120">New apps are enabled by default when released by Microsoft.</span></span>

<span data-ttu-id="cbf52-121">打开此开关后，用户可以在新应用添加到 Teams 应用目录后立即激活它们。</span><span class="sxs-lookup"><span data-stu-id="cbf52-121">When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="cbf52-122">要打开 Teams 应用目录，单击 Teams 底部的“**应用商店**”，然后单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="cbf52-122">To open the Teams app catalog, click **Store** at the bottom of Teams, then click **Apps**.</span></span> <span data-ttu-id="cbf52-123">如果你希望控制提供哪些应用，请关闭此开关。</span><span class="sxs-lookup"><span data-stu-id="cbf52-123">If you want to control which apps are available, turn this switch off.</span></span> <span data-ttu-id="cbf52-124">当然，如果你关闭此开关，必须记得定期查看新应用，以免贵组织错过酷炫的新应用。</span><span class="sxs-lookup"><span data-stu-id="cbf52-124">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

<span data-ttu-id="cbf52-125">侧向加载是你通过直接将 zip 文件上载到团队来向 Teams 添加应用的方式。</span><span class="sxs-lookup"><span data-stu-id="cbf52-125">Sideloading is how you add an app to Teams by uploading a zip file directly to a team.</span></span> <span data-ttu-id="cbf52-126">利用侧向加载可以在开发应用时对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="cbf52-126">Sideloading lets you test an app as it's being developed.</span></span> <span data-ttu-id="cbf52-127">利用它还可以构建仅限内部使用的应用并与你的团队共享该应用，而无需将其提交至 Office 应用商店中的 Teams 应用目录。</span><span class="sxs-lookup"><span data-stu-id="cbf52-127">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Office Store.</span></span> 

<span data-ttu-id="cbf52-128">仅团队所有者或获得权限的成员可以向 Teams 中侧向加载应用。</span><span class="sxs-lookup"><span data-stu-id="cbf52-128">Only team owners, or members who are granted permissions, can sideload apps into Teams.</span></span>  

![在租户范围的设置展开应用程序部分的屏幕截图。](media/Admin_settings_for_apps_in_Microsoft_Teams_image2.png)

## <a name="creating-and-uploading-app-packages"></a><span data-ttu-id="cbf52-130">创建和上载应用包</span><span class="sxs-lookup"><span data-stu-id="cbf52-130">Creating and uploading app packages</span></span> 

<span data-ttu-id="cbf52-131">若要了解有关应用程序的详细信息，请参阅[适用于团队的开发应用程序](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview)。</span><span class="sxs-lookup"><span data-stu-id="cbf52-131">To learn more about apps, see [Develop apps for Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview).</span></span> 



