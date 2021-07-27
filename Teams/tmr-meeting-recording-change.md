---
title: 使用 OneDrive for Business 和 SharePoint Online 录制会议
author: cichur
ms.author: v-cichur
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何从流式传输切换到OneDrive for Business SharePoint联机会议录制存储Microsoft Teams。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: e00ccbf9ade9b1fae3dde64033fe82b502e2366b
ms.sourcegitcommit: 79d20fa2c45173d5a990551e79571caff06d7f82
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2021
ms.locfileid: "53486132"
---
# <a name="use-onedrive-for-business-and-sharepoint-online-or-stream-for-meeting-recordings"></a>使用 OneDrive for Business 和 SharePoint Online 或 Stream 进行会议录制

> [!Note]
> 从使用 Microsoft Stream 更改为OneDrive for Business和Microsoft Office SharePoint Online录制是分阶段的方法。

|<div style="width:290px">日期&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |事件&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |
|:--------------|:----------------------|
|2020 年 10 月 5 日<br> *(完成)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| 启用 Teams 会议策略，将会议录制保存到 OneDrive for Business SharePoint Online，而不是将 Microsoft Stream (经典) |
|从 2021 年 1 月 7 日开始推出<br> *(完成)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|所有Teams会议录制都将保存到 OneDrive for Business 和 SharePoint Online，除非你通过修改组织的 Teams 会议策略并显式将其设置为"流式传输"来延迟此 **更改。** 将策略报告视为流是不够的。 需要将策略值显式设置为"流 **式传输"。**|
|从 2021 年 1 月 11 日开始推出<br> *(完成)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC仅**<br> 虽然GCC客户可以从 10 月 5 日起选择退出，但无法选择加入。 此功能将于 2021 年 1 GCC 11 日开始向所有客户推出，除非已选择退出。<br>  <br>从 2021 年 1 月 11 日开始，GCC 客户的所有新 Teams 会议录制都将保存到 OneDrive for Business 和 SharePoint Online，除非你通过修改组织的 Teams 会议策略并显式将其设置为流式传输来延迟此 **更改。** <br><br>如果已选择退出，但已准备好启用此功能，则为此，可显式Teams会议策略以 **OneDrive for Business。** |
|从 2021 年 3 月 1 日推出<br> *(完成)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC-High 和 DoD**<br> 现在，客户可以首次在Microsoft Teams启用云会议录制。 默认情况下，这些录制内容将在 OneDrive 和 SharePoint Online 上存储和播放。 |
|从 2021 年 7 月 7 日开始推出<br> *(完成)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**所有客户 (Enterprise、教育GCC)**<br> 对于Teams录制到 OneDrive 和 SharePoint Online 并且也在会议期间实时转录的 Teams 会议，现可在 Microsoft 搜索 中搜索以根据脚本查找会议录制文件。 |
|从 2021 年 8 月 16 日逐步推出 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**所有客户 (Enterprise、教育GCC)**<br>无法将新的会议录制保存到经典 (Microsoft Stream) ;所有客户都会自动将会议录制保存到 OneDrive for Business SharePoint Online，即使他们将会议策略Teams流式传输。<br><br> 我们建议客户为了更好地控制组织的变化，每当你习惯更改时都选择加入，而不是等待更改发生。 |

Microsoft Teams有一种保存会议录制的新方法。 作为从经典 Microsoft Stream 过渡到新 Stream[](/stream/streamnew/new-stream)的第一阶段，此方法将录制存储在 Microsoft 365 中的 Microsoft OneDrive for Business 和 SharePoint Online 上，并提供许多优势。

 (，) 平台的流式传输不会在近期弃用。 流式传输经典 (中的) 将一直存在，直到将来可以使用迁移工具将它们移动到 OneDrive SharePoint Online。 有关 [未来计划的信息](/stream/streamnew/classic-migration) ，请查看流式传输经典迁移。

> [!NOTE]
> 如果Teams录制无法成功上载到 OneDrive/SharePoint Online，则录制内容将暂时保存到 AZURE 媒体服务 (AMS) 。 存储在 AMS 中后，不会尝试自动将录制内容上传到 OneDrive/SharePoint 流。

AMS 中存储的会议录制在自动删除前 21 天内可用。 如果需要保留副本，用户可以从 AMS 下载视频。

使用 OneDrive for Business 和 SharePoint Online 存储录制的好处包括：

- TMR Teams S+C E5 自动 (标签)  (会议录制的保留) 
- 受益于 OneDrive for Business SharePoint Online 信息治理
- 轻松设置权限和共享
- 与来宾共享录制 (外部用户) 显式共享
- 请求访问流
- 提供OneDrive for Business和SharePoint联机共享链接
- 会议录制更快可用
- 在会议中记录的搜索基础脚本
- **Go 本地** 租户支持
- 多地域支持 - 录制存储在特定于该用户的区域
- 自带密钥 (BYOK) 支持

查看当前可用的 [功能的完整列表以及随着时间的推移预期的功能](/stream/streamnew/features-new-version-stream)。

有关详细信息，请观看"Microsoft Teams录制的新增功能"。

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint-online"></a>为 OneDrive for Business 和 SharePoint Online 设置会议录制选项

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
   Connect-MicrosoftTeams
   ```

5. 使用[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)设置 Teams 会议策略，以从流存储转换为 OneDrive for Business SharePoint Online。

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> 如果你的一些用户已分配了按组织者或按用户的策略，如果你希望他们在 OneDrive for Business 和 SharePoint Online 中也存储会议录制，则必须对此策略设置此设置。 有关详细信息，请参阅在 Teams[中管理会议策略](meeting-policies-in-teams.md)。

## <a name="learn-more"></a>了解详细信息

若要详细了解如何Teams会议录制，请参阅Teams[录制云会议。](cloud-recording.md) 可以在该文章中详细了解如何记录设置、管理、监管、权限和存储。
