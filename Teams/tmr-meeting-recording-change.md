---
title: 使用 OneDrive for Business 和 SharePoint Online 进行会议录制
author: cichur
ms.author: v-cichur
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中从 Stream 切换到 OneDrive for Business 和 SharePoint 会议录制存储。
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c53cc427c1db87a2d0296384d5d0c67e7e7996a
ms.sourcegitcommit: d34dbdc2f71f3d024cb7f1856fc0f8bbc701f66d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2021
ms.locfileid: "53506321"
---
# <a name="use-onedrive-for-business-and-sharepoint-online-or-stream-for-meeting-recordings"></a>使用 OneDrive for Business 和 SharePoint Online 或 Stream 进行会议录制

> [!Note]
> 将会议录制从 Microsoft Stream 改为 OneDrive for Business 和 Microsoft SharePoint Online 将是一项分阶段方法。

|<div style="width:290px">日期&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |事件&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |
|:--------------|:----------------------|
|2020 年 10 月 5 日<br> *（完成）* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| 启用 Teams 会议策略，将会议录制保存到 OneDrive for Business和 SharePoint Online，而不是 Microsoft Stream（经典）|
|从 2021 年 1 月 7 日开始推出<br> *（完成）* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|所有新的 Teams 会议录制都将保存到 OneDrive for Business 和 SharePoint Online，除非通过修改组织的 Teams 会议策略并将其显式设置为 **Stream** 来延迟此更改。 将策略报告视为 Stream 是不够的。 需要将策略值显式设置为 **Stream**。|
|从 2021 年 1 月 11 日开始推出<br> *（完成）* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**仅限 GCC**<br> 虽然 GCC 客户可以选择从 10 月 5 日开始退出，但你无法选择加入。 此功能将从 2021 年 1 月 11 日起向所有 GCC 客户推出，除非你已选择退出。<br>  <br>从 2021 年 1 月 11 日开始，GCC 客户的所有新 Teams 会议录制都将保存到 OneDrive for Business 和 SharePoint Online，除非通过修改组织的 Teams 会议策略并将其显式设置为 **Stream** 来延迟此更改。 <br><br>如果已选择退出，但已准备好启用此功能，则可以通过将 Teams 会议策略显式设置为 **OneDrive for Business** 来执行此操作。 |
|从 2021 年 3 月 1 日开始推出<br> *（完成）*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**仅限 GCC-High 和 DoD**<br> 现在，客户可以首次在其 Microsoft Teams 中启用云会议录制。 默认情况下，这些录制将在 OneDrive 和 SharePoint Online 上存储和播放。 |
|从 2021 年 7 月 7 日开始推出<br> *（完成）*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**所有客户（企业版、教育版和 GCC）**<br> 对于录制到 OneDrive 和 SharePoint Online 并在会议期间进行实时转录的 Teams 会议，现在可以在 Microsoft 搜索中搜索，以根据转录查找会议录制文件。 |
|从 2021 年 8 月 16 日开始以增量方式推出 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**所有客户（企业版、教育版和 GCC）**<br>无法将新的会议录制保存到 Microsoft Stream（经典）；所有客户都会自动将会议录制保存到 OneDrive for Business 和 SharePoint Online，即使他们已将其 Teams 会议策略更改为 Stream 也是如此。<br><br> 为了更好地控制组织中的更改，建议客户在对更改感到满意时选择加入，而不是等待更改发生。 |

Microsoft Teams 推出了一种保存会议记录的新方法。 在从经典 Microsoft Stream 过渡到[新版 Stream](/stream/streamnew/new-stream) 的第一阶段，此方法会将录制内容存储在 Microsoft 365 中的 Microsoft OneDrive for Business 和 SharePoint Online 中，并提供诸多好处。

作为平台的 Stream（经典）在不久的将来不会被弃用。 当前在 Stream（经典）中运行的视频将一直保留在那里，直到将来的迁移工具将它们移动到 OneDrive 和 SharePoint Online。 有关未来计划的详细信息，请查看 [Stream 经典迁移](/stream/streamnew/classic-migration)。

> [!NOTE]
> 如果 Teams 会议录制未能成功上传到 OneDrive/SharePoint Online，则录制内容将暂时保存到 Azure 媒体服务 (AMS)。 存储在 AMS 中后，无需重试即可自动将录制内容上传到 OneDrive/SharePoint Online 或 Stream。

存储在 AMS 中的会议录制文件在自动删除之前可使用 21 天。 如果用户需要保留副本，则可以从 AMS 下载视频。

使用 OneDrive for Business 和 SharePoint Online 存储录制内容的好处包括：

- Teams 会议录制 (TMR) 的保留策略（S+C E5 自动保留标签）
- 受益于 OneDrive for Business和 SharePoint Online 信息治理
- 易于设置权限和共享
- 仅通过显式共享与来宾（外部用户）共享录制内容
- 请求访问流
- 提供 OneDrive for Business 和 SharePoint Online 共享链接
- 可更快地获得会议录制
- 搜索在会议中录制的基础转录
- **转到本地** 租户支持
- 多地理位置支持 – 录制内容存储在特定于该用户的区域中
- 创建自己的密钥 (BYOK) 支持

查看[当前可用的功能以及随时间推移预期推出的功能](/stream/streamnew/features-new-version-stream)完整列表。

有关详细信息，请观看“Microsoft Teams 会议录制的新增功能”。

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint-online"></a>为 OneDrive for Business 和 SharePoint Online 设置会议录制选项

会议录制选项是 Teams 策略级别的设置。 以下示例说明了如何设置全局策略。 确保为分配给用户的策略设置会议录制选项。

> [!Note]
> Teams 会议策略更改需要一段时间才能传播。 设置几小时后再次检查，然后注销并再次登录到 Teams 桌面应用，或者只需重启计算机即可。

1. 安装 Teams PowerShell PowerShell。

   > [!NOTE]
   > Skype for Business Online 连接器目前是最新 Teams PowerShell 模块的一部分。 如果使用的是最新 Teams PowerShell 公共版本，则无需安装 Skype for Business Online 连接器。 请参阅[使用 PowerShell 管理 Skype for Business Online](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?preserve-view=true&view=o365-worldwide)。

2. 以管理员身份启动 PowerShell。

3. 安装 [Teams PowerShell 模块](./teams-powershell-install.md)。

4. 导入 MicrosoftTeams 模块并以 Teams 管理员身份登录。

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

5. 使用 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) 设置 Teams 会议策略，以便从 Stream 存储过渡到 OneDrive for Business 和 SharePoint Online。

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> 如果某些用户分配有按组织者或按用户策略，并且你希望他们也将会议录制存储在 OneDrive for Business 和 SharePoint Online 中，则必须在此策略上设置此设置。 若要了解详细信息，请参阅[管理 Teams 中的会议策略](meeting-policies-in-teams.md)。

## <a name="learn-more"></a>了解详细信息

若要了解有关 Teams 云会议录制的更多信息，请参阅 [Teams 云会议录制](cloud-recording.md)。 在该文章中，可以了解有关录制设置、管理、治理、权限和存储的更多信息。
