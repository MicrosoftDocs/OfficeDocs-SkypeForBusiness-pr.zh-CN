---
title: Skype for business Server 2015 的桌面客户端功能比较
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
ms.assetid: 16b14d59-7737-4f9d-aa4d-83765a18ea07
description: 摘要： Skype for Business Server 2015 或 Skype for Business Online 管理员可以使用这些表了解哪些客户端支持哪些功能。
ms.openlocfilehash: c07955758f86e31eb947a99ce8ba0e8dc7a44b30
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777797"
---
# <a name="desktop-client-feature-comparison-for-skype-for-business-server-2015"></a>Skype for business Server 2015 的桌面客户端功能比较

**摘要：** Skype for Business Server 2015 或 Skype for Business Online 管理员可以使用这些表了解哪些客户端支持哪些功能。
  
 在部署或升级到 Skype for Business 之前，请检查您的组织中已使用的客户端。 使用下面的表格了解功能支持对这些客户端的影响。 这可帮助您传达对用户所做的更改、使滚动过程的步调以及充分了解升级到最新客户端的好处。
  
Skype for business Server 2015 中提供的某些功能在 Skype for Business Online 中不可用，有关详细信息，请参阅[Online 或混合用户帐户限制](desktop-feature-comparison.md#Online-Hybrid)。 Skype for business Online 管理员可能需要参考[skype for Business Online 服务说明](https://technet.microsoft.com/library/skype-for-business-online-service-description.aspx)，以了解有关可用的不同计划的信息。

有关 Skype for business Server 2019 上的客户端支持，请参阅[适用于 skype for business 2019 的桌面客户端功能比较](../../../SfBServer2019/plan/feature-comparison.md)。
  
下表显示了与 Skype for business Server 2015 或 Skype for business Online 一起使用的每个客户端可用的功能。 您可能还需要参阅[Skype for business 的移动客户端功能比较](mobile-feature-comparison.md)，以实现智能手机和平板电脑客户端功能比较。 您的组织购买的客户端访问许可证或用户订阅许可证也会影响对您的用户可用的功能。 您是否向用户部署完整或基本客户端取决于您的组织选择购买的许可证或计划。 有关详细信息，请参阅[许可指南](https://products.office.com/skype-for-business/it-pros)。
  
> [!IMPORTANT]
> Skype for Business Server 2015 和 Skype for business Online 支持以前发布的以下客户端： Lync 2013、Lync 2010、Lync 2010 移动、Lync Phone Edition 和 Lync 2010 助理。 有关这些客户端与其他服务器一起使用时的信息，请参阅 lync server [2013 的客户端比较表](https://technet.microsoft.com/library/gg425836%28v=ocs.15%29.aspx)和[lync Server 2010 的客户端比较表](https://technet.microsoft.com/library/gg425836%28v=ocs.14%29.aspx)。

> [!NOTE]
> **Lync 2010 助理**客户端在 Skype For business Online 中不受支持。

> [!NOTE]
> Skype for Business Web 应用浏览器客户端和 Skype 会议应用程序 Windows 10 应用仅提供[会议支持](desktop-feature-comparison.md#BKMK_Conferencing)。 有关这些客户端的详细信息，请参阅[规划会议客户端（Web 应用程序和会议应用程序）](meetings-clients.md) 。
  
## <a name="enhanced-presence-support"></a>增强状态支持

<a name="BKMK_EnhancedPresence"> </a>

此表涵盖了增强状态功能，这些功能超出了用户是否在线、脱机、忙碌等的简单指示。
  
|功能/功能|Skype for Business 2015 或2016客户端|Mac 版 Skype for Business|Lync 2013 客户端|Lync Windows 应用商店应用|Lync 2010 | Lync 2010 Attendant|Lync Phone Edition|Communicator for Mac 2011|Lync for Mac 2011|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|发布状态 |&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|
|查看状态   |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|查看状态注释和外出消息 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|添加自定义位置 |&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|添加自定义注释 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|对我的图片使用来自任意公共网站的照片（在 Skype for Business Online 中不可用） |&#x2714;||&#x2714;|||||||

 &#x2776; 不支持基于日历的忙/闲信息的发布状态。
  
## <a name="contacts-and-contact-groups-support"></a>联系人和联系人组支持

<a name="BKMK_Contacts"> </a>

此表涵盖了与管理 IM 和状态联系人相关的功能。

|功能/功能|Skype for Business 2015 或2016客户端|Mac 版 Skype for Business | Lync 2013 客户端 | Lync Windows 应用商店应用 | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|预填充的联系人列表 |&#x2714;|||||||||
|查看和修改联系人列表 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|标记状态更改警报的联系人 |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;||||
|控制隐私关系 |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|搜索企业通讯簿 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|搜索 Microsoft Outlook 联系人 |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|管理联系人组 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|展开通讯组和 Microsoft 365 组 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|搜索响应组  <br/> （在 Skype for Business Online 中不可用） |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|显示“最近的联系人”组 |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|显示“当前对话”组 |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|||
|显示其他联系人视图（例如平铺） |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|按组、关系或新用户（已将您添加到联系人列表中的人员）对联系人进行排序 |&#x2714;||&#x2714;|按组排序 |&#x2714;|&#x2714;||||
|按状态（可用性）对联系人进行排序 |&#x2714;||&#x2714;||&#x2714;|&#x2714;|||&#x2714;|
|搜索和添加 Exchange 联系人 |&#x2714;||&#x2714;||||||&#x2714;|

## <a name="im-support"></a>IM 支持

<a name="BKMK_IMSupport"> </a>

此表涵盖与 IM 支持相关的功能。

|功能/功能 | Skype for Business 2015 或2016客户端 | Mac 版 Skype for Business | Lync 2013 客户端 | Lync Windows 应用商店应用 | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|启动与联系人的 IM 或通过电子邮件发送给联系人 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|在多个 IM 对话之间导航/在单个选项卡式窗口中跟踪多个对话 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|在 Outlook 中记录 IM 对话 |&#x2714;|如果服务器端对话历史记录处于打开状态，&#x2714;  |&#x2714;|&#x2714;|&#x2714;|&#x2714;||保存在 Communicator for Mac 中 |保存在 Lync for Mac 中 |
|使用准备好的对话模板 |||||&#x2714;|&#x2714;||||
|检查拼写 |&#x2714;|&#x2714;||&#x2714;|||||&#x2714;|
|技能搜索（包含 SharePoint Server 集成）  <br/> （本地 Skype for Business Server 和本地 SharePoint 2013 是技能搜索所必需的。） |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||
|持久聊天（群聊）集成  <br/> （不适用于 Skype for business Online） |&#x2714;||&#x2714;|||||||
|通过一次单击将持久聊天室提升为 Skype for Business 会议  <br/> （不适用于 Skype for business Online） |&#x2714;||&#x2714;|||||||
|IM 窗口中的发件人和收件人的嵌入式图片 |&#x2714;||&#x2714;|&#x2714;||||||
|发送墨迹消息 ||||&#x2714;||||||
|接收墨迹消息 |&#x2714;||&#x2714;|&#x2714;||||||
|将 IM 邮件设置为高重要性 |&#x2714;||&#x2714;|||||||
|在对等 IM 对话中传输文件 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|

## <a name="meetings-support"></a>会议支持

<a name="BKMK_Conferencing"> </a>

此表涵盖与会议支持相关的功能。
  
> [!NOTE]
> Skype for business Online 的 skype for business 会议功能在 Skype for Business Online 独立计划1中不可用。  正在[停](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-for-business-online-plan-1-retirement)用计划1。

在 Skype 到 Skype 会话中，如果有访问共享功能的用户的邀请，则 Skype for business Online 计划1用户可以参与桌面共享和应用程序共享。
有关详细信息，请参阅[Skype For Business Online 服务说明](https://technet.microsoft.com/library/jj822172.aspx)。
  
|功能/功能 | Skype for Business 2016 客户端 | Mac 版 Skype for Business | Skype for Business Web 应用 | Skype for Business 2015 客户端 | Lync 2013 客户端 | Lync Windows 应用商店应用 | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|添加计算机音频 |&#x2714;|&#x2714;|&#x2714; （需要插件） |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|添加视频 |&#x2714;|&#x2714;|&#x2714; （需要插件） |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|&#x2714;|
|查看多方视频（库视图） |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|基于视频的屏幕共享 |&#x2714;|&#x2714;|&#x2714;仅查看 |||||||||
|使用会议中演示者控件 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|访问详细的会议名单 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|参与多方 IM |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|共享桌面（如果已启用） |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776;  （需要插件） |&#x2714;|&#x2714;||&#x2714;|||&#x2714; &#x2776; |&#x2714; &#x2776; |
|共享程序（如果已启用） |&#x2714;|仅查看   |&#x2714; （需要插件） |&#x2714;|&#x2714;||&#x2714;||||仅查看 |
|添加匿名参与者（如果已启用） |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|使用电话拨入式音频会议 |&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714;|&#x2714;|||&#x2714;|
|启动 "立即开会" 会议 |&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|添加并演示 Microsoft PowerPoint 文件 |&#x2714;| &#x2778; 注释不可用 |&#x2714;|&#x2714;|&#x2714;|仅显示 |&#x2714;|||| 仅 &#x2778; 视图，不提供批注 |
|导航 Microsoft PowerPoint 文件 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|添加和编辑 OneNote 会议笔记 |&#x2714;||仅编辑（不添加） |&#x2714;|&#x2714;|||||||
|使用白板 |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|发起投票 |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|上载文件以与其他人共享 |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|安排会议 |Outlook 或 Skype for Business Web 计划程序 |Outlook 或 Skype for Business Web 计划程序 |Skype for Business Web 计划程序 |Outlook 或 Skype for Business Web 计划程序 |Outlook 或 Lync Web 计划程序 |Outlook 或 Lync Web 计划程序 |Outlook ||||Outlook |
|问&amp;：经理 |&#x2714;|||||||||||
|禁用与会者视频|&#x2714;||&#x2714;|||||||||
 | |禁用会议即时消息  |&#x2714;||&#x2714;|&#x2714;|&#x2714;|||||||
|静音受众   |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|使所有人成为与会者 |&#x2714;||&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|生成 Skype 会议直播  |&#x2714;|||||||||||
|代理人可以代表代理者安排会议  |&#x2714;|&#x2714;|&#x2714;|||||||||
|在 Skype for Business 和 Outlook 之间同步委派 |&#x2714;||&#x2714;|||||||||
|设置视频焦点（锁定视频） |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|提供/获取屏幕共享的控制权 |&#x2714;||&#x2714;|||||||||

 &#x2776; 参与者无法控制由 Skype for Business 在 Mac 上共享的桌面、适用于 mac 的 Lync 2011 或 Mac 2011 用户的 Communicator。 Skype for business on Mac、Lync for Mac 2011 和 Communicator for Mac 2011 用户无法控制由 Windows 用户共享的桌面。 这也不适用于最大 OSX 上的 Skype for business Web 应用。
  
 &#x2777; 适用于 Skype for Business Online，此功能需要 Microsoft PSTN 会议、Exchange 统一消息或第三方音频会议提供商。
  
 &#x2778; Lync for Mac 2011 客户端在 Skype for Business Web 应用程序在会议中共享时无法查看 Microsoft Office 2013 PowerPoint 演示文稿。
  
## <a name="voice-telephony-support"></a>语音（电话）支持

<a name="BKMK_Telephony"> </a>

此表涵盖了与语音服务支持相关的功能。
  
> [!NOTE]
> Skype for business 语音（电话）功能仅限于某些 Skype for Business Online 订阅计划。 > 有关详细信息，请参阅[Skype For Business Online 服务说明](https://technet.microsoft.com/library/jj822172.aspx)。
  
| 功能/功能 | Skype for Business 2015 或2016客户端 | Mac 版 Skype for Business | Lync 2013 客户端 | Lync Windows 应用商店应用 | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|启动呼叫 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|单击呼叫联系人  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|转接呼叫 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|管理呼叫转接 |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|管理团队呼叫设置 |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|管理代理 |&#x2714;|&#x2714;需要 Skype for Business Server 2015 CU4 或更高版本 |&#x2714; &#x2776; ||&#x2714;||||&#x2714;|
|向响应组发起呼叫 |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|支持紧急服务（E-911）  |&#x2714;|&#x2714;需要 Skype for Business Server 2015 CU6 或更高版本 |&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|针对 E-911 呼叫的 SIP URI 的 IM 通知 |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|用于电子911呼叫的通讯组列表的 IM 通知 |&#x2714;||&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|连接到语音邮件、设置或更改问候语 |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|未接来电通知 |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|代表其他联系人发起呼叫（经理/代理方案） |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|||||
|处理其他人的呼叫（如果配置为代理的话） |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;|||
|管理大量呼叫 |||||&#x2714;|&#x2714;||||
|呼叫寄存  |&#x2714;||&#x2714; &#x2776; |||||||
|群呼代接  |&#x2714;||&#x2714; &#x2776; ||||&#x2714;|||
|基于位置的路由  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|管理响应组/团队呼叫组 |&#x2714;||&#x2714;|||||||

 &#x2776; 此功能在 Skype for Business Online 中不可用。
  
## <a name="external-users-support"></a>外部用户支持

<a name="BKMK_ExternalUsers"> </a>

此表涵盖与驻留在 PSTN 上的外部用户支持相关的功能。

|功能/功能 | Skype for Business 2015 或2016客户端 | Mac 版 Skype for Business | Lync 2013 客户端 | Lync Windows 应用商店应用 | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|启动与公共联系人的 IM  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|启动与联盟联系人的 IM |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|进行与外部用户的双方或多方呼叫  <br/> （在 Skype for Business Online 中不可用） |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|

## <a name="recording-support"></a>录制支持

<a name="BKMK_Recording"> </a>

此表涵盖与录制会议支持相关的功能。
  
| 未来/功能 * * | Skype for Business 2015 或2016客户端 | Mac 版 Skype for Business | Lync 2013 客户端 | Lync Windows 应用商店应用 | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|音频、视频、应用程序共享、桌面共享和上载的内容的客户端录制 |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|文件传输、共享的 OneNote 页面和 PowerPoint 注释的客户端录制 |&#x2714; &#x2777; ||&#x2714; &#x2777; ||&#x2714;|||||
|选择首选录制分辨率 |&#x2714;||&#x2714;|||||||

 在某些 Skype for Business Online 独立计划中，&#x2776; 录制不可用。 录制需要完整的 Skype for Business 客户端权限。
  
 在 Skype for Business Online 中，文件传输、共享的 OneNote 页面和 PowerPoint 注释的 &#x2777; 录制不可用。
  
## <a name="modern-authentication"></a>新式验证

<a name="BKMK_Recording"> </a>

此表涵盖需要支持新式身份验证的功能。
  
新式验证还需要在[采用新式验证时支持的 Skype For business 拓扑](../../plan-your-deployment/modern-authentication/topologies-supported.md)中介绍的拓扑。

| 功能/功能 | Skype for Business 2015 或2016客户端 | Mac 版 Skype for Business | Lync 2013 客户端 | Lync Windows 应用商店应用 | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|新式验证 |&#x2714;|&#x2714;|&#x2714;|||||||
|多因素身份验证  |&#x2714;|&#x2714;|&#x2714;|||||||
|基于证书的身份验证  |&#x2714; （仅加入域的设备）| &#x2714;|&#x2714; （仅加入域的设备）  |||||||
|Kerberos 身份验证 |&#x2714;||&#x2714;|||||||

## <a name="archiving-compliance-and-logging-support"></a>存档、合规和日志记录支持

<a name="BKMK_Archiving"> </a>

此表涵盖与支持存档和日志记录功能相关的功能。

| 功能/功能 | Skype for Business 2015 或2016客户端 | Mac 版 Skype for Business | Lync 2013 客户端 | Lync Windows 应用商店应用 | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | **Communicator for Mac 2011** | Lync for Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Outlook 对话历史记录中的 IM 对话的存档 |&#x2714; &#x2776; |如果已启用服务器端对话历史记录 &#x2714; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|&#x2714;||保存在 Communicator for Mac 中 |保存在 Lync for Mac 中 |
|音频、视频、应用程序共享、桌面共享和上载的内容的客户端存档 |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|文件传输、共享的 OneNote 页面和 PowerPoint 注释的客户端存档  <br/> （在 Skype for Business Online 中不可用）|&#x2714;||&#x2714;||&#x2714;|||||
|访问任务栏中的 Skype for Business 图标中的登录日志 |&#x2714;||&#x2714;|||||||

 &#x2776; 适用于 Skype for Business Online 用户，此功能需要 Exchange Online，并且由用户的 Exchange 邮箱就地保留属性控制。
  
## <a name="client-limitations"></a>客户端限制

<a name="Types"> </a>

### <a name="basic-client-limitations"></a>基本客户端限制

<a name="Full-Basic"> </a>

以下功能可使用完整客户端，不能在基本客户端中使用：

- 管理团队呼叫设置
- 管理代理
- 处理其他人的呼叫（如果配置为代理的话）
- 管理大量呼叫
- 向响应组发起呼叫
- 呼叫寄存
- 更改问候语
- 群呼代接
- 当禁用用户状态并使用旧版 Outlook 客户端（2013或更早版本）时，不会生成未接来电通知电子邮件

### <a name="online-or-hybrid-user-account-limitations"></a>联机或混合用户帐户限制

<a name="Online-Hybrid"> </a>

用户帐户可以是联机或本地存在的，这将影响该用户可用的功能。 在 Skype for Business Online 上具有帐户的用户将无法访问以下功能，即使是完整客户端也是如此：
  
- 增强状态：对图片使用来自任意公共网站的照片
- 联系人：搜索响应组
- IM 支持：持久聊天（组聊天）集成
- IM 支持：通过一次单击将持久聊天室提升为 Skype for Business 会议
- 外部用户：与外部用户进行两方或多方呼叫

## <a name="see-also"></a>另请参阅

<a name="Types"> </a>

[规划客户端和设备](clients-and-devices.md)

[使用 Windows Installer （MSI）的 Skype for Business 版本的最新更新](../../sfb-client-updates.md)
