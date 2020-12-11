---
title: 使用 OneDrive for Business 和 SharePoint 录制会议
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中从 Stream 切换到 OneDrive for Business 和 SharePoint 会议录制存储。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea07079a94e2f76f8833e0854fd0161b4ff9ec09
ms.sourcegitcommit: 6b24c82837ca2c11f450a162ca4fab3dfa4ac8d4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620707"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>使用 OneDrive for Business 和 SharePoint 或 Stream 录制会议

> [!Note]
> 从使用 Microsoft Stream 更改为使用 OneDrive for Business 和 Microsoft SharePoint 录制会议是一种分阶段方法。

|<div style="width:290px">日期&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |事件&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|2020 年 10 月 5 日 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| 可以启用 Teams 会议策略，将会议录制保存到 OneDrive for Business 和 SharePoint，而不是将 Microsoft Stream (经典) |
|从 2021 年 1 月 7 日开始推出 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|所有新的 Teams 会议录制都将保存到 OneDrive for Business 和 SharePoint，除非你通过修改组织的 Teams 会议策略并显式将其设置为 Stream 来延迟此 **更改**。 将策略报告为流是不够的。 需要将策略值显式设置为 **Stream。**|
|从 2021 年 1 月 11 日开始推出 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**仅 GCC**<br> GCC 客户可以从 10 月 5 日起选择退出，但无法选择加入。 此功能将于 2021 年 1 月 11 日开始向所有 GCC 客户推出，除非你已选择退出。<br>  <br>从 2021 年 1 月 11 日开始，GCC 客户的所有新 Teams 会议录制都将保存到 OneDrive for Business 和 SharePoint，除非你通过修改组织的 Teams会议策略并显式将其设置为 Stream 来延迟此更改。 <br><br>如果你已选择退出，但已准备好启用此功能，则你可能需要将 Teams 会议策略显式设置为 **OneDrive for Business。** |
|从 2021 年 3 月 1 日推出 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**企业& GCC 客户**<br>无法将新的会议录制保存到 Microsoft Stream (经典) ;所有客户都会自动将会议录制保存到 OneDrive for Business 和 **SharePoint，** 即使他们将 Teams 会议策略更改为 Stream。<br><br> 我们建议客户在此日期之前推出此功能，以便他们可以控制发布时间。 |
|从 2021 年 7 月 7 日开始推出 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**教育客户**<br>无法将新的会议录制保存到 Microsoft Stream (经典) ;所有客户都会自动将会议录制保存到 OneDrive for Business 和 **SharePoint，** 即使他们将 Teams 会议策略更改为 Stream。<br><br> 我们建议客户在此日期之前推出此功能，以便他们可以控制发布时间。 我们已更新此计划，使教育客户能够完成进行中的课程。 |

> [!Note]
> 我们建议企业和教育客户，为了更好地控制组织的变化，每当适应更改时都选择加入，而不是等待更改发生。

Microsoft Teams 有一种保存会议录制的新方法。 作为从经典 Microsoft Stream 过渡到新 Stream[](https://docs.microsoft.com/stream/streamnew/new-stream)的第一阶段，此方法将录制存储在 Microsoft 365 中的 Microsoft OneDrive for Business 和 SharePoint 上，并提供许多优势。

使用 OneDrive for Business 和 SharePoint 存储录音的好处包括：

- Teams 会议录制的保留策略 (TMR)  (S+C E5 自动执行标签) 
- 从 OneDrive for Business 和 SharePoint 信息治理中获益
- 轻松设置权限和共享
- 与来宾共享 (外部用户) 仅显式共享
- 请求访问流
- 提供 OneDrive for Business 和 SharePoint 共享链接
- 增加配额
- 会议录制更快可用
- **转到本地** 租户支持
- 多地域支持 - 录制存储在特定于该用户的区域
- 自带密钥 (BYOK) 支持
- 改进了脚本质量和说话人归属

需要考虑一些限制：

- 将提供仅英语隐藏式字幕和脚本。
- 你将无法搜索脚本或其内容。
- 你将无法编辑脚本，但你可以关闭/打开字幕。
- 您可以控制共享录制内容的人，但无法阻止具有共享访问权限的人下载录制内容。
- 录制完成保存后，你将不会收到电子邮件，但录制完成后，录制内容将显示在会议聊天中。 发生此情况比之前在 Stream 中要快得多

有关详细信息，请观看"会议录制"。

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>为 OneDrive for Business 和 SharePoint 设置会议录制选项

会议录制选项是 Teams 策略级别的设置。 以下示例演示如何设置全局策略。 请确保为分配给用户的策略设置会议录制选项。

> [!Note]
> Teams 会议策略更改需要一段时间才能传播。 设置数小时后返回查看，然后注销并再次登录。

1. 安装 Skype for Business Online PowerShell。
**注意**：Skype for Business Online 连接器当前是最新 Teams PowerShell 模块的一部分。 如果你使用的是最新的 Teams PowerShell 公共版本，则无需安装 Skype for Business Online 连接器。 请参阅["使用 PowerShell 管理 Skype for Business Online"。](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)

    a. 下载[Skype for Business Online PowerShell。](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)

    b. 按照提示进行安装。

    c. 重启计算机。

2. 以管理员角色启动 PowerShell

3. 导入 SkypeOnline 连接器，然后以 Teams 管理员角色登录。

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

4. 使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) 设置 Teams 会议策略，以从流存储过渡到 OneDrive for Business 和 SharePoint。

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> 如果你的一些用户已分配了按组织者或按用户的策略，如果你希望他们同时将会议录制存储在 OneDrive for Business 和 SharePoint 中，则必须对此策略设置此设置。 有关详细信息，请参阅"[在 Teams 中管理会议策略"。](meeting-policies-in-teams.md)

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>选择退出 OneDrive for Business 和 SharePoint 以继续使用 Stream

即使策略指出已设置为 **Stream，** 也可能未设置。 通常，如果未设置策略，则默认设置为 **Stream。** 但是，通过此新更改，如果要选择退出使用 SharePoint 或 OneDrive for Business，则必须将策略重置为流式传输，以确保 **Stream** 是默认值。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>权限或基于角色的访问

> [!Note]
> 建议在共享 Teams 会议录制时，收件人需要是已登录的用户。 共享 **SharePoint (** 或) 中记录的文件时，请选择"组织人员 ["选项](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US)。 外部共享不是针对大型文件或大量文件的分发而设计的。 为了防止欺诈和滥用情况，与外部用户共享大量数据时可能会遇到问题。

|会议类型                               | 谁单击了"记录"？| 录制文件在哪里登陆？                               |谁有权访问？ R/W、R 或共享                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|与内部各方进行 1：1 通话             |呼叫者                 |调用方的 OneDrive for Business 帐户                        |调用方是所有者，并且拥有完全权限。 <br /><br />如果 (租户中，被呼叫) 具有只读访问权限。 无共享访问权限。 <br /><br /> 如果 (租户中，被呼叫者) 无法访问。 呼叫方必须共享给被叫方。|
|与内部各方进行 1：1 通话             |被叫方                 |被呼叫者 OneDrive for Business 帐户                        |被呼叫者是所有者，具有完全权限。 <br /><br />如果 (租户中具有只读访问权限，则调用方会进行调用。 无共享访问权限。 <br /><br />如果 (租户中，则调用方) 没有访问权限。 被调用方必须共享给呼叫方。|
|通过外部呼叫进行 1：1 通话             |呼叫者                 |调用方的 OneDrive for Business 帐户                        |调用方是所有者，并且拥有完全权限。<br /> <br />被呼叫者没有访问权限。 呼叫方必须共享给被叫方。|
|通过外部呼叫进行 1：1 通话             |被叫方                 |被呼叫者 OneDrive for Business 帐户                        |被呼叫者是所有者，具有完全权限。<br /><br />调用方没有访问权限。 被调用方必须共享给呼叫方。|
|群组通话                                 |通话的任何成员 |单击记录的 OneDrive for Business 帐户的成员  |单击"记录"的成员具有完全权限。 <br /><br /> 同一租户中的其他成员具有读取权限。 <br /><br /> 不同租户中的其他成员没有权限。|
|临时会议/已计划会议                    |组织者              |组织者的 OneDrive for Business 帐户                     |组织者对录制具有完全权限。 <br /><br /> 会议的其他所有成员都有读取访问权限。|
|临时会议/已计划会议                    |其他会议成员   |单击"记录"的成员                                  |单击"录制"的成员对录制具有完全权限。 <br /><br />组织者具有编辑权限，可以共享。<br /><br /> 所有其他成员都有读取访问权限。|
|与外部用户的临时/计划会议|组织者              |组织者的 OneDrive for Business 帐户                     |组织者对录制具有完全权限。<br /> <br /> 会议的其他所有成员（来自组织者的同一租户）具有读取访问权限。 <br /><br /> 所有其他外部成员没有访问权限，组织者必须将其共享给他们。|
|与外部用户的临时/计划会议|其他会议成员   |单击"记录"的成员                                  |单击"录制"的成员对录制具有完全权限。 组织者具有编辑权限，可以共享。 <br /><br /> 会议的其他所有成员（来自组织者的同一租户）具有读取访问权限。 <br /><br />所有其他外部成员没有访问权限，组织者必须将其共享给他们。|
|频道会议                            |频道成员         |该频道的 Teams SharePoint 位置                   |单击"录制"的成员对录制具有编辑权限。 <br /> <br />每个其他成员的权限基于频道 SharePoint 权限。|

## <a name="frequently-asked-questions"></a>常见问题解答

**会议录制内容将存储在何处？**

- 对于非频道会议，录制内容存储在 OneDrive for Business 顶层的名为 **"** 录制"的文件夹中，该文件夹属于开始会议录制的人。 示例：

  <i>录音机的 OneDrive for Business</i> /**录制**

- 对于频道会议，录制内容存储在 Teams 网站文档库中名为"录制" **的文件夹中**。 示例：

  <i>团队名称 - 频道名称</i> /**文档** /**录制**

**如何处理以前员工的录制？**

由于视频与 OneDrive for Business 和 SharePoint 中任何其他文件一样，因此处理员工离职后的所有权和保留期将遵循正常的 [OneDrive for Business]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)和 SharePoint 过程。

**谁有权查看会议录制内容？**

- 对于非频道会议，所有会议被邀请者（外部用户除外）将自动获得个人共享链接。 会议组织者或开始录制会议的人需要将外部用户显式添加到共享列表中。

- 对于频道会议，权限继承自频道中的所有者和成员列表。

**如何管理脚本？**

选择加入此预览版的客户不会在迁移到 OneDrive for Business 和 SharePoint 的 Teams 会议录制中提供隐藏式字幕。我们正在努力在 Q4 CY2020 中向会议录制添加字幕（从英语隐藏式字幕开始）。

对于已选择允许 Teams 云录制中所述的脚本的客户，Teams 会议录制中将提供隐藏 [式字幕](cloud-recording.md)。

字幕可帮助所有功能观看者创建包容性内容。 作为所有者，你可以隐藏字幕，尽管脚本在 Teams 上仍然可用，除非你从 Teams 中删除字幕。 了解如何 [打开或关闭会议录制](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)。

录制会议后 60 天内，Teams 会议录制支持隐藏式字幕。

如果将 Teams 会议录制内容从 OneDrive for Business 或 SharePoint 上的原始位置移动或复制，则不支持隐藏式字幕。

**我的存储配额受到怎样的影响？**

Teams 会议录制文件实时在 OneDrive for Business 和 SharePoint 中，并包含在这些服务的配额中。 请参阅 [SharePoint 配额](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) 和 [OneDrive for Business 配额](https://docs.microsoft.com/onedrive/set-default-storage-space)。

与 Stream 相比 [，使用 OneDrive for Business](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) 可获取更多存储空间，使用 SharePoint 可获取更多存储空间。

**如何播放 Teams 会议录制？**

视频将在 OneDrive for Business 或 SharePoint 的视频播放器上播放，具体取决于访问文件的位置。

**如果计划弃用添加到 Stream，现有视频是否将保持现有和持续多久？**

在不久的将来，不会弃用作为平台的流。 当前流中的视频将一直留在流中，直到我们开始迁移。 迁移后，这些视频也将迁移到 OneDrive for Business 或 SharePoint。 有关详细信息 [，请查看流式传输](https://docs.microsoft.com/stream/streamnew/classic-migration) 经典迁移。

**如何应用保留标签？**

请参阅 [如何自动应用保留标签](https://docs.microsoft.com/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings)。

**如何在 Microsoft Teams 中将策略分配给我的用户，哪些策略优先？**

查看[哪个策略优先？](https://docs.microsoft.com/MicrosoftTeams/assign-policies#which-policy-takes-precedence)
