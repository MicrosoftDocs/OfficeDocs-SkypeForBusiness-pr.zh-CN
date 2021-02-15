---
title: 用于呼叫会议、基于 Teams 策略的录制&简介
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
description: 了解用于呼叫会议和会议的基于 Teams &录制
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
ms.openlocfilehash: 2d8949a4eaa3365857768726a523ae480a94df55
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196766"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Teams 基于策略的通话记录简介&会议

基于策略的录制使采用 Microsoft Teams 进行呼叫和会议的组织能够规定何时应自动录制和捕获呼叫和联机会议，以根据相关公司或法规策略的要求进行后续处理和保留。

Teams 已经过增强，支持集成第三方录制解决方案，包括提供端到端解决方案（用于配置、管理、录制、存储和分析 Teams 通信）所需的平台功能、用户体验和管理界面。 增强功能包括通信平台 API 和用于录制的事件，它们提供：

- 跨设备和所有受支持的终结点无缝、高质量的媒体捕获，用于音频、视频、屏幕共享和聊天。

- 支持 Teams 用户与 Teams、Teams mobile、Skype for Business、PSTN (支持呼叫终结点之间的交互) 

- 用于符合性记录的新管理策略，包括与现有的 Teams 管理呼叫和会议工具和策略的集成

可以在 Microsoft 365 A3/A5/E3/E5/Business Premium 和 Office 365 A3/A5/E3/E5 用户上启用合规性记录。 

合规性记录解决方案集成功能也在 Ignite 2019 的合规性记录和 Microsoft Teams 会话中 [<span class="underline">进行了评审</span>](https://myignite.microsoft.com/archives/IG19-VCE40)。

## <a name="teams-interaction-recording-overview"></a>Teams 交互录制概述

交互录制用例可以有效地分为四个主要类别的记录功能 - 便利、功能、组织和合法拦截，如图所示：

![显示交互录制内容以及原因的屏幕截图。](media/recording-taxonomy.png "该图像显示录制类别。")

每个类别对如何启动录制、录制内容、录制位置、通知谁、谁控制访问以及如何处理保留要求不同。

| 类型                   | 方便 (Teams 录制)  | 组织 - 受管制 (合规性记录)  |
| ---------------------- | ------------------ | --------------- |
| 发起程序              | 用户               | 管理 (系统)   |
| 目标                 | 每呼叫/会议 | 按用户        |
| 存储所有者          | 用户               | 合规性      |
| 需要通知？ | 是                | 是             |
| 访问所有者           | 用户               | 合规性      |
| 保留策略？      | 可选           | 是             |

Teams 提供各种功能，用于 [<span class="underline">为</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) 会议和实时事件提供方便且功能齐全的录制。 组织记录意味着允许采用 Teams 呼叫和会议的组织通过管理策略规定何时应自动记录和捕获呼叫和联机会议，以便根据相关公司或法规策略的要求进行后续处理和保留。 此策略下的用户将注意到正在录制与 Teams 的数字交互，但无法禁用录制，并且交互完成后将无法访问录制。 记录成为组织存档的一部分，可供合规性人员和法律人员用于电子数据展示、法定保留和其他公司保留用途。

## <a name="example-user-needs"></a>用户需求示例

<table>
<thead>
<tr class="header">
<th><strong>角色</strong></th>
<th><strong>需要</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>记录的用户</td>
<td><ul>
<li><p>在录制正在进行时收到通知。</p></li>
<li><p>当策略和/或记录器错误导致调用行为发生更改时，请通知你。</p></li>
</ul></td>
</tr>
<tr class="even">
<td>通信管理员</td>
<td><ul>
<li><p>了解为何以及如何向 Teams 用户/终结点应用/强制实施录制策略。</p></li>
<li><p>为组织配置和维护 Teams 录制策略。</p></li>
<li><p>监视和排查 Teams 通话和会议与录制相关的问题。</p></li>
<li><p>对使用情况、质量和可靠性进行运营分析，为内部合规主管提供支持。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>合规性主管</td>
<td><ul>
<li><p>按照满足适当区域边界中的合规性义务所需的方式收集所有 Teams 通信。</p></li>
<li><p>基于通信相关的元数据或交互内容搜索交互。 常见示例包括：</p>
<ul>
<li><p><strong>元数据</strong> - 参与者、时间、方向、拨号号码、出发地号码、自定义业务数据</p></li>
<li><p><strong>内容</strong> - 听录、情绪、语音、相关交互</p></li>
</ul></li>
<li><p>分析收集的通信并与之交互，包括在收集交互时监视交互的能力。</p></li>
<li><p>确保收集的通信的安全性，并防止所有阶段发生篡改。</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>解决方案体系结构概述

合规性记录解决方案与 Teams 集成，如下图所示：

![显示团队自定义应用设置的屏幕截图](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "图像显示发送和接收 Teams 会议或呼叫时流。")

## <a name="recorder"></a>录音机

合规性记录解决方案的核心组件是记录器。
记录器构建为基于 Azure 的可缩放服务， (机器人) [<span class="underline">Microsoft</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) 的通信平台，并注册为 Microsoft Graph 的应用程序。 记录器提供与 Teams 通话和会议通信平台 [<span class="underline">API</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) 的直接交互，并提供媒体的终结点。

提供了 [<span class="underline">一个示例符合性记录器应用程序</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) ，演示如何配置机器人、创建应用实例和分配符合性策略。 该示例还举例说明了用于记录特定交互的 API 用法，例如[<span class="underline"></span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)处理传入呼叫路由[<span class="underline"></span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)、更改录制状态和删除正在[<span class="underline">录制的用户</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)。
有关特定 API 的图形文档，可在此处找到[<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http)和[<span class="underline">incomingContext。</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0)

记录器服务的确切实现因合作伙伴而异，但必须设计为支持多个记录器，以实现部署的高可用性和地理分布，以减少从 Teams 到记录器的延迟。 此外，设计记录器本身时，应该牢记复原能力和冗余。

合作伙伴必须在提交解决方案进行认证之前，与 Microsoft 确认 Microsoft Graph 通信 API 和 SDK 的最低要求发布版本，以确保合规性记录集成的所有要求都受支持。

符合性记录方案的两个具体要求是：

- 记录器机器人必须在 Azure 中部署

- 记录器机器人必须在 Azure 中的 Windows VM 上运行

Azure 和 Windows VM 要求仅适用于 Teams 机器人组件，这意味着合作伙伴可以实施他们选择的其他平台，但只要他们可以满足符合性记录的相关性能和功能要求。

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>符合性记录策略分配和预配

IT 管理员可以通过创建和分配符合性记录策略来确定要记录哪些用户，以及将哪个记录器用于每个用户。 当通信交互发生时，记录器会自动根据这些策略的配置参与对话。 合规性记录策略使用 [<span class="underline">Microsoft PowerShell 进行管理</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) ，可在每个组织的租户、每个用户和安全组级别应用。 你可以找到有关用于会议策略、调用[<span class="underline">策略和组</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams)策略的[<span class="underline"></span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy)Microsoft Docs[<span class="underline">详细信息</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)。

1. 在租户中创建应用程序实例。

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

2. 创建合规性记录策略。

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

   [<span class="underline">Set-CsTeamsComplianceRecordingPolicy</span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. 将合规性记录策略分配给用户。

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>用户体验

使用 Teams 客户端体验启用通知支持。 体验可以是视觉或音频。

**Teams 客户端 - 视觉通知**
- 桌面/Web
- 移动 (iOS/Android) 
- Teams 电话
- Teams 会议室

**其他终结点 - 音频通知**
- SIP 电话
- Skype for Business
- 音频会议
- PSTN 呼叫者

## <a name="compliance-recording-for-teams-certification-programs"></a>Teams 认证计划符合性记录

除了发布公开可用的 API，允许合作伙伴开发和集成 CCaaS 解决方案与 Teams 外，我们还为 Microsoft Teams 认证计划开发了合规性记录，以便为客户提供保证，即每个参与合作伙伴的解决方案都经过测试和验证，以提供他们期望从 Microsoft 解决方案获得的质量、兼容性和可靠性。  

以下合作伙伴已认证其 Microsoft Teams 解决方案。

|合作伙伴|解决方案网站 |
|:--|:--|
|ASC Technologies |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|配音器 |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|NICE |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |


以下合作伙伴正在认证其 Microsoft Teams 解决方案。

|合作伙伴|解决方案网站 |
|:--|:--|
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Ak Innovation |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|Red Box |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

随着更多合作伙伴加入并满足认证条件，此列表将更新。

## <a name="next-steps"></a>后续步骤

如果你是希望加入认证计划的供应商，请向<a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com。</a>
