---
title: 在 Teams 中规划生命周期管理 - Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 09/26/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 了解如何在 Teams 中规划实施生命周期管理规划功能。
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d4c8d99dcc3e1c96e5fbfce942b9def6d0db952
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754773"
---
# <a name="plan-for-lifecycle-management-in-teams"></a>在 Teams 中规划生命周期管理

Teams 提供了一组丰富的工具，用于为组织实施协作生命周期管理流程。本文通过适当的问题指导 IT 专业人员确定其对生命周期管理的要求，以及用于满足这些要求的工具。 

规划生命周期管理很重要，因为这意味着你要制定有效地完成工作的规划。大多数项目都会经历开始、中间和结束。团队也是如此，但其构建和使用方式多种多样，因此，团队处在生命周期的哪个阶段并不总是很明显。制定生命周期管理规划可帮助你在组织的项目经历这些阶段时对其进行跟踪。

> [!Tip]
> 观看以下会话，详细了解 Microsoft Teams 中的生命周期：[Microsoft Teams 中的治理、管理和生命周期](https://aka.ms/teams-governance)


## <a name="lifecycle-concepts"></a>生命周期概念

以下概念和定义都会影响你为生命周期管理做出的决策。

**Teams**

A _team_ is a collection of people, content, and tools that facilitate collaboration. A team defines who its members are, and the permissions and policies that apply to those members. Teams are built on Office 365 Groups, and changes to Office 365 group membership sync to the team. Like other Office 365 Groups, Teams come auto-provisioned with an Exchange mailbox, a SharePoint site, a OneNote notebook, and other assets within Office 365. [Learn more about Office 365 Groups](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

**频道**

Channels are the collaboration spaces within a team where the actual work is done. Each channel represents a different topic or workstream within the overall team. For each channel, a folder is automatically created on the SharePoint site to store all files shared to that channel, making it easy for users to find and work on the documents they care about. Channels can also be extended with apps that are relevant to the particular workstream—for example, you can add a Power BI dashboard to a channel to track the success of one aspect of your project.

**团队访问类型**

这些类型确定哪些人可以加入团队：

-   _Private_ teams are restricted to team members approved by the team owner(s). This is a typical setting for project teams and virtual teams in a large organization.
-   _Public_ teams are open for anyone in the organization to join directly. This is useful for collaboration on topics of general interest to people in different departments working on different projects. This is a good default setting for smaller organizations.

**团队用户类型和管理员角色** 

团队用户类型确定团队成员拥有的控制权限：

-   _Team creator_ has permissions to create a group or team in the directory. The admin can constrain this user type to a subset of admins or users. For more information, see [Manage who can create Office 365 Groups](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618). 
-   _Team owner_ manages membership and settings for the team. There can be as many as 10 team owners per team.
-   _团队成员_是组织中加入团队的成员。
-   _Guest_ is a user who’s external to your organization. Anyone with an email address can be invited as a guest if your organization has enabled [guest access](guest-access.md).

> [!Note]
> 有关团队所有者和团队成员功能的详细信息，请参阅[在 Microsoft Teams 中分配角色和权限](assign-roles-permissions.md)一文。

Teams admin roles determine what capabilities each admin role holder has. These are described in the following table.

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
    <td valign="top">管理 Teams 服务，创建和管理 Office 365 组</td>
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
<td valign="top">Access to the user profile page for troubleshooting calls in Call Analytics. Can only view user information for the specific user being searched for.<sup>3</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Teams 通信支持工程师</td>
<td valign="top">使用高级工具解决 Teams 中的通信问题</td>
<td valign="top">Access to the user profile page for troubleshooting calls in Call Analytics. Can view the full call record information.<sup>3</sup></td>
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

Before you roll Teams out to your organization, implement any governance policies that your organization has decided it requires. These can include items like naming conventions, expiration policies, retention policies, and more. Generally speaking, it’s much easier to implement these requirements prior to scaling your deployment across your organization.

有关详细信息，请参阅[在 Teams 中规划治理](plan-teams-governance.md)。

## <a name="teams-lifecycle-stages"></a>Teams 生命周期阶段

Generally speaking, a team has a purpose that’s aligned with a project or accomplishing a goal. Even if a team was formed based on a shared interest, the team membership will probably change over time and the discussion might grow stale—only to surface again in a slightly different way in a different team.

每个团队都会经历开始（创建团队和设置频道）、中间（使用团队，进行协作以符合工作流的节奏）以及（有时）结束（团队实现其目的，到达其有效期限终点）。 

有关详细信息，请参见[在 Microsoft Teams 管理中心中管理团队](manage-teams-in-modern-portal.md)。

### <a name="stage-1-beginning"></a>第 1 阶段：开始

#### <a name="create-the-team"></a>创建团队

The first step is to define the goal of the team (which can range from business processes to org structure to projects, or simply creating an open, unstructured collaboration hub). Defining the team goal goes hand in hand with identifying the right people. As far as practicable, it’s a good idea to foster open collaboration by aiming for broad membership. 

团队所有者邀请团队成员、设置团队图片和说明，并可以为各个成员设置权限。 

> [!Tip]
>  最好是至少确定两名团队所有者，以便考虑到缺席或重新分配的情况。

#### <a name="team-origins"></a>团队起源

可以采用各种方法创建团队，其中包括：

-   Create the team from scratch. Add members by using individual email aliases or usernames, or expand a distribution list.
-   Create the team from an existing team, and use its channel configuration and any app configuration as a template. You can optionally also use its membership list.
-   将某个团队添加到某个现有 Office 365 组，这还会为该团队提供访问其邮箱和 SharePoint 站点的权限。
-   Use the Microsoft Graph Teams APIs or PowerShell cmdlets to create teams. The APIs can programmatically create teams based on Global Address Book attributes (such as region or department) or business processes (client engagements or classroom rosters, for example).

可访问以下链接获取有关组织团队的详细信息：

-   [在 Teams 中组织团队的最佳做法](best-practices-organizing.md)
-   [部署聊天、团队、频道和应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
-   [部署会议](deploy-meetings-microsoft-teams-landing-page.md)
-   [部署云语音](cloud-voice-landing-page.md)


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>团队的目的是什么？</li><li>哪些人属于团队？</li><li>团队是私人团队还是公共团队？</li><li>新成员是否可以添加自己，或由团队所有者添加新成员？</li><li>哪些人有权创建频道或添加选项卡、聊天机器人和连接器？</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>创建团队。</li><li>规划频道。</li></ul>|


#### <a name="set-up-channels"></a>设置频道

任何团队所有者或有相应权限的成员都可以在团队中创建频道。 考虑每个频道的目标（其中包括围绕项目展开的协作、主题讨论内容或共同兴趣的各方面）这一点很重要。 默认情况下，每个团队都包括一个常规频道；大多数团队需要更多频道，成员将会创建额外的频道。 可能会出现这些情况：随着新主题或项目的出现，频道集将会随之逐渐增加，讨论内容可能会超出其开始的频道的范围。

为了引起大家的兴趣，频道所有者可以发布欢迎消息、将相关文档上载到“**文件**”选项卡，或者向频道添加选项卡或连接器。 所有者也可设置频道说明，并可以“自动收藏”重要频道，以便默认为所有团队成员列出这些频道。

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>哪些初始频道将会添加到团队？</li><li>将会提供哪些有关添加新频道的指导（如果有）？ （它们将按项目、按主题或按其他内容进行设置？）</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>创建初始频道</li><li>发布欢迎消息。</li><li>开始协作。</li></ul>|

### <a name="stage-2-middle"></a>第 2 阶段：中间

随着团队合作的开始，团队成员身份和频道层次结构可能会开始发展变化。 除非需要严格控制和锁定团队，否则，建议鼓励进行探索，即使这会导致终结也是如此。 随着用户越来越适应，他们可以尝试使用 \@团队提及功能、将频道标记为收藏项以及使用“常规”频道以习惯使用发布功能。 每个团队都不同；可通过使用来引导设计的发展变化。 可通过 Teams 报告功能来监控团队的使用情况和运行状况。

随着在 Teams 中启动和持续进行关键的组通信，信任、宽容和协作精神会随之逐渐增强。 团队成员会发现组对话优于一对一聊天的实用性。 各个团队都倾向于借助 Giphy 和贴纸等有趣的功能发展自己的个性。 同时，任何时候发生恶劣或粗鲁行为，务必要进行阻止。

由于团队是有活力的机体，偶尔需要对其进行检查和照顾。 下面提供了一些最佳做法：

-   在其开始衰落时安排支持者维持其使用，以及发现并传播有创意的新行为。 
-   妥善地管理来宾，确保来宾的访问在业务需求终止时终止。
-   允许频道随着业务需求而发展变化，根据需要添加新频道，允许旧频道停止使用（或者，如果这些频道包含敏感或临时性数据，根据你的保留要求，考虑将其存档或删除）。
-   随着组扩大或出现基于兴趣的领域时，创建新团队。
-   尝试使用不同的频道协作，例如，频道会议或围绕文档展开的选项卡对话。

如果团队开始墨守成规，请考虑：

-   推动在团队中进行通信，而不是电子邮件。
-   使用移动应用程序提高参与率。
-   精简频道数量。

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>将由谁监控使用情况以发现问题？</li><li>将使用哪些指标来确定团队运行是否正常？</li><li>确定已达到其有效期限终点的任何团队。</li><li>确定仍在用于某个目的但需要增强活力的不正常团队。</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>实施流程以监控各个团队运行状况。</li></ul>|

### <a name="stage-3-end"></a>第 3 阶段：结束

当团队的工作完成时，务必要正式确认其已结束。 这是向团队成员告知结束，此外，也防止任何人访问已过时的陈旧信息。 你可以使用团队本身完成结束事项，例如，事后剖析和执行摘要。

你可以删除你知道不需要的团队（例如，只是为了测试而创建的团队，或包含敏感数据的团队）。 团队实际上是通过“软删除”进行删除的，IT 最长可以在 21 天内将其恢复（Office 365 组是 30 天）。 删除团队不会影响按照合规性策略保留的任何聊天或内容。

你还可以使用过期和保留策略以及存档功能来减少公开不再使用或其所有者已离开组织的团队。

有关设置过期和保留策略的信息，请参阅 [Microsoft Teams 中的安全性和合规性概述](security-compliance-overview.md)。

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>决策点|<ul><li>定义团队到达其期限终点时的情况。</li><li>决定是否使团队的内容保留可用，以及保留多长时间。</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>记录最佳做法以及经验与教训。</li><li>存档数据（如果需要）。</li></ul>|

