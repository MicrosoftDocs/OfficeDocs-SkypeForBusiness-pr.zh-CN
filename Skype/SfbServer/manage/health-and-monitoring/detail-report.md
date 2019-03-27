---
title: 会议详细信息报告中 Skype 业务服务器
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 摘要： 了解在 Skype 用于 Business Server 会议详细信息报告。
ms.openlocfilehash: 122cd3b8bdc69342b4d0f55c9fe5168fdc44757d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880460"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a><span data-ttu-id="86bf4-103">会议详细信息报告中 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="86bf4-103">Conference Detail Report in Skype for Business Server</span></span>

<span data-ttu-id="86bf4-104">**摘要：** 了解用于在 Skype 业务服务器的会议详细信息报告。</span><span class="sxs-lookup"><span data-stu-id="86bf4-104">**Summary:** Learn about the Conference Detail Report used in Skype for Business Server.</span></span>

<span data-ttu-id="86bf4-p101">会议详细信息报告提供有关参与会议的所有用户的详细信息。例如，您可以查看用户加入会议的日期和时间、用户离开会议的日期和时间以及用于将该用户连接到会议的端点的用户代理等信息。还可以查看用户在每个会议中的角色的信息（例如，演示者或与会者）。可能最重要的是，您可以快速查看哪些用户成功加入和完成会议，哪些用户无法成功加入和完成会议。</span><span class="sxs-lookup"><span data-stu-id="86bf4-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="86bf4-109">访问会议详细信息报告</span><span class="sxs-lookup"><span data-stu-id="86bf4-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="86bf4-110">可从以下报告中访问会议详细信息报告：</span><span class="sxs-lookup"><span data-stu-id="86bf4-110">The Conference Detail Report can be accessed from the following reports:</span></span>

- <span data-ttu-id="86bf4-111">[Call Admission Control Report](call-admission-control-report.md)（通过单击会议的“详细信息”指标）</span><span class="sxs-lookup"><span data-stu-id="86bf4-111">The [Call Admission Control Report](call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

- <span data-ttu-id="86bf4-112">[Failure List Report](failure-list-report.md)（通过单击“会议”指标）</span><span class="sxs-lookup"><span data-stu-id="86bf4-112">The [Failure List Report](failure-list-report.md) (by clicking the Conference metric)</span></span>

- <span data-ttu-id="86bf4-113">[User Activity Report](call-diagnostic-reports-per-user.md)（通过单击“会议 URI”指标）</span><span class="sxs-lookup"><span data-stu-id="86bf4-113">The [User Activity Report](call-diagnostic-reports-per-user.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="86bf4-114">从会议详细信息报告可以通过单击诊断报告 （详细信息） 指标来访问[诊断报告](diagnostic-report.md)。</span><span class="sxs-lookup"><span data-stu-id="86bf4-114">From the Conference Detail Report you can access the [Diagnostic Repor](diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

## <a name="filters"></a><span data-ttu-id="86bf4-115">筛选器</span><span class="sxs-lookup"><span data-stu-id="86bf4-115">Filters</span></span>

<span data-ttu-id="86bf4-p102">无。您无法筛选会议详细信息报告。</span><span class="sxs-lookup"><span data-stu-id="86bf4-p102">None. You cannot filter on the Conference Detail Report.</span></span>

## <a name="metrics"></a><span data-ttu-id="86bf4-118">指标</span><span class="sxs-lookup"><span data-stu-id="86bf4-118">Metrics</span></span>

<span data-ttu-id="86bf4-119">下表列出了会议详细信息报告的“会议信息”部分提供的信息。</span><span class="sxs-lookup"><span data-stu-id="86bf4-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

<span data-ttu-id="86bf4-120">**会议信息指标**</span><span class="sxs-lookup"><span data-stu-id="86bf4-120">**Conference Information Metrics**</span></span>


| <span data-ttu-id="86bf4-121">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="86bf4-121">**Name**</span></span>                 | <span data-ttu-id="86bf4-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="86bf4-122">**Description**</span></span>                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="86bf4-123">**会议 URI**</span><span class="sxs-lookup"><span data-stu-id="86bf4-123">**Conference URI**</span></span> <br/> | <span data-ttu-id="86bf4-p103">分配给会议的 URI。例如：</span><span class="sxs-lookup"><span data-stu-id="86bf4-p103">URI assigned to the conference. For example:</span></span>  <br/> <span data-ttu-id="86bf4-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="86bf4-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span>  <br/> |
| <span data-ttu-id="86bf4-127">**池 FQDN**</span><span class="sxs-lookup"><span data-stu-id="86bf4-127">**Pool FQDN**</span></span> <br/>      | <span data-ttu-id="86bf4-128">会话中涉及的注册器池或边缘服务器的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="86bf4-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span>  <br/>                             |
| <span data-ttu-id="86bf4-129">**开始时间**</span><span class="sxs-lookup"><span data-stu-id="86bf4-129">**Start time**</span></span> <br/>     | <span data-ttu-id="86bf4-130">会议开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="86bf4-130">Date and time that the conference started.</span></span>  <br/>                                                                          |
| <span data-ttu-id="86bf4-131">**组织者**</span><span class="sxs-lookup"><span data-stu-id="86bf4-131">**Organizer**</span></span> <br/>      | <span data-ttu-id="86bf4-132">组织会议的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="86bf4-132">SIP address of the user who organized the conference.</span></span>  <br/>                                                               |
| <span data-ttu-id="86bf4-133">**结束时间**</span><span class="sxs-lookup"><span data-stu-id="86bf4-133">**End time**</span></span> <br/>       | <span data-ttu-id="86bf4-134">会议结束的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="86bf4-134">Date and time that the conference ended.</span></span>  <br/>                                                                            |

<span data-ttu-id="86bf4-135">下表列出了会议详细信息报告的“会议参与”部分提供的信息。</span><span class="sxs-lookup"><span data-stu-id="86bf4-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

<span data-ttu-id="86bf4-136">**会议参与指标**</span><span class="sxs-lookup"><span data-stu-id="86bf4-136">**Conference Participation Metrics**</span></span>

|<span data-ttu-id="86bf4-137">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="86bf4-137">**Name**</span></span>|<span data-ttu-id="86bf4-138">**说明**</span><span class="sxs-lookup"><span data-stu-id="86bf4-138">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="86bf4-139">**用户**</span><span class="sxs-lookup"><span data-stu-id="86bf4-139">**User**</span></span> <br/> |<span data-ttu-id="86bf4-140">参与会议的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="86bf4-140">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="86bf4-141">**角色**</span><span class="sxs-lookup"><span data-stu-id="86bf4-141">**Role**</span></span> <br/> |<span data-ttu-id="86bf4-142">会议参与者扮演的角色（例如“演示者”）。</span><span class="sxs-lookup"><span data-stu-id="86bf4-142">Role (for example, Presenter) played by the conference participant.</span></span>  <br/> |
|<span data-ttu-id="86bf4-143">**连接**</span><span class="sxs-lookup"><span data-stu-id="86bf4-143">**Connectivity**</span></span> <br/> |<span data-ttu-id="86bf4-144">参与者的网络连接（通常为“来自内部”或“来自外部”）。</span><span class="sxs-lookup"><span data-stu-id="86bf4-144">Network connectivity (typically From Internal or From External) for the participant.</span></span>  <br/> |
|<span data-ttu-id="86bf4-145">**加入时间**</span><span class="sxs-lookup"><span data-stu-id="86bf4-145">**Join time**</span></span> <br/> |<span data-ttu-id="86bf4-146">参与者加入会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="86bf4-146">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="86bf4-147">**离开时间**</span><span class="sxs-lookup"><span data-stu-id="86bf4-147">**Leave time**</span></span> <br/> |<span data-ttu-id="86bf4-148">参与者离开会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="86bf4-148">Date and time that the participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="86bf4-149">**用户代理**</span><span class="sxs-lookup"><span data-stu-id="86bf4-149">**User agent**</span></span> <br/> |<span data-ttu-id="86bf4-150">参与者的终结点使用的软件的标识符。</span><span class="sxs-lookup"><span data-stu-id="86bf4-150">Identifier for the software used by the participant's endpoint.</span></span>  <br/> |
|<span data-ttu-id="86bf4-151">**诊断报告**</span><span class="sxs-lookup"><span data-stu-id="86bf4-151">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="86bf4-p104">提供诊断和故障排除信息。包括 SIP 响应代码、诊断标题、会议加入时间和失败会话的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="86bf4-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |

<span data-ttu-id="86bf4-154">下表列出了会议详细信息报告的会议形式部分中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="86bf4-154">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

<span data-ttu-id="86bf4-155">**会议形式指标**</span><span class="sxs-lookup"><span data-stu-id="86bf4-155">**Conference Modalities Metrics**</span></span>

|<span data-ttu-id="86bf4-156">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="86bf4-156">**Name**</span></span>|<span data-ttu-id="86bf4-157">**说明**</span><span class="sxs-lookup"><span data-stu-id="86bf4-157">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="86bf4-158">**用户**</span><span class="sxs-lookup"><span data-stu-id="86bf4-158">**User**</span></span> <br/> |<span data-ttu-id="86bf4-159">参与会议的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="86bf4-159">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="86bf4-160">**加入时间**</span><span class="sxs-lookup"><span data-stu-id="86bf4-160">**Join time**</span></span> <br/> |<span data-ttu-id="86bf4-161">参与者加入会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="86bf4-161">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="86bf4-162">**离开时间**</span><span class="sxs-lookup"><span data-stu-id="86bf4-162">**Leave time**</span></span> <br/> |<span data-ttu-id="86bf4-163">参与者离开会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="86bf4-163">Date and time that a participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="86bf4-164">**会议服务器 URI**</span><span class="sxs-lookup"><span data-stu-id="86bf4-164">**Conferencing server URI**</span></span> <br/> |<span data-ttu-id="86bf4-165">会议中使用的会议服务器的 URI。</span><span class="sxs-lookup"><span data-stu-id="86bf4-165">URI for the Conferencing server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="86bf4-166">**诊断报告**</span><span class="sxs-lookup"><span data-stu-id="86bf4-166">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="86bf4-p105">提供诊断和故障排除信息。包括 SIP 响应代码、诊断标题、会议加入时间和失败会话的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="86bf4-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |


