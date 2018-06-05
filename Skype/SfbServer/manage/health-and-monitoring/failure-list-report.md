---
title: Skype for Business Server 2015 中的故障列表报告
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 摘要： 了解有关的故障列表报告中 Skype 业务服务器 2015年。
ms.openlocfilehash: 7cb146569958908e79700e725d473bc246295c9d
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569318"
---
# <a name="failure-list-report-in-skype-for-business-server-2015"></a><span data-ttu-id="a21f6-103">Skype for Business Server 2015 中的故障列表报告</span><span class="sxs-lookup"><span data-stu-id="a21f6-103">Failure List Report in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a21f6-104">**摘要：** 了解有关的故障列表报告中 Skype 业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="a21f6-104">**Summary:** Learn about the Failure List Report in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="a21f6-p101">故障列表报告提供有关参加失败的对等会话或会议会话的各个参与者的信息。此信息包括遇到问题的用户的 URI，以及与故障相关联的 SIP 响应代码和诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="a21f6-p101">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session. This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>
  
## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="a21f6-107">访问故障列表报告</span><span class="sxs-lookup"><span data-stu-id="a21f6-107">Accessing the Failure List Report</span></span>

<span data-ttu-id="a21f6-108">通过单击以下指标[故障分布报告中的业务服务器 2015 Skype](failure-distribution-report.md)上任一方式访问故障列表报告：</span><span class="sxs-lookup"><span data-stu-id="a21f6-108">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Skype for Business Server 2015](failure-distribution-report.md):</span></span>
  
- <span data-ttu-id="a21f6-109">主要诊断原因（会话）</span><span class="sxs-lookup"><span data-stu-id="a21f6-109">Top diagnostic reasons (sessions)</span></span>
    
- <span data-ttu-id="a21f6-110">主要形式（会话）</span><span class="sxs-lookup"><span data-stu-id="a21f6-110">Top modalities (sessions)</span></span>
    
- <span data-ttu-id="a21f6-111">主要池（会话）</span><span class="sxs-lookup"><span data-stu-id="a21f6-111">Top pools (sessions)</span></span>
    
- <span data-ttu-id="a21f6-112">主要来源（会话）</span><span class="sxs-lookup"><span data-stu-id="a21f6-112">Top sources (sessions)</span></span>
    
- <span data-ttu-id="a21f6-113">主要组件（会话）</span><span class="sxs-lookup"><span data-stu-id="a21f6-113">Top components (sessions)</span></span>
    
- <span data-ttu-id="a21f6-114">主要来源用户（会话）</span><span class="sxs-lookup"><span data-stu-id="a21f6-114">Top from users (sessions)</span></span>
    
- <span data-ttu-id="a21f6-115">主要目标用户（会话）</span><span class="sxs-lookup"><span data-stu-id="a21f6-115">Top to users (sessions)</span></span>
    
- <span data-ttu-id="a21f6-116">主要来源用户代理（会话）</span><span class="sxs-lookup"><span data-stu-id="a21f6-116">Top from user agents (sessions)</span></span>
    
<span data-ttu-id="a21f6-117">从故障列表报告可以通过单击对等会话的会话详细信息指标来访问[对等会话中的业务服务器 2015 Skype 的详细信息报告](peer-to-peer-session-detail-report.md)。</span><span class="sxs-lookup"><span data-stu-id="a21f6-117">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Skype for Business Server 2015](peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="a21f6-118">也可以单击会议的”会议“指标，以访问会议详细信息报告。</span><span class="sxs-lookup"><span data-stu-id="a21f6-118">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>
  
## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="a21f6-119">充分利用故障列表报告</span><span class="sxs-lookup"><span data-stu-id="a21f6-119">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="a21f6-p103">在故障列表报告中，您只需将鼠标置于每个响应代码或每个诊断 ID 上，即可查看它们的说明。例如，如果您将鼠标置于诊断 ID 7025 上，则将会看到在工具提示中显示以下内容：</span><span class="sxs-lookup"><span data-stu-id="a21f6-p103">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value. For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>
  
<span data-ttu-id="a21f6-122">为用户创建媒体时发生内部服务器错误。</span><span class="sxs-lookup"><span data-stu-id="a21f6-122">Internal server error creating media for user.</span></span>
  
<span data-ttu-id="a21f6-123">务必注意，故障列表报告并未提供一种简单直观的方式来直接检索至少参加一次失败会话的所有用户列表，也未提供一种用来确定失败会话中最常涉及哪些用户的方法。</span><span class="sxs-lookup"><span data-stu-id="a21f6-123">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="a21f6-124">（一方面，Failure List Report 具有没有筛选功能。）但是，如果将数据导出，然后将其转换为以逗号分隔值文件，您可以使用 Windows PowerShell 查找类似的问题的解答。</span><span class="sxs-lookup"><span data-stu-id="a21f6-124">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="a21f6-125">例如，假设将数据保存到名为 C:\Data\Failure_List.csv 的 .CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="a21f6-125">For example, suppose you save the data to a .CSV file named C:\Data\Failure_List.csv.</span></span> <span data-ttu-id="a21f6-126">根据该文件中所保存的数据，以下命令会列出至少一次失败会话中所涉及的所有用户：</span><span class="sxs-lookup"><span data-stu-id="a21f6-126">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span> 
  
```
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

<span data-ttu-id="a21f6-127">该命令将返回与以下类似的列表：</span><span class="sxs-lookup"><span data-stu-id="a21f6-127">That command will return a list similar to this:</span></span>
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

<span data-ttu-id="a21f6-128">以下两个命令将返回涉及每个用户的失败会话总数：</span><span class="sxs-lookup"><span data-stu-id="a21f6-128">These two commands report back the total number of failed sessions that each user was involved in:</span></span>
  
```
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

<span data-ttu-id="a21f6-129">这将返回与以下类似的数据：</span><span class="sxs-lookup"><span data-stu-id="a21f6-129">That will return data similar to this:</span></span>
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a><span data-ttu-id="a21f6-130">筛选器</span><span class="sxs-lookup"><span data-stu-id="a21f6-130">Filters</span></span>

<span data-ttu-id="a21f6-p105">无。您无法筛选故障列表报告。</span><span class="sxs-lookup"><span data-stu-id="a21f6-p105">None. You cannot filter the Failure List Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="a21f6-133">指标</span><span class="sxs-lookup"><span data-stu-id="a21f6-133">Metrics</span></span>

<span data-ttu-id="a21f6-134">下表列出了各失败呼叫的故障列表报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="a21f6-134">The following table lists the information provided in the Failure List Report for each failed call.</span></span>
  
<span data-ttu-id="a21f6-135">**故障列表报告指标**</span><span class="sxs-lookup"><span data-stu-id="a21f6-135">**Failure List Report Metrics**</span></span>

|<span data-ttu-id="a21f6-136">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="a21f6-136">**Name**</span></span>|<span data-ttu-id="a21f6-137">**您可以按此项排序？**</span><span class="sxs-lookup"><span data-stu-id="a21f6-137">**Can you sort on this item?**</span></span>|<span data-ttu-id="a21f6-138">**说明**</span><span class="sxs-lookup"><span data-stu-id="a21f6-138">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a21f6-139">**报告时间**</span><span class="sxs-lookup"><span data-stu-id="a21f6-139">**Reported time**</span></span> <br/> |<span data-ttu-id="a21f6-140">否</span><span class="sxs-lookup"><span data-stu-id="a21f6-140">No</span></span>  <br/> |<span data-ttu-id="a21f6-141">记录报告的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="a21f6-141">Date and time the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="a21f6-142">**请求**</span><span class="sxs-lookup"><span data-stu-id="a21f6-142">**Request**</span></span> <br/> |<span data-ttu-id="a21f6-143">否</span><span class="sxs-lookup"><span data-stu-id="a21f6-143">No</span></span>  <br/> |<span data-ttu-id="a21f6-p106">失败的 SIP 请求类型。例如 INVITE 或 BYE。</span><span class="sxs-lookup"><span data-stu-id="a21f6-p106">SIP request type that failed. For example, INVITE or BYE.</span></span>  <br/> |
|<span data-ttu-id="a21f6-146">**响应代码**</span><span class="sxs-lookup"><span data-stu-id="a21f6-146">**Response code**</span></span> <br/> |<span data-ttu-id="a21f6-147">否</span><span class="sxs-lookup"><span data-stu-id="a21f6-147">No</span></span>  <br/> |<span data-ttu-id="a21f6-148">会议失败时发送的 SIP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="a21f6-148">SIP response code sent when the conference failed.</span></span>  <br/> |
|<span data-ttu-id="a21f6-149">**诊断 ID**</span><span class="sxs-lookup"><span data-stu-id="a21f6-149">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="a21f6-150">否</span><span class="sxs-lookup"><span data-stu-id="a21f6-150">No</span></span>  <br/> |<span data-ttu-id="a21f6-151">附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。</span><span class="sxs-lookup"><span data-stu-id="a21f6-151">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="a21f6-152">**加入成本时间（毫秒）**</span><span class="sxs-lookup"><span data-stu-id="a21f6-152">**Join cost time (ms)**</span></span> <br/> |<span data-ttu-id="a21f6-153">否</span><span class="sxs-lookup"><span data-stu-id="a21f6-153">No</span></span>  <br/> |<span data-ttu-id="a21f6-154">用户加入会议所需的时间量（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="a21f6-154">Amount of time (in milliseconds) required for the user to join the conference.</span></span>  <br/> |
|<span data-ttu-id="a21f6-155">**来源用户**</span><span class="sxs-lookup"><span data-stu-id="a21f6-155">**From user**</span></span> <br/> |<span data-ttu-id="a21f6-156">否</span><span class="sxs-lookup"><span data-stu-id="a21f6-156">No</span></span>  <br/> |<span data-ttu-id="a21f6-157">发起呼叫的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="a21f6-157">SIP address of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="a21f6-158">**源用户代理**</span><span class="sxs-lookup"><span data-stu-id="a21f6-158">**From user agent**</span></span> <br/> |<span data-ttu-id="a21f6-159">否</span><span class="sxs-lookup"><span data-stu-id="a21f6-159">No</span></span>  <br/> |<span data-ttu-id="a21f6-160">呼叫发起用户的终结点使用的软件。</span><span class="sxs-lookup"><span data-stu-id="a21f6-160">Software used by the endpoint of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="a21f6-161">**目标用户**</span><span class="sxs-lookup"><span data-stu-id="a21f6-161">**To user**</span></span> <br/> |<span data-ttu-id="a21f6-162">否</span><span class="sxs-lookup"><span data-stu-id="a21f6-162">No</span></span>  <br/> |<span data-ttu-id="a21f6-163">被呼叫用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="a21f6-163">SIP address of the user who was being called.</span></span>  <br/> |
   

