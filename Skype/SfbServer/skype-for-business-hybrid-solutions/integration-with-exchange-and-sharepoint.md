---
title: 与 Exchange 和 SharePoint 集成
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
description: 摘要： 了解与 Exchange 和 SharePoint 的业务服务器 2015年集成 Skype。
ms.openlocfilehash: 5599ebcb4e4b9209f0f36ff767b8d261fbffba60
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23243254"
---
# <a name="integration-with-exchange-and-sharepoint"></a>与 Exchange 和 SharePoint 集成

**摘要：** 了解与 Exchange 和 SharePoint 的业务服务器 2015年集成的 Skype。

您可以为与 Microsoft Exchange Server 2016、 Microsoft Exchange Server 2013、 Microsoft Exchange Server 2010 和 SharePoint Server，这两个本地集成的业务服务器 2015年部署配置 Skype 和联机。 除非另行指定，否则所有客户端都支持下表中列出的功能。 有关客户端的详细信息支持，请参阅在[业务 online Skype 的客户端](https://go.microsoft.com/fwlink/p/?LinkId=281902)的业务联机客户端比较表的[Skype for Business 的桌面客户端功能比较](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)和 Skype。

## <a name="integration-with-exchange-server"></a>与 Exchange Server 集成

下表列出了与 Microsoft Exchange Server 集成时的混合部署中支持的功能。

 **Skype 的本地业务服务器和本地 Exchange**


|**功能**|**说明**|
|:-----|:-----|
|Outlook 中的 IM/状态  <br/> |有关详细信息，请参阅[IM 和状态](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx)。  <br/> |
|通过 Outlook 安排和加入联机会议  <br/> |有关详细信息，请参阅[业务服务器 2015 与 Exchange Server 的集成 Skype](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)。  <br/> |
|Outlook Web App 中的 IM/状态  <br/> |有关详细信息，请参阅[Configure Business Server 2015 的 Skype 的混合环境](../manage/authentication/configure-a-hybrid-environment.md)。  <br/> |
|通过 Outlook Web App 的日程安排和加入联机会议  <br/> ||
|移动客户端中的 IM/状态  <br/> ||
|在移动客户端中加入联机会议  <br/> |有关详细信息，请参阅[部署移动](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx)。  <br/> |
|根据 Outlook 日历闲/忙信息发布状态  <br/> ||
|联系人列表（通过统一联系人存储）  <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> Lync 2013 或业务桌面客户端的 Skype 是必需的。  <br/>  有关详细信息，请参阅[配置的业务服务器 2015 使用统一联系人存储库的 Skype](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)。  <br/> |
|Lync 2013 客户端，Skype 业务客户端和 Lync Web App 中的高分辨率联系人照片。  <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> 有关详细信息，请参阅[Configure 使用中的业务服务器 2015 Skype 高分辨率照片](../deploy/integrate-with-exchange-server/high-resolution-photos.md)。  <br/> |
|会议委派  <br/> |只有当两个用户联机驻留在相同林中或者驻留在内部部署中时才支持。 有关详细信息，请参阅[业务混合解决方案的 Skype](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|错过的对话历史记录和呼叫日志写入到用户的 exchange 邮箱  <br/> ||
|在 Exchang 中存档内容（IM 和会议）  <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> 有关详细信息，请参阅[存档的部署清单](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)。  <br/> |
|搜索存档内容  <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> |
|语音邮件  <br/> |有关详细信息，请参阅[部署内部部署 Exchange UM 提供 Lync Server 2013 语音邮件](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)。  <br/> |

 **Skype Business Server 本地和 Exchange Online**


|**功能**|**说明**|
|:-----|:-----|
|Outlook 中的 IM/状态  <br/> |有关详细信息，请参阅[配置集成业务服务器 2015年和 Outlook Web App 的内部部署 Skype](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|通过 Outlook 安排和加入联机会议  <br/> ||
|Outlook Web App 中的 IM/状态  <br/> |有关详细信息，请参阅[配置集成业务服务器 2015年和 Outlook Web App 的内部部署 Skype](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|从 Outlook Web App 的日程安排和加入联机会议  <br/> |有关详细信息，请参阅[配置集成业务服务器 2015年和 Outlook Web App 的内部部署 Skype](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|移动客户端中的 IM/状态  <br/> ||
|在移动客户端中加入联机会议  <br/> ||
|根据 Outlook 日历闲/忙信息发布状态  <br/> ||
|联系人列表（通过统一联系人存储）。  <br/> |仅限 Lync Server 2013。 Lync 2013 或业务桌面客户端的 Skype 是必需的。  <br/> 有关详细信息，请参阅[配置的业务服务器 2015 使用统一联系人存储库的 Skype](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Lync 2013 客户端，Skype 业务客户端和 Lync Web App 中的高分辨率联系人照片。  <br/> |有关详细信息，请参阅[Configure 使用中的业务服务器 2015 Skype 高分辨率照片](../deploy/integrate-with-exchange-server/high-resolution-photos.md)。  <br/> |
|会议委派  <br/> |只有当两个用户联机驻留在相同林中或者驻留在内部部署中时才支持。 有关详细信息，请参阅[业务混合解决方案的 Skype](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|错过的对话历史记录和呼叫日志写入到用户的 Exchange 邮箱  <br/> ||
|在 Exchang 中存档内容（IM 和会议）  <br/> |有关详细信息，请参阅[存档的部署清单](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)。  <br/> |
|搜索存档内容  <br/> |有关详细信息，请参阅在[配置 Exchange for SharePoint 电子数据展示中心](https://go.microsoft.com/fwlink/p/?LinkId=285448) <br/> |
|语音邮件  <br/> |有关详细信息，请参阅[提供 Lync Server 2013 用户语音邮件在 Hosted Exchange UM](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)。  <br/> |

 **Skype 业务在线和本地 Exchange**


|**功能**|**说明**|
|:-----|:-----|
|Outlook 中的状态  <br/> ||
|通过 IM 响应、PSTN 呼叫、Skype 通话或从 Outlook 电子邮件进行视频通话  <br/> ||
|通过 Outlook 安排和加入联机会议  <br/> ||
|移动客户端中的 IM/状态  <br/> ||
|在移动客户端中加入联机会议  <br/> ||
|根据 Outlook 日历闲/忙信息发布状态  <br/> ||
|错过的对话历史记录和呼叫日志写入到用户的 exchange 邮箱  <br/> ||
|Lync 2013 或 Skype 业务客户端中的高分辨率联系人照片。  <br/> |需要 Exchange 2016 或 Exchange 2013。 这是时不支持 Lync Web App 中的业务联机用户驻留在 Skype。  <br/> |
|会议委派  <br/> |只有当两个用户联机驻留在相同林中或者驻留在内部部署中时才支持。 有关详细信息，请参阅[业务混合解决方案的 Skype](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|错过的对话历史记录和呼叫日志写入到用户的 Exchange 邮箱  <br/> ||
|服务器端对话历史记录  <br/> ||

 **Skype for Business Online 和 Exchange Online**


|**功能**|**说明**|
|:-----|:-----|
|Outlook 中的 IM/状态  <br/> ||
|通过 Outlook 安排和加入联机会议  <br/> ||
|Outlook Web App 中的 IM/状态  <br/> ||
|从 Outlook Web App 的日程安排和加入联机会议  <br/> ||
|移动客户端中的 IM/状态  <br/> ||
|在移动客户端中加入联机会议  <br/> ||
|根据 Outlook 日历闲/忙信息发布状态  <br/> ||
|错过的对话历史记录和呼叫日志写入到用户的 exchange 邮箱  <br/> ||
|联系人列表（通过统一联系人存储）  <br/> |Lync Server 2013 或业务客户端所需的 Skype  <br/> |
|Lync 2013，Skype 业务客户端和 Lync Web App 中的高分辨率联系人照片  <br/> ||
|会议委派  <br/> |只有当两个用户联机驻留在相同林中或者驻留在内部部署中时才支持。 有关详细信息，请参阅[业务混合解决方案的 Skype](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|在 Exchang 中存档内容（IM 和会议）  <br/> ||
|搜索存档内容  <br/> ||
|语音邮件  <br/> ||

## <a name="integration-with-sharepoint"></a>与 SharePoint 集成

下表列出了在混合部署时与 SharePoint 集成支持的功能。

||**SharePoint 内部部署**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype 业务服务器 2015年本地** <br/> | 技能搜索 <br/>  在 SharePoint 中的状态 <br/> | 在 SharePoint 中的状态 <br/> |
|**Skype for Business Online** <br/> | 在 SharePoint 中的状态 <br/> | 在 SharePoint 中的状态 <br/> |


