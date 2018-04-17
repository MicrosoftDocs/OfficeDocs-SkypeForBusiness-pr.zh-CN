---
title: Desktop client feature comparison for Skype for Business
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 16b14d59-7737-4f9d-aa4d-83765a18ea07
description: 'Summary: Skype for Business Server 2015 or Skype for Business Online administrators can use these tables to understand what features are supported on which clients.'
ms.openlocfilehash: 0ce6457bea83c775ca5cf9373a5724f95785ddb1
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="desktop-client-feature-comparison-for-skype-for-business"></a>Desktop client feature comparison for Skype for Business
 
**Summary:** Skype for Business Server 2015 or Skype for Business Online administrators can use these tables to understand what features are supported on which clients.
  
 Before you deploy or upgrade to Skype for Business, check which clients are already in use in your organization. Use the tables below to understand the feature support impact on those clients. 这有助于你与用户交流更改、确定执行推出过程的进度以及完全了解升级到最新客户端的好处。
  
Some features available with Skype for Business Server 2015 are not available in Skype for Business Online, see [Online or Hybrid user account limitations](desktop-feature-comparison.md#Online-Hybrid) for specifics. Skype for Business Online Admins may want to refer to [Skype for Business Online Service Description](https://technet.microsoft.com/library/skype-for-business-online-service-description.aspx) for information on the different plans available to them.
  
The following tables show the features that are available with each client that works with Skype for Business Server 2015 or Skype for Business Online. You may also want to refer to [Mobile client feature comparison for Skype for Business](mobile-feature-comparison.md) for smart phone and tablet client feature comparisons. 你的组织购买的客户端访问许可证或用户订阅许可证也将影响用户可以使用的功能。 向用户部署完整版还是基本版客户端取决于贵组织选择购买的许可证或计划。 See the [Licensing Guide](https://products.office.com/en-us/skype-for-business/it-pros) for more details.
  
> [!IMPORTANT]
> Skype for Business Server 2015 and Skype for Business Online support the following previously released clients: Lync 2013, Lync 2010, Lync 2010 Mobile, Lync Phone Edition, and Lync 2010 Attendant. For information about these clients when used with other servers, see the [Client comparison tables for Lync Server 2013](https://technet.microsoft.com/en-us/library/gg425836%28v=ocs.15%29.aspx) and [Client comparison tables for Lync Server 2010](https://technet.microsoft.com/en-us/library/gg425836%28v=ocs.14%29.aspx). 
  
> [!NOTE]
> The **Lync 2010 Attendant** client is not supported in Skype for Business Online.
  
> [!NOTE]
> The Skype for Business Web App browser client and Skype Meetings App Windows 10 app only provide [Meetings support](desktop-feature-comparison.md#BKMK_Conferencing). Refer to [Plan for Meetings clients (Web App and Meetings App)](meetings-clients.md) for more about these clients.
  
## <a name="enhanced-presence-support"></a>增强状态支持
<a name="BKMK_EnhancedPresence"> </a>

除了有关用户处于联机、脱机和忙碌等状态的简单指示之外，此表还涵盖增强状态特性。 
  
|特性/功能|Skype for Business 2015 或 2016 客户端|Mac 版 Skype for Business|Lync 2013 client|Lync Windows 应用商店应用|Lync 2010 | Lync 2010 Attendant|Lync Phone Edition|Communicator for Mac 2011|Lync for Mac 2011|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|发布状态  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|
|查看状态  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|查看状态注释和外出消息  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|添加自定义位置  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|添加自定义注释  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|对“我的图片”使用任何公共网站中的照片  <br/> (not available in Skype for Business Online)  <br/> |&#x2714;||&#x2714;|||||||

 &#x2776;  Does not support publishing status based on calendar free/busy information.
  
## <a name="contacts-and-contact-groups-support"></a>联系人和联系人组支持
<a name="BKMK_Contacts"> </a>

此表涵盖与管理 IM 和状态联系人相关的特性。 
  

|特性/功能|Skype for Business 2015 或 2016 客户端|Mac 版 Skype for Business | Lync 2013 client | Lync Windows 应用商店应用 | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|预填充的联系人列表  <br/> |&#x2714;|||||||||
|查看和修改联系人列表  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|标记状态更改警报的联系人  <br/> |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;||||
|控制私人关系  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|搜索企业通讯簿  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|搜索 Microsoft Outlook 联系人  <br/> |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|管理联系人组  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|扩展通讯组和 Office 365 组  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|搜索响应组  <br/> (not available in Skype for Business Online)  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|显示最近的联系人组  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|显示当前对话组  <br/> |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|||
|显示其他联系人视图（例如平铺）  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|Sort contacts by Group, Relationship, or New (people who've added you to their Contacts list)  <br/> |&#x2714;||&#x2714;|按组排序  <br/> |&#x2714;|&#x2714;||||
|按状态（可用性）对联系人排序  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;|||&#x2714;|
|搜索和添加 Exchange 联系人  <br/> |&#x2714;||&#x2714;||||||&#x2714;|
   
## <a name="im-support"></a>IM 支持
<a name="BKMK_IMSupport"> </a>

此表涵盖与 IM 支持相关的特性。
  

|特性/功能 | Skype for Business 2015 或 2016 客户端 | Mac 版 Skype for Business | Lync 2013 client | Lync Windows 应用商店应用 | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|启动与联系人的 IM 或向联系人发送电子邮件  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|在单个选项卡式窗口中在多个 IM 对话之间导航/跟踪多个对话  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|在 Outlook 中记录 IM 对话  <br/> |&#x2714;|&#x2714;If server side conversation history is turned on  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;||保存在 Communicator for Mac 中  <br/> |保存在 Lync for Mac 中  <br/> |
|使用准备好的对话模板  <br/> |||||&#x2714;|&#x2714;||||
|检查拼写  <br/> |&#x2714;|&#x2714;||&#x2714;|||||&#x2714;|
|Skill search (with SharePoint Server integration)  <br/> (On-premises Skype for Business Server and on-premises SharePoint 2013 are required for skill search.)  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||
|持久聊天（群聊）集成  <br/> (not available for Skype for Business Online)  <br/> |&#x2714;||&#x2714;|||||||
|Escalate a Persistent Chat room to a Skype for Business Meeting with one click  <br/> (not available for Skype for Business Online)  <br/> |&#x2714;||&#x2714;|||||||
|IM 窗口中发送者和接收者的内嵌图片  <br/> |&#x2714;||&#x2714;|&#x2714;||||||
|发送墨迹消息  <br/> ||||&#x2714;||||||
|接收墨迹消息  <br/> |&#x2714;||&#x2714;|&#x2714;||||||
|发送高重要性 IM 消息  <br/> |&#x2714;||&#x2714;|||||||
   
## <a name="meetings-support"></a>会议支持
<a name="BKMK_Conferencing"> </a>

此表涵盖与会议支持相关的特性。
  
> [!NOTE]
>  Skype for Business meeting features aren't available in Skype for Business Online Standalone Plan 1.

在 Skype 至 Skype 会话中，Skype for Business Online 计划 1 用户可以在收到有权访问共享功能的用户邀请时参与桌面共享和应用共享。   
For details, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx). 
  
|特性/功能 | Skype for Business 2016 client | Mac 版 Skype for Business | Skype for Business Web App | Skype for Business 2015 client | Lync 2013 client | Lync Windows 应用商店应用 | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|添加计算机音频  <br/> |&#x2714;|&#x2714;|&#x2714;(requires plug-in)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|添加视频  <br/> |&#x2714;|&#x2714;|&#x2714;(requires plug-in)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|&#x2714;|
|查看多方视频（库视图）  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|基于视频的屏幕共享  <br/> |&#x2714;|&#x2714;Only for users homed on Skype for Business Online  <br/> |&#x2714;View-only  <br/> |||||||||
|使用会议中演示者控件  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|访问详细的会议名单  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|参与多方 IM  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|共享桌面（如果已启用）  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; (requires plug-in)  <br/> |&#x2714;|&#x2714;||&#x2714;|||&#x2714; &#x2776; |&#x2714; &#x2776; |
|共享程序（如果已启用）  <br/> |&#x2714;|仅查看  <br/> |&#x2714;(requires plug-in)  <br/> |&#x2714;|&#x2714;||&#x2714;||||仅查看  <br/> |
|添加匿名参与者（如果已启用）  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|使用电话拨入式音频会议  <br/> |&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714;|&#x2714;|||&#x2714;|
|启动“立即开会”会议  <br/> |&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|添加和演示 Microsoft PowerPoint 文件  <br/> |&#x2714;| &#x2778; View only, annotations not available  <br/> |&#x2714;|&#x2714;|&#x2714;|仅演示  <br/> |&#x2714;|||| &#x2778; View only, annotations not available  <br/> |
|导航 Microsoft PowerPoint 文件  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|添加和编辑 OneNote 会议笔记  <br/> |&#x2714;||仅编辑（不添加）  <br/> |&#x2714;|&#x2714;|||||||
|使用白板  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|发起投票  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|上载文件以与其他人共享  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|安排会议或电话会议  <br/> |Outlook or Skype for Business Web Scheduler  <br/> |Outlook or Skype for Business Web Scheduler  <br/> |Skype for Business Web Scheduler  <br/> |Outlook or Skype for Business Web Scheduler  <br/> |Outlook or Lync Web Scheduler  <br/> |Outlook or Lync Web Scheduler  <br/> |Outlook  <br/> ||||Outlook  <br/> |
|Q&amp;A Manager  <br/> |&#x2714;|||||||||||
|禁用与会者视频  <br/> |&#x2714;||&#x2714;|||||||||
|禁用会议 IM  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|||||||
|将受众设为静音  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|将每个人都设为与会者  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|开通 Skype 会议直播  <br/> |&#x2714;|||||||||||
|代理人可以代表委托人安排会议  <br/> |&#x2714;|仅 Skype for Business Online <br/>|&#x2714;|||||||||
|在 Skype for Business 与 Outlook 之间同步代理人  <br/> |&#x2714;||&#x2714;|||||||||
|基于视频的屏幕共享  <br/> |&#x2714;| 仅 Skype for Business Online <br/> |&#x2714;||&#x2714;|||||||
|设置视频聚焦（锁定视频）  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|提供/获取对屏幕共享的控制  <br/> |&#x2714;||&#x2714;|||||||||
   
 &#x2776;  Participants can't control desktops that are shared by Skype for Business on Mac, Lync for Mac 2011, or Communicator for Mac 2011 users. Skype for Business on Mac, Lync for Mac 2011 and Communicator for Mac 2011 users can't control desktops shared by Windows users. This also won't work for Skype for Business Web App on Max OSX.
  
 &#x2777;  For Skype for Business Online, this feature requires Microsoft PSTN Conferencing, Exchange Unified Messaging, or a 3rd party audio conferencing provider.
  
 &#x2778;  The Lync for Mac 2011 client cannot view Microsoft Office 2013 PowerPoint presentations when they have been shared in a conference by the Skype for Business Web App.
  
## <a name="voice-telephony-support"></a>语音（电话）支持
<a name="BKMK_Telephony"> </a>

此表涵盖与语音服务支持相关的特性。
  
> [!NOTE]
> Skype for Business Voice (Telephony) features are limited to certain Skype for Business Online subscription plans. > For details, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx). 
  
 | 特性/功能 | Skype for Business 2015 或 2016 客户端 | Mac 版 Skype for Business | Lync 2013 client | Lync Windows 应用商店应用 | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|拨打电话  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|单击以呼叫联系人  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|转移来电  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|管理呼叫转接  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|管理团队呼叫设置  <br/> |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|管理代理人  <br/> |&#x2714;|&#x2714;Requires Skype for Business Server 2015 CU4 or later  <br/> |&#x2714; &#x2776; ||&#x2714;||||&#x2714;|
|向响应组拨打电话  <br/> |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|支持紧急服务 (E-911)  <br/> |&#x2714;|&#x2714;Requires Skype for Business Server 2015 CU6 or later  <br/> |&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|IM notification to SIP URI(s) for E-911 call  <br/> |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|IM notification to distribution list for E-911 call  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|连接到语音邮件，设置或更改问候语  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|未接电话通知  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|代表其他联系人拨打电话（经理/代理人方案）  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|||||
|如果配置为代理人，则处理其他人的呼叫  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;|||
|管理大量呼叫  <br/> |||||&#x2714;|&#x2714;||||
|呼叫寄存  <br/> |&#x2714;||&#x2714; &#x2776; |||||||
|群呼应答  <br/> |&#x2714;||&#x2714; &#x2776; ||||&#x2714;|||
|基于位置的路由  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|管理响应组/团队呼叫组  <br/> |&#x2714;||&#x2714;|||||||
   
 &#x2776;  This feature isn't available in Skype for Business Online.
  
## <a name="external-users-support"></a>外部用户支持
<a name="BKMK_ExternalUsers"> </a>

此表涵盖与驻留在 PSTN 中的外部用户支持相关的特性。
  

|特性/功能 | Skype for Business 2015 或 2016 客户端 | Mac 版 Skype for Business | Lync 2013 client | Lync Windows 应用商店应用 | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|启动与公共联系人的 IM  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|启动与联盟联系人的 IM  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|进行与外部用户的双方或多方呼叫  <br/> (not available in Skype for Business Online)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
## <a name="recording-support"></a>录制支持
<a name="BKMK_Recording"> </a>

此表涵盖与会议录制支持相关的特性。
  
| Future/capability** | Skype for Business 2015 或 2016 客户端 | Mac 版 Skype for Business | Lync 2013 client | Lync Windows 应用商店应用 | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|音频、视频、应用程序共享、桌面共享和上载的内容的客户端记录  <br/> |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|在客户端录制文件传输、共享的 OneNote 页面和 PowerPoint 批注  <br/> |&#x2714; &#x2777; ||&#x2714; &#x2777; ||&#x2714;|||||
|选择首选的录制解决方案  <br/> |&#x2714;||&#x2714;|||||||
   
 &#x2776;  Recording is unavailable in certain Skype for Business Online standalone plans. 录制需要具有完整的 Skype for Business 客户端权限。
  
 &#x2777;  Recording of file transfers, shared OneNote pages, and PowerPoint annotations is unavailable in Skype for Business Online.
  
## <a name="modern-authentication"></a>现代化身份验证
<a name="BKMK_Recording"> </a>

此表涵盖需要支持新式身份验证的特性。 
  
Modern authentication also requires a topology described in [Skype for Business topologies supported with Modern Authentication](../../plan-your-deployment/modern-authentication/topologies-supported.md).
  

 | 特性/功能 | Skype for Business 2015 或 2016 客户端 | Mac 版 Skype for Business | Lync 2013 client | Lync Windows 应用商店应用 | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|现代化身份验证  <br/> |&#x2714;|&#x2714;|&#x2714;|||||||
|多重身份验证  <br/> |&#x2714;|&#x2714;|&#x2714;|||||||
|基于证书的身份验证  <br/> |&#x2714;(Domain-joined device only)  <br/> |&#x2714;|&#x2714;(Domain-joined device only)  <br/> |||||||
   
## <a name="archiving-compliance-and-logging-support"></a>存档、合规性和日志记录支持
<a name="BKMK_Archiving"> </a>

此表涵盖与存档和日志记录功能支持相关的特性。
  

 | 特性/功能 | Skype for Business 2015 或 2016 客户端 | Mac 版 Skype for Business | Lync 2013 client | Lync Windows 应用商店应用 | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | **Communicator for Mac 2011** | Lync for Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Outlook 对话历史记录中 IM 对话的存档  <br/> |&#x2714; &#x2776; |&#x2714;If server side conversation history is turned on  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|&#x2714;||保存在 Communicator for Mac 中  <br/> |保存在 Lync for Mac 中  <br/> |
|音频、视频、应用程序共享、桌面共享和上载的内容的客户端存档  <br/> |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|文件传输、共享的 OneNote 页面和 PowerPoint 注释的客户端存档  <br/> (unavailable in Skype for Business Online)  <br/> |&#x2714;||&#x2714;||&#x2714;|||||
|Access sign-in logs from Skype for Business icon in the task bar  <br/> |&#x2714;||&#x2714;|||||||
   
 &#x2776;  For Skype for Business Online users, this feature requires Exchange Online and is controlled by the user's Exchange mailbox In-Place Hold attribute.
  
## <a name="client-limitations"></a>客户端限制 
<a name="Types"> </a>

### <a name="basic-client-limitations"></a>基本客户端限制
<a name="Full-Basic"> </a>

以下功能在使用完整客户端时可用，在使用基本客户端时不可用： 
  
- 管理团队呼叫设置
    
- 管理代理人
    
- 代表其他联系人发起呼叫（经理/代理人方案）
    
- 如果配置为代理人，则处理其他人的呼叫
    
- 管理大量呼叫
    
- 发起针对响应组的呼叫
    
- 呼叫寄存
    
- Change greeting
    
- 组内呼叫应答
    
### <a name="online-or-hybrid-user-account-limitations"></a>联机或混合用户帐户限制
<a name="Online-Hybrid"> </a>

用户帐户可以联机形式存在或在本地存在，这将影响用户可以使用的功能。 Users with accounts on Skype for Business Online will not have access to the following features, even with the Full client: 
  
- 增强状态：对“我的图片”使用任何公共网站中的照片
    
- 联系人：搜索响应组
    
- IM 支持：持久聊天（群聊）集成
    
- IM Support: Escalate a Persistent Chat room to a Skype for Business Meeting with one click
    
- 外部用户：进行与外部用户的双方或多方呼叫
    
## <a name="see-also"></a>另请参阅
<a name="Types"> </a>

[Plan for clients and devices](clients-and-devices.md)

