---
title: 已知问题
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection: M365-voice
description: 本文按功能区域介绍 Microsoft Teams 会议室的已知问题。
ms.openlocfilehash: 6d924559f19aadec0d6d5634a000d7d10e1c2f58
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "36428030"
---
# <a name="known-issues"></a>已知问题 
 
本文按功能区域列出了 Microsoft Teams 会议室的已知问题。
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>更新 

| 问题标题 |  行为\/症状 | 已知解决方法 | 知识库文章 |
|  ---        |      ---             |   ---            | --- |
|  应用已过期         |    Microsoft Teams 会议室控制台显示“系统配置已过期”错误。                |   [使用 Microsoft Teams 会议室恢复工具](recovery-tool.md)             |  无 |


<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>用户界面 

| 问题标题 |  行为\/症状 | 已知解决方法 | 知识库文章 |
|  ---        |      ---             |   ---            | --- |
|虚拟键盘缺失   | 当你需要在 Microsoft Teams 会议室中输入信息时，不显示虚拟键盘。 在运行 Microsoft Teams 会议室的 Surface Pro 4 上安装 Windows 10 创意者更新（版本 1703）后，会出现此问题。 | 要解决此问题，请手动打开虚拟键盘。 为此，请按照下列步骤操作：<br><br> **1.** 点击并按住任务栏，然后点击“显示触摸键盘”按钮****。 键盘图标应出现在任务栏的右侧。 <br><br> **2.** 点击键盘图标以打开虚拟键盘。 | [KB4037694](https://support.microsoft.com/en-us/help/4037694/virtual-keyboard-missing-in-skype-room-systems-v2) | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>硬件

| 问题标题 |  行为\/症状 | 已知解决方法 | 知识库文章 |
|  ---        |      ---             |   ---            |   --- |
| 未检测到监视器 | 在 Surface Pro（2017 机型）设备上运行 Microsoft Teams 会议室时，检测不到监视器。 |  按住 Surface Pro 电源按钮 20 秒或更长时间。 执行此操作时，设备将重启并清除图形缓存。 |[KB4055681](https://support.microsoft.com/en-us/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>限制和预期行为

***

Microsoft Teams 会议室不支持 HDCP 输入，已发现它会导致 HDMI 采集功能（视频、音频）出现问题。 请确保连接到 Microsoft Teams 会议室的交换机禁用了 HDCP 选项。 

***

用作室内显示器正面的消费者电视必须支持 HDMI 的 "消费者电子设备" (CEC) 功能, 才能从待机模式自动切换到活动视频源。 并非所有电视都支持此功能。

***

始终使用有线1至 Gbps 网络连接, 确保您有所需的带宽。 

***

如果你的 Microsoft 团队聊天室设备失去了与域的信任, 你将无法在设备上进行身份验证并打开 "设置"。 例如, 如果在域加入域后从域中删除 Microsoft 团队聊天室, 则信任将丢失。 解决方法是使用本地管理员帐户登录。 
***
自 Microsoft Teams 会议室 3.0.12.0 版起，不再支持 64 位版本的 Windows 10 企业版 Anniversary Edition（英语版本 1607）。 
***
Microsoft 团队会议室是一个多窗口应用程序, 需要将房间内的正面显示连接到设备的 HDMI 端口, 才能使应用正常运行。 请确保你已连接 HDMI 显示器, 或者使用虚拟 HDMI 插头 (如果你正在测试, 并且尚未购买显示器)。
***
<a name="See"> </a>  
## <a name="see-also"></a>另请参阅

[Microsoft Teams 会议室帮助](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[管理 Microsoft Teams 会议室](skype-room-systems-v2.md)
