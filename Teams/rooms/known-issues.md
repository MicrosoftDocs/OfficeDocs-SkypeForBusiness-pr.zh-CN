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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: 管理员可以了解适用于用户的已知问题Microsoft Teams 会议室，包括更新、用户界面、硬件、限制和预期行为。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 72d80d930a8c140e6c2c00917a08cf69398fd4b1
ms.sourcegitcommit: badcd3abeed138c330ee98d739eac5bbc5c0bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2021
ms.locfileid: "61441122"
---
# <a name="known-issues"></a>已知问题 
 
本文按功能区域列出了 Microsoft Teams 会议室的已知问题。
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>更新 

| 问题标题 |  行为\/症状 | 已知解决方法 | 知识库文章 |
|  ---        |      ---             |   ---            | --- |
| 拆分库参与者视频   | 在双前会议室显示模式下，如果超过 9 个远程视频参与者的会议上没有共享内容，则会议室前显示具有自预览的 1 个视频可能会由于已知问题显示为音频。 此外，音频参与者数少于在双"会议室前端"显示器上显示的实际音频参与者数。 | 问题将在将来的更新中解决。 | 无 |
| 应用程序未启动 |  更新到应用程序版本 4.4.41.0 后，系统会启动到黑屏，或者几分钟后转到登录屏幕。 | 请按照更新到[Microsoft Teams 会议室 4.4.41.0](/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update)后应用程序无法启动中的步骤来解决此问题。  | 无 |
|  内容共享后会议音量低         |   Microsoft Teams 会议室 20H2 Windows 10的设备在通过室内 HDMI 共享内容后减少了媒体和会议音量。 这是由 20H2 Windows 10音频问题导致的。 | 此问题的修补程序在应用程序版本 [4.9.12.0 中提供](/microsoftteams/rooms/rooms-release-note#49120-7282021)。 | 无 |
|  应用已过期         |    Microsoft Teams 会议室控制台显示“系统配置已过期”错误。                |   [使用 Microsoft Teams 会议室恢复工具](recovery-tool.md)             |  无 |
|  设备已更新为不支持的版本Windows 10   |    Windows 10从版本 1803 更新到版本 1809，但不支持。 支持的版本为 1903。 |   如果 [DeferFeatureUpdatesPeriodinDays](/windows/deployment/update/waas-configure-wufb) 设置的组策略或 MDM 设置（允许您将功能更新延迟指定的天数）设置为最长 365 天，则可能会发生这种情况。 <br><br> Windows 10版本 1809 不受支持，Microsoft Teams 会议室版本 1903。 但是，截至 2020 年 3 月 27 日，版本 1809 已超过 365 天。 如果未更改此设置，Windows安装版本 1809，这可能会导致Microsoft Teams 会议室。<br><br>若要避免这种情况， **请删除** 用于延迟更新的任何组策略或 MDM 设置。 这Windows更新到最新的受支持 OS 版本。 <br><br>**重要提示：** 必须删除组策略或 MDM **设置 (** 未配置) 不 **设置为 0。** 如果策略设置为 0，Windows可能不支持的最新可用版本。 |  无 |



<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>用户界面 

| 问题标题 |  行为\/症状 | 已知解决方法 | 知识库文章 |
|  ---        |      ---             |   ---            | --- |
|虚拟键盘缺失   | 当你需要在 Microsoft Teams 会议室中输入信息时，不显示虚拟键盘。 此问题在版本 1903 Windows 10中发生。 | 通过更新为基于 x64 的系统安装 2020-04 Windows 10累积更新，版本 1903 Windows更新。  | 无 | 

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

如果希望房间前显示自动切换到活动视频源 (例如当源从备用模式唤醒时) 的一个"市/站"控制台，则必须满足某些条件。 此功能是可选的，但受 Microsoft Teams 会议室的支持，但基础硬件支持该功能。 用作房间前显示器的消费者电视需要支持 HDMI 的 CEC (CEC) 功能。  根据所选的扩展坞或主机 (可能不支持 CEC，请参阅制造商支持文档) ，需要来自 Crestron 的 [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) 或 Extron 的 [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) 等控制器才能启用所需行为。

此外，用作房间显示正面的消费者电视可能会导致软件Microsoft Teams 会议室问题。 这是因为备用模式的实现不一致、活动的视频源选择，以及将出错的 EDID 信息Microsoft Teams 会议室设备。 已知症状是房间显示器前面的黑色/灰色屏幕，或者主机在Microsoft Teams 会议室后无响应。  如果在使用使用者电视时遇到问题，建议从 FSR 视频产品组安装可配置的 EDID 控制器或 EDID 模拟器，例如来自 Crestron 的[HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E)或[DR-EDID Emulator。](https://fsrinc.com/fsr-products/product/dr-edid-manager-learner/category_pathway-143)

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
