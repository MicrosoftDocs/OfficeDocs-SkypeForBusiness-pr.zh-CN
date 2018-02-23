---
title: "在 Microsoft Teams 中搜索事件的审核日志"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 01/22/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: "了解如何从 Office 365 审核日志检索 Microsoft Teams 数据。"
appliesto:
- Microsoft Teams
ms.openlocfilehash: c1980bb84138570d9e9a221d7ccdc0b8fc62d203
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2018
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="0ca7c-103">在 Microsoft Teams 中搜索事件的审核日志</span><span class="sxs-lookup"><span data-stu-id="0ca7c-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================

<span data-ttu-id="0ca7c-104">审核日志可帮助你调查 Office 365 服务中的特定活动。</span><span class="sxs-lookup"><span data-stu-id="0ca7c-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="0ca7c-105">对于 Teams，审核的部分活动包括：</span><span class="sxs-lookup"><span data-stu-id="0ca7c-105">For Teams, here are some of the activities that are audited:</span></span>

-   <span data-ttu-id="0ca7c-106">团队创建</span><span class="sxs-lookup"><span data-stu-id="0ca7c-106">Team creation</span></span>

-   <span data-ttu-id="0ca7c-107">团队删除</span><span class="sxs-lookup"><span data-stu-id="0ca7c-107">Team deletion</span></span>

-   <span data-ttu-id="0ca7c-108">添加频道</span><span class="sxs-lookup"><span data-stu-id="0ca7c-108">Added channel</span></span>

-   <span data-ttu-id="0ca7c-109">更改设置</span><span class="sxs-lookup"><span data-stu-id="0ca7c-109">Changed setting</span></span>

<span data-ttu-id="0ca7c-110">要查看 Office 365 中审核的活动的完整列表，请阅读[在 Office 365 安全与合规中心搜索审核日志](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c?=&PickTab=Activities&ad=US#PickTab=Activities)。</span><span class="sxs-lookup"><span data-stu-id="0ca7c-110">To see the complete list of activities that are audited in Office 365, read [Search the audit log in the Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c?=&PickTab=Activities&ad=US#PickTab=Activities).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="0ca7c-111">在 Teams 中启用审核</span><span class="sxs-lookup"><span data-stu-id="0ca7c-111">Turn on auditing in Teams</span></span>

<span data-ttu-id="0ca7c-112">在查看审核数据之前，你必须首先在**安全与合规中心** (https://protection.office.com) 启用审核。</span><span class="sxs-lookup"><span data-stu-id="0ca7c-112">Before you can look at audit data, you have to first turn on auditing in the **Security & Compliance Center**(https://protection.office.com).</span></span> <span data-ttu-id="0ca7c-113">有关启用审核的帮助，请阅读[启用或关闭 Office 365 审核日志搜索](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)。</span><span class="sxs-lookup"><span data-stu-id="0ca7c-113">For help turning on auditing, read [Turn Office 365 audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="0ca7c-114">只有在启用审核后才能获取审核数据。</span><span class="sxs-lookup"><span data-stu-id="0ca7c-114">Audit data is only available from the point at which you turned on Auditing.</span></span>



## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="0ca7c-115">从审核日志检索 Teams 数据</span><span class="sxs-lookup"><span data-stu-id="0ca7c-115">Retrieve Teams data from the audit log</span></span>

1.  <span data-ttu-id="0ca7c-116">要检索审核日志，请转到[安全与合规中心](https://go.microsoft.com/fwlink/?linkid=855775)。</span><span class="sxs-lookup"><span data-stu-id="0ca7c-116">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="0ca7c-117">在“**搜索和调查**”下，选择“**审核日志搜索**”。![安全与合规中心的“审核日志搜索”页面屏幕截图。](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)</span><span class="sxs-lookup"><span data-stu-id="0ca7c-117">Under **Search & Investigation**, select **Audit log search**.![Screenshot of the Audit log search page of the Security & Compliance Center.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)</span></span>



2.  <span data-ttu-id="0ca7c-118">使用“**搜索**”按活动、日期和你要审核的用户进行筛选。</span><span class="sxs-lookup"><span data-stu-id="0ca7c-118">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>

3.  <span data-ttu-id="0ca7c-119">将结果导出到 Excel 以供进一步分析。</span><span class="sxs-lookup"><span data-stu-id="0ca7c-119">Export your results to Excel for further analysis.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="0ca7c-120">审核数据仅在审核启用后在审核日志中显示。</span><span class="sxs-lookup"><span data-stu-id="0ca7c-120">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="0ca7c-121">视频：技术提示：在 Teams 中使用审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="0ca7c-121">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="0ca7c-122">加入 Teams 计划经理 Ansuman Acharya，他将说明如何在 Office 365 安全与合规中心执行 Teams 审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="0ca7c-122">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span> 


> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]






