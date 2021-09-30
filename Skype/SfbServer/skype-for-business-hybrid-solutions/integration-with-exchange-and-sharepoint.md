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
ms.localizationpriority: medium
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
ms.openlocfilehash: a2caf4cf409f3631ebc0a85cd2957b30e9d36d2a
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013136"
---
# <a name="integration-with-exchange-and-sharepoint"></a>与 Exchange 和 SharePoint 集成

**摘要：** 了解 Skype for Business Server 2015 与 Exchange 和 SharePoint 集成。

您可以配置 Skype for Business Server 2015 部署，以与 Microsoft Exchange Server 2016、Microsoft Exchange Server 2013、Microsoft Exchange Server 2010 和 SharePoint Server（本地和联机）集成。 除非另行指定，否则所有客户端均支持下表中列出的功能。 有关客户端支持详细信息，请参阅 Client for [Skype for Business](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) online 中的桌面客户端功能比较和 Skype for Business Online 客户端比较Skype for Business[表](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)。

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

## <a name="integration-with-exchange-server"></a>与 Exchange Server

下表列出了混合部署中与混合部署集成时Microsoft Exchange Server。

 **Skype for Business Server本地部署和Exchange部署部署**


|**功能**|**备注**|
|:-----|:-----|
|im/Presence in Outlook  <br/> |有关详细信息，请参阅 [IM 和状态](/previous-versions/office/lync-server-2013/lync-server-2013-im-and-presence)。  <br/> |
|通过会议安排和加入联机Outlook  <br/> |有关详细信息，请参阅 Integrate [Skype for Business Server 2015 with Exchange Server](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)。  <br/> |
|im/Presence in Outlook Web App  <br/> |有关详细信息，请参阅在[Skype for Business Server 2015 中配置混合环境](../manage/authentication/configure-a-hybrid-environment.md)。  <br/> |
|通过会议安排和加入联机Outlook Web App  <br/> ||
|移动客户端中的 IM/状态  <br/> ||
|在移动客户端中加入联机会议  <br/> |有关详细信息，请参阅[部署移动。](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility)  <br/> |
|根据日历忙/Outlook信息发布状态  <br/> ||
|联系人列表 (统一联系人存储)   <br/> |需要Exchange 2016 或 Exchange 2013。  <br/> Lync 2013 或 Skype for Business桌面客户端是必需的。  <br/>  有关详细信息，请参阅 Configure [Skype for Business Server 2015 to use the unified contact store](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)。  <br/> |
|Lync 2013 客户端、Skype for Business客户端和 Lync Web App 中的高分辨率联系人照片。  <br/> |需要Exchange 2016 或 Exchange 2013。  <br/> 有关详细信息，请参阅 Configure [the use of high-resolution photos in Skype for Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md)。  <br/> 对于 Skype for Business MAC 和移动版应用上的照片，必须设置 Skype for Business Server 2015 和 Exchange Server 之间的集成，如在 Skype for Business Server 和[Exchange Server](../deploy/integrate-with-exchange-server/configure-partner-applications.md)中配置合作伙伴应用程序中所述。 <br/> |
|会议委派  <br/> |只有当两个用户都联机位于同一林中或两个用户都位于本地时，才受支持。 有关详细信息，请参阅配置 Skype for Business Server[和 Teams 之间的混合Teams。](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md) <br/> |
|错过的对话历史记录和呼叫日志将写入到用户的 Exchange 邮箱  <br/> ||
|将内容 (IM 和会议) 存档Exchange  <br/> |需要Exchange 2016 或 Exchange 2013。  <br/> 有关详细信息，请参阅[Deployment Checklist for Archiving。](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving)  <br/> |
|搜索存档内容  <br/> |需要Exchange 2016 或 Exchange 2013。  <br/> |
|语音邮件  <br/> |有关详细信息，请参阅[Deploying On-Premises Exchange UM to Provide Lync Server 2013 Voice Mail](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail)。  <br/> |

 **Skype for Business Server本地和Exchange Online**


|**功能**|**备注**|
|:-----|:-----|
|im/Presence in Outlook  <br/> |有关详细信息，请参阅 Configure [integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|通过会议安排和加入联机Outlook  <br/> ||
|im/Presence in Outlook Web App  <br/> |有关详细信息，请参阅 Configure [integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|从会议安排和加入联机Outlook Web App  <br/> |有关详细信息，请参阅 Configure [integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|移动客户端中的 IM/状态  <br/> ||
|在移动客户端中加入联机会议  <br/> ||
|根据日历忙/Outlook信息发布状态  <br/> ||
|联系人列表 (统一联系人存储) 。  <br/> |仅 Lync Server 2013。 Lync 2013 或 Skype for Business桌面客户端是必需的。  <br/> 有关详细信息，请参阅 Configure [Skype for Business Server 2015 to use the unified contact store](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Lync 2013 客户端、Skype for Business客户端和 Lync Web App 中的高分辨率联系人照片。  <br/> |有关详细信息，请参阅 Configure [the use of high-resolution photos in Skype for Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md)。  <br/> 对于 Skype for Business MAC 和移动版应用上的照片，必须设置 Skype for Business Server 2015 和 Exchange Server 之间的集成，如配置本地部署和 Skype for Business Server 之间的集成中所述[Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md)。 <br/> |
|会议委派  <br/> |只有当两个用户都联机位于同一林中或两个用户都位于本地时，才受支持。 有关详细信息，请参阅混合[Skype for Business解决方案](/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions)。 <br/> |
|错过的对话历史记录和呼叫日志将写入用户Exchange邮箱  <br/> ||
|将内容 (IM 和会议) 存档Exchange  <br/> |有关详细信息，请参阅[Deployment Checklist for Archiving。](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving)  <br/> |
|搜索存档内容  <br/> |有关详细信息，请参阅 Configure [Exchange for SharePoint eDiscovery Center](/exchange/configure-exchange-for-sharepoint-ediscovery-center-exchange-2013-help) <br/> |
|语音邮件  <br/> |有关详细信息，请参阅在托管 UM 上提供[Lync Server 2013 Exchange语音邮件](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)。  <br/> |


## <a name="integration-with-sharepoint"></a>与 SharePoint

下表列出了混合部署中与混合部署集成时SharePoint。

||**SharePoint 本地部署**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype for Business Server 2015 本地部署** <br/> | 技能搜索 <br/>  状态SharePoint <br/> | 状态SharePoint <br/> |
|**Skype for Business Online** <br/> | 状态SharePoint <br/> | 状态SharePoint <br/> |
