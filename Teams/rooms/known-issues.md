---
title: 已知问题
ms.author: dstrome
author: dstrome
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
description: 管理员可以了解适用于用户的已知问题Microsoft Teams 会议室，包括更新、用户界面、硬件、限制和预期行为。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 02e7d2411fa1d8a86fe20dcab3013be758f22a21
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117530"
---
# <a name="known-issues"></a>已知问题 
 
本文按功能区域列出了 Microsoft Teams 会议室的已知问题。
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>更新 

| 问题标题 |  行为\/症状 | 已知解决方法 | 知识库文章 |
|  ---        |      ---             |   ---            | --- |
| 应用程序未启动 |  更新到应用程序版本 4.4.41.0 后，系统会启动到黑屏，或者几分钟后转到登录屏幕。 | 请按照更新到[Microsoft Teams 会议室 4.4.41.0](/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update)后应用程序无法启动中的步骤来解决此问题。  | 无 |
|  SfB 会议内容共享未全屏显示         |    在Skype for Business中，使用高 DPI 设置在会议室前显示会议室可能会遇到共享到会议的内容在会议室显示前不显示全屏的问题。 这是由远程桌面协议 Windows 10 RDP (API 中) 问题造成的。 | 使用 `<WinRTRdpEnabled>` XML 设置禁用 Windows 10 RDP API 来解决此问题。 若要禁用，需要将值指定为 `false` 。 有关详细信息，请参阅使用 [XML 配置文件管理控制台设置](xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)。 | 无 |
|  应用已过期         |    Microsoft Teams 会议室控制台显示“系统配置已过期”错误。                |   [使用 Microsoft Teams 会议室恢复工具](recovery-tool.md)             |  无 |
|  设备已更新为不支持的版本Windows 10   |    Windows 10设备从版本 1803 更新到版本 1809，但不支持。 支持的版本为 1903。 |   如果 [DeferFeatureUpdatesPeriodinDays](/windows/deployment/update/waas-configure-wufb) 设置的组策略或 MDM 设置（允许您将功能更新延迟指定的天数）设置为最长 365 天，则可能会发生这种情况。 <br><br> Windows 10版本 1809 不受支持，Microsoft Teams 会议室版本 1903。 但是，截至 2020 年 3 月 27 日，版本 1809 已超过 365 天。 如果未更改此设置，Windows尝试安装版本 1809，这可能会导致Microsoft Teams 会议室。<br><br>若要避免这种情况， **请删除** 用于延迟更新的任何组策略或 MDM 设置。 这样Windows更新到最新的受支持 OS 版本。 <br><br>**重要** 必须删除组策略或 MDM **设置**， (未配置) 不设置为 **0。** 如果策略设置为 0，Windows可能不支持的最新可用版本。 |  无 |



<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>用户界面 

| 问题标题 |  行为\/症状 | 已知解决方法 | 知识库文章 |
|  ---        |      ---             |   ---            | --- |
|虚拟键盘缺失   | 当你需要在 Microsoft Teams 会议室中输入信息时，不显示虚拟键盘。 此问题出现在版本Windows 10 1903 的版本中。 | 通过更新为基于 x64 的系统安装 2020-04 Windows 10 1903 Windows更新。  | 无 | 

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

如果希望房间前显示自动切换到活动视频源 (例如当源从备用模式唤醒时) 的一个"市/站"控制台，则必须满足某些条件。 此功能是可选的，但受 Microsoft Teams 会议室的支持，但基础硬件支持该功能。 用作房间前显示器的消费者电视需要支持 HDMI 的使用者 (CEC) 功能。  根据所选的扩展坞或主机 (可能不支持 CEC，请参阅制造商支持文档) ，需要来自 Crestron 的 [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) 或 Extron 的 [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) 等控制器才能启用所需行为。 

***

始终使用 1 Gbps 有线网络连接，以确保你拥有所需的带宽。 

***

如果Microsoft Teams 会议室设备失去对域的信任，将无法在设备上进行身份验证并打开设置。 例如，如果在域加入Microsoft Teams 会议室删除域，信任将丢失。 解决方法是使用本地管理员帐户登录。 
***
Microsoft Teams 会议室是一个多窗口应用程序，需要将房间前显示器连接到设备的 HDMI 端口，使应用正常运行。 如果你正在测试并且尚未购买显示器，请确保你已连接 HDMI 显示器或使用虚拟 HDMI 插头。
***
<a name="See"> </a>  
## <a name="see-also"></a>另请参阅

[Microsoft Teams 会议室帮助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[管理 Microsoft Teams 会议室](rooms-manage.md)