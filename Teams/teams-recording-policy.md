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
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>有关Teams会议呼叫的基于策略的录制&简介

基于策略的记录使采用 Microsoft Teams 进行呼叫和会议的组织能够规定，当应按照相关公司或法规策略的要求自动记录和捕获呼叫和联机会议以用于后续处理和保留时，使用管理策略。

Teams已增强，以支持第三方录制解决方案的集成，包括提供端到端解决方案（用于配置、管理、录制、存储和分析 Teams 通信）所需的平台功能、用户体验和管理界面。 增强功能包括通信平台 API 和用于录制的事件，它们提供：

- 跨设备和所有受支持的终结点无缝、高质量的媒体捕获，用于音频、视频、屏幕共享和聊天。

- 支持在 Teams 用户与受支持的呼叫终结点 (Teams、Teams Mobile、Skype for Business、PSTN) 

- 用于合规性记录的新管理策略，包括与现有的Teams呼叫和会议工具和策略的集成

可以在 Microsoft 365 A3/A5/E3/E5/Business 高级版 和 Office 365 A3/A5/E3/E5 用户上启用合规性记录。 

合规性记录解决方案集成功能也在 Ignite 2019 的合规性记录和Microsoft Teams[评审](https://myignite.microsoft.com/archives/IG19-VCE40)。

## <a name="teams-interaction-recording-overview"></a>Teams交互录制概述

交互录制用例可以有效地分为四个主要类别的录制功能 – 便利、功能、组织和合法拦截，如下图所示：

> [!div class="mx-imgBorder"]
> ![显示交互录制内容以及原因的屏幕截图。](media/recording-taxonomy.png "图像显示录制类别。")

每个类别对于如何启动录制、录制内容、存储录制位置、通知谁、谁控制访问以及如何处理保留要求不同。

| 类型                   | 方便 (录制Teams录制)  | 组织 - 受管制 (合规性记录)  |
| ---------------------- | ------------------ | --------------- |
| 发起程序              | 用户               | 管理 (系统)   |
| 目标                 | 每呼叫/会议 | 按用户        |
| 存储所有者          | 用户               | 合规性      |
| 需要通知？ | 是                | 是             |
| 访问所有者           | 用户               | 合规性      |
| 保留策略？      | 可选           | 是             |

Teams为会议和实时[事件](./cloud-recording.md)提供了各种功能，便于进行功能齐全的录制。 组织记录意味着使组织能够采用 Teams 进行呼叫和会议，从而通过管理策略规定何时应自动录制和捕获呼叫和联机会议，以便根据相关公司或法规策略的要求进行后续处理和保留。 此策略下的用户将注意到正在录制其与 Teams 的数字交互，但无法禁用录制，并且完成交互后将无法访问录制。 记录成为组织存档的一部分，可供合规性和法律人员用于电子数据展示、法定保留和其他公司保留用途。

## <a name="example-user-needs"></a>用户需求示例

<table>
<thead>
<tr class="header">
<th>角色</th>
<th>需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>记录的用户</td>
<td><ul>
<li><p>在录制正在进行时收到通知。</p></li>
<li><p>当策略和/或记录器错误导致调用行为发生更改时，请通知。</p></li>
</ul></td>
</tr>
<tr class="even">
<td>通信管理员</td>
<td><ul>
<li><p>了解为何以及如何对用户/终结点应用/Teams录制策略。</p></li>
<li><p>配置和维护Teams组织的录制策略。</p></li>
<li><p>监视和排查与通话和Teams录制相关的问题。</p></li>
<li><p>通过使用情况、质量和可靠性的操作分析，为内部合规专员提供支持。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>合规性主管</td>
<td><ul>
<li><p>按照Teams区域边界的合规性义务所需的方式收集所有安全通信。</p></li>
<li><p>基于通信相关的元数据或交互内容搜索交互。 常见示例包括：</p>
<ul>
<li><p><strong>元数据</strong> - 参与者、时间、方向、拨号号码、出发地号码、自定义业务数据</p></li>
<li><p><strong>内容</strong> - 听录、情绪、语音、相关交互</p></li>
</ul></li>
<li><p>分析和与收集的通信进行交互，包括收集交互时监视交互的能力。</p></li>
<li><p>确保收集的通信的安全性，并防止所有阶段发生篡改。</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>解决方案体系结构概述

合规性记录解决方案与Teams集成，如下图所示：

> [!div class="mx-imgBorder"]
> ![显示团队自定义应用设置的屏幕截图](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "图像显示发送和Teams呼叫时流。")

## <a name="recorder"></a>录音机

合规性记录解决方案的核心组件是记录器。
记录器构建为基于 Azure 的可缩放服务， (机器人) [Microsoft](/graph/cloud-communications-concept-overview)的通信平台，并注册为 Microsoft Graph。 录制器提供与会议Teams通信平台[API](/graph/api/resources/communications-api-overview?view=graph-rest-1.0)的直接交互，并提供媒体的终结点。

提供了 [一个示例符合性记录器应用程序](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) ，演示如何配置机器人、创建应用实例和分配符合性策略。 该示例还包含用于记录特定交互的 API 用法示例，例如[](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)处理传入呼叫路由[](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)、更改录制状态和删除正在[录制的用户](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)。
Graph [updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0)和 incomingContext ，可在此处找到有关特定 API 的[一些文档](/graph/api/resources/incomingcontext?view=graph-rest-1.0)。

记录器服务的确切实现因合作伙伴而异，但必须设计为支持多个记录器，以实现部署的高可用性和地理分布，以减少从 Teams 到记录器的延迟。 此外，设计记录器本身时，应牢记复原能力和冗余。

合作伙伴必须在提交其解决方案进行认证之前，与 Microsoft 确认 Microsoft Graph 通信 API 和 SDK 的最低发布版本，以确保合规性记录集成的所有要求都受支持。

合规性记录方案的基本要求有两个：

- 记录器机器人必须部署在 Azure 中

- 记录器机器人必须在 Azure Windows VM 上运行

Azure 和 Windows VM 要求仅适用于 Teams 机器人组件，这意味着合作伙伴可以实施他们选择的其他平台，但必须符合合规性记录的相关性能和功能要求。

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>符合性记录策略分配和预配

IT 管理员可以通过创建和分配符合性记录策略来确定要记录哪些用户以及每个用户使用哪个记录器。 当通信交互发生时，记录器会自动根据这些策略的配置邀请其参与对话。 合规性记录策略使用 [Microsoft PowerShell](./teams-powershell-overview.md) 进行管理，可在租户、每个用户和安全组级别应用于每个组织。 有关用于会议策略、调用策略和组策略[](./meeting-policies-in-teams.md)的 Microsoft [](./teams-calling-policy.md) [Docs，可找到详细信息](./assign-policies.md#assign-a-policy-to-a-group)。

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

   请参阅[Set-CsTeamsComplianceRecordingPolicy。](/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. 将合规性记录策略分配给用户。

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   请参阅[Grant-CsTeamsComplianceRecordingPolicy。](/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>用户体验

使用客户端体验支持Teams通知。 体验可以是视觉或音频。

**Teams客户端 - 视觉通知**
- 桌面/Web
- 移动 (iOS/Android) 
- Teams手机
- Teams会议室

**其他终结点 - 音频通知**
- SIP 电话
- Skype for Business
- 音频会议
- PSTN 呼叫者

## <a name="compliance-recording-for-teams-certification-programs"></a>认证计划Teams符合性记录

除了发布允许合作伙伴开发和集成 CCaaS 解决方案与 Teams 的公开可用的 API 外，我们还为 Microsoft Teams 认证计划开发了合规性记录，为客户提供了保证，即每个参与合作伙伴的解决方案已经过测试和验证，以提供他们期望的 Microsoft 解决方案的质量、兼容性和可靠性。  

以下合作伙伴已认证其解决方案Microsoft Teams。<br/><br/>

|合作伙伴|解决方案网站 |
|:--|:--|
|ASC Technologies |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|配音器 |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|NICE |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Theta Lake |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

<br/>
以下合作伙伴正在验证其解决方案Microsoft Teams。<br/><br/>

|合作伙伴|解决方案网站 |
|:--|:--|
|Insightful Technology |[http://www.insightfultechnology.com/what-we-do/fixed-line-voice-recording/](http://www.insightfultechnology.com/what-we-do/fixed-line-voice-recording/) |
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|Oak Innovation |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|Red Box |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |

随着更多合作伙伴加入并满足认证条件，此列表将更新。

## <a name="next-steps"></a>后续步骤

如果你是希望加入认证计划的供应商，请通过 邮件<a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com。</a>
