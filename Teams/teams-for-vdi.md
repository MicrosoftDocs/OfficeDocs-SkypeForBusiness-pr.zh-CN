---
title: 虚拟桌面基础结构团队
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: 了解如何在虚拟化桌面基础结构 (VDI) 环境中运行的 Microsoft 团队。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c351e0cefc5e4de4ff74a175af4dee064bf96f3f
ms.sourcegitcommit: 946c77b847c1b2c5c43802ecfb0a918fa4f562d9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/15/2019
ms.locfileid: "31869827"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>虚拟桌面基础结构团队

本文介绍的要求和虚拟化环境中使用的 Microsoft 团队的限制。

## <a name="what-is-vdi"></a>什么是 VDI？

虚拟桌面基础结构 (VDI) 是承载桌面的操作系统和应用程序数据中心中的集中式服务器上的虚拟化技术。 这样完全个性化为具有完全安全和合规性的集中源的用户的桌面体验。 
 
目前，在虚拟化环境中的团队是用于使用专用的持久虚拟机 (VM) 与协作和聊天功能支持。 若要确保最佳用户体验，请按照本文中的指南。 

## <a name="teams-requirements"></a>团队要求

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a>设置策略，以关闭呼叫和会议团队中的功能

团队呼叫和会议体验不适合在 VDI 环境 （即将推出）。 我们建议您设置用户级别策略，以关闭呼叫和会议团队中的功能。

您可以仍选择运行团队完全 VDI 中使用的工作组桌面应用程序或 web 应用程序。 但是，我们建议您设置的策略，以避免会损害用户体验。  

传播策略更改可能需要一些时间 （几个小时）。 如果您没有立即看到给定帐户的更改，在几个小时后重试。

> [!NOTE]
> 当团队呼叫和会议最适合在虚拟桌面环境中使用时，可以还原这些策略和允许用户使用团队，他们通常的方式。 

#### <a name="calling"></a>通话

是否允许用户使用调用和专用中调用选项和组聊天，请使用控制**CSTeamsCallingPolicy** cmdlet。 下面是策略设置和建议的值的列表。

|策略名称  |说明 |建议的值  |
|---------|---------|---------|
|AllowCalling    |调用功能控件互操作。 打开允许 Skype 的业务用户来使一对一呼叫与团队用户，反之亦然。         |设置为 False，以防止 Skype 登录团队中的业务用户的呼叫。          |
|AllowPrivateCalling     | 控制是否在左侧的团队客户端应用程序栏中提供的电话应用程序和用户请参阅呼叫和视频呼叫私人聊天中的选项         |若要删除应用程序栏左侧的团队呼叫应用程序和私人聊天中删除电话和视频呼叫选项，则设置为 False。          |

#### <a name="create-and-assign-a-calling-policy"></a>创建和分配调用策略

1. 以管理员身份启动 Windows PowerShell 会话。
2. 连接到 Skype Online Connector。

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. 查看呼叫策略选项的列表。

       Get-CsTeamsCallingPolicy
 
4. 查找内置策略选项其中禁用所有呼叫的策略。 它如下所示。
   
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

5. 将使用团队虚拟化环境中的所有用户应用都于 DisallowCalling 内置策略选项。

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

有关团队调用策略的详细信息，请参阅[设置 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)。

#### <a name="meetings"></a>会议

使用**CsTeamsMeetingPolicy** cmdlet 来控制用户可以创建的会议、 其可以访问会议中的功能和供匿名用户和外部用户的会议功能的类型。 下面是策略设置和建议的值的列表。

|策略名称 |说明|建议的值                   |
|-------------------|-----------------|-----------------------|
|AllowPrivateMeetingScheduling  | 确定是否允许用户安排专用会议。| 设置为 False 以禁止用户能够安排专用会议。  |
|AllowChannelMeetingScheduling  | 确定是否允许用户安排通道会议。 | 设置为 False 以禁止用户能够安排通道会议。                       |
|AllowMeetNow |确定是否允许用户创建或启动临时会议。              |  将此参数设置为 False，以禁止用户启动临时会议。                     |
|ScreenSharingMode | 确定允许用户共享其屏幕呼叫或会议中的模式。 | 设置为 Disabled，以禁止用户共享其屏幕                          |
|AllowIPVideo |确定是否将视频启用中用户的会议或进行呼叫。                  |    设置为 False 以禁止用户共享其视频                                         |
| AllowAnonymousUsersToDialOut | 确定是否允许匿名用户拨到 PSTN 号码。 | 设置为 False 以禁止匿名用户外拨                                  |
| AllowAnonymousUsersToStartMeeting | 确定匿名用户是否可以开始会议。     |  设置为 False 以禁止用户启动会议                                            |
| AllowOutlookAddIn |确定用户是否可以安排 Outlook 桌面客户端中的团队会议。| 设置为 False 以禁止用户安排 Outlook 桌面客户端中的团队会议|
| AllowParticipantGiveRequestControl|确定参与者是否可以请求或授予的屏幕共享控制权。| 设置为 False 以禁止用户授予权限，并要求在会议中的控件    |
| AllowExternalParticipantGiveRequestControl | 确定外部参与者是否可以请求或授予的屏幕共享控制权。| 设置为 False 以禁止外部用户授予权限，请求在会议中的控件|
|AllowPowerPointSharing|确定是否在用户的会议中允许 PowerPoint 共享。 |设置为 False 以禁止用户共享在会议中的 PowerPoint 文件  |
|AllowWhiteboard | 确定是否在用户的会议中允许白板。 |   设置为 False 以禁止在会议中的白板 |
| AllowTranscription |确定是否在用户的会议中允许实时和/或后 meeting 标题和录音。|    设置为 False 以禁止转录和会议中的标题  |  
| AllowSharedNotes | 确定是否允许用户才能共享的便笺。 | 设置为 False 以禁止用户正在共享的便笺 |
|MediaBitRateKB |确定音频/视频/应用程序共享会议中的传输媒体比特率  | 建议的值为 5000 (5 MB)。 您可以更改它根据贵组织的需要。| 

#### <a name="create-and-assign-a-meeting-policy"></a>创建并分配的会议策略

1. 以管理员身份启动 Windows PowerShell 会话。
2. 连接到 Skype Online Connector。

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. 查看会议策略选项的列表。

       Get-CsTeamsMeetingPolicy
 
4. 查找内置策略选项其中禁用所有会议策略。 它如下所示。
   
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

5. 将使用团队虚拟化环境中的所有用户应用都于 AllOff 内置策略选项。 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 有关团队会议策略的详细信息，请参阅[设置 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。

### <a name="virtualization-provider-requirements"></a>虚拟化提供程序要求

已在前导虚拟化解决方案提供商验证团队应用程序。 多个市场提供程序，请参阅虚拟化解决方案提供商，以确保满足最低要求。

### <a name="virtual-machine-requirements"></a>虚拟机要求

使用不同的工作负荷和虚拟化环境中的用户需求，下面是 VM 配置的推荐最低值。

|参数  |度量值  |
|---------|---------|
|vCPU    |  2 个内核       |
|RAM     |  4 GB      |
|存储     | 8 GB       |

### <a name="virtual-machine-operating-system-requirements"></a>虚拟机操作系统要求

支持的操作系统的虚拟机是：

- Windows 10 及更高版本
- Windows Server 2012 R2 及更高版本

## <a name="install-teams-on-vdi"></a>在 VDI 上安装团队

下面是过程和工具，以部署团队桌面应用程序。 

1. 下载团队 MSI 程序包使用具体取决于环境的以下链接之一。 建议 VDI vm 与 64 位操作系统的 64 位版本。

    - [32 位版本](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [64 位版本](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. 运行以下命令以安装 VDI VM MSI （或完成更新它）。

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    此安装程序文件的团队。 此时，金色映像安装已完成。
 
    下一个交互式登录会话启动团队，并要求提供凭据。 请注意，不能使用 ALLUSER 属性 VDI 上安装团队时禁用自动启动的团队。 

3. 运行以下命令以卸载从 VDI 虚拟机的 MSI （或准备更新它）。

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    这将从 Program Files 卸载团队。

## <a name="known-issues-and-limitations"></a>已知的问题和限制

以下是已知问题和限制在 VDI 团队。

- **共享会话主机类型部署**： 范围内不共享会话主机类型部署 （例如，共享非持久 VM 配置）。
- **呼叫和会议**：

    - 呼叫和会议方案不为 VDI 进行优化。 这些方案将执行差。 我们建议使用用户级别策略，在[呼叫和会议团队中的功能设置策略，以关闭](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams)部分所述。  
    - 应用本文中所述的策略会影响使用呼叫和会议功能，具体取决于其他策略可能会影响您的组织中的其他用户的功能。 如果您的组织中的用户使用非 VDI 客户端，您可以选择不应用策略。  

- **加入呼叫和由其他用户创建的会议**： 虽然策略限制从创建会议的用户，他们仍可以加入会议如果另一个用户拨出到这些会议中。 在这些会议，用户可以共享视频，使用白板和其他功能取决于是否禁用使用 TeamsMeetingPolicy 这些功能。  
- **缓存内容**： 虚拟环境中哪些团队是否运行不持久 （和数据的每个用户会话末尾清理的方式），用户可能会注意到由于内容刷新，而不管用户是否访问相同的性能下降以前的会话中的内容。
- **客户端更新**： 上 VDI 团队不自动更新像 VDI 团队客户端的方式。  您必须通过[VDI 上安装的工作组](#install-teams-on-vdi)部分中所述安装新的 MSI 来更新虚拟机映像。 您必须先卸载要更新为新版本的当前版本。
- **用户体验**： 工作组在 VDI 环境中的用户体验可能不同于非 VDI 环境。 差异可能是因为策略设置和/或环境中的支持的功能。

对于团队已知未与 VDI 的问题，请参阅[已知问题的 Microsoft 团队](Known-issues.md)。

## <a name="related-topics"></a>相关主题

- [安装 Microsoft 团队使用 MSI](msi-deployment.md)