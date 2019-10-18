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
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 49091f7d8ada565adea61bf8219c6da828358893
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569659"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a><span data-ttu-id="d0235-103">运行报告以显示活动 StaffHub 的使用情况</span><span class="sxs-lookup"><span data-stu-id="d0235-103">Run a report to show active StaffHub usage</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d0235-104">2019年12月31日生效，Microsoft StaffHub 将停用。</span><span class="sxs-lookup"><span data-stu-id="d0235-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="d0235-105">我们正在将 StaffHub 功能构建到 Microsoft 团队中。</span><span class="sxs-lookup"><span data-stu-id="d0235-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="d0235-106">今天，团队包括 "倒班" 应用，用于计划管理，而其他功能将随着时间的推移而推出。</span><span class="sxs-lookup"><span data-stu-id="d0235-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="d0235-107">StaffHub 将停止为2019年12月31日的所有用户工作。</span><span class="sxs-lookup"><span data-stu-id="d0235-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="d0235-108">任何试图打开 StaffHub 的人都将显示一条消息，指导他们下载团队。</span><span class="sxs-lookup"><span data-stu-id="d0235-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="d0235-109">若要了解详细信息，请参阅[Microsoft StaffHub 已停用](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="d0235-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="d0235-110">使用本文中的步骤运行报表，获取组织中活动 StaffHub 用户的列表。</span><span class="sxs-lookup"><span data-stu-id="d0235-110">Use the steps in this article to run a report to get a list of active StaffHub users in your organization.</span></span> <span data-ttu-id="d0235-111">当你准备[将 StaffHub 团队移动到 Microsoft 团队](move-staffhub-teams-to-shifts-in-teams.md)时，此信息可能会很方便。</span><span class="sxs-lookup"><span data-stu-id="d0235-111">This information may come in handy when you prepare to [move your StaffHub teams to Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span> <span data-ttu-id="d0235-112">在报表中，当你将 StaffHub 切换到团队时，你将知道你需要在通信中加入的人员。</span><span class="sxs-lookup"><span data-stu-id="d0235-112">From the report, you'll know who you need to include in your communications when you make the switch from StaffHub to Teams.</span></span>

<span data-ttu-id="d0235-113">你需要拥有 Azure AD Premium 才能执行本文中的步骤。</span><span class="sxs-lookup"><span data-stu-id="d0235-113">You need to have Azure AD Premium to perform the steps in this article.</span></span>

1. <span data-ttu-id="d0235-114">登录到 Azure 门户。</span><span class="sxs-lookup"><span data-stu-id="d0235-114">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="d0235-115">在左窗格中，单击 " **Azure Active Directory**资源"。</span><span class="sxs-lookup"><span data-stu-id="d0235-115">In the left pane, click the **Azure Active Directory** resource.</span></span>
3. <span data-ttu-id="d0235-116">在 "**监视**" 下，单击 "**登录**"。</span><span class="sxs-lookup"><span data-stu-id="d0235-116">Under **Monitoring**, click **Sign-ins**.</span></span>
4. <span data-ttu-id="d0235-117">在 "**应用程序**" 下，键入**Microsoft StaffHub**。</span><span class="sxs-lookup"><span data-stu-id="d0235-117">Under **Application**, type **Microsoft StaffHub**.</span></span>
5. <span data-ttu-id="d0235-118">为报表设置所需的日期范围，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="d0235-118">Set the date range that you want for the report, and then click **Apply**.</span></span> 

    ![显示如何显示活动 StaffHub 用法的步骤的屏幕截图](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a><span data-ttu-id="d0235-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="d0235-120">Related topics</span></span>

- [<span data-ttu-id="d0235-121">将 Microsoft StaffHub 团队移动到 Microsoft 团队中的倒班</span><span class="sxs-lookup"><span data-stu-id="d0235-121">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
