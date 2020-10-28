---
title: 使用 OneDrive for Business 和 SharePoint 进行会议录制
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何从 Microsoft 团队中的 OneDrive for Business 和 SharePoint 会议录制存储切换到 OneDrive for Business 和 SharePoint 会议录制。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0e57587ea428d8395b65553fc05d1964daa5fb61
ms.sourcegitcommit: a1524afb546fde9844f53390fab85e7073da8cb2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2020
ms.locfileid: "48778855"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>使用 OneDrive for Business 和 SharePoint 或流进行会议录制

> [!Note]
> 使用 Microsoft Stream to OneDrive for Business 和 Microsoft SharePoint for 会议录制的更改将是一种分阶段方法。


|日期|活动|
|---|-----------------|
|第4季度早些 CY20|**OneDrive for business 和 SharePoint 上的团队会议录制可供选择加入或选择退出。**<br> 租户管理员可以选择加入或退出 OneDrive for Business 和 SharePoint 设置 PowerShell 中的团队策略|
|第4季度中旬 CY20|**OneDrive for business 和 SharePoint 上的团队会议录制设置为未选择的租户的默认设置**<br> 这是适用于大多数客户的推荐途径|
|第1季度 CY21|**不再允许将团队会议录制保存到经典流**<br>所有租户均可将团队会议录制内容保存到 OneDrive for business 和 SharePoint|

Microsoft 团队具有保存会议录制的新方法。 作为从经典 Microsoft Stream 过渡到 [新流](https://docs.microsoft.com/stream/streamnew/new-stream)的第一阶段，此方法将录制存储在 microsoft 365 中的 microsoft OneDrive for Business 和 SharePoint 中，并提供许多好处。

使用 OneDrive for Business 和 SharePoint 存储录制的好处包括：

- 团队会议录制的保留策略 (TMR)  (S + C E5 autoretention 标签) 
- 从 OneDrive for business 和 SharePoint 信息管理中获益
- 轻松设置权限和共享
- 仅具有明确共享的 (外部用户) 与来宾共享录制
- 请求访问流
- 提供 OneDrive for business 和 SharePoint 共享链接
- 增加了配额
- 会议录制更快地可用
- **转到本地** 租户支持
- 多地区支持-录制存储在特定于该用户的区域中
- 将您自己的密钥 (BYOK) 支持
- 改进的记录质量和演讲者特性

需要考虑以下限制：

- 将有英语的隐藏式字幕和脚本。
- 您将不能搜索脚本或其内容。
- 你将无法编辑这些脚本，但你可以将标题切换为 "开/关"。
- 你可以控制你共享录制的人员，但不能阻止具有共享访问权限的用户下载录制。
- 录制完成后，你将不会收到电子邮件，但录制将在会议聊天完成后显示在会议聊天中。 这将比以前在流中更快的速度

有关详细信息，请观看 "会议录制"。

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>为 OneDrive for business 和 SharePoint 设置会议录制选项

> [!Note]
> "会议录制" 选项是 "团队" 策略级别的一个设置。 以下示例显示了如何设置全局策略。 请确保为你分配给用户的策略设置了 "会议录制" 选项。
> 团队会议策略更改需要一段时间才能传播。 在设置后的几个小时后再次查看，然后注销并再次登录。

1. 安装 Skype For Business Online PowerShell。
**注意** ： Skype For Business Online 连接器目前是最新团队 PowerShell 模块的一部分。 如果您使用的是最新的团队 PowerShell 公共版本，则无需安装 Skype for Business Online 连接器。 请参阅 [管理与 PowerShell 的 Skype for Business Online](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)。

    a. 下载 [Skype For Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)。

    b. 按照提示进行安装。

    c. 重新启动计算机。

2. 以管理员身份启动 PowerShell

3. 导入 SkypeOnline 连接器并作为团队管理员登录。

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

4. 使用 [csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps&preserve-view=true) 将团队会议策略设置为从流存储过渡到 OneDrive for Business 和 SharePoint。

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>选择退出 OneDrive for Business 和 SharePoint 以继续使用流

即使策略指示它已设置为 **流** ，它也可能不会设置。 通常情况下，如果未设置策略，则默认设置为 " **流** "。 但是，如果你想要选择退出使用 SharePoint 或 OneDrive for Business，则必须将策略重置为 **流** ，以确保它是默认设置。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>权限或基于角色的访问

|会议类型                               | 单击 "记录"| 录制的土地在哪里？                               |谁有权访问？ R/W、R 或共享                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|与内部团体的1:1 通话             |呼叫者                 |呼叫者的 OneDrive for business 帐户                        |呼叫方是所有者，具有完全权限 <br /><br />被调用方 (如果在同一租户) 中具有只读访问权限，则没有共享访问权限 <br /><br /> 如果在不同租户) 中没有访问权限，则被调用方 (。 调用方必须将其共享给被呼叫方|
|与内部团体的1:1 通话             |被叫方                 |被呼叫者的 OneDrive for business 帐户                        |被呼叫方是所有者，具有完全权限 <br /><br />如果在同一租户中具有 "只读" 访问权限，则呼叫者 (，将无法进行共享访问 <br /><br />如果不同租户) 中没有访问权限，则调用方 (。 被呼叫方必须将其共享给被呼叫方|
|使用外部通话的1:1 通话             |呼叫者                 |呼叫者的 OneDrive for business 帐户                        |呼叫方是所有者，具有完全权限<br /> <br />被调用方没有访问权限。 调用方必须将其共享给被呼叫方|
|使用外部通话的1:1 通话             |被叫方                 |呼叫者的 OneDrive for business 帐户                        | 被呼叫方是所有者，具有完全权限<br /><br />呼叫方没有访问权限。 被呼叫方必须将其共享给呼叫方|
|群组通话                                 |任何呼叫成员 |单击记录的 OneDrive for Business 帐户的成员  |单击 "记录" 的成员具有完全权限 <br /><br /> 来自同一租户的其他成员具有读取权限 <br /><br /> 来自不同租户的其他成员没有权限。|
|即席/计划会议                    |组织者              |组织者的 OneDrive for Business 帐户                     | 组织者对录制具有完全的权限 <br /><br /> 会议的所有其他成员都具有 "读取" 访问权限|
|即席/计划会议                    |其他会议成员   |单击记录的成员                                  | 单击 "记录" 的成员对录制具有完全的权限 <br />组织者具有编辑权限，并且可以共享 <br /><br /> 所有其他成员都具有读取访问权限|
|与外部用户进行即席/计划会议|组织者              |组织者的 OneDrive for Business 帐户                     |组织者对录制具有完全的权限<br /> <br /> 与组织者相同的租户的所有其他会议成员都具有读取访问权限 <br /><br /> 所有其他外部成员都不具有访问权限，并且组织者必须将其共享|
|与外部用户进行即席/计划会议|其他会议成员   |单击记录的成员                                  | 单击 "记录" 的成员对录制具有完全权限-组织者具有编辑权限，并且可以共享 <br /><br /> 与组织者相同的租户的所有其他会议成员都具有读取访问权限 <br /><br />所有其他外部成员都不具有访问权限，并且组织者必须将其共享|
|频道会议                            |频道成员         |该频道的团队 SharePoint 位置                   | 单击 "记录" 的成员对录制具有编辑权限 <br /> <br />每个其他成员的权限都基于通道 SharePoint 权限|


## <a name="frequently-asked-questions"></a>常见问题解答

**会议录制将存储在何处？**

- 对于非频道会议，录制内容存储在属于开始会议录制人员 **Recordings** 的 OneDrive for business 的最高级别的文件夹中。 上例

  <i>录像机的 OneDrive For business</i> /**录制**

- 对于频道会议，录制内容存储在名为 " **录制** " 的文件夹中的 "团队网站" 文档库中。 上例

  <i>团队名称-频道名称</i> /**文档** /**录制**

**如何处理以前员工的录制？**

由于视频与 OneDrive for Business 和 SharePoint 中的任何其他文件一样，在员工离职后处理所有权和保留将遵循正常的 [OneDrive for business 和 sharepoint 进程]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)。

**哪些人具有查看会议录制的权限？**

- 对于非频道会议，除外部用户之外的所有会议被邀请者都将自动获取个人共享链接。 外部用户需要通过会议组织者或启动会议录制的人员显式添加到共享列表。

- 对于频道会议，权限继承自频道中的 "所有者" 和 "成员列表" 列表。

**如何管理脚本？**

选择加入此预览的客户将不会在其团队会议录制中提供隐藏字幕，这些标题将迁移到 OneDrive for Business 和 SharePoint。我们正在努力在2020年10月向会议录制添加字幕，以英文隐藏的字幕开始。

对于已选择加入以允许在[团队云录制](cloud-recording.md)中介绍的内容的客户，将在团队会议录制中提供隐藏式字幕

字幕有助于为所有功能的查看者创建包含内容。 作为所有者，你可以隐藏字幕，但除非你删除团队中的标题，否则仍可在团队中使用记录。 了解 [如何打开或关闭会议录制](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)

录制会议时，从录制会议的60天起，团队会议录制支持隐藏式字幕。

如果团队会议录制在 OneDrive for business 或 SharePoint 上的原始位置移动或复制，则隐藏式字幕不完全受支持。

**我的存储配额将受到怎样的影响**

工作组会议录制文件实时在 OneDrive for business 和 SharePoint 中，并包含在这些服务的配额中。 请参阅 [SharePoint 配额](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) 和 [OneDrive for business 配额] (https://docs.microsoft.com/onedrive/set-default-storage-space) 。

**如何播放团队会议录制？**

你的视频将在 OneDrive for business 或 SharePoint 的视频播放器上播放，具体取决于你访问该文件的位置。

**如果你计划将会弃用添加到 Stream，现有视频是否保持原样和持续多长时间？**

作为平台的流在不久的将来不会被弃用。 在开始迁移之前，当前实时流中的视频将一直保留。 迁移后，这些视频也将迁移到 OneDrive for business 或 SharePoint。 有关详细信息，请查看 [此处](https://docs.microsoft.com/stream/streamnew/classic-migration) 。

**如何应用保留标签？**

请参阅 [如何自动应用保留标签](https://docs.microsoft.com/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings)。
