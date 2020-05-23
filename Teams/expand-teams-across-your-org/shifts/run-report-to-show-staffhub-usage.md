---
title: 运行报告以显示活动 StaffHub 的使用情况
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解如何运行报表以获取组织中活动 StaffHub 用户的列表。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5701e508440a338e0f0ba1fd133dac98ec35d57f
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2020
ms.locfileid: "44349626"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a><span data-ttu-id="ce11c-103">运行报告以显示活动 StaffHub 的使用情况</span><span class="sxs-lookup"><span data-stu-id="ce11c-103">Run a report to show active StaffHub usage</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce11c-104">2020年6月30日生效，Microsoft StaffHub 将停用。</span><span class="sxs-lookup"><span data-stu-id="ce11c-104">Effective June 30, 2020, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="ce11c-105">我们正在将 StaffHub 功能构建到 Microsoft 团队中。</span><span class="sxs-lookup"><span data-stu-id="ce11c-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="ce11c-106">今天，团队包括 "倒班" 应用，用于计划管理，而其他功能将随着时间的推移而推出。</span><span class="sxs-lookup"><span data-stu-id="ce11c-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="ce11c-107">StaffHub 将在2020年6月30日停止为所有用户工作。</span><span class="sxs-lookup"><span data-stu-id="ce11c-107">StaffHub will stop working for all users on June 30, 2020.</span></span> <span data-ttu-id="ce11c-108">任何试图打开 StaffHub 的人都将显示一条消息，指导他们下载团队。</span><span class="sxs-lookup"><span data-stu-id="ce11c-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="ce11c-109">若要了解详细信息，请参阅[Microsoft StaffHub 已停用](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="ce11c-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="ce11c-110">使用本文中的步骤运行报表，获取组织中活动 StaffHub 用户的列表。</span><span class="sxs-lookup"><span data-stu-id="ce11c-110">Use the steps in this article to run a report to get a list of active StaffHub users in your organization.</span></span> <span data-ttu-id="ce11c-111">当你准备[将 StaffHub 团队移动到 Microsoft 团队](move-staffhub-teams-to-shifts-in-teams.md)时，此信息可能会很方便。</span><span class="sxs-lookup"><span data-stu-id="ce11c-111">This information may come in handy when you prepare to [move your StaffHub teams to Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span> <span data-ttu-id="ce11c-112">在报表中，当你将 StaffHub 切换到团队时，你将知道你需要在通信中加入的人员。</span><span class="sxs-lookup"><span data-stu-id="ce11c-112">From the report, you'll know who you need to include in your communications when you make the switch from StaffHub to Teams.</span></span>

<span data-ttu-id="ce11c-113">你需要拥有 Azure AD Premium 才能执行本文中的步骤。</span><span class="sxs-lookup"><span data-stu-id="ce11c-113">You need to have Azure AD Premium to perform the steps in this article.</span></span>

1. <span data-ttu-id="ce11c-114">登录到 Azure 门户。</span><span class="sxs-lookup"><span data-stu-id="ce11c-114">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="ce11c-115">在左窗格中，单击 " **Azure Active Directory**资源"。</span><span class="sxs-lookup"><span data-stu-id="ce11c-115">In the left pane, click the **Azure Active Directory** resource.</span></span>
3. <span data-ttu-id="ce11c-116">在 "**监视**" 下，单击 "**登录**"。</span><span class="sxs-lookup"><span data-stu-id="ce11c-116">Under **Monitoring**, click **Sign-ins**.</span></span>
4. <span data-ttu-id="ce11c-117">在 "**应用程序**" 下，键入**Microsoft StaffHub**。</span><span class="sxs-lookup"><span data-stu-id="ce11c-117">Under **Application**, type **Microsoft StaffHub**.</span></span>
5. <span data-ttu-id="ce11c-118">为报表设置所需的日期范围，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="ce11c-118">Set the date range that you want for the report, and then click **Apply**.</span></span> 

    ![显示如何显示活动 StaffHub 用法的步骤的屏幕截图](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a><span data-ttu-id="ce11c-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="ce11c-120">Related topics</span></span>

- [<span data-ttu-id="ce11c-121">将 Microsoft StaffHub 团队移动到 Microsoft 团队中的倒班</span><span class="sxs-lookup"><span data-stu-id="ce11c-121">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
