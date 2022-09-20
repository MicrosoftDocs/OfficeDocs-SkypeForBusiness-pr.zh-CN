---
title: 在 Microsoft Teams 中搜索事件的审核日志
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.reviewer: anwara
search.appverid: MET150
description: 了解如何从Microsoft Purview 合规门户中的审核日志中检索 Microsoft Teams 数据。
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7d94411132b575aa4754aae993f070a36718a2d
ms.sourcegitcommit: 6754f2d11da0afff067f0872acf778a83fd1595e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2022
ms.locfileid: "67808443"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>在 Microsoft Teams 中搜索事件的审核日志

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

审核日志可帮助你调查 Microsoft 365 服务中的特定活动。 对于 Microsoft Teams，下面是一些经过审核的活动：

- 团队创建
- 团队删除
- 添加频道
- 已删除的通道
- 更改的通道设置

有关审核 Teams 活动的完整列表，请参阅 [Teams 活动](#teams-activities)和 Teams 活动中的 [排班](#shifts-in-teams-activities)。

> [!NOTE]
> 来自专用频道的审核事件也会记录为团队和标准频道的审核事件。

## <a name="turn-on-auditing-in-teams"></a>在 Teams 中启用审核

在查看审核数据之前，必须先在Microsoft Purview 合规门户中启用审核。 有关详细信息，请参阅 [打开或关闭审核](/microsoft-365/compliance/turn-audit-log-search-on-or-off)。

> [!IMPORTANT]
> 仅从启用审核时起，审核数据才可用。

## <a name="retrieve-teams-data-from-the-audit-log"></a>从审核日志检索 Teams 数据

1. 若要检索 Teams 活动的审核日志，请转到 <https://compliance.microsoft.com> 并选择 **“审核**”。

2. 在 **“搜索** ”页上，筛选要审核的活动、日期和用户。

3. 将结果导出到 Excel 以供进一步分析。

有关分步说明，请参阅 [合规中心中的审核日志搜索](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log)。

> [!IMPORTANT]
> 仅当启用审核时，审核数据才会显示在审核日志中。

审核日志中保留和搜索审核记录的时间长度取决于 Microsoft 365 或Office 365订阅，特别是分配给用户的许可证类型。 若要了解详细信息，请参阅 [安全&合规中心服务说明](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)。

## <a name="tips-for-searching-the-audit-log"></a>有关搜索审核日志的提示

下面是有关在审核日志中搜索 Teams 活动的提示。

:::image type="content" alt-text="合规中心审核日志搜索页的屏幕截图" source="media/audit-log-search-page.png" lightbox="media/audit-log-search-page.png":::

- 可以通过单击一个或多个活动旁边的复选框来选择要搜索的特定活动。 如果选择了活动，则可以单击该活动以取消所选内容。 还可以使用搜索框显示包含你键入的关键字的活动。

  ![审核日志搜索页上活动下拉列表的屏幕截图](media/audit-log-search.png)

- 若要显示使用 cmdlet 运行的活动的事件，请选择“**活动**”列表中 **所有活动的“显示结果**”。 如果知道这些活动的操作名称，请在搜索框中键入它以显示活动，然后选择它。

- 若要清除当前搜索条件，请单击 **“全部清除**”。 日期范围将返回到过去七天的默认值。

- 如果找到 5，000 个结果，则可能假定有超过 5，000 个事件符合搜索条件。 可以优化搜索条件并重新运行搜索以返回更少的结果，也可以通过选择“ **导出** > **下载所有结果**”来导出所有搜索结果。 有关导出审核日志的分步说明，请参阅 [将搜索结果导出到文件](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#step-3-export-the-search-results-to-a-file)。

请查看 [此视频](https://www.youtube.com/embed/UBxaRySAxyE) ，了解如何使用音频日志搜索。 加入 Teams 的项目经理 Ansuman Acharya，他演示如何对 Teams 执行审核日志搜索。

## <a name="teams-activities"></a>Teams 活动

以下是在 Microsoft 365 审核日志中为 Teams 中的用户和管理员活动记录的所有事件的列表。 该表包括“ **活动** ”列中显示的友好名称，以及导出搜索结果时在审核记录的详细信息和 CSV 文件中显示的相应操作的名称。

|友好名称|操作|说明|
|---|---|---|
|向团队添加了机器人|BotAddedToTeam|用户将机器人添加到团队。|
|添加频道|ChannelAdded|用户将频道添加到团队。|
|添加了连接器|ConnectorAdded|用户将连接器添加到通道。|
|添加了有关 Teams 会议 <sup>2</sup> 的详细信息|MeetingDetail|Teams 添加了有关会议的信息，包括开始时间、结束时间和加入会议的 URL。|
|添加了有关会议参与者 <sup>的信息 2</sup>|MeetingParticipantDetail|Teams 添加了有关会议参与者的信息，包括每个参与者的用户 ID、参与者加入会议的时间以及参与者离开会议的时间。|
|添加了成员|MemberAdded|团队所有者将成员添加到团队、频道或群聊。|
|添加了选项卡|TabAdded|用户将选项卡添加到频道。|
|更改的通道设置|ChannelSettingChanged|当团队成员执行以下活动时，将记录 ChannelSettingChanged 操作。 对于上述每个活动，审核日志搜索结果的 **“项** ”列中会显示更改 (括号中所示的设置的说明。 <ul><li>更改团队频道的名称 (**频道名称**) </li><li>更改团队频道 (**频道说明**) </li> </ul>|
|更改了组织设置|TeamsTenantSettingChanged|当以下活动由 Microsoft 365 管理中心 中的全局管理员执行时，将记录 TeamsTenantSettingChanged 操作。 这些活动影响组织范围的 Teams 设置。 若要了解详细信息，请参阅 [组织管理 Teams 设置](enable-features-office-365.md)。 <br>对于上述每个活动，审核日志搜索结果的 **“项** ”列中会显示更改的设置的说明 (在括号中显示) 。<ul><li>为组织启用或禁用 Teams (**Microsoft Teams**) 。</li><li>为组织启用或禁用 Microsoft Teams 与Skype for Business之间的互操作性 (**Skype for Business互操作性**) 。</li><li>启用或禁用 Microsoft Teams 客户端中的组织图表视图 (**组织图表视图**) 。</li><li>启用或禁用团队成员安排私人会议 (**私人会议安排**) 的能力。</li><li>启用或禁用团队成员安排频道会议 (**频道会议安排**) 的能力。</li><li>启用或禁用 Teams 会议中的视频呼叫 (**视频以进行 Skype 会议**) 。</li><li>为组织启用或禁用 Microsoft Teams 会议中的屏幕共享 (**Skype 会议的屏幕共享**) 。</li><li>启用或禁用将名为 Giphys () 的动画图像添加到 Teams 对话 (**动画图像**) 的功能。</li><li>更改组织的内容分级设置 (**内容分级**) 。 内容分级限制可在对话中显示的动画图像的类型。</li><li>启用或禁用团队成员从 Internet 添加自定义模因)  (可自定义图像的功能， (**Internet) 中的可自定义图像** 进行团队对话。</li><li>启用或禁用团队成员向团队对话添加可编辑图像的功能 (称为贴纸)  (**可编辑图像**) 。</li><li>启用或禁用该功能，使团队成员能够在 Microsoft Teams 聊天和频道中使用机器人 (**组织范围的机器人)**。</li><li>为 Microsoft Teams 启用特定机器人。 这不包括 T-Bot，它是在为组织启用机器人时提供的 Teams 帮助机器人， (**单个机器人**) 。</li><li>启用或禁用团队成员 (**扩展或选项卡**) 添加扩展或选项卡的功能。</li><li>为 Microsoft Teams 启用或禁用专有机器人的旁加载 (**端加载机器人**) 。</li><li>启用或禁用用户向 Microsoft Teams 频道发送电子邮件的功能 (**频道电子邮件**) 。</li></ul>|
|在团队中更改成员的角色|MemberRoleChanged|团队所有者会更改团队中成员的角色。 以下值指示分配给用户的角色类型。 <br><br>**1** - 指示成员角色。<br>**2** - 指示所有者角色。<br>**3** - 指示来宾角色。<br><br>Members 属性还包括组织的名称和成员的电子邮件地址。|
|更改了团队设置|TeamSettingChanged|当团队所有者执行以下活动时，将记录 TeamSettingChanged 操作。 对于上述每个活动，审核日志搜索结果的 **“项** ”列中会显示更改的设置的说明 (在括号中显示) 。<ul><li>更改团队的访问类型。 可以将 Teams 设置为专用或公共 (**团队访问类型**) 。 当团队是专用 (默认设置) 时，用户只能通过邀请访问团队。 当团队公开时，任何人都可以发现它。</li><li>更改团队 (**团队分类**) 的信息分类。 例如，团队数据可以归类为业务影响大、业务影响中等或业务影响低。</li><li>更改团队名称 (**团队名称**) 。</li><li>更改团队说明 (**) 的团队说明** 。</li><li>对团队设置所做的更改。 若要访问这些设置，团队所有者可以右键单击团队，选择 **“管理团队**”，然后单击 **“设置”** 选项卡。对于这些活动，已更改的设置的名称会显示在审核日志搜索结果的 **“项** ”列中。</li></ul>|
|创建聊天 <sup>1、 </sup> <sup>2</sup>|ChatCreated|创建了 Teams 聊天。|
|创建的团队|TeamCreated|用户创建团队。|
|删除了一条消息|MessageDeleted|已删除聊天或频道中的消息。|
|删除了所有组织应用|DeletedAllOrganizationApps|从目录中删除了所有组织应用。|
|已删除的应用|AppDeletedFromCatalog|已从目录中删除应用。|
|已删除的通道|ChannelDeleted|用户从团队中删除频道。|
|已删除的团队|TeamDeleted|团队所有者删除团队。|
|在 Teams 中编辑了包含 URL 链接的消息|MessageEditedHasLink|用户编辑消息并在 Teams 中向其添加 URL 链接。|
|导出的消息 <sup>1、 </sup> <sup>2</sup>|MessagesExported|已导出聊天或频道消息。|
|未能验证对共享频道<sup>3</sup> 的邀请|FailedValidation|用户响应对共享频道的邀请，但邀请未通过验证。|
|提取聊天 <sup>1、 </sup> <sup>2</sup>|ChatRetrieved|检索了 Microsoft Teams 聊天。|
|提取消息<sup>1、 </sup> <sup>2</sup> 的所有托管内容|MessageHostedContentsListed|检索消息中的所有托管内容，如图像或代码片段。|
|已安装的应用|AppInstalled|已安装应用。|
|对卡片执行的操作|PerformedCardAction|用户在聊天中对自适应卡片采取了操作。 自适应卡片通常由机器人用来在聊天中丰富显示信息和交互。 <br/><br/>**注意：** 审核日志中仅提供聊天中自适应卡片上的内联输入操作。 例如，当用户在由 Poll 机器人生成的自适应卡片的频道对话中提交投票响应时。 将打开对话框的用户操作（如“查看结果”）或对话框中的用户操作在审核日志中不可用。|
|发布新消息 <sup>1、 </sup> <sup>2</sup>|MessageSent|一条新消息已发布到聊天或频道。|
|已发布的应用|AppPublishedToCatalog|已将应用添加到目录。|
|读取消息 <sup>1、 </sup> <sup>2</sup>|MessageRead|检索聊天或频道的消息。|
|读取邮件 <sup>1、 </sup> <sup>2</sup> 的托管内容|MessageHostedContentRead|检索消息中的托管内容，例如图像或代码片段。|
|从团队中删除了机器人|BotRemovedFromTeam|用户从团队中删除机器人。|
|删除的连接器|ConnectorRemoved|用户从通道中删除连接器。|
|已删除的成员|MemberRemoved|团队所有者从团队、频道或群聊中删除成员。|
|删除了团队频道<sup>3</sup> 的共享|TerminatedSharing|已禁用共享频道的团队或频道所有者共享。|
|已还原团队频道<sup>3</sup> 的共享|SharingRestored|团队或频道所有者为共享频道重新启用共享。|
|已删除的选项卡|TabRemoved|用户从通道中删除选项卡。|
|响应共享频道<sup>3</sup> 的邀请|InviteeResponded|用户响应了共享频道邀请。|
|响应了对共享频道<sup>3</sup> 的受邀者响应|ChannelOwnerResponded|频道所有者响应了响应共享频道邀请的用户的响应。|
|检索的消息 <sup>1、 </sup> <sup>2</sup>|MessagesListed|从聊天或频道检索消息。|
|在 Teams 中发送包含 URL 链接的消息|MessageCreatedHasLink|用户在 Teams 中发送包含 URL 链接的消息。|
|已发送消息创建 <sup>1、 </sup> <sup>2</sup> 的更改通知|MessageCreatedNotification|已发送更改通知以通知订阅的侦听器应用程序新消息。|
|已发送邮件删除更改通知 <sup>1、 </sup> <sup>2</sup>|MessageDeletedNotification|已发送更改通知，以通知订阅的侦听器应用程序已删除消息。|
|已发送消息更新 <sup>1、 </sup> <sup>2</sup> 的更改通知|MessageUpdatedNotification|已发送更改通知以通知订阅的侦听器应用程序更新的消息。|
|已发送共享频道<sup>3</sup> 的邀请|InviteSent|频道所有者或成员向共享频道发送邀请。 如果将频道策略配置为与外部用户共享频道，则可以向组织外部的人员发送对共享频道的邀请。|
|订阅消息更改通知 <sup>1、 </sup> <sup>2</sup>|SubscribedToMessages|订阅由侦听器应用程序创建，用于接收消息的更改通知。|
|卸载的应用|AppUninstalled|已卸载应用。|
|已更新的应用|AppUpdatedInCatalog|已在目录中更新应用。|
|更新了聊天 <sup>1、 </sup> <sup>2</sup>|ChatUpdated|Teams 聊天已更新。|
|更新了消息 <sup>1、 </sup> <sup>2</sup>|MessageUpdated|已更新聊天或频道的消息。|
|更新的连接器|ConnectorUpdated|用户修改了通道中的连接器。|
|“更新”选项卡|TabUpdated|用户修改了通道中的选项卡。|
|升级后的应用|AppUpgraded|应用已升级到目录中的最新版本。|
|登录到 Teams 的用户|TeamsSessionStarted|用户登录到 Microsoft Teams 客户端。 此事件不会捕获令牌刷新活动。|

> [!NOTE]
> <sup>1</sup> 仅在通过调用 Microsoft 图形 API 执行操作时记录此事件的审核记录。 如果操作在 Teams 客户端中执行，则不会记录审核记录<br/><sup>2</sup> 此事件仅在审核 (高级) 中可用。 这意味着在审核日志中记录这些事件之前，必须为用户分配相应的许可证。 有关仅在审核 (高级) 中可用的活动的详细信息， [请参阅 Microsoft Purview 中的审核 (高级) ](/microsoft-365/compliance/advanced-audit#advanced-audit-events)。 有关审核 (高级) 许可要求， [请参阅 Microsoft 365 中的审核解决方案](/microsoft-365/compliance/auditing-solutions-overview#licensing-requirements)。 <br/> <sup>3</sup> 此事件以公共预览版提供。

## <a name="shifts-in-teams-activities"></a>Teams 活动中的班次

**（处于预览阶段）**

如果你的组织在 Teams 中使用 Shifts 应用，则可以在审核日志中搜索与 Shifts 应用相关的活动。 以下是在 Microsoft 365 审核日志中为 Teams 中的 Shifts 活动记录的所有事件的列表。

|友好名称|操作|说明|
|---|---|---|
|添加了计划组|ScheduleGroupAdded|用户成功将新的计划组添加到计划中。|
|编辑的计划组|ScheduleGroupEdited|用户成功编辑计划组。|
|已删除的计划组|ScheduleGroupDeleted|用户成功从计划中删除计划组。|
|已撤回的计划|ScheduleWithdrawn|用户成功撤回已发布的计划。|
|添加了班次|ShiftAdded|用户成功添加了班次。|
|编辑的班次|ShiftEdited|用户已成功编辑班次。|
|已删除的班次|ShiftDeleted|用户成功删除了班次。|
|增加了休假时间|TimeOffAdded|用户已成功按计划添加休假时间。|
|编辑的休假时间|TimeOffEdited|用户成功编辑休假。|
|已删除的休假时间|TimeOffDeleted|用户成功删除了休假时间。|
|添加了打开的班次|OpenShiftAdded|用户成功将打开的班次添加到计划组。|
|编辑的打开班次|OpenShiftEdited|用户在计划组中成功编辑打开的班次。|
|已删除的打开班次|OpenShiftDeleted|用户成功从计划组中删除打开的班次。|
|共享计划|ScheduleShared|用户成功共享了日期范围的团队计划。|
|使用时间时钟打卡|ClockedIn|用户使用时间时钟成功打卡。|
|使用时间时钟打卡|ClockedOut|用户使用时间时钟成功打卡。|
|使用时间时钟开始中断|BreakStarted|用户在活动时间时钟会话期间成功启动中断。|
|使用时间时钟结束中断|BreakEnded|用户在活动时间时钟会话期间成功结束中断。|
|添加了时间时钟条目|TimeClockEntryAdded|用户在时间表上成功添加了新的手动时间时钟条目。|
|编辑的时间时钟条目|TimeClockEntryEdited|用户在时间表上成功编辑时间时钟条目。|
|已删除的时间时钟条目|TimeClockEntryDeleted|用户成功删除时间表上的“时间时钟”条目。|
|添加了班次请求|RequestAdded|用户添加了班次请求。|
|响应班次请求|RequestRespondedTo|用户响应了班次请求。|
|已取消的班次请求|RequestCancelled|用户取消了班次请求。|
|更改的计划设置|ScheduleSettingChanged|用户更改 Shifts 设置中的设置。|
|添加了员工集成|WorkforceIntegrationAdded|Shifts 应用与第三方系统集成。|
|已接受的脱班消息|OffShiftDialogAccepted|用户确认轮班后访问 Teams 的轮班消息。|

## <a name="office-365-management-activity-api"></a>Office 365管理活动 API

可以使用Office 365管理活动 API 检索有关 Teams 事件的信息。 若要详细了解 Teams 的管理活动 API 架构，请参阅 [Teams 架构](/office/office-365-management-api/office-365-management-activity-api-schema#microsoft-teams-schema)。

## <a name="attribution-in-teams-audit-logs"></a>Teams 审核日志中的归因

对 Teams (（例如，通过 Azure Active Directory (Azure AD) 、Microsoft 365 管理门户或Microsoft 365 组 图形 API添加或删除) 的用户）的成员身份更改将显示在 Teams 审核消息和常规频道中，并归于团队的现有所有者，而不是操作的实际发起者。 在这些情况下，请查阅 Azure AD 或 [Microsoft 365 组审核日志](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) ，查看相关信息。

## <a name="use-defender-for-cloud-apps-to-set-activity-policies"></a>使用 Defender for Cloud Apps 设置活动策略

使用[Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security)集成，可以设置[活动策略](/cloud-app-security/user-activity-policies)，以使用应用提供程序的 API 强制实施各种自动化进程。 借助这些策略，可以监视各种用户执行的特定活动，或遵循特定类型的活动的意外高速率。

设置活动检测策略后，它会开始生成警报。 警报仅在创建策略后发生的活动上生成。 下面是一些示例方案，说明如何在 Defender for Cloud Apps 中使用活动策略来监视 Teams 活动。

### <a name="external-user-scenario"></a>外部用户方案

从业务角度来看，你可能想要关注一个方案是将外部用户添加到 Teams 环境。 如果已启用外部用户，则监视其状态是一个好主意。  可以使用 [Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security) 来识别潜在威胁。

:::image type="content" alt-text="用于监视添加外部用户的策略。" source="media/TeamsExternalUserAddPolicy.png" lightbox="media/TeamsExternalUserAddPolicy.png":::

此策略用于监视添加外部用户的屏幕截图允许你命名策略、根据业务需求设置严重性、将策略设置为 (在这种情况下) 单个活动，然后建立仅专门监视非内部用户添加情况的参数，并将此活动限制为 Teams。

可以在活动日志中查看此策略的结果：

:::image type="content" alt-text="外部用户策略触发的事件。" source="media/TeamsExternalUserList.png" lightbox="media/TeamsExternalUserList.png":::

可在此处查看已设置的策略的匹配项，并根据需要进行任何调整，或导出结果以在其他位置使用。

### <a name="mass-delete-scenario"></a>批量删除方案

如前所述，可以监视删除方案。 可以创建一个策略来监视 Teams 网站的大规模删除。 在此示例中，设置了基于警报的策略，以在 30 分钟内检测团队的大规模删除。

:::image type="content" alt-text="显示为大规模团队删除检测设置策略的策略的策略。" source="media/TeamsMassDeletePolicy.png" lightbox="media/TeamsMassDeletePolicy.png":::

如屏幕截图所示，可以为此策略设置许多不同的参数来监视 Teams 删除，包括严重性、单个或重复操作，以及将此限制为 Teams 和网站删除的参数。 这可以独立于模板完成，也可以创建一个模板来根据组织需求来基于此策略。

建立适用于企业的策略后，可以在触发事件时查看活动日志中的结果：

:::image type="content" alt-text="由大规模删除触发的屏幕截图事件。" source="media/TeamsMassDeleteList.png" lightbox="media/TeamsMassDeleteList.png":::

可以向下筛选到已设置的策略，以查看该策略的结果。 如果你在活动日志中得到的结果并不令人满意 (也许你看到很多结果，或者没有任何结果) ，这可能会帮助你微调查询，使其与需要它执行的操作更相关。

### <a name="alert-and-governance-scenario"></a>警报和治理方案

触发活动策略时，可以设置警报并向管理员和其他用户发送电子邮件。 可以设置自动治理操作，例如暂停用户或让用户以自动方式再次登录。 此示例演示如何在触发活动策略时暂停用户帐户，并确定用户在 30 分钟内删除了两个或更多个团队。

![活动策略的警报和治理操作的屏幕截图。](media/audit-log-governance.png)

## <a name="use-defender-for-cloud-apps-to-set-anomaly-detection-policies"></a>使用 Defender for Cloud Apps 设置异常情况检测策略

Defender for Cloud Apps 中的[异常情况检测策略](/cloud-app-security/anomaly-detection-policy) (UEBA) 和机器学习 (ML) 提供现用的用户和实体行为分析，以便可以立即在云环境中运行高级威胁检测。 由于它们已自动启用，因此新的异常情况检测策略通过提供即时检测来提供即时检测，针对用户和连接到网络的计算机和设备的众多行为异常提供即时结果。 此外，新策略还公开了 Defender for Cloud Apps 检测引擎中的更多数据，以帮助你加快调查过程并包含持续的威胁。

我们正在努力将 Teams 事件集成到异常情况检测策略中。 目前，可以为其他 Office 产品设置异常情况检测策略，并针对与这些策略匹配的用户执行操作项。

## <a name="related-topics"></a>相关主题

- [在Microsoft Purview 合规门户中搜索审核日志](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
