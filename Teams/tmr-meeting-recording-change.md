---
title: 使用OneDrive for Business和 SharePoint 进行会议录制
author: CarolynRowe
ms.author: crowe
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中从 Stream 切换到 OneDrive for Business 和 SharePoint 会议录制存储。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: bc315353e1ece0b4d455937c1677e35e3c18d152
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794150"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>使用OneDrive for Business和 SharePoint 或 Stream 进行会议录制

> [!NOTE]
> 从 2021 年 8 月 30 日起，已完成将 Teams 会议录制从经典流存储到 OneDrive 和 SharePoint (ODSP) 的更改。 所有录制现在都存储在 ODSP 中。 此更改将替代 RecordingStorageMode 策略，在 PowerShell 中修改设置不再有任何影响。

|日期&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|事件&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|2020 年 10 月 5 日<br> *（完成）* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| 你允许 Teams 会议策略将会议录制保存到OneDrive for Business和 SharePoint，而不是Microsoft Stream (经典) |
|从 2021 年 1 月 7 日开始推出<br> *（完成）* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|除非通过修改组织的 Teams 会议策略并将其显式设置为 **Stream** 来延迟此更改，否则所有新的 Teams 会议录制都将保存到 OneDrive for Business 和 SharePoint。 将策略报告视为 Stream 是不够的。 需要将策略值显式设置为 **Stream**。|
|从 2021 年 1 月 11 日开始推出<br> *（完成）* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**仅限 GCC**<br> 虽然 GCC 客户可以选择从 10 月 5 日开始退出，但你无法选择加入。 此功能将从 2021 年 1 月 11 日起向所有 GCC 客户推出，除非你已选择退出。<br>  <br>从 2021 年 1 月 11 日开始，所有面向 GCC 客户的新 Teams 会议录制都将保存到 OneDrive for Business 和 SharePoint，除非通过修改组织的 Teams 会议策略并将其显式设置为 **Stream** 来延迟此更改。 <br><br>如果已选择退出，但已准备好启用此功能，则可以通过将 Teams 会议策略显式设置为 **OneDrive for Business** 来执行此操作。 |
|从 2021 年 3 月 1 日开始推出<br> *（完成）*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**仅限 GCC-High 和 DoD**<br> 现在，客户可以首次在其 Microsoft Teams 中启用云会议录制。 默认情况下，这些录制将在 OneDrive 和 SharePoint 上存储和播放。 |
|从 2021 年 8 月 16 日开始以增量方式推出 <br> *（完成）* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**所有客户（企业版、教育版和 GCC）**<br>无法将新的会议录制保存到Microsoft Stream (经典) ;所有客户将自动将会议录制保存到OneDrive for Business和 SharePoint，即使他们已将其 Teams 会议策略更改为流式传输。<br><br> 为了更好地控制组织中的更改，建议客户在对更改感到满意时选择加入，而不是等待更改发生。 |

Microsoft Teams 推出了一种保存会议记录的新方法。 作为从经典Microsoft Stream过渡到[新流](/stream/streamnew/new-stream)的第一阶段，此方法将录制内容存储在 microsoft 365 中的 Microsoft OneDrive for Business 和 SharePoint 上，并提供许多好处。

> [!NOTE]
> 如果 Teams 会议录制未能成功上传到 OneDrive/SharePoint，将显示“录制意外结束”错误消息，而录制将暂时保存到 Azure 媒体服务 (AMS) 。 存储在 AMS 中后，不会尝试将录制自动上传到 OneDrive/SharePoint 或 Stream。

存储在 AMS 中的会议录制文件在自动删除之前可使用 21 天。 如果用户需要保留副本，则可以从 AMS 下载视频。

使用OneDrive for Business和 SharePoint 存储录音的好处包括：

- Teams 会议录制 (TMR) 的保留策略（S+C E5 自动保留标签）
- 受益于OneDrive for Business和 SharePoint 信息治理
- 易于设置权限和共享
- 仅通过显式共享与来宾（外部用户）共享录制内容
- 请求访问流
- 提供OneDrive for Business和 SharePoint 共享链接
- 可更快地获得会议录制
- **转到本地** 租户支持
- 多地理位置支持 – 录制内容存储在特定于该用户的区域中
- 创建自己的密钥 (BYOK) 支持

查看[当前可用的功能以及随时间推移预期推出的功能](/stream/streamnew/features-new-version-stream)完整列表。

有关详细信息，请观看“Microsoft Teams 会议录制的新增功能”。

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>为OneDrive for Business和 SharePoint 设置会议录制选项

会议录制选项是 Teams 策略级别的设置。 以下示例说明了如何设置全局策略。 确保为分配给用户的策略设置会议录制选项。

> [!Note]
> Teams 会议策略更改需要一段时间才能传播。设置几小时后再次检查，然后注销并再次登录到 Teams 桌面应用，或者只需重启计算机即可。

1. 安装 Teams PowerShell。

   > [!NOTE]
   > Skype for Business Online 连接器目前是最新 Teams PowerShell 模块的一部分。 如果使用的是最新 Teams PowerShell 公共版本，则无需安装 Skype for Business Online 连接器。 请参阅[使用 PowerShell 管理 Skype for Business Online](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?preserve-view=true&view=o365-worldwide)。

2. 以管理员身份启动 PowerShell。

3. 安装 [Teams PowerShell 模块](./teams-powershell-install.md)。

4. 导入 MicrosoftTeams 模块并以 Teams 管理员身份登录。

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

5. 使用 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) 设置 Teams 会议策略，以便从流存储过渡到 OneDrive for Business 和 SharePoint。

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> 如果某些用户分配了每个组织者或每个用户的策略，则必须在此策略上设置此设置（如果希望它们也将其存储在 OneDrive for Business 和 SharePoint 中）。 若要了解详细信息，请参阅[管理 Teams 中的会议策略](meeting-policies-overview.md)。


## <a name="permissions-or-role-based-access"></a>权限或基于角色的访问

> [!Note]
> 我们建议在共享 Teams 会议录制时，收件人必须是登录用户。 在 [共享 Share SharePoint 文件或文件夹](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US)中所述的文件时，选择“组织 **)  (** 人员”选项。 外部共享不是为分发大型文件或大量文件而设计的。 为了防止欺诈和滥用情况，在向外部用户共享大量数据时可能会遇到问题。

|会议类型                               | 谁单击了“录制”？| 录制内容位于何处？                               |谁具有访问权限？ R/W、R 或共享                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|与内部参与方进行 1 对 1 通话             |呼叫方                 |呼叫方的 OneDrive for Business 账户                        |呼叫方是所有者，且具有完全权限。 <br /><br />被呼叫方（如果在同一租户中）具有只读访问权限。没有共享访问权限。 <br /><br /> 被呼叫方（如果位于不同租户中）没有访问权限。 呼叫方必须将其共享给被呼叫方。|
|与内部参与方的 1 对 1 通话             |被呼叫方                 |被呼叫方的 OneDrive for Business 账户                        |被呼叫方是所有者，且具有完全权限。 <br /><br />呼叫方（如果在同一租户中）具有只读访问权限。 <br /><br />呼叫方（如果位于不同的租户中）无访问权限。 被呼叫方必须将其共享给呼叫方。|
|使用外部呼叫进行 1：1 通话             |呼叫方                 |呼叫方的 OneDrive for Business 账户                        |呼叫方是所有者，且具有完全权限。<br /> <br />被呼叫方没有访问权限。 呼叫方必须将其共享给被呼叫方。|
|使用外部呼叫进行 1：1 通话             |被呼叫方                 |被呼叫方的 OneDrive for Business 账户                        |被呼叫方是所有者，且具有完全权限。<br /><br />呼叫方没有访问权限。 被呼叫方必须将其共享给呼叫方。|
|群组通话                                 |通话的任何成员 |单击“录制”的组成员的 OneDrive for Business 帐户  |单击“录制”的成员具有完全权限。 <br /><br /> 同一租户中的其他组成员具有读取权限。 <br /><br /> 来自不同租户的其他组成员没有权限。|
|临时/计划的会议                    |组织者              |组织者的 OneDrive for Business 账户                     |组织者对录制内容具有完全权限。 <br /><br /> 会议的所有其他成员均具有读取访问权限。|
|临时/计划的会议                    |其他会议成员   |单击“录制”的会议成员                                  |单击“录制”的成员对录制内容具有完全权限。 <br /><br />组织者具有编辑权限，且可以共享。<br /><br /> 所有其他会议成员均具有读取访问权限。|
|与外部用户的临时/计划会议|组织者              |组织者的 OneDrive for Business 账户                     |组织者对录制内容具有完全权限。<br /> <br /> 来自组织者所在的同一租户的会议所有其他成员均具有读取访问权限。 <br /><br /> 所有其他外部成员均无访问权限，并且组织者必须将其共享给他们。|
|与外部用户的临时/计划会议|其他会议成员   |单击“录制”的成员                                  |单击“录制”的成员对录制内容具有完全权限。 组织者具有编辑权限，且可以共享。 <br /><br /> 来自组织者所在的同一租户的会议所有其他成员均具有读取访问权限。 <br /><br />所有其他外部成员均无访问权限，并且组织者必须将其共享给他们。|
|频道会议                            |频道成员         |该频道的 Teams SharePoint 位置。 **注意**：基于 IP 的限制不支持将频道会议录制上传到 SharePoint。 建议使用 [Azure 条件访问](/azure/active-directory/conditional-access/overview)。 |单击“录制”的成员具有录制的编辑权限。 <br /> <br />其他每个成员的权限都基于频道 SharePoint 权限。|

## <a name="frequently-asked-questions"></a>常见问题解答

**会议录制将存储在何处？**

- 对于非频道会议，录制内容存储在名为 **“录制**”的文件夹中，该文件夹位于OneDrive for Business的顶层，属于开始会议录制的人员。 示例：

  <i>记录器的OneDrive for Business</i>/**记录器**

- 对于频道会议，录制内容存储在 Teams 网站文档库中名为 **“录制”** 的文件夹中。 示例：

  <i>Teams 名称 - 频道名称</i>/**文件**/**录音**

**当 Stream 文件 (（例如录制) ）存储在 SharePoint/OneDrive 中时，如何确定它们的去向？管理员是否能够更改其去向？**

默认情况下，所有录制文件都将转到选择 **“记录**”的用户的 OneDrive 帐户。 对于频道会议，录制内容将始终转到频道的 SharePoint 网站。 管理员无法更改记录的存储位置。

**如何实现处理前雇员的录音？**

由于视频与 OneDrive for Business 和 SharePoint 中的任何其他文件一样，因此在员工离职后处理所有权和保留将遵循正常的[OneDrive for Business和 SharePoint 过程](/onedrive/retention-and-deletion)。

**谁有权查看会议录制？**

- 对于非频道会议，除外部用户外，所有会议受邀者都将自动获得个人共享链接。 外部用户需要由会议组织者或开始会议录制的人员显式添加到共享列表中。

- 对于频道会议，权限从频道中的所有者和成员列表继承。

> [!NOTE]
> 录制完成保存后，你将不会收到电子邮件，但录制将在会议聊天完成后显示在会议聊天中。 这比之前在 Stream 中执行的要快得多。

**如何管理字幕？**

仅当用户在录制时打开了听录功能时，才会在播放期间提供 Teams 会议录制内容的隐藏式字幕。 管理员必须 [启用录制听录](meetings-policies-recording-and-transcription.md#allow-transcription) ，以确保其用户可以选择使用听录记录会议。

作为所有者，你可以隐藏会议录制内容中的字幕，尽管会议脚本仍可在 Teams 上使用，除非你将其从 Teams 删除。

在录制会议后的 60 天内，Teams 会议录制支持隐藏式字幕。

如果在 OneDrive for Business 或 SharePoint 上移动或复制 Teams 会议录制的原始位置，则不完全支持隐藏字幕。

> [!NOTE]
> 将提供仅限英语的隐藏式字幕（会议听录在 GCC 中尚不可用）。

**我的存储配额将受到怎样的影响？**

Teams 会议录制文件以 OneDrive for Business 和 SharePoint 为生，并包含在这些服务的配额中。 请参阅 [SharePoint 配额](/sharepoint/sites/plan-site-maintenance-and-management#quotas)和[OneDrive for Business配额](/onedrive/set-default-storage-space)。

与 Stream 相比，使用 [OneDrive for Business](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) 可以获得更多存储，使用 SharePoint 可以获得更多可互换存储。

**如何播放 Teams 会议录制？**

视频将在OneDrive for Business或 SharePoint 的视频播放器上播放，具体取决于你访问文件的位置。

**如果计划弃用添加到 Stream，现有视频会保持原样，持续多久？**

作为平台的流在不久的将来不会弃用。 当前在 Stream 中直播的视频将一直保留在那里，直到开始迁移为止。 迁移后，这些视频也将迁移到 OneDrive for Business 或 SharePoint。 有关详细信息，请查看 [迁移详细](/stream/streamnew/migration-details) 信息。

**如何实现将保留标签应用于 Microsoft Teams 会议录制？**

请参阅 [如何自动应用保留标签](/microsoft-365/compliance/apply-retention-labels-automatically)。

**如何实现为 Microsoft Teams 中的用户分配策略，哪些策略优先？**

请参阅[哪个策略优先？](./policy-assignment-overview.md#which-policy-takes-precedence)

**如果用户没有OneDrive for Business或 SharePoint，或者存储配额已满，录制将走向何方？**

录制将降落在我们的临时存储位置，在那里将举行 21 天。 在此期间，组织者必须下载录制。 如果在 21 天内未下载，则会删除录制。
