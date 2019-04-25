---
title: 为用户启用 Office 365 中的电话系统与 Skype 中的内部部署 PSTN 连接的业务服务器
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: 本主题介绍如何为用户启用 Office 365 中的电话系统与内部部署 PSTN 连接。 在执行本主题中的步骤之前，您应阅读以下文章:。
ms.openlocfilehash: a3eec7adbd4897889cbc2ef8c7e985231c53bc99
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234068"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>为用户启用 Office 365 中的电话系统与 Skype 中的内部部署 PSTN 连接的业务服务器
 
本主题介绍如何为用户启用 Office 365 中的电话系统与内部部署 PSTN 连接。 在执行本主题中的步骤之前，您应阅读以下文章:。
  
- 若要了解如何设置混合连接性，请参阅[规划业务服务器和 Skype 业务 online Skype 之间的混合连接性](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)和[部署之间 Skype 业务服务器和 Skype 业务 online 的混合连接](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)。
    
- 若要了解有关规划您的部署，请参阅[规划与业务服务器 Skype 中的内部部署 PSTN 连接的 Office 365 中的电话系统](plan-phone-system-with-on-premises-pstn-connectivity.md)。
    
- 若要了解有关在 Office 365 中，包括许可和计划的电话系统的详细信息，请参阅[PSTN 呼叫 for Business 的 Skype 的计划](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)。
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>将用户迁移到 Office 365 中的电话系统与内部部署 PSTN 连接

之前为业务 Online 将用户移动到 Skype，建议您在 Skype 本地用户启用企业服务器或 Lync Server 2013 和联机移动它们。 有关详细信息，请参阅[规划 Skype 业务服务器和 Skype 业务 online 之间的混合连接](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)和[为本地的企业语音用户启用](enable-the-users-for-enterprise-voice-on-premises.md)（执行时用户都驻留的特殊注意事项部分内部部署）。 
  
必须在本地 Active Directory 中创建并同步到 Office 365 使用 Azure AD 连接器的受支持的版本的所有用户。 用户不能启用用户直接在 Azure AD 中创建 Office 365 中的电话系统。 如果您想要启用与 Azure AD 中创建的用户的内部部署 PSTN 连接的 Office 365 中的电话系统，您将需要在您的内部部署中创建新的用户帐户 AD，配置帐户内部部署，，，然后将同步帐户使用受支持的 Azure AD 连接器工具版本。 
  
为用户启用 Office 365 中的电话系统与内部部署 PSTN 连接，然后为业务 Online 将它们移动到 Skype 需要执行以下步骤：
  
- [为本地的企业语音用户启用](enable-the-users-for-enterprise-voice-on-premises.md)（执行驻留在内部部署用户时）。
    
- [Assign a Voice Routing Policy](assign-a-voice-routing-policy.md)（当用户驻留在本地时执行）。
    
- [将用户同步到云和分配许可证](synchronize-users-to-the-cloud-and-assign-licenses.md)（执行使用 Office 365）。
    
- [在本地将用户移动到业务 online Skype](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online)（执行使用 Windows PowerShell 在本地，但使用 Office 365 管理员凭据）。
    
- [为用户启用企业语音 online 和 Office 365 语音邮件中的电话系统](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md)（使用远程 PowerShell 执行。
    

