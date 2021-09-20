---
title: 将OneDrive for Business和SharePoint用于会议录制
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: 6d8f04eebbd1123bf753c221e49a2b523d91ff43
ms.sourcegitcommit: cf2f96dbd485ac4cc822c5a591ccce6b47f12cc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2021
ms.locfileid: "59456392"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>使用OneDrive for Business或SharePoint流进行会议录制

> [!NOTE]
> 从经典流Teams到 OneDrive 和 SharePoint (ODSP) 存储会议录制的更改已在 2021 年 8 月 30 日完成。 现在，所有录制都存储在 ODSP 中。 此更改将覆盖 RecordingStorageMode 策略，并且修改 PowerShell 中的设置不再具有任何影响。

|日期&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|事件&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|2020 年 10 月 5 日<br> *（完成）* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| 启用 Teams 会议策略，将会议录制保存到 OneDrive for Business SharePoint 而不是 Microsoft Stream (经典) |
|从 2021 年 1 月 7 日开始推出<br> *（完成）* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|所有Teams会议录制都将保存到 OneDrive for Business 和 SharePoint 除非您通过修改组织的 Teams 会议策略并显式将其设置为流式传输来延迟此 **更改**。 将策略报告视为 Stream 是不够的。 需要将策略值显式设置为 **Stream**。|
|从 2021 年 1 月 11 日开始推出<br> *（完成）* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**仅限 GCC**<br> 虽然 GCC 客户可以选择从 10 月 5 日开始退出，但你无法选择加入。 此功能将从 2021 年 1 月 11 日起向所有 GCC 客户推出，除非你已选择退出。<br>  <br>从 2021 年 1 月 11 日开始，GCC 客户的所有新 Teams 会议录制都将保存到 OneDrive for Business 和 SharePoint，除非你通过修改组织的 Teams 会议策略并显式将其设置为流式传输来延迟此 **更改。** <br><br>如果已选择退出，但已准备好启用此功能，则可以通过将 Teams 会议策略显式设置为 **OneDrive for Business** 来执行此操作。 |
|从 2021 年 3 月 1 日开始推出<br> *（完成）*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**仅限 GCC-High 和 DoD**<br> 现在，客户可以首次在其 Microsoft Teams 中启用云会议录制。 默认情况下，这些录制内容将存储并OneDrive SharePoint播放。 |
|从 2021 年 8 月 16 日开始以增量方式推出 <br> *（完成）* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**所有客户（企业版、教育版和 GCC）**<br>无法将新的会议录制保存到 Microsoft Stream (经典) ;所有客户都会自动将会议录制保存到OneDrive for Business SharePoint，即使他们将会议策略更改为Teams流式传输。<br><br> 为了更好地控制组织中的更改，建议客户在对更改感到满意时选择加入，而不是等待更改发生。 |

Microsoft Teams 推出了一种保存会议记录的新方法。 作为从经典 Microsoft Stream 过渡到新流的第一[](/stream/streamnew/new-stream)阶段，此方法将录制存储在 Microsoft OneDrive for Business 和 SharePoint Microsoft 365 中，并提供许多优势。

> [!NOTE]
> 如果Teams录制无法成功上传到 OneDrive/SharePoint，将显示"录制意外结束"错误消息，录制内容将暂时保存到 Azure 媒体服务 (AMS) 。 存储在 AMS 中后，不会尝试自动将录制内容上传到OneDrive/SharePoint流。

存储在 AMS 中的会议录制文件在自动删除之前可使用 21 天。 如果用户需要保留副本，则可以从 AMS 下载视频。

使用录音和OneDrive for Business SharePoint的好处包括：

- Teams 会议录制 (TMR) 的保留策略（S+C E5 自动保留标签）
- 从信息OneDrive for Business SharePoint中获益
- 易于设置权限和共享
- 仅通过显式共享与来宾（外部用户）共享录制内容
- 请求访问流
- 提供OneDrive for Business和SharePoint链接
- 可更快地获得会议录制
- **转到本地** 租户支持
- 多地理位置支持 – 录制内容存储在特定于该用户的区域中
- 创建自己的密钥 (BYOK) 支持

查看[当前可用的功能以及随时间推移预期推出的功能](/stream/streamnew/features-new-version-stream)完整列表。

有关详细信息，请观看“Microsoft Teams 会议录制的新增功能”。

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>设置用于录制和录制OneDrive for Business SharePoint

会议录制选项是 Teams 策略级别的设置。 以下示例说明了如何设置全局策略。 确保为分配给用户的策略设置会议录制选项。

> [!Note]
> Teams 会议策略更改需要一段时间才能传播。设置几小时后再次检查，然后注销并再次登录到 Teams 桌面应用，或者只需重启计算机即可。

1. 安装 Teams PowerShell PowerShell。

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

5. 使用[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)设置 Teams 会议策略，以从流存储转换为OneDrive for Business SharePoint。

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> 如果你的一些用户已分配了按组织者或按用户的策略，如果你希望他们还在 OneDrive for Business 和 SharePoint 中存储会议录制，则必须对此策略设置此设置。 若要了解详细信息，请参阅[管理 Teams 中的会议策略](meeting-policies-in-teams.md)。

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>选择退出 OneDrive for Business SharePoint以继续使用流

即使策略指出已设置为"流 **式传输"，** 也可能未设置该策略。 通常，如果未设置策略，则默认设置为"流 **"。** 但是，使用此新更改时，如果要选择退出使用 SharePoint 或 OneDrive for Business，则必须将策略重置为"流"，以确保 **"** 流"是默认值。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>权限或基于角色的访问

> [!Note]
> 建议在共享会议录制内容时，收件人必须Teams登录的用户。 共享 **文件 (或**) 中记录的文件时，请选择"组织SharePoint [人员"选项](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US)。 外部共享不是针对大型文件或大量文件的分发而设计的。 为了防止欺诈和滥用情况，与外部用户共享大量数据时可能会遇到问题。

|会议类型                               | 谁单击了“录制”？| 录制内容位于何处？                               |谁具有访问权限？ R/W、R 或共享                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|与内部参与方进行 1 对 1 通话             |呼叫方                 |呼叫方的 OneDrive for Business 账户                        |呼叫方是所有者，且具有完全权限。 <br /><br />被呼叫方（如果在同一租户中）具有只读访问权限。没有共享访问权限。 <br /><br /> 被呼叫方（如果位于不同租户中）没有访问权限。 呼叫方必须将其共享给被呼叫方。|
|与内部参与方的 1 对 1 通话             |被呼叫方                 |被呼叫方的 OneDrive for Business 账户                        |被呼叫方是所有者，且具有完全权限。 <br /><br />呼叫方（如果在同一租户中）具有只读访问权限。 <br /><br />呼叫方（如果位于不同的租户中）无访问权限。 被呼叫方必须将其共享给呼叫方。|
|使用外部呼叫进行 1：1 通话             |呼叫方                 |呼叫方的 OneDrive for Business 账户                        |呼叫方是所有者，且具有完全权限。<br /> <br />被呼叫方没有访问权限。 呼叫方必须将其共享给被呼叫方。|
|使用外部呼叫进行 1：1 通话             |被呼叫方                 |被呼叫方的 OneDrive for Business 账户                        |被呼叫方是所有者，且具有完全权限。<br /><br />呼叫方没有访问权限。 被呼叫方必须将其共享给呼叫方。|
|群组通话                                 |通话的任何成员 |单击“录制”的组成员的 OneDrive for Business 帐户  |单击“录制”的成员具有完全权限。 <br /><br /> 同一租户的其他组成员具有读取权限。 <br /><br /> 不同租户的其他组成员没有权限。|
|临时/计划的会议                    |组织者              |组织者的 OneDrive for Business 账户                     |组织者对录制内容具有完全权限。 <br /><br /> 会议的其他所有成员都具有读取访问权限。|
|临时/计划的会议                    |其他会议成员   |单击“录制”的会议成员                                  |单击“录制”的成员对录制内容具有完全权限。 <br /><br />组织者具有编辑权限，且可以共享。<br /><br /> 所有其他会议成员具有读取访问权限。|
|与外部用户的临时/计划会议|组织者              |组织者的 OneDrive for Business 账户                     |组织者对录制内容具有完全权限。<br /> <br /> 会议的所有其他成员与组织者同一租户具有读取访问权限。 <br /><br /> 所有其他外部成员均无访问权限，并且组织者必须将其共享给他们。|
|与外部用户的临时/计划会议|其他会议成员   |单击“录制”的成员                                  |单击“录制”的成员对录制内容具有完全权限。 组织者具有编辑权限，且可以共享。 <br /><br /> 会议的所有其他成员与组织者同一租户具有读取访问权限。 <br /><br />所有其他外部成员均无访问权限，并且组织者必须将其共享给他们。|
|频道会议                            |频道成员         |Teams SharePoint通道的位置。 **注意**：基于 IP 的限制不支持SharePoint上载到视频的频道会议录制。 建议使用 [Azure 条件访问](/azure/active-directory/conditional-access/overview)。 |单击"录制"的成员对录制具有编辑权限。 <br /> <br />每个其他成员的权限都基于频道SharePoint权限。|

## <a name="frequently-asked-questions"></a>常见问题解答

**会议录制内容将存储在何处？**

- 对于非频道会议，录制内容存储在名为 **"** 录制"的文件夹中，该文件夹位于会议录制OneDrive for Business的顶级文件夹。 示例：

  <i>录音机OneDrive for Business</i> /**录制**

- 对于频道会议，录制内容存储在Teams文档库中名为"录制 **"的文件夹中**。 示例：

  <i>Teams名称 - 频道名称</i> /**文档** /**录制**

**流式 (文件（例如) ）存储在SharePoint/OneDrive中时，如何确定它们的位置？管理员能否更改其位置？**

默认情况下，所有录制文件都将转到OneDrive录制 "的用户 **的帐户。** 对于频道会议，录制内容将始终转到SharePoint的录制网站。 管理员不能更改录制内容存储位置。

**如何处理以前员工的录音？**

由于视频与视频和视频中任何其他文件OneDrive for Business SharePoint，因此处理员工离职后的所有权和保留期将遵循正常的OneDrive for Business SharePoint[过程](/onedrive/retention-and-deletion#the-onedrive-deletion-process)。

**Who有权查看会议录制内容？**

- 对于非频道会议，所有会议被邀请者（外部用户除外）将自动获得个人共享链接。 外部用户将需要由会议组织者或开始会议录制的人显式添加到共享列表中。

- 对于频道会议，权限继承自频道中的所有者和成员列表。

> [!NOTE]
> 录制完成保存后，你将不会收到电子邮件，但录制完成后，录制内容将显示在会议聊天中。 这比之前在流中发生的要快得多。

**如何管理字幕？**

仅当用户在录制时打开了听录功能时，才会在播放期间提供 Teams 会议录制内容的隐藏式字幕。 管理员必须 [通过策略启用录制听录](/microsoftteams/cloud-recording#turn-on-or-turn-off-recording-transcription)，以确保其用户可以选择使用听录来记录会议。

作为所有者，你可以隐藏会议录制内容中的字幕，尽管会议脚本仍可在 Teams 上使用，除非你将其从 Teams 删除。

从录制会议开始Teams 60 天内，会议录制都支持隐藏式字幕。

如果将会议录制内容从会议录制Teams或录制文件的原始位置移动或复制，则隐藏式字幕OneDrive for Business SharePoint。

> [!NOTE]
> 将提供仅限英语的隐藏式字幕（会议听录在 GCC 中尚不可用）。

**我的存储配额受到怎样的影响？**

Teams会议录制文件以OneDrive for Business SharePoint并包含在这些服务的配额中。 请参阅[SharePoint配额](/sharepoint/sites/plan-site-maintenance-and-management#quotas)和[OneDrive for Business配额](/onedrive/set-default-storage-space)。

与流相比，[使用](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)OneDrive for Business 可获取更多存储空间，使用流获得更SharePoint。

**如何播放会议Teams录制？**

你的视频将在视频播放器上播放OneDrive for Business SharePoint你访问该文件的位置。

**如果计划弃用添加到流，现有视频是否将保持现有和持续多久？**

在不久的将来，不会弃用作为平台的流。 流中当前提供的视频将一直留在该位置，直到我们开始迁移。 迁移后，这些视频也将迁移到OneDrive for Business或SharePoint视频。 有关详细信息 [，请查看流式](/stream/streamnew/classic-migration) 传输经典迁移。

**如何将保留标签应用于Microsoft Teams录制？**

请参阅 [如何自动应用保留标签](/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings)。

**如何向用户分配策略Microsoft Teams哪些策略优先？**

请参阅[哪个策略优先？。](./assign-policies.md#which-policy-takes-precedence)

**如果用户没有存储空间或存储空间，或者OneDrive for Business或SharePoint配额已满，录制将在哪里？**

录制内容将登陆到临时存储位置，该位置将保存 21 天。 在此期间，组织者必须下载录制内容。 如果未在 21 天内下载，则删除录制内容。
