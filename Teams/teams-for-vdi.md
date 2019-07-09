---
title: 适用于虚拟化桌面基础结构的 Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi
description: 了解如何在虚拟桌面基础结构 (VDI) 环境中运行 Microsoft 团队。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e88a5fb4e8522a94389e3bad24ddc3da8283a53
ms.sourcegitcommit: 2f12e0d4dc2ef8e848a63bf3a9c63e07e4439cf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35588140"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>适用于虚拟化桌面基础结构的 Teams

本文介绍在虚拟化环境中使用 Microsoft 团队的要求和限制。

## <a name="what-is-vdi"></a>什么是 VDI？

虚拟桌面基础结构 (VDI) 是在数据中心的集中式服务器上托管桌面操作系统和应用程序的虚拟化技术。 这使具有完全安全和合规的集中源的用户能够获得完全个性化的桌面体验。 
 
目前, 虚拟化环境中的团队可通过专用永久性虚拟机 (VM) 支持协作和聊天功能。 若要确保获得最佳的用户体验, 请按照本文中的指南操作。 

## <a name="teams-requirements"></a>团队要求

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a>设置策略以关闭团队中的呼叫和会议功能

团队通话和会议体验未针对 VDI 环境进行优化 (即将推出)。 我们建议你设置用户级策略以关闭团队中的呼叫和会议功能。

你仍然可以选择使用团队桌面应用或 web 应用在 VDI 中完全运行团队。 但是, 我们建议你设置策略以避免损害用户体验。  

需要花费一些时间 (几个小时) 才能传播策略更改。 如果你没有立即看到给定帐户的更改, 请在几个小时后重试。

> [!NOTE]
> 当团队通话和会议被优化为在虚拟桌面环境中使用时, 您可以还原这些策略, 并允许用户按正常方式使用团队。 

#### <a name="calling"></a>通话

使用**CSTeamsCallingPolicy** cmdlet 控制是否允许用户在私人聊天和群组聊天中使用呼叫和呼叫选项。 下面是策略设置和推荐值的列表。

|策略名称  |说明 |推荐值  |
|---------|---------|---------|
|AllowCalling    |控制互操作调用功能。 启用此功能将允许 Skype for Business 用户与团队用户进行一对一呼叫, 反之亦然。         |设置为 False 以阻止来自团队的 Skype for Business 用户的呼叫。          |
|AllowPrivateCalling     | 控制呼叫应用是否在团队客户端左侧的应用栏中可用, 以及用户是否在私人聊天中看到呼叫和视频通话选项         |设置为 False 可从团队左侧的应用栏中删除呼叫应用, 并删除私人聊天中的呼叫和视频通话选项。          |

#### <a name="create-and-assign-a-calling-policy"></a>创建和分配呼叫策略

1. 以管理员身份启动 Windows PowerShell 会话。
2. 连接到 Skype Online 连接器。

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. 查看通话策略选项列表。

       Get-CsTeamsCallingPolicy
 
4. 查找已禁用所有呼叫策略的内置策略选项。 其外观如下所示。
   
        Identity                        : Tag:DisallowCalling
        AllowCalling                    : False
        AllowPrivateCalling             : False
        AllowVoicemail                  : False
        AllowCallGroups                 : False
        AllowDelegation                 : False
        AllowUserControl                : False
        AllowCallForwardingToUser       : False
        AllowCallForwardingToPhone      : False
        PreventTollBypass               : False

5. 将 DisallowCalling 内置策略选项应用于将在虚拟化环境中使用团队的所有用户。

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

有关团队调用策略的详细信息, 请参阅[设置 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)。

#### <a name="meetings"></a>会议

使用**CsTeamsMeetingPolicy** cmdlet 控制用户可以创建的会议类型、会议期间可以访问的功能以及匿名用户和外部用户可用的会议功能。 下面是策略设置和推荐值的列表。

|策略名称 |说明|推荐值                   |
|-------------------|-----------------|-----------------------|
|AllowPrivateMeetingScheduling  | 确定是否允许用户安排私人会议。| 设置为 False 将禁止用户安排私人会议。  |
|AllowChannelMeetingScheduling  | 确定是否允许用户安排频道会议。 | 设置为 False 可禁止用户安排频道会议。                       |
|AllowMeetNow |确定是否允许用户创建或启动临时会议。              |  将此值设置为 False 可禁止用户启动临时会议。                     |
|ScreenSharingMode | 确定允许用户在通话或会议中共享其屏幕的模式。 | 设置为 "已禁用" 以禁止用户共享其屏幕                          |
|AllowIPVideo |确定是否在用户的会议或呼叫中启用视频。                  |    设置为 False 以禁止用户共享其视频                                         |
| AllowAnonymousUsersToDialOut | 确定是否允许匿名用户拨出到 PSTN 号码。 | 设置为 False 以禁止匿名用户拨出                                  |
| AllowAnonymousUsersToStartMeeting | 确定匿名用户是否可以启动会议。     |  设置为 False 以禁止用户启动会议                                            |
| AllowOutlookAddIn |确定用户是否可以在 Outlook 桌面客户端中安排团队会议。| 设置为 False 以禁止用户在 Outlook 桌面客户端中安排团队会议|
| AllowParticipantGiveRequestControl|确定参与者是否可以请求或提供屏幕共享的控制权。| 设置为 False 以禁止用户在会议中授予和请求控件    |
| AllowExternalParticipantGiveRequestControl | 确定外部参与者是否可以请求或提供屏幕共享的控制权。| 设置为 False 以禁止外部用户授予, 请求在会议中控制|
|AllowPowerPointSharing|确定用户的会议中是否允许 PowerPoint 共享。 |设置为 False 以禁止用户在会议中共享 PowerPoint 文件  |
|AllowWhiteboard | 确定用户的会议中是否允许白板。 |   设置为 False 以在会议中禁用白板 |
| AllowTranscription |确定用户的会议中是否允许实时和/或后期会议标题和转录。|    设置为 False 以禁止会议中的脚本和字幕  |  
| AllowSharedNotes | 确定是否允许用户接受共享笔记。 | 设置为 False 以禁止用户接受共享笔记 |
|MediaBitRateKB |确定会议中音频/视频/应用共享传输的媒体比特率  | 建议值为 5000 (5 MB)。 您可以根据组织的需要对其进行更改。| 

#### <a name="create-and-assign-a-meeting-policy"></a>创建和分配会议策略

1. 以管理员身份启动 Windows PowerShell 会话。
2. 连接到 Skype Online 连接器。

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. 查看会议策略选项列表。

       Get-CsTeamsMeetingPolicy
 
4. 查找已禁用所有会议策略的内置策略选项。 其外观如下所示。
   
        Identity                                    : Tag:AllOff
        Description                                 :
        AllowChannelMeetingScheduling               : False
        AllowMeetNow                                : False
        AllowIPVideo                                : False
        AllowAnonymousUsersToDialOut                : False
        AllowAnonymousUsersToStartMeeting           : False
        AllowPrivateMeetingScheduling               : False
        AutoAdmittedUsers                           : False
        AllowCloudRecording                         : False
        AllowOutlookAddIn                           : False
        AllowPowerPointSharing                      : False
        AllowParticipantGiveRequestControl          : False
        AllowExternalParticipantGiveRequestControl  : False
        AllowSharedNotes                            : False
        AllowWhiteboard                             : False
        AllowTranscription                          : False
        MediaBitRateKb                              : False
        ScreenSharingMode                           : False

5. 将 AllOff 内置策略选项应用于将在虚拟化环境中使用团队的所有用户。 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 有关团队会议策略的详细信息, 请参阅[设置 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。

### <a name="virtualization-provider-requirements"></a>虚拟化提供商要求

团队应用已在主流虚拟化解决方案提供商处验证。 有了多个市场提供商, 请咨询您的虚拟化解决方案提供商以确保满足最低要求。

### <a name="virtual-machine-requirements"></a>虚拟机要求

利用虚拟化环境中的各种工作负载和用户需求, 以下是推荐的最低 VM 配置。

|参数  |测度  |
|---------|---------|
|vCPU    |  2核       |
|RAM     |  4 GB      |
|Storage     | 8 GB       |

### <a name="virtual-machine-operating-system-requirements"></a>虚拟机操作系统要求

适用于 VM 的受支持的操作系统是:

- Windows 10 及更高版本
- Windows Server 2012 R2 及更高版本

## <a name="install-teams-on-vdi"></a>在 VDI 上安装团队

下面是部署团队桌面应用的过程和工具。 

1. 根据环境, 使用下列链接之一下载团队 MSI 程序包。 我们建议使用64位操作系统的 VDI VM 64 位版本。

    - [32位版本](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [64位版本](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. 运行以下命令, 将 MSI 安装到 VDI VM (或完成更新)。

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    这将把团队安装到程序文件。 此时, 将完成黄金图像设置。
 
    下一个交互式登录会话将启动团队并要求提供凭据。 请注意, 在 VDI 上使用 ALLUSER 属性安装团队时, 不可能禁用团队的自动启动。 

3. 运行以下命令以从 VDI VM 卸载 MSI (或准备更新它)。

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    这将从程序文件中卸载团队。

## <a name="known-issues-and-limitations"></a>已知问题和限制

以下是 VDI 上团队的已知问题和限制。

- **共享会话主机类型部署**: 共享会话主机类型部署 (例如, 共享非永久性 VM 配置) 不在作用域内。
- **通话和会议**:

    - 不会针对 VDI 优化通话和会议方案。 这些方案的性能将较差。 我们建议使用用户级策略, 如在团队部分中[关闭呼叫和会议功能的 "设置策略](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams)" 中所述。  
    - 应用本文中所述的策略会影响使用呼叫和会议功能的能力, 这取决于其他策略可能会影响组织中的其他用户。 如果你的组织中的用户使用非 VDI 客户端, 你可以选择不应用策略。  

- **加入由其他用户创建的呼叫和会议**: 虽然这些策略限制用户创建会议, 但如果其他用户通过会议拨出, 他们仍可以加入会议。 在这些会议中, 用户共享视频的能力, 使用白板和其他功能取决于是否使用 TeamsMeetingPolicy 禁用了这些功能。  
- **缓存的内容**: 如果运行团队的虚拟环境不是永久性的 (在每个用户会话结束时清除数据), 用户可能会因内容刷新而发现性能下降, 无论用户是否访问以前会话中的内容。
- **客户端更新**: vdi 上的团队不会像非 VDI 团队客户的那样自动更新。  你必须按照 "在[VDI 上安装团队](#install-teams-on-vdi)" 部分中的说明, 通过安装新 MSI 来更新 VM 映像。 必须卸载当前版本才能更新到较新版本。
- **用户体验**: VDI 环境中的团队用户体验可能与非 VDI 环境不同。 这些差异可能是由于环境中的策略设置和/或功能支持而造成的。

对于不与 VDI 无关的团队已知问题, 请参阅[Microsoft 团队的已知问题](Known-issues.md)。

## <a name="related-topics"></a>相关主题

- [使用 MSI 安装 Microsoft 团队](msi-deployment.md)
