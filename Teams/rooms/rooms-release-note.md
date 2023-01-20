---
title: Microsoft Teams 会议室 (Windows) 的发行说明
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
- Teams_ITAdmin_Rooms
description: 管理员可以阅读Microsoft Teams 会议室的发行说明，其中列出了Microsoft Teams 会议室中的累积改进。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5e6a0c85453d1613a5d3841a8511feea487937d7
ms.sourcegitcommit: 776820a6c927fafabdfad9f50654fe7648d77bf3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2023
ms.locfileid: "69845899"
---
# <a name="release-notes-for-microsoft-teams-rooms"></a>Microsoft Teams 会议室发行说明

本文讨论Microsoft Teams 会议室中的累积改进。

Teams 会议室有两种类型的更新：Teams 会议室应用更新和 Teams Web 客户端。

Teams 会议室应用更新通过 Microsoft Store 或[手动更新](manual-update.md)进行。 汇报将应用于设备上本地安装的 通用 Windows 平台 (UWP) 应用程序。

Teams Web 客户端更新通过 Teams Web 应用交付服务进行。 Teams Web 客户端是基于云的服务，不需要更新设备上安装的本地 UWP 应用程序。

有关 Teams 更新方式的详细信息，请参阅 [Teams 更新过程](../teams-client-update.md)

Teams 会议室受新式生命周期策略的约束。 有关详细信息，请参阅 [Teams 更新过程](../teams-client-update.md#servicing-agreement)。

## <a name="version-history"></a>版本历史记录

|释放 |发布到 <br/> Microsoft Store |
|--- |--- |
|4.15.58.0 | 1/10/2023 |
|4.14.24.0 |9/2/2022 |
|4.13.132.0 |8/2/2022 |
|4.12.139.0 |7/14/2022 |
|4.12.138.0 |5/26/2022 |
|4.12.126.0 |4/27/2022 |
|4.11.17.0 |3/3/2022 |
|4.11.12.0 |1/24/2022 |
|Teams Web 客户端版本 | 2021 年 12 月 |
|Teams Web 客户端版本 | 2021 年 10 月 |
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

## <a name="microsoft-teams-rooms-feature-introduction-and-issue-resolution"></a>Microsoft Teams 会议室功能介绍和问题解决

### <a name="415580-1102023"></a>4.15.58.0 (2023/1/10) 

此更新中引入：

- 会议内通知改进
- 库、大型库和一起模式 <sup>1</sup> 中的会议聊天
- 在 Teams 会议中启动白板
- 适合帧的会议室视频名单控制
- 溢出会议支持
- 通过直接来宾加入按 ID 加入缩放会议。 此版本中添加了对按 ID 加入 Zoom 会议的支持，并将在未来几周内启用。
- 第三方会议的质量修复 (直接来宾加入) 
- 修复了 Teams 未登录时显示无许可证的设置中的许可证信息
- 新的默认壁纸 (生动的标志) 和其他四个新壁纸

<sup>1</sup> 可在[使用 XML 配置文件远程管理Microsoft Teams 会议室控制台设置](xml-config-file.md)中找到用于通过 XML 从所有会议布局隐藏会议聊天的管理员配置。

### <a name="414240-922022"></a>4.14.24.0 (2022/9/2) 

此更新中引入：

- 前行布局体验更新
- 固定和隐藏会议室视频
- 用于在双显示Teams 会议室 <sup>1</sup> 中关闭拆分库的管理员配置
- 双显示Teams 会议室现在最多可以显示 18 个参与者视频流
- 支持Microsoft Teams 会议室专业版和 Microsoft Teams 会议室基本会议室许可证

<sup>1</sup> 有关通过 XML 关闭拆分库的管理员配置，请参阅[使用 XML 配置文件远程管理Microsoft Teams 会议室控制台设置](../rooms/xml-config-file.md)。

### <a name="4131320-822022"></a>4.13.132.0 (2022/8/2) 

此更新中引入：

- 使用会议 ID 加入 Teams 会议
- 一对一 Teams 的端到端加密调用<sup>1</sup> 
- Teams 会议<sup>2</sup> 中的噪音抑制
- 共享托盘体验更新
- 会议室视频的静音和取消静音状态
- 仅内容布局默认设置管理员  
- 新式身份验证默认处于打开状态

 <sup>1</sup> 在对来自Teams 会议室设备的呼叫启用端到端加密之前，需要为设备的用户帐户配置策略。 可以从 Teams 管理中心或使用 Teams PowerShell 更新用户策略。 有关详细信息，请参阅 [配置 Teams 会议室用户帐户的策略。](../teams-end-to-end-encryption.md)

 <sup>2</sup> Teams 会议室在版本 4.12 中添加了对具有管理员替代的噪音抑制的支持。

> [!IMPORTANT]
> 在此更新中，新的Teams 会议室设备现在默认在连接到 Microsoft Teams 和Exchange Online时使用新式身份验证。
>
> 强烈建议在 8 月底之前通过为其会议室帐户启用新式身份验证来测试Teams 会议室设备。
>
> 此更改有助于为 Exchange Online 中即将推出的更新做好准备，以从 2022 年 10 月 1 日起关闭基本身份验证。 有关详细信息，请参阅 [Exchange Online 中的基本身份验证弃用 – 2022 年 5 月更新 ](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-authentication-deprecation-in-exchange-online-may-2022/ba-p/3301866)。  

### <a name="4121390-7142022"></a>4.12.139.0 (2022/7/14) 

此更新中引入：

- 更改版本号以允许受 Windows [KB5013942](https://support.microsoft.com/topic/may-10-2022-kb5013942-os-builds-19042-1706-19043-1706-and-19044-1706-60b51119-85be-4a34-9e21-8954f6749504) 影响的系统重新注册应用，以便它可以启动。 从 4.1.2.138.0 起，此应用版本中没有功能更改。

> [!NOTE]
> 有关详细信息，请参阅Teams 会议室[和设备中的已知问题](/microsoftteams/troubleshoot/teams-rooms-and-devices/rooms-known-issues)中的“Teams 会议室应用在更新后无法启动”。

### <a name="4121380-5262022"></a>4.12.138.0 (2022/5/26) 

此更新中引入：
- 修复了来自 Jabra Panacast 50 (会议视频、内容相机视频) 的多个同时视频流的 bug
- 跨云会议现在可以使用默认会议音频设备
- 质量和可靠性修复

### <a name="4121260-4272022"></a>4.12.126.0 (2022/4/27) 

此更新中引入：
- IT 管理员可以注册 Teams 会议室设备，以通过 XML 设置接收公共预览功能。 注册后，设备将开始接收 beta 版功能。 Microsoft [Teams 公共预览版 -Microsoft Tech Community](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview) <sup>1，2</sup> 中宣布了进入 beta 测试的所有功能  
- IT 管理员可以通过 XML 设置<sup>2</sup> 远程设置会议室前显示分辨率和缩放
- IT 管理员可以通过 XML 设置<sup>3</sup> 禁用 Microsoft 噪音抑制 
- IT 管理员可以通过注册表项设置<sup>4</sup> 替代设备上的下载文件夹清理
- 让用户加入托管在另一个云 (上的 Teams 会议，即 GCCH 客户可以加入在商业云上托管的 Teams 会议，反之亦然)  
- Teams 会议室现在阻止从PowerPoint Live中的 URL 启动边缘浏览器，这是使用触摸显示器的 Teams 会议室的附加安全措施 
- 现在开会体验已得到改进，可向用户添加邀请用户加入聊天室的说明 
- 支持 Teams 会议室的 Windows 10 21H2 功能版本   
- 主屏幕上的新 Cortana 入口点，“共享/演示”按钮已返回 

> <sup>1</sup> 可[在此处](../public-preview-doc-updates.md#enable-public-preview)找到注册公共预览版 MTR Windows 设备的说明
> 
> <sup>2</sup> 可[在此处](../rooms/xml-config-file.md#set-front-of-room-scale-and-resolution)找到会议室前显示分辨率和通过 XML 进行远程缩放
>
> <sup>3</sup> 目前，仅发布管理员设置。 用户控制和启用噪音抑制将在 2022 年 5 月发布 4.12 后发布。 
>
> <sup>4</sup> 可[在此处](../rooms/rooms-operations.md#collecting-logs-on-microsoft-teams-rooms)找到设备清理说明
> 
> 
> [!NOTE]
> Windows 10 21H2 功能更新将在安装应用程序 7 天后更新，或者管理员可以使用手动更新来更快地安装。 具有这些更改的Microsoft Teams 会议室应用程序版本 4.12 将于 2022 年 4 月开始推出，并在 2-3 周内完成推出。 应用程序更新通过 Windows 应用商店提供，应用程序会自动安装。 仅在 Windows 上的 Microsoft Teams 会议室 上推出此功能。 准备所需执行的操作：你可能希望通知用户有关此更新体验的信息，并根据需要更新培训和文档。

### <a name="411170-332022"></a>4.11.17.0 (2022/3/3) 

此更新中引入：
- 相机框架的 Bug 修复，这将增强相机视图中的所有内容。

### <a name="411120-1242022"></a>4.11.12.0 (2022/1/24) 

此更新中引入：
- Windows<sup>1</sup> 上 MTR 的前行布局 (预览版)  
- 管理员设置，将“前行布局”设置为默认值  
- 立即开会并调用仅适用于 Teams 的应用更新，Teams 默认客户端模式<sup>1，2</sup>
- 在 Teams 会议<sup>1</sup> 中切换多个摄像机 
- 默认摄像机设置 
- MTR 主机上的 Cortana 推送通话图标更新 
- 会议室标准和高级 SKU 中包含的 Azure AD Premium 1 许可证 
- AAD 条件访问策略支持<sup>3</sup> 
- OOBE 中默认启用 Cortana 语音激活
- 远程 PTZ 控件支持<sup>4</sup>

> <sup>1</sup> 这些功能将使用 Teams Web 客户端推出，并将在未来几周内完成推出。 有关详细信息，请阅读有关 [Teams 更新](../teams-client-update.md) 的详细信息。
> 
> Windows 上的 <sup>2</sup> 个 Teams 会议室仅在 Microsoft Teams 中运行或Skype for Business，Microsoft Teams (默认) 使用新的会议和通话体验进行更新，但其他模式不受此更新的影响。
> 
> <sup>3</sup> 请参阅有关为Teams 会议室设置 [AAD 条件访问](../rooms/rooms-authentication.md#azure-ad-conditional-access)策略的附加详细信息。
> 
> <sup>4</sup> 此功能要求 IT 管理员配置 Teams 桌面客户端远程 PTZ 控制应用。
> 

### <a name="teams-rooms-web-client-update-december-2021"></a>Teams 会议室 Web 客户端更新 (2021 年 12 月) 

此更新中引入：
- 当内容未共享时，跨会议室的双前显示拆分视频布局

### <a name="teams-rooms-web-client-update-october-2021"></a>Teams 会议室 Web 客户端更新 (2021 年 10 月) 

此更新中引入：
- 使用 Teams 桌面客户端进行统一的名单控制，其中包含结构化会议分组、会议选项和演示者/与会者的控制，提高手动排序顺序，并能够直接从名单邀请用户从聊天或会议邀请 
- 通用条形呼叫控件与会议呼叫控件、布局按钮和会议状态信息中的桌面客户端对齐
- 对房间单前部和双正面显示器的动态库支持
- 合并了会议室布局选项前面的统一布局选取器
- 聚焦或固定 Teams 会议中的多个参与者
- 大型会议支持，演示者/与会者控件可通过从名单中点击参与者进行访问
- 能够锁定会议室是组织者的会议的会议，以及对锁定的会议的认识
- 当远程用户与演示者视图选项共享内容时，演示者模式 (气象员) 使用支持
- Teams 会议中的反应支持 

> [!NOTE]
> Web 客户端更新适用于应用程序版本 4.10 和 4.9 的所有Teams 会议室。 管理员将能够注册Teams 会议室公共预览版计划，以便很快获得 Web 客户端功能的预演高峰。

### <a name="410100-1012021"></a>4.10.10.0 (2021/10/1) 

此更新中引入：
- 会议室远程允许用户在其移动设备上使用 Teams 控制聊天室的基本功能 *
- Logitech scribe 内容相机支持用于共享到会议的 BLE 按钮
- 聊天气泡在会议聊天中提供通知，以使用会议聊天来引起人们对所讲内容的关注 *
- GCC High 中现已提供大型库和一起模式支持
- 添加到 Cortana 的新技能、按姓名向会议添加人员以及按姓名呼叫 
- 默认情况下，在所有设备上启用 Cortana Push to Talk。 若要了解详细信息，请参阅 [Teams 中的 Cortana 语音帮助](../cortana-in-teams.md)。

> [!NOTE]
> 已弃用的 19H1 支持。 4.10 支持的最小 OS 版本为 19H2。

> [!NOTE]
> *这些功能是使用 Teams 服务推出的，适用于大于 4.9 的所有应用程序版本。

> [!NOTE]
> 若要从 Teams 移动应用和 MTR-W 加入已安排的会议，请在 Teams 移动应用的名册中查找会议室帐户，然后按“控制此会议室”菜单，你可以从应用控制呼叫控制。

### <a name="49120-7282021"></a>4.9.12.0 (2021/7/28) 

此更新中引入：
- 仅 Microsoft Teams 模式现在可在应用程序设置中使用，因此无需再设置Skype for Business帐户。 在此模式下，登录到 Teams 仅模式的设备以来宾用户身份加入Skype for Business会议。
- 修复了导致呼叫音量降低的 HDMI 音频问题。 对于具有应用程序版本 4.9.12.0 的所有设备，将自动启用 HDMI 音频功能。

> [!NOTE]
> 随着Skype for Business生命周期即将结束，建议更新到仅 Teams 模式。

### <a name="48310-05122021"></a>4.8.31.0 (2021/05/12) 

此更新中引入：
- Windows 10 20H2 支持 

> [!NOTE]
> Crestron UC-Engine (包含“KYSKLi”的 BIOS 版本日期) Teams 会议室存在兼容性问题，系统 OEM 将在近期内提供更新的驱动程序。 Windows 10 20H2 不会提供给这些设备。 有关 Windows 版本支持的详细信息，请参阅[Windows 10版本支持](./rooms-lifecycle-support.md#windows-10-release-support)。

### <a name="48250-04222021"></a>4.8.25.0 (2021/04/22) 

此更新中引入：
- 修复了以下问题：Teams 会议室控制台上的会议室信息对于从全局地址列表 (GAL) 隐藏的房间帐户不显示

> [!NOTE]
> GCCH 客户可以从[手动更新Microsoft Teams 会议室设备下载升级](manual-update.md)包

### <a name="48190-04062021"></a>4.8.19.0 (2021/04/06) 

此更新中引入：
- 政府社区云高 (GCCH) Teams 会议室支持。 具有现有Teams 会议室设备的 GCCH 客户可以从[手动更新Microsoft Teams 会议室设备](manual-update.md)下载版本 4.8.19.0
- 加入具有更好视频质量的 Zoom 会议 (720p 支持) 并接收参与者的视频库
- Skype for Business Teams 默认模式删除了登录失败横幅。 此更改支持组织删除Skype for Business基础结构
- Teams 会议加入链接分析现在处理Microsoft Defender高级威胁防护安全链接，允许无缝加入外部 Teams
- 修复了当共享者电脑在 Windows 中设置了自定义 DPI 时，Skype for Business会议中的共享内容缩放问题
- 质量和可靠性修复

### <a name="47190-02032021"></a>4.7.19.0 (2021/02/03) 

此更新中引入：
- 质量和可靠性修复

### <a name="47150-12112020"></a>4.7.15.0 (2020/12/11) 

此更新中引入：

- 在 Teams 会议中将 HDMI 音频共享给会议参与者
- Cortana 语音技能 (预览) 
- 当Teams 会议室以与会者身份加入时，根据音频权限防止取消静音。 有关详细信息，请参阅 [在 Teams 会议中管理与会者音频权限](https://support.microsoft.com/office/manage-attendee-audio-permissions-in-teams-meetings-f9db15e1-f46f-46da-95c6-34f9f39e671a)。
- 从 Teams 会议室控制台聚焦某人的视频，并在会议室显示器上使用聚焦视频

> [!NOTE]
> Cortana 语音技能适用于位于 美国 中的租户的所选音频外围设备。 将来将添加更多国家或地区。 有关详细信息，请参阅 [Teams 中的 Cortana 语音帮助](../cortana-in-teams.md)

### <a name="46230-10192020"></a>4.6.23.0 (2020/10/19) 

此更新中引入：

- 修复了在 Teams 会议中调用屏幕键盘时的白半屏问题

### <a name="46200-09302020"></a>4.6.20.0 (2020/09/30) 

此更新中引入：

- 在会议室显示器正面查看具有 3x3 视频库的更多视频  
- 从地铁启动本地实时隐藏式字幕
- 使用直接来宾加入 (预览) 从Teams 会议室加入 Zoom 会议

> [!NOTE]
> 3x3 视频库和本地实时隐藏式字幕通过 Microsoft Teams 服务提供。 具有应用程序版本 4.5.37.0 及更高版本的所有Teams 会议室设备都可使用这些功能。

### <a name="45370-08142020"></a>4.5.37.0 (2020/08/14) 

此更新中引入：

- Microsoft Teams 与 Surface Hub 2S 之间的协调会议
- 修复了安装[Windows 10更新 KB4565351](https://support.microsoft.com/help/4565351/windows-10-update-kb4565351) 或[Windows 10更新 KB4571709](https://support.microsoft.com/help/4571709/windows-10-update-kb4571709) 时 Skype For Business 登录失败的问题

### <a name="45350-07232020"></a>4.5.35.0 (2020/07/23) 

此更新中引入：

- 使用直接来宾加入从Teams 会议室加入 Cisco Webex 会议
- Teams 管理员中心启用和自动注册
- Windows 10 1909 版本支持
- 即使存在内容，也可以切换到视频库布局
- 对与会者和演示者控件的虚拟举手支持
- 会议和默认扬声器的可调整默认音量设置
- 从 Teams 会议室 (租户) 搜索和调用联合用户

> [!IMPORTANT]
> 版本 4.5 是支持 Windows 10 版本 1803 的最后一个版本;将来的版本不会提供给Windows 10版本 1803 上的系统。 有关 Windows 版本支持的详细信息，请参阅[Windows 10版本支持](./rooms-lifecycle-support.md#windows-10-release-support)。

### <a name="44630-06252020"></a>4.4.63.0 (2020/06/25) 

此更新中引入：

- 质量和可靠性修复
- 修复了“更新到 4.4.41.0 后应用程序无法启动”问题

> [!NOTE]
> 如果设备未自动更新到版本 4.4.63.0，请按照[更新到版本 4.4.41.0 后Microsoft Teams 会议室应用程序未启动](https://support.microsoft.com/help/4565998/teams-rooms-application-does-not-start-after-update)中的步骤解决此问题。

### <a name="44410-05062020"></a>4.4.41.0 (2020/05/06) 

此更新中引入：

- 应用程序在 Windows 10 展台中启动的可靠性修复

### <a name="44250-03312020"></a>4.4.25.0 (2020/03/31) 

此更新中引入：

- 对 Exchange 和 Skype for Business 的新式身份验证支持
- 支持使用 Teams 客户端圈) 对 Teams (服务组件进行动态紧急呼叫
- 能够使用 XML 为双显示会议室禁用会议中的重复内容
- 应用程序初始屏幕
- 开源软件 (OSS) 设备设置中的通知

### <a name="43420-03022020"></a>4.3.42.0 (2020/03/02) 

此更新中引入：

- “适用于企业的 Windows 汇报”的策略更新
- 修复了 Azure Monitor 中显示错误的设备事件报告

### <a name="43330-1102020"></a>4.3.33.0 (2020/1/10) 

此更新中引入：

- 修复了某些配置中出现的窗口大小调整/闪烁问题
- 删除了第三方会议的日历处理
- 已删除 Cortana 状态设置

### <a name="43230-12132019"></a>4.3.23.0 (2019/12/13) 

此更新中引入：

- 自动应答基于邻近感应的呼叫和用于控制此内容的管理员设置
- 设备管理员设置 UI 刷新，在“关于”选项卡下添加了设备配置
- 房间控制返回到主屏幕
- GCC 中可用的会议室 SKU
- 内容相机支持基于Surface Pro的系统 (最低要求应用版本：4.2.4.0) 

### <a name="4240-10072019"></a>4.2.4.0 (2019/10/07) 

此更新中引入：

- Windows 10 1903 支持。 Windows 10 1903 更新在应用更新后的几天内提供
- 屏幕键盘无法可靠地显示的修复

### <a name="41220-08152019"></a>4.1.22.0 (2019/08/15) 

此更新中引入：

- 一项新的内容相机功能，使用户能够智能地将传统白板加入 Teams 会议
- 对控制台 UI 进行其他改进，以减少混乱，并将“设置”移动到新的侧栏中，可通过主机上的“更多”访问
- 如果未连接本地内容电缆或未连接内容相机，则禁用共享托盘按钮
- 修复了触摸键盘仅在 MTR 系统重启后第一次出现失败的问题
- 质量和可靠性修复

### <a name="401050-07102019"></a>4.0.105.0 (2019/07/10) 

此更新中引入：

- Skype 会议室系统应用商店应用将品牌重塑为“Microsoft Teams 会议室”
- Microsoft Teams 会议室与 Microsoft Teams 重新对齐的控制台用户界面
- 主题更新：仅保留会议室显示器前面的自定义背景图像，同时将主机背景设置为中性颜色，以确保主机 UI 控件满足颜色对比度 - 辅助功能要求
- 用于 Teams 呼叫/会议的会议内呼叫控件的通用栏，以提供与 Microsoft Teams 电脑/Web/移动客户端一致的体验<sup>1</sup>
- Teams 通话/会议后通话质量反馈评分<sup>1</sup>
- 从电脑/Web/移动 Teams 客户端<sup>1</sup> <sup>2</sup> 共享时，在会议室显示器前面 Microsoft Teams 会议室接收/呈现 Microsoft Whiteboard
- 由于 Microsoft Teams 会议室 客户端的兼容性问题，删除了对 Windows 10 版本 1809 升级的支持。 Windows 10版本 19H1 支持将在将来的版本中添加

<sup>1</sup> 使用 Teams 环推出 Microsoft Teams 服务。 此功能可能早于 4.0.105.0 客户端更新提供

<sup>2</sup> 要求 IT 管理员打开 Microsoft Whiteboard。 此外，如果你有一个支持触摸的会议室显示正面，你必须使用 Windows 设置校准多个触摸显示器，并具有设备管理员登录名，以开始使用 Microsoft Whiteboard 从共享到 Teams 会议中的会议室显示器进行协作

### <a name="40850-0482019"></a>4.0.85.0 (2019/04/8) 

此更新中引入：

- 修复了“提供反馈”功能的问题
- 为即将Windows 10版本 1809 的Microsoft Teams 会议室设备升级做准备的优化

### <a name="40780-03142019"></a>4.0.78.0 (2019/03/14) 

此更新中引入：

- 修复了影响旧版Windows 10 RS2 版本中设备的“应用启动时挂起”bug。

### <a name="40760-03042019"></a>4.0.76.0 (2019/03/04) 

此更新中引入：

- 用于 Microsoft Teams P2P 会议和 PSTN 呼叫的 DTMF 键盘。 若要使 Microsoft Teams 成为默认呼叫客户端，管理员必须将 IsTeamsDefaultClient 设置为 true
- 将远程参与者的传入视频固定到会议室屏幕前的全屏。 在主机上使用参与者名单中的“固定”命令
- 通过添加会议室前通知对大厅通知的改进
- Microsoft Teams 会议室设备上未启用蓝牙信标时，删除了会议室前显示转换图标
- 解决 Teams 会议中的音量控制问题

### <a name="40640-12142018"></a>4.0.64.0 (2018/12/14) 

此更新中引入：

- 在双屏会议室系统上的会议室前面 (FoR) 显示器上显示内容
- 主题和会议室前用户界面改进
- TLS 1.2 客户端支持。 对于本地客户，通过 TLS 1.2 为 Microsoft Teams 会议室 启用通信需要Skype for Business Server 2015 累积更新 9 (CU9) 或 Skype for Business Server 2019 累积更新 1 (CU1) 。

### <a name="40510-11172018"></a>4.0.51.0 (2018/11/17) 

此更新中引入：

- 对 Teams 会议的双显示 (会议室正面) 支持

### <a name="40310-10162018"></a>4.0.31.0 (2018/10/16) 

此更新中引入：

- 质量和可靠性修复

### <a name="40270-1012018"></a>4.0.27.0 (2018/10/1) 

此更新中引入：

- 为以后的版本 1803 升级准备Microsoft Teams 会议室应用所需的代码更改Windows 10
- 修复本地化 EULA (特别是挪威语) 防止超出 EULA OOBE 设置窗口的格式设置问题
- 使Microsoft Teams 会议室应用程序在旧版 Lync 会议室系统上运行所需的代码更改。 [在此处](./lrs-migration.md)查看更多内容。

### <a name="40190-8312018"></a>4.0.19.0 (2018/8/31) 

此更新中引入：

- 未启动的 Crestron 应用程序的修补程序，在按下 Crestron SR 设备上的应用按钮时，通常可以访问该应用程序。 Microsoft Teams 会议室安装 4.0.19.0 后需要重启应用。

### <a name="40180-08272018"></a>4.0.18.0 (2018/08/27) 

此更新中引入：

- Teams 模式下的“报告问题”功能改进 (相当于Skype for Business模式下的“提供反馈”) 
- 为 SIP 呼叫启用从 Teams 回退到Skype for Business模式的功能
- 辅助功能改进 (讲述人、放大镜) 
- 应用 XML 预配更改后，根据需要自动重启应用
- 其他修复

### <a name="4080-07062018"></a>4.0.8.0 (2018/07/06) 

此更新中引入：

- 此更新在会议室系统设备上启用Skype for Business *和* Teams 会议支持。 应用更新后，Teams 默认处于关闭状态。 管理员可以在设备设置中本地或通过远程 xml 推送启用 Teams。

### <a name="311150-06182018"></a>3.1.115.0 (2018/06/18) 

此更新中引入：

- 修复问题，以解决在应用启动期间在某些系统上观察到的错误。

### <a name="311130-06132018"></a>3.1.113.0 (2018/06/13) 

此更新中引入：

- 使 Microsoft 能够更灵活地管理 Windows 汇报的更改。
- 最终用户体验没有变化。

### <a name="311120-06052018"></a>3.1.112.0 (2018/06/05) 

此更新中引入：

- 修复了 解决连接到两个会议室前显示器和视频引入的基于 Surface Pro 2017 设备的主机响应能力问题
- 自动检查以确保系统正在运行最新的预配脚本

### <a name="311040-04162018"></a>3.1.104.0 (2018/04/16) 

此更新中引入：

- 修复以改进基于 Windows 10 版本 1709 的系统中的 OSK (屏幕键盘) 行为
- 为将来的操作系统更新做准备的改进

### <a name="311000-03162018"></a>3.1.100.0 (2018/03/16) 

此更新中引入：

- 应用程序已更新以改进遥测

### <a name="31990-03142018"></a>3.1.99.0 (2018/03/14) 

此更新中引入：

- 修复了可能出现间歇性会议加入问题的问题
- 修复了已知导致设备“挂起”体验的问题

### <a name="31980-382018"></a>3.1.98.0 (2018/3/8) 

此更新中引入：

- Bug/崩溃修复以提高稳定性
- 支持大小可变的控制台
- 外围音频处理卸载 (其他媒体允许列表) 
- 使 IT 专业人员能够使用 Windows 10 版本 1709 1 月更新及更高版本生成自己操作映像的优化。

### <a name="30160-11272017"></a>3.0.16.0 (2017/11/27) 

此更新中引入：

- 修复了“提供反馈”功能的问题。

### <a name="30150-1032017"></a>3.0.15.0 (2017/10/3) 

此更新中引入：

- 支持 [Polycom MSR 系列](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl) 扩展坞硬件
- 对 [Logitech Brio 的支持](https://www.logitech.com/product/brio)
- 解决了当会议室中没有活动时，主机 (显示器和房间前) 无法进入睡眠模式的问题

### <a name="30120-912017"></a>3.0.12.0 (9/1/2017) 

此更新中引入：

- 在 Surface Pro (2017) 平板电脑上运行
- 支持Windows 10 企业版 Creator 的更新 (英语版本 1703) 
- 支持 [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system) 扩展坞硬件
- OEM 对 Crestron) 环境控制 (的支持

自Microsoft Teams 会议室版本 3.0.12.0 (update 3) 起，不再支持 64 位版本的 Windows 10 企业版 周年 (英语版本 1607) 。

### <a name="3080-842017"></a>3.0.8.0 (2017/8/4) 

此更新中引入：

- 解决了通过参与者搜索字段搜索联合用户时观察到的问题。 在此修补程序之前，外部联合用户的搜索结果可能未正确解析，而是返回不正确的结果。

### <a name="3060-772017"></a>3.0.6.0 (7/7/2017) 

此更新中引入：

- Dual-Screen旧系统奇偶校验) 支持 (
- 主题 (内置主题，并能够设置自定义主题) 
- 为公共版本提供反馈的能力
- 改进了围绕会议加入可靠性的遥测
- 改进了 OMS 报告
- IT 管理员远程配置设备的功能

### <a name="2020-03152017"></a>2.0.2.0 (2017/03/15) 

此更新中引入：

- 应用内用户选择会议室音频和视频 USB 设备
- 使用 Microsoft Operations Management Suite（现在为 Azure Monitor）的客户提供集成会议室控制台状态报告

### <a name="release-to-market-1272016"></a>发布到市场 (12/7/2016) 

**功能 () ：**

 **为 Skype for Business 而构建**

- 一键式加入 Skype 会议
- Skype 会议体验针对屏幕填充高清视频和高清宽带音频的房间进行优化
- 所有参与者均可使用所选设备从任意位置连接到 Skype 会议
- 从目录中（在此可立即看到用户的状态）或通过电话呼叫邀请用户
- 支持 Skype for Business PSTN 会议和 PSTN 呼叫，以替代会议室中的单独会议电话

 **转换任何会议室**

- 专用的 Skype 会议应用针对桌面中心触摸式控制器和会议室前方的大型显示屏进行了优化
- 在会议室显示器或投影仪前重用现有投资
- 适用于各种类型的会议室，从小型到大型会议室
- 经认证的 Skype for Business 音频和视频设备可用于各种规模的会议室
- 内置有线引入，用于将桌面共享投影到会议室和Skype 会议

 **易于部署、便于管理**

- 当检测到房间中的人员时自动唤醒显示器的 Always-On 设备
- UWP（通用 Windows 平台）Skype 会议应用的部署和更新都非常简单
- Windows AppLocker 可将设备锁定至 Skype 会议应用
- 通过Intune和Configuration Manager (MDM) 作为Windows 10 企业版设备进行监视和管理
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
