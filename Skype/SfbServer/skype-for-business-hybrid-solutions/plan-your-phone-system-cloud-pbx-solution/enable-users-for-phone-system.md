---
title: 在 Skype for Business Server 中使用本地 PSTN 连接启用电话系统用户
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: 本主题介绍如何为具有本地 PSTN 连接的电话系统启用用户。 在按照本主题中的步骤操作之前，应阅读以下内容：。
ms.openlocfilehash: 0a843b49546bfc5451197a3ef8ca48799c194731
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120864"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>在 Skype for Business Server 中使用本地 PSTN 连接启用电话系统用户

本主题介绍如何为具有本地 PSTN 连接的电话系统启用用户。 在按照本主题中的步骤操作之前，应阅读以下内容：。
  
- 若要了解如何设置混合连接，请参阅规划 Skype for Business Server 和 [Skype for Business Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) 之间的混合连接和部署 Skype for Business Server 和 Skype for Business Online 之间的混合 [连接](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)。
    
- 若要了解有关规划部署的信息，请参阅在 Skype for Business Server 中使用本地 [PSTN 连接规划电话系统](plan-phone-system-with-on-premises-pstn-connectivity.md)。
    
- 若要了解有关电话系统（包括许可和计划）的更多信息，请参阅[PSTN Calling plans for Skype for Business。](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)
    
> [!Important]
> Skype for Business Online 将于 2021 年 7 月 31 日停用，此后服务将不再可用。  此外，将不再支持本地环境（无论是通过 Skype for Business Server 还是云连接器版本与 Skype for Business Online）之间的 PSTN 连接。  了解如何使用直接路由将本地电话网络连接到[Teams。](/MicrosoftTeams/direct-routing-landing-page)

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>将用户移动到具有本地 PSTN 连接的电话系统

在将用户迁移到 Skype for Business Online 之前，建议在 Skype for Business Server 或 Lync Server 2013 中在本地启用用户，然后联机移动用户。 有关详细信息，请参阅 Plan [hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) 和 Enable the users for 企业语音 on premises [ (](enable-the-users-for-enterprise-voice-on-premises.md) performed while the users are homed on-premises) 的特殊注意事项部分。 
  
所有用户都必须在本地 Active Directory 中创建，并且使用受支持的 Azure AD 连接器版本同步到 Microsoft 365 或 Office 365。 无法为直接在 Azure AD 中创建的 Office 365 电话系统启用用户。 如果要为在 Azure AD 中创建的用户启用具有本地 PSTN 连接的电话系统，则需要在本地 AD 中为该用户创建新帐户，在本地配置帐户，然后使用受支持的 Azure AD 连接器工具版本同步该帐户。 
  
为具有本地 PSTN 连接的电话系统启用用户，然后将他们移动到 Skype for Business Online 需要以下步骤：
  
- [为用户启用企业语音本地](enable-the-users-for-enterprise-voice-on-premises.md) (，而用户位于本地) 。
    
- [分配在用户](assign-a-voice-routing-policy.md) (内部部署服务器时执行的语音路由) 。
    
- [将用户同步到云，并分配 (](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) Office 365) 。
    
- [将本地用户移动到 Skype for Business Online](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md) (使用本地Windows PowerShell，但使用 Office 365 管理员凭据) 。
    
- [为用户启用企业语音远程 PowerShell](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) 执行的电话 (语音邮件功能。
