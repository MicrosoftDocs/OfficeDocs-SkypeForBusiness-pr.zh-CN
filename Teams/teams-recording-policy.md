---
title: 有关呼叫 & 会议的基于团队策略的录制简介
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: 了解用于呼叫 & 会议的基于团队策略的录制
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 61fbce79fc528f4b69baed9c08a8dabc9d40ed4a
ms.sourcegitcommit: 76fc38fe1fbbd93bf2815c57e66fc479df34d929
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002194"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a><span data-ttu-id="f703a-103">Callings & 会议的基于团队政策的录制简介</span><span class="sxs-lookup"><span data-stu-id="f703a-103">Introduction to Teams policy-based recording for callings & meetings</span></span>

<span data-ttu-id="f703a-104">基于策略的录制使 Microsoft 团队可以通过管理策略自动记录和捕获针对后续处理和保留（如相关的公司或规章策略所需）进行呼叫和会议的适用于 stipulate 的 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="f703a-104">Policy-based recording enables organizations that adopt Microsoft Teams for calling and meetings to stipulate, using an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span>

<span data-ttu-id="f703a-105">团队已得到改进，可支持第三方录制解决方案的集成，包括平台功能、用户体验和管理界面，以便为配置、管理、记录、存储和分析团队通信提供端到端的解决方案所需。</span><span class="sxs-lookup"><span data-stu-id="f703a-105">Teams has been enhanced to support integration of third-party recording solutions, including the platform functionality, user experiences, and administrative interfaces needed to provide an end-to-end solution for configuring, managing, recording, storing, and analyzing Teams communications.</span></span> <span data-ttu-id="f703a-106">这包括用于录制的通信平台 Api 和事件，其中提供：</span><span class="sxs-lookup"><span data-stu-id="f703a-106">This includes communications platform APIs and events for recording, which provides:</span></span>

- <span data-ttu-id="f703a-107">跨设备的无缝、高质量媒体捕获和音频、视频、屏幕共享和聊天的所有受支持的终结点。</span><span class="sxs-lookup"><span data-stu-id="f703a-107">Seamless, high-quality media capture across devices and all   supported endpoints for audio, video, screen share, and chat.</span></span>

- <span data-ttu-id="f703a-108">支持团队用户和支持的呼叫终结点之间的交互捕获 (团队、团队移动、Skype for business、PSTN) </span><span class="sxs-lookup"><span data-stu-id="f703a-108">Support for interaction capture between Teams users and supported   calling endpoints (Teams, Teams Mobile, Skype for Business, PSTN)</span></span>

- <span data-ttu-id="f703a-109">针对合规性录制的新管理策略，包括与现有团队的集成管理呼叫和会议工具和策略</span><span class="sxs-lookup"><span data-stu-id="f703a-109">New administrative policies for compliance recording, including   integration with existing Teams administrative calling and   meeting tools and policies</span></span>

<span data-ttu-id="f703a-110">合规性录制可在 Microsoft 365 A3/A5/E3/E5/Business Premium 和 Office 365 A3/A5/E3 用户上启用。</span><span class="sxs-lookup"><span data-stu-id="f703a-110">Compliance Recording can be enabled on Microsoft 365 A3/A5/E3/E5/Business Premium and Office 365 A3/A5/E3/E5 users.</span></span> 

<span data-ttu-id="f703a-111">合规性录制解决方案集成功能还在 [<span class="underline">合规性录制和 Microsoft 团队会话</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions)的 Ignite 2019 中查看。</span><span class="sxs-lookup"><span data-stu-id="f703a-111">The compliance recording solution integration capabilities were also reviewed at Ignite 2019 in the [<span class="underline">Compliance Recording and Microsoft Teams session</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).</span></span>

## <a name="teams-interaction-recording-overview"></a><span data-ttu-id="f703a-112">团队交互录制概述</span><span class="sxs-lookup"><span data-stu-id="f703a-112">Teams interaction recording overview</span></span>

<span data-ttu-id="f703a-113">交互录制使用案例可以有效地分成四种主要类别的录制功能-方便、功能、组织和合法截取，如图所示：</span><span class="sxs-lookup"><span data-stu-id="f703a-113">Interaction recording use cases can effectively be separated into four primary categories of recording functionality – Convenience, Functional, Organizational, and Lawful Intercept, as shown in the image:</span></span>

<span data-ttu-id="f703a-114">![显示交互录制内容和原因的屏幕截图。](media/recording-taxonomy.png "图像显示 "录制" 类别。")</span><span class="sxs-lookup"><span data-stu-id="f703a-114">![Screenshot showing the interaction recording what and why.](media/recording-taxonomy.png "The image shows the recording categories.")</span></span>

<span data-ttu-id="f703a-115">每个类别都需要对启动录制的方式有不同的要求、录制的内容、录制的位置、通知的人员、控制访问的人员以及如何处理保留。</span><span class="sxs-lookup"><span data-stu-id="f703a-115">Each of the categories entails different requirements for how recordings are initiated, what is recorded, where recordings are stored, who is notified, who controls access, and how retention is handled.</span></span>

| <span data-ttu-id="f703a-116">类型</span><span class="sxs-lookup"><span data-stu-id="f703a-116">Type</span></span>                   | <span data-ttu-id="f703a-117">参考</span><span class="sxs-lookup"><span data-stu-id="f703a-117">Convenience</span></span>        | <span data-ttu-id="f703a-118">功能</span><span class="sxs-lookup"><span data-stu-id="f703a-118">Functional</span></span>         | <span data-ttu-id="f703a-119">组织-常规</span><span class="sxs-lookup"><span data-stu-id="f703a-119">Org - General</span></span>      | <span data-ttu-id="f703a-120">组织级管控</span><span class="sxs-lookup"><span data-stu-id="f703a-120">Org - Regulated</span></span> | <span data-ttu-id="f703a-121">合法截距</span><span class="sxs-lookup"><span data-stu-id="f703a-121">Lawful Intercept</span></span>   |
| ---------------------- | ------------------ | ------------------ | ------------------ | --------------- | ------------------ |
| <span data-ttu-id="f703a-122">启动</span><span class="sxs-lookup"><span data-stu-id="f703a-122">Initiator</span></span>              | <span data-ttu-id="f703a-123">用户</span><span class="sxs-lookup"><span data-stu-id="f703a-123">User</span></span>               | <span data-ttu-id="f703a-124">应用/解决方案</span><span class="sxs-lookup"><span data-stu-id="f703a-124">App/Solution</span></span>       | <span data-ttu-id="f703a-125">管理员 (系统) </span><span class="sxs-lookup"><span data-stu-id="f703a-125">Admin (system)</span></span>     | <span data-ttu-id="f703a-126">管理员 (系统) </span><span class="sxs-lookup"><span data-stu-id="f703a-126">Admin (system)</span></span>  | <span data-ttu-id="f703a-127">LEA</span><span class="sxs-lookup"><span data-stu-id="f703a-127">LEA</span></span>                |
| <span data-ttu-id="f703a-128">目标</span><span class="sxs-lookup"><span data-stu-id="f703a-128">Target</span></span>                 | <span data-ttu-id="f703a-129">每次通话/会议</span><span class="sxs-lookup"><span data-stu-id="f703a-129">Per-call / meeting</span></span> | <span data-ttu-id="f703a-130">每次通话/会议</span><span class="sxs-lookup"><span data-stu-id="f703a-130">Per-call / meeting</span></span> | <span data-ttu-id="f703a-131">每次通话/会议</span><span class="sxs-lookup"><span data-stu-id="f703a-131">Per-call / meeting</span></span> | <span data-ttu-id="f703a-132">每用户</span><span class="sxs-lookup"><span data-stu-id="f703a-132">Per-user</span></span>        | <span data-ttu-id="f703a-133">每个终结点/已完成</span><span class="sxs-lookup"><span data-stu-id="f703a-133">Per-endpoint / DID</span></span> |
| <span data-ttu-id="f703a-134">存储所有者</span><span class="sxs-lookup"><span data-stu-id="f703a-134">Storage owner</span></span>          | <span data-ttu-id="f703a-135">用户</span><span class="sxs-lookup"><span data-stu-id="f703a-135">User</span></span>               | <span data-ttu-id="f703a-136">应用</span><span class="sxs-lookup"><span data-stu-id="f703a-136">App</span></span>                | <span data-ttu-id="f703a-137">Iis</span><span class="sxs-lookup"><span data-stu-id="f703a-137">Admin</span></span>              | <span data-ttu-id="f703a-138">合规性</span><span class="sxs-lookup"><span data-stu-id="f703a-138">Compliance</span></span>      | <span data-ttu-id="f703a-139">LEA</span><span class="sxs-lookup"><span data-stu-id="f703a-139">LEA</span></span>                |
| <span data-ttu-id="f703a-140">需要通知？</span><span class="sxs-lookup"><span data-stu-id="f703a-140">Notification required?</span></span> | <span data-ttu-id="f703a-141">是</span><span class="sxs-lookup"><span data-stu-id="f703a-141">Yes</span></span>                | <span data-ttu-id="f703a-142">是</span><span class="sxs-lookup"><span data-stu-id="f703a-142">Yes</span></span>                | <span data-ttu-id="f703a-143">是</span><span class="sxs-lookup"><span data-stu-id="f703a-143">Yes</span></span>                | <span data-ttu-id="f703a-144">是</span><span class="sxs-lookup"><span data-stu-id="f703a-144">Yes</span></span>             | <span data-ttu-id="f703a-145">否</span><span class="sxs-lookup"><span data-stu-id="f703a-145">No</span></span>                 |
| <span data-ttu-id="f703a-146">访问所有者</span><span class="sxs-lookup"><span data-stu-id="f703a-146">Access Owner</span></span>           | <span data-ttu-id="f703a-147">用户</span><span class="sxs-lookup"><span data-stu-id="f703a-147">User</span></span>               | <span data-ttu-id="f703a-148">应用</span><span class="sxs-lookup"><span data-stu-id="f703a-148">App</span></span>                | <span data-ttu-id="f703a-149">Iis</span><span class="sxs-lookup"><span data-stu-id="f703a-149">Admin</span></span>              | <span data-ttu-id="f703a-150">合规性</span><span class="sxs-lookup"><span data-stu-id="f703a-150">Compliance</span></span>      | <span data-ttu-id="f703a-151">LEA</span><span class="sxs-lookup"><span data-stu-id="f703a-151">LEA</span></span>                |
| <span data-ttu-id="f703a-152">保留策略？</span><span class="sxs-lookup"><span data-stu-id="f703a-152">Retention Policy?</span></span>      | <span data-ttu-id="f703a-153">可选</span><span class="sxs-lookup"><span data-stu-id="f703a-153">Optional</span></span>           | <span data-ttu-id="f703a-154">是</span><span class="sxs-lookup"><span data-stu-id="f703a-154">Yes</span></span>                | <span data-ttu-id="f703a-155">是</span><span class="sxs-lookup"><span data-stu-id="f703a-155">Yes</span></span>                | <span data-ttu-id="f703a-156">是</span><span class="sxs-lookup"><span data-stu-id="f703a-156">Yes</span></span>             | <span data-ttu-id="f703a-157">是</span><span class="sxs-lookup"><span data-stu-id="f703a-157">Yes</span></span>                |

<span data-ttu-id="f703a-158">团队提供各种功能，用于会议和实时事件的 [<span class="underline">便利</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) 和功能录制。</span><span class="sxs-lookup"><span data-stu-id="f703a-158">Teams provides various capabilities for [<span class="underline">convenient</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) and functional recording for meetings and live events.</span></span> <span data-ttu-id="f703a-159">组织录制意味着，当应根据相关的公司或规章策略的要求自动记录和捕获在后续处理和保留期间进行的呼叫和会议时，通过管理策略将使用团队进行呼叫和会议的组织 stipulate。</span><span class="sxs-lookup"><span data-stu-id="f703a-159">Organizational recording means enabling organizations adopting Teams for calling and meetings to stipulate, by way of an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span> <span data-ttu-id="f703a-160">此策略下的用户将知道他们正在录制与团队的数字交互，但不能禁用录制，并且在交互完成后将无法访问录制。</span><span class="sxs-lookup"><span data-stu-id="f703a-160">Users under this policy will be aware that their digital interactions with Teams are being recorded but will not be able to disable the recording and will not have access to the recording once the interaction is complete.</span></span> <span data-ttu-id="f703a-161">在电子数据展示、法律封存和其他公司保留使用中，该记录将成为组织存档的一部分，以供合规性和法律人员使用。</span><span class="sxs-lookup"><span data-stu-id="f703a-161">The recording becomes part of the organizational archive available to compliance and legal personnel for eDiscovery, legal hold, and other corporate retention uses.</span></span>

## <a name="example-user-needs"></a><span data-ttu-id="f703a-162">用户需求示例</span><span class="sxs-lookup"><span data-stu-id="f703a-162">Example user needs</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="f703a-163"><strong>角色</strong></span><span class="sxs-lookup"><span data-stu-id="f703a-163"><strong>Persona</strong></span></span></th>
<th><span data-ttu-id="f703a-164"><strong>需要</strong></span><span class="sxs-lookup"><span data-stu-id="f703a-164"><strong>Needs</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f703a-165">录制的用户</span><span class="sxs-lookup"><span data-stu-id="f703a-165">Recorded users</span></span></td>
<td><ul>
<li><p><span data-ttu-id="f703a-166">正在进行录制时收到通知。</span><span class="sxs-lookup"><span data-stu-id="f703a-166">Be notified when recording is in progress.</span></span></p></li>
<li><p><span data-ttu-id="f703a-167">当策略和/或记录器错误导致调用行为发生更改时收到通知。</span><span class="sxs-lookup"><span data-stu-id="f703a-167">Be informed when policy and/or recorder error is causing changes in calling behavior.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f703a-168">通信管理员</span><span class="sxs-lookup"><span data-stu-id="f703a-168">Communications admin</span></span></td>
<td><ul>
<li><p><span data-ttu-id="f703a-169">了解为什么以及如何向团队用户/终结点应用/强制录制策略。</span><span class="sxs-lookup"><span data-stu-id="f703a-169">Understand why and how to apply / enforce recording policies to Teams users / endpoints.</span></span></p></li>
<li><p><span data-ttu-id="f703a-170">配置和维护组织的团队记录策略。</span><span class="sxs-lookup"><span data-stu-id="f703a-170">Configure and maintain Teams recording policies for the organization.</span></span></p></li>
<li><p><span data-ttu-id="f703a-171">监控和解决团队通话和会议与录制相关的问题。</span><span class="sxs-lookup"><span data-stu-id="f703a-171">Monitor and troubleshoot recording-related issues with Teams calls and meetings.</span></span></p></li>
<li><p><span data-ttu-id="f703a-172">针对使用情况、质量和可靠性，支持内部合规性监察官和运营分析。</span><span class="sxs-lookup"><span data-stu-id="f703a-172">Support internal compliance officer with operational analytics on usage, quality, and reliability.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f703a-173">合规性监察官</span><span class="sxs-lookup"><span data-stu-id="f703a-173">Compliance officer</span></span></td>
<td><ul>
<li><p><span data-ttu-id="f703a-174">按所需方式收集所有团队通信，以满足适当区域边界的合规性义务。</span><span class="sxs-lookup"><span data-stu-id="f703a-174">Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.</span></span></p></li>
<li><p><span data-ttu-id="f703a-175">根据与通信相关的元数据或交互内容搜索交互。</span><span class="sxs-lookup"><span data-stu-id="f703a-175">Search for interactions based on communication-related metadata or interaction content.</span></span> <span data-ttu-id="f703a-176">常见示例包括：</span><span class="sxs-lookup"><span data-stu-id="f703a-176">Common examples include:</span></span></p>
<ul>
<li><p><span data-ttu-id="f703a-177"><strong>元数据</strong> - 参与者、时间、方向、已拨号码、原始电话号码、自定义业务数据</span><span class="sxs-lookup"><span data-stu-id="f703a-177"><strong>Metadata</strong> - Participants, time, direction, dialed number, origin number, Custom business data</span></span></p></li>
<li><p><span data-ttu-id="f703a-178"><strong>内容</strong> -脚本、情绪、拼音、相关交互</span><span class="sxs-lookup"><span data-stu-id="f703a-178"><strong>Content</strong> – Transcription, sentiment, phonetics, related interactions</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="f703a-179">分析并与收集的通信进行交互，包括在收集交互时监视交互的能力。</span><span class="sxs-lookup"><span data-stu-id="f703a-179">Analyze and interact with collected communications, including the ability to monitor interactions as they are being collected.</span></span></p></li>
<li><p><span data-ttu-id="f703a-180">确保收集的通信的安全性，并防止所有阶段被篡改。</span><span class="sxs-lookup"><span data-stu-id="f703a-180">Ensure security of collected communications and prevent tampering at all stages.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a><span data-ttu-id="f703a-181">解决方案体系结构概述</span><span class="sxs-lookup"><span data-stu-id="f703a-181">Solution architecture overview</span></span>

<span data-ttu-id="f703a-182">合规性录制解决方案与团队集成，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="f703a-182">Compliance recording solutions are integrated with Teams as shown in the following diagram:</span></span>

<span data-ttu-id="f703a-183">![显示团队自定义应用设置的屏幕截图](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "图像显示发送和接收团队会议或通话时的流程。")</span><span class="sxs-lookup"><span data-stu-id="f703a-183">![Screenshot showing the team custom app setting](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "The images shows the flow when a Teams meeting or call is sent and received.")</span></span>

## <a name="recorder"></a><span data-ttu-id="f703a-184">盘</span><span class="sxs-lookup"><span data-stu-id="f703a-184">Recorder</span></span>

<span data-ttu-id="f703a-185">合规性录制解决方案的核心组件是录像机。</span><span class="sxs-lookup"><span data-stu-id="f703a-185">The core component of the compliance recording solution is the recorder.</span></span>
<span data-ttu-id="f703a-186">录音机是以可伸缩的基于 Azure 的服务构建的， (机器人) [<span class="underline">利用 microsoft 的通信平台</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) ，并使用 microsoft Graph 注册为应用程序。</span><span class="sxs-lookup"><span data-stu-id="f703a-186">Recorders are built as scalable Azure-based services (bots) that [<span class="underline">leverage Microsoft’s communications platform</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) and register as applications with Microsoft Graph.</span></span> <span data-ttu-id="f703a-187">记录器提供与团队通话和会议 [<span class="underline">通信平台 api</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) 的直接交互，并提供媒体接收的终结点。</span><span class="sxs-lookup"><span data-stu-id="f703a-187">The recorder provides the direct interaction with the Teams calls and meetings [<span class="underline">communications platform APIs</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and provides the endpoint for media ingestion.</span></span>

<span data-ttu-id="f703a-188">提供了一个 [<span class="underline">示例合规性记录器应用程序，该应用程序</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) 显示如何配置 bot、创建应用实例并分配合规性策略。</span><span class="sxs-lookup"><span data-stu-id="f703a-188">A [<span class="underline">sample compliance recorder application is available</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) that shows how to configure the bot, create the app instance and assign the compliance policies.</span></span> <span data-ttu-id="f703a-189">该示例还包含用于录制特定交互（如处理 [<span class="underline">传入呼叫</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) 路由、 [<span class="underline">更改录制状态</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)和 [<span class="underline">删除正在录制的用户</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)）的 API 用法的示例。</span><span class="sxs-lookup"><span data-stu-id="f703a-189">The sample also has examples on API usage for recording specific interactions such as handling [<span class="underline">incoming call</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) routing, [<span class="underline">changing recording states</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), and [<span class="underline">removing the user who is being recorded</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span></span>
<span data-ttu-id="f703a-190">有关 [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) 和 [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0)，可在此处找到有关特定 api 的图形文档。</span><span class="sxs-lookup"><span data-stu-id="f703a-190">Graph documentation on the specific APIs can be found here for [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) and [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span></span>

<span data-ttu-id="f703a-191">记录器服务的确切实现因合作伙伴而异，但必须设计为支持多个刻录机才能实现高可用性和部署的地理位置分布，以减少团队与记录器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="f703a-191">The exact implementation of the recorder service will vary by partner but must be designed to support multiple recorders in order to achieve high availability and geographical distribution of deployment to reduce latency from Teams to the recorder.</span></span> <span data-ttu-id="f703a-192">此外，该刻录机自身的设计应考虑恢复性和冗余。</span><span class="sxs-lookup"><span data-stu-id="f703a-192">In addition, it is expected that Recorders themselves be designed with resiliency and redundancy in mind.</span></span>

<span data-ttu-id="f703a-193">合作伙伴必须先确认 Microsoft Graph 通信 Api 和 Sdk 的最低版本，然后再提交其认证解决方案，以确保符合性录制集成的所有要求均受支持。</span><span class="sxs-lookup"><span data-stu-id="f703a-193">Partners must confirm the minimum required release version of the Microsoft Graph communications APIs and SDKs with Microsoft before submitting their solution for certification to ensure that all requirements of compliance recording integration are supported.</span></span>

<span data-ttu-id="f703a-194">符合性录制方案的基本要求有两个特定要求：</span><span class="sxs-lookup"><span data-stu-id="f703a-194">Two specific requirements that are fundamental for compliance recording scenario are:</span></span>

- <span data-ttu-id="f703a-195">录像机 bot 必须部署在 Azure 中</span><span class="sxs-lookup"><span data-stu-id="f703a-195">Recorder bot must be deployed in Azure</span></span>

- <span data-ttu-id="f703a-196">录像机 bot 必须在 Azure 中的 Windows VM 上运行</span><span class="sxs-lookup"><span data-stu-id="f703a-196">Recorder bot must run on a Windows VM in Azure</span></span>

<span data-ttu-id="f703a-197">Azure 和 Windows VM 要求仅适用于 "团队 Bot" 组件，这意味着合作伙伴可以实现其选择的其余平台，前提是它们可以满足符合性录制的相关性能和功能要求。</span><span class="sxs-lookup"><span data-stu-id="f703a-197">The Azure and Windows VM requirements only apply to the Teams Bot component, which means that a partner may implement the rest of the platform of their choice provided they can meet the relevant performance and functional requirements for compliance recording.</span></span>

## <a name="compliance-recording-policy-assignment-and-provisioning"></a><span data-ttu-id="f703a-198">合规性录制策略分配和预配</span><span class="sxs-lookup"><span data-stu-id="f703a-198">Compliance recording policy assignment and provisioning</span></span>

<span data-ttu-id="f703a-199">IT 管理员可以通过创建和分配合规性录制策略来确定要录制的用户以及将用于每个用户的记录器。</span><span class="sxs-lookup"><span data-stu-id="f703a-199">IT Administrators can determine which users are to be recorded and which recorder will be used for each user, by creating and assigning compliance recording policies.</span></span> <span data-ttu-id="f703a-200">在通信交互发生时，会根据这些策略的配置自动邀请刻录机参与对话。</span><span class="sxs-lookup"><span data-stu-id="f703a-200">Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.</span></span> <span data-ttu-id="f703a-201">合规性录制策略使用 [<span class="underline">Microsoft Powershell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) 进行管理，并且可应用于每个组织的租户、每用户和安全组级别。</span><span class="sxs-lookup"><span data-stu-id="f703a-201">Compliance recording policies are managed using [<span class="underline">Microsoft Powershell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) and can be applied at the tenant, per-user, and security group level for each organization.</span></span> <span data-ttu-id="f703a-202">你可以在 Microsoft 文档中查找有关 [<span class="underline">会议策略</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams)、 [<span class="underline">呼叫策略</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) 和  [<span class="underline">组策略</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f703a-202">You can find more information on Microsoft Docs for [<span class="underline">Meeting policies</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams), [<span class="underline">calling policies</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) and  [<span class="underline">group policies</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group).</span></span>

1. <span data-ttu-id="f703a-203">在租户中创建应用程序实例。</span><span class="sxs-lookup"><span data-stu-id="f703a-203">Create an application instance in your tenant.</span></span>

   ```powershell
   PS C:\> New-CsOnlineApplicationInstance -UserPrincipalName cr.instance@contoso.onmicrosoft.com -DisplayName ComplianceRecordingBotInstance -ApplicationId fcc88ff5-a42d-49cf-b3d8-f2e1f609d511

   RunspaceId        : 4c13efa6-77bc-42db-b5bf-bdd62cdfc5df
   ObjectId          : 5069aae5-c451-4983-9e57-9455ced220b7
   TenantId          : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   UserPrincipalName : cr.instance@contoso.onmicrosoft.com
   ApplicationId     : fcc88ff5-a42d-49cf-b3d8-f2e1f609d511
   DisplayName       : ComplianceRecordingBotInstance
   PhoneNumber       :
   ```

   ```powershell
   PS C:\> Sync-CsOnlineApplicationInstance -ObjectId 5069aae5-c451-4983-9e57-9455ced220b7
   ```

2. <span data-ttu-id="f703a-204">创建合规性录制策略。</span><span class="sxs-lookup"><span data-stu-id="f703a-204">Create a Compliance Recording policy.</span></span>

   ```powershell
   PS C:\> New-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy -Enabled $true -Description "Test policy created by tenant admin"

   Identity                        : Global
   ComplianceRecordingApplications : {}
   Enabled                         : True
   WarnUserOnRemoval               : True
   Description                     : Test policy created by tenant admin
   ```

   ```powershell
   PS C:\> Set-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy `
   -ComplianceRecordingApplications @(New-CsTeamsComplianceRecordingApplication -Id 5069aae5-c451-4983-9e57-9455ced220b7 -Parent TestComplianceRecordingPolicy)
   ```

   [<span data-ttu-id="f703a-205"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="f703a-205"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. <span data-ttu-id="f703a-206">将合规性录制策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="f703a-206">Assign the Compliance Recording policy to a user.</span></span>

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span data-ttu-id="f703a-207"><span class="underline">授权-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="f703a-207"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a><span data-ttu-id="f703a-208">用户体验</span><span class="sxs-lookup"><span data-stu-id="f703a-208">User experiences</span></span>

<span data-ttu-id="f703a-209">使用团队客户体验启用通知支持。</span><span class="sxs-lookup"><span data-stu-id="f703a-209">Support for notifications is enabled using the Teams client experiences.</span></span> <span data-ttu-id="f703a-210">体验可以是视觉的，也可以是音频。</span><span class="sxs-lookup"><span data-stu-id="f703a-210">The experiences can be either visual or audio.</span></span>

<span data-ttu-id="f703a-211">**团队客户端-视觉通知**</span><span class="sxs-lookup"><span data-stu-id="f703a-211">**Teams clients - visual notice**</span></span>
- <span data-ttu-id="f703a-212">桌面/web</span><span class="sxs-lookup"><span data-stu-id="f703a-212">Desktop/web</span></span>
- <span data-ttu-id="f703a-213">Mobile (iOS/Android) </span><span class="sxs-lookup"><span data-stu-id="f703a-213">Mobile (iOS/Android)</span></span>
- <span data-ttu-id="f703a-214">团队手机</span><span class="sxs-lookup"><span data-stu-id="f703a-214">Teams phones</span></span>
- <span data-ttu-id="f703a-215">团队聊天室</span><span class="sxs-lookup"><span data-stu-id="f703a-215">Teams rooms</span></span>

<span data-ttu-id="f703a-216">**其他终结点-音频通知**</span><span class="sxs-lookup"><span data-stu-id="f703a-216">**Other endpoints - audio notice**</span></span>
- <span data-ttu-id="f703a-217">SIP 电话</span><span class="sxs-lookup"><span data-stu-id="f703a-217">SIP phones</span></span>
- <span data-ttu-id="f703a-218">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f703a-218">Skype for Business</span></span>
- <span data-ttu-id="f703a-219">音频会议</span><span class="sxs-lookup"><span data-stu-id="f703a-219">Audio conferencing</span></span>
- <span data-ttu-id="f703a-220">PSTN 呼叫者</span><span class="sxs-lookup"><span data-stu-id="f703a-220">PSTN callers</span></span>

## <a name="compliance-recording-for-teams-certification-programs"></a><span data-ttu-id="f703a-221">团队认证计划的合规性录制</span><span class="sxs-lookup"><span data-stu-id="f703a-221">Compliance recording for Teams certification programs</span></span>

<span data-ttu-id="f703a-222">除了发布可供合作伙伴开发和集成 CCaaS 解决方案的公共 Api 之外，我们还制定了 Microsoft 团队认证计划的合规性录制，以确保每个参与合作伙伴的解决方案都经过测试和验证，以提供他们所期望的各种 Microsoft 解决方案的质量、兼容性和可靠性。</span><span class="sxs-lookup"><span data-stu-id="f703a-222">In addition to publishing publicly-available APIs allowing partners to develop and integrate CCaaS solutions with Teams, we have developed the compliance recording for Microsoft Teams certification program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>  

<span data-ttu-id="f703a-223">以下合作伙伴已验证其 Microsoft 团队的解决方案。</span><span class="sxs-lookup"><span data-stu-id="f703a-223">The following partners have certified their solution for Microsoft Teams.</span></span>

|<span data-ttu-id="f703a-224">配偶</span><span class="sxs-lookup"><span data-stu-id="f703a-224">Partner</span></span>|<span data-ttu-id="f703a-225">解决方案网站</span><span class="sxs-lookup"><span data-stu-id="f703a-225">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="f703a-226">良好</span><span class="sxs-lookup"><span data-stu-id="f703a-226">NICE</span></span> |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |


<span data-ttu-id="f703a-227">以下合作伙伴正在验证其 Microsoft 团队解决方案的过程。</span><span class="sxs-lookup"><span data-stu-id="f703a-227">The following partners are in the process of certifying their solution for Microsoft Teams.</span></span>

|<span data-ttu-id="f703a-228">配偶</span><span class="sxs-lookup"><span data-stu-id="f703a-228">Partner</span></span>|<span data-ttu-id="f703a-229">解决方案网站</span><span class="sxs-lookup"><span data-stu-id="f703a-229">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="f703a-230">ASC 技术</span><span class="sxs-lookup"><span data-stu-id="f703a-230">ASC Technologies</span></span> |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|<span data-ttu-id="f703a-231">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="f703a-231">AudioCodes</span></span> |[https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording) |
|<span data-ttu-id="f703a-232">CallCabinet</span><span class="sxs-lookup"><span data-stu-id="f703a-232">CallCabinet</span></span> |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|<span data-ttu-id="f703a-233">Dubber</span><span class="sxs-lookup"><span data-stu-id="f703a-233">Dubber</span></span> |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|<span data-ttu-id="f703a-234">Landis 技术</span><span class="sxs-lookup"><span data-stu-id="f703a-234">Landis Technologies</span></span> |[https://landistechnologies.com/](https://landistechnologies.com/) |
|<span data-ttu-id="f703a-235">Luware</span><span class="sxs-lookup"><span data-stu-id="f703a-235">Luware</span></span> |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|<span data-ttu-id="f703a-236">Numonix</span><span class="sxs-lookup"><span data-stu-id="f703a-236">Numonix</span></span> |[https://numonix.cloud](https://numonix.cloud)    |
|<span data-ttu-id="f703a-237">橡木创新</span><span class="sxs-lookup"><span data-stu-id="f703a-237">Oak Innovation</span></span> |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|<span data-ttu-id="f703a-238">红色框</span><span class="sxs-lookup"><span data-stu-id="f703a-238">Red Box</span></span> |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|<span data-ttu-id="f703a-239">Verint</span><span class="sxs-lookup"><span data-stu-id="f703a-239">Verint</span></span> |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

<span data-ttu-id="f703a-240">此列表将随着更多合作伙伴加入和满足认证标准而更新。</span><span class="sxs-lookup"><span data-stu-id="f703a-240">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f703a-241">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f703a-241">Next steps</span></span>

<span data-ttu-id="f703a-242">如果您是希望加入认证计划的供应商，请邮寄  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>。</span><span class="sxs-lookup"><span data-stu-id="f703a-242">If you are a vendor seeking to join the certification program, please mail  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span></span>
