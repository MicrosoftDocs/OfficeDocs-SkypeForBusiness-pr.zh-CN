---
title: 在 Microsoft Teams 中搜索事件的审核日志
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.reviewer: anach
search.appverid: MET150
description: 了解如何从审核日志中检索 Microsoft 团队数据。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b1235dcd1a33800185eb005f5e309204790c5b1
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778888"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="500c5-103">在 Microsoft Teams 中搜索事件的审核日志</span><span class="sxs-lookup"><span data-stu-id="500c5-103">Search the audit log for events in Microsoft Teams</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="500c5-104">审核日志可帮助你调查 Office 365 服务中的特定活动。</span><span class="sxs-lookup"><span data-stu-id="500c5-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="500c5-105">对于 Teams，审核的部分活动包括：</span><span class="sxs-lookup"><span data-stu-id="500c5-105">For Teams, here are some of the activities that are audited:</span></span>

- <span data-ttu-id="500c5-106">团队创建</span><span class="sxs-lookup"><span data-stu-id="500c5-106">Team creation</span></span>

- <span data-ttu-id="500c5-107">团队删除</span><span class="sxs-lookup"><span data-stu-id="500c5-107">Team deletion</span></span>

- <span data-ttu-id="500c5-108">添加频道</span><span class="sxs-lookup"><span data-stu-id="500c5-108">Added channel</span></span>

- <span data-ttu-id="500c5-109">更改设置</span><span class="sxs-lookup"><span data-stu-id="500c5-109">Changed setting</span></span>

> [!NOTE]
> <span data-ttu-id="500c5-110">来自专用频道的审核事件也会被记录为团队和标准频道。</span><span class="sxs-lookup"><span data-stu-id="500c5-110">Audit events from private channels are also logged as they are for teams and standard channels.</span></span>

<span data-ttu-id="500c5-111">若要查看在 Microsoft 365 中审核的活动的完整列表，请参阅[在 microsoft 365 合规性中心中搜索审核日志](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c)。</span><span class="sxs-lookup"><span data-stu-id="500c5-111">To see the complete list of activities that are audited in Microsoft 365, read [Search the audit log in the Microsoft 365 Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="500c5-112">在 Teams 中启用审核</span><span class="sxs-lookup"><span data-stu-id="500c5-112">Turn on auditing in Teams</span></span>

<span data-ttu-id="500c5-113">在你可以查看审核数据之前，你必须先在[安全 & 合规中心](https://protection.office.com)中启用审核。</span><span class="sxs-lookup"><span data-stu-id="500c5-113">Before you can look at audit data, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="500c5-114">有关启用审核的帮助，请参阅[打开或关闭审核日志搜索](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)。</span><span class="sxs-lookup"><span data-stu-id="500c5-114">For help turning on auditing, read [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="500c5-115">只有在启用审核后才能获取审核数据。</span><span class="sxs-lookup"><span data-stu-id="500c5-115">Audit data is only available from the point at which you turned on Auditing.</span></span>

## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="500c5-116">从审核日志检索 Teams 数据</span><span class="sxs-lookup"><span data-stu-id="500c5-116">Retrieve Teams data from the audit log</span></span>

1. <span data-ttu-id="500c5-117">要检索审核日志，请转到[安全与合规中心](https://go.microsoft.com/fwlink/?linkid=855775)。</span><span class="sxs-lookup"><span data-stu-id="500c5-117">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="500c5-118">在 "**搜索**" 下，选择 "**审核日志搜索**"。</span><span class="sxs-lookup"><span data-stu-id="500c5-118">Under **Search**, select **Audit log search**.</span></span>
1. <span data-ttu-id="500c5-119">使用“**搜索**”按活动、日期和你要审核的用户进行筛选。</span><span class="sxs-lookup"><span data-stu-id="500c5-119">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>
1. <span data-ttu-id="500c5-120">将结果导出到 Excel 以供进一步分析。</span><span class="sxs-lookup"><span data-stu-id="500c5-120">Export your results to Excel for further analysis.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="500c5-121">审核数据仅在审核启用后在审核日志中显示。</span><span class="sxs-lookup"><span data-stu-id="500c5-121">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="external-user-scenario"></a><span data-ttu-id="500c5-122">外部用户方案</span><span class="sxs-lookup"><span data-stu-id="500c5-122">External user scenario</span></span>

<span data-ttu-id="500c5-123">从业务角度看，您可能想要关注的一种方案是向团队环境添加外部用户。</span><span class="sxs-lookup"><span data-stu-id="500c5-123">One scenario you might want to keep an eye on, from a business perspective, is the addition of external users to your Teams environment.</span></span> <span data-ttu-id="500c5-124">如果启用外部用户，则监视其状态是一个好主意。</span><span class="sxs-lookup"><span data-stu-id="500c5-124">If external users are enabled, then monitoring their presence is a good idea.</span></span>

![通过批量删除触发的事件列表的屏幕截图](media/TeamsExternalUserAddPolicy.png)

<span data-ttu-id="500c5-126">通过此策略的屏幕截图，你可以命名策略，根据你的业务需求设置严重性，将其设置为（在本例中为 "单个活动"），然后建立仅用于专门监视非内部用户添加的参数，并将此活动限制为 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="500c5-126">The screenshot of this policy to monitor external user adds allows you to name the policy, set the severity according to your business needs, set it as (in this case) a single activity, and then establish the parameters that will specifically monitor only the addition of non-internal users, and limit this activity to Microsoft Teams.</span></span>

<span data-ttu-id="500c5-127">然后，将能够在活动日志中查看此策略的结果：</span><span class="sxs-lookup"><span data-stu-id="500c5-127">Then results from this policy will be able to be viewed in the activity log:</span></span>

![通过批量删除触发的事件列表的屏幕截图](media/TeamsExternalUserList.png)

<span data-ttu-id="500c5-129">在此处，你可以查看与你已设置的策略的匹配项，并根据需要进行任何调整，或将结果导出为在其他位置使用。</span><span class="sxs-lookup"><span data-stu-id="500c5-129">Here you can review matches to the policy you've set, and make any adjustments as needed, or export the results to use elsewhere.</span></span>

## <a name="mass-delete-scenario"></a><span data-ttu-id="500c5-130">批量删除方案</span><span class="sxs-lookup"><span data-stu-id="500c5-130">Mass delete scenario</span></span>

<span data-ttu-id="500c5-131">如上文所述，您可以监控删除方案。</span><span class="sxs-lookup"><span data-stu-id="500c5-131">As mentioned above, you can monitor deletion scenarios.</span></span> <span data-ttu-id="500c5-132">可以创建一个策略来监视团队网站的大量删除：</span><span class="sxs-lookup"><span data-stu-id="500c5-132">It's possible to create a policy that would monitor mass deletion of Teams sites:</span></span>

![策略创建页面的屏幕截图，显示用于批量工作组删除检测的策略设置](media/TeamsMassDeletePolicy.png)

<span data-ttu-id="500c5-134">如屏幕截图所示，你可以为此策略设置许多不同的参数以监视团队删除，包括严重性、单个或重复操作，以及将此限制为团队和网站删除的参数。</span><span class="sxs-lookup"><span data-stu-id="500c5-134">As the screenshot shows, you can set many different parameters for this policy to monitor Teams deletions, including severity, single or repeated action, and parameters limiting this to Teams and site deletion.</span></span> <span data-ttu-id="500c5-135">这可以独立于模板执行，也可以根据组织的需要，创建基于此策略创建的模板。</span><span class="sxs-lookup"><span data-stu-id="500c5-135">This can be done independently of a template, or you may have a template created to base this policy off, depending on your organizational needs.</span></span>

<span data-ttu-id="500c5-136">建立适用于您的企业的策略后，您可以在触发事件时查看活动日志中的结果：</span><span class="sxs-lookup"><span data-stu-id="500c5-136">Once you've established a policy that will work for your business, you can then review the results in the activity log as events are triggered:</span></span>

![通过批量删除触发的事件列表的屏幕截图](media/TeamsMassDeleteList.png)

<span data-ttu-id="500c5-138">您可以筛选到已设置的策略，以查看该策略的结果。</span><span class="sxs-lookup"><span data-stu-id="500c5-138">You can filter down to the policy you've set to see the results of that policy.</span></span> <span data-ttu-id="500c5-139">如果你在活动日志中获得的结果不满意（也许你看到了大量结果，或者根本看不到任何结果），这可能会帮助你微调查询以使其更与你需要的内容相关。</span><span class="sxs-lookup"><span data-stu-id="500c5-139">If the results you're getting in the activity log are not satisfactory (maybe you're seeing a lot of results, or nothing at all), this may help you to fine-tune the query to make it more relevant to what you need it to do.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="500c5-140">视频：技术提示：在 Teams 中使用审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="500c5-140">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="500c5-141">加入 Teams 计划经理 Ansuman Acharya，他将说明如何在 Office 365 安全与合规中心执行 Teams 审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="500c5-141">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span>

> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]
