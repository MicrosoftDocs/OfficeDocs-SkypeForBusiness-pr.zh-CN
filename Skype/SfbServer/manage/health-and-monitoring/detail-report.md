---
title: Skype for Business Server 中的会议详细信息报告
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
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 摘要：了解 Skype for Business Server 中使用的会议详细信息报告。
ms.openlocfilehash: 245691fcb304a872942be4d5a9aabe8183b4db14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816902"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a><span data-ttu-id="88572-103">Skype for Business Server 中的会议详细信息报告</span><span class="sxs-lookup"><span data-stu-id="88572-103">Conference Detail Report in Skype for Business Server</span></span>

<span data-ttu-id="88572-104">**摘要：** 了解 Skype for Business Server 中使用的会议详细信息报告。</span><span class="sxs-lookup"><span data-stu-id="88572-104">**Summary:** Learn about the Conference Detail Report used in Skype for Business Server.</span></span>

<span data-ttu-id="88572-105">会议详细信息报告提供有关参与会议的所有用户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="88572-105">The Conference Detail Report provides detailed information about all the users who participated in a conference.</span></span> <span data-ttu-id="88572-106">例如，你可以看到诸如用户加入会议的日期和时间、用户离开会议的日期和时间以及用于将该用户连接到会议的终结点的用户代理等信息。</span><span class="sxs-lookup"><span data-stu-id="88572-106">For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference.</span></span> <span data-ttu-id="88572-107">还可以查看用户在每个会议角色中的角色信息， (演示者或与会者) 。</span><span class="sxs-lookup"><span data-stu-id="88572-107">You can also see information the user's role in each conference (for example, Presenter or Attendee).</span></span> <span data-ttu-id="88572-108">也许最重要的是，你可以快速了解哪些用户已成功加入和完成会议，哪些用户未能成功加入和完成会议。</span><span class="sxs-lookup"><span data-stu-id="88572-108">Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="88572-109">访问会议详细信息报告</span><span class="sxs-lookup"><span data-stu-id="88572-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="88572-110">可以从以下报告访问会议详细信息报告：</span><span class="sxs-lookup"><span data-stu-id="88572-110">The Conference Detail Report can be accessed from the following reports:</span></span>

- <span data-ttu-id="88572-111">呼叫 [允许控制报告](call-admission-control-report.md) (会议详细信息指标进行) </span><span class="sxs-lookup"><span data-stu-id="88572-111">The [Call Admission Control Report](call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

- <span data-ttu-id="88572-112">故障 [列表报告](failure-list-report.md) (会议指标) </span><span class="sxs-lookup"><span data-stu-id="88572-112">The [Failure List Report](failure-list-report.md) (by clicking the Conference metric)</span></span>

- <span data-ttu-id="88572-113">用户 [活动报告 (](call-diagnostic-reports-per-user.md) 单击会议 URI 指标) </span><span class="sxs-lookup"><span data-stu-id="88572-113">The [User Activity Report](call-diagnostic-reports-per-user.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="88572-114">从会议详细信息报告中，可以通过单击诊断报告[](diagnostic-report.md) (详细信息) 报告。</span><span class="sxs-lookup"><span data-stu-id="88572-114">From the Conference Detail Report you can access the [Diagnostic Report](diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

## <a name="filters"></a><span data-ttu-id="88572-115">筛选器</span><span class="sxs-lookup"><span data-stu-id="88572-115">Filters</span></span>

<span data-ttu-id="88572-116">无。</span><span class="sxs-lookup"><span data-stu-id="88572-116">None.</span></span> <span data-ttu-id="88572-117">您无法对会议详细信息报告进行筛选。</span><span class="sxs-lookup"><span data-stu-id="88572-117">You cannot filter on the Conference Detail Report.</span></span>

## <a name="metrics"></a><span data-ttu-id="88572-118">指标</span><span class="sxs-lookup"><span data-stu-id="88572-118">Metrics</span></span>

<span data-ttu-id="88572-119">下表列出了会议详细信息报告的"会议信息"部分提供的信息。</span><span class="sxs-lookup"><span data-stu-id="88572-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

<span data-ttu-id="88572-120">**会议信息指标**</span><span class="sxs-lookup"><span data-stu-id="88572-120">**Conference Information Metrics**</span></span>


| <span data-ttu-id="88572-121">**名称**</span><span class="sxs-lookup"><span data-stu-id="88572-121">**Name**</span></span>                 | <span data-ttu-id="88572-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="88572-122">**Description**</span></span>                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="88572-123">**会议 URI**</span><span class="sxs-lookup"><span data-stu-id="88572-123">**Conference URI**</span></span> <br/> | <span data-ttu-id="88572-124">分配给会议的 URI。</span><span class="sxs-lookup"><span data-stu-id="88572-124">URI assigned to the conference.</span></span> <span data-ttu-id="88572-125">例如：</span><span class="sxs-lookup"><span data-stu-id="88572-125">For example:</span></span>  <br/> <span data-ttu-id="88572-126">sip：kmyer@litwareinc.com;gruu;opaque=app：conf：focus：id：drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="88572-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span>  <br/> |
| <span data-ttu-id="88572-127">**池 FQDN**</span><span class="sxs-lookup"><span data-stu-id="88572-127">**Pool FQDN**</span></span> <br/>      | <span data-ttu-id="88572-128">会话中涉及的注册器池或边缘服务器的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="88572-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span>  <br/>                             |
| <span data-ttu-id="88572-129">**开始时间**</span><span class="sxs-lookup"><span data-stu-id="88572-129">**Start time**</span></span> <br/>     | <span data-ttu-id="88572-130">会议开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="88572-130">Date and time that the conference started.</span></span>  <br/>                                                                          |
| <span data-ttu-id="88572-131">**Organizer**</span><span class="sxs-lookup"><span data-stu-id="88572-131">**Organizer**</span></span> <br/>      | <span data-ttu-id="88572-132">组织会议的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="88572-132">SIP address of the user who organized the conference.</span></span>  <br/>                                                               |
| <span data-ttu-id="88572-133">**结束时间**</span><span class="sxs-lookup"><span data-stu-id="88572-133">**End time**</span></span> <br/>       | <span data-ttu-id="88572-134">会议结束的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="88572-134">Date and time that the conference ended.</span></span>  <br/>                                                                            |

<span data-ttu-id="88572-135">下表列出了会议详细信息报告的"会议参与"部分提供的信息。</span><span class="sxs-lookup"><span data-stu-id="88572-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

<span data-ttu-id="88572-136">**会议参与指标**</span><span class="sxs-lookup"><span data-stu-id="88572-136">**Conference Participation Metrics**</span></span>

|<span data-ttu-id="88572-137">**名称**</span><span class="sxs-lookup"><span data-stu-id="88572-137">**Name**</span></span>|<span data-ttu-id="88572-138">**说明**</span><span class="sxs-lookup"><span data-stu-id="88572-138">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="88572-139">"用户"</span><span class="sxs-lookup"><span data-stu-id="88572-139">**User**</span></span> <br/> |<span data-ttu-id="88572-140">参与会议的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="88572-140">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="88572-141">**角色**</span><span class="sxs-lookup"><span data-stu-id="88572-141">**Role**</span></span> <br/> |<span data-ttu-id="88572-142">会议参与者扮演的角色（例如“演示者”）。</span><span class="sxs-lookup"><span data-stu-id="88572-142">Role (for example, Presenter) played by the conference participant.</span></span>  <br/> |
|<span data-ttu-id="88572-143">**连接**</span><span class="sxs-lookup"><span data-stu-id="88572-143">**Connectivity**</span></span> <br/> |<span data-ttu-id="88572-144">参与者的网络连接（通常为“来自内部”或“来自外部”）。</span><span class="sxs-lookup"><span data-stu-id="88572-144">Network connectivity (typically From Internal or From External) for the participant.</span></span>  <br/> |
|<span data-ttu-id="88572-145">**加入时间**</span><span class="sxs-lookup"><span data-stu-id="88572-145">**Join time**</span></span> <br/> |<span data-ttu-id="88572-146">参与者加入会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="88572-146">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="88572-147">**离开时间**</span><span class="sxs-lookup"><span data-stu-id="88572-147">**Leave time**</span></span> <br/> |<span data-ttu-id="88572-148">参与者离开会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="88572-148">Date and time that the participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="88572-149">**用户代理**</span><span class="sxs-lookup"><span data-stu-id="88572-149">**User agent**</span></span> <br/> |<span data-ttu-id="88572-150">参与者终结点使用的软件的标识符。</span><span class="sxs-lookup"><span data-stu-id="88572-150">Identifier for the software used by the participant's endpoint.</span></span>  <br/> |
|<span data-ttu-id="88572-151">**诊断报告**</span><span class="sxs-lookup"><span data-stu-id="88572-151">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="88572-152">提供诊断和疑难解答信息。</span><span class="sxs-lookup"><span data-stu-id="88572-152">Provides diagnostic and troubleshooting information.</span></span> <span data-ttu-id="88572-153">包括 SIP 响应代码、诊断标头、会议加入时间以及失败的会话的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="88572-153">Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |

<span data-ttu-id="88572-154">下表列出了会议详细信息报告的"会议形式"部分提供的信息。</span><span class="sxs-lookup"><span data-stu-id="88572-154">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

<span data-ttu-id="88572-155">**会议形式指标**</span><span class="sxs-lookup"><span data-stu-id="88572-155">**Conference Modalities Metrics**</span></span>

|<span data-ttu-id="88572-156">**名称**</span><span class="sxs-lookup"><span data-stu-id="88572-156">**Name**</span></span>|<span data-ttu-id="88572-157">**说明**</span><span class="sxs-lookup"><span data-stu-id="88572-157">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="88572-158">"用户"</span><span class="sxs-lookup"><span data-stu-id="88572-158">**User**</span></span> <br/> |<span data-ttu-id="88572-159">参与会议的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="88572-159">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="88572-160">**加入时间**</span><span class="sxs-lookup"><span data-stu-id="88572-160">**Join time**</span></span> <br/> |<span data-ttu-id="88572-161">参与者加入会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="88572-161">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="88572-162">**离开时间**</span><span class="sxs-lookup"><span data-stu-id="88572-162">**Leave time**</span></span> <br/> |<span data-ttu-id="88572-163">参与者离开会议的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="88572-163">Date and time that a participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="88572-164">**会议服务器 URI**</span><span class="sxs-lookup"><span data-stu-id="88572-164">**Conferencing server URI**</span></span> <br/> |<span data-ttu-id="88572-165">会议中使用的会议服务器的 URI。</span><span class="sxs-lookup"><span data-stu-id="88572-165">URI for the Conferencing server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="88572-166">**诊断报告**</span><span class="sxs-lookup"><span data-stu-id="88572-166">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="88572-167">提供诊断和疑难解答信息。</span><span class="sxs-lookup"><span data-stu-id="88572-167">Provides diagnostic and troubleshooting information.</span></span> <span data-ttu-id="88572-168">包括 SIP 响应代码、诊断标头、会议加入时间以及失败的会话的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="88572-168">Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |


