---
title: 在虚拟环境中运行的 Microsoft 团队
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/28/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jaym
description: 了解如何在虚拟化环境中运行的 Microsoft 团队。
localization_priority: Normal
ms.custom:
- Devices
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 47c920d46e37364782ac656b93398deb01c41e6d
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23256270"
---
<a name="run-microsoft-teams-in-a-virtual-environment"></a>在虚拟环境中运行的 Microsoft 团队
============================================

本文介绍虚拟化环境中使用团队的要求和限制。

某些对安全问题及合规性问题特别敏感的组织使用虚拟桌面基础结构 (Virtual Desktop Infrastructure, VDI) 环境。 用户执行虚拟桌面包含所有其桌面应用程序和使用远程桌面服务或类似的远程连接的文件上的工作。 由于没有优化虚拟桌面上的团队访问或 （不带其他软件） 的用户的本地设备上使用的音频或视频设备，在 VDI 环境中工作将通常具有与呼叫，如多媒体方案相关的挑战视频呼叫、 屏幕共享、 应用程序共享、 共同创作和详细信息。 

> [!NOTE]
> 组织可以选择运行团队完全 vdi （使用的 Web 应用程序或桌面客户端），但建议以下策略已关闭，使用户不必虚拟化环境中都不好的体验。 请注意，可能需要一些时间，这些策略更改将传播。 如果您没有立即看到给定帐户的更改，几个小时后重试。 

## <a name="calling"></a>通话

*CsTeamsCallingPolicy* cmdlet 启用管理员控制是否调用，并在专用呼叫选项和群聊或未启用。 


|策略名称 |说明  |推荐的值  |
|---------|---------|---------|
|AllowPrivateCalling   |控制呼叫应用程序是否为左滑轨团队客户端中可用。 此外将控制用户是否可以看到私人聊天中的电话和视频呼叫选项。 |此设置为**False**以删除左滑轨调用应用程序并删除私人聊天中的电话和视频呼叫选项。 |

### <a name="powershell-instructions"></a>PowerShell 说明

1.  以管理员身份启动 PowerShell。
2.  连接到 Skype 联机连接器：<br>
\>> *# 设置 Office 365 用户名和密码*<br>
\>> *$username ="管理电子邮件地址"*<br>
\>> *$password = ConvertTo SecureString"密码"-AsPlainText-Force*<br>
\>> *$LiveCred = 新对象 typename System.Management.Automation.PSCredential-参数列表 $username，$password*<br><br>
\>> *# 连接到 Skype Online*<br>
\>> *导入模块 SkypeOnlineConnector*<br>
\>> *$sfboSession = 新建 CsOnlineSession-凭据 $LiveCred*<br>
\>> *导入 PSSession $sfboSession*<br>
3.  查看的调用策略选项的列表：<br>
\>> *Get CsTeamsCallingPolicy*
4.  查找其中禁用所有呼叫策略前 canned 选项：<br>
![与禁用的所有会议策略的会议选项的屏幕截图。](media/virtual-environment-image2.png)
5.  适用于所有用户都将使用团队虚拟化环境中的"DisallowCalling"前 canned 的策略选项：<br>
\>> *授予 CsTeamsCallingPolicy PolicyName DisallowCalling-Identity"用户电子邮件 id"*

## <a name="meetings"></a>会议

*CsTeamsMeetingPolicy* cmdlet 使管理员能够控制用户可以创建的会议或他们可以访问会议中的功能的类型。 它还有助于确定会议如何处理匿名或外部用户。

|策略名称 |说明  |推荐的值  |
|---------|---------|---------|
|AllowPrivateMeetingScheduling    |确定是否将允许用户安排专用会议。         |此设置为**False**以禁止用户能够安排专用会议。         |
|AllowChannelMeetingScheduling     |确定是否将允许用户安排通道会议。         |此设置为**False**以禁止用户能够安排通道会议。         |
|AllowMeetNow     |确定是否将允许用户创建或启动临时会议。         |此设置为**False**以禁止用户启动临时会议。         |
|ScreenSharingMode     |确定在将允许用户共享屏幕呼叫或会议中的模式。         |此设置为**已禁用**以禁止用户共享其屏幕。         |
|AllowIPVideo     |确定是否将视频启用中用户的会议或进行呼叫。         |此设置为**False**以禁止用户共享其视频。         |
|AllowAnonymousUsersToDialOut     |确定是否允许匿名用户拨到 PSTN 号码。         |此设置为**False**可禁止匿名用户拨出。         |
|AllowAnonymousUsersToStartMeeting     |确定是否匿名用户可以启动会议。         |此设置为**False**可禁止他们发起会议。         |
|AllowOutlookAddIn     |确定用户是否可以安排 Outlook 桌面客户端中的团队会议。         |此设置为**False**以禁止用户安排 Outlook 客户端中的团队会议。         |
|AllowParticipantGiveRequestControl     |确定参与者是否可以请求或授予的屏幕共享控制权。         |将此设置为**False**可禁止用户授予权限，请求在会议中的控件。         |
|AllowExternalParticipantGiveRequestControl     |确定外部参与者是否可以请求或授予的屏幕共享控制权。         |将此设置为**False**可禁止外部用户授予权限，请求在会议中的控件。         |
|AllowPowerPointSharing     |确定是否在用户的会议中允许 PowerPoint 共享。         |此设置为**True**以允许。<br>此设置为**False**以禁止用户共享在会议中的 PowerPoint 文件。         |
|AllowWhiteboard     |确定是否在用户的会议中允许白板。         |此设置为**False**可禁止在会议中的白板应用程序。         |
|AllowTranscription     |确定是否在用户的会议中允许实时和/或后 meeting 标题和录音。         |此设置为**False**可禁止转录和字幕会议中。         |

### <a name="powershell-instructions"></a>PowerShell 说明

1.  以管理员身份启动 PowerShell。
2.  连接到 Skype 联机连接器：<br>
\>> *# 设置 Office 365 用户名和密码*<br>
\>> *$username ="管理电子邮件地址"*<br>
\>> *$password = ConvertTo SecureString"密码"-AsPlainText-Force*<br>
\>> *$LiveCred = 新对象 typename System.Management.Automation.PSCredential-参数列表 $username，$password*<br><br>
\>> *# 连接到 Skype Online*<br>
\>> *导入模块 SkypeOnlineConnector*<br>
\>> *$sfboSession = 新建 CsOnlineSession-凭据 $LiveCred*<br>
\>> *导入 PSSession $sfboSession*
3.  查看的会议策略选项的列表：<br>
\>> *Get CsTeamsMeetingPolicy*
4.  查找其中禁用所有会议策略前 canned 选项：<br>
![调用不带禁用的所有会议策略选项的屏幕截图。](media/virtual-environment-image1.png)
5.  适用于所有用户都将使用团队虚拟化环境中的"AllOff"前 canned 的策略选项：<br>
\>> *授予 CsTeamsMeetingPolicy PolicyName AllOff-Identity"用户电子邮件 id"*

##<a name="known-limitations"></a>已知限制

除了提到音频和视频限制因此，有一些上虚拟化环境的用户可能面临的附加限制：

- **加入由其他人创建的会议。** 即使上述策略限制从创建会议的用户，他们仍然能够加入由其他用户发送的会议。 这些会议中共享视频，其能够使用白板和其他功能将取决于是否管理员是否已禁用它们。

- **缓存内容相关的问题。** 如果虚拟环境中运行团队不持续存在 （数据清理的每个用户会话结束时），用户可能会注意到由于无需重新所有内容再次都下载，无论是否在客户端的性能下降给定的用户在以前的会话中访问相同的内容。 可以使用漫游缓存解决方案，例如所提供的 FSLogix 缓解这种性能影响。

一旦团队优化虚拟桌面环境中使用了，管理员可以还原这些策略和允许用户使用团队，他们通常的方式。

         
        
        
        
        
        
        
        
        
        
        


