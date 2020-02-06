---
title: Skype for business 的移动客户端功能比较
ms.author: v-lanac
author: lanachin
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
description: 摘要：在规划 Skype for business 服务器时查看移动客户端的功能支持。
ms.openlocfilehash: 85d193fba624a7895b975bb30bf6392e9fc8c563
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803542"
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Skype for business 的移动客户端功能比较
 
**摘要：** 在规划 Skype for business 服务器时查看移动客户端的功能支持。
  
本文将比较 Skype for Business 移动客户端和 Skype for business 桌面客户端之间的功能和功能，包括以下类别：
  
- 登录、推送通知和常规功能
    
- 增强状态
    
- 联系人和联系人组
    
- 即时消息 (IM)
    
- Skype for business 到 Skype for business 音频和视频
    
- 会议
    
- 电话
    
- 外部用户
    
- 存档与合规性
    
-  新式验证
    
下表列出了 Skype for business 服务器的本地部署中的 Skype for business 用户可用的功能。 Skype for Business Online 和 Microsoft Office 365 用户也可以使用相同的功能，除非表脚注中另有指示。
  
> [!NOTE]
> 有关最终用户的联机帮助和资源，请参阅[发现 Skype for](https://go.microsoft.com/fwlink/p/?LinkId=528686)business。 
  
> [!NOTE]
> 若要比较其他 Skype for Business 客户端中的可用功能，请参阅[Skype for business 的桌面客户端功能比较](desktop-feature-comparison.md)。 

> [!NOTE]
> 在 Skype for Business Server 2019 中，MCX （移动服务）对旧式移动客户端的支持不再可用。 所有当前 Skype for business 移动客户端都已使用统一通信 Web API （UCWA）来支持即时消息（IM）、状态和联系人。 具有使用 MCX 的旧客户端的用户将需要升级到当前客户端。
  
## <a name="sign-in-push-notifications-and-general-features"></a>登录、推送通知和常规功能

 
 | 特性/功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business 会话保持登录状态  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|
|支持推送通知  <br/> |&#x2714; &#x2778; |&#x2714;|&#x2714; &#x2779; |&#x2714; &#x2779; |
|可在同一设备上缓存多个用户的帐户信息  <br/> |&#x2714;||||
|屏幕阅读器/语音朗读  <br/> |&#x2714;|仅 &#x2714; &#x2777;  英语  <br/> |&#x2714;|&#x2714;|
|使用外部键盘访问辅助功能  <br/> |&#x2714;||&#x2714;|&#x2714;|
|Microsoft 客户体验改善计划支持  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 在 Windows Phone 上 &#x2776;，Skype for Business 将在处于非活动状态一段时间后自动登录，如下所示：
  
- 如果用户已启用推送通知，则 Skype for business 将在处于非活动状态10天后进行注销。
    
- 如果用户未启用推送通知，则当用户离开应用时，Skype for Business 将立即注销。
    
在 iOS 设备上，由于网络连接断开或其他问题，在移动客户端未与服务器联系10天后，Skype for Business 会自动注销。
  
 仅在应用中 &#x2777;。
  
 当应用在后台运行时，&#x2778; 通知可用。
 
 &#x2779; Google/Android/GCNS 和 Apple/APNS 手机通知服务均使用 HTTPS/TLS 加密来传递通知。 通知负载在通知提供程序处理时以纯文本方式处理。
 
-   Android 版 Skype for Business 通过 GCNS 发送简单通知（通过），无客户数据。
-   IOS 版 Skype for Business 通过 APNS 接收通知（通过 APNS 发送），其中可能包括客户数据用于呼叫或消息。
 
  
## <a name="enhanced-presence-support"></a>增强状态支持


 | 特性/功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|发布和查看状态  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|根据日历闲/忙信息查看状态  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|查看状态注释和外出消息  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|添加自定义位置  <br/> |&#x2714;||||
|添加自定义注释  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|根据日历闲/忙信息发布状态   <br/> |&#x2714; &#x2776; ||||
|设置手动状态（如“忙碌”、“请勿打扰”等等）  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; Skype for Business 移动客户端不会根据用户的忙/闲日历信息更新用户的状态。 如果移动客户端用户也登录到 Skype for business 桌面客户端，则桌面客户端会根据用户的忙/闲日历信息更新用户的状态。 如果用户仅登录到移动客户端，则用户的状态不会根据忙/闲日历信息进行更新。
  
## <a name="contacts-and-contact-groups-support"></a>联系人和联系人组支持


 | 特性/功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|查看联系人列表  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|查看联系人组  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|查看常用联系人组  <br/> |&#x2714;||||
|修改联系人列表  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|标记状态更改警报的联系人  <br/> |&#x2714;||||
|控制私人关系  <br/> |&#x2714;||||
|搜索企业通讯簿  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|搜索联系人列表  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|管理联系人组  <br/> |&#x2714;|||&#x2714;|
|展开通讯组  <br/> |&#x2714;|&#x2714;||&#x2714;|
|搜索响应组  <br/> |&#x2714; &#x2776; |&#x2714;||&#x2714;|
|显示或隐藏联系人照片  <br/> |&#x2714;|&#x2714;|||
|将联系人固定到您的主屏幕  <br/> ||&#x2714;|||
   
 &#x2776; Skype for Business Online 和/或 Office 365 用户不可用。
  
## <a name="instant-messaging-support"></a>即时消息支持


 | 特性/功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|启动与联系人的即时消息 (IM)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|参与多方 IM  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|从对话窗口中邀请其他人  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|显示当前对话  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|在多个 IM 对话之间进行导航  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|在 Exchange 中自动记录 IM 对话  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|以电子邮件的形式发送 IM 对话  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|向联系人发送电子邮件  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|查看错过的 IM 邀请  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|收到传入 IM 时振动  <br/> ||&#x2714; &#x2776; |&#x2714;|&#x2714;|
   
 &#x2776; 此设备 vibrates 在每次收到即时消息时，即使即时消息对话中的当前消息显示
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Skype for business 到 Skype for business 音频和视频


 | 特性/功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for business 至 Skype for business 语音  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Skype for business 至 Skype for business 视频  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
> [!NOTE]
> 移动设备上的视频默认需要 WiFi 连接。 
  
## <a name="conferencing-support"></a>会议支持


 | 特性/功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|单击会议提醒中的链接可加入视频或 VoIP 会议  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|参与多方 IM  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|使用电话拨出式会议（服务器呼叫移动设备）  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|使用电话拨入式音频会议  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|观看会议视频  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|查看多方视频（库视图）  <br/> |&#x2714;||||
|在会议厅中等待  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|使用会议中演示者控件  <br/> |&#x2714;||||
|访问音频会议的详细会议名单  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|访问 IM 会议的详细会议名单  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|共享桌面或程序  <br/> |&#x2714;||||
|查看共享的桌面或程序（VbSS 或 RDP）  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|查看共享的 PowerPoint 文件  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777;&#x2778; |&#x2714; &#x2777; &#x2778;|
|上载和演示 PowerPoint 文件  <br/> |&#x2714;||&#x2714; &#x2777; |&#x2714; &#x2777; |
|使用会议工具（使用白板、发起投票、共享文件）  <br/> |&#x2714;||||
|导航您的会议列表  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|即使您没有 Skype for Business 帐户也可加入会议  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|查看有关会议参与者的更多信息  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|直接从您的客户端或设备启动与多个参与者的未计划的组对话   <br/> |&#x2714;|&#x2714;|&#x2714;||
   
 &#x2776; 对于 Office 365 用户，此功能需要企业语音，它是 E5 许可证的一部分。
  
 默认情况下，&#x2777; 需要 WiFi 连接。
 
 不支持在 PowerPoint 演示文稿中查看嵌入视频的 &#x2778;。
  
## <a name="telephony-support"></a>电话支持


 | 特性/功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|在 Skype for Business 中，点击 "呼叫" 图标以呼叫联系人  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|转移来电  <br/> |&#x2714;|&#x2714;|&#x2714;||
|协商转接  <br/> |&#x2714; &#x2778; ||||
|管理呼叫转接  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|
|管理团队呼叫设置  <br/> |&#x2714; &#x2776; ||||
|管理代理人  <br/> |&#x2714; &#x2776; ||||
|向响应组拨打电话  <br/> |&#x2714; &#x2776; ||||
|支持紧急服务  <br/> |&#x2714; &#x2777; ||||
|代表其他联系人拨打电话（经理/代理人方案）  <br/> |&#x2714; &#x2776; ||||
|处理另一个联系人的呼叫（如果已配置为代理人）  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|通过工号拨号  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
|访问语音邮件  <br/> |&#x2714;|&#x2714;|&#x2714;||
|在 Skype for Business 中使用键盘  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
   
 &#x2776; 适用于 Skype for Business Online 和/或 Office 365 E5 用户以及驻留在已启用企业语音的 Skype for business 服务器或 Lync Server 2013 的用户。
  
 &#x2777; Skype for business Online 和/或 Office 365 用户，此功能由 Microsoft 合作伙伴支持。
  
 仅 &#x2778; Windows 桌面客户端。
  
## <a name="external-user-support"></a>外部用户支持


 | 特性/功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|启动与公共联系人的 IM  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|启动与联盟联系人的 IM  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|进行与外部用户的双方呼叫  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|进行与外部用户的多方呼叫  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|通过拨打联盟联系人的已发布工作电话号码，使用 "通过工作电话呼叫" 联系其移动电话 &#x2776;            <br/> ||&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; 默认情况下，将为联盟用户分配外部联系人私人关系。 若要能够通过呼叫联盟联系人的已发布的工作电话号码来通过其移动电话与其取得联系，该联盟联系人必须手动为你分配“同事”私人关系。
  
## <a name="address-book-integration"></a>通讯簿集成


 | 特性/功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|呼叫设备通讯簿联系人  <br/> ||&#x2714;|&#x2714;|&#x2714;|
|直接从设备通讯簿向联系人进行 Skype for Business 呼叫  <br/> ||||&#x2714;|
   
## <a name="archiving-and-compliance-support"></a>存档与合规性支持


 | 特性/功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|提供客户端存档  <br/> |&#x2714;||||
|提供客户端记录  <br/> |&#x2714; &#x2776; ||||
   
 &#x2776; Skype for Business Online 和/或 Office 365 用户不可用。
  
## <a name="modern-authentication"></a>新式身份验证

此表涵盖需要支持新式身份验证的特性。
  
新式验证还要求[使用新式验证支持的 Skype for business 拓扑](../../plan-your-deployment/modern-authentication/topologies-supported.md)中介绍的拓扑。
  

 | 特性/功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|新式验证   <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|多重身份验证  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|基于证书的身份验证  <br/> |&#x2714; （仅限域加入的设备）  <br/> ||&#x2714;|&#x2714;|
|移动应用程序管理（通过 Intune）  <br/> |||&#x2714;|&#x2714;|
   

