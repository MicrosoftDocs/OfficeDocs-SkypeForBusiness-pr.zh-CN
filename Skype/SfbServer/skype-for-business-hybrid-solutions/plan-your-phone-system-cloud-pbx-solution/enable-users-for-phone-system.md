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
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: 本主题介绍如何为用户启用电话系统本地 PSTN 连接。 在按照本主题中的步骤操作之前，应阅读以下内容：。
ms.openlocfilehash: ffd7e9f02466dddeef31ba7ffd3a194a04b9b2ff
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2021
ms.locfileid: "61563659"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>在 Skype for Business Server 中使用本地 PSTN 连接启用电话系统用户

本主题介绍如何为用户启用电话系统本地 PSTN 连接。 在按照本主题中的步骤操作之前，应阅读以下内容：。
  
- 若要了解如何设置混合连接，请参阅在 Skype for Business Server 和[Skype for Business Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)之间规划混合连接和在 Skype for Business Server 和[Skype for Business Online](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)。
    
- 若要了解如何规划部署，请参阅 Plan[电话系统 with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md)。
    
- 若要详细了解电话系统，包括许可和计划，请参阅[pstN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)。
    
> [!Important]
> Skype for Business Online 于 2021 年 7 月 31 日停用，并且本地环境（无论是通过 Skype for Business Server 还是云连接器版本与 Skype for Business Online）之间的 PSTN 连接不再受支持。 了解如何使用直接路由将本地电话网络Teams[到呼叫。](/MicrosoftTeams/direct-routing-landing-page)

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>将用户电话系统本地 PSTN 连接进行迁移

在将用户移动到 Skype for Business Online 之前，建议在 Skype for Business Server 或 Lync Server 2013 中在本地启用用户，然后联机移动用户。 有关详细信息，请参阅规划[Skype for Business Server](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)和 Skype for Business Online 之间的混合连接，以及当用户位于本地 (时为用户启用 企业语音 本地[ (](enable-the-users-for-enterprise-voice-on-premises.md)的特殊注意事项部分) 。 
  
所有用户都必须在本地 Active Directory 中创建，并Microsoft 365 Office 365版本的 Azure AD Connector 进行同步。 不能为直接在电话系统Office 365创建的用户启用Azure AD。 如果要为在 Azure AD 中创建的用户启用具有本地 PSTN 连接的 电话系统，则需要在本地 AD 中为该用户创建新帐户，在本地配置帐户，然后使用受支持的 Azure AD 连接器工具版本同步该帐户。 
  
为用户启用电话系统本地 PSTN 连接，然后将他们移动到 Skype for Business Online 需要以下步骤：
  
- [为用户启用企业语音本地](enable-the-users-for-enterprise-voice-on-premises.md) (本地部署时执行) 。
    
- [分配在用户](assign-a-voice-routing-policy.md) (本地用户时执行的语音路由) 。
    
- [将用户同步到云，并分配使用](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) (执行的Office 365) 。
    
- [将本地用户移动到 Skype for Business Online](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md) (使用本地Windows PowerShell，但使用 Office 365 管理员凭据) 。
    
- [为用户启用企业语音和电话系统 PowerShell](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (语音邮件功能。
