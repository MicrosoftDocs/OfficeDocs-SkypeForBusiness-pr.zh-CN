---
title: 在 Skype for Business Server 中为使用本地 PSTN 连接的 Office 365 中的用户启用电话系统
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
description: 本主题介绍如何为使用本地 PSTN 连接的 Office 365 中的电话系统启用用户。 在执行本主题中的步骤之前，您应阅读以下内容：。
ms.openlocfilehash: 87dcafcfe0c5ce69bcdbcd9809d23cea80c234ba
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050184"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>在 Skype for Business Server 中为使用本地 PSTN 连接的 Office 365 中的用户启用电话系统
 
本主题介绍如何为使用本地 PSTN 连接的 Office 365 中的电话系统启用用户。 在执行本主题中的步骤之前，您应阅读以下内容：。
  
- 若要了解如何设置混合连接，请参阅[规划 skype For Business server 和 skype for Business online 之间的混合连接](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)，以及[在 Skype for Business server 和 Skype for Business online 之间部署混合连接](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)。
    
- 若要了解如何规划部署，请参阅在[Skype For Business Server 中使用本地 PSTN 连接规划 Office 365 中的电话系统](plan-phone-system-with-on-premises-pstn-connectivity.md)。
    
- 若要了解有关 Office 365 中的电话系统（包括许可和计划）的详细信息，请参阅[适用于 Skype For business 的 PSTN 呼叫计划](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)。
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>将用户移动到使用本地 PSTN 连接的 Office 365 中的电话系统

在将用户迁移到 Skype for business Online 之前，建议您在 Skype for Business Server 或 Lync Server 2013 中的本地启用用户，然后将其联机移动。 有关详细信息，请参阅[规划 skype For Business Server 和 skype for Business Online 之间的混合连接](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)和为[用户启用企业语音](enable-the-users-for-enterprise-voice-on-premises.md)（在用户托管本地时执行）的特殊注意事项部分。 
  
所有用户都必须在本地 Active Directory 中创建，并使用受支持的 Azure AD 连接器版本同步到 Office 365。 您无法在 Office 365 中为直接在 Azure AD 中创建的 Office 中的用户启用电话系统。 如果要为在 Azure AD 中创建的用户在 Office 365 中启用与本地 PSTN 连接的电话系统，你需要在本地 AD 中为该用户创建一个新帐户，在本地配置帐户，然后使用同步该帐户受支持的 Azure AD 连接器工具版本。 
  
为使用本地 PSTN 连接的 Office 365 中的用户启用电话系统，然后将其移动到 Skype for Business Online，需要执行以下步骤：
  
- [为用户启用企业语音](enable-the-users-for-enterprise-voice-on-premises.md)（在用户托管本地时执行）。
    
- [分配语音路由策略](assign-a-voice-routing-policy.md)（在用户驻留在本地时执行）。
    
- [将用户同步到云并分配许可证](synchronize-users-to-the-cloud-and-assign-licenses.md)（使用 Office 365 执行）。
    
- [将本地用户移动到 Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) （使用本地 Windows PowerShell 执行，但使用 Office 365 管理员凭据）。
    
- [在 Office 365 语音邮件中为用户启用企业语音在线和电话系统](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md)（使用远程 PowerShell 执行）。
    

