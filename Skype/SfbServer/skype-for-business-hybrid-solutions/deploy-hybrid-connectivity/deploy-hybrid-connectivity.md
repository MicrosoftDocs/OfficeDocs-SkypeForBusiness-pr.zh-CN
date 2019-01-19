---
title: 部署混合连接性 |Skype Online 业务服务器 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
description: 摘要：阅读本主题可了解如何部署 Skype for Business Server 与 Skype for Business Online 之间的混合连接。
ms.openlocfilehash: 5e97517cab50f344c5be4981ff64553366dd7710
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2019
ms.locfileid: "29348889"
---
# <a name="deploy-hybrid-connectivity-between-skype-for-business-server-and-skype-for-business-online"></a>部署 Skype for Business Server 与 Skype for Business Online 之间的混合连接

**摘要：** 阅读本主题可了解如何部署 Skype for Business Server 与 Skype for Business Online 之间的混合连接。
  
之前执行本主题中的步骤，您应该已经阅读[规划 Skype 业务服务器和 Skype 业务 online 之间的混合连接性](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)。
  
Skype 业务服务器和 Skype 业务 online 之间的混合连接意味着用户的域名，例如，contoso.com，分别使用 Skype 本地 Business Server 和 Skype 业务 online 之间。 部分域用户驻留在本地，而另一部分用户驻留在线上。
  
下表列出了业务 Online 和 Microsoft Office 365 准备您的环境以进行混合部署 Skype 所需的步骤。
  
|步骤|说明|
|:-----|:-----|
|创建 Office 365 租户帐户和启用业务联机 Skype  <br/> |了解有关 Office 365 和 Skype 的业务 Online 在[Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980)。  <br/> 若要确保你的环境满足 Office 365 要求，请参阅[系统要求](https://products.office.com/en-US/office-system-requirements)。  <br/> 有关设置 Office 365 的详细信息，请参阅 [Office 365 入门](https://go.microsoft.com/fwlink/p/?LinkId=254982)。  <br/> |
|将您的域添加到 Office 365 租户，并验证所有权  <br/> | 您必须将您的域添加到 Office 365 租户中，然后按照步骤在 Office 365 中验证域。 这是为了确认您是域的所有者。 <br/> 若要将你的域添加到您的 Office 365 租户中，请按照[将域添加到 Office 365 中](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)中所述的步骤操作。  <br/> |
|准备 Active Directory 同步  <br/> |Active Directory 同步保持内部部署 Active Directory 与 Office 365 持续同步。 这样，你可以创建每个用户帐户和组的同步版本，同时实现从本地 Microsoft Exchange Server 环境到 Microsoft Exchange Online 的全局地址列表 (GAL) 同步。 有关详细信息，请参阅[目录集成工具](https://go.microsoft.com/fwlink/p/?LinkId=530320)。  <br/>  **重要说明**您需要在本地和联机部署之间您组织中的业务用户的所有 Skype 的同步的 AD 帐户即使用户不移到 Skype 业务 online。 如果未能同步所有用户，组织内本地用户与联机用户之间的通信将出现问题。           |
|移动试用用户  <br/> |您已完成的步骤准备和配置您的环境的 Skype 业务 online 后，您可以开始将试点用户移到 online Office 365 租户。 请参阅[移动用户从本地到业务 online Skype](move-users-from-on-premises-to-skype-for-business-online.md)。  <br/> |

## <a name="related-content"></a>相关的内容

配置之间 Skype 业务 server 和 Office 365 的混合连接性的信息，请参阅[Business Server 和 Office 365 的 Skype 之间配置混合连接性](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。