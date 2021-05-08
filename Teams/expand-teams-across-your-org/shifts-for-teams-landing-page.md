---
title: Teams 中的排班
description: 获取设置和管理日程安排管理工具 Shifts 所需的管理员指导，Teams。
ms.topic: conceptual
author: cichur
ms.author: v-cichur
audience: admin
manager: serdars
f1.keywords:
- NOCSH
ms.date: 03/29/2019
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 889c3f4149489f6bcea44acde93d897a7f2e50e1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092550"
---
# <a name="shifts-for-teams"></a><span data-ttu-id="d85ab-103">Teams 中的排班</span><span class="sxs-lookup"><span data-stu-id="d85ab-103">Shifts for Teams</span></span>

<span data-ttu-id="d85ab-104">Teams为组织中一线员工提供有效通信和协作所需的工具。</span><span class="sxs-lookup"><span data-stu-id="d85ab-104">Teams gives Frontline Workers in your organization the tools they need to communicate and collaborate effectively.</span></span> <span data-ttu-id="d85ab-105">本文演示如何设置和管理。</span><span class="sxs-lookup"><span data-stu-id="d85ab-105">This article shows you how to set up and manage.</span></span> <span data-ttu-id="d85ab-106">排班并使用日程安排Teams。</span><span class="sxs-lookup"><span data-stu-id="d85ab-106">Shifts and use the schedule management tool in Teams.</span></span>

### <a name="set-up-and-manage-shifts-for-your-organization"></a><span data-ttu-id="d85ab-107">为组织设置和管理班次</span><span class="sxs-lookup"><span data-stu-id="d85ab-107">Set up and manage Shifts for your organization</span></span>

|               |               |               |               |
| ------------- | ------------- | ------------- | ------------- |
|![task-checklist-planning-teams](../media/task-checklist-planning-teams-small.svg) | <span data-ttu-id="d85ab-109">**[管理组织中班次](./shifts/manage-the-shifts-app-for-your-organization-in-teams.md)**</span><span class="sxs-lookup"><span data-stu-id="d85ab-109">**[Manage Shifts in your organization](./shifts/manage-the-shifts-app-for-your-organization-in-teams.md)**</span></span> |![设计](../media/Help-small.svg)  | <span data-ttu-id="d85ab-111">**[一线员工相关的班次帮助](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Specific_apps)**</span><span class="sxs-lookup"><span data-stu-id="d85ab-111">**[Shifts Help for Frontline Workers](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Specific_apps)**</span></span> |

### <a name="shifts-extensions"></a><span data-ttu-id="d85ab-112">班次扩展</span><span class="sxs-lookup"><span data-stu-id="d85ab-112">Shifts extensions</span></span>

|               |               |
| ------------- | ------------- |
| ![api](../media/api-small.svg) | <span data-ttu-id="d85ab-114">**[Shift Graph API](/graph/api/resources/shift?view=graph-rest-1.0)** 使用 Graph API，可以将 Shifts 数据与外部员工管理系统集成。</span><span class="sxs-lookup"><span data-stu-id="d85ab-114">**[Shift Graph APIs](/graph/api/resources/shift?view=graph-rest-1.0)** Shifts Graph APIs allow you to integrate Shifts data with external workforce management systems.</span></span> <span data-ttu-id="d85ab-115">你可以灵活地在后端生成自定义 Shifts 体验，同时为用户提供丰富的前端体验Teams。</span><span class="sxs-lookup"><span data-stu-id="d85ab-115">You'll have the flexibility to build custom Shifts experiences in the back end, while giving users a rich, front-end experience in Teams.</span></span>             |
| ![api](../media/api-small.svg) | <span data-ttu-id="d85ab-117">**[员工管理集成](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)** 如果使用第三方员工管理系统（如 Kronos 和 JDA）进行日程安排、时间和出席，则可以通过 Shifts Graph API 和 SDK 与开源集成直接集成 Shifts。</span><span class="sxs-lookup"><span data-stu-id="d85ab-117">**[Workforce management integrations](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)** If you're using third-party workforce management systems, such as Kronos and JDA, for scheduling, time, and attendance, you can integrate directly with Shifts through Shifts Graph APIs and SDK with open source integrations.</span></span> |
| ![api](../media/process-flow-teams-small.svg) | <span data-ttu-id="d85ab-119">**[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shifts + Power Automate可让你从 Shifts 获取信息，并与其他应用一起创建自定义工作流，并大规模执行操作。</span><span class="sxs-lookup"><span data-stu-id="d85ab-119">**[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shifts + Power Automate lets you take info from Shifts and create custom workflows with other apps and perform operations at scale.</span></span> <span data-ttu-id="d85ab-120">使用很少的代码或无代码自动执行关键过程。</span><span class="sxs-lookup"><span data-stu-id="d85ab-120">Automate key processes with little to no code.</span></span> <span data-ttu-id="d85ab-121">触发器和模板支持多种方案，例如，在不需要经理批准时为轮班请求启用自动审批。</span><span class="sxs-lookup"><span data-stu-id="d85ab-121">The triggers and templates support a variety of scenarios such as enabling auto-approvals for shift requests when a manager’s approval isn't needed.</span></span> |

## <a name="featured-training"></a><span data-ttu-id="d85ab-122">特色培训</span><span class="sxs-lookup"><span data-stu-id="d85ab-122">Featured training</span></span>

|               |               |               |               |               |               |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| ![arrow-right-2-teams](../media/arrow-right-2-teams-small.svg)  |  [<span data-ttu-id="d85ab-124">视频：什么是 Shifts？</span><span class="sxs-lookup"><span data-stu-id="d85ab-124">Video: What is Shifts?</span></span>](https://support.office.com/article/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) |![clock-teams](../media/clock-teams-small.svg)  |  [<span data-ttu-id="d85ab-126">视频：什么是 Shifts？</span><span class="sxs-lookup"><span data-stu-id="d85ab-126">Video: What is Shifts?</span></span>](https://support.office.com/article/create-a-shifts-schedule-2b94ca38-36db-4a1c-8fee-f8f0fec9a984) |![blocks-teams](../media/blocks-teams-small.svg)  |  [<span data-ttu-id="d85ab-128">视频：管理排班计划</span><span class="sxs-lookup"><span data-stu-id="d85ab-128">Video: Manage a Shifts schedule</span></span>](https://support.office.com/article/manage-a-shifts-schedule-63acda7b-ea39-441a-b1c6-c404a72e79f7) |