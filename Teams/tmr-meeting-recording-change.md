---
title: 将 OneDrive 和 SharePoint 用于会议录制
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
ms.openlocfilehash: 7a42c46cf9592c64676d153e1885357a4ee8ec7b
ms.sourcegitcommit: 48cb3cdd69558ec80f8f25f870b302a65280ce5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2020
ms.locfileid: "48389930"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>使用 OneDrive for Business 和 SharePoint 或流进行会议录制

> [!Note]
> 将会议录制从 Microsoft Stream 改为 OneDrive for Business 和 SharePoint 将是一种分阶段的方法。 在启动时，租户管理员可以立即选择此新工作流选项，并开始在10月2020中查看录制自动上载到 OneDrive for Business 和 SharePoint。 11月，您必须选择退出如果您希望继续使用流，并且在2021的早期，我们将要求所有客户使用 OneDrive for Business 和 SharePoint 进行新的会议录制。

Microsoft 团队具有保存会议录制的新方法。 作为从经典 Microsoft Stream 过渡到 [新流](https://docs.microsoft.com/stream/streamnew/new-stream)的第一阶段，此方法将录制存储在 microsoft 365 中的 microsoft OneDrive 和 SharePoint 上并提供许多好处。

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

1. 安装 Skype For Business Online PowerShell 管理控制台。

    a. 下载 [Skype For Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide)。

    b. 按照提示进行安装。

    c. 重新启动计算机。

2. 以管理员身份启动 PowerShell

3. 导入 SkypeOnline 连接器并作为团队管理员登录。

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. 使用 [csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) 设置团队会议策略以从流存储切换到 ODSP。

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>选择退出 OneDrive for Business 和 SharePoint 以继续使用流

即使策略指示它已设置为 **流**，它也可能不会设置。 通常情况下，如果未设置策略，则默认设置为 " **流**"。 但是，如果你想要取消使用 SharePoint 或 OneDrive，请使用此新更改，然后必须将策略重置为 **流** ，以确保它是默认设置。

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a>常见问题解答

**会议录制将存储在何处？**

- 对于非频道会议，录制将存储在属于已启动会议录制 **的人员** 的 OneDrive 的最高级别的文件夹中。 上例

  <i>录像机的 OneDrive For business</i> /**录制**

- 对于频道会议，录制内容存储在名为 " **录制**" 的文件夹中的 "团队网站" 文档库中。 上例

  <i>团队名称-频道名称</i> /**文档** /**录制**

**如何处理以前员工的录制？**

由于视频与 OneDrive 和 SharePoint 中的任何其他文件一样，在员工离职后处理所有权和保留将遵循正常的 [OneDrive 和 sharepoint 进程]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)。

**哪些人具有查看会议录制的权限？**

- 对于非频道会议，除外部用户之外的所有会议被邀请者都将自动获取个人共享链接。 外部用户需要通过会议组织者或启动会议录制的人员显式添加到共享列表。

- 对于频道会议，权限继承自频道中的 "所有者" 和 "成员列表" 列表。

**如何管理脚本？**

选择加入此预览的客户将不会在其团队会议录制中提供已迁移到 OneDrive 和 SharePoint 的隐藏字幕。我们正在努力在2020年10月向会议录制添加字幕，以英文隐藏的字幕开始。

对于已选择加入以允许在[团队云录制](cloud-recording.md)中介绍的内容的客户，将在团队会议录制中提供隐藏式字幕

字幕有助于为所有功能的查看者创建包含内容。 作为所有者，你可以隐藏字幕，但除非你删除团队中的标题，否则仍可在团队中使用记录。 了解 [如何打开或关闭会议录制](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)

录制会议时，从录制会议的60天起，团队会议录制支持隐藏式字幕。

**我的存储配额将受到怎样的影响**

工作组会议录制文件实时在 OneDrive for business 和 SharePoint 中，并包含在这些服务的配额中。 请参阅 [SharePoint 配额](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) 和 [OneDrive for business 配额] (https://docs.microsoft.com/onedrive/set-default-storage-space) 。

**如何播放团队会议录制？**

你的视频将在 OneDrive for business 或 SharePoint 的视频播放器上播放，具体取决于你访问该文件的位置。

**如果你计划将会弃用添加到 Stream，现有视频是否保持原样和持续多长时间？**

作为平台的流在不久的将来不会被弃用。 在开始迁移之前，当前实时流中的视频将一直保留。 迁移后，这些视频也将迁移到 ODSP。 有关详细信息，请查看 [此处](https://docs.microsoft.com/stream/streamnew/classic-migration) 。
