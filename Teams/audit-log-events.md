---
title: 在 Microsoft Teams 中搜索事件的审核日志
description: 了解如何从Microsoft Purview 合规门户的审核日志中检索 Microsoft Teams 数据。
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- tier1
- purview-compliance
- M365-collaboration
- audit
f1.keywords:
- NOCSH
ms.reviewer: anwara
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7219ee11f6818890b8be34f42f76dfa26ef0d12
ms.sourcegitcommit: 5e0900ed7a21ed4e854cc00dbfb4ae4ff2372262
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2023
ms.locfileid: "69950439"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>在 Microsoft Teams 中搜索事件的审核日志

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

审核日志可帮助你调查 Microsoft 365 服务中的特定活动。 对于 Microsoft Teams，下面是审核的一些活动：

- 团队创建
- 团队删除
- 添加频道
- 已删除的通道
- 已更改通道设置

有关审核 Teams 活动的完整列表，请参阅 [Teams 活动](#teams-activities)和 Teams 活动中的 [排班](#shifts-in-teams-activities)。

> [!NOTE]
> 还会记录来自专用频道的审核事件，就像团队和标准频道一样。

## <a name="turn-on-auditing-in-teams"></a>在 Teams 中启用审核

必须先在Microsoft Purview 合规门户中启用审核，然后才能查看审核数据。 有关详细信息，请参阅 [打开或关闭审核](/microsoft-365/compliance/turn-audit-log-search-on-or-off)。

> [!IMPORTANT]
> 审核数据仅在启用审核时可用。

## <a name="retrieve-teams-data-from-the-audit-log"></a>从审核日志检索 Teams 数据

1. 若要检索 Teams 活动的审核日志，请转到 <https://compliance.microsoft.com> 并选择“ **审核**”。

2. 在 **“搜索** ”页上，筛选要审核的活动、日期和用户。

3. 将结果导出到 Excel 以供进一步分析。

有关分步说明，请参阅 [在合规中心搜索审核日志](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log)。

> [!IMPORTANT]
> 仅当审核处于打开状态时，审核数据才显示在审核日志中。

审核记录在审核日志中保留和可搜索的时间长度取决于 Microsoft 365 或 Office 365 订阅，特别是分配给用户的许可证类型。 若要了解详细信息，请参阅 [安全&合规中心服务说明](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)。

## <a name="tips-for-searching-the-audit-log"></a>有关搜索审核日志的提示

下面是在审核日志中搜索 Teams 活动的提示。

:::image type="content" alt-text="合规中心的审核日志搜索页的屏幕截图" source="media/audit-log-search-page.png" lightbox="media/audit-log-search-page.png":::

- 可以通过单击一个或多个活动旁边的复选框来选择要搜索的特定活动。 如果选择了某个活动，可以单击该活动以取消选择。 还可以使用搜索框显示包含所键入关键字的活动。

  ![审核日志搜索页上的活动下拉列表的屏幕截图](media/audit-log-search.png)

- 若要显示使用 cmdlet 运行的活动的事件，请在“**活动**”列表中选择“**显示所有活动的结果**”。 如果知道这些活动的操作名称，请在搜索框中键入它以显示活动，然后选择它。

- 若要清除当前搜索条件，请单击“ **全部清除**”。 日期范围将返回过去七天的默认值。

- 如果找到 5，000 个结果，则可能假设有 5，000 多个事件符合搜索条件。 可以优化搜索条件并重新运行搜索以返回更少的结果，也可以通过选择“**导出** > 下载所有结果”来导出 **所有搜索结果**。 有关导出审核日志的分步说明，请参阅 [将搜索结果导出到文件](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#step-3-export-the-search-results-to-a-file)。

查看 [此视频](https://www.youtube.com/embed/UBxaRySAxyE) ，了解如何使用音频日志搜索。 加入 Teams 项目经理 Ansuman Acharya，他演示了如何对 Teams 执行审核日志搜索。

## <a name="teams-activities"></a>Teams 活动

下面是 Microsoft 365 审核日志中 Teams 中为用户和管理员活动记录的所有事件的列表。 该表包括“ **活动”** 列中显示的友好名称，以及导出搜索结果时显示在审核记录详细信息和 CSV 文件中的相应操作的名称。

|**友好名称**|**操作**|**说明**|
|:----------------|:------------|:--------------|
|向团队添加了机器人|BotAddedToTeam|用户将机器人添加到团队。|
|添加频道|ChannelAdded|用户向团队添加频道。|
|添加了连接器|ConnectorAdded|用户向通道添加连接器。|
|添加了有关 Teams 会议 <sup>2</sup> 的详细信息|MeetingDetail|Teams 添加了有关会议的信息，包括开始时间、结束时间和加入会议的 URL。|
|添加了有关会议参与者 <sup>2</sup> 的信息|MeetingParticipantDetail|Teams 添加了有关会议参与者的信息，包括每个参与者的用户 ID、参与者加入会议的时间以及参与者离开会议的时间。|
|添加了成员|MemberAdded|团队所有者将成员添加到团队、频道或群组聊天。|
|添加了选项卡|TabAdded|用户向频道添加选项卡。|
| 应用的敏感度标签 | SensitivityLabelApplied | 用户或会议组织者向 Teams 会议应用了敏感度标签。 |
|已更改通道设置|ChannelSettingChanged|当团队成员执行以下活动时，将记录 ChannelSettingChanged 操作。 对于其中每个活动，审核日志搜索结果的 **“项** ”列中会显示对已更改的设置的说明 (括号中显示。 <ul><li>更改团队频道的名称 (**频道名称**) </li><li>更改团队频道的说明 (**频道说明**) </li> </ul>|
|更改了组织设置|TeamsTenantSettingChanged|当Microsoft 365 管理中心中的全局管理员执行以下活动时，将记录 TeamsTenantSettingChanged 操作。 这些活动会影响组织范围的 Teams 设置。 若要了解详细信息，请参阅 [为组织管理 Teams 设置](enable-features-office-365.md)。 <br>对于其中每个活动，已更改的设置的说明 (显示在圆括号中，) 显示在审核日志搜索结果的 **“项”** 列中。<ul><li>为组织启用或禁用 Teams (**Microsoft Teams**) 。</li><li>为组织启用或禁用 Microsoft Teams 和 Skype for Business 之间的互操作性， (**Skype for Business互操作性**) 。</li><li>启用或禁用 Microsoft Teams 客户端中的组织结构图视图 (**组织图表视图**) 。</li><li>启用或禁用团队成员安排私人会议的功能， (**私人会议安排**) 。</li><li>启用或禁用团队成员 (频道会议 **安排**) 的功能。</li><li>启用或禁用 Teams 会议中的视频通话 (**Skype 会议** 的视频) 。</li><li>为组织启用或禁用 Microsoft Teams 会议中的屏幕共享 (**Skype 会议) 屏幕共享** 。</li><li>启用或禁用将名为 Giphys) 的动画图像 (添加到 Teams 对话 (**动画图像**) 的功能。</li><li>更改组织 (**内容分级) 的内容分级** 设置。 内容分级限制可在对话中显示的动画图像的类型。</li><li>启用或禁用团队成员将可自定义图像 () 从 Internet 添加到团队对话的功能， (**来自 Internet) 的可自定义图像** 。</li><li>启用或禁用团队成员将可编辑图像 (称为贴纸) 添加到团队对话 (**可编辑图像**) 的功能。</li><li>启用或禁用团队成员在 Microsoft Teams 聊天和频道中使用机器人的功能， (**组织范围的机器人)**。</li><li>为 Microsoft Teams 启用特定机器人。 这不包括 T-Bot，它是 Teams 帮助机器人，在为组织启用机器人时可用， (**单个机器人**) 。</li><li>启用或禁用团队成员 (扩展或选项卡) 添加 **扩展或选项卡** 的功能。</li><li>启用或禁用 Microsoft Teams 专有机器人的旁加载 (**机器人) 的旁加载** 。</li><li>启用或禁用用户将电子邮件发送到 Microsoft Teams 频道 (**频道电子邮件**) 的功能。</li></ul>|
|更改了团队中成员的角色|MemberRoleChanged|团队所有者更改团队中成员的角色。 以下值指示分配给用户的角色类型。 <br><br>**1** - 指示成员角色。<br>**2** - 指示所有者角色。<br>**3** - 指示来宾角色。<br><br>Members 属性还包括组织名称和成员的电子邮件地址。|
|更改了团队设置|TeamSettingChanged|当团队所有者执行以下活动时，将记录 TeamSettingChanged 操作。 对于其中每个活动，已更改的设置的说明 (显示在圆括号中，) 显示在审核日志搜索结果的 **“项”** 列中。<ul><li>更改团队的访问类型。 团队可以设置为专用或公共 (**团队访问类型**) 。 当团队是专用 (默认设置) 时，用户只能通过邀请访问团队。 当团队是公开的时，任何人都可以发现它。</li><li>更改团队 (**团队分类**) 的信息分类。 例如，团队数据可分为高业务影响、中等业务影响或低业务影响。</li><li>更改团队名称 (**团队名称**) 。</li><li>更改团队说明 (团队 **说明**) 。</li><li>对团队设置所做的更改。 若要访问这些设置，团队所有者可以右键单击团队，选择 **“管理团队**”，然后单击“ **设置”** 选项卡。对于这些活动，已更改的设置的名称将显示在审核日志搜索结果的 **“项** ”列中。</li></ul>|
| 已更改敏感度标签 | SensitivityLabelChanged | 用户更改了 Teams 会议中的敏感度标签。 |
|创建了聊天 <sup>1、 </sup> <sup>2</sup>|ChatCreated|已创建 Teams 聊天。|
|已创建团队|TeamCreated|用户创建团队。|
|已删除邮件|MessageDeleted|聊天或频道中的消息已删除。|
|删除了所有组织应用|DeletedAllOrganizationApps|从目录中删除了所有组织应用。|
|已删除的应用|AppDeletedFromCatalog|已从目录中删除应用。|
|已删除的通道|ChannelDeleted|用户从团队中删除频道。|
|已删除的团队|TeamDeleted|团队所有者删除团队。|
|在 Teams 中使用 URL 链接编辑了邮件|MessageEditedHasLink|用户在 Teams 中编辑邮件并添加指向该邮件的 URL 链接。|
|导出的消息 <sup>1、 </sup> <sup>2</sup>|MessagesExported|聊天或频道消息已导出。|
|未能验证对共享频道<sup>3</sup> 的邀请|FailedValidation|用户响应对共享频道的邀请，但邀请验证失败。|
|提取的聊天 <sup>1、 </sup> <sup>2</sup>|ChatRetrieved|检索了 Microsoft Teams 聊天。|
|提取消息<sup>1、 </sup> <sup>2</sup> 的所有托管内容|MessageHostedContentsListed|已检索消息中的所有托管内容，例如图像或代码片段。|
|已安装的应用|AppInstalled|已安装应用。|
|对卡执行的操作|PerformedCardAction|用户在聊天中对自适应卡片执行了操作。 自适应卡片通常由机器人用来允许在聊天中丰富地显示信息和交互。 <br/><br/>**注意：** 审核日志中仅提供对聊天中的自适应卡片的内联输入操作。 例如，当用户在由投票机器人生成的自适应卡片上的频道对话中提交投票响应时。 将打开对话框的用户操作（例如“查看结果”）或对话中的用户操作在审核日志中不可用。|
|已发布新消息 <sup>1、 </sup> <sup>2</sup>|MessageSent|新消息已发布到聊天或频道。|
|已发布的应用|AppPublishedToCatalog|应用已添加到目录中。|
|阅读消息 <sup>1、 </sup> <sup>2</sup>|MessageRead|检索了聊天或频道的消息。|
|读取消息 <sup>1、 </sup> <sup>2</sup> 的托管内容|MessageHostedContentRead|已检索消息中的托管内容，例如图像或代码片段。|
|从团队中删除了机器人|BotRemovedFromTeam|用户从团队中删除机器人。|
|已删除连接器|ConnectorRemoved|用户从通道中删除连接器。|
|已删除的成员|MemberRemoved|团队所有者从团队、频道或群组聊天中删除成员。|
| 已删除敏感度标签 | SensitivityLabelRemoved | 用户从 Teams 会议中删除了敏感度标签。 |
|删除了团队频道<sup>3</sup> 的共享|TerminatedSharing|团队或频道所有者禁用了共享频道的共享。|
|恢复了团队频道<sup>3</sup> 的共享|SharingRestored|团队或频道所有者为共享频道重新启用共享。|
|已删除选项卡|TabRemoved|用户从频道中删除选项卡。|
|已响应共享频道<sup>3</sup> 的邀请|InviteeResponded|用户响应了共享频道邀请。|
|响应了对共享频道<sup>3</sup> 的被邀请者响应|ChannelOwnerResponded|频道所有者响应了响应共享频道邀请的用户的响应。|
|检索到的消息 <sup>1、 </sup> <sup>2</sup>|MessagesListed|检索了来自聊天或频道的消息。|
|在 Teams 中使用 URL 链接发送了消息|MessageCreatedHasLink|用户在 Teams 中发送包含 URL 链接的消息。|
|已发送消息创建更改通知 <sup>1、 </sup> <sup>2</sup>|MessageCreatedNotification|已发送更改通知，通知订阅的侦听器应用程序收到新消息。|
|发送消息删除 <sup>更改通知 1、 </sup> <sup>2</sup>|MessageDeletedNotification|已发送更改通知，通知订阅的侦听器应用程序已删除的消息。|
|已发送消息更新 <sup>1、 </sup> <sup>2</sup> 的更改通知|MessageUpdatedNotification|已发送更改通知，通知订阅的侦听器应用程序更新的消息。|
|已发送共享频道<sup>3</sup> 邀请|InviteSent|频道所有者或成员向共享频道发送邀请。 如果频道策略配置为与外部用户共享频道，则可以向组织外部的人员发送共享频道邀请。|
|已订阅消息更改通知 <sup>1、 </sup> <sup>2</sup>|SubscribedToMessages|订阅由侦听器应用程序创建，用于接收消息的更改通知。|
|卸载的应用|AppUninstalled|应用已卸载。|
|已更新的应用|AppUpdatedInCatalog|已在目录中更新应用。|
|更新了聊天 <sup>1、 </sup> <sup>2</sup>|ChatUpdated|Teams 聊天已更新。|
|更新了消息 <sup>1、 </sup> <sup>2</sup>|MessageUpdated|聊天或频道的消息已更新。|
|更新了连接器|ConnectorUpdated|用户修改了通道中的连接器。|
|“已更新”选项卡|TabUpdated|用户修改了频道中的选项卡。|
|升级后的应用|AppUpgraded|应用已升级到目录中的最新版本。|
|用户登录到 Teams|TeamsSessionStarted|用户登录到 Microsoft Teams 客户端。 此事件不会捕获令牌刷新活动。|

> [!NOTE]
> <sup>1</sup> 仅当通过调用 Microsoft 图形 API 执行操作时，才会记录此事件的审核记录。 如果在 Teams 客户端中执行操作，则不会记录审核记录<br/><sup>2</sup> 此事件仅在审核 (Premium) 中可用。 这意味着必须先为用户分配相应的许可证，然后才能将这些事件记录到审核日志中。 有关仅在审核 (Premium) 中可用的活动的详细信息，请参阅 [Microsoft Purview 中的审核 (Premium) ](/microsoft-365/compliance/advanced-audit#advanced-audit-events)。 有关审核 (Premium) 许可要求，请参阅 [Microsoft 365 中的审核解决方案](/microsoft-365/compliance/auditing-solutions-overview#licensing-requirements)。 <br/> <sup>3</sup> 此事件以公共预览版提供。

## <a name="shifts-in-teams-activities"></a>Teams 活动中的班次

**（处于预览阶段）**

如果你的组织正在使用 Teams 中的排班应用，则可以在审核日志中搜索与排班应用相关的活动。 下面是 Microsoft 365 审核日志中 Teams 中为排班活动记录的所有事件的列表。

|友好名称|操作|说明|
|---|---|---|
|添加了计划组|ScheduleGroupAdded|用户已成功将新的计划组添加到计划。|
|已编辑的计划组|ScheduleGroupEdited|用户已成功编辑计划组。|
|已删除的计划组|ScheduleGroupDeleted|用户已成功从计划中删除计划组。|
|撤销计划|ScheduleWithdrawn|用户成功撤销已发布的计划。|
|添加了班次|ShiftAdded|用户成功添加班次。|
|已编辑的班次|ShiftEdited|用户已成功编辑班次。|
|已删除的班次|ShiftDeleted|用户成功删除了班次。|
|增加了休假时间|TimeOffAdded|用户已成功在计划上增加休假时间。|
|编辑的休假时间|TimeOffEdited|用户成功编辑休假。|
|已删除休假|TimeOffDeleted|用户已成功删除休假。|
|添加了开放班次|OpenShiftAdded|用户已成功将打开的班次添加到计划组。|
|编辑的打开班次|OpenShiftEdited|用户成功编辑了计划组中的未完成的班次。|
|已删除的打开班次|OpenShiftDeleted|用户已成功从计划组中删除未完成的班次。|
|共享计划|ScheduleShared|用户已成功共享日期范围的团队计划。|
|使用 Time clock 打卡|ClockedIn|用户使用“时间时钟”成功打卡。|
|使用 Time clock 打卡出|ClockedOut|用户使用 Time clock 成功打卡。|
|使用时间时钟开始中断|BreakStarted|用户在活动时钟会话期间成功开始中断。|
|使用时钟结束中断|BreakEnded|用户在活动时钟会话期间成功结束中断。|
|添加了时钟条目|TimeClockEntryAdded|用户已成功在时间表上添加新的手动时钟条目。|
|已编辑的时钟条目|TimeClockEntryEdited|用户已成功编辑时间表上的时钟条目。|
|已删除的时钟条目|TimeClockEntryDeleted|用户成功删除了时间表上的时钟条目。|
|添加了排班请求|RequestAdded|用户添加了排班请求。|
|响应了班次请求|RequestRespondedTo|用户响应了排班请求。|
|已取消的排班请求|RequestCancelled|用户取消了排班请求。|
|更改了计划设置|ScheduleSettingChanged|用户更改排班设置中的设置。|
|添加了劳动力集成|WorkforceIntegrationAdded|Shifts 应用与第三方系统集成。|
|接受的关闭班次消息|OffShiftDialogAccepted|用户确认下班消息，以在轮班时间后访问 Teams。|

## <a name="office-365-management-activity-api"></a>Office 365管理活动 API

可以使用Office 365管理活动 API 来检索有关 Teams 事件的信息。 若要详细了解 Teams 的管理活动 API 架构，请参阅 [Teams 架构](/office/office-365-management-api/office-365-management-activity-api-schema#microsoft-teams-schema)。

## <a name="attribution-in-teams-audit-logs"></a>Teams 审核日志中的属性

对 Teams (（例如，通过 Azure Active Directory (Azure AD) ) 、Microsoft 365 管理门户或Microsoft 365 组 图形 API添加或删除的用户）的成员身份更改将显示在 Teams 审核消息和常规频道中，其中包含团队现有所有者的归属，而不是操作的实际发起者。 在这些方案中，请参阅 Azure AD 或 [Microsoft 365 组审核日志](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) 以查看相关信息。

## <a name="use-defender-for-cloud-apps-to-set-activity-policies"></a>使用 Defender for Cloud Apps 设置活动策略

使用[Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security)集成，可以设置[活动策略](/cloud-app-security/user-activity-policies)，以使用应用提供程序的 API 强制实施各种自动化过程。 这些策略使你能够监视各种用户执行的特定活动，或遵循特定类型活动的意外高速率。

设置活动检测策略后，它开始生成警报。 仅针对创建策略后发生的活动生成警报。 下面是一些示例方案，介绍了如何使用 Defender for Cloud Apps 中的活动策略来监视 Teams 活动。

### <a name="external-user-scenario"></a>外部用户方案

从业务角度来看，你可能希望关注的一个方案是向 Teams 环境添加外部用户。 如果启用了外部用户，则监视其状态是一个好主意。  可以使用 [Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security) 识别潜在威胁。

:::image type="content" alt-text="用于监视添加外部用户的策略。" source="media/TeamsExternalUserAddPolicy.png" lightbox="media/TeamsExternalUserAddPolicy.png":::

用于监视添加外部用户的此策略的屏幕截图允许你命名策略、根据业务需求设置严重性、在本例中将其设置为 () 单个活动，然后建立将专门监视非内部用户的添加的参数，并将此活动限制为 Teams。

可以在活动日志中查看此策略的结果：

:::image type="content" alt-text="外部用户策略触发的事件。" source="media/TeamsExternalUserList.png" lightbox="media/TeamsExternalUserList.png":::

在这里，可以查看与已设置的策略的匹配项，并根据需要进行任何调整，或导出结果以在其他地方使用。

### <a name="mass-delete-scenario"></a>批量删除方案

如前所述，可以监视删除方案。 可以创建一个策略来监视 Teams 网站的批量删除。 在此示例中，基于警报的策略设置为在 30 分钟内检测团队的大规模删除。

:::image type="content" alt-text="显示为批量团队删除检测设置策略的策略的策略。" source="media/TeamsMassDeletePolicy.png" lightbox="media/TeamsMassDeletePolicy.png":::

如屏幕截图所示，你可以为此策略设置许多不同的参数来监视 Teams 删除，包括严重性、单一操作或重复操作，以及限制为 Teams 和网站删除的参数。 这可以独立于模板完成，也可以创建模板来基于此策略，具体取决于组织需求。

建立适用于业务的策略后，可以在触发事件时查看活动日志中的结果：

:::image type="content" alt-text="批量删除触发的屏幕截图事件。" source="media/TeamsMassDeleteList.png" lightbox="media/TeamsMassDeleteList.png":::

可以向下筛选到已设置的策略，以查看该策略的结果。 如果活动日志中获取的结果不尽如人意 (可能看到大量结果，或者没有任何) ，这可能有助于微调查询，使其与需要执行的操作更相关。

### <a name="alert-and-governance-scenario"></a>警报和治理方案

触发活动策略时，可以设置警报并向管理员和其他用户发送电子邮件。 可以设置自动化治理操作，例如暂停用户或让用户以自动方式重新登录。 此示例演示如何在触发活动策略时暂停用户帐户，并确定用户在 30 分钟内删除了两个或更多团队。

![活动策略的警报和治理操作的屏幕截图。](media/audit-log-governance.png)

## <a name="use-defender-for-cloud-apps-to-set-anomaly-detection-policies"></a>使用 Defender for Cloud Apps 设置异常情况检测策略

Defender for Cloud Apps 中的[异常情况检测策略](/cloud-app-security/anomaly-detection-policy) (UEBA) 和机器学习 (ML) 提供现装的用户和实体行为分析，以便可以跨云环境立即运行高级威胁检测。 由于它们会自动启用，因此新的异常情况检测策略通过提供即时检测来提供即时结果，针对用户以及连接到网络的计算机和设备中的大量行为异常。 此外，新策略会公开来自 Defender for Cloud Apps 检测引擎的更多数据，以帮助你加快调查过程并遏制持续威胁。

我们正在努力将 Teams 事件集成到异常情况检测策略中。 现在，你可以为其他 Office 产品设置异常情况检测策略，并针对与这些策略匹配的用户执行操作项目。

## <a name="related-topics"></a>相关主题

- [在Microsoft Purview 合规门户中搜索审核日志](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
