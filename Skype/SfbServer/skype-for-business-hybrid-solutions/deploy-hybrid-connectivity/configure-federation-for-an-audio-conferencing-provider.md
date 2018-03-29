---
title: 在混合部署配置音频会议提供商的联盟
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
description: 摘要： 了解如何在 Skype 为业务在线配置音频会议提供商的联盟。
ms.openlocfilehash: 8ac7e8d365b2a46ac37091510c6909ea996d8ada
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>在混合部署配置音频会议提供商的联盟
 
**摘要：**了解如何在 Skype 为业务在线配置音频会议提供商的联盟。
  
如果希望在混合部署（包含本地版与联机版）中使用音频会议提供商 (ACP)，您需要在本地部署和 ACP 合作伙伴（作为允许的合作伙伴服务器）之间配置联盟。 您可以通过向本地部署的联盟域列表添加 ACP 合作伙伴域和边缘服务器（可称为访问代理）来配置联盟。 然后，ACP 合作伙伴需要将您的本地边缘服务器池的 FQDN 添加到允许的联盟域列表。 联系您的 ACP 提供商以了解详细信息。 您的 ACP 合作伙伴需要将您的本地边缘服务器池的 FQDN 添加到允许的联盟域列表。
  
- **将 ACP 域和边缘服务器添加为允许的联盟域**
    
    为允许合作伙伴服务器 （允许的联盟域） 添加 ACP 域，请按[配置支持允许外部域](http://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx)中的步骤操作。 边缘服务器时，将添加 ACP 伙伴的边缘服务器的 FQDN。 您可能需要联系 ACP 合作伙伴，获得其边缘服务器的 FQDN，ACP 也可能称之为访问代理。
    
- **向 ACP 合作伙伴提供您的边缘服务器池的 FQDN**
    
    ACP 合作伙伴需要将您的边缘服务器池的 FQDN 添加到允许的联盟域列表，以便配置联盟，将您的本地域添加为允许的合作伙伴服务器。
    

