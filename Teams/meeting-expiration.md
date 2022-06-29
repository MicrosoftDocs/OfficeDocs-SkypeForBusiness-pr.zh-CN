---
title: Microsoft Teams 中的会议策略和会议过期
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej, brgussin
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: 了解如何使用会议策略设置来控制 Microsoft Teams 中的会议过期。
ms.openlocfilehash: 08ca5a75b8dd470b006d44e562eb795f814faba6
ms.sourcegitcommit: bdb919a6f53556f76dd4a71759412023e6e18fbb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2022
ms.locfileid: "66529684"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Microsoft Teams 中的会议策略和会议过期

Microsoft Teams 中的[会议策略](meeting-policies-overview.md)用于控制组织中的用户是否可以启动和安排会议，以及可供会议参与者参加由用户安排的会议的功能。 可以使用全局（组织范围内的默认）策略，也可以创建并分配自定义策略。 在 Microsoft Teams 管理中心或使用 [Get](/powershell/module/skype/get-csteamsmeetingpolicy)、 [New](/powershell/module/skype/new-csteamsmeetingpolicy)、 [Set](/powershell/module/skype/set-csteamsmeetingpolicy)、 [Remove](/powershell/module/skype/remove-csteamsmeetingpolicy)、 [Grant](/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy PowerShell cmdlet 管理会议策略。

控制用户是否可以启动和安排会议以及控制用户安排的会议过期的会议策略设置。 当会议加入链接和会议 ID 过期时，任何人都无法加入会议。 以下会议策略设置确定用户是否可以在 Teams 中启动和安排会议。 本文介绍会议设置。

- [立即在频道中开会](meeting-policies-in-teams-general.md#meet-now-in-channels)：控制用户是否可以在频道中启动即席会议。
- [频道会议日程安排](meeting-policies-in-teams-general.md#channel-meeting-scheduling)：控制用户是否可以在频道中安排会议。
- [私人会议计划](meeting-policies-in-teams-general.md#private-meeting-scheduling)：控制用户是否可以在 Teams 中安排私人会议。 当会议未发布到团队中的某个频道时，这个会议就是私人的。
- [Outlook 加载](meeting-policies-in-teams-general.md#outlook-add-in)项：控制用户是否可以从 Outlook 安排私人会议。 当会议未发布到团队中的某个频道时，这个会议就是私人的。
- [立即在私人会议中开会](meeting-policies-in-teams-general.md#meet-now-in-private-meetings)：控制用户是否可以启动即席私人会议。

默认情况下，这些设置处于打开状态。 关闭这些设置中的任何一个时，分配策略的任何用户都无法启动或安排此类的新会议。 同时，会议加入用户以前启动或计划过期的所有现有会议的链接和会议 ID。

例如，如果为用户分配了一个会议策略，其中这些会议策略设置设置为 **“打开”**，然后你 **立即在频道设置中关闭“允许会议** ”，则该用户不能再在频道中启动即席会议，而频道“会议”现在联接用户以前创建的链接已过期。 用户仍然可以启动和安排其他会议类型，并加入其他人组织的会议。

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>当会议加入链接和会议 ID 过期时会发生什么情况？

会议加入链接和会议 ID 到期后，任何人都无法加入会议。 当用户尝试通过链接或电话加入会议时，他们将收到一条消息，指出会议不再可用。 会话、文件、白板、录音、脚本和其他与会议相关的内容被保留，用户仍然可以访问它们。

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>打开并关闭会议策略设置时会发生什么情况？

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>将会议策略设置从打开切换到关闭

当会议策略设置设置为 **“打开”时**，分配策略的用户可以启动或安排此类会议，每个人都可以加入。 将会议策略设置切换为 **“关闭**”时，分配策略的用户无法启动或计划此类的新会议，并且用户先前安排的现有会议的会议加入链接和会议 ID 已过期。

请记住，用户仍然可以加入由其他人组织的会议。

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>将会议策略设置从关闭切换到打开

将会议策略设置从 **“关闭** ”切换到 **“打开”时**，分配该策略的用户可以启动或安排此类会议。 如果会议策略设置已关闭，然后再次为用户打开，则用户组织的所有以前安排的 (和已过期) 会议将变为活动状态，用户可以使用会议加入链接或电话加入会议。  

## <a name="meeting-expiration-scenarios"></a>会议过期方案

下面是本文中讨论的每个会议策略设置的会议过期工作原理摘要。

|如果你想...&nbsp;&nbsp; |执行此操作&nbsp;&nbsp;&nbsp;&nbsp;  |会议加入行为&nbsp;&nbsp;&nbsp;&nbsp;  |
|---------------------------|---------------------|---------|
|过期的专用会议现在由用户启动&nbsp;&nbsp;|**立即在私人会议中关闭“会议**”。&nbsp;&nbsp;|用户现在无法加入由用户启动的专用 **会议** 。|
|使用户安排的专用会议过期&nbsp;&nbsp;|关闭 **私人会议计划**_并_ 关闭 **Outlook 加载项**。 &nbsp;&nbsp;|任何人都不能加入用户安排的专用会议。 这会阻止用户参加以下会议：<ul><li>过去发生的私人会议。</li><li>为将来安排但尚未举行的私人会议。</li><li>定期私人会议的未来实例。</li></ul><br>**私人会议计划** 和 **Outlook 加载项** 都必须关闭，才能使用户安排的专用会议过期。 如果一个设置处于关闭状态，而另一个设置处于打开状态，则现有会议的会议加入链接和会议 ID 将保持活动状态，并且不会过期。|
|过期频道 **会议现在** 由用户启动&nbsp;&nbsp;|**立即在频道中关闭“会议”**_，并_ 关闭 **频道会议日程安排**。&nbsp;&nbsp;|没有人可以加入用户启动的 **“立即开会** ”频道。|
|使用户安排的频道会议过期&nbsp;&nbsp;|关闭 **频道会议日程安排**。&nbsp;&nbsp;|没有人可以加入用户安排的频道会议。 这会阻止用户参加以下会议：<ul><li>过去发生的频道会议。</li><li>针对未来计划但尚未发生的频道会议。</li><li>定期频道会议的未来实例。</li></ul>|

如果希望用户访问以前由特定用户安排或启动的会议，可以：

- 为该用户启用会议策略设置。
- 关闭该用户的会议策略设置，并让启用了策略设置的另一个用户创建一个新会议来替换过期的会议。

> [!NOTE]
> 如果会议是由代理人发送的，该代表有权代表另一个人（例如经理）发送会议邀请，则会议策略设置将应用于 (经理) 授予权限的人员。

## <a name="changes-to-meeting-expiration"></a>会议过期更改

所有新创建的 Teams 会议录制 (TMR) 将默认过期 120 天。 默认情况下，所有租户都处于启用状态。 这意味着默认情况下， *在启用此功能后* 创建的所有 TMR 将在创建日期后 120 天内删除。 管理员还可以将会议设置为 **永不过期**。 OneDrive 和 SharePoint 系统将监视所有 TMR 上设置的过期日期，并在其过期日期自动将 TMR 移动到回收站。

> [!NOTE]
> 会议脚本的一个副本保存在 OneDrive SharePoint 中，第二个副本保存在 Exchange 的临时存储中。 当 TMR 自动过期时，OSDP 副本将过期。

自动会议过期是一种轻型的内务管理机制，用于减少旧 TMR 创建的存储混乱。 平均而言，在所有客户中，96% 的 TMR 在 60 天后不会被监视，99% 的 TMR 在 110 天后不会被监视。 我们相信，几乎所有客户都会通过删除 60 天后可能不会再被监视的录音，从租户上的存储负载减少中获益。 我们的目标是在默认情况下为所有客户提供尽可能干净的体验。

使用会议过期来限制由 Teams 会议记录驱动的云存储消耗的 OneDrive 或 SharePoint。 典型的会议录制每小时消耗大约 400 MB 的录制量。

> [!NOTE]
> A1 用户的最大默认到期日期为 30 天。

### <a name="expiration-date"></a>有效期

- 过期日期计算为 **创建的日期** 以及 **管理员在 Teams 策略中设置的默认天数**。
- 播放不会影响过期日期。

### <a name="change-the-default-expiration-date"></a>更改默认过期日期

管理员可以在 PowerShell 或 Teams 管理中心编辑默认过期设置。 任何更改只会影响新 *创建* 的 TMR（从该时间点开始）。 它不会影响在该日期之前创建的任何录制。 管理员无法更改现有 TMR 的过期日期。 这样做是为了保护拥有 TMR 的用户的决定。 会议和通话都可以由此设置控制。

可按如下所示设置过期日期值：

- 最小值： **1 天**
- 最大值： **99，999 天**
- 还可以将到期日期设置为 **-1** ，以便录制不会过期。

示例 PowerShell 命令：

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -NewMeetingRecordingExpirationDays 50
```

可以根据 **会议策略** 在 Teams 管理中心设置到期日期。 启用 **会议自动过期后，** 你将获得设置录制过期的选项。

![管理员会议过期策略的中心屏幕截图。](media/meeting-expiration-policy.jpg)

### <a name="security-and-compliance"></a>安全性和合规性

#### <a name="should-i-rely-on-this-feature-for-strict-security-and-compliance-adherence"></a>是否应依赖此功能来严格遵守安全性和合规性？

不可以，不应依赖此项进行法律保护，因为最终用户可以修改他们控制的任何录制的过期日期。

#### <a name="will-a-retention-andor-deletion-policy-ive-set-in-the-security--compliance-center-override-the-teams-meeting-recording-expiration-setting"></a>我在安全&合规中心设置的保留和/或删除策略是否会替代 Teams 会议记录过期设置？

是的，你在合规中心设置的任何策略都具有完全优先级。

例如：

- 如果你有一个策略，指出网站中的所有文件必须保留 100 天，并且 Teams 会议录制的到期设置为 30 天，则录制将保留整整 100 天。
- 如果你有一个删除策略，指出所有 Teams 会议录制将在五天后删除，并且 Teams 会议录制的过期设置为 30 天，则录制将在五天后删除。

### <a name="will-this-feature-enforce-file-retention"></a>此功能是否会强制文件进行保留？

否，文件不会因此功能或其设置而保留。 如果具有删除权限的用户尝试删除具有过期设置的 TMR，则将执行该用户的删除操作。

### <a name="what-skus-are-required-for-this-feature"></a>此功能需要哪些 SKU？

- 默认情况下，所有 SKU 都将具有此功能。
- A1 用户将默认为最长 30 天的过期期，但他们可以根据需要更改过期日期。

### <a name="what-if-i-want-the-admin-to-have-full-control-over-the-lifecycle-of-meeting-recordings-and-dont-want-to-give-end-users-the-ability-to-override-the-expiration-date"></a>如果希望管理员完全控制会议录制的生命周期，并且不想让最终用户能够替代过期日期，该怎么办？

建议使用安全性和符合性保留和/或删除策略。 该产品/服务旨在解决复杂的策略和 SLA 驱动的行政法律问题。

自动过期功能仅用作一种轻型家政机制，用于减少从旧 Teams 会议录制中创建的存储混乱。

### <a name="will-future-tmrs-migrated-from-classic-stream-after-this-feature-is-released-have-auto-expiration-applied-to-them-too"></a>发布此功能后，从经典流迁移的 TMR 将来是否也会应用自动到期？

否，迁移的 TMR 不会有到期设置。 相反，我们鼓励管理员仅迁移要保留的 TMR。 迁移文档将提供更多详细信息。

### <a name="how-is-this-feature-different-from-the-expiration-message-i-see-when-a-tmr-upload-to-onedrive-and-sharepoint-fails"></a>此功能与 TMR 上传到 OneDrive 和 SharePoint 失败时看到的过期消息有何不同？

当录制无法上传到 OneDrive 或 SharePoint 时，Teams 应用程序会在聊天中显示一条消息，用户在从 Teams 服务器中永久删除 TMR 之前，最多有 21 天的时间下载 TMR。 由于 TMR 上传失败，此现有过期体验与帮助文档中讨论的 OneDrive 和 SharePoint 自动过期功能无关。

### <a name="how-do-i-know-the-distribution-of-tmr-playbacks-so-i-know-what-the-optimal-auto-expiration-default-should-be-for-my-tenant"></a>如何实现知道 TMR 播放的分布情况，以便我知道租户的最佳自动过期默认值应该是什么？

1. 在库中查找视频。
1. 选择 **...** > **细节**
1. 选择详细信息窗格顶部的视图数。

你将看到显示以下内容的文件统计信息：

- 唯一查看者的数量
- 总视图数
- 过去 90 天观众和观众的日复一日地观看的趋势
- 查看保留 (查看或未查看视频的哪个部分) 

### <a name="when-will-the-file-be-deleted"></a>文件何时删除？

录制通常在过期日期后的一天内删除，但在极少数情况下可能需要长达五天的时间。 文件所有者将在录制过期时收到电子邮件通知，并将定向到回收站以恢复录制。

> [!NOTE]
> 在到期日期，记录将移入回收站，并清除过期日期字段。 如果从回收站恢复录制，则此功能不会再删除该记录，因为过期日期已清除。

## <a name="related-topics"></a>相关主题

[更改会议到期日期 - 最终用户控件](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24#bkmk_view_change_expiration_date)

[管理 Teams 中的会议策略](meeting-policies-overview.md)

[向 Teams 中的用户分配策略](policy-assignment-overview.md)

[Teams PowerShell 概览](teams-powershell-overview.md)

[Microsoft Teams 的限制和规范](/microsoftteams/limits-specifications-teams)
