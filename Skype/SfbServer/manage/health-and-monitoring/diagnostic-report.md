---
title: Skype for Business 服务器中的诊断报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: '摘要: 了解 Skype for Business 服务器中的诊断报告。'
ms.openlocfilehash: d71906f2407a0daadc04417ab60a23c86f5eeb52
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305771"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a><span data-ttu-id="4ba3c-103">Skype for Business 服务器中的诊断报告</span><span class="sxs-lookup"><span data-stu-id="4ba3c-103">Diagnostic Report in Skype for Business Server</span></span>
 
<span data-ttu-id="4ba3c-104">**摘要:** 了解 Skype for Business 服务器中的诊断报告。</span><span class="sxs-lookup"><span data-stu-id="4ba3c-104">**Summary:** Learn about the Diagnostic Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="4ba3c-105">诊断报告提供失败的会话的诊断和故障排除信息。</span><span class="sxs-lookup"><span data-stu-id="4ba3c-105">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="4ba3c-106">此信息包括在会话失败时所报告的诊断 ID 和诊断标头。</span><span class="sxs-lookup"><span data-stu-id="4ba3c-106">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="4ba3c-107">诊断 ID 是附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），而诊断标头提供诊断 ID 的附带说明。</span><span class="sxs-lookup"><span data-stu-id="4ba3c-107">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="4ba3c-108">该报告可能还包含报告组件所了解的有价值的故障排除详细信息。</span><span class="sxs-lookup"><span data-stu-id="4ba3c-108">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="4ba3c-109">例如：</span><span class="sxs-lookup"><span data-stu-id="4ba3c-109">For example:</span></span>
  
- <span data-ttu-id="4ba3c-p102">由生成故障的 PSTN 网关提供的原因代码。在 PSTN 网络上，传出呼叫失败时，会自动生成 ISDN 用户部分 (ISUP) 原因代码。例如，PSTN 网关可能会发送原因代码 34，指示不存在可用于完成呼叫的任何电路或信道。</span><span class="sxs-lookup"><span data-stu-id="4ba3c-p102">The cause code provided by the PSTN gateway that generated the failure. When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated. For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>
    
- <span data-ttu-id="4ba3c-113">针对连接失败的对等方 FQDN、端口和 Winsock 错误。</span><span class="sxs-lookup"><span data-stu-id="4ba3c-113">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>
    
- <span data-ttu-id="4ba3c-p103">针对 DNS 解析失败所查找的名称。每次客户端联系名称服务器并请求与指定的设备名称相对应的 IP 地址时，都会进行 DNS 解析。</span><span class="sxs-lookup"><span data-stu-id="4ba3c-p103">Names being looked up for DNS resolution failures. DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>
    
## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="4ba3c-116">访问诊断报告</span><span class="sxs-lookup"><span data-stu-id="4ba3c-116">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="4ba3c-117">可通过在 Skype for Business Server 或会议详细信息报告[中单击对等会话详细信息报告](peer-to-peer-session-detail-report.md)上的诊断报告 (详细信息) 指标来访问诊断报告。</span><span class="sxs-lookup"><span data-stu-id="4ba3c-117">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Skype for Business Server](peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>
  
## <a name="filters"></a><span data-ttu-id="4ba3c-118">筛选器</span><span class="sxs-lookup"><span data-stu-id="4ba3c-118">Filters</span></span>

<span data-ttu-id="4ba3c-p104">无。您不能对诊断报告进行筛选。</span><span class="sxs-lookup"><span data-stu-id="4ba3c-p104">None. You cannot filter the Diagnostic Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="4ba3c-121">指标</span><span class="sxs-lookup"><span data-stu-id="4ba3c-121">Metrics</span></span>

<span data-ttu-id="4ba3c-122">下表列出了各会话的诊断报告中提供的信息。</span><span class="sxs-lookup"><span data-stu-id="4ba3c-122">The following table lists the information provided in the Diagnostic Report for each session.</span></span>
  
<span data-ttu-id="4ba3c-123">**诊断报告指标**</span><span class="sxs-lookup"><span data-stu-id="4ba3c-123">**Diagnostic Report Metrics**</span></span>

|<span data-ttu-id="4ba3c-124">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="4ba3c-124">**Name**</span></span>|<span data-ttu-id="4ba3c-125">**是否可按此项排序？**</span><span class="sxs-lookup"><span data-stu-id="4ba3c-125">**Can you sort on this item?**</span></span>|<span data-ttu-id="4ba3c-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="4ba3c-126">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4ba3c-127">**报告时间**</span><span class="sxs-lookup"><span data-stu-id="4ba3c-127">**Report time**</span></span> <br/> |<span data-ttu-id="4ba3c-128">否</span><span class="sxs-lookup"><span data-stu-id="4ba3c-128">No</span></span>  <br/> |<span data-ttu-id="4ba3c-129">记录报告的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="4ba3c-129">Date and time that the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="4ba3c-130">**响应代码**</span><span class="sxs-lookup"><span data-stu-id="4ba3c-130">**Response code**</span></span> <br/> |<span data-ttu-id="4ba3c-131">否</span><span class="sxs-lookup"><span data-stu-id="4ba3c-131">No</span></span>  <br/> |<span data-ttu-id="4ba3c-132">会话失败时发送的 SIP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="4ba3c-132">SIP response code sent when the session failed.</span></span>  <br/> |
|<span data-ttu-id="4ba3c-133">**请求类型**</span><span class="sxs-lookup"><span data-stu-id="4ba3c-133">**Request type**</span></span> <br/> |<span data-ttu-id="4ba3c-134">否</span><span class="sxs-lookup"><span data-stu-id="4ba3c-134">No</span></span>  <br/> |<span data-ttu-id="4ba3c-p105">失败的 SIP 请求类型。例如，INVITE、BYE 或 SERVICE。</span><span class="sxs-lookup"><span data-stu-id="4ba3c-p105">SIP request type that failed. For example, INVITE, BYE, or SERVICE.</span></span>  <br/> |
|<span data-ttu-id="4ba3c-137">**来源**</span><span class="sxs-lookup"><span data-stu-id="4ba3c-137">**Source**</span></span> <br/> |<span data-ttu-id="4ba3c-138">否</span><span class="sxs-lookup"><span data-stu-id="4ba3c-138">No</span></span>  <br/> |<span data-ttu-id="4ba3c-139">错误的来源。</span><span class="sxs-lookup"><span data-stu-id="4ba3c-139">Source of the error.</span></span>  <br/> |
|<span data-ttu-id="4ba3c-140">**源用户 URI**</span><span class="sxs-lookup"><span data-stu-id="4ba3c-140">**From user URI**</span></span> <br/> |<span data-ttu-id="4ba3c-141">否</span><span class="sxs-lookup"><span data-stu-id="4ba3c-141">No</span></span>  <br/> |<span data-ttu-id="4ba3c-142">发起会话的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="4ba3c-142">SIP address of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="4ba3c-143">**源用户代理**</span><span class="sxs-lookup"><span data-stu-id="4ba3c-143">**From user agent**</span></span> <br/> |<span data-ttu-id="4ba3c-144">否</span><span class="sxs-lookup"><span data-stu-id="4ba3c-144">No</span></span>  <br/> |<span data-ttu-id="4ba3c-145">发起会话的用户的终结点使用的软件。</span><span class="sxs-lookup"><span data-stu-id="4ba3c-145">Software used by the endpoint of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="4ba3c-146">**诊断 ID**</span><span class="sxs-lookup"><span data-stu-id="4ba3c-146">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="4ba3c-147">否</span><span class="sxs-lookup"><span data-stu-id="4ba3c-147">No</span></span>  <br/> |<span data-ttu-id="4ba3c-148">附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。</span><span class="sxs-lookup"><span data-stu-id="4ba3c-148">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="4ba3c-149">**内容类型**</span><span class="sxs-lookup"><span data-stu-id="4ba3c-149">**Content type**</span></span> <br/> |<span data-ttu-id="4ba3c-150">否</span><span class="sxs-lookup"><span data-stu-id="4ba3c-150">No</span></span>  <br/> |<span data-ttu-id="4ba3c-p106">失败的媒体内容类型。例如，常见内容类型为 Application/sdp。会话描述协议 (SDP) 是用于会话公告、会话邀请及其他形式的多媒体会话启动的标准 Internet 协议。</span><span class="sxs-lookup"><span data-stu-id="4ba3c-p106">Type of media content that failed. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span>  <br/> |
|<span data-ttu-id="4ba3c-154">**应用程序**</span><span class="sxs-lookup"><span data-stu-id="4ba3c-154">**Application**</span></span> <br/> |<span data-ttu-id="4ba3c-155">否</span><span class="sxs-lookup"><span data-stu-id="4ba3c-155">No</span></span>  <br/> |<span data-ttu-id="4ba3c-156">错误涉及的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4ba3c-156">Application involved in the error.</span></span>  <br/> |
|<span data-ttu-id="4ba3c-157">**目标用户 URI**</span><span class="sxs-lookup"><span data-stu-id="4ba3c-157">**To user URI**</span></span> <br/> |<span data-ttu-id="4ba3c-158">否</span><span class="sxs-lookup"><span data-stu-id="4ba3c-158">No</span></span>  <br/> |<span data-ttu-id="4ba3c-159">受邀加入会话的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="4ba3c-159">SIP address of the user who was invited to the session.</span></span>  <br/> |
|<span data-ttu-id="4ba3c-160">**会议加入时间（毫秒）**</span><span class="sxs-lookup"><span data-stu-id="4ba3c-160">**Conference join times (ms)**</span></span> <br/> |<span data-ttu-id="4ba3c-161">否</span><span class="sxs-lookup"><span data-stu-id="4ba3c-161">No</span></span>  <br/> |<span data-ttu-id="4ba3c-162">用户加入会议所需的时间量（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="4ba3c-162">Amount of time (in milliseconds) it took for the user to join the conference.</span></span>  <br/> |
|<span data-ttu-id="4ba3c-163">**诊断标头**</span><span class="sxs-lookup"><span data-stu-id="4ba3c-163">**Diagnostic header**</span></span> <br/> |<span data-ttu-id="4ba3c-164">否</span><span class="sxs-lookup"><span data-stu-id="4ba3c-164">No</span></span>  <br/> |<span data-ttu-id="4ba3c-165">诊断 ID 描述</span><span class="sxs-lookup"><span data-stu-id="4ba3c-165">Diagnostic ID description.</span></span>  <br/> |
   
<span data-ttu-id="4ba3c-166">可以在[Ms Diagnostics 标题页面](https://msdn.microsoft.com/en-us/library/gg132446%28v=office.12%29.aspx)上找到诊断错误列表。</span><span class="sxs-lookup"><span data-stu-id="4ba3c-166">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](https://msdn.microsoft.com/en-us/library/gg132446%28v=office.12%29.aspx).</span></span>
  

