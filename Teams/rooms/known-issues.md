---
title: 已知问题
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 管理员可以了解 Microsoft 团队聊天室的已知问题列表，包括更新、用户界面、硬件、限制和预期行为。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1083ceb040f173aeef0a8a60d56a888a6b8fdb17
ms.sourcegitcommit: 02dd624d39a14f48b9d2463881605d2f051722e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2020
ms.locfileid: "44874449"
---
# <a name="known-issues"></a>已知问题 
 
本文按功能区域列出了 Microsoft Teams 会议室的已知问题。
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>更新 

| 问题标题 |  行为\/症状 | 已知解决方法 | 知识库文章 |
|  ---        |      ---             |   ---            | --- |
| 应用程序不启动 |  更新到应用程序版本4.4.41.0 后，系统将启动到黑屏，或在几分钟后转到登录屏幕。 | 请按照[Microsoft 团队聊天室应用程序在更新到版本4.4.41.0 后无法启动](https://docs.microsoft.com/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update)的步骤来解决此问题。  | 无 |
|  应用已过期         |    Microsoft Teams 会议室控制台显示“系统配置已过期”错误。                |   [使用 Microsoft Teams 会议室恢复工具](recovery-tool.md)             |  无 |
|  设备更新为不受支持的 Windows 10 版本   |    Windows 10 设备从版本1803更新到版本1809，不受支持。 支持的版本为1903。 |   如果 DeferFeatureUpdatesPeriodinDays 设置的[组策略或 MDM 设置](https://docs.microsoft.com/windows/deployment/update/waas-configure-wufb)（允许您将功能更新推迟到指定的天数内），则可能会发生这种情况，最大为365天。 <br><br> Microsoft 团队聊天室不支持 Windows 10 版本1809，但支持版本1903。 但是，从2020年3月27日起，版本1809超过365天。 如果此设置未更改，Windows 将尝试安装版本1809，这可能会导致 Microsoft 团队聊天室出现问题。<br><br>为避免这种情况，请**删除**延迟更新的任何组策略或 MDM 设置。 这允许 Windows 更新到最新的受支持的操作系统版本。 <br><br>**重要提示**必须**删除**"组策略" 或 "MDM" 设置（未配置），并且**未设置为 "0**"。 如果该策略设置为0，则 Windows 会获得可能不受支持的最新可用版本。 |  无 |



<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>用户界面 

| 问题标题 |  行为\/症状 | 已知解决方法 | 知识库文章 |
|  ---        |      ---             |   ---            | --- |
|虚拟键盘缺失   | 当你需要在 Microsoft Teams 会议室中输入信息时，不显示虚拟键盘。 此问题出现在 Windows 10 版本1903中。 | 通过 Windows 更新为基于 x64 的系统的 Windows 10 版本1903安装2020-04 累积更新。  | 无 | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>硬件

| 问题标题 |  行为\/症状 | 已知解决方法 | 知识库文章 |
|  ---        |      ---             |   ---            |   --- |
| 未检测到监视器 | 在 Surface Pro（2017 机型）设备上运行 Microsoft Teams 会议室时，检测不到监视器。 |  按住 Surface Pro 电源按钮 20 秒或更长时间。 执行此操作时，设备将重启并清除图形缓存。 |[KB4055681](https://support.microsoft.com/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>限制和预期行为

***

Microsoft Teams 会议室不支持 HDCP 输入，已发现它会导致 HDMI 采集功能（视频、音频）出现问题。 请确保连接到 Microsoft Teams 会议室的交换机禁用了 HDCP 选项。 

***

如果你希望在从待机模式唤醒源时自动切换到活动视频源（如 MTR 控制台），则必须满足某些条件。 此功能是可选的，但 Microsoft 团队工作室软件支持此功能，但提供的基础硬件支持此功能。 在室内显示时使用的消费者电视需要支持 HDMI 的 "消费者电子设备控制" （CEC）功能。  根据所选的坞站或控制台（可能不支持 CEC，请参阅制造商支持文档），可能需要[EXTRON HD CTL 100](https://www.extron.com/article/hdctl100ad)之类的工作区控制器来启用所需的行为。 

***

始终使用有线1至 Gbps 网络连接，确保您有所需的带宽。 

***

如果你的 Microsoft 团队聊天室设备失去了与域的信任，你将无法在设备上进行身份验证并打开 "设置"。 例如，如果在域加入域后从域中删除 Microsoft 团队聊天室，则信任将丢失。 解决方法是使用本地管理员帐户登录。 
***
Microsoft 团队会议室是一个多窗口应用程序，需要将房间内的正面显示连接到设备的 HDMI 端口，才能使应用正常运行。 请确保你已连接 HDMI 显示器，或者使用虚拟 HDMI 插头（如果你正在测试，并且尚未购买显示器）。
***
<a name="See"> </a>  
## <a name="see-also"></a>另请参阅

[Microsoft Teams 会议室帮助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[管理 Microsoft Teams 会议室](rooms-manage.md)
