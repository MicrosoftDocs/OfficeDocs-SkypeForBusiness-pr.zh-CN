---
title: 与 Exchange 和 SharePoint 集成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
- SPO_Content
ms.custom: ''
ms.assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
description: 摘要：了解 Skype for Business Server 2015 与 Exchange 和 SharePoint 的集成。
ms.openlocfilehash: 9d5f665d5bffede2de10c77735ea76fe55337af8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799802"
---
# <a name="integration-with-exchange-and-sharepoint"></a>与 Exchange 和 SharePoint 集成

**摘要：** 了解 Skype for Business Server 2015 与 Exchange 和 SharePoint 的集成。

你可以将 Skype for business Server 2015 部署配置为与 Microsoft Exchange Server 2016、Microsoft Exchange Server 2013、Microsoft Exchange Server 2010 和 SharePoint Server （本地和联机）集成。 除非另行指定，否则所有客户端都支持下表中列出的功能。 有关客户端支持的详细信息，请参阅 skype for business 的[桌面客户端功能比较](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)和 skype For business online 客户端比较客户端与[skype for](https://go.microsoft.com/fwlink/p/?LinkId=281902)business online 的比较表。

## <a name="integration-with-exchange-server"></a>与 Exchange Server 集成

下表列出了与 Microsoft Exchange Server 集成时的混合部署中支持的功能。

 **本地 Skype for business 服务器和 Exchange 内部部署**


|**功能**|**注释**|
|:-----|:-----|
|Outlook 中的 IM/状态  <br/> |有关详细信息，请参阅[IM 和联机状态](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx)。  <br/> |
|通过 Outlook 安排和加入联机会议  <br/> |有关详细信息，请参阅将[Skype For Business 服务器2015与 Exchange Server 集成](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)。  <br/> |
|Outlook Web App 中的 IM/状态  <br/> |有关详细信息，请参阅[在 Skype For Business Server 2015 中配置混合环境](../manage/authentication/configure-a-hybrid-environment.md)。  <br/> |
|通过 Outlook Web App 安排和加入联机会议  <br/> ||
|移动客户端中的 IM/状态  <br/> ||
|在移动客户端中加入联机会议  <br/> |有关详细信息，请参阅[部署移动性](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx)。  <br/> |
|根据 Outlook 日历闲/忙信息发布状态  <br/> ||
|联系人列表（通过统一联系人存储）  <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> 需要 Lync 2013 或 Skype for business 桌面客户端。  <br/>  有关详细信息，请参阅[配置 Skype For Business Server 2015 以使用统一联系人存储](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)。  <br/> |
|Lync 2013 客户端、Skype for Business 客户端和 Lync Web App 中的高分辨率联系人照片。  <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> 有关详细信息，请参阅[在 Skype for Business Server 2015 中配置高分辨率照片的使用](../deploy/integrate-with-exchange-server/high-resolution-photos.md)。  <br/> 对于 MAC 版 Skype for Business 应用和手机版的照片，必须按照在[skype for Business server 和 Exchange server 中配置合作伙伴应用程序](../deploy/integrate-with-exchange-server/configure-partner-applications.md)中的说明，设置 skype For business server 2015 和 exchange server 之间的集成。 <br/> |
|会议委派  <br/> |只有当两个用户联机驻留在相同林中或者驻留在内部部署中时才支持。 有关详细信息，请参阅[Skype For business 混合解决方案](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|错过的对话历史记录和呼叫日志将写入用户的 exchange 邮箱  <br/> ||
|在 Exchang 中存档内容（IM 和会议）  <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> 有关详细信息，请参阅[存档的部署清单](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)。  <br/> |
|搜索存档内容  <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> |
|语音邮件  <br/> |有关详细信息，请参阅[部署本地 EXCHANGE UM 以提供 Lync Server 2013 语音邮件](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)。  <br/> |

 **本地和 Exchange Online 上的 Skype for Business 服务器**


|**功能**|**注释**|
|:-----|:-----|
|Outlook 中的 IM/状态  <br/> |有关详细信息，请参阅[配置本地 Skype for Business Server 2015 和 Outlook Web App 之间的集成](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|通过 Outlook 安排和加入联机会议  <br/> ||
|Outlook Web App 中的 IM/状态  <br/> |有关详细信息，请参阅[配置本地 Skype for Business Server 2015 和 Outlook Web App 之间的集成](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|从 Outlook Web App 安排和加入联机会议  <br/> |有关详细信息，请参阅[配置本地 Skype for Business Server 2015 和 Outlook Web App 之间的集成](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|移动客户端中的 IM/状态  <br/> ||
|在移动客户端中加入联机会议  <br/> ||
|根据 Outlook 日历闲/忙信息发布状态  <br/> ||
|联系人列表（通过统一联系人存储）。  <br/> |仅限 Lync Server 2013。 需要 Lync 2013 或 Skype for business 桌面客户端。  <br/> 有关详细信息，请参阅[配置 Skype For Business Server 2015 以使用统一联系人存储](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Lync 2013 客户端、Skype for Business 客户端和 Lync Web App 中的高分辨率联系人照片。  <br/> |有关详细信息，请参阅[在 Skype for Business Server 2015 中配置高分辨率照片的使用](../deploy/integrate-with-exchange-server/high-resolution-photos.md)。  <br/> 对于适用于 MAC 和手机版的 Skype for business 应用程序中的照片，Skype for business Server 2015 和 Exchange Server 之间的集成必须按照[配置本地 skype for Business 服务器和 Outlook Web app 之间](../deploy/integrate-with-exchange-server/outlook-web-app.md)的说明进行设置。 <br/> |
|会议委派  <br/> |只有当两个用户联机驻留在相同林中或者驻留在内部部署中时才支持。 有关详细信息，请参阅[Skype For business 混合解决方案](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|错过的对话历史记录和呼叫日志将写入用户的 Exchange 邮箱  <br/> ||
|在 Exchang 中存档内容（IM 和会议）  <br/> |有关详细信息，请参阅[存档的部署清单](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)。  <br/> |
|搜索存档内容  <br/> |有关详细信息，请参阅[配置 SharePoint 电子数据展示中心的 Exchange](https://go.microsoft.com/fwlink/p/?LinkId=285448) <br/> |
|语音邮件  <br/> |有关详细信息，请参阅向[Lync Server 2013 用户提供托管 EXCHANGE UM 上的语音邮件](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)。  <br/> |

 **Skype for business Online 和本地 Exchange**


|**功能**|**注释**|
|:-----|:-----|
|Outlook 中的状态  <br/> ||
|通过 IM 响应、PSTN 呼叫、Skype 通话或从 Outlook 电子邮件进行视频通话  <br/> ||
|通过 Outlook 安排和加入联机会议  <br/> ||
|移动客户端中的 IM/状态  <br/> ||
|在移动客户端中加入联机会议  <br/> ||
|根据 Outlook 日历闲/忙信息发布状态  <br/> ||
|错过的对话历史记录和呼叫日志将写入用户的 exchange 邮箱  <br/> ||
|Lync 2013 或 Skype for business 客户端中的高分辨率联系人照片。  <br/> |需要 Exchange 2016 或 Exchange 2013。 当用户托管在 Skype for Business Online 上时，Lync Web App 不支持此功能。  <br/> |
|会议委派  <br/> |只有当两个用户联机驻留在相同林中或者驻留在内部部署中时才支持。 有关详细信息，请参阅[Skype For business 混合解决方案](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|错过的对话历史记录和呼叫日志将写入用户的 Exchange 邮箱  <br/> ||
|服务器端对话历史记录  <br/> ||

 **Skype for Business Online 和 Exchange Online**


|**功能**|**注释**|
|:-----|:-----|
|Outlook 中的 IM/状态  <br/> ||
|通过 Outlook 安排和加入联机会议  <br/> ||
|Outlook Web App 中的 IM/状态  <br/> ||
|从 Outlook Web App 安排和加入联机会议  <br/> ||
|移动客户端中的 IM/状态  <br/> ||
|在移动客户端中加入联机会议  <br/> ||
|根据 Outlook 日历闲/忙信息发布状态  <br/> ||
|错过的对话历史记录和呼叫日志将写入用户的 exchange 邮箱  <br/> ||
|联系人列表（通过统一联系人存储）  <br/> |需要 Lync Server 2013 或 Skype for business 客户端  <br/> |
|Lync 2013 中的高分辨率联系人照片、Skype for Business 客户端和 Lync Web App  <br/> ||
|会议委派  <br/> |只有当两个用户联机驻留在相同林中或者驻留在内部部署中时才支持。 有关详细信息，请参阅[Skype For business 混合解决方案](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|在 Exchang 中存档内容（IM 和会议）  <br/> ||
|搜索存档内容  <br/> ||
|语音邮件  <br/> ||

## <a name="integration-with-sharepoint"></a>与 SharePoint 集成

下表列出了与 SharePoint 集成时的混合部署中支持的功能。

||**SharePoint 本地版**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype for business 服务器本地2015** <br/> | 技能搜索 <br/>  SharePoint 中的状态 <br/> | SharePoint 中的状态 <br/> |
|**Skype for Business Online** <br/> | SharePoint 中的状态 <br/> | SharePoint 中的状态 <br/> |


