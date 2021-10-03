---
title: 适用于 Microsoft Teams 会议室 的发行说明
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
description: 管理员可以阅读有关更新的Microsoft Teams 会议室说明，其中列出了 Microsoft Teams 会议室。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f4f6c719a0be5e1d400eae37ba19be8e0dbd0214
ms.sourcegitcommit: 26ce61afcb743c8b9e06b4fa048ad93ab70c31c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2021
ms.locfileid: "60082872"
---
# <a name="release-notes-for-microsoft-teams-rooms"></a>适用于 Microsoft Teams 会议室 的发行说明

本文讨论在性能方面的累积Microsoft Teams 会议室。

## <a name="version-history"></a>版本历史记录

|发布 |发布到 <br/> Microsoft Store |
|--- |--- |
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

### <a name="410100-1012021"></a>2021/10/10 (4.10.10.0) 

此更新中引入：
- 会议室远程功能允许用户使用移动设备上的Teams控制房间的基本功能 *
- Logitech 转录内容相机支持用于共享到会议中的 BLE 按钮
- 聊天气泡在会议聊天中提供通知，以使用会议聊天引起对所说消息的注意 *
- 大型库和"共同"模式支持现已在 GCC High 中提供
- 添加到会议的新Cortana、按姓名添加到会议以及按姓名呼叫 
- Cortana默认情况下，在所有设备上启用"推送到交谈"功能。 若要了解更多[Cortana，请参阅在 Teams 中提供语音Teams。](../cortana-in-teams.md)

> [!NOTE]
> 已弃用 19H1 支持。 4.10 支持的操作系统最低版本为 19H2。

> [!NOTE]
> *这些功能是使用 Teams推出的，并且将处理所有大于 4.9 的应用程序版本。

> [!NOTE]
> 若要同时从 Teams 移动应用和按按 TEAMS Mobile 应用在花名册中查找会议室帐户并按"控制此会议室"菜单，你可以从应用控制呼叫控件。

### <a name="49120-7282021"></a>2021/7/28 (4.9.12.0) 

此更新中引入：
- Microsoft Teams模式现在在应用程序设置中可用，因此无需再设置Skype for Business帐户。 在此模式下，登录到仅Teams模式的设备Skype for Business作为来宾用户加入会议。
- 修复了 HDMI 音频导致呼叫音量降低的问题。 对于应用程序版本 4.9.12.0 的所有设备，会自动启用 HDMI 音频功能。

> [!NOTE]
> 当Skype for Business生命周期结束时，建议更新为仅Teams模式。

### <a name="48310-05122021"></a>2021/05/12 (4.8.31.0) 

此更新中引入：
- Windows 10 20H2 支持 

> [!NOTE]
> Crestron UC-Engine (包含"KYSKLi"的 BIOS 版本日期) Teams 会议室存在兼容性问题，并且系统 OEM 将在近期提供更新的驱动程序。 Windows 10 20H2 不向这些设备提供。 有关版本支持Windows，请参阅版本[Windows 10支持](./rooms-lifecycle-support.md#windows-10-release-support)。

### <a name="48250-04222021"></a>2021/04/22 (4.8.25.0) 

此更新中引入：
- 修复了以下问题：Teams 会议室主机上的会议室信息未显示，而聊天室帐户隐藏在 GAL (列表中) 

> [!NOTE]
> GCCH 客户可以从手动更新设备下载Microsoft Teams 会议室[包](manual-update.md)

### <a name="48190-04062021"></a>2021/04/06 (4.8.19.0) 

此更新中引入：
- 政府社区云高 (GCCH) 支持Teams 会议室。 具有现有 Teams 会议室 设备的 GCCH 客户可以从手动更新设备下载 4.8.19.0 [Microsoft Teams 会议室版本](manual-update.md)
- 通过 720p 支持 (加入缩放会议) 并接收参与者的视频库
- Skype for Business默认模式下删除了登录失败Teams横幅。 此更改支持组织删除Skype for Business基础结构
- Teams会议加入链接分析现在处理 Microsoft Defender 高级线程保护保险箱链接以允许无缝加入外部Teams连接
- 修复了当共享者的电脑在 Skype for Business 中设置了自定义 DPI 时，会议中的共享内容缩放Windows
- 质量和可靠性修复

### <a name="47190-02032021"></a>2021/02/03 (4.7.19.0) 

此更新中引入：
- 质量和可靠性修复

### <a name="47150-12112020"></a>4.7.15.0 (2020/12/11) 

此更新中引入：

- 与会议参与者共享 HDMI 音频Teams会议
- Cortana语音技能 (预览版) 
- 当聊天室作为与会者加入时，Teams基于音频权限取消静音。 有关详细信息，请参阅[管理会议中的与会者Teams权限](https://support.microsoft.com/office/manage-attendee-audio-permissions-in-teams-meetings-f9db15e1-f46f-46da-95c6-34f9f39e671a)。
- 从会议室控制台聚焦某人Teams，在会议室显示器上使用聚焦视频

> [!NOTE]
> Cortana语音技能适用于位于美国的租户的精选音频外围设备。 将来会添加其他国家和地区。 有关详细信息，请参阅Cortana[语音帮助Teams](../cortana-in-teams.md)

### <a name="46230-10192020"></a>2020/10/19 (4.6.23.0) 

此更新中引入：

- 修复了在会议中调用屏幕键盘时出现白色半Teams的问题

### <a name="46200-09302020"></a>2020/09/30 (4.6.20.0) 

此更新中引入：

- 在会议室显示器前查看更多带 3x3 视频库的视频  
- 从一线线启动本地实时隐藏式字幕
- 使用直接来宾加入Teams 会议室预览版从 (缩放) 

> [!NOTE]
> 3x3 视频库和本地实时隐藏式字幕通过 Microsoft Teams传送。 这些功能适用于应用程序版本Teams 会议室 4.5.37.0 及以上版本的所有设备。

### <a name="45370-08142020"></a>2020/08/14 (4.5.37.0) 

此更新中引入：

- Microsoft Teams 2S Surface Hub协调会议
- 修复了Skype [KB4565351 Windows 10安装更新](https://support.microsoft.com/help/4565351/windows-10-update-kb4565351) [KB4571709](https://support.microsoft.com/help/4571709/windows-10-update-kb4571709)时Windows 10 For Business 登录失败的问题

### <a name="45350-07232020"></a>2020/07/23 (4.5.35.0) 

此更新中引入：

- 通过直接来宾加入Teams 会议室加入 Cisco WebEx 会议
- Teams管理中心启用和自动注册
- Windows 10 1909 版本支持
- 即使内容存在，也切换到视频库布局
- 虚拟举手支持与会者和演示者控件
- 会议和默认扬声器的可调整默认音量设置
- 从会议室搜索并 (联合) Teams用户

> [!IMPORTANT]
> 版本 4.5 是最后一个版本，Windows 10版本 1803;将来的版本将不会提供给版本 1803 Windows 10的系统。 有关版本支持Windows，请参阅版本[Windows 10支持](./rooms-lifecycle-support.md#windows-10-release-support)。

### <a name="44630-06252020"></a>2020/06/25 (4.4.63.0) 

此更新中引入：

- 质量和可靠性修复
- 修复了"更新到 4.4.41.0 后应用程序无法启动"问题

> [!NOTE]
> 如果设备未自动更新到版本 4.4.63.0，请按照[更新到版本 4.4.41.0](https://support.microsoft.com/help/4565998/teams-rooms-application-does-not-start-after-update)后 Microsoft Teams 会议室 应用程序中无法启动的步骤来解决此问题。

### <a name="44410-05062020"></a>4.4.41.0 (2020/05/06) 

此更新中引入：

- 在展台启动应用程序的可靠性Windows 10修复

### <a name="44250-03312020"></a>2020/03/31 (4.4.25.0) 

此更新中引入：

- 新式身份验证支持Exchange Skype for Business
- 支持动态紧急呼叫，Teams (服务组件，并且使用客户端环Teams释放) 
- 使用 XML 为双显示器会议室禁用会议外重复内容的能力
- 应用程序初始屏幕
- 开放源代码软件 (OSS) 设备设置中的通知

### <a name="43420-03022020"></a>4.3.42.0 (2020/03/02) 

此更新中引入：

- "适用于企业Windows更新"的策略更新
- 修复了设备事件报告在 Azure Monitor 中显示错误的问题

### <a name="43330-1102020"></a>2020/1/10 (4.3.33.0) 

此更新中引入：

- 修复了某些配置中出现的窗口大小调整/闪烁问题
- 删除了第三方会议的日历处理
- Cortana状态设置已删除

### <a name="43230-12132019"></a>2019/12/13 (4.3.23.0) 

此更新中引入：

- 基于自动应答邻近感应的呼叫和管理员设置来控制这一点
- 设备管理员设置 UI 刷新，同时在"关于"选项卡下添加设备配置
- 会议室控件返回到主屏幕
- 会议室SKU 在 GCC
- 内容相机支持基于 Surface Pro 的系统 (最低要求的应用版本：4.2.4.0) 

### <a name="4240-10072019"></a>2019/10/07 (4.2.4.0) 

此更新中引入：

- Windows 10 1903 支持。 Windows 10应用更新后的几天内提供 1903 更新
- 修复了屏幕键盘无法可靠地显示的问题

### <a name="41220-08152019"></a>2019/08/15 (4.1.22.0) 

此更新中引入：

- 新的内容相机功能，使用户能够智能地将传统白板加入其Teams会议
- 对控制台 UI 的其他改进，以减少混乱设置移动到新的侧栏中，该侧栏可通过主机上的"更多"访问
- 如果本地内容电缆未连接或内容相机未连接，则禁用共享托盘按钮
- 修复了触摸键盘故障的问题，该问题仅在重新启动了一个一个设计公司系统之后才显示
- 质量和可靠性修复

### <a name="401050-07102019"></a>2019/07/10 (4.0.105.0) 

此更新中引入：

- Skype会议室系统应用商店应用品牌"Microsoft Teams 会议室"
- Microsoft Teams 会议室主机用户界面重新Microsoft Teams
- 主题更新：仅在会议室显示器前保留自定义背景图像，同时使主机背景成为中性颜色，以确保主机 UI 控件满足颜色对比度 - 辅助功能要求
- 用于呼叫/会议的会议内呼叫控件的通用Teams栏，以提供与电脑/Web/移动Microsoft Teams一致的体验<sup>1</sup>
- 通话后通话质量反馈Teams分级<sup>1</sup>
- 从电脑/Microsoft Whiteboard/移动Microsoft Teams 会议室客户端<sup>1 2</sup>共享时，在会议室Teams上接收/呈现<sup>图像</sup>
- 由于客户端Windows 10兼容性问题，删除了对版本 1809 Microsoft Teams 会议室的支持。 Windows 10未来版本中将添加版本 19H1 支持

<sup>1 Microsoft Teams</sup>环推出Teams服务。 此功能可能在 4.0.105.0 客户端更新之前或之后可用

<sup>2</sup>要求 IT 管理员启用Microsoft Whiteboard。 此外，如果会议室显示器前面启用了触摸功能，则必须使用设备管理员登录名的 Windows 设置校准多个触摸显示器，以开始使用 Microsoft Whiteboard 从共享到 Teams 会议的房间显示进行协作

### <a name="40850-0482019"></a>2019/04/8 (4.0.85.0) 

此更新中引入：

- 修复了"提供反馈"功能的问题
- 为即将推出的设备升级到 Microsoft Teams 会议室版本 1809 Windows 10优化

### <a name="40780-03142019"></a>2019/03/14 (4.0.78.0) 

此更新中引入：

- 修复了"在应用启动时挂起"bug，该 bug 影响旧版 RS2 Windows 10上的设备。

### <a name="40760-03042019"></a>2019/03/04 (4.0.76.0) 

此更新中引入：

- 用于 P2P Microsoft Teams PSTN 呼叫的 DTMF 键盘。 若要Microsoft Teams客户端，管理员必须将 IsTeamsDefaultClient 设置为 true
- 将远程参与者的传入视频固定到会议室显示器前面的全屏。 使用主机上参与者名单的"固定"命令
- 改进了大厅通知，并新增了"会议室前"通知
- 当设备未启用蓝牙时，会议室前显示转换Microsoft Teams 会议室图标
- 修复了会议中音量Teams问题

### <a name="40640-12142018"></a>2018/12/14 (4.0.64.0) 

此更新中引入：

- 在双屏幕会议室系统上 (FoR) 显示内容
- "Theming"和"Front of Room"用户界面改进
- TLS 1.2 客户端支持。 对于本地客户，通过 TLS 1.2 for Microsoft Teams 会议室 启用通信需要 Skype for Business Server 2015 累积更新 9 (CU9) 或 Skype for Business Server 2019 累积更新 1 (CU1) 。

### <a name="40510-11172018"></a>2018/11/17 (4.0.51.0) 

此更新中引入：

- 会议室 (的双显示器) 支持Teams会议

### <a name="40310-10162018"></a>2018/10/16 (4.0.31.0) 

此更新中引入：

- 质量和可靠性修复

### <a name="40270-1012018"></a>2018/10/1 (4.0.27.0) 

此更新中引入：

- 为以后的版本 1803 Microsoft Teams 会议室准备 Windows 10 应用所需的代码更改
- 修复本地化 EUL（特别是挪威 (）) 阻止超过 EULA OOBE 设置窗口的格式问题
- 在旧版 Lync 会议室Microsoft Teams 会议室运行应用程序所需的代码更改。 在此处查看 [更多信息](./lrs-migration.md)。

### <a name="40190-8312018"></a>2018/8/31 (4.0.19.0) 

此更新中引入：

- 在按下了 Crestron SR 设备上应用按钮时，通常可访问的用于 Crestron 应用程序的修补程序。 Microsoft Teams 会议室 4.0.19.0 后需要重启应用。

### <a name="40180-08272018"></a>2018/08/27 (4.0.18.0) 

此更新中引入：

- "报告问题"功能改进Teams模式 ("提供反馈"等效于Skype for Business模式) 
- 支持从 SIP 呼叫Teams Skype for Business到呼叫模式
- "讲述人 (放大镜"选项的辅助功能) 
- 应用 XML 预配更改后，如果需要，自动重启应用
- 其他修补程序

### <a name="4080-07062018"></a>2018/07/06 (4.0.8.0) 

此更新中引入：

- 此更新在会议室 *Skype for Business Teams* 会议支持。 Teams更新后，默认会关闭该状态。 管理员可以在本地设备Teams或远程 xml 推送来启用连接。

### <a name="311150-06182018"></a>2018/06/18 (3.1.115.0) 

此更新中引入：

- 修复了在应用启动期间在某些系统上观察到的错误。

### <a name="311130-06132018"></a>2018/06/13 (3.1.113.0) 

此更新中引入：

- 通过更改，Microsoft 可以更灵活地管理Windows更新。
- 不更改最终用户体验。

### <a name="311120-06052018"></a>2018/06/05 (3.1.112.0) 

此更新中引入：

- 修复了在连接到两个房间前显示器和视频Surface Pro的基于 2017 的设备上观察到的主机响应问题
- 自动检查以确保系统正在运行最新的预配脚本

### <a name="311040-04162018"></a>2018/04/16 (3.1.104.0) 

此更新中引入：

- 修复了在基于 Windows 10 (1709 的系统中改进屏幕键盘) 的 OSK 功能
- 为将来操作系统更新做准备的改进

### <a name="311000-03162018"></a>2018/03/16 (3.1.100.0) 

此更新中引入：

- 更新应用程序以改进遥测

### <a name="31990-03142018"></a>2018/03/14 (3.1.99.0) 

此更新中引入：

- 修复了可能发生间歇性会议加入问题的问题
- 修复了已知导致设备"挂起"体验的问题

### <a name="31980-382018"></a>3.1.98.0 (2018/3/8) 

此更新中引入：

- Bug/崩溃修复，以提高稳定性
- 支持可变大小的主机
- 外围设备音频处理卸载 (其他媒体允许列表) 
- 使 IT 专业人员能够使用版本 1709 1 月更新Windows 10构建自己动手映像的优化。

### <a name="30160-11272017"></a>2017/11/27 (3.0.16.0) 

此更新中引入：

- 修复了"提供反馈"功能的问题。

### <a name="30150-1032017"></a>2017/10/3 (3.0.15.0) 

此更新中引入：

- 支持 [Polycom MSR 系列扩展](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl) 坞硬件
- 对 [Logitech Brio 的支持](https://www.logitech.com/product/brio)
- 解决在 (没有活动时，) 主机和房间前显示无法进入睡眠模式的问题

### <a name="30120-912017"></a>2017/9/1 (3.0.12.0) 

此更新中引入：

- 在 2017 Surface Pro (平板电脑上运行) 
- 支持Windows 10 企业版的 Update (英语版本 1703) 
- 支持 [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system) 扩展坞硬件
- Oem 对 Crestron (环境控制) 

自 Microsoft Teams 会议室 版本 3.0.12.0 (update) 3 起，不再支持 64 位版本的 Windows 10 企业版 周年版 (英文版 1607) 。

### <a name="3080-842017"></a>2017/8/4 (3.0.8.0) 

此更新中引入：

- 解决通过"参与者"搜索字段搜索联合用户时观察到的问题。 在此修补程序之前，外部联合用户的搜索结果可能未正确解析，而是返回了不正确的结果。

### <a name="3060-772017"></a>2017/7/7 (3.0.6.0) 

此更新中引入：

- Dual-Screen支持 (旧版系统奇偶校验) 
- 主题 (内置主题，并能够设置自定义主题) 
- 为公共版本提供反馈的能力
- 改进了有关会议加入可靠性的遥测
- 改进了 OMS 报告
- IT 管理员能够远程配置设备

### <a name="2020-03152017"></a>2017/03/15 (2.0.2.0) 

此更新中引入：

- 应用内用户选择会议室音频和视频 USB 设备
- 使用 Microsoft Operations Management Suite（现为 Azure Monitor）的客户集成会议室控制台状态报告

### <a name="release-to-market-1272016"></a>2016 年 12 (7 月 12 日上市) 

**功能 () ：**

 **为 Skype for Business 而构建**

- 一键式加入 Skype 会议
- Skype 会议屏幕填充 HD 视频和 HD 宽带音频的会议室优化的体验
- 所有参与者均可使用所选设备从任意位置连接到 Skype 会议
- 从目录中（在此可立即看到用户的状态）或通过电话呼叫邀请用户
- 支持 Skype for Business PSTN 会议和 PSTN 呼叫，以替代会议室中的单独会议电话

 **转换任何会议室**

- 专用的 Skype 会议应用针对桌面中心触摸式控制器和会议室前方的大型显示屏进行了优化
- 重复使用会议室显示器或投影仪前面的现有投资
- 适用于各种类型的会议室，从小型到大型会议室
- 经认证的 Skype for Business 音频和视频设备可用于各种规模的会议室
- 内置的有线采集可用于将桌面共享投影到会议室和 Skype 会议

 **易于部署、便于管理**

- 在检测到会议室中的人员时自动唤醒显示器的始终打开设备
- UWP（通用 Windows 平台）Skype 会议应用的部署和更新都非常简单
- Windows AppLocker 可将设备锁定至 Skype 会议应用
- 通过 Intune 和 Configuration Manager Windows 10 企业版 MDM 应用程序作为 (设备进行监视) 
- 企业级可靠性
- 由于最终用户很熟悉 Skype 用户界面，因此只需进行少量培训
- 在 Surface Pro 4 平板电脑上运行

<a name="See"> </a>
## <a name="see-also"></a>另请参阅

[Microsoft Teams 会议室帮助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[准备环境](rooms-prep.md)

[支持Microsoft Teams 会议室当前分支版本](rooms-lifecycle-support.md)

[已知问题](known-issues.md)

[Microsoft Teams 会议室规划](rooms-plan.md)

[管理 Microsoft Teams 会议室](rooms-manage.md)
