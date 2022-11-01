---
title: 通话&会议基于 Teams 策略的录制简介
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
ms.localizationpriority: medium
search.appverid: MET150
description: 了解通话&会议的基于 Teams 策略的录制
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
- tier3
- purview-compliance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 088515e6d9d4fe9e6dc893d736f7baac1148c731
ms.sourcegitcommit: 86b9503eb0085e23176cb346767f880ea3a73e77
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2022
ms.locfileid: "68808281"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>通话&会议基于 Teams 策略的录制简介

基于策略的录制使采用 Microsoft Teams 进行通话和会议的组织可以使用管理策略来规定何时应根据相关公司或法规策略的要求自动录制和捕获呼叫和联机会议，以便进行后续处理和保留。

Teams 已得到增强，以支持第三方录制解决方案的集成，包括提供用于配置、管理、录制、存储和分析 Teams 通信的端到端解决方案所需的平台功能、用户体验和管理界面。 增强功能包括通信平台 API 和用于录制的事件，这些 API 提供：

- 跨设备以及所有支持的音频、视频、屏幕共享和聊天终结点的无缝高质量媒体捕获。

- 支持 Teams 用户和支持的呼叫终结点之间的交互捕获， (Teams、Teams Mobile、Skype for Business、PSTN) 

- 用于合规性录制的新管理策略，包括与现有 Teams 管理通话和会议工具和策略的集成

可以在 Microsoft 365 A3/A5/E3/E5/Business Premium 和 Office 365 A3/A5/E3/E5 用户上启用合规性记录。 

Ignite 2019 的 [合规性记录和 Microsoft Teams 会议](https://myignite.microsoft.com/archives/IG19-VCE40)中还审查了合规性记录解决方案集成功能。

## <a name="teams-interaction-recording-overview"></a>Teams 交互录制概述

交互录制用例可以有效地分为四个主要类别的录制功能 - 便利、功能、组织和合法拦截，如图所示：

> [!div class="mx-imgBorder"]
> ![显示交互记录内容和原因的屏幕截图。](media/recording-taxonomy.png "图像显示录制类别。")

每个类别对录制的启动方式、录制内容、录制位置、通知人员、控制访问权限以及处理保留的方式提出了不同的要求。

| 类型                   | 方便 (常规 Teams 录制)  | 组织 - 受监管 (合规性记录)  |
| ---------------------- | ------------------ | --------------- |
| 引发              | 用户               | 管理员 (系统)   |
| 目标                 | 按呼叫/会议 | 按用户        |
| 存储所有者          | 用户               | 合规性      |
| 需要通知？ | 是                | 是             |
| 访问所有者           | 用户               | 合规性      |
| 保留策略？      | 可选           | 是             |

Teams 提供各种 [功能，方便](./cloud-recording.md) 且功能齐全的会议和实时活动录制。 组织记录是指允许采用 Teams 进行通话和会议的组织根据管理策略规定何时应根据相关公司或法规策略的要求自动记录和捕获呼叫和联机会议，以便进行后续处理和保留。 此策略下的用户将注意到，他们与 Teams 的数字交互正在录制，但无法禁用录制，并且一旦交互完成，将无法访问录制内容。 记录成为组织存档的一部分，可供合规性和法律人员使用电子数据展示、法定保留和其他公司保留使用。

## <a name="example-user-needs"></a>示例用户需求

<table>
<thead>
<tr class="header">
<th>角色</th>
<th>需要</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>记录的用户</td>
<td><ul>
<li><p>录制正在进行时收到通知。</p></li>
<li><p>当策略和/或记录器错误导致调用行为发生变化时收到通知。</p></li>
</ul></td>
</tr>
<tr class="even">
<td>通信管理员</td>
<td><ul>
<li><p>了解为何以及如何对 Teams 用户/终结点应用/强制实施录制策略。</p></li>
<li><p>为组织配置和维护 Teams 录制策略。</p></li>
<li><p>监视和排查与 Teams 通话和会议录制相关的问题。</p></li>
<li><p>通过有关使用情况、质量和可靠性的操作分析，为内部合规性官员提供支持。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>合规性官员</td>
<td><ul>
<li><p>以在适当的区域边界中履行合规性义务所需的方式收集所有 Teams 通信。</p></li>
<li><p>根据与通信相关的元数据或交互内容搜索交互。 常见示例包括：</p>
<ul>
<li><p><strong>元</strong> - 参与者、时间、方向、拨号号码、原点号码、自定义业务数据</p></li>
<li><p><strong>内容</strong> - 听录、情绪、拼音、相关交互</p></li>
</ul></li>
<li><p>分析和与收集的通信进行交互，包括能够监视正在收集的交互。</p></li>
<li><p>确保收集的通信的安全性，并防止所有阶段的篡改。</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>解决方案体系结构概述

合规性记录解决方案与 Teams 集成，如下图所示：

> [!div class="mx-imgBorder"]
> ![显示团队自定义应用设置的屏幕截图。](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "图像显示发送和接收 Teams 会议或呼叫时的流。")

> [!NOTE]
> 此解决方案专为使用 Teams 启用基于策略的合规性记录而设计。 不支持此解决方案的任何其他用途。

## <a name="recorder"></a>录音机

合规性录制解决方案的核心组件是记录器。
记录器构建为基于 Azure 的可缩放服务， ([使用 Microsoft 通信平台并在 Microsoft](/graph/cloud-communications-concept-overview) Graph 中注册为应用程序的机器人) 。 记录器提供与 Teams 呼叫和会议 [通信平台 API 的](/graph/api/resources/communications-api-overview) 直接交互，并提供用于媒体引入的终结点。

[提供了一个示例合规性记录器应用程序](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot)，演示如何配置机器人、创建应用实例和分配合规性策略。 此示例还提供了有关用于记录特定交互（例如处理 [传入呼叫](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) 路由、 [更改录制状态](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)和 [删除正在录制的用户](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)）的 API 用法的示例。
有关特定 API 的图形文档，可在此处找到 [updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http) 和 [incomingContext](/graph/api/resources/incomingcontext)。

记录器服务的确切实现因合作伙伴而异，但必须设计为支持多个记录器，以实现部署的高可用性和地理分布，以减少从 Teams 到记录器的延迟。 此外，在设计记录器本身时，还需考虑到复原能力和冗余。

在提交解决方案进行认证之前，合作伙伴必须与 Microsoft 确认 Microsoft Graph 通信 API 和 SDK 的最低版本要求，以确保符合性记录集成的所有要求都受支持。

符合性记录方案的基本两个特定要求是：

- 记录器机器人必须在 Azure 中部署

- 记录器机器人必须在 Azure 中的 Windows VM 上运行

Azure 和 Windows VM 要求仅适用于 Teams 机器人组件，这意味着合作伙伴可以实施他们选择的平台的其余部分，前提是他们能够满足合规性记录的相关性能和功能要求。

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>合规性记录策略分配和预配

IT 管理员可以通过创建和分配符合性记录策略，确定要记录哪些用户以及每个用户将使用哪个记录器。 发生通信交互时，系统会根据这些策略的配置自动邀请记录器参与对话。 合规性记录策略使用 [Microsoft PowerShell](./teams-powershell-overview.md) 进行管理，可应用于每个组织的租户、每个用户和安全组级别。 可找到有关 Microsoft Learn for [Meeting 策略](./meeting-policies-overview.md)、 [通话策略](./teams-calling-policy.md) 和  [组策略](./assign-policies-users-and-groups.md#assign-a-policy-to-a-group)的详细信息。

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

2. 创建符合性记录策略。

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

   请参阅 [Set-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/set-csteamscompliancerecordingpolicy)。

3. 将合规性记录策略分配给用户。

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   请参阅 [Grant-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/grant-csteamscompliancerecordingpolicy)。

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>用户体验

使用 Teams 客户端体验启用对通知的支持。 体验可以是视觉体验，也可以是音频体验。

**Teams 客户端 - 视觉通知**
- 桌面/Web
- 移动 (iOS/Android) 
- Teams 电话
- Teams 会议室

**其他终结点 - 音频通知**
- SIP 电话
- Skype for Business
- 音频会议 (拨入号码的默认或用户选择语言) 的音频通知
- PSTN 呼叫者使用 Teams 用户的默认语言 (音频通知) 

> [!NOTE]
> 会议模式呼叫队列不支持合规性录制。 请使用转移模式呼叫队列。
> 如果用户遇到 Internet 中断，并且使用 SBA 发出和接听 PSTN 呼叫，则合规性记录将不起作用。

## <a name="compliance-recording-for-teams-certification-programs"></a>Teams 认证计划的合规性记录

除了发布公开可用的 API，允许合作伙伴开发 CCaaS 解决方案并将其与 Teams 集成外，我们还为 Microsoft Teams 认证计划开发了合规性记录，以确保每个参与合作伙伴的解决方案已经过测试和验证，以提供他们期望从 Microsoft 解决方案获得的质量、兼容性和可靠性的保证。  

以下合作伙伴已认证其 Microsoft Teams 解决方案。<br/><br/>

|伙伴|解决方案网站 |
|:--|:--|
|ASC 技术 |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams](https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Dubber |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|Insightful 技术 |[https://insightfultechnology.com/teams/](https://insightfultechnology.com/teams/) |
|Mida Solutions |[https://www.midasolutions.com/recorder-for-teams/](https://www.midasolutions.com/recorder-for-teams/) |
|NICE 参与 |[https://www.nice.com/products/workforce-engagement/call-recording/air-and-engage](https://www.nice.com/products/workforce-engagement/call-recording/air-and-engage) |
|NICE NTR |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|橡树创新 |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |
|红框 |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/red-box-partners/microsoft-integration/compliance-recording-for-microsoft-teams)  |
|Theta Lake |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|橡树创新 |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |

<br/>
以下合作伙伴正在认证其 Microsoft Teams 解决方案。<br/><br/>

|伙伴|解决方案网站 |
|:--|:--|
|GuardRec |[https://www.guardrec.com/en/teams-compliance-recording/](https://www.guardrec.com/en/teams-compliance-recording/) |
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|Redwood Technologies |[https://www.contentguru.com/en-gb/solutions/needs/compliance-recording-MS-Teams/](https://www.contentguru.com/en-gb/solutions/needs/compliance-recording-MS-Teams/) |


此列表将随着更多合作伙伴加入并满足认证条件而更新。


## <a name="next-steps"></a>后续步骤

如果你是寻求加入认证计划的供应商，请填写 [此表单](https://aka.ms/CallingPlatformIntake) 作为下一步。 如果需要提供其他上下文和详细信息，请向 [Teamscategorypartner@microsoft.com](mailto:Teamscategorypartner@microsoft.com) 发送邮件。
