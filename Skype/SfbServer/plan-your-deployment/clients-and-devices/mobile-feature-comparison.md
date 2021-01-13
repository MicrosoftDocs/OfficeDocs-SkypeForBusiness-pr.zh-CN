---
title: Skype for Business 的移动客户端功能比较
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b2c950c9-76a5-400a-b146-9b1a22790c12
description: 摘要：在规划 Skype for Business Server 时查看移动客户端的功能支持。
ms.openlocfilehash: cdd6e5d5afc95fe6488ee89ed96739963b5f5ac0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825992"
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Skype for Business 的移动客户端功能比较
 
**摘要：** 在规划 Skype for Business Server 时查看对移动客户端的功能支持。
  
本文将 Skype for Business 移动客户端和 Skype for Business 桌面客户端之间的特性和功能分为以下几类：
  
- 登录、推送通知和常规功能
    
- 增强状态
    
- 联系人和联系人组
    
- 即时消息 (IM)
    
- Skype for Business 到 Skype for Business 音频和视频
    
- 会议
    
- 电话
    
- 外部用户
    
- 存档与合规性
    
-  新式验证
    
下表列出了 Skype for Business Server 本地部署中 Skype for Business 用户可用的功能。 Skype for Business Online 和 Microsoft 365 或 Office 365 用户也可使用相同功能，除非表脚注中另有说明。
  
> [!NOTE]
> 有关最终用户的联机帮助和资源，请参阅["发现 Skype for Business"。](https://go.microsoft.com/fwlink/p/?LinkId=528686) 
  
> [!NOTE]
> 若要比较其他 Skype for Business 客户端中提供的功能，请参阅 [Skype for Business 的桌面客户端功能比较](desktop-feature-comparison.md)。 

> [!NOTE]
> SKYPE (Server 2019 中不再提供对) 移动客户端的 MCX 移动服务支持。 所有当前的 Skype for Business 移动客户端已使用统一通信 Web API (UCWA) 来支持即时消息 (IM) 、状态和联系人。 使用 MCX 的旧客户端的用户将需要升级到当前客户端。
  
## <a name="sign-in-push-notifications-and-general-features"></a>登录、推送通知和常规功能

 
 | 功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business 会话保持登录状态  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|
|支持推送通知  <br/> |&#x2714; &#x2778; |&#x2714;|&#x2714; &#x2779; |&#x2714; &#x2779; |
|可在同一设备上缓存多个用户的帐户信息  <br/> |&#x2714;||||
|屏幕阅读器/语音播放  <br/> |&#x2714;|&#x2714; &#x2777;           英语  <br/> |&#x2714;|&#x2714;|
|使用外部键盘实现辅助功能  <br/> |&#x2714;||&#x2714;|&#x2714;|
|Microsoft 客户体验改善计划支持  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; Windows Phone 上，Skype for Business 会在一段时间不活动后自动注销，如下所示：
  
- 如果用户已启用推送通知，Skype for Business 在 10 天不活动后注销。
    
- 如果用户未启用推送通知，Skype for Business 在用户离开应用后即会退出。
    
在 iOS 设备上，由于网络连接中断或其他问题，移动客户端在 10 天内未与服务器联系后，Skype for Business 将自动退出。
  
 &#x2777;应用内。
  
 &#x2778;在后台运行时，通知可用。
 
 &#x2779; Google/Android/GCNS 和 Apple/APNS 移动通知服务均使用 HTTPS/TLS 加密传递通知。 通知有效负载在通知提供程序处理时以纯文本处理。
 
-   Skype for Business for Android 接收简单通知 (GCNS) 无客户数据。
-   Skype for Business for iOS (通过 APNS) 发送的通知，其中可能包含呼叫或邮件的客户数据。
 
  
## <a name="enhanced-presence-support"></a>增强状态支持


 | 功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|发布和查看状态  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|根据日历闲/忙信息查看状态  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|查看状态注释和外出消息  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|添加自定义位置  <br/> |&#x2714;||||
|添加自定义注释  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|根据日历闲/忙信息发布状态  <br/> |&#x2714; &#x2776; ||||
|设置手动状态 (如忙碌、请勿打扰等)   <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; Skype for Business 移动客户端不会基于用户的忙/闲日历信息更新用户状态。 如果移动客户端用户还登录到 Skype for Business 桌面客户端，桌面客户端将基于用户的忙/闲日历信息更新用户状态。 如果用户仅登录到移动客户端，则用户状态不会基于忙/闲日历信息进行更新。
  
## <a name="contacts-and-contact-groups-support"></a>联系人和联系人组支持


 | 功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|查看联系人列表  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|查看联系人组  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|查看常用联系人组  <br/> |&#x2714;||||
|修改联系人列表  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|标记状态更改警报的联系人  <br/> |&#x2714;||||
|控制隐私关系  <br/> |&#x2714;||||
|搜索企业通讯簿  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|搜索联系人列表  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|管理联系人组  <br/> |&#x2714;|||&#x2714;|
|扩展通讯组  <br/> |&#x2714;|&#x2714;||&#x2714;|
|搜索响应组  <br/> |&#x2714; &#x2776; |&#x2714;||&#x2714;|
|显示或隐藏联系人照片  <br/> |&#x2714;|&#x2714;|||
|将联系人固定到主屏幕  <br/> ||&#x2714;|||
   
 &#x2776; Skype for Business Online 和/或 Microsoft 365 或 Office 365 用户不可用。
  
## <a name="instant-messaging-support"></a>即时消息支持


 | 功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|与联系人 (即时消息) 即时消息  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|参与多方 IM  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|从对话窗口中邀请其他人  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|显示当前对话  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|在多个 IM 对话之间进行导航  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|在 Exchange 中自动记录 IM 对话  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|以电子邮件的形式发送 IM 对话  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|向联系人发送电子邮件  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|查看错过的 IM 邀请  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|收到传入 IM 时振动  <br/> ||&#x2714; &#x2776; |&#x2714;|&#x2714;|
   
 &#x2776;即使 IM 对话中的当前消息显示，此设备每次收到 IM 时都会振动
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Skype for Business 到 Skype for Business 音频和视频


 | 功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business 到 Skype for Business 语音  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Skype for Business 到 Skype for Business 视频  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
> [!NOTE]
> 移动设备上的视频默认需要 WiFi 连接。 
  
## <a name="conferencing-support"></a>会议支持


 | 功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|单击会议提醒中的链接以加入视频或 VoIP 会议  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|参与多方 IM  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|使用电话拨出式会议（服务器呼叫移动设备）  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|使用电话拨入式音频会议  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|观看会议视频  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|查看多方视频 (库视图)   <br/> |&#x2714;||||
|在会议厅中等待  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|使用会议中演示者控件  <br/> |&#x2714;||||
|访问音频会议的详细会议名单  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|访问 IM 会议的详细会议名单  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|共享桌面或程序  <br/> |&#x2714;||||
|通过 VbSS 或 RDP (查看共享桌面或)   <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|查看共享 PowerPoint 文件  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777;&#x2778; |&#x2714; &#x2777; &#x2778;|
|上载和显示 PowerPoint 文件  <br/> |&#x2714;||&#x2714; &#x2777; |&#x2714; &#x2777; |
|使用会议 (白板、投票、共享文件)   <br/> |&#x2714;||||
|导航您的会议列表  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|即使没有 Skype for Business 帐户，也加入会议  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|查看有关会议参与者详细信息  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|直接从客户端或设备启动与多个参与者的未计划组对话  <br/> |&#x2714;|&#x2714;|&#x2714;||
   
 &#x2776;对于 Microsoft 365 或 Office 365 用户，此功能企业语音 E5 许可证的一部分。
  
 &#x2777;需要 WiFi 连接。
 
 &#x2778;不支持在 PowerPoint 演示文稿中查看嵌入的视频。
  
## <a name="telephony-support"></a>电话支持


 | 功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|在 Skype for Business 中，点击呼叫图标以呼叫联系人  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|转接呼叫  <br/> |&#x2714;|&#x2714;|&#x2714;||
|咨询转接  <br/> |&#x2714; &#x2778; ||||
|管理呼叫转接  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|
|管理团队呼叫设置  <br/> |&#x2714; &#x2776; ||||
|管理代理  <br/> |&#x2714; &#x2776; ||||
|向响应组发起呼叫  <br/> |&#x2714; &#x2776; ||||
|支持紧急服务  <br/> |&#x2714; &#x2777; ||||
|代表其他联系人发起呼叫（经理/代理方案）  <br/> |&#x2714; &#x2776; ||||
|处理其他联系人的呼叫（如果配置为代理人）  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|使用通过工位电话呼叫  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
|访问语音邮件  <br/> |&#x2714;|&#x2714;|&#x2714;||
|在 Skype for Business 中使用小键盘  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
   
 &#x2776; Skype for Business Online 和/或 Office 365 E5 用户，以及位于 Skype for Business Server 或 Lync Server 2013 上且启用了 企业语音 的用户。
  
 &#x2777;对于 Skype for Business Online 和/或 Microsoft 365 或 Office 365 用户，Microsoft 合作伙伴支持此功能。
  
 &#x2778; Windows 桌面客户端。
  
## <a name="external-user-support"></a>外部用户支持


 | 功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|启动与公共联系人的 IM  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|启动与联盟联系人的 IM  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|进行与外部用户的双方呼叫  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|进行与外部用户的多方呼叫  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|使用通过工号呼叫通过拨打其已发布的工作电话号码来联系其移动电话上的联盟&#x2776;            <br/> ||&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;默认情况下，为联盟用户分配外部联系人私人关系。 要能够通过呼叫联盟联系人的已发布工作号码，可以在移动电话上联系联盟联系人，该联盟联系人必须手动分配给您"同事"私人关系。
  
## <a name="address-book-integration"></a>通讯簿集成


 | 功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|呼叫设备通讯簿联系人  <br/> ||&#x2714;|&#x2714;|&#x2714;|
|直接从设备通讯簿向联系人进行 Skype for Business 呼叫  <br/> ||||&#x2714;|
   
## <a name="archiving-and-compliance-support"></a>存档和合规性支持


 | 功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|提供客户端存档  <br/> |&#x2714;||||
|提供客户端记录  <br/> |&#x2714; &#x2776; ||||
   
 &#x2776; Skype for Business Online 和/或 Microsoft 365 或 Office 365 用户不可用。
  
## <a name="modern-authentication"></a>新式验证

此表涵盖需要支持新式验证的功能。
  
新式身份验证还需要在 Skype for Business 拓扑中介绍 [的拓扑，该拓扑受新式验证支持](../../plan-your-deployment/modern-authentication/topologies-supported.md)。
  

 | 功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|新式验证  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|多重身份验证  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|基于证书的身份验证  <br/> |&#x2714; (已加入域的设备)   <br/> ||&#x2714;|&#x2714;|
|通过 Intune (移动应用程序管理)   <br/> |||&#x2714;|&#x2714;|
   

