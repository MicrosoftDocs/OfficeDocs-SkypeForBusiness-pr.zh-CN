---
title: 已知的问题
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本文讨论有关 Skype 会议室系统 v2，按功能区域的已知的问题。
ms.openlocfilehash: 2fde12d616260963dc342df2d9cef94acf616756
ms.sourcegitcommit: dc7a7da270121c3702f38614158c9067ad38f12a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2018
ms.locfileid: "19881540"
---
# <a name="known-issues"></a>已知的问题 
 
本文列出了 Skype 会议室系统 v2，按功能区域的已知的问题。
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>更新 

| 问题标题 |  行为\/症状 | 已知的解决方法 | 知识库文章 |
|  ---        |      ---             |   ---            | --- |
|  过期的应用程序         |    Skype 会议室系统 v2 控制台将显示"系统配置过期"错误。                |   [使用 Skype 会议室系统 v2 恢复工具](recovery-tool.md)             |  无 |


<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>用户界面 

| 问题标题 |  行为\/症状 | 已知的解决方法 | 知识库文章 |
|  ---        |      ---             |   ---            | --- |
|虚拟键盘缺少   | 当您需要在 Skype 会议室系统 v2 中输入信息时，不显示虚拟键盘。 在其运行 Skype 会议室系统 v2 Surface Pro 4 上安装 Windows 10 创建者更新 （版本 1703年） 后，将发生此问题。 | 若要解决此问题，请手动打开虚拟键盘。 若要执行此操作，请按照以下步骤：<br><br> **1。** 点击和保留任务栏，然后点击**显示触摸键盘**按钮。 键盘图标应显示在任务条形图的右侧。 <br><br> **2。** 点击键盘图标以打开虚拟键盘。 | [KB4037694](https://support.microsoft.com/en-us/help/4037694/virtual-keyboard-missing-in-skype-room-systems-v2) | 
   

<a name="Hardware"> </a>  
## <a name="hardware"></a>硬件

| 问题标题 |  行为\/症状 | 已知的解决方法 | 知识库文章 |
|  ---        |      ---             |   ---            |   --- |
| 未检测到的监视器 | 当您运行 Surface Pro (模型 2017) 设备上的 Skype 会议室系统 v2 时，监视器未检测到。 |  20 个或多个秒钟按住 Surface Pro 电源按钮。 这样做，设备会重新启动，并清除图形缓存。 |[KB4055681](https://support.microsoft.com/en-us/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 
          
<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>限制和预期的行为
***
V2 不支持 HDCP 输入，观察到与 HDMI 会导致问题的 Skype 会议室系统接收功能 （视频、 音频）。 注意确保交换机连接到 Skype 会议室系统 v2 已关闭的 HDCP 选项。 
***
用作会议室前端显示屏的消费者电视需要支持/启用 HDMI 的 Consumer Electronics Control (CEC) 功能，以使其可以自动从待机模式切换至活动视频源。 并非所有电视都支持此功能。 
***
始终使用有线 1 Gbps 网络连接以确保您将具有所需的带宽。 
***
如果 Skype 会议室系统 v2 设备丢失与 （例如，如果您 Skype 会议室系统 v2 从域中删除后加入域） 域的信任，您将无法进行身份验证到设备，然后打开设置。 解决方法是使用本地管理员帐户登录。 
***
从 Skype 会议室系统 v2 版本 3.0.12.0 不再支持 64 位版本的 Windows 10 企业周年日 edition （英语、 版本 1607年）。 
***

<a name="See"> </a>  
## <a name="see-also"></a>另请参阅

[Skype 会议室系统版本 2 帮助](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[管理 Skype 会议室系统 v2](skype-room-systems-v2.md)