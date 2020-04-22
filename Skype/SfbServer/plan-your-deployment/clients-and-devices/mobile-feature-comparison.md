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
description: 摘要：在规划 Skype for business Server 时，请查看对移动客户端的功能支持。
ms.openlocfilehash: 36ae93e796e4142a9ae3b5fb85ac806c9a38cdca
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777767"
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Skype for business 的移动客户端功能比较
 
**摘要：** 在规划 Skype for business Server 时，请查看对移动客户端的功能支持。
  
本文按以下类别比较 Skype for Business 移动客户端和 Skype for business 桌面客户端之间的特性和功能：
  
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
    
下表列出了 Skype for business Server 的本地部署中 Skype for business 用户可使用的功能。 Skype for Business Online 和 Microsoft 365 或 Office 365 用户也可以使用相同的功能，除非在表脚注中以其他方式指明。
  
> [!NOTE]
> 有关最终用户的联机帮助和资源，请参阅[发现 Skype For business](https://go.microsoft.com/fwlink/p/?LinkId=528686)。 
  
> [!NOTE]
> 若要比较其他 Skype for Business 客户端中提供的功能，请参阅[适用于 skype For business 的桌面客户端功能比较](desktop-feature-comparison.md)。 

> [!NOTE]
> Skype for Business Server 2019 中不再提供对旧版移动客户端的 MCX （移动服务）支持。 所有当前 Skype for Business 移动客户端都已使用统一通信 Web API （UCWA）来支持即时消息（IM）、状态和联系人。 具有使用 MCX 的旧版客户端的用户将需要升级到当前客户端。
  
## <a name="sign-in-push-notifications-and-general-features"></a>登录、推送通知和常规功能

 
 | 功能/功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business 会话仍处于登录  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|
|支持推送通知  <br/> |&#x2714; &#x2778; |&#x2714;|&#x2714; &#x2779; |&#x2714; &#x2779; |
|可在同一设备上缓存多个用户的帐户信息  <br/> |&#x2714;||||
|屏幕阅读器/语音  <br/> |&#x2714;|仅 &#x2714; &#x2777;  英语  <br/> |&#x2714;|&#x2714;|
|使用外部键盘进行辅助功能  <br/> |&#x2714;||&#x2714;|&#x2714;|
|Microsoft 客户体验改善计划支持  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 在 Windows Phone 上 &#x2776;，Skype for Business 在一段时间不活动后自动注销，如下所示：
  
- 如果用户已启用推送通知，Skype for Business 将在处于不活动状态10天后登录。
    
- 如果用户未启用推送通知，则在用户离开应用程序后，Skype for Business 将立即注销。
    
在 iOS 设备上，Skype for Business 在移动客户端因网络连接丢失或其他问题而在10天内未连接到服务器后，会自动发出 "注销"。
  
 仅在应用程序中 &#x2777;。
  
 当应用程序在后台运行时，&#x2778; 通知可用。
 
 &#x2779; Google/Android/GCNS 和 Apple/APNS 移动通知服务使用 HTTPS/TLS 加密来传递通知。 通知有效负载在通知提供程序处理时以纯文本形式处理。
 
-   适用于 Android 的 Skype for Business 接收简单通知（通过 GCNS 传递），无客户数据。
-   适用于 iOS 的 Skype for Business 接收通知（通过 APNS 传递），其中可能包括呼叫或邮件的客户数据。
 
  
## <a name="enhanced-presence-support"></a>增强状态支持


 | 功能/功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|发布和查看状态  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|根据日历闲/忙信息查看状态  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|查看状态注释和外出消息  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|添加自定义位置  <br/> |&#x2714;||||
|添加自定义注释  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|根据日历闲/忙信息发布状态  <br/> |&#x2714; &#x2776; ||||
|设置手动状态（例如，忙、Do Not 打扰等）  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; Skype for Business 移动客户端不会根据用户的忙/闲日历信息更新用户的状态。 如果移动客户端用户也登录到 Skype for Business 桌面客户端，则桌面客户端将根据用户的忙/闲日历信息更新用户的状态。 如果用户仅登录到移动客户端，则用户的状态不会根据忙/闲日历信息进行更新。
  
## <a name="contacts-and-contact-groups-support"></a>联系人和联系人组支持


 | 功能/功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
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
|展开通讯组  <br/> |&#x2714;|&#x2714;||&#x2714;|
|搜索响应组  <br/> |&#x2714; &#x2776; |&#x2714;||&#x2714;|
|显示或隐藏联系人照片  <br/> |&#x2714;|&#x2714;|||
|将联系人固定到你的主屏幕  <br/> ||&#x2714;|||
   
 &#x2776; 对 Skype for Business Online 和/或 Microsoft 365 或 Office 365 用户不可用。
  
## <a name="instant-messaging-support"></a>即时消息支持


 | 功能/功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|启动与联系人的即时消息（IM）  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|参与多方 IM  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|从对话窗口中邀请其他人  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|显示当前对话  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|在多个 IM 对话之间进行导航  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|在 Exchange 中自动记录 IM 对话  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|以电子邮件的形式发送 IM 对话  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|向联系人发送电子邮件  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|查看错过的 IM 邀请  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|收到传入 IM 时振动  <br/> ||&#x2714; &#x2776; |&#x2714;|&#x2714;|
   
 无论是否显示即时消息对话中的当前消息，vibrates 此设备在收到即时消息时都 &#x2776;
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Skype for business 到 Skype for business 音频和视频


 | 功能/功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for business 到 Skype for business voice  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Skype for business 到 Skype for business 视频  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
> [!NOTE]
> 移动设备上的视频默认需要 WiFi 连接。 
  
## <a name="conferencing-support"></a>会议支持


 | 功能/功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|单击会议提醒中的链接以加入视频或 VoIP 会议  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
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
|查看共享桌面或程序（VbSS 或 RDP）  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|查看共享的 PowerPoint 文件  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777;&#x2778; |&#x2714; &#x2777; &#x2778;|
|上传和演示 PowerPoint 文件  <br/> |&#x2714;||&#x2714; &#x2777; |&#x2714; &#x2777; |
|使用会议工具（使用白板、执行投票、共享文件）  <br/> |&#x2714;||||
|导航您的会议列表  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|即使你没有 Skype for Business 帐户也可加入会议  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|查看有关会议参与者的详细信息  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|直接从客户端或设备启动与多个参与者的未计划的组对话  <br/> |&#x2714;|&#x2714;|&#x2714;||
   
 &#x2776; 对于 Microsoft 365 或 Office 365 用户，此功能需要企业语音，这是 E5 许可证的一部分。
  
 默认情况下，&#x2777; 需要 WiFi 连接。
 
 不支持在 PowerPoint 演示文稿中查看嵌入的视频 &#x2778;。
  
## <a name="telephony-support"></a>电话支持


 | 功能/功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|在 Skype for Business 中，点击呼叫图标以呼叫联系人  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|转接呼叫  <br/> |&#x2714;|&#x2714;|&#x2714;||
|咨询转移  <br/> |&#x2714; &#x2778; ||||
|管理呼叫转接  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|
|管理团队呼叫设置  <br/> |&#x2714; &#x2776; ||||
|管理代理  <br/> |&#x2714; &#x2776; ||||
|向响应组发起呼叫  <br/> |&#x2714; &#x2776; ||||
|支持紧急服务  <br/> |&#x2714; &#x2777; ||||
|代表其他联系人发起呼叫（经理/代理方案）  <br/> |&#x2714; &#x2776; ||||
|如果配置为代理人，则处理其他联系人的呼叫  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|使用通过工作的呼叫  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
|访问语音邮件  <br/> |&#x2714;|&#x2714;|&#x2714;||
|在 Skype for Business 中使用小键盘  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
   
 &#x2776; 适用于 Skype for business Online 和/或 Office 365 E5 用户以及驻留在启用企业语音的 Skype for Business Server 或 Lync Server 2013 的用户。
  
 &#x2777; 适用于 Skype for Business Online 和/或 Microsoft 365 或 Office 365 用户，Microsoft 合作伙伴支持此功能。
  
 仅 &#x2778; Windows 桌面客户端。
  
## <a name="external-user-support"></a>外部用户支持


 | 功能/功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|启动与公共联系人的 IM  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|启动与联盟联系人的 IM  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|进行与外部用户的双方呼叫  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|进行与外部用户的多方呼叫  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|通过工作呼叫已发布的工作电话号码，使用 "通过工作呼叫" 访问其移动电话上的联盟联系人 &#x2776;            <br/> ||&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; 默认情况下，向联合用户分配外部联系人隐私关系。 若要能够通过呼叫其发布的工作电话号码来访问其移动电话上的联盟联系人，联合联系人必须手动为你分配同事隐私关系。
  
## <a name="address-book-integration"></a>通讯簿集成


 | 功能/功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|呼叫设备通讯簿联系人  <br/> ||&#x2714;|&#x2714;|&#x2714;|
|直接从设备通讯簿向联系人发出 Skype for Business 呼叫  <br/> ||||&#x2714;|
   
## <a name="archiving-and-compliance-support"></a>存档和合规性支持


 | 功能/功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|提供客户端存档  <br/> |&#x2714;||||
|提供客户端记录  <br/> |&#x2714; &#x2776; ||||
   
 &#x2776; 对 Skype for Business Online 和/或 Microsoft 365 或 Office 365 用户不可用。
  
## <a name="modern-authentication"></a>新式验证

此表涵盖需要支持新式身份验证的功能。
  
新式验证还需要在[采用新式验证时支持的 Skype For business 拓扑](../../plan-your-deployment/modern-authentication/topologies-supported.md)中介绍的拓扑。
  

 | 功能/功能  | Skype for Business 桌面客户端  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|新式验证  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|多因素身份验证  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|基于证书的身份验证  <br/> |&#x2714; （仅加入域的设备）  <br/> ||&#x2714;|&#x2714;|
|移动应用程序管理（通过 Intune）  <br/> |||&#x2714;|&#x2714;|
   

