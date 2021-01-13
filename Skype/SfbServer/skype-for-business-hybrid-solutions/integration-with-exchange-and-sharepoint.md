---
title: 与 Exchange 和 SharePoint 集成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 943392fbd63238621825edad380ac9c140935635
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821102"
---
# <a name="integration-with-exchange-and-sharepoint"></a>与 Exchange 和 SharePoint 集成

**摘要：** 了解 Skype for Business Server 2015 与 Exchange 和 SharePoint 的集成。

可以配置 Skype for Business Server 2015 部署，以与 Microsoft Exchange Server 2016、Microsoft Exchange Server 2013、Microsoft Exchange Server 2010 和 SharePoint Server（本地和联机）集成。 除非另行指定，否则所有客户端均支持下表中列出的功能。 有关客户端支持详细信息，请参阅 Skype for Business 客户端比较表的 [Skype for Business](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) 和 Skype for [Business](https://go.microsoft.com/fwlink/p/?LinkId=281902)Online 客户端比较表。

## <a name="integration-with-exchange-server"></a>与Exchange Server

下表列出了混合部署中与混合部署集成时支持Microsoft Exchange Server。

 **本地 Skype for Business Server 和本地 Exchange**


|**功能**|**备注**|
|:-----|:-----|
|Outlook 中的 IM/状态  <br/> |有关详细信息，请参阅 [IM 和状态](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx)。  <br/> |
|通过 Outlook 安排和加入联机会议  <br/> |有关详细信息，请参阅将[Skype for Business Server 2015 与 Exchange Server。](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)  <br/> |
|IM/Presence in Outlook Web App  <br/> |有关详细信息，请参阅在 [Skype for Business Server 2015](../manage/authentication/configure-a-hybrid-environment.md)中配置混合环境。  <br/> |
|通过会议安排和加入联机Outlook Web App  <br/> ||
|移动客户端中的 IM/状态  <br/> ||
|在移动客户端中加入联机会议  <br/> |有关详细信息，请参阅部署[移动。](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx)  <br/> |
|根据 Outlook 日历忙/闲信息发布状态  <br/> ||
|通过统一 (存储功能访问联系人列表)   <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> Lync 2013 或 Skype for Business 桌面客户端是必需的。  <br/>  有关详细信息，请参阅配置 [Skype for Business Server 2015 以使用统一的联系人存储](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)。  <br/> |
|Lync 2013 客户端、Skype for Business 客户端和 Lync Web App 中的高分辨率联系人照片。  <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> 有关详细信息，请参阅在 [Skype for Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md)中配置高分辨率照片的使用。  <br/> 对于适用于 MAC 和移动的 Skype for Business 应用上的照片，必须设置 Skype for Business Server 2015 和 Exchange Server 之间的集成，如 [在 Skype for Business Server](../deploy/integrate-with-exchange-server/configure-partner-applications.md)和 Exchange Server 中配置合作伙伴应用程序中所述。 <br/> |
|会议委派  <br/> |仅在两个用户都联机位于同一林中或两个用户都位于本地时受支持。 有关详细信息，请参阅 [Skype for Business 混合解决方案](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|错过的对话历史记录和呼叫日志将写入用户的 Exchange 邮箱  <br/> ||
|在 Exchange (IM 和会议) 存档内容  <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> 有关详细信息，请参阅 [存档的部署清单](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)。  <br/> |
|搜索存档内容  <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> |
|语音邮件  <br/> |有关详细信息，请参阅部署 [本地 Exchange UM 以提供 Lync Server 2013 语音邮件](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)。  <br/> |

 **本地 Skype for Business Server 和 Exchange Online**


|**功能**|**备注**|
|:-----|:-----|
|Outlook 中的 IM/状态  <br/> |有关详细信息，请参阅配置本地[Skype for Business Server 2015](../deploy/integrate-with-exchange-server/outlook-web-app.md)与 Outlook Web App <br/> |
|通过 Outlook 安排和加入联机会议  <br/> ||
|IM/Presence in Outlook Web App  <br/> |有关详细信息，请参阅配置本地[Skype for Business Server 2015](../deploy/integrate-with-exchange-server/outlook-web-app.md)与 Outlook Web App <br/> |
|从会议安排和加入联机Outlook Web App  <br/> |有关详细信息，请参阅配置本地[Skype for Business Server 2015](../deploy/integrate-with-exchange-server/outlook-web-app.md)与 Outlook Web App <br/> |
|移动客户端中的 IM/状态  <br/> ||
|在移动客户端中加入联机会议  <br/> ||
|根据 Outlook 日历忙/闲信息发布状态  <br/> ||
|联系人列表 (统一联系人存储) 。  <br/> |仅 Lync Server 2013。 Lync 2013 或 Skype for Business 桌面客户端是必需的。  <br/> 有关详细信息，请参阅配置 [Skype for Business Server 2015 以使用统一的联系人存储](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Lync 2013 客户端、Skype for Business 客户端和 Lync Web App 中的高分辨率联系人照片。  <br/> |有关详细信息，请参阅在 [Skype for Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md)中配置高分辨率照片的使用。  <br/> 对于适用于 MAC 和移动的 Skype for Business 应用上的照片，必须按配置本地 Skype for Business Server 与 Outlook Web App 之间的集成中所述设置 Skype for Business Server 2015 和 [Exchange Server 之间的集成](../deploy/integrate-with-exchange-server/outlook-web-app.md)。 <br/> |
|会议委派  <br/> |仅在两个用户都联机位于同一林中或两个用户都位于本地时受支持。 有关详细信息，请参阅 [Skype for Business 混合解决方案](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|错过的对话历史记录和呼叫日志将写入用户的 Exchange 邮箱  <br/> ||
|在 Exchange (IM 和会议) 存档内容  <br/> |有关详细信息，请参阅 [存档的部署清单](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)。  <br/> |
|搜索存档内容  <br/> |有关详细信息，请参阅配置 [Exchange for SharePoint 电子数据展示中心](https://go.microsoft.com/fwlink/p/?LinkId=285448) <br/> |
|语音邮件  <br/> |有关详细信息，请参阅在托管 Exchange UM 上提供 [Lync Server 2013](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)用户语音邮件。  <br/> |

 **Skype for Business Online 和本地 Exchange**


|**功能**|**备注**|
|:-----|:-----|
|Outlook 中的状态  <br/> ||
|通过 IM、PSTN 呼叫、Skype 呼叫或来自 Outlook 电子邮件的视频呼叫进行响应  <br/> ||
|通过 Outlook 安排和加入联机会议  <br/> ||
|移动客户端中的 IM/状态  <br/> ||
|在移动客户端中加入联机会议  <br/> ||
|根据 Outlook 日历忙/闲信息发布状态  <br/> ||
|错过的对话历史记录和呼叫日志将写入用户的 Exchange 邮箱  <br/> ||
|Lync 2013 或 Skype for Business 客户端中的高分辨率联系人照片。  <br/> |需要 Exchange 2016 或 Exchange 2013。 当用户位于 Skype for Business Online 上时，Lync Web App 不支持此功能。  <br/> |
|会议委派  <br/> |仅在两个用户都联机位于同一林中或两个用户都位于本地时受支持。 有关详细信息，请参阅 [Skype for Business 混合解决方案](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|错过的对话历史记录和呼叫日志将写入用户的 Exchange 邮箱  <br/> ||
|服务器端对话历史记录  <br/> ||

 **Skype for Business Online 和 Exchange Online**


|**功能**|**备注**|
|:-----|:-----|
|Outlook 中的 IM/状态  <br/> ||
|通过 Outlook 安排和加入联机会议  <br/> ||
|IM/Presence in Outlook Web App  <br/> ||
|从会议安排和加入联机Outlook Web App  <br/> ||
|移动客户端中的 IM/状态  <br/> ||
|在移动客户端中加入联机会议  <br/> ||
|根据 Outlook 日历忙/闲信息发布状态  <br/> ||
|错过的对话历史记录和呼叫日志将写入用户的 Exchange 邮箱  <br/> ||
|通过统一 (存储功能访问联系人列表)   <br/> |需要 Lync Server 2013 或 Skype for Business 客户端  <br/> |
|Lync 2013、Skype for Business 客户端和 Lync Web App 中的高分辨率联系人照片  <br/> ||
|会议委派  <br/> |仅在两个用户都联机位于同一林中或两个用户都位于本地时受支持。 有关详细信息，请参阅 [Skype for Business 混合解决方案](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|在 Exchange (IM 和会议) 存档内容  <br/> ||
|搜索存档内容  <br/> ||
|语音邮件  <br/> ||

## <a name="integration-with-sharepoint"></a>与 SharePoint 集成

下表列出了与 SharePoint 集成时混合部署中支持的功能。

||**SharePoint 本地部署**|**SharePoint Online**|
|:-----|:-----|:-----|
|**本地 Skype for Business Server 2015** <br/> | 技能搜索 <br/>  SharePoint 中的状态 <br/> | SharePoint 中的状态 <br/> |
|**Skype for Business Online** <br/> | SharePoint 中的状态 <br/> | SharePoint 中的状态 <br/> |


