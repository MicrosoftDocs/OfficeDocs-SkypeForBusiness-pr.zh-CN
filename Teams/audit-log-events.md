---
title: "在 Microsoft Teams 中搜索事件的审核日志 | Microsoft 支持"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "了解如何从审核日志检索 Microsoft Teams 数据。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 558db88d32229fcaef70ea5278d7437fbea92198
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2017
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="18b59-103">在 Microsoft Teams 中搜索事件的审核日志</span><span class="sxs-lookup"><span data-stu-id="18b59-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================

<span data-ttu-id="18b59-104">通过审核日志可以对 Office 365 服务中的重大事件进行特定搜索。</span><span class="sxs-lookup"><span data-stu-id="18b59-104">The Audit Log provides ad-hoc search capabilities into notable events across Office 365 services.</span></span> <span data-ttu-id="18b59-105">就 Microsoft Teams 具体而言，下面是一些捕获的事件示例：</span><span class="sxs-lookup"><span data-stu-id="18b59-105">For Microsoft Teams specifically, below are a few examples of events captured:</span></span>

-   <span data-ttu-id="18b59-106">团队创建</span><span class="sxs-lookup"><span data-stu-id="18b59-106">Team Creation</span></span>

-   <span data-ttu-id="18b59-107">团队删除</span><span class="sxs-lookup"><span data-stu-id="18b59-107">Team Deletion</span></span>

-   <span data-ttu-id="18b59-108">添加了频道</span><span class="sxs-lookup"><span data-stu-id="18b59-108">Added Channel</span></span>

-   <span data-ttu-id="18b59-109">更改了设置</span><span class="sxs-lookup"><span data-stu-id="18b59-109">Changed Setting</span></span>

<span data-ttu-id="18b59-110">Office 365 中的完整事件列表相当广泛，请参阅[此处](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities)。</span><span class="sxs-lookup"><span data-stu-id="18b59-110">The complete event list across Office 365 is quite extensive and can be found [here](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities).</span></span>

<span data-ttu-id="18b59-111">必须先启用审核，你才可以深入探索审核。</span><span class="sxs-lookup"><span data-stu-id="18b59-111">Before you can dig into audit insights, auditing must first be enabled.</span></span> <span data-ttu-id="18b59-112">要启用审核，请导航到*安全性和合规性*管理中心。</span><span class="sxs-lookup"><span data-stu-id="18b59-112">To enable Auditing, navigate to the *Security & Compliance* Admin Center.</span></span> <span data-ttu-id="18b59-113">在*“搜索活动”*下方，单击**“立即开始录制”**。</span><span class="sxs-lookup"><span data-stu-id="18b59-113">Under *Search for activity*, click on **Start recording now**.</span></span> <span data-ttu-id="18b59-114">24 小时后，可以通过位于*“搜索和调查”*选项卡下方的*“审核日志搜索”*获取审核数据。</span><span class="sxs-lookup"><span data-stu-id="18b59-114">After 24hrs, audit data will be available via *Audit Log Search* located under the *Search & Investigation* tab.</span></span>


| |  |
|---------|---------|
|![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image1.png)<br></br><span data-ttu-id="18b59-115">重要提示</span><span class="sxs-lookup"><span data-stu-id="18b59-115">Important:</span></span>     |<span data-ttu-id="18b59-116">只能在启用了审核的点获取审核数据。</span><span class="sxs-lookup"><span data-stu-id="18b59-116">Audit data is only available from the point at which Auditing was enabled.</span></span>         |

![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image2.png)

<span data-ttu-id="18b59-117">现在，我们来看看如何从审核日志检索 Microsoft Teams 数据：</span><span class="sxs-lookup"><span data-stu-id="18b59-117">Now, let’s look at how to retrieve Microsoft Teams data from the Audit Log:</span></span>

1.  <span data-ttu-id="18b59-118">要检索审核日志信息，请导航到[安全性和合规性管理中心](https://go.microsoft.com/fwlink/?linkid=855775)。</span><span class="sxs-lookup"><span data-stu-id="18b59-118">To retrieve Audit Log information, navigate to the [Security & Compliance Admin Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="18b59-119">在*“搜索和调查”*下方，选择**“审核日志搜索”**。</span><span class="sxs-lookup"><span data-stu-id="18b59-119">Under *Search & Investigation*, select **Audit log search.**</span></span>

    <span data-ttu-id="18b59-120">a.</span><span class="sxs-lookup"><span data-stu-id="18b59-120">A</span></span>  <span data-ttu-id="18b59-121">Microsoft Teams 已定义可以选择的审核活动，如下所示。</span><span class="sxs-lookup"><span data-stu-id="18b59-121">Microsoft Teams has defined audit activities that can be selected as shown below.</span></span>

![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)

2.  <span data-ttu-id="18b59-122">选择感兴趣的活动后，提供要基于其检索 Microsoft Teams 信息的日期范围和用户。</span><span class="sxs-lookup"><span data-stu-id="18b59-122">After selecting the activities of interest, supply a date range and users to retrieve Microsoft Teams information from.</span></span> <span data-ttu-id="18b59-123">单击**“搜索”**检索结果。</span><span class="sxs-lookup"><span data-stu-id="18b59-123">Click **Search** to retrieve the results.</span></span>

3.  <span data-ttu-id="18b59-124">此信息可以导出到 Excel，并可以根据需要筛选。</span><span class="sxs-lookup"><span data-stu-id="18b59-124">This information can be exported to Excel and filtered as needed.</span></span>


|  | |
|---------|---------|
|![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image1.png)<br></br><span data-ttu-id="18b59-125">重要提示</span><span class="sxs-lookup"><span data-stu-id="18b59-125">Important:</span></span> |<span data-ttu-id="18b59-126">如果以前未启用审核，则需要将其启用，数据才会显示在审核日志中。</span><span class="sxs-lookup"><span data-stu-id="18b59-126">If auditing has not been enabled previously, that needs to be enabled before data will appear in the Audit Log.</span></span>         |
