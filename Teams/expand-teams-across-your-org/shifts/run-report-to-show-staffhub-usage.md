---
title: 运行报告以显示活动 StaffHub 的使用情况
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 05/10/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 了解如何运行报表以获取组织中活动 StaffHub 用户的列表。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59931183cadec09b2fc26a55cf7e284f51198efc
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548204"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a><span data-ttu-id="9c5d1-103">运行报告以显示活动 StaffHub 的使用情况</span><span class="sxs-lookup"><span data-stu-id="9c5d1-103">Run a report to show active StaffHub usage</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9c5d1-104">2019年10月1日生效, Microsoft StaffHub 将停用。</span><span class="sxs-lookup"><span data-stu-id="9c5d1-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="9c5d1-105">我们正在将 StaffHub 功能构建到 Microsoft 团队中。</span><span class="sxs-lookup"><span data-stu-id="9c5d1-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="9c5d1-106">今天, 团队包括 "倒班" 应用, 用于计划管理, 而其他功能将随着时间的推移而推出。</span><span class="sxs-lookup"><span data-stu-id="9c5d1-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="9c5d1-107">StaffHub 将停止为2019年10月1日的所有用户工作。</span><span class="sxs-lookup"><span data-stu-id="9c5d1-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="9c5d1-108">任何试图打开 StaffHub 的人都将显示一条消息, 指导他们下载团队。</span><span class="sxs-lookup"><span data-stu-id="9c5d1-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="9c5d1-109">若要了解详细信息, 请参阅[Microsoft StaffHub 已停用](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="9c5d1-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="9c5d1-110">使用本文中的步骤运行报表, 获取组织中活动 StaffHub 用户的列表。</span><span class="sxs-lookup"><span data-stu-id="9c5d1-110">Use the steps in this article to run a report to get a list of active StaffHub users in your organization.</span></span> <span data-ttu-id="9c5d1-111">当你准备[将 StaffHub 团队移动到 Microsoft 团队](move-staffhub-teams-to-shifts-in-teams.md)时, 此信息可能会很方便。</span><span class="sxs-lookup"><span data-stu-id="9c5d1-111">This information may come in handy when you prepare to [move your StaffHub teams to Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span> <span data-ttu-id="9c5d1-112">在报表中, 当你将 StaffHub 切换到团队时, 你将知道你需要在通信中加入的人员。</span><span class="sxs-lookup"><span data-stu-id="9c5d1-112">From the report, you'll know who you need to include in your communications when you make the switch from StaffHub to Teams.</span></span>

<span data-ttu-id="9c5d1-113">你需要拥有 Azure AD Premium 才能执行本文中的步骤。</span><span class="sxs-lookup"><span data-stu-id="9c5d1-113">You need to have Azure AD Premium to perform the steps in this article.</span></span>

1. <span data-ttu-id="9c5d1-114">登录到 Azure 门户。</span><span class="sxs-lookup"><span data-stu-id="9c5d1-114">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="9c5d1-115">在左窗格中, 单击 " **Azure Active Directory**资源"。</span><span class="sxs-lookup"><span data-stu-id="9c5d1-115">In the left pane, click the **Azure Active Directory** resource.</span></span>
3. <span data-ttu-id="9c5d1-116">在 "**监视**" 下, 单击 "**登录**"。</span><span class="sxs-lookup"><span data-stu-id="9c5d1-116">Under **Monitoring**, click **Sign-ins**.</span></span>
4. <span data-ttu-id="9c5d1-117">在 "**应用程序**" 下, 键入**Microsoft StaffHub**。</span><span class="sxs-lookup"><span data-stu-id="9c5d1-117">Under **Application**, type **Microsoft StaffHub**.</span></span>
5. <span data-ttu-id="9c5d1-118">为报表设置所需的日期范围, 然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="9c5d1-118">Set the date range that you want for the report, and then click **Apply**.</span></span> 

    ![屏幕截图显示如何显示活动 StaffHub 用法的步骤](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a><span data-ttu-id="9c5d1-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="9c5d1-120">Related topics</span></span>

- [<span data-ttu-id="9c5d1-121">将 Microsoft StaffHub 团队移动到 Microsoft 团队中的倒班</span><span class="sxs-lookup"><span data-stu-id="9c5d1-121">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
