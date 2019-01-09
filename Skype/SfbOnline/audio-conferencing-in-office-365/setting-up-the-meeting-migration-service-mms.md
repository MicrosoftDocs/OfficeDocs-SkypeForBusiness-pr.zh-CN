---
title: 使用会议迁移服务 (MMS)
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 会议迁移服务 (MMS) 是在后台运行，并为用户的业务和 Microsoft 团队会议将自动更新 Skype 的服务。 MMS 旨在消除用户运行会议迁移工具需要更新其 Skype 业务和 Microsoft 团队的会议。
ms.openlocfilehash: 94f3d315810e6fdee93ffa8abfe6a657ca8b43fd
ms.sourcegitcommit: 1b9f19b1bd8f33ee2f011cd5ea2d0d75bf8647c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "27783514"
---
# <a name="using-the-meeting-migration-service-mms"></a>使用会议迁移服务 (MMS)

会议迁移服务 (MMS) 是更新以下方案中的用户的现有会议的服务：

- 当迁移用户从内部部署到云 （是否业务 online Skype 或 TeamsOnly）。
- 当管理员对用户的音频会议设置进行了更改 
- 在用户升级到 TeamsOnly 模式 （仅适用于技术计 サ ョ [点击] 客户）

默认情况下 MMS 是自动触发中每种情况下，尽管管理员可以禁用它在租户级别。 此外，管理员可以使用 PowerShell cmdlet 以手动触发给定用户的会议迁移。

> [!NOTE]
> 将 Skype 转换业务团队会议的会议的功能和更新现有团队会议修改音频会议设置的能力是当前限制为仅点击客户。

**限制**： 会议如果以下任一情况，不能使用迁移服务：

- 用户邮箱位于 Exchange 内部部署中。
- 用户正在迁移从云到 Skype 的业务 Server 内部部署。

在这些情况下，最终用户可以使用[会议迁移工具](https://www.microsoft.com/en-us/download/details.aspx?id=51659)来迁移他们自己的会议而。

## <a name="how-mms-works"></a>MMS 的工作原理

指定用户的触发 MMS 时，为该用户的迁移请求位于队列中。 若要避免任何问题的竞争条件，排队有意未处理请求之前，至少 90 分钟过去的。 一旦 MMS 处理请求，则它将执行以下任务：

1. 搜索所有现有会议的用户组织的和计划将来的该用户的邮箱。
2. 根据用户的邮箱中找到的信息，其更新或计划新会议中团队或 Skype 业务 online 为该用户，具体取决于具体的情况。
3. 在电子邮件中，它取代了会议详细信息中的联机会议块。
4. 代表会议组织者向所有会议收件人发送的会议的更新的版本。 会议受邀者将其电子邮件中收到与更新后的会议坐标为会议更新。 

    ![由 MMS 更新的会议块](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

从触发 MMS 的时间，它通常需要大约 2 小时，直到都将迁移用户的会议。 但是，如果用户具有大量的会议，则可能需要更长时间。 如果 MMS 遇到错误迁移用户的一个或多个会议，它将定期重试达 9 倍 24 小时的范围内。

**说明**：

- MMS 在迁移会议时会替换联机会议信息块中的所有内容。因此，如果用户编辑了信息块，它们的更改会被覆盖。用户拥有的所有联机会议信息块以外的内容不会受到影响。
- 仅 Skype 业务或 Microsoft 团队通过单击**添加 Skype 会议**按钮在 Web 上的 Outlook 或 outlook 使用 Skype Meeting 外接程序安排的会议都将迁移。 如果用户复制和粘贴到新的会议的 Skype 联机会议信息从一个会议，则不会更新该新的会议，由于没有原始服务中的没有会议。
- MMS 运行后，不会保留会议内容已创建或连接到会议 （白板、 投票，等等）。 如果你的会议组织者提前对会议附加了内容，在 MMS 运行之后需要重新创建该内容。
- 日历项以及 Skype 会议中共享会议笔记的链接也会被覆盖。 请注意，仍将存储在 OneNote 中的实际会议备注是存在;它是仅链接到共享便笺的都将被覆盖。
- 与会者超过 250（包括组织者）的会议不会迁移。
- 邀请的正文中的某些 UNICODE 字符可能会错误地更新下列特殊字符之一： ï，¿，½。

## <a name="triggering-mms-for-a-user"></a>用户的触发 MMS

本节介绍在以下情况下触发 MMS 时，会发生什么情况：

- 到云时从内部部署迁移用户
- 当管理员对用户的音频会议设置进行了更改 
- 在用户升级到 TeamsOnly 模式 （仅适用于点击客户）
- 当您使用 PowerShell 

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>更新会议的内部部署用户移到云中时

这是其中 MMS 帮助创建更平稳转换为您的用户的最常见方案。 但不会议迁移现有会议按 Skype 中为 Business Server 内部部署的用户将不再起作用后联机移动该用户。 因此，当您使用的内部部署管理工具 (是`Move-CsUser`或管理控制面板) 以将用户移动到云，现有会议将自动移动到云，如下所示：

- 如果`MoveToTeams`中切换`Move-CsUser`指定，则会议都将迁移直接到团队。 使用此开关需要 Skype Business Server CU8 或更高版本。
- 否则会议都将迁移到 Skype 业务 online。

在任一情况下，如果用户已分配的音频会议许可证之前被移动到云，会议将创建使用电话拨入式坐标。 如果用户从内部部署迁移到云，并且想要使用音频会议的用户，我们建议您首先分配音频会议，移动用户，以便触发仅 1 会议迁移之前。

> [!NOTE]
> 当前直接向团队通过 MoveToTeams 交换机迁移会议的功能才可用点击中。 如果您不是点击客户并指定了 MoveToTeams 开关，用户将移至 TeamsOnly 模式，但会议将被移动到 Skype 业务 online。 即使用户处于 TeamsOnly 模式，他们仍可以加入任何 Skype 业务会议。

### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>更新会议用户的音频会议设置更改时

在以下情况下，MMS 会更新现有 Skype 业务和 Microsoft 团队会议添加、 删除或修改电话拨入式坐标：

- 第三方音频会议提供商未启用时，您可以分配或删除用户和该用户的 Microsoft 音频会议服务许可证。
- 当您更改用户的音频会议提供商从任何其他提供程序为 Microsoft，提供用户分配 Microsoft 音频会议许可证。 有关详细信息，请参阅[分配 Microsoft 作为音频会议提供商](https://docs.microsoft.com/en-us/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。 另请注意，支持第三方音频会议提供商 [ACP] 已安排生命周期结束上 2019，年 4 月 1，为[以前宣布](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers)。
- 当您启用或禁用的用户的音频会议。
- 当您更改或重置用户配置为使用公开会议的会议 ID。
- 当您将用户移动到新的音频会议桥。
- 当从音频会议桥的电话号码时未分配。 这是一个复杂的方案，需要执行附加步骤。 有关详细信息，请参阅[Change 音频会议网桥上的电话号码](https://docs.microsoft.com/en-us/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。

并非所有更改用户的音频会议设置都触发 MMS。 具体地说，下列两种更改不会使 MMS 更新会议：

- 当你更改会议组织者的 SIP 地址（其 SIP 用户名或 SIP 域）时
- 当您更改您的组织的会议 URL 使用`Update-CsTenantMeetingUrl`命令。


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>更新会议分配 TeamsUpgradePolicy 时

> [!NOTE]
> 本节介绍将首先对可点击客户的即将发布功能。

默认情况下，会议迁移时，会自动触发向用户授予实例`TeamsUpgradePolicy`与`mode=TeamsOnly`或`mode= SfBWithTeamsCollabAndMeetings`。 如果您不希望将会议迁移授予这些模式，之一时，然后指定`MigrateMeetingsToTeams $false`中`Grant-CsTeamsUpgradePolicy`。

此外请注意以下情况：

- 会议迁移时才会激活您授予`TeamsUpgradePolicy`为某个特定用户。 如果您授予`TeamsUpgradePolicy`与`mode=TeamsOnly`或`mode=SfBWithTeamsCollabAndMeetings`在租户范围内，会议迁移不调用。
- 用户只能授予 TeamsOnly 模式如果用户驻留联机。 必须使用移动用户驻留在内部部署的`Move-CsUser`如上文所述。
- 授予 TeamsOnly 或 SfBWithTeamsCollabAndMeetings 模式不转换现有团队会议为 Skype 业务会议。

### <a name="trigger-meeting-migration-manually-via-powershell"></a>通过 PowerShell 自定义手动触发会议迁移

除了自动会议迁移，管理员可以手动触发会议迁移的用户通过运行 cmdlet `Start-CsExMeetingMigration`。 此 cmdlet 队列中指定的用户的迁移请求。 新`TargetMeetingType`（这是当前仅限于技术应用程序中的参与者） 参数可以指定如何迁移会议： 

- 使用`TargetMeetingType Current`指定的业务会议的 Skype 能够 Skype 业务会议并团队会议保持团队会议。 可能更改但是音频会议协调，和业务会议的任何本地 Skype 将业务 online 迁移到 Skype。
- 使用`TargetMeetingType Teams`指定必须将任何现有会议迁移到团队，无论是否会议位于 Skype 中适用于商务联机或本地和无论是否需要的任何音频会议更新如下。 

下面的示例演示如何启动会议迁移用户 ashaw@contoso.com，以便所有会议都将都迁移到团队：

```
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```

> [!NOTE]
> 开始 CsExMeetingMigration cmdlet 可供所有客户，但新 TargetMeetingTypeParameter 仅目前点击客户的功能。 


## <a name="managing-mms"></a>管理 MMS

使用 Windows PowerShell，可以检查持续迁移的状态、 手动触发会议迁移和完全禁用迁移。 

### <a name="check-the-status-of-meeting-migrations"></a>检查会议迁移的状态

您使用`Get-CsMeetingMigrationStatus`cmdlet 来检查会议迁移的状态。 下面列出了一些示例。

- 要获取所有 MMS 迁移摘要状态，请运行以下命令提供所有迁移状态的表格视图：

    ```
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- 若要获取特定时间段内的所有迁移的完整详细信息，请使用`StartTime`和`EndTime`参数。 例如，以下命令将返回完整详细信息发生的所有迁移 2018 年 10 月 1，从到 2018 年 10 月 8。

    ```
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- 若要检查的特定用户迁移状态，请使用`Identity`参数。 例如，运行以下命令会返回用户 ashaw@contoso.com 的状态：

    ```
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
如果您看到任何已失败的迁移，采取操作来解决这些问题尽快，因为用户将能够电话拨入式会议按这些用户，直到您解决这些问题。 如果`Get-CsMeetingMigrationStatus`显示任何迁移在故障状态，执行以下步骤：
 
1. 确定受影响的用户。 运行以下命令获取受影响的用户列表，以及报告的具体错误：

    ```
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table Identity, LastMessage
    ```
2. 对于每个受影响的用户，运行会议迁移工具以手动将迁移其会议。

3. 如果使用会议迁移工具还是无法完成迁移，你有两个选择：

    - 让用户创建新的 Skype 会议。
    - [联系支持人员](https://go.microsoft.com/fwlink/p/?LinkID=518322)。


### <a name="enabling-and-disabling-mms"></a>启用和禁用 MMS

所有组织，默认情况下启用 MMS，但可以禁用，如下所示：

- 完全禁用租户。 
- 只禁用与音频会议相关的更改。 在这种情况下，MMS 将用户从内部部署到云或授予 TeamsOnly 模式或 SfBWithTeamsCollabAndMeetings 模式中的迁移时仍运行`TeamsUpgradePolicy`。

例如，您可能想要手动迁移所有会议或更改您的组织的音频会议设置的大量时暂时禁用 MMS

若要查看 MMS 启用您的组织，请运行以下命令。 如果启用 MMS `MeetingMigrationEnabled` ，则参数`$true`。
```
Get-CsTenantMigrationConfiguration
```
若要启用或禁用 MMS 完全，使用`Set-CsTenantMigrationConfiguration`命令。 例如，若要禁用 MMS，运行以下命令：

```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
如果您想检查它是否已启用音频会议更新 MMS 启用组织中，检查的值`AutomaticallyMigrateUserMeetings`中的输出参数`Get-CsOnlineDialInConferencingTenantSettings`。 若要启用或禁用 MMS 为音频会议，请使用`Set-CsOnlineDialInConferencingTenantSettings`。 例如，若要禁用 MMS 为音频会议，请运行以下命令：

```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[内部部署和云之间移动用户](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)
