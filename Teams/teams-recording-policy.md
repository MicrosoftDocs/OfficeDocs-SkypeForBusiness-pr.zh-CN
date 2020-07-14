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
ms.openlocfilehash: 48cc430ea864614a306725958b56dda934e00eef
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121642"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Callings & 会议的基于团队政策的录制简介

基于策略的录制使 Microsoft 团队可以通过管理策略自动记录和捕获针对后续处理和保留（如相关的公司或规章策略所需）进行呼叫和会议的适用于 stipulate 的 Microsoft 团队。

团队已得到改进，可支持第三方录制解决方案的集成，包括平台功能、用户体验和管理界面，以便为配置、管理、记录、存储和分析团队通信提供端到端的解决方案所需。 这包括用于录制的通信平台 Api 和事件，其中提供：

- 跨设备的无缝、高质量媒体捕获和音频、视频、屏幕共享和聊天的所有受支持的终结点。

- 支持团队用户与支持的呼叫终结点之间的交互捕获（团队、团队 Mobile、Skype for business、PSTN）

- 针对合规性录制的新管理策略，包括与现有团队的集成管理呼叫和会议工具和策略

- 为具有单独许可证的团队用户启用

合规性录制解决方案集成功能还在[<span class="underline">合规性录制和 Microsoft 团队会话</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions)的 Ignite 2019 中查看。

## <a name="teams-interaction-recording-overview"></a>团队交互录制概述

交互录制使用案例可以有效地分成四种主要类别的录制功能-方便、功能、组织和合法截取，如图所示：

![显示交互录制内容和原因的屏幕截图。](media/recording-taxonomy.png "图像显示 "录制" 类别。")

每个类别都需要对启动录制的方式有不同的要求、录制的内容、录制的位置、通知的人员、控制访问的人员以及如何处理保留。

|                        | 参考        | 功能         | 组织-常规      | 组织级管控 | 合法截距   |
| ---------------------- | ------------------ | ------------------ | ------------------ | --------------- | ------------------ |
| 启动              | 用户               | 应用/解决方案       | 管理员（系统）     | 管理员（系统）  | LEA                |
| 目标                 | 每次通话/会议 | 每次通话/会议 | 每次通话/会议 | 每用户        | 每个终结点/已完成 |
| 存储所有者          | 用户               | 应用                | Iis              | 符合      | LEA                |
| 需要通知？ | 必需                | 是                 | 是                 | 是             | 否                 |
| 访问所有者           | 用户               | 应用                | Iis              | 符合      | LEA                |
| 保留策略？      | 可选           | 必需                | 是                 | 是              | 是                |

团队提供各种功能，用于会议和实时事件的[<span class="underline">便利</span>](https://docs.microsoft.com/microsoftteams/cloud-recording)和功能录制。 组织录制意味着，当应根据相关的公司或规章策略的要求自动记录和捕获在后续处理和保留期间进行的呼叫和会议时，通过管理策略将使用团队进行呼叫和会议的组织 stipulate。 此策略下的用户将知道他们正在录制与团队的数字交互，但不能禁用录制，并且在交互完成后将无法访问录制。 在电子数据展示、法律封存和其他公司保留使用中，该记录将成为组织存档的一部分，以供合规性和法律人员使用。

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
<td>录制的用户</td>
<td><ul>
<li><p>正在进行录制时收到通知。</p></li>
<li><p>当策略和/或记录器错误导致调用行为发生更改时收到通知。</p></li>
</ul></td>
</tr>
<tr class="even">
<td>通信管理员</td>
<td><ul>
<li><p>了解为什么以及如何向团队用户/终结点应用/强制录制策略。</p></li>
<li><p>配置和维护组织的团队记录策略。</p></li>
<li><p>监控和解决团队通话和会议与录制相关的问题。</p></li>
<li><p>针对使用情况、质量和可靠性，支持内部合规性监察官和运营分析。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>合规性监察官</td>
<td><ul>
<li><p>按所需方式收集所有团队通信，以满足适当区域边界的合规性义务。</p></li>
<li><p>根据与通信相关的元数据或交互内容搜索交互。 常见示例包括：</p>
<ul>
<li><p><strong>元数据</strong> -参与者、时间、方向、已拨号码、原始电话号码、自定义业务数据</p></li>
<li><p><strong>内容</strong>-脚本、情绪、拼音、相关交互</p></li>
</ul></li>
<li><p>分析并与收集的通信进行交互，包括在收集交互时监视交互的能力。</p></li>
<li><p>确保收集的通信的安全性，并防止所有阶段被篡改。</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>解决方案体系结构概述

合规性录制解决方案与团队集成，如下图所示：

![显示团队自定义应用设置的屏幕截图](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "图像显示发送和接收团队会议或通话时的流程。")

## <a name="recorder"></a>盘

合规性录制解决方案的核心组件是录像机。
录音机构建为[<span class="underline">利用 microsoft 的通信平台</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview)的可伸缩基于 Azure 的服务（bot），并使用 microsoft Graph 注册为应用程序。 记录器提供与团队通话和会议[<span class="underline">通信平台 api</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0)的直接交互，并提供媒体接收的终结点。

提供了一个[<span class="underline">示例合规性记录器应用程序，该应用程序</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot)显示如何配置 bot、创建应用实例并分配合规性策略。 该示例还包含用于录制特定交互（如处理[<span class="underline">传入呼叫</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)   路由、[<span class="underline">更改录制状态</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)和[<span class="underline">删除正在录制的用户</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)）的 API 用法的示例。
有关[<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http)和[<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0)，可在此处找到有关特定 api 的图形文档。

记录器服务的确切实现因合作伙伴而异，但必须设计为支持多个刻录机才能实现高可用性和部署的地理位置分布，以减少团队与记录器之间的延迟。 此外，该刻录机自身的设计应考虑恢复性和冗余。

合作伙伴必须先确认 Microsoft Graph 通信 Api 和 Sdk 的最低版本，然后再提交其认证解决方案，以确保符合性录制集成的所有要求均受支持。

符合性录制方案的基本要求有两个特定要求：

- 录像机 bot 必须部署在 Azure 中

- 录像机 bot 必须在 Azure 中的 Windows VM 上运行

Azure 和 Windows VM 要求仅适用于 "团队 Bot" 组件，这意味着合作伙伴可以实现其选择的其余平台，前提是它们可以满足符合性录制的相关性能和功能要求。

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>合规性录制策略分配和预配

IT 管理员可以通过创建和分配合规性录制策略来确定要录制的用户以及将用于每个用户的记录器。 在通信交互发生时，会根据这些策略的配置自动邀请刻录机参与对话。 合规性录制策略使用[<span class="underline">Microsoft Powershell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)进行管理，并且可应用于每个组织的租户、每用户和安全组级别。 你可以在 Microsoft 文档中查找有关[<span class="underline">会议策略</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams)、[<span class="underline">呼叫策略</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy)和[<span class="underline">组策略</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)的详细信息。

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

2. 创建合规性录制策略。

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

3. 将合规性录制策略分配给用户。

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span class="underline">授权-CsTeamsComplianceRecordingPolicy</span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>用户体验

使用团队客户体验启用通知支持。 体验可以是视觉的，也可以是音频。

**团队客户端-视觉通知**
- 桌面/web
- 手机（iOS/Android）
- 团队手机
- 团队聊天室

**其他终结点-音频通知**
- SIP 电话
- Skype for Business
- 音频会议
- PSTN 呼叫者

## <a name="compliance-recording-for-teams-certification-programs"></a>团队认证计划的合规性录制

除了发布可供合作伙伴开发和集成 CCaaS 解决方案的公共 Api 之外，我们还制定了 Microsoft 团队认证计划的合规性录制，以确保每个参与合作伙伴的解决方案都经过测试和验证，以提供他们所期望的各种 Microsoft 解决方案的质量、兼容性和可靠性。  

以下合作伙伴正在验证其 Microsoft 团队解决方案的过程。  

|配偶|解决方案网站 |
|:--|:--|
|ASC 技术 |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|良好 |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|红色框 |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

此列表将随着更多合作伙伴加入和满足认证标准而更新。

## <a name="next-steps"></a>后续步骤

如果您是希望加入认证计划的供应商，请邮寄<a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>。
