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
description: 了解如何从 Office 365 审核日志检索 Microsoft Teams 数据。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3c1f82a7688e3fdde7be85004c717293cc5777fa
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826270"
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="f6c92-103">在 Microsoft Teams 中搜索事件的审核日志</span><span class="sxs-lookup"><span data-stu-id="f6c92-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="f6c92-104">审核日志可帮助你调查 Office 365 服务中的特定活动。</span><span class="sxs-lookup"><span data-stu-id="f6c92-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="f6c92-105">对于 Teams，审核的部分活动包括：</span><span class="sxs-lookup"><span data-stu-id="f6c92-105">For Teams, here are some of the activities that are audited:</span></span>

- <span data-ttu-id="f6c92-106">团队创建</span><span class="sxs-lookup"><span data-stu-id="f6c92-106">Team creation</span></span>

- <span data-ttu-id="f6c92-107">团队删除</span><span class="sxs-lookup"><span data-stu-id="f6c92-107">Team deletion</span></span>

- <span data-ttu-id="f6c92-108">添加频道</span><span class="sxs-lookup"><span data-stu-id="f6c92-108">Added channel</span></span>

- <span data-ttu-id="f6c92-109">更改设置</span><span class="sxs-lookup"><span data-stu-id="f6c92-109">Changed setting</span></span>

> [!NOTE]
> <span data-ttu-id="f6c92-110">来自专用频道的审核事件也会被记录为团队和标准频道。</span><span class="sxs-lookup"><span data-stu-id="f6c92-110">Audit events from private channels are also logged as they are for teams and standard channels.</span></span>

<span data-ttu-id="f6c92-111">要查看 Office 365 中审核的活动的完整列表，请阅读[在 Office 365 安全与合规中心搜索审核日志](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c)。</span><span class="sxs-lookup"><span data-stu-id="f6c92-111">To see the complete list of activities that are audited in Office 365, read [Search the audit log in the Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="f6c92-112">在 Teams 中启用审核</span><span class="sxs-lookup"><span data-stu-id="f6c92-112">Turn on auditing in Teams</span></span>

<span data-ttu-id="f6c92-113">在你可以查看审核数据之前，你必须先在[安全 & 合规中心](https://protection.office.com)中启用审核。</span><span class="sxs-lookup"><span data-stu-id="f6c92-113">Before you can look at audit data, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="f6c92-114">有关启用审核的帮助，请阅读[启用或关闭 Office 365 审核日志搜索](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)。</span><span class="sxs-lookup"><span data-stu-id="f6c92-114">For help turning on auditing, read [Turn Office 365 audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6c92-115">只有在启用审核后才能获取审核数据。</span><span class="sxs-lookup"><span data-stu-id="f6c92-115">Audit data is only available from the point at which you turned on Auditing.</span></span>

## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="f6c92-116">从审核日志检索 Teams 数据</span><span class="sxs-lookup"><span data-stu-id="f6c92-116">Retrieve Teams data from the audit log</span></span>


1.  <span data-ttu-id="f6c92-117">要检索审核日志，请转到[安全与合规中心](https://go.microsoft.com/fwlink/?linkid=855775)。</span><span class="sxs-lookup"><span data-stu-id="f6c92-117">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="f6c92-118">在 "**搜索**" 下，选择 "**审核日志搜索**"。</span><span class="sxs-lookup"><span data-stu-id="f6c92-118">Under **Search**, select **Audit log search**.</span></span>



2. <span data-ttu-id="f6c92-119">使用“**搜索**”按活动、日期和你要审核的用户进行筛选。</span><span class="sxs-lookup"><span data-stu-id="f6c92-119">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>

3. <span data-ttu-id="f6c92-120">将结果导出到 Excel 以供进一步分析。</span><span class="sxs-lookup"><span data-stu-id="f6c92-120">Export your results to Excel for further analysis.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6c92-121">审核数据仅在审核启用后在审核日志中显示。</span><span class="sxs-lookup"><span data-stu-id="f6c92-121">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="f6c92-122">视频：技术提示：在 Teams 中使用审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="f6c92-122">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="f6c92-123">加入 Teams 计划经理 Ansuman Acharya，他将说明如何在 Office 365 安全与合规中心执行 Teams 审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="f6c92-123">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span> 

> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]
