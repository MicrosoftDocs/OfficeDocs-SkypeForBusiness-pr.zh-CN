---
title: 有关Teams会议呼叫的基于策略的录制&简介
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
description: 了解Teams会议呼叫的基于策略&录制
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
ms.openlocfilehash: df8a0f5b33bbea100b0303d224d7ba50946c6e5b
ms.sourcegitcommit: 56bebf42f545af57fdf387faa90e555abc8acd40
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/18/2021
ms.locfileid: "52513875"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a><span data-ttu-id="3c5d3-103">有关Teams会议呼叫的基于策略的录制&简介</span><span class="sxs-lookup"><span data-stu-id="3c5d3-103">Introduction to Teams policy-based recording for callings & meetings</span></span>

<span data-ttu-id="3c5d3-104">基于策略的记录使采用 Microsoft Teams 进行呼叫和会议的组织能够规定，当应按照相关公司或法规策略的要求自动记录和捕获呼叫和联机会议以用于后续处理和保留时，使用管理策略。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-104">Policy-based recording enables organizations that adopt Microsoft Teams for calling and meetings to stipulate, using an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span>

<span data-ttu-id="3c5d3-105">Teams已增强，以支持第三方录制解决方案的集成，包括提供端到端解决方案（用于配置、管理、录制、存储和分析 Teams 通信）所需的平台功能、用户体验和管理界面。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-105">Teams has been enhanced to support integration of third-party recording solutions, including the platform functionality, user experiences, and administrative interfaces needed to provide an end-to-end solution for configuring, managing, recording, storing, and analyzing Teams communications.</span></span> <span data-ttu-id="3c5d3-106">增强功能包括通信平台 API 和用于录制的事件，它们提供：</span><span class="sxs-lookup"><span data-stu-id="3c5d3-106">Enhancements include communications platform APIs and events for recording, which provides:</span></span>

- <span data-ttu-id="3c5d3-107">跨设备和所有受支持的终结点无缝、高质量的媒体捕获，用于音频、视频、屏幕共享和聊天。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-107">Seamless, high-quality media capture across devices and all   supported endpoints for audio, video, screen share, and chat.</span></span>

- <span data-ttu-id="3c5d3-108">支持在 Teams 用户与受支持的呼叫终结点 (Teams、Teams Mobile、Skype for Business、PSTN) </span><span class="sxs-lookup"><span data-stu-id="3c5d3-108">Support for interaction capture between Teams users and supported   calling endpoints (Teams, Teams Mobile, Skype for Business, PSTN)</span></span>

- <span data-ttu-id="3c5d3-109">用于合规性记录的新管理策略，包括与现有的Teams呼叫和会议工具和策略的集成</span><span class="sxs-lookup"><span data-stu-id="3c5d3-109">New administrative policies for compliance recording, including   integration with existing Teams administrative calling and   meeting tools and policies</span></span>

<span data-ttu-id="3c5d3-110">可以在 Microsoft 365 A3/A5/E3/E5/Business 高级版 和 Office 365 A3/A5/E3/E5 用户上启用合规性记录。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-110">Compliance Recording can be enabled on Microsoft 365 A3/A5/E3/E5/Business Premium and Office 365 A3/A5/E3/E5 users.</span></span> 

<span data-ttu-id="3c5d3-111">合规性记录解决方案集成功能也在 Ignite 2019 的合规性记录和Microsoft Teams[评审](https://myignite.microsoft.com/archives/IG19-VCE40)。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-111">The compliance recording solution integration capabilities were also reviewed at Ignite 2019 in the [Compliance Recording and Microsoft Teams session](https://myignite.microsoft.com/archives/IG19-VCE40).</span></span>

## <a name="teams-interaction-recording-overview"></a><span data-ttu-id="3c5d3-112">Teams交互录制概述</span><span class="sxs-lookup"><span data-stu-id="3c5d3-112">Teams interaction recording overview</span></span>

<span data-ttu-id="3c5d3-113">交互录制用例可以有效地分为四个主要类别的录制功能 – 便利、功能、组织和合法拦截，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="3c5d3-113">Interaction recording use cases can effectively be separated into four primary categories of recording functionality – Convenience, Functional, Organizational, and Lawful Intercept, as shown in the image:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3c5d3-114">![显示交互录制内容以及原因的屏幕截图。](media/recording-taxonomy.png "图像显示录制类别。")</span><span class="sxs-lookup"><span data-stu-id="3c5d3-114">![Screenshot showing the interaction recording what and why.](media/recording-taxonomy.png "The image shows the recording categories.")</span></span>

<span data-ttu-id="3c5d3-115">每个类别对于如何启动录制、录制内容、存储录制位置、通知谁、谁控制访问以及如何处理保留要求不同。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-115">Each of the categories entails different requirements for how recordings are initiated, what is recorded, where recordings are stored, who is notified, who controls access, and how retention is handled.</span></span>

| <span data-ttu-id="3c5d3-116">类型</span><span class="sxs-lookup"><span data-stu-id="3c5d3-116">Type</span></span>                   | <span data-ttu-id="3c5d3-117">方便 (录制Teams录制) </span><span class="sxs-lookup"><span data-stu-id="3c5d3-117">Convenience (Regular Teams Recording)</span></span> | <span data-ttu-id="3c5d3-118">组织 - 受管制 (合规性记录) </span><span class="sxs-lookup"><span data-stu-id="3c5d3-118">Org - Regulated (Compliance Recording)</span></span> |
| ---------------------- | ------------------ | --------------- |
| <span data-ttu-id="3c5d3-119">发起程序</span><span class="sxs-lookup"><span data-stu-id="3c5d3-119">Initiator</span></span>              | <span data-ttu-id="3c5d3-120">用户</span><span class="sxs-lookup"><span data-stu-id="3c5d3-120">User</span></span>               | <span data-ttu-id="3c5d3-121">管理 (系统) </span><span class="sxs-lookup"><span data-stu-id="3c5d3-121">Admin (system)</span></span>  |
| <span data-ttu-id="3c5d3-122">目标</span><span class="sxs-lookup"><span data-stu-id="3c5d3-122">Target</span></span>                 | <span data-ttu-id="3c5d3-123">每呼叫/会议</span><span class="sxs-lookup"><span data-stu-id="3c5d3-123">Per-call / meeting</span></span> | <span data-ttu-id="3c5d3-124">按用户</span><span class="sxs-lookup"><span data-stu-id="3c5d3-124">Per-user</span></span>        |
| <span data-ttu-id="3c5d3-125">存储所有者</span><span class="sxs-lookup"><span data-stu-id="3c5d3-125">Storage owner</span></span>          | <span data-ttu-id="3c5d3-126">用户</span><span class="sxs-lookup"><span data-stu-id="3c5d3-126">User</span></span>               | <span data-ttu-id="3c5d3-127">合规性</span><span class="sxs-lookup"><span data-stu-id="3c5d3-127">Compliance</span></span>      |
| <span data-ttu-id="3c5d3-128">需要通知？</span><span class="sxs-lookup"><span data-stu-id="3c5d3-128">Notification required?</span></span> | <span data-ttu-id="3c5d3-129">是</span><span class="sxs-lookup"><span data-stu-id="3c5d3-129">Yes</span></span>                | <span data-ttu-id="3c5d3-130">是</span><span class="sxs-lookup"><span data-stu-id="3c5d3-130">Yes</span></span>             |
| <span data-ttu-id="3c5d3-131">访问所有者</span><span class="sxs-lookup"><span data-stu-id="3c5d3-131">Access Owner</span></span>           | <span data-ttu-id="3c5d3-132">用户</span><span class="sxs-lookup"><span data-stu-id="3c5d3-132">User</span></span>               | <span data-ttu-id="3c5d3-133">合规性</span><span class="sxs-lookup"><span data-stu-id="3c5d3-133">Compliance</span></span>      |
| <span data-ttu-id="3c5d3-134">保留策略？</span><span class="sxs-lookup"><span data-stu-id="3c5d3-134">Retention Policy?</span></span>      | <span data-ttu-id="3c5d3-135">可选</span><span class="sxs-lookup"><span data-stu-id="3c5d3-135">Optional</span></span>           | <span data-ttu-id="3c5d3-136">是</span><span class="sxs-lookup"><span data-stu-id="3c5d3-136">Yes</span></span>             |

<span data-ttu-id="3c5d3-137">Teams为会议和实时[事件](./cloud-recording.md)提供了各种功能，便于进行功能齐全的录制。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-137">Teams provides various capabilities for [convenient](./cloud-recording.md) and functional recording for meetings and live events.</span></span> <span data-ttu-id="3c5d3-138">组织记录意味着使组织能够采用 Teams 进行呼叫和会议，从而通过管理策略规定何时应自动录制和捕获呼叫和联机会议，以便根据相关公司或法规策略的要求进行后续处理和保留。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-138">Organizational recording means enabling organizations adopting Teams for calling and meetings to stipulate, by way of an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span> <span data-ttu-id="3c5d3-139">此策略下的用户将注意到正在录制其与 Teams 的数字交互，但无法禁用录制，并且完成交互后将无法访问录制。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-139">Users under this policy will be aware that their digital interactions with Teams are being recorded but will not be able to disable the recording and will not have access to the recording once the interaction is complete.</span></span> <span data-ttu-id="3c5d3-140">记录成为组织存档的一部分，可供合规性和法律人员用于电子数据展示、法定保留和其他公司保留用途。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-140">The recording becomes part of the organizational archive available to compliance and legal personnel for eDiscovery, legal hold, and other corporate retention uses.</span></span>

## <a name="example-user-needs"></a><span data-ttu-id="3c5d3-141">用户需求示例</span><span class="sxs-lookup"><span data-stu-id="3c5d3-141">Example user needs</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="3c5d3-142">角色</span><span class="sxs-lookup"><span data-stu-id="3c5d3-142">Persona</span></span></th>
<th><span data-ttu-id="3c5d3-143">需求</span><span class="sxs-lookup"><span data-stu-id="3c5d3-143">Needs</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="3c5d3-144">记录的用户</span><span class="sxs-lookup"><span data-stu-id="3c5d3-144">Recorded users</span></span></td>
<td><ul>
<li><p><span data-ttu-id="3c5d3-145">在录制正在进行时收到通知。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-145">Be notified when recording is in progress.</span></span></p></li>
<li><p><span data-ttu-id="3c5d3-146">当策略和/或记录器错误导致调用行为发生更改时，请通知。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-146">Be informed when policy and/or recorder error is causing changes in calling behavior.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3c5d3-147">通信管理员</span><span class="sxs-lookup"><span data-stu-id="3c5d3-147">Communications admin</span></span></td>
<td><ul>
<li><p><span data-ttu-id="3c5d3-148">了解为何以及如何对用户/终结点应用/Teams录制策略。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-148">Understand why and how to apply / enforce recording policies to Teams users / endpoints.</span></span></p></li>
<li><p><span data-ttu-id="3c5d3-149">配置和维护Teams组织的录制策略。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-149">Configure and maintain Teams recording policies for the organization.</span></span></p></li>
<li><p><span data-ttu-id="3c5d3-150">监视和排查与通话和Teams录制相关的问题。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-150">Monitor and troubleshoot recording-related issues with Teams calls and meetings.</span></span></p></li>
<li><p><span data-ttu-id="3c5d3-151">通过使用情况、质量和可靠性的操作分析，为内部合规专员提供支持。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-151">Support internal compliance officer with operational analytics on usage, quality, and reliability.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3c5d3-152">合规性主管</span><span class="sxs-lookup"><span data-stu-id="3c5d3-152">Compliance officer</span></span></td>
<td><ul>
<li><p><span data-ttu-id="3c5d3-153">按照Teams区域边界的合规性义务所需的方式收集所有安全通信。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-153">Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.</span></span></p></li>
<li><p><span data-ttu-id="3c5d3-154">基于通信相关的元数据或交互内容搜索交互。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-154">Search for interactions based on communication-related metadata or interaction content.</span></span> <span data-ttu-id="3c5d3-155">常见示例包括：</span><span class="sxs-lookup"><span data-stu-id="3c5d3-155">Common examples include:</span></span></p>
<ul>
<li><p><span data-ttu-id="3c5d3-156"><strong>元数据</strong> - 参与者、时间、方向、拨号号码、出发地号码、自定义业务数据</span><span class="sxs-lookup"><span data-stu-id="3c5d3-156"><strong>Metadata</strong> - Participants, time, direction, dialed number, origin number, Custom business data</span></span></p></li>
<li><p><span data-ttu-id="3c5d3-157"><strong>内容</strong> - 听录、情绪、语音、相关交互</span><span class="sxs-lookup"><span data-stu-id="3c5d3-157"><strong>Content</strong> – Transcription, sentiment, phonetics, related interactions</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="3c5d3-158">分析和与收集的通信进行交互，包括收集交互时监视交互的能力。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-158">Analyze and interact with collected communications, including the ability to monitor interactions as they are being collected.</span></span></p></li>
<li><p><span data-ttu-id="3c5d3-159">确保收集的通信的安全性，并防止所有阶段发生篡改。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-159">Ensure security of collected communications and prevent tampering at all stages.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a><span data-ttu-id="3c5d3-160">解决方案体系结构概述</span><span class="sxs-lookup"><span data-stu-id="3c5d3-160">Solution architecture overview</span></span>

<span data-ttu-id="3c5d3-161">合规性记录解决方案与Teams集成，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="3c5d3-161">Compliance recording solutions are integrated with Teams as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3c5d3-162">![显示团队自定义应用设置的屏幕截图](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "图像显示发送和Teams呼叫时流。")</span><span class="sxs-lookup"><span data-stu-id="3c5d3-162">![Screenshot showing the team custom app setting](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "The images shows the flow when a Teams meeting or call is sent and received.")</span></span>

## <a name="recorder"></a><span data-ttu-id="3c5d3-163">录音机</span><span class="sxs-lookup"><span data-stu-id="3c5d3-163">Recorder</span></span>

<span data-ttu-id="3c5d3-164">合规性记录解决方案的核心组件是记录器。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-164">The core component of the compliance recording solution is the recorder.</span></span>
<span data-ttu-id="3c5d3-165">记录器构建为基于 Azure 的可缩放服务， (机器人) [Microsoft](/graph/cloud-communications-concept-overview)的通信平台，并注册为 Microsoft Graph。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-165">Recorders are built as scalable Azure-based services (bots) that [leverage Microsoft’s communications platform](/graph/cloud-communications-concept-overview) and register as applications with Microsoft Graph.</span></span> <span data-ttu-id="3c5d3-166">录制器提供与会议Teams通信平台[API](/graph/api/resources/communications-api-overview?view=graph-rest-1.0)的直接交互，并提供媒体的终结点。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-166">The recorder provides the direct interaction with the Teams calls and meetings [communications platform APIs](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and provides the endpoint for media ingestion.</span></span>

<span data-ttu-id="3c5d3-167">提供了 [一个示例符合性记录器应用程序](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) ，演示如何配置机器人、创建应用实例和分配符合性策略。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-167">A [sample compliance recorder application is available](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) that shows how to configure the bot, create the app instance and assign the compliance policies.</span></span> <span data-ttu-id="3c5d3-168">该示例还包含用于记录特定交互的 API 用法示例，例如[](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)处理传入呼叫路由[](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)、更改录制状态和删除正在[录制的用户](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-168">The sample also has examples on API usage for recording specific interactions such as handling [incoming call](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) routing, [changing recording states](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), and [removing the user who is being recorded](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span></span>
<span data-ttu-id="3c5d3-169">Graph [updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0)和 incomingContext ，可在此处找到有关特定 API 的[一些文档](/graph/api/resources/incomingcontext?view=graph-rest-1.0)。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-169">Graph documentation on the specific APIs can be found here for [updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0) and [incomingContext](/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span></span>

<span data-ttu-id="3c5d3-170">记录器服务的确切实现因合作伙伴而异，但必须设计为支持多个记录器，以实现部署的高可用性和地理分布，以减少从 Teams 到记录器的延迟。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-170">The exact implementation of the recorder service will vary by partner but must be designed to support multiple recorders in order to achieve high availability and geographical distribution of deployment to reduce latency from Teams to the recorder.</span></span> <span data-ttu-id="3c5d3-171">此外，设计记录器本身时，应牢记复原能力和冗余。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-171">In addition, it is expected that Recorders themselves be designed with resiliency and redundancy in mind.</span></span>

<span data-ttu-id="3c5d3-172">合作伙伴必须在提交其解决方案进行认证之前，与 Microsoft 确认 Microsoft Graph 通信 API 和 SDK 的最低发布版本，以确保合规性记录集成的所有要求都受支持。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-172">Partners must confirm the minimum required release version of the Microsoft Graph communications APIs and SDKs with Microsoft before submitting their solution for certification to ensure that all requirements of compliance recording integration are supported.</span></span>

<span data-ttu-id="3c5d3-173">合规性记录方案的基本要求有两个：</span><span class="sxs-lookup"><span data-stu-id="3c5d3-173">Two specific requirements that are fundamental for compliance recording scenario are:</span></span>

- <span data-ttu-id="3c5d3-174">记录器机器人必须部署在 Azure 中</span><span class="sxs-lookup"><span data-stu-id="3c5d3-174">Recorder bot must be deployed in Azure</span></span>

- <span data-ttu-id="3c5d3-175">记录器机器人必须在 Azure Windows VM 上运行</span><span class="sxs-lookup"><span data-stu-id="3c5d3-175">Recorder bot must run on a Windows VM in Azure</span></span>

<span data-ttu-id="3c5d3-176">Azure 和 Windows VM 要求仅适用于 Teams 机器人组件，这意味着合作伙伴可以实施他们选择的其他平台，但必须符合合规性记录的相关性能和功能要求。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-176">The Azure and Windows VM requirements only apply to the Teams Bot component, which means that a partner may implement the rest of the platform of their choice provided they can meet the relevant performance and functional requirements for compliance recording.</span></span>

## <a name="compliance-recording-policy-assignment-and-provisioning"></a><span data-ttu-id="3c5d3-177">符合性记录策略分配和预配</span><span class="sxs-lookup"><span data-stu-id="3c5d3-177">Compliance recording policy assignment and provisioning</span></span>

<span data-ttu-id="3c5d3-178">IT 管理员可以通过创建和分配符合性记录策略来确定要记录哪些用户以及每个用户使用哪个记录器。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-178">IT Administrators can determine which users are to be recorded and which recorder will be used for each user, by creating and assigning compliance recording policies.</span></span> <span data-ttu-id="3c5d3-179">当通信交互发生时，记录器会自动根据这些策略的配置邀请其参与对话。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-179">Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.</span></span> <span data-ttu-id="3c5d3-180">合规性记录策略使用 [Microsoft PowerShell](./teams-powershell-overview.md) 进行管理，可在租户、每个用户和安全组级别应用于每个组织。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-180">Compliance recording policies are managed using [Microsoft PowerShell](./teams-powershell-overview.md) and can be applied at the tenant, per-user, and security group level for each organization.</span></span> <span data-ttu-id="3c5d3-181">有关用于会议策略、调用策略和组策略[](./meeting-policies-in-teams.md)的 Microsoft [](./teams-calling-policy.md) [Docs，可找到详细信息](./assign-policies.md#assign-a-policy-to-a-group)。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-181">You can find more information on Microsoft Docs for [Meeting policies](./meeting-policies-in-teams.md), [calling policies](./teams-calling-policy.md) and  [group policies](./assign-policies.md#assign-a-policy-to-a-group).</span></span>

1. <span data-ttu-id="3c5d3-182">在租户中创建应用程序实例。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-182">Create an application instance in your tenant.</span></span>

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

2. <span data-ttu-id="3c5d3-183">创建合规性记录策略。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-183">Create a Compliance Recording policy.</span></span>

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

   <span data-ttu-id="3c5d3-184">请参阅[Set-CsTeamsComplianceRecordingPolicy。](/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="3c5d3-184">See [Set-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps).</span></span>

3. <span data-ttu-id="3c5d3-185">将合规性记录策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-185">Assign the Compliance Recording policy to a user.</span></span>

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   <span data-ttu-id="3c5d3-186">请参阅[Grant-CsTeamsComplianceRecordingPolicy。](/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="3c5d3-186">See [Grant-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps).</span></span>

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a><span data-ttu-id="3c5d3-187">用户体验</span><span class="sxs-lookup"><span data-stu-id="3c5d3-187">User experiences</span></span>

<span data-ttu-id="3c5d3-188">使用客户端体验支持Teams通知。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-188">Support for notifications is enabled using the Teams client experiences.</span></span> <span data-ttu-id="3c5d3-189">体验可以是视觉或音频。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-189">The experiences can be either visual or audio.</span></span>

<span data-ttu-id="3c5d3-190">**Teams客户端 - 视觉通知**</span><span class="sxs-lookup"><span data-stu-id="3c5d3-190">**Teams clients - visual notice**</span></span>
- <span data-ttu-id="3c5d3-191">桌面/Web</span><span class="sxs-lookup"><span data-stu-id="3c5d3-191">Desktop/web</span></span>
- <span data-ttu-id="3c5d3-192">移动 (iOS/Android) </span><span class="sxs-lookup"><span data-stu-id="3c5d3-192">Mobile (iOS/Android)</span></span>
- <span data-ttu-id="3c5d3-193">Teams手机</span><span class="sxs-lookup"><span data-stu-id="3c5d3-193">Teams phones</span></span>
- <span data-ttu-id="3c5d3-194">Teams会议室</span><span class="sxs-lookup"><span data-stu-id="3c5d3-194">Teams rooms</span></span>

<span data-ttu-id="3c5d3-195">**其他终结点 - 音频通知**</span><span class="sxs-lookup"><span data-stu-id="3c5d3-195">**Other endpoints - audio notice**</span></span>
- <span data-ttu-id="3c5d3-196">SIP 电话</span><span class="sxs-lookup"><span data-stu-id="3c5d3-196">SIP phones</span></span>
- <span data-ttu-id="3c5d3-197">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3c5d3-197">Skype for Business</span></span>
- <span data-ttu-id="3c5d3-198">音频会议</span><span class="sxs-lookup"><span data-stu-id="3c5d3-198">Audio conferencing</span></span>
- <span data-ttu-id="3c5d3-199">PSTN 呼叫者</span><span class="sxs-lookup"><span data-stu-id="3c5d3-199">PSTN callers</span></span>

## <a name="compliance-recording-for-teams-certification-programs"></a><span data-ttu-id="3c5d3-200">认证计划Teams符合性记录</span><span class="sxs-lookup"><span data-stu-id="3c5d3-200">Compliance recording for Teams certification programs</span></span>

<span data-ttu-id="3c5d3-201">除了发布允许合作伙伴开发和集成 CCaaS 解决方案与 Teams 的公开可用的 API 外，我们还为 Microsoft Teams 认证计划开发了合规性记录，为客户提供了保证，即每个参与合作伙伴的解决方案已经过测试和验证，以提供他们期望的 Microsoft 解决方案的质量、兼容性和可靠性。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-201">In addition to publishing publicly available APIs allowing partners to develop and integrate CCaaS solutions with Teams, we have developed the compliance recording for Microsoft Teams certification program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>  

<span data-ttu-id="3c5d3-202">以下合作伙伴已认证其解决方案Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-202">The following partners have certified their solution for Microsoft Teams.</span></span><br/><br/>

|<span data-ttu-id="3c5d3-203">合作伙伴</span><span class="sxs-lookup"><span data-stu-id="3c5d3-203">Partner</span></span>|<span data-ttu-id="3c5d3-204">解决方案网站</span><span class="sxs-lookup"><span data-stu-id="3c5d3-204">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="3c5d3-205">ASC Technologies</span><span class="sxs-lookup"><span data-stu-id="3c5d3-205">ASC Technologies</span></span> |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|<span data-ttu-id="3c5d3-206">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="3c5d3-206">AudioCodes</span></span> |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|<span data-ttu-id="3c5d3-207">CallCabinet</span><span class="sxs-lookup"><span data-stu-id="3c5d3-207">CallCabinet</span></span> |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|<span data-ttu-id="3c5d3-208">配音器</span><span class="sxs-lookup"><span data-stu-id="3c5d3-208">Dubber</span></span> |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|<span data-ttu-id="3c5d3-209">NICE</span><span class="sxs-lookup"><span data-stu-id="3c5d3-209">NICE</span></span> |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|<span data-ttu-id="3c5d3-210">Numonix</span><span class="sxs-lookup"><span data-stu-id="3c5d3-210">Numonix</span></span> |[https://numonix.cloud](https://numonix.cloud)    |
|<span data-ttu-id="3c5d3-211">Theta Lake</span><span class="sxs-lookup"><span data-stu-id="3c5d3-211">Theta Lake</span></span> |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |
|<span data-ttu-id="3c5d3-212">Verint</span><span class="sxs-lookup"><span data-stu-id="3c5d3-212">Verint</span></span> |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

<br/>
<span data-ttu-id="3c5d3-213">以下合作伙伴正在验证其解决方案Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-213">The following partners are in the process of certifying their solution for Microsoft Teams.</span></span><br/><br/>

|<span data-ttu-id="3c5d3-214">合作伙伴</span><span class="sxs-lookup"><span data-stu-id="3c5d3-214">Partner</span></span>|<span data-ttu-id="3c5d3-215">解决方案网站</span><span class="sxs-lookup"><span data-stu-id="3c5d3-215">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="3c5d3-216">Insightful Technology</span><span class="sxs-lookup"><span data-stu-id="3c5d3-216">Insightful Technology</span></span> |[http://www.insightfultechnology.com/what-we-do/fixed-line-voice-recording/](http://www.insightfultechnology.com/what-we-do/fixed-line-voice-recording/) |
|<span data-ttu-id="3c5d3-217">Landis Technologies</span><span class="sxs-lookup"><span data-stu-id="3c5d3-217">Landis Technologies</span></span> |[https://landistechnologies.com/](https://landistechnologies.com/) |
|<span data-ttu-id="3c5d3-218">Luware</span><span class="sxs-lookup"><span data-stu-id="3c5d3-218">Luware</span></span> |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|<span data-ttu-id="3c5d3-219">Oak Innovation</span><span class="sxs-lookup"><span data-stu-id="3c5d3-219">Oak Innovation</span></span> |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|<span data-ttu-id="3c5d3-220">Red Box</span><span class="sxs-lookup"><span data-stu-id="3c5d3-220">Red Box</span></span> |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |

<span data-ttu-id="3c5d3-221">随着更多合作伙伴加入并满足认证条件，此列表将更新。</span><span class="sxs-lookup"><span data-stu-id="3c5d3-221">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3c5d3-222">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3c5d3-222">Next steps</span></span>

<span data-ttu-id="3c5d3-223">如果你是希望加入认证计划的供应商，请通过 邮件<a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com。</a></span><span class="sxs-lookup"><span data-stu-id="3c5d3-223">If you are a vendor seeking to join the certification program, please mail  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span></span>
