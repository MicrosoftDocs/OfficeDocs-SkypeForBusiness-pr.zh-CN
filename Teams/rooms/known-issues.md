---
title: 已知问题
ms.author: czawideh
author: cazawideh
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
description: 了解适用于 Microsoft Teams 会议室的已知问题，包括更新、用户界面、硬件、限制和预期行为。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5322020d37e3251aa54a20afecba353dd6335f55
ms.sourcegitcommit: e9b0a274fdfee3d5bc8211cb099155546b281fe0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2022
ms.locfileid: "62926315"
---
# <a name="known-issues"></a>已知问题 
 
本文按功能区域列出了 Microsoft Teams 会议室的已知问题。
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>更新 

| 问题标题 |  行为\/症状 | 已知解决方法 | 知识库文章 |
|  ---        |      ---             |   ---            | --- |
| 未检测到边缘时，白板/内容相机无法增强内容 | 更新到 4.11.12.0 后，当内容相机视图中没有白板边缘时，相机不会增强/覆盖相机视图中的所有内容。| 修复后将包含在将来的版本中，以增强相机视图中的所有内容。 解决方法是，在白板的框中应用的刷带可用于临时提供内容相机可用于聚焦和增强内容的边缘。 | 无 |
| Edge 浏览器自动启动 | 在设备启动时，在内部版本 97.0.1072.62 之前，Edge 浏览器会自动随 Microsoft Teams Room 应用一起启动。 | 这应会自动解决，无需用户交互，在 2022 年 1 月 17 日（星期一）或之前。 如果需要更快的解决方法：当 Edge 与 Microsoft Teams 一起启动时，请访问 URL edge://settings/help，更新应会自动下载并应用。 应用完更新后，在浏览器中选择"重启"。 关闭Azure IoT Edge，重新启动系统，问题应得到解决。 | 无 |
| 拆分库参与者视频   |  如果会议中没有包含超过 9 个远程参与者的共享内容，并且会议采用双"会议室前端"显示模式，则"会议室前"显示器上具有自预览的 1 个视频可能会显示为音频。 此外，音频参与者数少于在双"会议室前端"显示器上显示的实际音频参与者数。 | 问题将在将来的更新中解决。 | 无 |
| 应用程序未启动 |  更新到应用程序版本 4.4.41.0 后，系统会启动到黑屏，或者几分钟后转到登录屏幕。 | 请按照更新到 [Microsoft Teams 会议室 4.4.41.0](/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update) 后应用程序无法启动中的步骤来解决此问题。  | 无 |
|  内容共享后会议音量低         |   Microsoft Teams 会议室 20H2 Windows 10的设备在通过室内 HDMI 共享内容后减少了媒体和会议音量。 这是由 20H2 Windows 10音频问题导致的。 | 此问题的修补程序在应用程序版本 [4.9.12.0 中提供](/microsoftteams/rooms/rooms-release-note#49120-7282021)。 | 无 |
|  应用已过期         |    Microsoft Teams 会议室控制台显示“系统配置已过期”错误。                |   [使用 Microsoft Teams 会议室恢复工具](recovery-tool.md)             |  无 |
|  设备已更新为不支持的版本Windows 10   |    Windows 10从版本 1803 更新到版本 1809，但不支持。 支持的版本为 1903。 |   如果 [DeferFeatureUpdatesPeriodinDays 设置的组](/windows/deployment/update/waas-configure-wufb) 策略或 MDM 设置（允许您将功能更新延迟指定的天数）设置为最长 365 天，则可能会发生这种情况。 <br><br> Windows 10版本 1809 不受支持，Microsoft Teams 会议室版本 1903。 但是，截至 2020 年 3 月 27 日，版本 1809 已超过 365 天。 如果未更改此设置，Windows安装版本 1809，这可能会导致Microsoft Teams 会议室。<br><br>若要避免这种情况， **请删除** 用于延迟更新的任何组策略或 MDM 设置。 这样Windows更新到最新的受支持 OS 版本。 <br><br>**重要提示：** 必须删除组策略或 **MDM 设置 (** 未配置) 不设置为 **0**。 如果策略设置为 0，Windows可能不支持的最新可用版本。 |  无 |



<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>用户界面 

| 问题标题 |  行为\/症状 | 已知解决方法 | 知识库文章 |
|  ---        |      ---             |   ---            | --- |
|虚拟键盘缺失   | 当你需要在 Microsoft Teams 会议室中输入信息时，不显示虚拟键盘。 此问题出现在版本 1903 Windows 10 1903 中。 | 通过更新为基于 x64 的系统安装 2020-04 Windows 10累积更新，版本 1903 Windows更新。  | 无 | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>硬件

| 问题标题 |  行为\/症状 | 已知解决方法 | 知识库文章 |
|  ---        |      ---             |   ---            |   --- |
| 未检测到监视器 | 在 Surface Pro（2017 机型）设备上运行 Microsoft Teams 会议室时，检测不到监视器。 |  按住 Surface Pro 电源按钮 20 秒或更长时间。 执行此操作时，设备将重启并清除图形缓存。 |[KB4055681](https://support.microsoft.com/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>限制和预期行为

***

前行在"会议室前"显示屏的布局选取器中标记为"预览"。 将来将添加更多功能和改进。 以下限制将解决发布后问题：

- 前行布局在"会议室前"单一显示器上最多显示 4 个视频参与者。 它最多在双前端会议室上显示 9 个视频。 这些参与者是从最后一位活动演讲人中选出的。

- 前行需要 1080p 显示器，缩放比例为 100%。 如果"会议室前端"显示屏上的字号太小或过大，而会议室需要，请参阅更改"房间前"[](rooms-operations.md#change-scale-and-resolution)的缩放比例和分辨率以调整显示设置。

***

Microsoft Teams 会议室不支持 HDCP 输入，已发现它会导致 HDMI 采集功能（视频、音频）出现问题。 请确保连接到 Microsoft Teams 会议室的交换机禁用了 HDCP 选项。 

***

如果希望会议室前显示器自动切换到活动视频源（例如，一个一台"一部"，当源从备用模式唤醒时，必须满足某些条件。 此功能是可选的，但受 Microsoft Teams 会议室的支持，但基础硬件支持该功能。 用作房间前显示器的消费者电视需要支持 HDMI 的 CEC (CEC) 功能。  可能需要一个控制器（如来自 Crestron 的 [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) 或 [Extron 的 Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) ）来启用所需行为，具体取决于所选的扩展坞或主机。 请参阅制造商的支持文档，确认扩展坞或主机支持 CEC。

此外，用作房间显示正面的消费者电视可能会导致软件Microsoft Teams 会议室问题。 这是因为备用模式的实现不一致、活动的视频源选择，以及将出错的 EDID 信息Microsoft Teams 会议室设备。 已知症状是房间显示器正面出现黑色/灰色屏幕，或者Microsoft Teams 会议室从待机状态唤醒后无响应。  如果在使用使用者电视时遇到问题，我们建议安装可配置的 EDID 控制器或 EDID 模拟器，例如来自 Crestron 的 [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E)，或者来自 FSR 视频产品组的 [DR-EDID Emulator](https://fsrinc.com/fsr-products/product/dr-edid-manager-learner/category_pathway-143)。

***

始终使用 1 Gbps 有线网络连接，以确保你拥有所需的带宽。 

***

如果Microsoft Teams 会议室设备失去对域的信任，将无法在设备上进行身份验证并打开设置。 例如，如果在域加入Microsoft Teams 会议室删除域，信任将丢失。 解决方法是使用本地管理员帐户登录。 
***
Microsoft Teams 会议室是一个多窗口应用程序，要求房间前显示器连接到设备的 HDMI 端口，使应用正常运行。 如果你正在测试并且尚未购买显示器，请确保你已连接 HDMI 显示器或使用虚拟 HDMI 插头。
***
<a name="See"> </a>  
## <a name="see-also"></a>另请参阅

[Microsoft Teams 会议室帮助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[管理 Microsoft Teams 会议室](rooms-manage.md)
