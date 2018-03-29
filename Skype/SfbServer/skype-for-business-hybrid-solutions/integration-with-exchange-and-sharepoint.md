---
title: 与 Exchange 和 SharePoint 集成
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
description: 摘要： 了解业务服务器 2015年集成与交换和 SharePoint Skype。
ms.openlocfilehash: 5c266656e02113645fa2f8aaa2f28dc4953b4540
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="integration-with-exchange-and-sharepoint"></a>与 Exchange 和 SharePoint 集成
 
**摘要：**了解业务服务器 2015年集成与交换和 SharePoint 的 Skype。
  
您可以与 Microsoft Exchange Server 2016年、 Microsoft Exchange Server 2013年、 Microsoft Exchange Server 2010 中和 SharePoint 服务器上部署集成的业务服务器 2015年部署配置 Skype 并处于联机状态。 除非另行指定，否则所有客户端都支持下表中列出的功能。 有关客户端支持，请参阅[有关业务的 Skype 的桌面客户端功能比较](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)和 Skype 在线业务在[Skype 的在线业务的客户端](https://go.microsoft.com/fwlink/p/?LinkId=281902)的客户端比较表。
  
## <a name="integration-with-exchange-server"></a>与 Exchange Server 集成

下表列出了支持混合部署时与 Microsoft Exchange Server 集成中的功能。 
  
 **Skype 业务服务器上部署和内部部署的 Exchange**
  
| |
|**功能**|**说明**|
|:-----|:-----|
|Outlook 中的 IM/状态  <br/> |有关详细信息，请参阅[IM 和状态](http://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx)。  <br/> |
|通过 Outlook 安排和加入联机会议  <br/> |有关详细信息，请参阅[Exchange Server 具有的业务服务器 2015年的集成 Skype](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)。  <br/> |
|在 Outlook Web App 的 IM/显示状态  <br/> |有关详细信息，请参阅[配置中业务服务器 2015年的 Skype 的混合环境](../manage/authentication/configure-a-hybrid-environment.md)。  <br/> |
|通过 Outlook Web App 的日程安排和加入联机会议  <br/> ||
|移动客户端中的 IM/状态  <br/> ||
|在移动客户端中加入联机会议  <br/> |有关详细信息，请参阅[部署移动](http://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx)。  <br/> |
|根据 Outlook 日历闲/忙信息发布状态  <br/> ||
|联系人列表（通过统一联系人存储）  <br/> |要求交换 2016年或 Exchange 2013。  <br/> Lync 2013 或 Skype 业务桌面客户机是必需的。  <br/>  有关详细信息，请参阅[配置为使用统一的联系人存储库的业务服务器 2015年的 Skype](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)。  <br/> |
|Lync 2013 客户端，Skype 业务客户和 Lync Web 应用程序中的高分辨率联系人照片。  <br/> |要求交换 2016年或 Exchange 2013。  <br/> 有关详细信息，请参阅[配置使用的业务服务器 2015年的 Skype 的高分辨率照片](../deploy/integrate-with-exchange-server/high-resolution-photos.md)。  <br/> |
|会议委派  <br/> |只有当两个用户联机驻留在相同林中或者驻留在内部部署中时才支持。  <br/> |
|错过的对话历史记录和调用日志写入到用户的 exchange 邮箱  <br/> ||
|在 Exchang 中存档内容（IM 和会议）  <br/> |要求交换 2016年或 Exchange 2013。  <br/> 有关详细信息，请参阅[存档的部署清单](http://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)。  <br/> |
|搜索存档内容  <br/> |要求交换 2016年或 Exchange 2013。  <br/> |
|语音邮件  <br/> |有关详细信息，请参阅[部署内部 Exchange UM 到提供 Lync 服务器 2013年语音邮件](http://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)。  <br/> |
   
 **Skype 业务服务器内部部署和联机交换**
  
| |
|**功能**|**说明**|
|:-----|:-----|
|Outlook 中的 IM/状态  <br/> |有关详细信息，请参阅[配置业务服务器 2015年和 Outlook Web App 内部 Skype 之间的集成](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|通过 Outlook 安排和加入联机会议  <br/> ||
|在 Outlook Web App 的 IM/显示状态  <br/> |有关详细信息，请参阅[配置业务服务器 2015年和 Outlook Web App 内部 Skype 之间的集成](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|从 Outlook Web App 的日程安排和加入联机会议  <br/> |有关详细信息，请参阅[配置业务服务器 2015年和 Outlook Web App 内部 Skype 之间的集成](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|移动客户端中的 IM/状态  <br/> ||
|在移动客户端中加入联机会议  <br/> ||
|根据 Outlook 日历闲/忙信息发布状态  <br/> ||
|联系人列表（通过统一联系人存储）。  <br/> |仅 Lync Server 2013。 Lync 2013 或 Skype 业务桌面客户机是必需的。  <br/> 有关详细信息，请参阅[配置为使用统一的联系人存储库的业务服务器 2015年的 Skype](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Lync 2013 客户端，Skype 业务客户和 Lync Web 应用程序中的高分辨率联系人照片。  <br/> |有关详细信息，请参阅[配置使用的业务服务器 2015年的 Skype 的高分辨率照片](../deploy/integrate-with-exchange-server/high-resolution-photos.md)。  <br/> |
|会议委派  <br/> |只有当两个用户联机驻留在相同林中或者驻留在内部部署中时才支持。  <br/> |
|错过的对话历史记录和调用日志写入到用户的 Exchange 邮箱  <br/> ||
|在 Exchang 中存档内容（IM 和会议）  <br/> |有关详细信息，请参阅[存档的部署清单](http://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)。  <br/> |
|搜索存档内容  <br/> |有关详细信息，请参阅在[将 Exchange 配置为 SharePoint eDiscovery 中心](https://go.microsoft.com/fwlink/p/?LinkId=285448) <br/> |
|语音邮件  <br/> |有关详细信息，请参阅[提供 Lync 服务器 2013年用户语音邮件在 UM 承载 Exchange](http://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)。  <br/> |
   
 **Skype 的在线业务和内部部署的 Exchange**
  
| |
|**功能**|**说明**|
|:-----|:-----|
|Outlook 中的状态  <br/> ||
|通过 IM 响应、PSTN 呼叫、Skype 通话或从 Outlook 电子邮件进行视频通话  <br/> ||
|通过 Outlook 安排和加入联机会议  <br/> ||
|移动客户端中的 IM/状态  <br/> ||
|在移动客户端中加入联机会议  <br/> ||
|根据 Outlook 日历闲/忙信息发布状态  <br/> ||
|错过的对话历史记录和调用日志写入到用户的 exchange 邮箱  <br/> ||
|Lync 2013 或 Skype 业务客户端中的高分辨率联系人照片。  <br/> |要求交换 2016年或 Exchange 2013。 这不是支持 Lync Web 应用程序时的在线业务在 Skype 上驻留用户。  <br/> |
|会议委派  <br/> |只有当两个用户联机驻留在相同林中或者驻留在内部部署中时才支持。  <br/> |
|错过的对话历史记录和调用日志写入到用户的 Exchange 邮箱  <br/> ||
|服务器端对话历史记录  <br/> ||
   
 **Skype 的在线业务和在线交换**
  
| |
|**功能**|**说明**|
|:-----|:-----|
|Outlook 中的 IM/状态  <br/> ||
|通过 Outlook 安排和加入联机会议  <br/> ||
|在 Outlook Web App 的 IM/显示状态  <br/> ||
|从 Outlook Web App 的日程安排和加入联机会议  <br/> ||
|移动客户端中的 IM/状态  <br/> ||
|在移动客户端中加入联机会议  <br/> ||
|根据 Outlook 日历闲/忙信息发布状态  <br/> ||
|错过的对话历史记录和调用日志写入到用户的 exchange 邮箱  <br/> ||
|联系人列表（通过统一联系人存储）  <br/> |Lync Server 2013 或 Skype 业务客户端所需的  <br/> |
|Lync 2013，Skype 业务客户端，并且 Lync Web 应用程序中的高分辨率联系人照片  <br/> ||
|会议委派  <br/> |只有当两个用户联机驻留在相同林中或者驻留在内部部署中时才支持。  <br/> |
|在 Exchang 中存档内容（IM 和会议）  <br/> ||
|搜索存档内容  <br/> ||
|语音邮件  <br/> ||
   
## <a name="integration-with-sharepoint"></a>与 SharePoint 集成

下表列出了支持混合部署时与 SharePoint 集成中的功能。
  
||**SharePoint 部署**|**SharePoint 在线**|
|:-----|:-----|:-----|
|**Skype 业务服务器 2015年的场所** <br/> | 技能搜索 <br/>  在 SharePoint 中的存在 <br/> | 在 SharePoint 中的存在 <br/> |
|**Skype 的在线业务** <br/> | 在 SharePoint 中的存在 <br/> | 在 SharePoint 中的存在 <br/> |
   

