---
title: Microsoft Teams 会议室 (Windows) 发行说明
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: 管理员可以阅读Microsoft Teams 会议室的发行说明，其中列出了Microsoft Teams 会议室的累积改进。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 07b4661df5df7ac766c17a07c2bdd940b3d2cb6b
ms.sourcegitcommit: 2871c05e00458a0cc76d919ff822b0b354bd1f72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2022
ms.locfileid: "66810104"
---
# <a name="release-notes-for-microsoft-teams-rooms"></a>Microsoft Teams 会议室发行说明

本文介绍Microsoft Teams 会议室的累积改进。

Teams 会议室有两种类型的更新：Teams 会议室应用更新和 Teams Web 客户端。 

Teams 会议室应用更新通过 Microsoft Store 或[手动更新](manual-update.md)进行。 更新应用于在设备上本地安装的通用 Windows 平台 (UWP) 应用程序。

Teams Web 客户端更新通过 Teams Web 应用交付服务进行。 Teams Web 客户端是基于云的服务，不需要更新设备上安装的本地 UWP 应用程序。

有关 Teams 更新方式的详细信息，请参阅 [Teams 更新过程](../teams-client-update.md)

Teams 会议室受现代生命周期策略的约束。 有关详细信息，请参阅 [Teams 更新过程](../teams-client-update.md#servicing-agreement)。

## <a name="version-history"></a>版本历史记录

|释放 |发布到 <br/> Microsoft Store |
|--- |--- |
|4.12.139.0 |7/14/2022 |
|4.12.138.0 |5/26/2022 |
|4.12.126.0 |4/27/2022 |
|4.11.17.0 |3/3/2022 |
|4.11.12.0 |1/24/2022 |
|Teams Web-Client版本 | 2021 年 12 月 |
|Teams Web-Client版本 | 2021 年 10 月 |
|4.10.10.0 |10/1/2021 |
|4.9.12.0 |07/28/2021 |
|4.8.31.0 |05/12/2021 |
|4.8.25.0 |04/22/2021 |
|4.8.19.0 |04/06/2021 |
|4.7.19.0 |02/03/2021 |
|4.7.15.0 |12/11/2020 |
|4.6.23.0 |10/19/2020 |
|4.6.20.0 |09/30/2020 |
|4.5.37.0 |08/14/2020 |
|4.5.35.0 |07/23/2020 |
|4.4.63.0 |06/25/2020 |
|4.4.41.0 |05/06/2020 |
|4.4.25.0 |03/31/2020 |
|4.3.42.0 |03/02/2020 |
|4.3.33.0 |1/10/2020 |
|4.3.23.0 |12/13/2019 |
|4.2.4.0 |10/07/2019 |
|4.1.22.0 |08/15/2019 |
|4.0.105.0 |07/10/2019 |
|4.0.85.0 |04/08/2019 |
|4.0.78.0 |03/14/2019 |
|4.0.76.0 |03/04/2019 |
|4.0.64.0 |12/14/2018 |
|4.0.51.0 |11/17/2018 |
|4.0.31.0 |10/16/2018 |
|4.0.27.0 |10/1/2018 |
|4.0.19.0 |08/31/2018 |
|4.0.18.0 |08/27/2018 |
|4.0.8.0 |07/06/2018 |
|3.1.115.0|06/18/2018 |
|3.1.113.0|06/13/2018 |
|3.1.112.0|06/05/2018 |
|3.1.104.0|04/16/2018 |
|3.1.100.0|03/16/2018 |
|3.1.99.0 |3/14/2018 |
|3.1.98.0 |3/8/2018 |
|3.0.16.0 |11/27/2017 |
|3.0.15.0 |10/3/2017 |
|3.0.12.0 |9/1/2017 |
|3.0.8.0 |11/16/2017 |
|3.0.6.0 |11/16/2017 |
|2.0.2.0 |03/15/2017 |
|RTM (1.0.8)  |12/7/2016 |

## <a name="microsoft-teams-rooms-feature-introduction-and-issue-resolution"></a>Microsoft Teams 会议室功能简介和问题解决

### <a name="4121390-7142022"></a>4.12.139.0 (2022/7/14) 

在此更新中引入：

- 更改版本号以允许受 Windows [KB5013942](https://support.microsoft.com/topic/may-10-2022-kb5013942-os-builds-19042-1706-19043-1706-and-19044-1706-60b51119-85be-4a34-9e21-8954f6749504) 影响的系统重新注册应用，以便它可以启动。 此应用版本中没有 4.1.2.138.0 的功能更改。

> [!NOTE]
> 有关详细信息，请参阅Teams 会议室[和设备中的已知问题](/microsoftteams/troubleshoot/teams-rooms-and-devices/rooms-known-issues)中的“Teams 会议室应用更新后无法启动”。

### <a name="4121380-5262022"></a>4.12.138.0 (5/26/2022) 

在此更新中引入：
- 针对 Jabra Panacast 50 中的多个同时同步视频流的 Bug 修复 (会议视频、内容相机视频) 
- 跨云会议现在可以使用默认会议音频设备
- 质量和可靠性修复

### <a name="4121260-4272022"></a>4.12.126.0 (2022/4/27) 

在此更新中引入：
- IT 管理员可以通过 XML 设置注册 Teams 会议室设备以接收公共预览版功能。 注册后，设备将开始接收 beta 功能。 所有用于 beta 测试的功能都在 [Microsoft Teams 公共预览版中公布 - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview) <sup>1，2</sup>  
- IT 管理员可以通过 XML 设置<sup>2</sup> 设置会议室前显示分辨率和远程缩放
- IT 管理员可以通过 XML 设置<sup>3</sup> 禁用 Microsoft 干扰抑制 
- IT 管理员可以通过注册表项设置<sup>4</sup> 覆盖设备上的下载文件夹清理
- 使用户能够加入托管在另一个云 (上的 Teams 会议，即 GCCH 客户可以加入在商业云上托管的 Teams 会议，反之亦然)  
- Teams 会议室现在阻止从 PowerPoint Live 中的 URL 启动边缘浏览器，作为对具有触摸显示的 Teams 会议室的附加安全措施 
- 现已改善会议体验，为用户添加邀请用户到会议室的说明 
- 支持 teams 会议室Windows 10 21H2 功能版本   
- 主屏幕上的新 Cortana 入口点，返回“共享/显示”按钮 

> <sup>1</sup> 有关注册公共预览版 MTR Windows 设备的说明，请参阅 [此处](../public-preview-doc-updates.md#enable-public-preview)
> 
> <sup>2</sup> 会议室前显示分辨率和通过 XML 远程缩放可[在此](../rooms/xml-config-file.md#set-front-of-room-scale-and-resolution)处找到
>
> <sup>3</sup> 此时，仅发布管理员设置。 2022 年 5 月 4.12 版发布后，用户将控制和启用干扰抑制。 
>
> <sup>4</sup> 设备清理说明可[在此](../rooms/rooms-operations.md#collecting-logs-on-microsoft-teams-rooms)处找到
> 
> 
> [!NOTE]
> Windows 10 21H2 功能更新将在安装应用程序 7 天后更新，否则管理员可以改用手动更新来更快地安装。 Microsoft Teams 会议室应用程序版本 4.12 进行这些更改后，将于 2022 年 4 月开始推出，并在 2-3 周内完成推出。 应用程序更新通过 Windows 应用商店传送，应用程序会自动安装。 这仅在 Windows 上的Microsoft Teams 会议室上推出。 需要执行哪些操作来准备：可能需要通知用户有关此更新体验的信息，并根据需要更新培训和文档。

### <a name="411170-332022"></a>4.11.17.0 (2022/3/3) 

在此更新中引入：
- 相机框架的 Bug 修复将增强相机视图中的所有内容。

### <a name="411120-1242022"></a>4.11.12.0 (2022/1/24) 

在此更新中引入：
- Windows<sup>1</sup> 上 MTR 预览版)  (前行布局 
- 管理员设置，将前排布局设置为默认设置  
- 立即开会并仅调用 Teams 的应用更新，Teams 默认客户端模式<sup>为 1，2</sup>
- 在 Teams 会议<sup>1</sup> 中的多个摄像机之间切换 
- 默认视频相机设置 
- MTR 控制台上的 Cortana 推到谈话图标更新 
- 会议室标准版和高级 SKU 中包含 Azure AD Premium 1 许可证 
- AAD 条件访问策略支持<sup>3</sup> 
- 默认情况下在 OOBE 中启用了 Cortana 语音激活
- 远程 PTZ 控件支持<sup>4</sup>

> <sup>1</sup> 这些功能使用 Teams Web 客户端推出，并将在未来几周内完成推出。 有关 [Teams 更新](../teams-client-update.md) 的详细信息，请阅读详细信息。
> 
> Windows 上仅在 Microsoft Teams 或 Skype for Business 中运行的 <sup>2</sup> 个 Teams 会议室和 Microsoft Teams (默认) 使用新的会议和呼叫体验进行更新，但此更新不会影响其他模式。
> 
> <sup>3</sup> 请参阅有关为Teams 会议室设置 [AAD 条件访问策略的](../rooms/rooms-authentication.md#azure-ad-conditional-access)附加详细信息。
> 
> <sup>4</sup> 此功能要求 IT 管理员配置 Teams 桌面客户端远程 PTZ 控件应用。
> 

### <a name="teams-rooms-web-client-update-december-2021"></a>Teams 会议室 Web 客户端更新 (2021 年 12 月) 

在此更新中引入：
- 当内容未共享时，跨会议室的双正面显示拆分视频布局

### <a name="teams-rooms-web-client-update-october-2021"></a>Teams 会议室 Web 客户端更新 (2021 年 10 月) 

在此更新中引入：
- 使用 Teams 桌面客户端的统一名册控制，为演示者/与会者提供结构化会议分组、会议选项和控件、提高手排序顺序以及直接从名册邀请聊天或会议邀请的用户 
- 在会议呼叫控件、布局按钮和会议状态信息中，通用栏呼叫控件与桌面客户端对齐
- 对会议室显示的单面和双面显示器的动态库支持
- 统一布局选取器前厅布局选项合并
- 在 Teams 会议中聚焦或固定多个参与者
- 通过从名册中点击参与者可访问的演示者/与会者控制的大型会议支持
- 能够锁定会议室是组织者的会议，以及锁定会议的意识
- 当远程用户与演示者视图选项共享内容时，演示者模式 (气象员) 使用支持
- Teams 会议中的反应支持 

> [!NOTE]
> Web 客户端更新适用于应用程序版本 4.10 和 4.9 的所有Teams 会议室。 管理员将能够注册Teams 会议室公共预览版计划，以便很快获得 Web 客户端功能的潜移高峰。

### <a name="410100-1012021"></a>4.10.10.0 (2021/10/1) 

在此更新中引入：
- 使用会议室远程功能，用户可以在移动设备上使用 Teams 控制会议室的基本功能 *
- Logitech 将内容相机支持用于共享到会议中的 BLE 按钮
- 聊天气泡提供会议聊天中的通知，以提醒人们注意使用会议聊天所说的内容 *
- GCC High 中现已提供大型库和“在一起”模式支持
- 添加到 Cortana 的新技能、按名称将人员添加到会议和按名称呼叫 
- 默认情况下，所有设备上都会启用 Cortana Push to Talk。 若要了解详细信息，请参阅 [Teams 中的 Cortana 语音帮助](../cortana-in-teams.md)。

> [!NOTE]
> 已弃用 19H1 支持。 4.10 支持的最小 OS 版本为 19H2。

> [!NOTE]
> *这些功能使用 Teams 服务推出，适用于所有大于 4.9 的应用程序版本。

> [!NOTE]
> 若要从 Teams Mobile 应用和 MTR-W 加入计划的会议，请在 Teams 移动应用的名册中找到会议室帐户，然后按“控制此会议室”菜单，你可以从应用控制呼叫控件。

### <a name="49120-7282021"></a>4.9.12.0 (2021/7/28) 

在此更新中引入：
- 仅 Microsoft Teams 模式现在在应用程序设置中可用，因此无需再设置Skype for Business帐户。 在此模式下，以来宾用户身份登录到 Teams 的设备将以来宾用户身份加入Skype for Business会议。
- 修复了导致调用量降低的 HDMI 音频。 对于应用程序内部版本为 4.9.12.0 的所有设备，将自动启用 HDMI 音频功能。

> [!NOTE]
> 随着Skype for Business生命周期的结束，建议更新为仅限 Teams 模式。

### <a name="48310-05122021"></a>4.8.31.0 (2021/05/12) 

在此更新中引入：
- Windows 10 20H2 支持 

> [!NOTE]
> Crestron UC-Engine (包含“KYSKLi”的 BIOS 版本日期) Teams 会议室存在兼容性问题，系统 OEM 将在不久的将来提供更新的驱动程序。 Windows 10 20H2 不会提供给这些设备。 有关 Windows 版本支持的详细信息，请[参阅Windows 10版本支持](./rooms-lifecycle-support.md#windows-10-release-support)。

### <a name="48250-04222021"></a>4.8.25.0 (2021/04/22) 

在此更新中引入：
- 修复了以下问题：Teams 会议室控制台上的会议室信息未显示在全局地址列表中隐藏的会议室帐户 (GAL) 

> [!NOTE]
> GCCH 客户可以从[手动更新Microsoft Teams 会议室设备](manual-update.md)下载升级包

### <a name="48190-04062021"></a>4.8.19.0 (2021/04/06) 

在此更新中引入：
- 政府社区云高 (GCCH) 对Teams 会议室的支持。 具有现有Teams 会议室设备的 GCCH 客户可以从[手动更新Microsoft Teams 会议室设备](manual-update.md)下载版本 4.8.19.0
- 使用更好的视频质量加入 Zoom 会议 (720p 支持) 并接收参与者的视频库
- Skype for Business针对 Teams 默认模式删除的登录失败横幅。 此更改支持删除Skype for Business基础结构的组织
- Teams 会议加入链接分析现在处理 Microsoft Defender 高级威胁防护安全链接，以允许无缝加入外部 Teams
- 修复了共享者电脑在 Windows 中设置了自定义 DPI 时Skype for Business会议中的共享内容缩放问题
- 质量和可靠性修复

### <a name="47190-02032021"></a>4.7.19.0 (02/03/2021) 

在此更新中引入：
- 质量和可靠性修复

### <a name="47150-12112020"></a>4.7.15.0 (2020/12/11) 

在此更新中引入：

- 在 Teams 会议中向会议参与者共享 HDMI 音频
- Cortana 语音技能 (预览版) 
- 当Teams 会议室以与会者身份加入时，请防止基于音频权限取消调用。 有关详细信息，请参阅 [Teams 会议中的“管理与会者音频权](https://support.microsoft.com/office/manage-attendee-audio-permissions-in-teams-meetings-f9db15e1-f46f-46da-95c6-34f9f39e671a)限”。
- 从 Teams 会议室控制台聚焦某人的视频，并在会议室显示屏上使用聚焦视频

> [!NOTE]
> Cortana 语音技能可用于选择位于美国中的租户的音频外围设备。 将来将添加其他国家或地区。 有关详细信息，请参阅 [Teams 中的 Cortana 语音帮助](../cortana-in-teams.md)

### <a name="46230-10192020"></a>4.6.23.0 (2020/10/19) 

在此更新中引入：

- 修复了在 Teams 会议中调用屏幕键盘时的白色半屏

### <a name="46200-09302020"></a>4.6.20.0 (2020/09/30) 

在此更新中引入：

- 在会议室显示器前查看包含 3x3 视频库的更多视频  
- 从 MTR 开始本地实时隐藏字幕
- 通过直接来宾加入Teams 会议室加入 Zoom 会议 (预览版) 

> [!NOTE]
> 3x3 视频库和本地实时隐藏字幕通过 Microsoft Teams 服务提供。 这些功能适用于应用程序版本为 4.5.37.0 及更高版本的所有Teams 会议室设备。

### <a name="45370-08142020"></a>4.5.37.0 (2020/08/14) 

在此更新中引入：

- Microsoft Teams 与 Surface Hub 2S 之间的协调会议
- 修复了安装 [Windows 10 更新 KB4565351](https://support.microsoft.com/help/4565351/windows-10-update-kb4565351) 或 [Windows 10 更新 KB4571709](https://support.microsoft.com/help/4571709/windows-10-update-kb4571709) 时 Skype For Business 登录失败的问题

### <a name="45350-07232020"></a>4.5.35.0 (2020/07/23) 

在此更新中引入：

- 通过直接来宾加入从Teams 会议室加入 Cisco Webex 会议
- Teams 管理员中心启用和自动注册
- Windows 10 1909 版本支持
- 即使存在内容，也可切换到视频库布局
- 虚拟举手支持与会者和演示者控制
- 会议和默认扬声器的可调整默认音量设置
- 从 Teams 会议室搜索和调用联合用户 (租户) 

> [!IMPORTANT]
> 版本 4.5 是支持 Windows 10 版本 1803 的最后一个版本;未来版本将不会提供给 Windows 10 版本 1803 上的系统。 有关 Windows 版本支持的详细信息，请[参阅Windows 10版本支持](./rooms-lifecycle-support.md#windows-10-release-support)。

### <a name="44630-06252020"></a>4.4.63.0 (2020/06/25) 

在此更新中引入：

- 质量和可靠性修复
- 修复了“应用程序在更新到 4.4.41.0 后不会启动”问题

> [!NOTE]
> 如果设备未自动更新到版本 4.4.63.0，请按照Microsoft Teams 会议室应用程序在[更新到版本 4.4.41.0 后不启动](https://support.microsoft.com/help/4565998/teams-rooms-application-does-not-start-after-update)的步骤来解决问题。

### <a name="44410-05062020"></a>4.4.41.0 (2020/05/06) 

在此更新中引入：

- 应用程序的可靠性修复从 Windows 10 展台开始

### <a name="44250-03312020"></a>4.4.25.0 (2020/31) 

在此更新中引入：

- 对 Exchange 和Skype for Business的新式身份验证支持
- 支持使用 Teams 客户端通道对 Teams (服务组件进行动态紧急呼叫) 
- 使用 XML 为双显示会议室禁用会议外重复内容的功能
- 应用程序初始屏幕
- 开源软件 (OSS) 设备设置中的通知

### <a name="43420-03022020"></a>4.3.42.0 (2020/03/02) 

在此更新中引入：

- “适用于企业的 Windows 更新”的策略更新
- 修复了在 Azure Monitor 中显示错误的设备事件报告

### <a name="43330-1102020"></a>4.3.33.0 (2020/10) 

在此更新中引入：

- 某些配置中出现的窗口调整大小/闪烁问题的修复
- 删除了第三方会议的日历处理
- 已删除 Cortana 状态设置

### <a name="43230-12132019"></a>4.3.23.0 (2019/12/13) 

在此更新中引入：

- 自动应答基于邻近的调用和管理设置来控制此问题
- 设备管理员设置 UI 刷新，在“关于”选项卡下添加设备配置
- 房间控件回到主屏幕
- GCC 中提供的会议室 SKU
- 基于Surface Pro系统的内容相机支持 (所需的最低应用版本：4.2.4.0) 

### <a name="4240-10072019"></a>4.2.4.0 (2019/07) 

在此更新中引入：

- Windows 10 1903 支持。 Windows 10应用更新后几天内提供 1903 更新
- 屏幕键盘未可靠显示的修补程序

### <a name="41220-08152019"></a>4.1.22.0 (2019/08/15) 

在此更新中引入：

- 一种新的内容相机功能，使用户能够智能地将传统白板包含到 Teams 会议中
- 对控制台 UI 进行其他改进，以减少混乱，并将“设置”移动到通过主机上的更多内容访问的新侧栏中
- 如果本地内容电缆未连接或内容相机未连接，则禁用共享托盘按钮
- 修复了触摸键盘的问题，即仅在 MTR 系统重启后第一次出现该键盘失败
- 质量和可靠性修复

### <a name="401050-07102019"></a>4.0.105.0 (2019/07/10) 

在此更新中引入：

- Skype 会议室系统应用商店应用品牌更名为“Microsoft Teams 会议室”
- Microsoft Teams 会议室控制台用户界面重新调整到 Microsoft Teams
- 主题更新：仅在会议室显示器前保留自定义背景图像，同时使控制台背景成为中性颜色，以确保控制台 UI 控件满足颜色对比度 - 辅助功能要求
- 适用于 Teams 呼叫/会议的会议内呼叫控件的通用栏，可提供与 Microsoft Teams 电脑/Web/移动客户<sup>端 1</sup> 的一致体验
- Teams 呼叫/会议<sup>1</sup> 后的通话质量反馈评级
- 从电脑/Web/移动 Teams 客户端<sup>1</sup> <sup>2</sup> 共享时，在会议室显示Microsoft Teams 会议室前接收/呈现 Microsoft Whiteboard
- 由于Microsoft Teams 会议室客户端的兼容性问题，删除了对版本 1809 升级Windows 10支持。 Windows 10版本 19H1 支持将在将来的版本中添加

<sup>1</sup> 使用 Teams 环的 Microsoft Teams 服务推出。 此功能可能早于或晚于 4.0.105.0 客户端更新

<sup>2</sup> 需要 IT 管理员启用 Microsoft Whiteboard。 此外，如果在会议室显示屏前启用了触摸，则必须使用 Windows 设置和设备管理员登录来校准多个触摸显示器，以便开始使用 Microsoft Whiteboard 从共享到 Teams 会议的会议室显示器进行协作

### <a name="40850-0482019"></a>4.0.85.0 (2019/04/8) 

在此更新中引入：

- 修复了“提供反馈”功能的问题
- 为即将Microsoft Teams 会议室设备升级到 Windows 10 版本 1809 做准备的优化

### <a name="40780-03142019"></a>4.0.78.0 (2019/03/14) 

在此更新中引入：

- 修复了影响旧版 Windows 10 RS2 内部版本的设备的“在应用启动时挂起”bug。

### <a name="40760-03042019"></a>4.0.76.0 (2019/03/04) 

在此更新中引入：

- 用于 Microsoft Teams P2P 会议和 PSTN 调用的 DTMF 键盘。 若要使 Microsoft Teams 成为默认呼叫客户端，管理员必须将 IsTeamsDefaultClient 设置为 true
- 将远程参与者的传入视频固定到会议室显示屏前的全屏。 在控制台上使用参与者名册中的“Pin”命令
- 通过添加会议室前通知来改进大厅通知
- 当未在Microsoft Teams 会议室设备上启用蓝牙信标时，会议室前显示强制转换图标已删除
- 解决 Teams 会议中的批量控制问题

### <a name="40640-12142018"></a>4.0.64.0 (2018/12/14) 

在此更新中引入：

- 在两个屏幕会议室系统上显示会议室前 (FoR) 上显示的内容
- 会议室主题和会议室前用户界面改进
- TLS 1.2 客户端支持。 对于本地客户，为Microsoft Teams 会议室启用通过 TLS 1.2 进行通信需要Skype for Business Server 2015 累积更新 9 (CU9) 或 Skype for Business Server 2019 累积更新 1 (CU1) 。

### <a name="40510-11172018"></a>4.0.51.0 (2018/11/17) 

在此更新中引入：

- 双显示 (会议室前) 支持 Teams 会议

### <a name="40310-10162018"></a>4.0.31.0 (2018/10/16) 

在此更新中引入：

- 质量和可靠性修复

### <a name="40270-1012018"></a>4.0.27.0 (2018/10/1) 

在此更新中引入：

- 为以后Windows 10版本 1803 升级准备Microsoft Teams 会议室应用所需的代码更改
- 修复了本地化 EULA 的格式设置问题 (特别是挪威) 防止超越 EULA OOBE 设置窗口
- 在旧版 Lync 会议室系统上运行Microsoft Teams 会议室应用程序所需的代码更改。 请参阅 [此处](./lrs-migration.md)的详细信息。

### <a name="40190-8312018"></a>4.0.19.0 (2018/8/31) 

在此更新中引入：

- Crestron 应用程序的修补程序无法启动，当按下 Crestron SR 设备上的应用按钮时，通常可以访问该修补程序。 Microsoft Teams 会议室安装 4.0.19.0 后需要重新启动应用。

### <a name="40180-08272018"></a>4.0.18.0 (2018/08/27) 

在此更新中引入：

- Teams 模式中的“报告问题”功能改进 (等效于Skype for Business模式下的“提供反馈) 
- 为 SIP 调用启用从 Teams 回退到Skype for Business模式的功能
-  (讲述人、放大镜) 的辅助功能改进
- 应用 XML 预配更改后，在需要时自动重启应用
- 其他修补程序

### <a name="4080-07062018"></a>4.0.8.0 (07/06/2018) 

在此更新中引入：

- 此更新在会议室系统设备上支持Skype for Business *和* Teams 会议。 应用更新后，团队默认处于关闭状态。 管理员可以在设备设置中或通过远程 xml 推送在本地启用 Teams。

### <a name="311150-06182018"></a>3.1.115.0 (2018/06/18) 

在此更新中引入：

- 修复了如何解决在应用启动期间在某些系统上观察到的错误。

### <a name="311130-06132018"></a>3.1.113.0 (2018/06/13) 

在此更新中引入：

- 使 Microsoft 能够更灵活地管理 Windows 更新的更改。
- 对最终用户体验没有更改。

### <a name="311120-06052018"></a>3.1.112.0 (2018/06/05) 

在此更新中引入：

- 修复了在连接到两个会议室前显示器和视频引入的基于 2017 Surface Pro设备上观察到的控制台响应问题
- 自动检查以确保系统正在运行最新的预配脚本

### <a name="311040-04162018"></a>3.1.104.0 (2018/04/16) 

在此更新中引入：

- 修复了改进基于 Windows 10 版本 1709 的系统中的屏幕键盘 () 行为的 OSK
- 为将来的操作系统更新做准备的改进

### <a name="311000-03162018"></a>3.1.100.0 (2018/03/16) 

在此更新中引入：

- 应用程序已更新以改进遥测

### <a name="31990-03142018"></a>3.1.99.0 (2018/03/14) 

在此更新中引入：

- 修复了可能发生间歇性会议加入问题的问题
- 修复了已知导致设备“挂起”体验的问题

### <a name="31980-382018"></a>3.1.98.0 (3/8/2018) 

在此更新中引入：

- 用于提高稳定性的 Bug/故障修复
- 支持变量大小的控制台
- 外围音频处理卸载 (其他媒体允许列表) 
- 使 IT 专业人员能够使用 Windows 10版本 1709 1 月更新和更高版本生成自行执行的映像的优化。

### <a name="30160-11272017"></a>3.0.16.0 (2017/11/27) 

在此更新中引入：

- 修复了“提供反馈”功能的问题。

### <a name="30150-1032017"></a>3.0.15.0 (2017/3/3) 

在此更新中引入：

- 支持 [Polycom MSR 系列](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl) 停靠硬件
- 对 [Logitech Brio](https://www.logitech.com/product/brio) 的支持
- 解决了显示 (控制台和会议室前) 在会议室中没有活动时无法进入睡眠模式的问题

### <a name="30120-912017"></a>3.0.12.0 (2017/9/1) 

在此更新中引入：

- 在 Surface Pro (2017) 平板电脑上运行
- 支持Windows 10 企业版创意者更新 (英语，生成 1703) 
- 支持 [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system) 停靠硬件
-  (Crestron) 的环境控制 OEM 支持

自 Microsoft Teams 会议室 版本 3.0.12.0 (更新 3) 起，64 位版本的Windows 10 企业版周年版 (英语版本 1607) 不再受支持。

### <a name="3080-842017"></a>3.0.8.0 (2017/8/4) 

在此更新中引入：

- 解决通过参与者搜索字段搜索联合用户时观察到的问题。 在此修复之前，外部联合用户的搜索结果可能未正确解析，而是返回了错误的结果。

### <a name="3060-772017"></a>3.0.6.0 (2017/7/7) 

在此更新中引入：

- Dual-Screen支持旧版系统奇偶校验 () 
- 主题 (内置主题以及设置自定义主题) 
- 为公共生成提供反馈的能力
- 改进了有关会议联接可靠性的遥测
- 改进了 OMS 报告
- IT 管理员远程配置设备的能力

### <a name="2020-03152017"></a>2.0.2.0 (2017/03/15) 

在此更新中引入：

- 会议室音频和视频 USB 设备的应用内用户选择
- 使用 Microsoft Operations Management Suite（现为 Azure Monitor）的客户的集成会议室控制台状态报告

### <a name="release-to-market-1272016"></a>发布到市场 (2016/12/7) 

**功能 (的) ：**

 **为 Skype for Business 而构建**

- 一键式加入 Skype 会议
- Skype 会议体验已针对具有屏幕填充高清视频和高清宽带音频的会议室进行了优化
- 所有参与者均可使用所选设备从任意位置连接到 Skype 会议
- 从目录中（在此可立即看到用户的状态）或通过电话呼叫邀请用户
- 支持 Skype for Business PSTN 会议和 PSTN 呼叫，以替代会议室中的单独会议电话

 **转换任何会议室**

- 专用的 Skype 会议应用针对桌面中心触摸式控制器和会议室前方的大型显示屏进行了优化
- 在会议室显示器或投影仪前重复使用现有投资
- 适用于各种类型的会议室，从小型到大型会议室
- 经认证的 Skype for Business 音频和视频设备可用于各种规模的会议室
- 内置有线引入项目桌面共享到会议室和Skype 会议

 **易于部署、便于管理**

- 在检测到会议室中的人员时自动唤醒显示器的 Always-on 设备
- UWP（通用 Windows 平台）Skype 会议应用的部署和更新都非常简单
- Windows AppLocker 可将设备锁定至 Skype 会议应用
- 通过 Intune 和 Configuration Manager (MDM) 作为Windows 10 企业版设备进行监视和管理
- 企业级可靠性
- 由于最终用户很熟悉 Skype 用户界面，因此只需进行少量培训
- 在 Surface Pro 4 平板电脑上运行

<a name="See"> </a>
## <a name="see-also"></a>另请参阅

[Microsoft Teams 会议室帮助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[准备环境](rooms-prep.md)

[支持Microsoft Teams 会议室 Current Branch 版本](rooms-lifecycle-support.md)

[已知问题](known-issues.md)

[Microsoft Teams 会议室规划](rooms-plan.md)

[管理 Microsoft Teams 会议室](rooms-manage.md)
