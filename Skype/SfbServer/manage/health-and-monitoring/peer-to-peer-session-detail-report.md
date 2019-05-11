---
title: Skype 中的业务服务器的对等会话详细信息报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
description: 摘要： 了解在 Skype 业务服务器的对等会话详细信息报告。
ms.openlocfilehash: 77b5a80c2280d5242e4efcc0dc696c6720da4f64
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33925227"
---
# <a name="peer-to-peer-session-detail-report-in-skype-for-business-server"></a><span data-ttu-id="ae375-103">Skype 中的业务服务器的对等会话详细信息报告</span><span class="sxs-lookup"><span data-stu-id="ae375-103">Peer-to-Peer Session Detail Report in Skype for Business Server</span></span>
 
<span data-ttu-id="ae375-104">**摘要：** 了解业务服务器的对等会话详细信息报告中 Skype。</span><span class="sxs-lookup"><span data-stu-id="ae375-104">**Summary:** Learn about the Peer-to-Peer Session Detail Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="ae375-p101">对等会话详细信息报告返回有关对等会话的详细信息。例如，如果您选择即时消息会话，则此报告将告知您会话中两个用户各自发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="ae375-p101">The Peer-to-Peer Session Detail Report returns detailed information about a peer-to-peer session. For example, if you select an instant messaging session, the report will tell you the number of messages sent by each of the two users in the session.</span></span>
  
## <a name="accessing-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="ae375-107">访问对等会话详细信息报告</span><span class="sxs-lookup"><span data-stu-id="ae375-107">Accessing the Peer-to-Peer Session Detail Report</span></span>

<span data-ttu-id="ae375-108">可以从下列任一报告（可从监控报告主页中访问所有这些报告）访问对等会话详细信息报告：</span><span class="sxs-lookup"><span data-stu-id="ae375-108">The Peer-to-Peer Session Detail Report can be accessed from any of the following reports (all of which can be accessed from the Monitoring Reports home page):</span></span>
  
- <span data-ttu-id="ae375-109">IP 电话清单报告</span><span class="sxs-lookup"><span data-stu-id="ae375-109">IP Phone Inventory Report</span></span>
    
- <span data-ttu-id="ae375-110">用户活动报告</span><span class="sxs-lookup"><span data-stu-id="ae375-110">User Activity Report</span></span>
    
- <span data-ttu-id="ae375-111">呼叫允许控制报告</span><span class="sxs-lookup"><span data-stu-id="ae375-111">Call Admission Control Report</span></span>
    
- <span data-ttu-id="ae375-112">故障列表报告</span><span class="sxs-lookup"><span data-stu-id="ae375-112">Failure List Report</span></span> 
    
<span data-ttu-id="ae375-113">从对等会话详细信息报告中可以访问[诊断报告中的业务服务器 Skype](diagnostic-report.md)通过单击诊断报告 （详细信息） 指标。</span><span class="sxs-lookup"><span data-stu-id="ae375-113">From within the Peer-to-Peer Session Detail Report you can access the [Diagnostic Report in Skype for Business Server](diagnostic-report.md) by clicking the Diagnostic Report (Details) metric.</span></span> <span data-ttu-id="ae375-114">此外，还可以通过单击这两个指标之一来访问主要故障报告：</span><span class="sxs-lookup"><span data-stu-id="ae375-114">You can also access the Top Failures Report by clicking either of these two metrics:</span></span>
  
- <span data-ttu-id="ae375-115">响应</span><span class="sxs-lookup"><span data-stu-id="ae375-115">Response</span></span>
    
- <span data-ttu-id="ae375-116">诊断 ID</span><span class="sxs-lookup"><span data-stu-id="ae375-116">Diagnostic ID</span></span>
    
## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="ae375-117">最充分地利用对等会话详细信息报告</span><span class="sxs-lookup"><span data-stu-id="ae375-117">Making the Best Use of the Peer-to-Peer session Detail Report</span></span>

<span data-ttu-id="ae375-p103">对等会话详细信息报告包括大量指标，其中有许多指标是系统管理员所不熟悉的。不过，通常您只需将鼠标指针悬停在指标标签的上方即可查看提供了指标的简要说明的工具提示。</span><span class="sxs-lookup"><span data-stu-id="ae375-p103">The Peer-to-Peer Session Detail Report includes a large number of metrics, many of which might not be familiar to system administrators. Often-times, however, you can view a tooltip that offers a brief description of that metric simply by holding your mouse over the metric label.</span></span>
  
<span data-ttu-id="ae375-p104">请注意，给定报告上显示的实际指标将取决于您所选的对等会话的类型。音频/视频会话将报告一组与即时消息会话不同的指标。</span><span class="sxs-lookup"><span data-stu-id="ae375-p104">Note that the actual metrics shown on a given report will depend on the type of peer-to-peer session you selected. An audio/video session will report a different set of metrics than an instant messaging session.</span></span>
  
<span data-ttu-id="ae375-122">还可以将鼠标指针悬停在响应代码和诊断 ID 指标的上方来获取这些值的描述：</span><span class="sxs-lookup"><span data-stu-id="ae375-122">You can also hold your mouse over the Response code and Diagnostic ID metrics in order to obtain a description of those values:</span></span>
  
## <a name="filters"></a><span data-ttu-id="ae375-123">筛选器</span><span class="sxs-lookup"><span data-stu-id="ae375-123">Filters</span></span>

<span data-ttu-id="ae375-p105">无。无法筛选对等会话详细信息报告。</span><span class="sxs-lookup"><span data-stu-id="ae375-p105">None. You cannot filter the Peer-to-Peer Session Detail Report.</span></span>
  
## <a name="session-information-metrics"></a><span data-ttu-id="ae375-126">会话信息指标</span><span class="sxs-lookup"><span data-stu-id="ae375-126">Session Information Metrics</span></span>

<span data-ttu-id="ae375-127">下表列出了每个会话的对等会话详细信息报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="ae375-127">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session.</span></span>
  
<span data-ttu-id="ae375-128">**会话信息指标**</span><span class="sxs-lookup"><span data-stu-id="ae375-128">**Session Information Metrics**</span></span>

|<span data-ttu-id="ae375-129">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="ae375-129">**Name**</span></span>|<span data-ttu-id="ae375-130">**说明**</span><span class="sxs-lookup"><span data-stu-id="ae375-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ae375-131">**池 FQDN**</span><span class="sxs-lookup"><span data-stu-id="ae375-131">**Pool FQDN**</span></span> <br/> |<span data-ttu-id="ae375-132">会话中涉及的注册器池或边缘服务器的完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="ae375-132">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server involved in the session.</span></span>  <br/> |
|<span data-ttu-id="ae375-133">**邀请时间**</span><span class="sxs-lookup"><span data-stu-id="ae375-133">**Invite time**</span></span> <br/> |<span data-ttu-id="ae375-134">最初发送会话邀请的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="ae375-134">Date and time the session invitation was originally sent.</span></span>  <br/> |
|<span data-ttu-id="ae375-135">**响应时间**</span><span class="sxs-lookup"><span data-stu-id="ae375-135">**Response time**</span></span> <br/> |<span data-ttu-id="ae375-136">收到邀请接受函的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="ae375-136">Date and time that the invitation acceptance was received.</span></span>  <br/> |
|<span data-ttu-id="ae375-137">**来源用户**</span><span class="sxs-lookup"><span data-stu-id="ae375-137">**From user**</span></span> <br/> |<span data-ttu-id="ae375-138">发起会话的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="ae375-138">SIP address of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="ae375-139">**源用户代理**</span><span class="sxs-lookup"><span data-stu-id="ae375-139">**From user agent**</span></span> <br/> |<span data-ttu-id="ae375-140">发起会话的用户的终结点使用的软件。</span><span class="sxs-lookup"><span data-stu-id="ae375-140">Software used by the endpoint of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="ae375-141">**源用户为内部用户**</span><span class="sxs-lookup"><span data-stu-id="ae375-141">**Is From user internal**</span></span> <br/> |<span data-ttu-id="ae375-142">指示启动会话的用户是否登录到内部网络。</span><span class="sxs-lookup"><span data-stu-id="ae375-142">Indicates whether the user who initiated the session was logged on to the internal network.</span></span>  <br/> |
|<span data-ttu-id="ae375-143">**源用户与桌面电话集成**</span><span class="sxs-lookup"><span data-stu-id="ae375-143">**Is From user integrated with desk phone**</span></span> <br/> |<span data-ttu-id="ae375-144">指示启动会话的用户使用的终结点是否与其桌面电话集成。</span><span class="sxs-lookup"><span data-stu-id="ae375-144">Indicates whether the endpoint used by the user who initiated the session is integrated with his or her desktop phone.</span></span>  <br/> |
|<span data-ttu-id="ae375-145">**会话优先级**</span><span class="sxs-lookup"><span data-stu-id="ae375-145">**Session Priority**</span></span> <br/> |<span data-ttu-id="ae375-p106">分配给会话的优先级。有效优先级有：未知、非紧急、正常和紧急。</span><span class="sxs-lookup"><span data-stu-id="ae375-p106">Priority assigned to the session. Valid priorities are: Unknown; Non-Urgent; Normal; Urgent; and Emergency.</span></span>  <br/> |
|<span data-ttu-id="ae375-148">**响应代码**</span><span class="sxs-lookup"><span data-stu-id="ae375-148">**Response code**</span></span> <br/> |<span data-ttu-id="ae375-149">会话失败时发送的 SIP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="ae375-149">SIP response code sent when the session failed.</span></span>  <br/> |
|<span data-ttu-id="ae375-150">**前端**</span><span class="sxs-lookup"><span data-stu-id="ae375-150">**Front end**</span></span> <br/> |<span data-ttu-id="ae375-151">会议中使用的前端服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="ae375-151">Name of the Front End Server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="ae375-152">**捕获时间**</span><span class="sxs-lookup"><span data-stu-id="ae375-152">**Capture time**</span></span> <br/> |<span data-ttu-id="ae375-153">记录会话信息的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="ae375-153">Date and time that the session information was recorded.</span></span>  <br/> |
|<span data-ttu-id="ae375-154">**结束时间**</span><span class="sxs-lookup"><span data-stu-id="ae375-154">**End time**</span></span> <br/> |<span data-ttu-id="ae375-155">会话结束的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="ae375-155">Date and time the session ended.</span></span>  <br/> |
|<span data-ttu-id="ae375-156">**目标用户**</span><span class="sxs-lookup"><span data-stu-id="ae375-156">**To user**</span></span> <br/> |<span data-ttu-id="ae375-157">受邀加入会话的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="ae375-157">SIP address of the user who was invited to the session.</span></span>  <br/> |
|<span data-ttu-id="ae375-158">**目标用户代理**</span><span class="sxs-lookup"><span data-stu-id="ae375-158">**To user agent**</span></span> <br/> |<span data-ttu-id="ae375-159">受邀加入会话的用户的终结点使用的软件。</span><span class="sxs-lookup"><span data-stu-id="ae375-159">Software used by the endpoint of the user who was invited to the session.</span></span>  <br/> |
|<span data-ttu-id="ae375-160">**目标用户为内部用户**</span><span class="sxs-lookup"><span data-stu-id="ae375-160">**Is To user internal**</span></span> <br/> |<span data-ttu-id="ae375-161">指示受邀加入会话的用户是否登录到内部网络。</span><span class="sxs-lookup"><span data-stu-id="ae375-161">Indicates whether the user who was invited to the session was logged on to the internal network.</span></span>  <br/> |
|<span data-ttu-id="ae375-162">**目标用户与桌面电话集成**</span><span class="sxs-lookup"><span data-stu-id="ae375-162">**Is To user integrated with desk phone**</span></span> <br/> |<span data-ttu-id="ae375-163">指示受邀加入会话的用户使用的终结点是否与其桌面电话集成。</span><span class="sxs-lookup"><span data-stu-id="ae375-163">Indicates whether the endpoint used by the user who was invited to the session is integrated with his or her desktop phone.</span></span>  <br/> |
|<span data-ttu-id="ae375-164">**为重试会话**</span><span class="sxs-lookup"><span data-stu-id="ae375-164">**Is retried session**</span></span> <br/> |<span data-ttu-id="ae375-165">指示会话是否是在尝试重试以前失败的会话。</span><span class="sxs-lookup"><span data-stu-id="ae375-165">Indicates whether the session is an attempt to retry a session that previously failed.</span></span>  <br/> |
|<span data-ttu-id="ae375-166">**诊断 ID**</span><span class="sxs-lookup"><span data-stu-id="ae375-166">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="ae375-p107">附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。将光标停留在 ID 号上可查看有关该 ID 的其他信息。</span><span class="sxs-lookup"><span data-stu-id="ae375-p107">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Hold the mouse over the ID number to view additional information about that ID.</span></span>  <br/> |
   
## <a name="metrics-for-modalities"></a><span data-ttu-id="ae375-169">形式指标</span><span class="sxs-lookup"><span data-stu-id="ae375-169">Metrics for Modalities</span></span>

<span data-ttu-id="ae375-170">下表列出了每种会话形式的对等会话详细信息报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="ae375-170">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session modality.</span></span>
  
<span data-ttu-id="ae375-171">**形式指标**</span><span class="sxs-lookup"><span data-stu-id="ae375-171">**Metrics for Modalities**</span></span>

|<span data-ttu-id="ae375-172">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="ae375-172">**Name**</span></span>|<span data-ttu-id="ae375-173">**是否可按此项排序？**</span><span class="sxs-lookup"><span data-stu-id="ae375-173">**Can you sort on this item?**</span></span>|<span data-ttu-id="ae375-174">**说明**</span><span class="sxs-lookup"><span data-stu-id="ae375-174">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ae375-175">**形式**</span><span class="sxs-lookup"><span data-stu-id="ae375-175">**Modalities**</span></span> <br/> |<span data-ttu-id="ae375-176">否</span><span class="sxs-lookup"><span data-stu-id="ae375-176">No</span></span>  <br/> |<span data-ttu-id="ae375-p108">会话中使用的形式。例如，即时消息 (IM) 或文件传输。</span><span class="sxs-lookup"><span data-stu-id="ae375-p108">Modalities used in the session. For example, instant messaging (IM) or file transfer.</span></span>  <br/> |
|<span data-ttu-id="ae375-179">**源用户消息**</span><span class="sxs-lookup"><span data-stu-id="ae375-179">**From user messages**</span></span> <br/> |<span data-ttu-id="ae375-180">否</span><span class="sxs-lookup"><span data-stu-id="ae375-180">No</span></span>  <br/> |<span data-ttu-id="ae375-181">启动会话的用户发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="ae375-181">Number of messages sent by the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="ae375-182">**目标用户消息**</span><span class="sxs-lookup"><span data-stu-id="ae375-182">**To user messages**</span></span> <br/> |<span data-ttu-id="ae375-183">否</span><span class="sxs-lookup"><span data-stu-id="ae375-183">No</span></span>  <br/> |<span data-ttu-id="ae375-184">受邀加入会话的用户发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="ae375-184">Number of messages sent by the user who was invited to join the session.</span></span>  <br/> |
   
## <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="ae375-185">诊断报告指标</span><span class="sxs-lookup"><span data-stu-id="ae375-185">Metrics for Diagnostic Reports</span></span>

<span data-ttu-id="ae375-186">下表列出了每个诊断报告的对等会话详细信息报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="ae375-186">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each diagnostic report.</span></span>
  
<span data-ttu-id="ae375-187">**诊断报告指标**</span><span class="sxs-lookup"><span data-stu-id="ae375-187">**Metrics for Diagnostic Reports**</span></span>

|<span data-ttu-id="ae375-188">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="ae375-188">**Name**</span></span>|<span data-ttu-id="ae375-189">**是否可按此项排序？**</span><span class="sxs-lookup"><span data-stu-id="ae375-189">**Can you sort on this item?**</span></span>|<span data-ttu-id="ae375-190">**说明**</span><span class="sxs-lookup"><span data-stu-id="ae375-190">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ae375-191">**详情**</span><span class="sxs-lookup"><span data-stu-id="ae375-191">**Detail**</span></span> <br/> |<span data-ttu-id="ae375-192">否</span><span class="sxs-lookup"><span data-stu-id="ae375-192">No</span></span>  <br/> |<span data-ttu-id="ae375-193">当您单击此项时，报告显示会话的诊断报告。</span><span class="sxs-lookup"><span data-stu-id="ae375-193">When you click this item, the report shows the Diagnostic Report for the session.</span></span>  <br/> |
|<span data-ttu-id="ae375-194">**报告时间**</span><span class="sxs-lookup"><span data-stu-id="ae375-194">**Report time**</span></span> <br/> |<span data-ttu-id="ae375-195">否</span><span class="sxs-lookup"><span data-stu-id="ae375-195">No</span></span>  <br/> |<span data-ttu-id="ae375-196">记录报告的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="ae375-196">Date and time the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="ae375-197">**请求**</span><span class="sxs-lookup"><span data-stu-id="ae375-197">**Request**</span></span> <br/> |<span data-ttu-id="ae375-198">否</span><span class="sxs-lookup"><span data-stu-id="ae375-198">No</span></span>  <br/> |<span data-ttu-id="ae375-p109">SIP 请求类型。例如 INVITE 或 BYE。</span><span class="sxs-lookup"><span data-stu-id="ae375-p109">SIP request type. For example, INVITE or BYE.</span></span>  <br/> |
|<span data-ttu-id="ae375-201">**诊断 ID**</span><span class="sxs-lookup"><span data-stu-id="ae375-201">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="ae375-202">否</span><span class="sxs-lookup"><span data-stu-id="ae375-202">No</span></span>  <br/> |<span data-ttu-id="ae375-203">附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。</span><span class="sxs-lookup"><span data-stu-id="ae375-203">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="ae375-204">**内容类型**</span><span class="sxs-lookup"><span data-stu-id="ae375-204">**Content type**</span></span> <br/> |<span data-ttu-id="ae375-205">否</span><span class="sxs-lookup"><span data-stu-id="ae375-205">No</span></span>  <br/> |<span data-ttu-id="ae375-p110">会议中使用的媒体内容的类型。例如，常见内容类型为 Application/sdp。会话描述协议 (SDP) 是用于会话公告、会话邀请及其他形式的多媒体会话启动的标准 Internet 协议。</span><span class="sxs-lookup"><span data-stu-id="ae375-p110">Type of media content used in the conference. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span>  <br/> |
|<span data-ttu-id="ae375-209">**报告者**</span><span class="sxs-lookup"><span data-stu-id="ae375-209">**Reported by**</span></span> <br/> |<span data-ttu-id="ae375-210">否</span><span class="sxs-lookup"><span data-stu-id="ae375-210">No</span></span>  <br/> |<span data-ttu-id="ae375-211">报告问题的计算机（即客户端或服务器）。</span><span class="sxs-lookup"><span data-stu-id="ae375-211">Computer (that is, client or server) that reported the problem.</span></span>  <br/> |
   

