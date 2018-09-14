---
title: 管理 Office 365 组织中的 Microsoft 团队功能
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
search.appverid: MET150
description: 了解如何启用或禁用 Office 365 组织，包括选项卡、 连接器、 自动程序或这三个任意组合中的 Microsoft 团队应用程序。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0ff482ccd6486fcab836565033a0cf7e02517717
ms.sourcegitcommit: b265545216ff36772d5dc2df381a9046bc71098e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965617"
---
# <a name="manage-microsoft-teams-features-in-your-office-365-organization"></a><span data-ttu-id="94478-103">管理 Office 365 组织中的 Microsoft 团队功能</span><span class="sxs-lookup"><span data-stu-id="94478-103">Manage Microsoft Teams features in your Office 365 organization</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="94478-104">所有团队设置很快将都迁移到新的 Microsoft 团队和 Skype 的业务 Admin Center。</span><span class="sxs-lookup"><span data-stu-id="94478-104">All Teams settings will soon be migrated to the new Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="94478-105">在 Office 365 管理中心中托管的唯一团队功能是应用程序。</span><span class="sxs-lookup"><span data-stu-id="94478-105">The only Teams feature that is managed in the Office 365 admin center is Apps.</span></span> 

<span data-ttu-id="94478-106">除非另有说明，否则选项的默认值为“开启”。</span><span class="sxs-lookup"><span data-stu-id="94478-106">Unless otherwise noted, the default value for an option is On.</span></span>

> [!NOTE] 
> <span data-ttu-id="94478-107">要管理 Teams 的管理员设置，请转到 Office 365 管理中心并打开“**设置**” > “**服务和外接程序**”，然后选择“**Microsoft Teams**”。</span><span class="sxs-lookup"><span data-stu-id="94478-107">To manage admin settings for Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="94478-108">如果你已使用 Office 365 管理员身份登录，点击此链接应该能实现此操作：</span><span class="sxs-lookup"><span data-stu-id="94478-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span> 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

## <a name="office-365-tenant-wide-settings"></a><span data-ttu-id="94478-109">Office 365 租户范围的设置</span><span class="sxs-lookup"><span data-stu-id="94478-109">Office 365 tenant-wide settings</span></span> 

<span data-ttu-id="94478-110">在**租户范围的设置**，可以打开或关闭应用程序。</span><span class="sxs-lookup"><span data-stu-id="94478-110">In **Tenant-wide settings**, you can turn on or turn off Apps.</span></span>

<span data-ttu-id="94478-111">要编辑 Teams 的**租户范围的设置**，请转到 Office 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="94478-111">To edit **Tenant-wide settings** for Teams, go to the Office 365 admin center.</span></span> <span data-ttu-id="94478-112">选择 **“设置”** > **“服务和外接程序”** > **“Microsoft Teams”**。</span><span class="sxs-lookup"><span data-stu-id="94478-112">Choose **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span>

## <a name="apps"></a><span data-ttu-id="94478-113">应用</span><span class="sxs-lookup"><span data-stu-id="94478-113">Apps</span></span>

<span data-ttu-id="94478-114">应用是第三方服务提供的选项卡、连接器或聊天机器人或这三者的任意组合。</span><span class="sxs-lookup"><span data-stu-id="94478-114">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service.</span></span> <span data-ttu-id="94478-115">可以在 Office 365 管理中心配置 Teams 管理策略来控制允许哪些外部第三方应用。</span><span class="sxs-lookup"><span data-stu-id="94478-115">There are Teams admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed.</span></span> <span data-ttu-id="94478-116">这些策略允许您指定的应用程序允许的和不允许，新的外部应用程序行为，以及是否允许端加载应用程序。</span><span class="sxs-lookup"><span data-stu-id="94478-116">These policies let you specify which apps are allowed and disallowed, new external app behavior, and whether side-loading apps is allowed.</span></span> 

<span data-ttu-id="94478-117">在 **“应用”** 下，可以为贵组织配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="94478-117">Under **Apps**, you can configure the following settings for your organization:</span></span> 

![“应用”部分屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- <span data-ttu-id="94478-119">**在 Microsoft Teams 中允许外部应用：** 如果打开此开关，用户可以添加可供 Office 365 租户使用的选项卡和聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="94478-119">**Allow external apps in Microsoft Teams**: When this switch is turned on, users can add tabs and bots that are available to the Office 365 tenant.</span></span> 
 
    ![“应用”部分中的“允许外部应用”控件的屏幕截图。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- <span data-ttu-id="94478-121">**默认启用新的外部应用：** 打开此开关后，用户可以在新应用添加到 Teams 应用目录后立即激活它们。</span><span class="sxs-lookup"><span data-stu-id="94478-121">**Enable new external apps by default**: When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="94478-122">如果你希望控制新应用，请关闭此开关。</span><span class="sxs-lookup"><span data-stu-id="94478-122">Turn off this switch if you want to control new apps.</span></span> <span data-ttu-id="94478-123">当然，如果你关闭此开关，必须记得定期查看新应用，以免贵组织错过酷炫的新应用。</span><span class="sxs-lookup"><span data-stu-id="94478-123">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

- <span data-ttu-id="94478-124">**允许侧向加载外部应用：** 如果打开此开关，用户可以安装和启用自定义聊天机器人和选项卡。</span><span class="sxs-lookup"><span data-stu-id="94478-124">**Allow sideloading of external apps**: When this switch is turned on, users can install and enable custom bots and tabs.</span></span> 

<span data-ttu-id="94478-125">要了解详细信息，请阅读 [Teams 中适用于应用的管理员设置](admin-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="94478-125">To learn more, read [Admin settings for apps in Teams](admin-settings.md).</span></span> 

