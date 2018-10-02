---
title: 配置 live 事件中的 Microsoft 团队
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
description: 了解如何在 Microsoft 团队中，包括设置与会者可见性和录制选项配置 live 事件设置。
appliesto:
- Microsoft Teams
ms.openlocfilehash: fcd9bc02257d67f1af959d2158042ea73545a25e
ms.sourcegitcommit: 6447a3aa060452c8d6879524cd6a56aecf33b152
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2018
ms.locfileid: "25354353"
---
# <a name="configure-live-events-in-microsoft-teams"></a>配置 live 事件中的 Microsoft 团队
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

## <a name="set-up-event-support-link"></a>设置事件支持链接
这是将向 live 事件与会者显示的链接。 

在 Windows PowerShell 中，运行以下命令：
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
## <a name="configure-attendee-visibility-options"></a>配置 attendee 可见性选项
这将允许 live 事件组织者具有适当的与会者可见性创建事件。

|**值**  |**行为**  |
|---------|---------|
|所有人     |用户具有一个选项以创建具有以下 attendee 可见性 live 事件： 公共，公司和特定人员中的每个人。 |
|EveryoneInCompany     |用户具有一个选项以创建具有以下 attendee 可见性 live 事件： 公司和特定人员中的每个人。 用户无法创建可由匿名用户参加的实时事件。|
|InvitedUsers |用户只能创建 live 被限制为特定的某个人，如输入的事件管理器的事件。 用户不能与公共和公司身份验证中的每个人创建 live 事件。 |

使用 BroadcastAttendeeVisibility TeamsMeetingBroadcastPolicy 在 PowerShell 中设置来控制是否用户可以安排可以监视通过匿名与会者的广播的事件。 

除非您的自定义策略分配给用户，用户将获得全局策略，具有默认设置为 EveryoneInCompany。 
 
在 Windows PowerShell 中，运行以下内容以允许用户在全局策略中创建匿名事件：
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="configure-recording-options"></a>配置录制选项
> [!NOTE]
> 此选项才适用于使用快速入门生产方法的事件。

始终记录的实时事件，从不记录，还是事件组织者可以决定记录事件，这样，管理员控制。  

|**值**  |**行为**  |
|---------|---------|
|始终启用 |始终记录此用户组织的 live 事件。 用户不具有用于重写的选项。 如果记录的实时事件，事件团队成员能够下载录制后事件，并且与会者可以观看后的事件是通过的事件。 |
|AlwaysDisabled |永远不会记录此用户组织的 live 事件。 用户不具有用于重写的选项。 如果记录的实时事件，为事件团队成员，创建不录制并与会者无法观看结束后的事件。 |
|UserOverride |用户可以决定 live 事件记录，以便在录制文件可以创建为事件工作组成员，并且与会者可以观看后的事件是通过的事件。 |

使用录制选项创建的实时事件管理器的实时事件的控件设置*BroadcastRecordingMode* **TeamsMeetingBroadcastPolicy**在 PowerShell 中。

在 Windows PowerShell 中，运行以下 cmdlet 以更新全局策略中的记录模式：
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="configure-real-time-transcription-and-translation-in-teams-live-events-coming-soon"></a>配置实时转录和转换团队 live 事件 （即将推出）
> [!NOTE]
> 此选项才适用于使用快速入门生产方法的事件。

这将允许 live 事件组织者，以启用实时标题和转换为 live 事件与会者。 

使用中的设置*AllowBroadcastTranscription* **TeamsMeetingBroadcastPolicy**在 PowerShell 中控制是否 live 事件与会者都将能够看到转录和转换。 您可以了解有关在此处管理**TeamsMeetingBroadcastPolicy**与 Office 365 PowerShell 的详细信息。  

除非您的自定义策略分配给用户，用户将获得全局策略，具有转录和默认情况下禁用的转换。

在 Windows PowerShell 中，运行以下 cmdlet，以在全局策略中打开转录和上的事件与会者的转换：
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```
## <a name="administrative-tools"></a>管理工具 
虽然 Microsoft 直接控制所有 Office 365 Online 数据中心，并负责整体系统性能，但它可以控制仅结合为 Office 365 用户提供的总体体验的元素的一部分。 组织自己负责网络连接到数据中心，客户的广域网 (WAN) 和客户的局域网 (Lan)。 此外，它们是负责用户设备和其配置。边缘服务器还负责维护所需的授权每个用户的任何所需的功能，包括，但不是限于到，只要用户需要访问功能的管理这些功能的功能。

客户可以使用以下工具来管理的各种工作组 live 事件相关的任务。
- [Microsoft Office 365 管理中心](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_Office365admincenterl)
- [Microsoft 团队和 Skype 的业务 Online 管理中心](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_ExchangeAdministrationCenter)
- [Microsoft 流管理中心](https://stream.microsoft.com)
- [远程 Windows PowerShell](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_RemoteWindowsPowerShell)

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？
当谈到 Windows PowerShell，它的所有有关管理用户和用户允许或不允许执行的操作。 使用 Windows PowerShell，您可以管理 Office 365 和 Skype 业务 online 使用单点具有多个要执行的任务时，可以简化您的日常工作的管理。 若要开始使用 Windows PowerShell，请参阅下列主题：
 - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
 - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)

例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
 - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
 - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
 - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
