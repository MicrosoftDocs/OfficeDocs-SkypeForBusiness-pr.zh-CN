---
title: Skype for Business Server 2015 的桌面客户端功能比较
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
ms.assetid: 16b14d59-7737-4f9d-aa4d-83765a18ea07
description: 摘要：Skype for Business Server 2015 或 Skype for Business Online 管理员可以使用这些表了解哪些客户端支持哪些功能。
ms.openlocfilehash: 6c23f924ef950f869cb2e337e59edda28715d11d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109288"
---
# <a name="desktop-client-feature-comparison-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 的桌面客户端功能比较

**摘要：** Skype for Business Server 2015 或 Skype for Business Online 管理员可以使用这些表了解哪些客户端支持哪些功能。
  
 在部署或升级到 Skype for Business 之前，请检查组织中已在使用哪些客户端。 使用下表可了解功能支持对客户端的影响。 这可以帮助您将更改传达给用户、调整推出过程的速度，并完全了解升级到最新客户端的好处。
  
Skype for Business Server 2015 中提供某些功能在 Skype for Business Online 中不可用，请参阅 [联机](desktop-feature-comparison.md#Online-Hybrid) 或混合用户帐户限制了解具体信息。 Skype for Business Online 管理员可能需要参阅 [Skype for Business Online 服务](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description) 说明，了解他们可用的不同计划。

有关 Skype for Business Server 2019 上的客户端支持，请参阅 Skype [for Business 2019](../../../SfBServer2019/plan/feature-comparison.md) 的桌面客户端功能比较。
  
下表显示了适用于使用 Skype for Business Server 2015 或 Skype for Business Online 的每个客户端的功能。 你可能还需要参考 [Skype for Business](mobile-feature-comparison.md) 的移动客户端功能比较，以便进行智能手机和平板电脑客户端功能比较。 组织购买的客户端访问许可证或用户订阅许可证还会影响哪些功能可供用户使用。 是向用户部署完整客户端还是基本客户端取决于组织选择购买的许可证或计划。 有关详细信息 [，请参阅许可](https://products.office.com/skype-for-business/it-pros) 指南。
  
> [!IMPORTANT]
> Skype for Business Server 2015 和 Skype for Business Online 支持以下以前发布的客户端：Lync 2013、Lync 2010、Lync 2010 Mobile、Lync Phone Edition 和 Lync 2010 Attendant。 有关与其他服务器一同使用的这些客户端的信息，请参阅[Client comparison tables for Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-desktop-client-comparison-tables)和 Client comparison tables for Lync Server [2010。](/previous-versions/office/skype-server-2010/gg425836(v=ocs.14))

> [!NOTE]
> **Lync 2010 Attendant** 客户端在 Skype for Business Online 中不受支持。

> [!NOTE]
> Skype for Business Web App 浏览器客户端和 Skype 会议应用 Windows 10 应用仅提供 [会议支持](desktop-feature-comparison.md#BKMK_Conferencing)。 有关这些 [客户端 (请参阅 Plan for Meetings clients) Web App 和 Meetings App ](meetings-clients.md)) 。
  
## <a name="enhanced-presence-support"></a>增强状态支持

<a name="BKMK_EnhancedPresence"> </a>

此表涵盖的增强状态功能超出了用户是否处于联机、脱机、忙碌等状态的简单指示之外。
  
|功能|Skype for Business 2015 或 2016 客户端|Mac 版 Skype for Business|Lync 2013 客户端|Lync Windows 应用商店应用|Lync 2010 | Lync 2010 Attendant|Lync Phone Edition|Communicator for Mac 2011|Lync for Mac 2011|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|发布状态 |&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|
|查看状态   |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|查看状态注释和外出消息 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|添加自定义位置 |&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|添加自定义注释 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|将来自任何公共站点的照片用于 Skype for Business Online (中不可用的"我的图片")  |&#x2714;||&#x2714;|||||||

 &#x2776;不支持基于日历忙/闲信息的发布状态。
  
## <a name="contacts-and-contact-groups-support"></a>联系人和联系人组支持

<a name="BKMK_Contacts"> </a>

此表涵盖与管理 IM 和状态联系人相关的功能。

|功能|Skype for Business 2015 或 2016 客户端|Mac 版 Skype for Business | Lync 2013 客户端 | Lync Windows 应用商店应用 | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|预填充的联系人列表 |&#x2714;|||||||||
|查看和修改联系人列表 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|标记状态更改警报的联系人 |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;||||
|控制隐私关系 |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|搜索企业通讯簿 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|搜索 Microsoft Outlook 联系人 |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|管理联系人组 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|展开通讯组和 Microsoft 365 组 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|搜索响应组  <br/>  (Skype for Business Online)  |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|显示“最近的联系人”组 |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|显示“当前对话”组 |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|||
|显示其他联系人视图（例如平铺） |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|按组、关系或新联系人 (已添加到联系人列表联系人列表的联系人进行排序)  |&#x2714;||&#x2714;|按组排序 |&#x2714;|&#x2714;||||
|按状态和可用性 (对联系人)  |&#x2714;||&#x2714;||&#x2714;|&#x2714;|||&#x2714;|
|搜索和添加 Exchange 联系人 |&#x2714;||&#x2714;||||||&#x2714;|

## <a name="im-support"></a>IM 支持

<a name="BKMK_IMSupport"> </a>

此表涵盖与 IM 支持相关的功能。

|功能 | Skype for Business 2015 或 2016 客户端 | Mac 版 Skype for Business | Lync 2013 客户端 | Lync Windows 应用商店应用 | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|与联系人发起 IM 或向联系人发送电子邮件 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|在多个 IM 对话之间导航/在单个选项卡式窗口中跟踪多个对话 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|在 Outlook 中记录 IM 对话 |&#x2714;|&#x2714;如果服务器端对话历史记录已打开  |&#x2714;|&#x2714;|&#x2714;|&#x2714;||保存在 Communicator for Mac 中 |保存在 Lync for Mac 中 |
|使用准备好的对话模板 |||||&#x2714;|&#x2714;||||
|检查拼写 |&#x2714;|&#x2714;||&#x2714;|||||&#x2714;|
|技能搜索 (SharePoint Server 集成)   <br/>  (技能搜索需要本地 Skype for Business Server 和本地 SharePoint 2013。)  |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||
|持久聊天 (群聊) 集成  <br/>  (Skype for Business Online)  |&#x2714;||&#x2714;|||||||
|单击一下即可将持久聊天室升级为 Skype for Business 会议  <br/>  (Skype for Business Online)  |&#x2714;||&#x2714;|||||||
|IM 窗口中发件人和接收方的内联图片 |&#x2714;||&#x2714;|&#x2714;||||||
|发送墨迹消息 ||||&#x2714;||||||
|接收墨迹消息 |&#x2714;||&#x2714;|&#x2714;||||||
|将 IM 消息设置为高重要性 |&#x2714;||&#x2714;|||||||
|在对等 IM 对话中传输文件 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|

## <a name="meetings-support"></a>会议支持

<a name="BKMK_Conferencing"> </a>

此表涵盖与会议支持相关的功能。
  
> [!NOTE]
> Skype for Business 会议功能在 Skype for Business Online 独立计划 1 中不可用。  计划 1 即将 [停用](../../../SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-for-business-online-plan-1-retirement.md)。

在 Skype 到 Skype 会话中，如果 Skype for Business Online 计划 1 用户受邀访问共享功能，则他们可以参与桌面共享和应用程序共享。
有关详细信息，请参阅 [Skype for Business Online 服务说明](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)。
  
|功能 | Skype for Business 2016 客户端 | Mac 版 Skype for Business | Skype for Business Web 应用 | Skype for Business 2015 客户端 | Lync 2013 客户端 | Lync Windows 应用商店应用 | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|添加计算机音频 |&#x2714;|&#x2714;|&#x2714; (需要插件)  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|添加视频 |&#x2714;|&#x2714;|&#x2714; (需要插件)  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|&#x2714;|
|查看多方视频 (库视图)  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|基于视频的屏幕共享 |&#x2714;|&#x2714;|&#x2714;仅查看 |||||||||
|使用会议中演示者控件 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|访问详细的会议名单 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|参与多方 IM |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|共享桌面（如果已启用） |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776;  (需要插件)  |&#x2714;|&#x2714;||&#x2714;|||&#x2714; &#x2776; |&#x2714; &#x2776; |
|共享程序（如果已启用） |&#x2714;|仅查看   |&#x2714; (需要插件)  |&#x2714;|&#x2714;||&#x2714;||||仅查看 |
|添加匿名参与者（如果已启用） |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|使用拨入音频会议 |&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714;|&#x2714;|||&#x2714;|
|启动"立即开会"会议 |&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|添加并演示 Microsoft PowerPoint 文件 |&#x2714;| &#x2778;批注不可用 |&#x2714;|&#x2714;|&#x2714;|仅呈现 |&#x2714;|||| &#x2778;查看，批注不可用 |
|导航 Microsoft PowerPoint 文件 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|添加和编辑 OneNote 会议笔记 |&#x2714;||仅编辑 (添加)  |&#x2714;|&#x2714;|||||||
|使用白板 |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|发起投票 |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|上载文件以与其他人共享 |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|安排会议 |Outlook 或 Skype for Business Web 计划程序 |Outlook 或 Skype for Business Web 计划程序 |Skype for Business Web 计划程序 |Outlook 或 Skype for Business Web 计划程序 |Outlook 或 Lync Web 计划程序 |Outlook 或 Lync Web 计划程序 |Outlook ||||Outlook |
|问答 &amp; 管理器 |&#x2714;|||||||||||
|禁用与会者视频|&#x2714;||&#x2714;|||||||||
 | |禁用会议 IM  |&#x2714;||&#x2714;|&#x2714;|&#x2714;|||||||
|将受众设为静音   |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|使每个人都成为与会者 |&#x2714;||&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|生成 Skype 会议直播  |&#x2714;|||||||||||
|代理人可以代表代理者安排会议  |&#x2714;|&#x2714;|&#x2714;|||||||||
|在 Skype for Business 和 Outlook 之间同步代理人 |&#x2714;||&#x2714;|||||||||
|设置视频聚焦 (锁定视频)  |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|授予/控制屏幕共享 |&#x2714;||&#x2714;|||||||||

 &#x2776;参与者无法控制由 Mac 版 Skype for Business、Lync for Mac 2011 或 Communicator For Mac 2011 用户共享的桌面。 Mac 版 Skype for Business、Lync for Mac 2011 和 Communicator for Mac 2011 用户无法控制 Windows 用户共享的桌面。 这同样对 Max OSX 上的 Skype for Business Web App 不起作用。
  
 &#x2777;对于 Skype for Business Online，此功能需要 Microsoft PSTN 会议、Exchange 统一消息或第三方音频会议提供商。
  
 &#x2778; Skype for Business Web App 在会议共享 Microsoft Office 2013 PowerPoint 演示文稿时，Lync for Mac 2011 客户端无法查看这些演示文稿。
  
## <a name="voice-telephony-support"></a>语音 (电话) 支持

<a name="BKMK_Telephony"> </a>

此表涵盖与语音服务支持相关的功能。
  
> [!NOTE]
> Skype for Business Voice (Telephony) 功能仅限于某些 Skype for Business Online 订阅计划。 有关详细信息，请参阅 [Skype for Business Online 服务说明](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)。
  
| 功能 | Skype for Business 2015 或 2016 客户端 | Mac 版 Skype for Business | Lync 2013 客户端 | Lync Windows 应用商店应用 | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|发起呼叫 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|单击呼叫联系人  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|转接呼叫 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|管理呼叫转接 |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|管理团队呼叫设置 |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|管理代理 |&#x2714;|&#x2714;需要 Skype for Business Server 2015 CU4 或更高版本 |&#x2714; &#x2776; ||&#x2714;||||&#x2714;|
|向响应组发起呼叫 |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|支持 E-911 (紧急)   |&#x2714;|&#x2714;需要 Skype for Business Server 2015 CU6 或更高版本 |&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|针对 E-911 呼叫 (SIP URI) IM 通知 |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|向通讯组列表发送 E-911 呼叫的 IM 通知 |&#x2714;||&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|连接到语音邮件，设置或更改问候语 |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|未接来电通知 |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|代表其他联系人发起呼叫（经理/代理方案） |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|||||
|处理其他人的呼叫（如果配置为代理的话） |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;|||
|管理大量呼叫 |||||&#x2714;|&#x2714;||||
|呼叫寄存  |&#x2714;||&#x2714; &#x2776; |||||||
|群呼代接  |&#x2714;||&#x2714; &#x2776; ||||&#x2714;|||
|基于位置的路由  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|管理响应组/团队呼叫组 |&#x2714;||&#x2714;|||||||
|应答自动助理呼叫 |&#x2714;||&#x2714;|||||||

&#x2776;此功能在 Skype for Business Online 中不可用。
  
## <a name="external-users-support"></a>外部用户支持

<a name="BKMK_ExternalUsers"> </a>

此表涵盖与支持位于 PSTN 上的外部用户相关的功能。

|功能 | Skype for Business 2015 或 2016 客户端 | Mac 版 Skype for Business | Lync 2013 客户端 | Lync Windows 应用商店应用 | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|启动与公共联系人的 IM  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|启动与联盟联系人的 IM |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|进行与外部用户的双方或多方呼叫  <br/>  (Skype for Business Online)  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|

## <a name="recording-support"></a>录制支持

<a name="BKMK_Recording"> </a>

此表涵盖与录制会议支持相关的功能。
  
| 未来/功能** | Skype for Business 2015 或 2016 客户端 | Mac 版 Skype for Business | Lync 2013 客户端 | Lync Windows 应用商店应用 | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|客户端录制音频、视频、应用程序共享、桌面共享和上载的内容 |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|客户端记录文件传输、共享 OneNote 页面和 PowerPoint 注释 |&#x2714; &#x2777; ||&#x2714; &#x2777; ||&#x2714;|||||
|选择首选录制分辨率 |&#x2714;||&#x2714;|||||||

 &#x2776;录制在某些 Skype for Business Online 独立计划中不可用。 录制需要完整的 Skype for Business 客户端权限。
  
 &#x2777;记录文件传输、共享的 OneNote 页面和 PowerPoint 注释在 Skype for Business Online 中不可用。
  
## <a name="modern-authentication"></a>新式验证

<a name="BKMK_Recording"> </a>

此表涵盖需要新式验证支持的功能。
  
新式验证还需要 Skype for Business 拓扑支持新式验证 [中所述的拓扑](../../plan-your-deployment/modern-authentication/topologies-supported.md)。

| 功能 | Skype for Business 2015 或 2016 客户端 | Mac 版 Skype for Business | Lync 2013 客户端 | Lync Windows 应用商店应用 | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|新式验证 |&#x2714;|&#x2714;|&#x2714;|||||||
|多重身份验证  |&#x2714;|&#x2714;|&#x2714;|||||||
|基于证书的身份验证  |&#x2714; (已加入域的设备) | &#x2714;|&#x2714; (已加入域的设备)   |||||||
|Kerberos 身份验证 |&#x2714;||&#x2714;|||||||

## <a name="archiving-compliance-and-logging-support"></a>存档、合规性和日志记录支持

<a name="BKMK_Archiving"> </a>

此表涵盖与存档和日志记录功能支持相关的功能。

| 功能 | Skype for Business 2015 或 2016 客户端 | Mac 版 Skype for Business | Lync 2013 客户端 | Lync Windows 应用商店应用 | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | **Communicator for Mac 2011** | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Outlook 对话历史记录中的 IM 对话存档 |&#x2714; &#x2776; |&#x2714;如果启用了服务器端对话历史记录 |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|&#x2714;||保存在 Communicator for Mac 中 |保存在 Lync for Mac 中 |
|音频、视频、应用程序共享、桌面共享和上载内容的客户端存档 |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|文件传输、共享 OneNote 页面和 PowerPoint 批注的客户端存档  <br/>  (Skype for Business Online) |&#x2714;||&#x2714;||&#x2714;|||||
|从任务栏中的 Skype for Business 图标访问登录日志 |&#x2714;||&#x2714;|||||||

 &#x2776; 对于 Skype for Business Online 用户，此功能需要 Exchange Online，并且由用户的 Exchange 邮箱和保留In-Place控制。
  
## <a name="client-limitations"></a>客户端限制

<a name="Types"> </a>

### <a name="basic-client-limitations"></a>基本客户端限制

<a name="Full-Basic"> </a>

以下功能使用完整客户端提供，在基本客户端中不可用：

- 管理团队呼叫设置
- 管理代理
- 处理其他人的呼叫（如果配置为代理的话）
- 管理大量呼叫
- 向响应组发起呼叫
- 呼叫寄存
- 更改问候语
- 群呼代接
- 如果用户状态为 UM 已禁用，并且正在使用旧版 Outlook 客户端 (2013 或更早版本，将不会生成未接来电通知) 

### <a name="online-or-hybrid-user-account-limitations"></a>联机或混合用户帐户限制

<a name="Online-Hybrid"> </a>

用户帐户可以联机或本地存在，这会影响该用户可用的功能。 在 Skype for Business Online 上拥有帐户的用户将无法访问以下功能，即使使用完整客户端：
  
- 增强状态：将来自任何公共网站的照片用于"我的图片"
- 联系人：搜索响应组
- IM 支持：持久聊天 (群聊) 集成
- IM 支持：单击一下即可将持久聊天室升级为 Skype for Business 会议
- 外部用户：与外部用户进行双方或多方呼叫

## <a name="see-also"></a>另请参阅

<a name="Types"> </a>

[规划客户端和设备](clients-and-devices.md)

[使用 Windows Installer 的 Skype for Business 版本的最新 (MSI) ](../../sfb-client-updates.md)