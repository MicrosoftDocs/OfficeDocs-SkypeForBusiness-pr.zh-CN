---
title: Skype for Business Server 中的故障列表报告
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 摘要：了解 Skype for Business Server 中的故障列表报告。
ms.openlocfilehash: 48654ee827f0d7efcb50bcccc4e1d2f3fdb5422e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816842"
---
# <a name="failure-list-report-in-skype-for-business-server"></a><span data-ttu-id="5c49f-103">Skype for Business Server 中的故障列表报告</span><span class="sxs-lookup"><span data-stu-id="5c49f-103">Failure List Report in Skype for Business Server</span></span> 
 
<span data-ttu-id="5c49f-104">**摘要：** 了解 Skype for Business Server 中的故障列表报告。</span><span class="sxs-lookup"><span data-stu-id="5c49f-104">**Summary:** Learn about the Failure List Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="5c49f-105">故障列表报告提供有关参与失败的对等会话或会议会话的单个参与者的信息。</span><span class="sxs-lookup"><span data-stu-id="5c49f-105">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session.</span></span> <span data-ttu-id="5c49f-106">此信息包括遇到问题的用户的 URI，以及与故障关联的 SIP 响应代码和诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="5c49f-106">This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>
  
## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="5c49f-107">访问故障列表报告</span><span class="sxs-lookup"><span data-stu-id="5c49f-107">Accessing the Failure List Report</span></span>

<span data-ttu-id="5c49f-108">通过单击 Skype for Business Server 中的故障分布报告上的以下任一指标可以访问故障 [列表报告](failure-distribution-report.md)：</span><span class="sxs-lookup"><span data-stu-id="5c49f-108">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Skype for Business Server](failure-distribution-report.md):</span></span>
  
- <span data-ttu-id="5c49f-109">主要诊断原因（会话）</span><span class="sxs-lookup"><span data-stu-id="5c49f-109">Top diagnostic reasons (sessions)</span></span>
    
- <span data-ttu-id="5c49f-110">主要形式（会话）</span><span class="sxs-lookup"><span data-stu-id="5c49f-110">Top modalities (sessions)</span></span>
    
- <span data-ttu-id="5c49f-111">主要池（会话）</span><span class="sxs-lookup"><span data-stu-id="5c49f-111">Top pools (sessions)</span></span>
    
- <span data-ttu-id="5c49f-112">主要来源（会话）</span><span class="sxs-lookup"><span data-stu-id="5c49f-112">Top sources (sessions)</span></span>
    
- <span data-ttu-id="5c49f-113">主要组件（会话）</span><span class="sxs-lookup"><span data-stu-id="5c49f-113">Top components (sessions)</span></span>
    
- <span data-ttu-id="5c49f-114">主要来源用户（会话）</span><span class="sxs-lookup"><span data-stu-id="5c49f-114">Top from users (sessions)</span></span>
    
- <span data-ttu-id="5c49f-115">主要目标用户（会话）</span><span class="sxs-lookup"><span data-stu-id="5c49f-115">Top to users (sessions)</span></span>
    
- <span data-ttu-id="5c49f-116">主要来源用户代理（会话）</span><span class="sxs-lookup"><span data-stu-id="5c49f-116">Top from user agents (sessions)</span></span>
    
<span data-ttu-id="5c49f-117">从故障列表报告中，可以通过单击对等会话的会话详细信息指标来访问 [Skype for Business Server](peer-to-peer-session-detail-report.md) 中的对等会话详细信息报告。</span><span class="sxs-lookup"><span data-stu-id="5c49f-117">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Skype for Business Server](peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="5c49f-118">您还可以通过单击会议的"会议"指标来访问会议详细信息报告。</span><span class="sxs-lookup"><span data-stu-id="5c49f-118">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>
  
## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="5c49f-119">充分利用故障列表报告</span><span class="sxs-lookup"><span data-stu-id="5c49f-119">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="5c49f-120">在故障列表报告中，只需将鼠标悬停在该值上即可查看每个响应代码或每个诊断 ID 的说明。</span><span class="sxs-lookup"><span data-stu-id="5c49f-120">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value.</span></span> <span data-ttu-id="5c49f-121">例如，如果你将鼠标悬停在诊断 ID 7025 上，你将在工具提示中看到以下内容：</span><span class="sxs-lookup"><span data-stu-id="5c49f-121">For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>
  
<span data-ttu-id="5c49f-122">为用户创建媒体时出现内部服务器错误。</span><span class="sxs-lookup"><span data-stu-id="5c49f-122">Internal server error creating media for user.</span></span>
  
<span data-ttu-id="5c49f-123">值得注意的是，故障列表报告不提供直接检索至少参与一个失败会话的所有用户列表的直观方法，也不提供用于确定失败会话通常涉及哪些用户的方法。</span><span class="sxs-lookup"><span data-stu-id="5c49f-123">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="5c49f-124"> (首先，故障列表报告没有筛选功能。) 但是，如果您导出数据，然后将数据转换为逗号分隔值文件，您可以使用 Windows PowerShell 查找类似这些问题的解答。</span><span class="sxs-lookup"><span data-stu-id="5c49f-124">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="5c49f-125">例如，假设将数据保存到一个 。名为 C:\Data\Failure_List.csv 的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="5c49f-125">For example, suppose you save the data to a .CSV file named C:\Data\Failure_List.csv.</span></span> <span data-ttu-id="5c49f-126">根据该文件中保存的数据，此命令将列出参与至少一个失败会话的所有用户：</span><span class="sxs-lookup"><span data-stu-id="5c49f-126">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span> 
  
```PowerShell
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

<span data-ttu-id="5c49f-127">该命令将返回类似于以下的列表：</span><span class="sxs-lookup"><span data-stu-id="5c49f-127">That command will return a list similar to this:</span></span>
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

<span data-ttu-id="5c49f-128">以下两个命令将报告每个用户参与的失败会话总数：</span><span class="sxs-lookup"><span data-stu-id="5c49f-128">These two commands report back the total number of failed sessions that each user was involved in:</span></span>
  
```PowerShell
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

<span data-ttu-id="5c49f-129">这将返回与以下内容类似的数据：</span><span class="sxs-lookup"><span data-stu-id="5c49f-129">That will return data similar to this:</span></span>
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a><span data-ttu-id="5c49f-130">筛选器</span><span class="sxs-lookup"><span data-stu-id="5c49f-130">Filters</span></span>

<span data-ttu-id="5c49f-131">无。</span><span class="sxs-lookup"><span data-stu-id="5c49f-131">None.</span></span> <span data-ttu-id="5c49f-132">无法筛选故障列表报告。</span><span class="sxs-lookup"><span data-stu-id="5c49f-132">You cannot filter the Failure List Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="5c49f-133">指标</span><span class="sxs-lookup"><span data-stu-id="5c49f-133">Metrics</span></span>

<span data-ttu-id="5c49f-134">下表列出了每个失败呼叫的故障列表报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="5c49f-134">The following table lists the information provided in the Failure List Report for each failed call.</span></span>
  
<span data-ttu-id="5c49f-135">**故障列表报告指标**</span><span class="sxs-lookup"><span data-stu-id="5c49f-135">**Failure List Report Metrics**</span></span>

|<span data-ttu-id="5c49f-136">**名称**</span><span class="sxs-lookup"><span data-stu-id="5c49f-136">**Name**</span></span>|<span data-ttu-id="5c49f-137">**是否可按此项排序？**</span><span class="sxs-lookup"><span data-stu-id="5c49f-137">**Can you sort on this item?**</span></span>|<span data-ttu-id="5c49f-138">**说明**</span><span class="sxs-lookup"><span data-stu-id="5c49f-138">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5c49f-139">**报告的时间**</span><span class="sxs-lookup"><span data-stu-id="5c49f-139">**Reported time**</span></span> <br/> |<span data-ttu-id="5c49f-140">否</span><span class="sxs-lookup"><span data-stu-id="5c49f-140">No</span></span>  <br/> |<span data-ttu-id="5c49f-141">记录报告的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="5c49f-141">Date and time the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="5c49f-142">**请求**</span><span class="sxs-lookup"><span data-stu-id="5c49f-142">**Request**</span></span> <br/> |<span data-ttu-id="5c49f-143">否</span><span class="sxs-lookup"><span data-stu-id="5c49f-143">No</span></span>  <br/> |<span data-ttu-id="5c49f-144">失败的 SIP 请求类型。</span><span class="sxs-lookup"><span data-stu-id="5c49f-144">SIP request type that failed.</span></span> <span data-ttu-id="5c49f-145">例如 INVITE 或 BYE。</span><span class="sxs-lookup"><span data-stu-id="5c49f-145">For example, INVITE or BYE.</span></span>  <br/> |
|<span data-ttu-id="5c49f-146">**响应代码**</span><span class="sxs-lookup"><span data-stu-id="5c49f-146">**Response code**</span></span> <br/> |<span data-ttu-id="5c49f-147">否</span><span class="sxs-lookup"><span data-stu-id="5c49f-147">No</span></span>  <br/> |<span data-ttu-id="5c49f-148">会议失败时发送的 SIP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="5c49f-148">SIP response code sent when the conference failed.</span></span>  <br/> |
|<span data-ttu-id="5c49f-149">**诊断 ID**</span><span class="sxs-lookup"><span data-stu-id="5c49f-149">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="5c49f-150">否</span><span class="sxs-lookup"><span data-stu-id="5c49f-150">No</span></span>  <br/> |<span data-ttu-id="5c49f-151">附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。</span><span class="sxs-lookup"><span data-stu-id="5c49f-151">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="5c49f-152">**加入成本时间 (毫秒)**</span><span class="sxs-lookup"><span data-stu-id="5c49f-152">**Join cost time (ms)**</span></span> <br/> |<span data-ttu-id="5c49f-153">否</span><span class="sxs-lookup"><span data-stu-id="5c49f-153">No</span></span>  <br/> |<span data-ttu-id="5c49f-154">用户 (会议) 所需时间（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="5c49f-154">Amount of time (in milliseconds) required for the user to join the conference.</span></span>  <br/> |
|<span data-ttu-id="5c49f-155">**来源用户**</span><span class="sxs-lookup"><span data-stu-id="5c49f-155">**From user**</span></span> <br/> |<span data-ttu-id="5c49f-156">否</span><span class="sxs-lookup"><span data-stu-id="5c49f-156">No</span></span>  <br/> |<span data-ttu-id="5c49f-157">发起呼叫的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="5c49f-157">SIP address of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="5c49f-158">**源用户代理**</span><span class="sxs-lookup"><span data-stu-id="5c49f-158">**From user agent**</span></span> <br/> |<span data-ttu-id="5c49f-159">否</span><span class="sxs-lookup"><span data-stu-id="5c49f-159">No</span></span>  <br/> |<span data-ttu-id="5c49f-160">发起呼叫的用户的终结点使用的软件。</span><span class="sxs-lookup"><span data-stu-id="5c49f-160">Software used by the endpoint of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="5c49f-161">**目标用户**</span><span class="sxs-lookup"><span data-stu-id="5c49f-161">**To user**</span></span> <br/> |<span data-ttu-id="5c49f-162">否</span><span class="sxs-lookup"><span data-stu-id="5c49f-162">No</span></span>  <br/> |<span data-ttu-id="5c49f-163">被叫用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="5c49f-163">SIP address of the user who was being called.</span></span>  <br/> |
   

