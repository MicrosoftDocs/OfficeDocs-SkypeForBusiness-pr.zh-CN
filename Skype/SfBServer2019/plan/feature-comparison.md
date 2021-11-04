---
title: Skype for Business Server 2019 的桌面客户端功能比较
ms.author: v-mahoffman
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 16b14d59-7737-4f9d-aa4d-83765a18ea07
description: 摘要：Skype for Business Server 2019 或 Skype for Business Online 管理员可以使用这些表了解哪些客户端支持哪些功能。
ms.openlocfilehash: 556b88bfe587d1d5a5a1c78461863f0ae8f8fbbf
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777402"
---
# <a name="desktop-client-feature-comparison-for-skype-for-business-server-2019"></a>Skype for Business Server 2019 的桌面客户端功能比较

**摘要：Skype for Business Server** 2019 或 Skype for Business Online 管理员可以使用这些表了解哪些客户端支持哪些功能。

 在部署或升级到 Skype for Business Server，请检查组织中已在使用哪些客户端。 使用下表可了解功能支持对客户端的影响。 这可以帮助您将更改传达给用户、调整推出过程的速度，并完全了解升级到最新客户端的好处。

Skype for Business Server 2019 中提供某些功能在 Skype for Business Online 中不可用;请参阅[联机或混合用户帐户限制](feature-comparison.md#Online-Hybrid)了解具体信息。 Skype for Business在线管理员可能希望参考 Skype for Business [Online 服务说明](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)，了解他们可用的不同计划。

下表显示了与 Skype for Business Server 2019 或 Skype for Business Online 一起提供的功能。 您可能还需要参考移动客户端功能[比较，了解](../../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)Skype for Business和平板电脑客户端功能比较。 组织购买的客户端访问许可证或用户订阅许可证还会影响哪些功能可供用户使用。 是向用户部署完整客户端还是基本客户端取决于组织选择购买的许可证或计划。 有关详细信息 [，请参阅许可](https://products.office.com/skype-for-business/it-pros) 指南。

> [!IMPORTANT]
> Skype for Business Server 2019 和 Skype for Business Online 支持之前发布的以下客户端：Lync 2013、Skype for Business 2015 和 Skype for Business 2016 以及 Skype for Business 2019 客户端。 有关与其他服务器一同使用的这些客户端的信息，请参阅[Client comparison tables for Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-desktop-client-comparison-tables)和 Desktop client feature comparison for Skype for Business [2015。](../../SfbServer/plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) 


> [!NOTE]
> 会议Skype for Business Web应用客户端和Skype会议应用Windows 10仅提供[会议支持](feature-comparison.md#BKMK_Conferencing)。 请参阅 [Plan for Meetings clients (Web App and Meetings App) ](../../SfbServer/plan-your-deployment/clients-and-devices/meetings-clients.md) 了解有关这些客户端的信息。

## <a name="enhanced-presence-support"></a>增强状态支持
<a name="BKMK_EnhancedPresence"> </a>

此表涵盖的增强状态功能超出了用户是否处于联机、脱机、忙碌等状态的简单指示之外。 


| 功能                                                                                  | Skype for Business 2015、2016 或 2019 客户端 | Mac 版 Skype for Business | Lync 2013 客户端 |
|:----------------------------------------------------------------------------------------------------|:----------------------------------------------|:--------------------------|:-----------------|
| 发布状态                                                                                      | &#x2714;                                      | &#x2714; &#x2776;         | &#x2714;         |
| 查看状态                                                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| 查看状态注释和外出消息                                                        | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| 添加自定义位置                                                                               | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| 添加自定义注释                                                                                   | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| 将来自任何公共网站的照片用于"我的图片"  <br/>  (Online Skype for Business中)  | &#x2714;                                      |                           | &#x2714;         |

 &#x2776;不支持基于日历忙/闲信息的发布状态。

## <a name="contacts-and-contact-groups-support"></a>联系人和联系人组支持
<a name="BKMK_Contacts"> </a>

此表涵盖与管理 IM 和状态联系人相关的功能。 


| 功能                                                                            | Skype for Business 2015、2016 或 2019 客户端 | Mac 版 Skype for Business | Lync 2013 客户端 |
|:----------------------------------------------------------------------------------------------|:----------------------------------------------|:--------------------------|:-----------------|
| 预填充的联系人列表                                                                   | &#x2714;                                      |                           |                  |
| 查看和修改联系人列表                                                                 | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| 标记状态更改警报的联系人                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| 控制隐私关系                                                                 | &#x2714;                                      |                           | &#x2714;         |
| 搜索企业通讯簿                                                             | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| 搜索 Microsoft Outlook 联系人                                                             | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| 管理联系人组                                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| 展开通讯组和Microsoft 365组                                              | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| 搜索响应组  <br/>  (Online Skype for Business中)                 | &#x2714;                                      |                           | &#x2714;         |
| 显示“最近的联系人”组                                                                 | &#x2714;                                      |                           | &#x2714;         |
| 显示“当前对话”组                                                           | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| 显示其他联系人视图（例如平铺）                                           | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| 按组、关系或新联系人 (已添加到联系人列表联系人列表的联系人进行排序)  | &#x2714;                                      |                           | &#x2714;         |
| 按状态和可用性 (对联系人)                                                         | &#x2714;                                      |                           | &#x2714;         |
| 搜索和添加Exchange联系人                                                              | &#x2714;                                      |                           | &#x2714;         |

## <a name="im-support"></a>IM 支持
<a name="BKMK_IMSupport"> </a>

此表涵盖与 IM 支持相关的功能。

|功能 | Skype for Business 2015、2016 或 2019 客户端 | Mac 版 Skype for Business | Lync 2013 客户端 | 
|:-----|:-----|:-----|:-----|  
|与联系人发起 IM 或向联系人发送电子邮件  |&#x2714;|&#x2714;|&#x2714;|  
|在多个 IM 对话之间导航/在单个选项卡式窗口中跟踪多个对话   |&#x2714;|&#x2714;|&#x2714;| 
|在 Outlook 中记录 IM 对话  |&#x2714;|&#x2714; 如果服务器端对话历史记录已打开   |&#x2714;|   
|检查拼写 |&#x2714;|&#x2714;||   
|技能搜索 (服务器SharePoint集成)   <br/>  (技能Skype for Business Server 2013 SharePoint本地部署和本地)   |&#x2714;||&#x2714;|
|持久聊天 (群聊) 集成  <br/>  (Online Skype for Business不可用) |&#x2714;||&#x2714;|  
|单击一下即可将持久聊天室Skype for Business会议升级为会议  <br/>  (Online Skype for Business不可用)  |&#x2714;||&#x2714;| 
|IM 窗口中发件人和接收方的内联图片 |&#x2714;||&#x2714;| 
|接收墨迹消息 |&#x2714;||&#x2714;| 
|将 IM 消息设置为高重要性 |&#x2714;||&#x2714;|

## <a name="meetings-support"></a>会议支持
<a name="BKMK_Conferencing"> </a>

此表涵盖与会议支持相关的功能。

> [!NOTE]
>  Skype for Business Online 独立计划 1 中Skype for Business会议功能。  计划 1 即将 [停用](../../SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-for-business-online-plan-1-retirement.md
)。

在Skype到 Skype 会话中，如果 Skype for Business Online 计划 1 用户受邀访问共享功能，则他们可以参与桌面共享和应用程序共享。
有关详细信息，请参阅 Skype for Business [Online 服务说明](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)。 

|功能 | Skype for Business 2016 客户端 | Mac 版 Skype for Business | Skype for Business Web 应用 | Skype for Business 2015 客户端 | Lync 2013 客户端 | 
|:-----|:-----|:-----|:-----|:-----|:-----|  
|添加计算机音频  |&#x2714;|&#x2714;|&#x2714; (需要插件)   |&#x2714;|&#x2714;| 
|添加视频 |&#x2714;|&#x2714;|&#x2714; (需要插件)  |&#x2714;|&#x2714;| 
|查看多方视频 (库视图)   |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|基于视频的屏幕共享    |&#x2714;|&#x2714;|&#x2714;仅查看   ||| 
|使用会议中演示者控件 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;| 
|访问详细的会议名单 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|  
|参与多方 IM |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|  
|共享桌面（如果已启用）  |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776;  (需要插件)  |&#x2714;| &#x2714;|
|共享程序（如果已启用） |&#x2714;|仅查看   |&#x2714; (需要插件)   |&#x2714;|&#x2714;|   
|添加匿名参与者（如果已启用） |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|使用拨入音频会议&#x2777;|&#x2714; |&#x2714;|&#x2714;  |&#x2714;|&#x2714;  |
|启动"立即开会"会议|&#x2714;|&#x2714;||&#x2714;|&#x2714;|  
|添加并演示 Microsoft PowerPoint 文件 |&#x2714;| &#x2778;批注不可用   |&#x2714;|&#x2714;|&#x2714;| 
|导航 Microsoft PowerPoint文件 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;| 
|添加和编辑OneNote会议笔记  |&#x2714;||仅编辑 (添加)   |&#x2714;|&#x2714;|
|使用白板 |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|发起投票 |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Upload文件与其他人共享 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|安排会议 |Outlook 或 Skype for Business Web计划程序  |Outlook 或 Skype for Business Web计划程序 |Skype for Business Web计划程序 |Outlook 或 Skype for Business Web计划程序   |Outlook 或 Lync Web 计划程序 |  
|问答 &amp; 管理器 |&#x2714;|||||
|禁用与会者视频 |&#x2714;||&#x2714;|||
|禁用会议 IM |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|将受众设为静音 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|使每个人都成为与会者 |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|生成Skype 会议广播 |&#x2714;|||||
|代理人可以代表代理者安排会议 |&#x2714;|&#x2714;|&#x2714;|||
|在代理与Skype for Business之间Outlook |&#x2714;||&#x2714;|&#x2714;|| 
|设置视频聚焦 (锁定视频)  |&#x2714;||&#x2714;|&#x2714;|&#x2714;| 
|授予/控制屏幕共享  |&#x2714;||&#x2714;|||

 &#x2776;参与者无法控制 Mac 上的 Skype for Business、Lync for Mac 2011 或 Communicator for Mac 2011 用户共享的桌面。 Skype for Business Mac、Lync for Mac 2011 和 Communicator for Mac 2011 用户无法控制由 Windows 用户共享的桌面。 这同样对在最大 OSX Skype for Business Web应用不起作用。

 &#x2777; 对于 Skype for Business Online，此功能需要 Microsoft PSTN 会议、Exchange统一消息或第三方音频会议提供商。

 &#x2778; Lync for Mac 2011 客户端Microsoft Office在会议PowerPoint共享 2013 Skype for Business Web应用。

&#x2779;对于 Skype for Business 2016 应用，必须使用即点即用版本 16.0.4227 或更高版本。

&#x2780;对于 Skype for Business 2015 应用，你必须拥有 9 月更新版本 15.0.4747 或更高版本。

## <a name="voice-telephony-support"></a>语音 (电话) 支持
<a name="BKMK_Telephony"> </a>

此表涵盖与语音服务支持相关的功能。

> [!NOTE]
> Skype for BusinessVoice (Telephony) features are limited to certain Skype for Business Online subscription plans. 有关详细信息，请参阅 Skype for Business [Online 服务说明](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)。 

 | 功能 | Skype for Business 2015、2016 或 2019 客户端 | Mac 版 Skype for Business | Lync 2013 客户端 |  
|:-----|:-----|:-----|:-----| 
|发起呼叫 |&#x2714;|&#x2714;|&#x2714;|
|单击呼叫联系人 |&#x2714;|&#x2714;|&#x2714;|
|转接呼叫 |&#x2714;|&#x2714;|&#x2714;|  
|管理呼叫转接 |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|管理团队呼叫设置 |&#x2714;||&#x2714; &#x2776; |
|管理代理 |&#x2714;|&#x2714;   |&#x2714; &#x2776; |
|向响应组发起呼叫|&#x2714;||&#x2714; &#x2776; |
|支持 E-911 (紧急)  |&#x2714;|&#x2714; |&#x2714; &#x2776; |
|针对 E-911 呼叫 (SIP URI) IM 通知 |&#x2714;|&#x2714;|&#x2714;|
|向通讯组列表发送 E-911 呼叫的 IM 通知|&#x2714;|&#x2714;|&#x2714;|
|连接语音邮件，设置或更改问候语 |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|未接来电通知 |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|代表其他联系人发起呼叫（经理/代理方案） |&#x2714;|&#x2714;|&#x2714; &#x2776; |
|处理其他人的呼叫（如果配置为代理的话） |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|呼叫寄存 |&#x2714;||&#x2714; &#x2776; |
|群呼代接 |&#x2714;||&#x2714; &#x2776; |
|基于位置的路由 |&#x2714;|&#x2714;|&#x2714;| 
|管理响应组/团队呼叫组 |&#x2714;||&#x2714;|

 &#x2776;此功能在 Skype for Business Online 中不可用。

## <a name="external-users-support"></a>外部用户支持
<a name="BKMK_ExternalUsers"> </a>

此表涵盖与支持位于 PSTN 上的外部用户相关的功能。


|功能 | Skype for Business 2015、2016 或 2019 客户端 | Mac 版 Skype for Business | Lync 2013 客户端 |  
|:-----|:-----|:-----|:-----|  
|启动与公共联系人的 IM |&#x2714;|&#x2714;|&#x2714;| 
|启动与联盟联系人的 IM |&#x2714;|&#x2714;|&#x2714;| 
|进行与外部用户的双方或多方呼叫  <br/>  (Online Skype for Business中)   |&#x2714;|&#x2714;|&#x2714;| 

## <a name="recording-support"></a>录制支持
<a name="BKMK_Recording"> </a>

此表涵盖与录制会议支持相关的功能。

| 功能 | Skype for Business 2015、2016 或 2019 客户端 | Mac 版 Skype for Business | Lync 2013 客户端 |   
|:-----|:-----|:-----|:-----|  
|客户端录制音频、视频、应用程序共享、桌面共享和上载的内容 |&#x2714; &#x2776; ||&#x2714; &#x2776; |
|客户端记录文件传输、共享OneNote页和PowerPoint批注| &#x2714; &#x2777; ||&#x2714; &#x2777; |
|选择首选录制分辨率  |&#x2714;||&#x2714;|

 &#x2776;联机独立计划的某些Skype for Business录制不可用。 录制需要完全Skype for Business客户端权限。

 &#x2777;联机版中OneNote文件传输、共享PowerPoint和Skype for Business记录。

## <a name="modern-authentication"></a>新式验证
<a name="BKMK_Recording"> </a>

此表涵盖需要新式验证支持的功能。 

新式验证还需要新式验证支持Skype for Business[中介绍的拓扑](../../SfbServer/plan-your-deployment/modern-authentication/topologies-supported.md)。


 | 功能 | Skype for Business 2015、2016 或 2019 客户端 | Mac 版 Skype for Business | Lync 2013 客户端 | 
|:-----|:-----|:-----|:-----|  
|新式验证 |&#x2714;|&#x2714;|&#x2714;|
|多重身份验证|&#x2714;|&#x2714;|&#x2714;|
|基于证书的身份验证 |&#x2714; (已加入域的设备)  |&#x2714;|&#x2714; (已加入域的设备)   |
|Kerberos 身份验证 |&#x2714;||&#x2714;|

## <a name="archiving-compliance-and-logging-support"></a>存档、合规性和日志记录支持
<a name="BKMK_Archiving"> </a>

此表涵盖与存档和日志记录功能支持相关的功能。


 | 功能 | Skype for Business 2015、2016 或 2019 客户端 | Mac 版 Skype for Business | Lync 2013 客户端 |  
|:-----|:-----|:-----|:-----|  
|在对话历史记录中存档OUTLOOK IM 对话|&#x2714; &#x2776; |&#x2714; 如果服务器端对话历史记录已打开  |&#x2714; &#x2776; | 
|音频、视频、应用程序共享、桌面共享和上载内容的客户端存档  |&#x2714; &#x2776; ||&#x2714; &#x2776; |
|客户端存档文件传输、共享OneNote页面PowerPoint注释 (在 Skype for Business Online)   |&#x2714;||&#x2714;|
|从任务栏中的"Skype for Business"图标访问登录日志 |&#x2714;||&#x2714;|

 &#x2776; 对于 Skype for Business Online 用户，此功能Exchange Online由用户的 Exchange 邮箱和保留In-Place控制。

## <a name="client-limitations"></a>客户端限制
<a name="Types"> </a>

### <a name="basic-client-limitations"></a>基本客户端限制
<a name="Full-Basic"> </a>

以下功能使用完整客户端提供，在基本客户端中不可用： 

- 管理团队呼叫设置

- 管理代理

- 代表其他联系人发起呼叫（经理/代理方案）

- 处理其他人的呼叫（如果配置为代理的话）

- 管理大量呼叫

- 向响应组发起呼叫

- 呼叫寄存

- 更改问候语

- 群呼代接

### <a name="online-or-hybrid-user-account-limitations"></a>联机或混合用户帐户限制
<a name="Online-Hybrid"> </a>

用户帐户可以联机或本地存在，这会影响该用户可用的功能。 拥有 Skype for Business Online 帐户的用户将无法访问以下功能，即使使用完整客户端： 

- 增强状态：将来自任何公共网站的照片用于"我的图片"

- 联系人：搜索响应组

- IM 支持：持久聊天 (群聊) 集成

- IM 支持：单击一下即可将持久聊天室升级Skype for Business会议

- 外部用户：与外部用户进行双方或多方呼叫

## <a name="see-also"></a>另请参阅
<a name="Types"> </a>

[规划客户端和设备](../../SfbServer/plan-your-deployment/clients-and-devices/clients-and-devices.md)

[使用 MSI 安装程序Skype for Business安装程序Windows版本的 (更新) ](../../SfbServer/sfb-client-updates.md)