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
description: 摘要：了解 Skype for Business Server 2015 与 Exchange 和 SharePoint 集成。
ms.openlocfilehash: f8d57924d3a82effbc552de660b973aa36e7b8fe
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52236988"
---
# <a name="integration-with-exchange-and-sharepoint"></a>与 Exchange 和 SharePoint 集成

**摘要：** 了解 Skype for Business Server 2015 与 Exchange 和 SharePoint 集成。

您可以配置 Skype for Business Server 2015 部署，以与 Microsoft Exchange Server 2016、Microsoft Exchange Server 2013、Microsoft Exchange Server 2010 和 SharePoint Server（本地和联机）集成。 除非另行指定，否则所有客户端均支持下表中列出的功能。 有关客户端支持详细信息，请参阅适用于 Skype for Business 的桌面客户端功能[比较](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)和 Skype for Business Online 客户端比较表（位于[Skype for Business Online）。](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

## <a name="integration-with-exchange-server"></a>与 Exchange Server

下表列出了混合部署中与混合部署集成时Microsoft Exchange Server。

 **Skype for Business Server本地部署和Exchange部署**


|**功能**|**备注**|
|:-----|:-----|
|IM/状态Outlook  <br/> |有关详细信息，请参阅 [IM 和状态](/previous-versions/office/lync-server-2013/lync-server-2013-im-and-presence)。  <br/> |
|通过会议安排和加入Outlook  <br/> |有关详细信息，请参阅 Integrate [Skype for Business Server 2015 with Exchange Server](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)。  <br/> |
|im/Presence in Outlook Web App  <br/> |有关详细信息，请参阅在[Skype for Business Server 2015 中配置混合环境](../manage/authentication/configure-a-hybrid-environment.md)。  <br/> |
|通过会议安排和加入联机Outlook Web App  <br/> ||
|移动客户端中的 IM/状态  <br/> ||
|在移动客户端中加入联机会议  <br/> |有关详细信息，请参阅[部署移动。](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility)  <br/> |
|根据日历忙/Outlook信息发布状态  <br/> ||
|联系人列表 (统一联系人存储)   <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> Lync 2013 或 Skype for Business桌面客户端是必需的。  <br/>  有关详细信息，请参阅 Configure [Skype for Business Server 2015 to use the unified contact store](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)。  <br/> |
|Lync 2013 客户端、Skype for Business客户端和 Lync Web App 中的高分辨率联系人照片。  <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> 有关详细信息，请参阅 Configure [the use of high-resolution photos in Skype for Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md)。  <br/> 对于 Skype for Business MAC 和移动设备应用上的照片，必须设置 Skype for Business Server 2015 和 Exchange Server 之间的集成，如在 Skype for Business Server 和[Exchange Server](../deploy/integrate-with-exchange-server/configure-partner-applications.md)中配置合作伙伴应用程序中所述。 <br/> |
|会议委派  <br/> |只有当两个用户都联机位于同一林中或两个用户都位于本地时，才受支持。 有关详细信息，请参阅混合[Skype for Business解决方案](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|错过的对话历史记录和呼叫日志将写入到用户的 Exchange 邮箱  <br/> ||
|存档 (IM 和会议) 内容Exchange  <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> 有关详细信息，请参阅[Deployment Checklist for Archiving。](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving)  <br/> |
|搜索存档内容  <br/> |需要 Exchange 2016 或 Exchange 2013。  <br/> |
|语音邮件  <br/> |有关详细信息，请参阅[Deploying On-Premises Exchange UM to Provide Lync Server 2013 Voice Mail](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail)。  <br/> |

 **Skype for Business Server本地和Exchange Online**


|**功能**|**备注**|
|:-----|:-----|
|IM/状态Outlook  <br/> |有关详细信息，请参阅 Configure [integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|通过会议安排和加入Outlook  <br/> ||
|im/Presence in Outlook Web App  <br/> |有关详细信息，请参阅 Configure [integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|从会议安排和加入联机Outlook Web App  <br/> |有关详细信息，请参阅 Configure [integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|移动客户端中的 IM/状态  <br/> ||
|在移动客户端中加入联机会议  <br/> ||
|根据日历忙/Outlook信息发布状态  <br/> ||
|联系人列表 (统一联系人存储) 。  <br/> |仅 Lync Server 2013。 Lync 2013 或 Skype for Business桌面客户端是必需的。  <br/> 有关详细信息，请参阅 Configure [Skype for Business Server 2015 to use the unified contact store](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Lync 2013 客户端、Skype for Business客户端和 Lync Web App 中的高分辨率联系人照片。  <br/> |有关详细信息，请参阅 Configure [the use of high-resolution photos in Skype for Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md)。  <br/> 对于 Skype for Business MAC 和移动版应用上的照片，必须设置 Skype for Business Server 2015 和 Exchange Server 之间的集成，如配置本地 Skype for Business Server 和 Outlook Web App 之间的[集成](../deploy/integrate-with-exchange-server/outlook-web-app.md)中所述。 <br/> |
|会议委派  <br/> |只有当两个用户都联机位于同一林中或两个用户都位于本地时，才受支持。 有关详细信息，请参阅混合[Skype for Business解决方案](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|错过的对话历史记录和呼叫日志将写入用户Exchange邮箱  <br/> ||
|存档 (IM 和会议) 内容Exchange  <br/> |有关详细信息，请参阅[Deployment Checklist for Archiving。](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving)  <br/> |
|搜索存档内容  <br/> |有关详细信息，请参阅 Configure [Exchange for SharePoint eDiscovery Center](/exchange/configure-exchange-for-sharepoint-ediscovery-center-exchange-2013-help) <br/> |
|语音邮件  <br/> |有关详细信息，请参阅在托管 UM 上提供[Lync Server 2013 Exchange语音邮件](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)。  <br/> |

 **Skype for Business联机Exchange本地部署**


|**功能**|**备注**|
|:-----|:-----|
|状态Outlook  <br/> ||
|通过 IM、PSTN 呼叫、Skype呼叫或视频呼叫从电子邮件Outlook响应  <br/> ||
|通过会议安排和加入联机Outlook  <br/> ||
|移动客户端中的 IM/状态  <br/> ||
|在移动客户端中加入联机会议  <br/> ||
|根据日历忙/Outlook信息发布状态  <br/> ||
|错过的对话历史记录和呼叫日志将写入到用户的 Exchange 邮箱  <br/> ||
|Lync 2013 或 Skype for Business 客户端中的高分辨率联系人照片。  <br/> |需要 Exchange 2016 或 Exchange 2013。 当用户位于 Skype for Business Online 上时，Lync Web App 中Skype for Business此功能。  <br/> |
|会议委派  <br/> |只有当两个用户都联机位于同一林中或两个用户都位于本地时，才受支持。 有关详细信息，请参阅混合[Skype for Business解决方案](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|错过的对话历史记录和呼叫日志将写入用户Exchange邮箱  <br/> ||
|服务器端对话历史记录  <br/> ||

 **Skype for Business联机和Exchange Online**


|**功能**|**备注**|
|:-----|:-----|
|IM/状态Outlook  <br/> ||
|通过会议安排和加入联机Outlook  <br/> ||
|im/Presence in Outlook Web App  <br/> ||
|从会议安排和加入联机Outlook Web App  <br/> ||
|移动客户端中的 IM/状态  <br/> ||
|在移动客户端中加入联机会议  <br/> ||
|根据日历忙/Outlook信息发布状态  <br/> ||
|错过的对话历史记录和呼叫日志将写入到用户的 Exchange 邮箱  <br/> ||
|联系人列表 (统一联系人存储)   <br/> |需要 Lync Server 2013 Skype for Business客户端  <br/> |
|Lync 2013、Skype for Business 客户端和 Lync Web App 中的高分辨率联系人照片  <br/> ||
|会议委派  <br/> |只有当两个用户都联机位于同一林中或两个用户都位于本地时，才受支持。 有关详细信息，请参阅混合[Skype for Business解决方案](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|存档 (IM 和会议) 内容Exchange  <br/> ||
|搜索存档内容  <br/> ||
|语音邮件  <br/> ||

## <a name="integration-with-sharepoint"></a>与 SharePoint

下表列出了混合部署中与混合部署集成时SharePoint。

||**SharePoint 本地部署**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype for Business Server 2015 本地部署** <br/> | 技能搜索 <br/>  状态SharePoint <br/> | 状态SharePoint <br/> |
|**Skype for Business Online** <br/> | 状态SharePoint <br/> | 状态SharePoint <br/> |