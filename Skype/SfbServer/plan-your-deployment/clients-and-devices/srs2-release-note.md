---
title: 发行说明
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本文讨论中 Skype 会议室系统 v2 累积改进。
ms.openlocfilehash: 7eb6eb3c9bcd2cbbbe72a6fc96d619303216cd37
ms.sourcegitcommit: e53749714dcde9f7b184d5ef554bffbc77f54267
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2019
ms.locfileid: "28729398"
---
# <a name="release-notes"></a>发行说明 

本文讨论中 Skype 会议室系统 v2 累积改进。


##  <a name="version-history"></a>版本历史记录

| 发行版 | 发布到 <br>Microsoft 存储 | 
| ---     | ---  |
| 4.0.64.0 | 2018 年 12 月 14 日   |
| 4.0.51.0 | 11/17/2018   | 
| 4.0.31.0 | 10/16/2018   | 
| 4.0.27.0 |  10/1/2018    | 
| 4.0.19.0 |  08/31/2018    |   
| 4.0.18.0 |  08/27/2018    |   
| 4.0.8.0 |  07/06/2018    |   
| 3.1.115.0|  06/18/2018    |
| 3.1.113.0|  06/13/2018    |   
| 3.1.112.0|  06/05/2018    |   
| 3.1.104.0|  04/16/2018    |            
| 3.1.100.0|  03/16/2018    |            
| 3.1.99.0 | 3/14/2018      |  
| 3.1.98.0    | 3/8/2018    |   
|  3.0.16.0    |  11/27/2017   |
| 3.0.15.0 | 10/3/2017  |            
| 3.0.12.0 |  9/1/2017  |            
| 3.0.8.0 | 11/16/2017 | 
| 3.0.6.0 | 11/16/2017 | 
| 2.0.2.0  | 03/15/2017 | 
| RTM (1.0.8) | 12/7/2016  | 


## <a name="skype-room-systems-v2-feature-introduction-and-issue-resolution"></a>Skype 会议室系统 v2 功能简介和解决问题

### <a name="40640-12142018"></a>4.0.64.0 (14/12/2018)
此更新中引入了：
- 在这两个前端的空间 （） 双屏幕会议室系统上显示上显示内容
- 主题和前端的聊天室的用户界面改进
- TLS 1.2 客户端支持。 对于在内部部署客户通讯 over TLS 1.2 启用 Skype 会议室系统 V2 需要 Skype 业务 2015 Cummulative 更新 9 (CU9) 或 Skype Buisness 2019 Cummulative 更新 1 (CU1)。

### <a name="40510-11172018"></a>4.0.51.0 (11/17/2018)
此更新中引入了：
- 双显示 （前端的房间） 支持团队会议 

### <a name="40310-10162018"></a>4.0.31.0 (16/10/2018)
此更新中引入了：
- 质量和可靠性修补程序 

### <a name="40270-1012018"></a>4.0.27.0 (1/10/2018)
此更新中引入了： 
- 准备更高版本的 Windows 10 版本 1803年升级 SRSv2 应用程序所需的代码更改
- 修复与本地化 Eula-专门挪威语-这将阻止执行超出 EULA OOBE 安装窗口的格式的问题
- 需要进行 Skype 会议室系统 v2 应用程序在旧式 Lync 会议室系统上运行的代码更改。 查看更多[此处](https://aka.ms/lrsupgrade)。
 

### <a name="40190-8312018"></a>4.0.19.0 (8/31/2018)
此更新中引入了： 
- 修补程序 Crestron 应用程序未启动其通常会访问通过按 Crestron SR 设备上的应用程序按钮。 SRSv2 4.0.19.0 安装后，需要的应用程序重新启动 

### <a name="40180-08272018"></a>4.0.18.0 (08/27/2018)
此更新中引入了： 
- 在工作组模式下 （相当于 Skype 中的"提供反馈"业务模式） 的"报告问题"功能改进
- 启用功能回退到从 Skype 团队对 SIP 呼叫业务模式
- 辅助功能改进 （讲述人、 放大镜）
- 自动重新启动应用程序时所需已应用了 XML 设置更改之后
- Miscellaneous 修补程序

### <a name="4080-07062018"></a>4.0.8.0 (06/07/2018)
此更新中引入了： 
- 此更新使业务*和*团队会议支持会议室系统设备上两个 Skype。  团队已禁用默认情况下应用更新后。  管理员可以在设备设置中或通过远程 xml 推送本地启用团队。

### <a name="311150-06182018"></a>3.1.115.0 (06/18/2018)
此更新中引入了： 
- 在某些系统观察到的应用程序启动期间的地址错误修复。

### <a name="311130-06132018"></a>3.1.113.0 (13/06/2018)
此更新中引入了： 
- 更改能够更加灵活地启用 Microsoft 管理 Windows 更新。
- 最终用户体验不变。

### <a name="311120-06052018"></a>3.1.112.0 (05/06/2018)
此更新中引入了： 
- 固定到问题观察到的连接到两个前端的聊天室显示和视频的基于 Surface Pro 2017年的设备上接收地址控制台响应速度
- 自动的检查以确保系统正在运行最新设置的脚本。

### <a name="311040-04162018"></a>3.1.104.0 (16/04/2018)
此更新中引入了： 
- 修复以提高 OSK （屏幕键盘） 窗口 10 版本 1709年基于系统中的行为
- 改进将来的操作系统更新做好准备

### <a name="311000-03162018"></a>3.1.100.0 (16/03/2018)
此更新中引入了：  
- 进行了更新以改进遥测的应用程序。

### <a name="31990-03142018"></a>3.1.99.0 (14/03/2018)
此更新中引入了： 
- 可能出现的问题，其中间歇性与会问题的修补程序。
- 解决了已知导致设备"挂起"体验的问题。

### <a name="31980--382018"></a>3.1.98.0 (8/3/2018)
此更新中引入了： 
- Bug/崩溃修补程序，来提高稳定性
- 大小可变的控制台支持
- 卸载 （其他媒体白） 的外围音频处理
- 优化，这将使 IT 专业人员来构建自己动手图像与 Windows 10 版本 1709 年 1 月更新和更高版本。  

<!--### 3.1.97.0 (00/00/0000)
Introduced in this update:  
- Support for [Lenovo Hub 500](https://www3.lenovo.com/us/en/hub500)  hardware only.  -->


### <a name="30160-11272017"></a>3.0.16.0 (11/27/2017)
此更新中引入了：  
- 具有"提供反馈"功能解决的问题。

### <a name="30150-1032017"></a>3.0.15.0 (3/10/2017)
此更新中引入了： 
- [Polycom MSR](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl)系列支持停靠硬件
- [Logitech Brio](https://www.logitech.com/en-us/product/brio)支持
- 解决的问题，其中显示 （控制台和前端的聊天室） 无法在聊天室中没有任何活动时进入休眠模式。


### <a name="30120-912017"></a>3.0.12.0 (1/9/2017)
此更新中引入了：   
- Surface Pro (2017) 平版电脑上运行  
- 支持 Windows 10 企业 Creator 更新 （英语、 生成 1703年）    
- 支持[Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system)停靠硬件    
- 对环境控件 (Crestron) 的 OEM 支持
    
从 Skype 会议室系统 v2 版本 3.0.12.0 （更新 3） 不再支持 64 位版本的 Windows 10 企业周年日 edition （英语、 版本 1607年）。 

### <a name="3080-842017"></a>3.0.8.0 (4/8/2017) 
此更新中引入了： 
- 解析观察时搜索的联合用户通过参与者搜索字段中的问题。 此修补程序之前外部联盟用户的搜索结果可能不具有正确地解析并且改为返回正确结果。 

### <a name="3060-772017"></a>3.0.6.0 (7/7/2017) 
此更新中引入了： 
- （对于旧系统奇偶校验） 的双屏幕支持   
- Themability （内置主题和能够设置自定义主题） 
- 提供反馈的公共生成的功能     
- 改进了的遥测周围会议加入可靠性     
- 报告的其他 OMS     
- IT 管理员来远程配置设备的功能<!--  - Front-of-Room UX shows room details pre-meeting U2  --> 


### <a name="2020-03152017"></a>2.0.2.0 (03/15/2017)
此更新中引入了： 
- 在应用程序用户选择会议室内音频和视频 USB 设备
- 集成会议室控制台状态报告的客户使用 Microsoft 操作管理套件 （请参阅[使用 OMS 的规划 Skype 会议室系统 v2 管理](oms-management.md)） 

### <a name="release-to-market--1272016"></a>版本上市 (7/12/2016)
**功能：** 

 **为 Skype for Business 而构建**
  
- 一键式加入 Skype 会议    
- 为配有满屏高清视频和高清宽带音频的会议室优化的 Skype 会议体验
- 所有参与者均可使用所选设备从任意位置连接到 Skype 会议
- 从目录中（在此可立即看到用户的状态）或通过电话呼叫邀请用户
- 支持 Skype for Business PSTN 会议和 PSTN 呼叫，以替代会议室中的单独会议电话
    
  **转换任何会议室**
  
- 专用的 Skype 会议应用针对桌面中心触摸式控制器和会议室前方的大型显示屏进行了优化
- 重用会议室显示屏和投影仪的现有投资
- 适用于各种类型的会议室，从小型到大型会议室
- 经认证的 Skype for Business 音频和视频设备可用于各种规模的会议室
- 内置的有线采集可用于将桌面共享投影到会议室和 Skype 会议
    
  **易于部署、便于管理**
  
- 常开式设备会在检测到会议室中有人时自动唤醒显示屏
- UWP（通用 Windows 平台）Skype 会议应用的部署和更新都非常简单
- Windows AppLocker 可将设备锁定至 Skype 会议应用
- 通过 Intune 和 SCCM (MDM) 作为 Windows 10 企业版设备来监控和管理
- 企业级可靠性
- 由于最终用户很熟悉 Skype 用户界面，因此只需进行少量培训
- 在 Surface Pro 4 平板电脑上运行
 

<a name="See"> </a>  
## <a name="see-also"></a>另请参阅

[Skype 会议室系统版本 2 帮助](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[业务环境准备您的 Skype](srs-v2-prep.md)

[Skype 会议室系统 v2 当前分支版本的支持](srs2-lifecycle-support.md)

[有关 Skype 会议室系统 v2 的已知的问题](../../manage/skype-room-systems-v2/known-issues.md)

[Plan for Skype Room Systems v2](skype-room-systems-v2-0.md)

[管理 Skype 会议室系统 v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)
