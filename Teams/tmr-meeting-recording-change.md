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
description: 了解如何从流式传输切换到OneDrive for Business SharePoint会议录制存储Microsoft Teams。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: d0de88cd3295e1e04681cf6ff63bccab80e4b4a8
ms.sourcegitcommit: a731226d62d8b23fe73bd7bf61654e16367fbd90
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "51948658"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>使用OneDrive for Business或SharePoint流进行会议录制

> [!Note]
> 从使用 Microsoft Stream 更改为使用 OneDrive for Business 和 Microsoft SharePoint 录制会议是一种分阶段的方法。

|<div style="width:290px">日期&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |事件&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|2020 年 10 月 5 日<br> *(完成)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| 启用 Teams 会议策略，将会议录制保存到 OneDrive for Business SharePoint 而不是 Microsoft Stream (经典) |
|从 2021 年 1 月 7 日开始推出<br> *(完成)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|所有Teams会议录制都将保存到 OneDrive for Business 和 SharePoint，除非你通过修改组织的 Teams 会议策略并显式将其设置为"流式传输"来延迟此 **更改。** 将策略报告视为流是不够的。 需要将策略值显式设置为"流 **式传输"。**|
|从 2021 年 1 月 11 日开始推出<br> *(完成)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC仅**<br> 虽然GCC客户可以从 10 月 5 日起选择退出，但无法选择加入。 此功能将于 2021 年 1 GCC 11 日开始向所有客户推出，除非已选择退出。<br>  <br>从 2021 年 1 月 11 日开始，GCC 客户的所有新 Teams 会议录制都将保存到 OneDrive for Business 和 SharePoint，除非你通过修改组织的 Teams 会议策略并显式将其设置为流式传输来延迟此 **更改。** <br><br>如果已选择退出，但已准备好启用此功能，则为此，可显式Teams会议策略以 **OneDrive for Business。** |
|从 2021 年 3 月 1 日推出<br> *(完成)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC-High 和 DoD**<br> 现在，客户可以首次在Microsoft Teams启用云会议录制。 默认情况下，这些录音将存储并OneDrive SharePoint播放。 |
|从 2021 年 7 月 7 日开始逐步推出 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**所有客户 (Enterprise、教育GCC)**<br>无法将新的会议录制保存到经典 (Microsoft Stream) ;即使所有客户将会议策略更改为OneDrive for Business，SharePoint会议录制也将自动保存到Teams流式传输。<br><br> 我们建议客户为了更好地控制组织的变化，每当你习惯更改时都选择加入，而不是等待更改发生。 |

Microsoft Teams有一种保存会议录制的新方法。 作为从经典 Microsoft Stream 过渡到新 Stream[](/stream/streamnew/new-stream)的第一阶段，此方法将录制存储在 Microsoft OneDrive for Business 和 SharePoint Microsoft 365 中，并提供许多优势。

> [!NOTE]
> 如果Teams会议录制无法成功上传到 OneDrive/SharePoint，则录制内容将暂时保存到AZURE 媒体服务 (AMS) 。 存储在 AMS 中后，不会尝试自动将录制内容上传到OneDrive/SharePoint流。

AMS 中存储的会议录制在自动删除前 21 天内可用。 如果需要保留副本，用户可以从 AMS 下载视频。

使用录音和OneDrive for Business SharePoint的好处包括：

- TMR Teams S+C E5 自动 (标签)  (会议录制的保留) 
- 从 OneDrive for Business 和信息SharePoint中获益
- 轻松设置权限和共享
- 与来宾共享录制 (外部用户) 显式共享
- 请求访问流
- 提供OneDrive for Business和SharePoint链接
- 会议录制更快可用
- **Go 本地** 租户支持
- 多地域支持 - 录制存储在特定于该用户的区域
- 自带密钥 (BYOK) 支持

查看当前可用的 [功能的完整列表以及随着时间的推移预期的功能](https://docs.microsoft.com/stream/streamnew/features-new-version-stream)。 

有关详细信息，请观看"Microsoft Teams录制的新增功能"。

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>为录制和录制设置OneDrive for Business SharePoint

会议录制选项是策略级别的Teams设置。 以下示例演示如何设置全局策略。 请确保为分配给用户的策略设置会议录制选项。

> [!Note]
> Teams会议策略更改需要一段时间才能传播。 设置数小时后返回检查，然后注销并再次登录到 Teams 桌面应用，或只需重启计算机。

1. 安装 Teams PowerShell。

   > [!NOTE]
   > Skype for Business联机连接器当前是 PowerShell 模块Teams的一部分。 如果使用最新的 PowerShell Teams版本，则无需安装 Skype for Business Online 连接器。 请参阅[使用 PowerShell Skype for Business Online 管理网络](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?preserve-view=true&view=o365-worldwide)。

2. 以管理员角色启动 PowerShell。

3. 安装[Teams PowerShell 模块](./teams-powershell-install.md)。

4. 导入 MicrosoftTeams 模块，以管理员Teams登录。


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
> 如果你的一些用户已分配了按组织者或按用户的策略，如果你希望他们同时将会议录制存储在 OneDrive for Business 和 SharePoint 中，则必须对此策略设置此设置。 有关详细信息，请参阅在 Teams[中管理会议策略](meeting-policies-in-teams.md)。

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>选择退出 OneDrive for Business SharePoint以继续使用流

即使策略指出已设置为"流 **式传输"，** 也可能未设置该策略。 通常，如果未设置策略，则默认设置为"流 **"。** 但是，使用此新更改时，如果要选择退出使用 SharePoint 或 OneDrive for Business，则必须将策略重置为"流"，以确保 **"** 流"是默认值。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>权限或基于角色的访问

> [!Note]
> 建议在共享会议录制时，收件人必须Teams登录的用户。 共享 **文件 (或**) 中记录的文件时，请选择"组织SharePoint [人员"选项](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US)。 外部共享不是针对大型文件或大量文件的分发而设计的。 为了防止欺诈和滥用情况，与外部用户共享大量数据时可能会遇到问题。

|会议类型                               | Who单击"记录"？| 录制内容将登陆何处？                               |Who访问权限？ R/W、R 或共享                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|与内部方进行 1：1 通话             |呼叫者                 |呼叫方OneDrive for Business帐户                        |调用方是所有者，拥有完全权限。 <br /><br />如果 (同一租户) 具有只读访问权限，将调用者。 无共享访问权限。 <br /><br /> 如果 (租户中无法访问，) 被呼叫方。 呼叫方必须共享给被呼叫者。|
|与内部方进行 1：1 通话             |被叫方                 |被呼叫者OneDrive for Business帐户                        |被呼叫者是所有者，拥有完全权利。 <br /><br />如果 (租户中具有只读访问权限，则调用方会进行调用。 无共享访问权限。 <br /><br />如果 (租户中，调用方) 无法访问。 被呼叫者必须共享给呼叫方。|
|通过外部呼叫进行 1：1 通话             |呼叫者                 |呼叫方OneDrive for Business帐户                        |调用方是所有者，拥有完全权限。<br /> <br />被呼叫者没有访问权限。 呼叫方必须共享给被呼叫者。|
|通过外部呼叫进行 1：1 通话             |被叫方                 |被呼叫者OneDrive for Business帐户                        |被呼叫者是所有者，拥有完全权利。<br /><br />调用方没有访问权限。 被呼叫者必须共享给呼叫方。|
|群组通话                                 |呼叫的任何成员 |单击记录帐户的OneDrive for Business成员  |单击"记录"的成员具有完全权限。 <br /><br /> 同一租户的其他 fr 具有读取权限。 <br /><br /> 不同租户的其他组成员没有权限。|
|临时会议/已计划会议                    |组织者              |组织者的OneDrive for Business帐户                     |组织者对录制内容拥有完全权限。 <br /><br /> 会议的其他所有成员都具有读取访问权限。|
|临时会议/已计划会议                    |其他会议成员   |单击"记录"的会议成员                                  |单击"录制"的成员对录制具有完全权限。 <br /><br />组织者具有编辑权限，可以共享。<br /><br /> 所有其他会议成员具有读取访问权限。|
|与外部用户的临时/计划会议|组织者              |组织者的OneDrive for Business帐户                     |组织者对录制内容拥有完全权限。<br /> <br /> 会议的所有其他成员与组织者同一租户具有读取访问权限。 <br /><br /> 所有其他外部成员没有访问权限，组织者必须将其共享给他们。|
|与外部用户的临时/计划会议|其他会议成员   |单击"记录"的成员                                  |单击"录制"的成员对录制具有完全权限。 组织者具有编辑权限，可以共享。 <br /><br /> 会议的所有其他成员与组织者同一租户具有读取访问权限。 <br /><br />所有其他外部成员没有访问权限，组织者必须将其共享给他们。|
|频道会议                            |频道成员         |Teams通道SharePoint位置                   |单击"录制"的成员对录制具有编辑权限。 <br /> <br />每个其他成员的权限都基于频道SharePoint权限。|

## <a name="frequently-asked-questions"></a>常见问题解答

**会议录制内容将存储在何处？**

- 对于非频道会议，录制内容存储在名为 **"** 录制"的文件夹中，该文件夹位于会议录制OneDrive for Business的顶级文件夹。 示例：

  <i>录音机OneDrive for Business</i> /**录制**

- 对于频道会议，录制内容存储在Teams文档库中名为"录制 **"的文件夹中**。 示例：

  <i>Teams名称 - 频道名称</i> /**文档** /**录制**

**流式 (文件（如) 存储在 SharePoint/OneDrive 中时，如何确定它们的位置？管理员能否更改其位置？**

默认情况下，所有录制文件都将转到OneDrive"录制"的用户 **的帐户。** 对于频道会议，录制内容将始终转到SharePoint的录制网站。 管理员不能更改录制内容存储位置。

**如何处理以前员工的录音？**

由于视频与文件和视频OneDrive for Business文件SharePoint，因此处理员工离职后的所有权和保留期将遵循正常的OneDrive for Business SharePoint[过程]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)。

**Who有权查看会议录制内容？**

- 对于非频道会议，所有会议被邀请者（外部用户除外）将自动获得个人共享链接。 外部用户将需要由会议组织者或开始会议录制的人显式添加到共享列表中。

- 对于频道会议，权限继承自频道中的所有者和成员列表。

> [!NOTE]
> 录制完成保存后，你将不会收到电子邮件，但录制完成后，录制内容将显示在会议聊天中。 这比之前在流中发生的要快得多。
> 你可以控制与谁共享录制内容，但无法阻止具有共享访问权限的人下载录制内容。  

**如何管理字幕？**

只有当用户在录制Teams已打开听录时，才能在播放过程中使用会议录制的隐藏式字幕。 管理员必须通过 [策略启用录制听录]( https://docs.microsoft.com/microsoftteams/cloud-recording#turn-on-or-turn-off-recording-transcription) ，以确保其用户可以选择使用听录录制来录制会议。

题注可帮助所有功能观看者创建包容性内容。 作为所有者，您可以在会议录制内容上隐藏字幕，尽管会议脚本仍可用于Teams，除非将其删除。 

从录制会议开始Teams 60 天内，会议录制都支持隐藏式字幕。

如果将会议录制内容移动或Teams从会议录制内容的原始位置移动或复制，则隐藏式字幕OneDrive for Business SharePoint。

> [!NOTE]
> 会议听录中尚 (提供仅英语隐藏式字幕GCC) 。

**我的存储配额受到怎样的影响？**

Teams录制文件以OneDrive for Business SharePoint并包含在这些服务的配额中。 请参阅[SharePoint配额](/sharepoint/sites/plan-site-maintenance-and-management#quotas)和[OneDrive for Business配额](/onedrive/set-default-storage-space)。

与流相比，[使用](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)OneDrive for Business 可获取更多存储空间，使用 SharePoint。

**如何播放会议Teams录制？**

视频将在视频播放器上播放OneDrive for Business SharePoint，具体取决于你访问文件的位置。

**如果计划弃用添加到流，现有视频是否将保持现有和持续多久？**

在不久的将来，不会弃用作为平台的流。 流中当前提供的视频将一直留在该位置，直到我们开始迁移。 迁移后，这些视频也将迁移到OneDrive for Business SharePoint或视频。 有关详细信息 [，请查看流式](/stream/streamnew/classic-migration) 传输经典迁移。

**如何应用保留标签？**

请参阅 [如何自动应用保留标签](/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings)。

**如何向用户分配策略Microsoft Teams哪些策略优先？**

请参阅[哪个策略优先？。](./assign-policies.md#which-policy-takes-precedence)

**如果用户没有录制内容或OneDrive for Business SharePoint？**

录制内容将登陆到临时存储位置，该位置将保存 21 天。 在此期间，组织者必须下载录制内容。 如果未在 21 天内下载，则删除录制内容。

