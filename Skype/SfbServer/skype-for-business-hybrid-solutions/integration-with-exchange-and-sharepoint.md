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
ms.openlocfilehash: 01ebbdd94098fa9f7785f41fedbcbdfe7589f03e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092830"
---
# <a name="integration-with-exchange-and-sharepoint"></a>与 Exchange 和 SharePoint 集成

**摘要：** 了解 Skype for Business Server 2015 与 Exchange 和 SharePoint 的集成。

你可以配置 Skype for Business Server 2015 部署，以与本地和联机的 Microsoft Exchange Server 2016、Microsoft Exchange Server 2013、Microsoft Exchange Server 2010 和 SharePoint Server 集成。 除非另行指定，否则所有客户端均支持下表中列出的功能。 有关客户端支持详细信息，请参阅 Skype [for Business](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) 的桌面客户端功能比较和 Skype for Business Online 客户端比较表。Skype for Business Online 客户端 [比较](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)表。

## <a name="integration-with-exchange-server"></a>与 Exchange Server

下表列出了混合部署中与混合部署集成时Microsoft Exchange Server。

 **本地 Skype for Business Server 和 Exchange 本地**


|**功能**|**备注**|
|:-----|:-----|
|Outlook 中的 IM/状态  <br/> |有关详细信息，请参阅 [IM 和状态](/previous-versions/office/lync-server-2013/lync-server-2013-im-and-presence)。  <br/> |
|通过 Outlook 安排和加入联机会议  <br/> |有关详细信息，请参阅将 [Skype for Business Server 2015](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)与 Exchange Server 集成。  <br/> |
|IM/状态Outlook Web App  <br/> |有关详细信息，请参阅在 [Skype for Business Server 2015](../manage/authentication/configure-a-hybrid-environment.md)中配置混合环境。  <br/> |
|通过会议安排和加入Outlook Web App  <br/> ||
|移动客户端中的 IM/状态  <br/> ||
|在移动客户端中加入联机会议  <br/> |有关详细信息，请参阅[部署移动。](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility)  <br/> |
|根据 Outlook 日历忙/闲信息发布状态  <br/> ||
|联系人列表 (统一联系人存储)   <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> 需要 Lync 2013 或 Skype for Business 桌面客户端。  <br/>  有关详细信息，请参阅配置 [Skype for Business Server 2015 以使用统一的联系人存储](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)。  <br/> |
|Lync 2013 客户端、Skype for Business 客户端和 Lync Web App 中的高分辨率联系人照片。  <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> 有关详细信息，请参阅[Configure the use of high-resolution photos in Skype for Business Server 2015。](../deploy/integrate-with-exchange-server/high-resolution-photos.md)  <br/> 对于适用于 MAC 和移动的 Skype for Business 应用上的照片，必须设置 Skype for Business Server 2015 和 Exchange Server 之间的集成，如在 [Skype for Business Server](../deploy/integrate-with-exchange-server/configure-partner-applications.md)和 Exchange Server 中配置合作伙伴应用程序中所述。 <br/> |
|会议委派  <br/> |只有当两个用户都联机位于同一林中或两个用户都位于本地时，才受支持。 有关详细信息，请参阅 [Skype for Business 混合解决方案](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|错过的对话历史记录和呼叫日志将写入到用户的 Exchange 邮箱  <br/> ||
|存档 Exchange (IM 和会议) 内容  <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> 有关详细信息，请参阅[Deployment Checklist for Archiving。](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving)  <br/> |
|搜索存档内容  <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> |
|语音邮件  <br/> |有关详细信息，请参阅部署本地 [Exchange UM 以提供 Lync Server 2013 语音邮件](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail)。  <br/> |

 **本地 Skype for Business Server 和 Exchange Online**


|**功能**|**备注**|
|:-----|:-----|
|Outlook 中的 IM/状态  <br/> |有关详细信息，请参阅 [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|通过 Outlook 安排和加入联机会议  <br/> ||
|IM/状态Outlook Web App  <br/> |有关详细信息，请参阅 [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|从会议安排和加入联机Outlook Web App  <br/> |有关详细信息，请参阅 [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|移动客户端中的 IM/状态  <br/> ||
|在移动客户端中加入联机会议  <br/> ||
|根据 Outlook 日历忙/闲信息发布状态  <br/> ||
|联系人列表 (统一联系人存储) 。  <br/> |仅 Lync Server 2013。 需要 Lync 2013 或 Skype for Business 桌面客户端。  <br/> 有关详细信息，请参阅配置 [Skype for Business Server 2015 以使用统一的联系人存储](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Lync 2013 客户端、Skype for Business 客户端和 Lync Web App 中的高分辨率联系人照片。  <br/> |有关详细信息，请参阅[Configure the use of high-resolution photos in Skype for Business Server 2015。](../deploy/integrate-with-exchange-server/high-resolution-photos.md)  <br/> 对于适用于 MAC 和移动的 Skype for Business 应用上的照片，必须设置 Skype for Business Server 2015 和 Exchange Server 之间的集成，如配置本地 [Skype for Business Server](../deploy/integrate-with-exchange-server/outlook-web-app.md)和 Outlook Web App 之间的集成中所述。 <br/> |
|会议委派  <br/> |只有当两个用户都联机位于同一林中或两个用户都位于本地时，才受支持。 有关详细信息，请参阅 [Skype for Business 混合解决方案](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|错过的对话历史记录和呼叫日志将写入用户的 Exchange 邮箱  <br/> ||
|存档 Exchange (IM 和会议) 内容  <br/> |有关详细信息，请参阅[Deployment Checklist for Archiving。](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving)  <br/> |
|搜索存档内容  <br/> |有关详细信息，请参阅为 [SharePoint 电子数据展示中心配置 Exchange](/exchange/configure-exchange-for-sharepoint-ediscovery-center-exchange-2013-help) <br/> |
|语音邮件  <br/> |有关详细信息，请参阅在托管 Exchange UM 上提供 [Lync Server 2013 用户语音邮件](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)。  <br/> |

 **Skype for Business Online 和本地 Exchange**


|**功能**|**备注**|
|:-----|:-----|
|Outlook 中的状态  <br/> ||
|通过 IM、PSTN 呼叫、Skype 呼叫或来自 Outlook 电子邮件的视频呼叫进行响应  <br/> ||
|通过 Outlook 安排和加入联机会议  <br/> ||
|移动客户端中的 IM/状态  <br/> ||
|在移动客户端中加入联机会议  <br/> ||
|根据 Outlook 日历忙/闲信息发布状态  <br/> ||
|错过的对话历史记录和呼叫日志将写入到用户的 Exchange 邮箱  <br/> ||
|Lync 2013 或 Skype for Business 客户端中的高分辨率联系人照片。  <br/> |需要 Exchange 2016 或 Exchange 2013。 当用户位于 Skype for Business Online 上时，Lync Web App 不支持此功能。  <br/> |
|会议委派  <br/> |只有当两个用户都联机位于同一林中或两个用户都位于本地时，才受支持。 有关详细信息，请参阅 [Skype for Business 混合解决方案](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|错过的对话历史记录和呼叫日志将写入用户的 Exchange 邮箱  <br/> ||
|服务器端对话历史记录  <br/> ||

 **Skype for Business Online 和 Exchange Online**


|**功能**|**备注**|
|:-----|:-----|
|Outlook 中的 IM/状态  <br/> ||
|通过 Outlook 安排和加入联机会议  <br/> ||
|IM/状态Outlook Web App  <br/> ||
|从会议安排和加入联机Outlook Web App  <br/> ||
|移动客户端中的 IM/状态  <br/> ||
|在移动客户端中加入联机会议  <br/> ||
|根据 Outlook 日历忙/闲信息发布状态  <br/> ||
|错过的对话历史记录和呼叫日志将写入到用户的 Exchange 邮箱  <br/> ||
|联系人列表 (统一联系人存储)   <br/> |需要 Lync Server 2013 或 Skype for Business 客户端  <br/> |
|Lync 2013、Skype for Business 客户端和 Lync Web App 中的高分辨率联系人照片  <br/> ||
|会议委派  <br/> |只有当两个用户都联机位于同一林中或两个用户都位于本地时，才受支持。 有关详细信息，请参阅 [Skype for Business 混合解决方案](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|存档 Exchange (IM 和会议) 内容  <br/> ||
|搜索存档内容  <br/> ||
|Voicemail  <br/> ||

## <a name="integration-with-sharepoint"></a>与 SharePoint 集成

下表列出了与 SharePoint 集成时混合部署中支持的功能。

||**SharePoint 本地部署**|**SharePoint Online**|
|:-----|:-----|:-----|
|**本地 Skype for Business Server 2015** <br/> | 技能搜索 <br/>  SharePoint 中的状态 <br/> | SharePoint 中的状态 <br/> |
|**Skype for Business Online** <br/> | SharePoint 中的状态 <br/> | SharePoint 中的状态 <br/> |