---
title: 规划生命周期管理
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 在本文中，你将了解如何进行相关规划，以便在 Teams 中实施生命周期管理功能。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 44be1d139fe37a34cad620cb449ac8bfe10eb99b
ms.sourcegitcommit: 43823358e7e1c1cece72a69a2ceb4eff86d3f927
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/10/2020
ms.locfileid: "48416925"
---
# <a name="plan-for-lifecycle-management-in-teams"></a>在 Teams 中规划生命周期管理

Teams 提供了一组丰富的工具，用于为组织实施协作生命周期管理流程。本文通过适当的问题指导 IT 专业人员确定其对生命周期管理的要求，以及用于满足这些要求的工具。 

规划生命周期管理很重要，因为这意味着你要制定有效地完成工作的规划。大多数项目都会经历开始、中间和结束。Teams 也是如此，但其构建和使用方式多种多样，因此，Teams 处在生命周期的哪个阶段并不总是很明显。制定生命周期管理规划可帮助你在组织的项目经历这些阶段时对其进行跟踪。

> [!Tip]
> 观看以下会话，详细了解 Microsoft Teams 中的生命周期：[Microsoft Teams 中的治理、管理和生命周期](https://aka.ms/teams-governance)


## <a name="lifecycle-concepts"></a>生命周期概念

以下概念和定义都会影响你为生命周期管理做出的决策。

**Teams**

_团队_ 是包含人员、内容和促进协作的工具的集合。 团队规定了其成员以及应用于这些成员的权限和策略。 Teams 是基于 Microsoft 365 组进行构建的，并且对 Microsoft 365 组成员身份的更改会同步到团队。 与其他 Microsoft 365 组一样，Teams 中自动预配了一个 Exchange 邮箱、一个 SharePoint 站点、一个 OneNote 笔记本以及 Microsoft 365 或 Office 365 中的其他资源。 [了解有关 Microsoft 365 组的详细信息。](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)

**频道**

频道是团队中的协作空间，在此完成实际工作。 每个频道均代表整个团队中一个不同的主题或工作流。 对于每个频道，都会自动在 SharePoint 站点上创建一个文件夹以用于存储共享到相应频道的所有文件，从而方便用户查找和处理其需要的文档。 也可以使用与特定工作流相关的应用程序扩展频道，例如，你可以将 Power BI 仪表板添加到某个频道以跟踪项目的某个方面的成功情况。

**团队访问类型**

这些类型确定哪些人可以加入团队：

-   _私人_ 团队限于团队所有者批准的团队成员。 这是大型组织中项目团队和虚拟团队的典型设置。
-   _公共_ 团队向组织中的所有人开放，可以直接加入。 要对处理不同项目的不同部门的人员都关注的主题进行协作，这很有用。 这是适合小型组织的默认设置。

**团队用户类型和管理员角色** 

团队用户类型确定团队成员拥有的控制权限：

-   *团队创建者* 有权在目录中创建组或团队。 管理员可以将此用户类型限定于一部分管理员或用户。 有关详细信息，请参阅[管理哪些人可以创建 Microsoft 365 组](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。 团队创建者会自动成为团队的所有者。
-   *团队所有者* 管理团队的成员身份和设置。 每个团队的团队所有者可以多达 100 人。
-   *团队成员* 是组织中加入团队的成员。
-   *来宾* 是组织外部的用户。 如果组织启用了[来宾访问](guest-access.md)，则可以邀请有电子邮件地址的任何人作为来宾。

> [!Note]
> 有关团队所有者和团队成员功能的详细信息，请参阅[在 Microsoft Teams 中分配角色和权限](assign-roles-permissions.md)一文。

团队管理员角色确定每个管理员角色拥有者可以使用的功能。 下表对此进行了介绍。

<table>
 <thead>
  <tr>
    <th width="0.5%"></th>
    <th width="15.5%">角色&nbsp;&nbsp;</th>
    <th width="25%">说明</th>
    <th width="60%">可以执行的任务（使用备注的工具）</th>
  </tr>
</thead>
<tbody>
   <tr>
    <td valign="top" colspan="2">Teams 服务管理员</td>
    <td valign="top">管理 Teams 服务，创建和管理 Microsoft 365 组</td>
    <td valign="top">管理会议，包括会议策略、配置和会议网桥<sup>1</sup><br><br>管理语音，包括通话策略、电话号码存量和分配、呼叫队列以及自动助理<sup>1</sup><br><br>管理消息，包括消息策略<sup>1</sup><br><br>管理组织范围的所有设置，包括联合、Teams 升级和 Teams 客户端设置<sup>1</sup><br><br>管理组织中的团队及其关联的设置，包括成员身份<sup>2</sup><br><br>查看用户配置文件页面，以及使用高级故障排除工具集解决用户通话质量问题<sup>3</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Teams 通信管理员</td>
<td valign="top">在 Microsoft Teams 服务中管理通话和会议功能</td>
<td valign="top">管理会议，包括会议策略、配置和会议网桥<sup>1</sup><br><br>管理语音，包括通话策略、电话号码存量和分配、呼叫队列以及自动助理<sup>1</sup><br><br>查看用户配置文件页面，以及使用高级故障排除工具集解决用户通话质量问题<sup>1</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Teams 通信专家</td>
<td valign="top">使用基本工具解决 Teams 中的通信问题</td>
<td valign="top">访问用户配置文件页面以对通话分析中的通话进行故障排除。 只能查看搜索的特定用户的用户信息。<sup>3</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Teams 通信支持工程师</td>
<td valign="top">使用高级工具解决 Teams 中的通信问题</td>
<td valign="top">访问用户配置文件页面以对通话分析中的通话进行故障排除。 可以查看完整的通话记录信息。<sup>3</sup></td>
</tr>
<tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3"><a href="https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell
">PowerShell—Skype for Business 模块</a>或 <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Microsoft Teams 管理中心</a></td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3"><a href="https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3">PowerShell—Microsoft Teams 模块</a>或 <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Microsoft Teams 管理中心</a></td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3">仅 <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">Microsoft Teams 管理中心</a></td>
</tr>
</tfoot>
</table>


## <a name="it-decisions-to-make-before-getting-started"></a>开始之前要做出的 IT 决策

在向组织推出 Teams 之前，应实施组织决定要求的所有治理策略。 其中可以包括命名约定、过期策略、保留策略等各项。 一般而言，在整个组织中扩展部署之前实施这些要求要容易得多。

有关详细信息，请参阅[在 Teams 中规划治理](plan-teams-governance.md)。

## <a name="teams-lifecycle-stages"></a>Teams 生命周期阶段

一般而言，团队会有与项目一致或实现某个目标的目的。 即使团队是基于某个共同的兴趣而建的，团队成员身份也可能会随着时间而变化，并且讨论内容可能也会变得过时 - 只是在不同的团队中以稍微不同的方式同样出现。

每个团队都会经历开始（创建团队和设置频道）、中间（使用团队，进行协作以符合工作流的节奏）以及（有时）结束（团队实现其目的，到达其有效期限终点）。 

有关详细信息，请参见[在 Microsoft Teams 管理中心中管理团队](manage-teams-in-modern-portal.md)。

### <a name="stage-1-beginning"></a>第 1 阶段：开始

#### <a name="create-the-team"></a>创建团队

第一步是定义团队的目标（可以是业务流程、组织结构或项目，或者只是创建一个开放的非结构化协作中心）。 定义团队目标的同时要确定合适的人员。 在切实可行的范围内，建议力求包含广泛的成员身份来培养开放性的协作。 

团队所有者邀请团队成员、设置团队图片和说明，并可以为各个成员设置权限。 

> [!Tip]
>  最好是至少确定两名团队所有者，以便考虑到缺席或重新分配的情况。

#### <a name="team-origins"></a>团队起源

可以采用各种方法创建团队，其中包括：

-   从头开始创建团队。 通过使用各个电子邮件别名或用户名添加成员，或者扩展通讯组列表。
-   基于某个现有团队创建团队，并将其频道配置和任何应用配置用作模板。 你也可以选择使用其成员身份列表。
-   将某个团队添加到某个现有 Microsoft 365 组，这还会为该团队提供访问其邮箱和 SharePoint 站点的权限。
-   使用 Microsoft Graph Teams API 或 PowerShell cmdlet 创建团队。 这些 API 可以根据全球通讯簿属性（例如，区域或部门）或业务流程（例如，客户端参与或教室名册）以编程方式创建团队。

可访问以下链接获取有关组织团队的详细信息：

-   [在 Teams 中组织团队的最佳做法](best-practices-organizing.md)
-   [部署聊天、团队、频道和应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
-   [部署会议](deploy-meetings-microsoft-teams-landing-page.md)
-   [部署云语音](cloud-voice-landing-page.md)


|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>团队的目的是什么？</li><li>哪些人属于团队？</li><li>团队是私人团队还是公共团队？</li><li>新成员是否可以添加自己，或由团队所有者添加新成员？</li><li>哪些人有权创建频道或添加选项卡、聊天机器人和连接器？</li></ul> |
| ![描述后续步骤的图标](media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>创建团队。</li><li>规划频道。</li></ul>|


#### <a name="set-up-channels"></a>设置频道

任何团队所有者或有相应权限的成员都可以在团队中创建频道。 考虑每个频道的目标（其中包括围绕项目展开的协作、主题讨论内容或共同兴趣的各方面）这一点很重要。 默认情况下，每个团队都包括一个常规频道；大多数团队需要更多频道，成员将会创建额外的频道。 可能会出现这些情况：随着新主题或项目的出现，频道集将会随之逐渐增加，讨论内容可能会超出其开始的频道的范围。

为了引起大家的兴趣，频道所有者可以发布欢迎消息、将相关文档上载到“**文件**”选项卡，或者向频道添加选项卡或连接器。 所有者也可设置频道说明，并可以“自动收藏”重要频道，以便默认为所有团队成员列出这些频道。

在创建频道名称之前，请先考虑频道名称，因为在团队中重命名频道不会重命名 SharePoint 文档库中的相应文件夹，这可能导致最终用户混淆。 

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>哪些初始频道将会添加到团队？</li><li>将会提供哪些有关添加新频道的指导（如果有）？ （它们将按项目、按主题或按其他内容进行设置？）</li></ul> |
| ![描述后续步骤的图标](media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>创建初始频道</li><li>发布欢迎消息。</li><li>开始协作。</li></ul>|

### <a name="stage-2-middle"></a>第 2 阶段：中间

随着团队合作的开始，团队成员身份和频道层次结构可能会开始发展变化。 除非需要严格控制和锁定团队，否则，建议鼓励进行探索，即使这会导致终结也是如此。 随着用户越来越适应，他们可以尝试使用 \@团队提及功能、将频道标记为收藏项以及使用“常规”频道以习惯使用发布功能。 每个团队都不同；可通过使用来引导设计的发展变化。 可通过 Teams 报告功能来监控团队的使用情况和运行状况。

随着在 Teams 中启动和持续进行关键的组通信，信任、宽容和协作精神会随之逐渐增强。 团队成员会发现组对话优于一对一聊天的实用性。 各个团队都倾向于借助 Giphy 和贴纸等有趣的功能发展自己的个性。 同时，任何时候发生恶劣或粗鲁行为，务必要进行阻止。

由于团队是有活力的机体，偶尔需要对其进行检查和照顾。 下面提供了一些最佳做法：

- 在其开始衰落时安排支持者维持其使用，以及发现并传播有创意的新行为。 
- 妥善地管理来宾，确保来宾的访问在业务需求终止时终止。
- 鼓励成员使用线程化对话和主题行，以通过滚动频道来提高可见性和关注度。
- 允许频道随着业务需求而发展变化，根据需要添加新频道，允许旧频道停止使用（或者，如果这些频道包含敏感或临时性数据，根据你的保留要求，考虑将其存档或删除）。
- 随着组扩大或出现基于兴趣的领域时，创建新团队。
- 尝试使用不同的频道协作，例如，频道会议或围绕文档展开的选项卡对话。
- 使用 Microsoft Teams 移动应用来提高参与度。

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>将由谁监控使用情况以发现问题？</li><li>将使用哪些指标来确定团队运行是否正常？</li><li>确定已达到其有效期限终点的任何团队。</li><li>确定仍在用于某个目的但需要增强活力的不正常团队。</li></ul> |
| ![描述后续步骤的图标](media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>实施流程以监控各个团队运行状况。</li></ul>|

### <a name="stage-3-end"></a>第 3 阶段：结束

当团队的工作完成时，务必要正式确认其已结束。 这是向团队成员告知结束，此外，也防止任何人访问已过时的陈旧信息。 你可以使用团队本身完成结束事项，例如，事后剖析和执行摘要。

你可以删除你知道不需要的团队（例如，只是为了测试而创建的团队，或包含敏感数据的团队）。 团队实际上是通过“软删除”进行删除的，IT 最长可以在 21 天内将其恢复（Microsoft 365 组是 30 天）。 删除团队不会影响按照合规性策略保留的任何聊天或内容。 频道也具有“软删除”，并且可在删除后的最长 21 天内恢复。 删除频道不会从 SharePoint 文档库中删除文件夹或其内容。

你还可以使用过期和保留策略以及存档功能来减少公开不再使用或其所有者已离开组织的团队。

应用于 Teams 或相关服务（如 SharePoint）的保留策略可能会禁止删除团队。 此外，请考虑团队中的内容通常不仅仅是 SharePoint 文档库中的文件；它是对话、Planner 版块、Wiki、表单结果、录制的会议、OneNote 笔记本以及其他各种内容。

有关设置过期和保留策略的信息，请参阅 [Microsoft Teams 中的安全性和合规性概述](security-compliance-overview.md)。

|    |     |
|-----------|------------|
| ![描述决策点的图标](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>定义团队到达其期限终点时的情况。</li><li>决定是否使团队的内容保留可用，以及保留多长时间。</li></ul> |
| ![描述后续步骤的图标](media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>记录最佳做法以及经验与教训。</li><li>存档数据（如果需要）。</li></ul>|

## <a name="related-topics"></a>相关主题

[Teams 的管控快速入门](teams-adoption-governance-quick-start.md)
