---
title: 部署 Skype for Business Server 与 Skype for Business Online 之间的混合连接
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
description: 摘要： 阅读本主题可了解如何部署 Skype 业务服务器和 Skype 业务 online 之间的混合连接性。
ms.openlocfilehash: d96cff493daf8efa213c635a5a1454bfa370de9a
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-hybrid-connectivity-between-skype-for-business-server-and-skype-for-business-online"></a>部署 Skype for Business Server 与 Skype for Business Online 之间的混合连接
 
**摘要：**阅读本主题可了解如何部署 Skype for Business Server 与 Skype for Business Online 之间的混合连接。
  
之前执行本主题中的步骤，您应该已经阅读[规划 Skype 业务服务器和 Skype 业务 online 之间的混合连接性](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)。
  
Skype 业务服务器和 Skype 业务 online 之间的混合连接意味着用户的域名，例如，contoso.com，分别使用 Skype 本地 Business Server 和 Skype 业务 online 之间。 部分域用户驻留在本地，而另一部分用户驻留在线上。 
  
下表列出了业务 Online 和 Microsoft Office 365 准备您的环境以进行混合部署 Skype 所需的步骤。 
  
|**步骤**|**说明**|
|:-----|:-----|
|创建 Office 365 租户帐户和启用业务联机 Skype  <br/> |了解有关 Office 365 和 Skype 的业务 Online 在[Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980)。  <br/> 若要确保您的环境已准备好让 Office 365，请参阅[System Requirements](https://go.microsoft.com/fwlink/p/?LinkId=401408)。  <br/> 有关设置 Office 365 的详细信息，请参阅[Getting Started with Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982)。  <br/> |
|将您的域添加到 Office 365 租户，并验证所有权  <br/> | 您必须将您的域添加到 Office 365 租户中，然后按照步骤在 Office 365 中验证域。 这是为了确认您是域的所有者。 <br/> 若要将您的域添加到 Office 365 租户，请按照在[您将域添加到 Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254983)中所述的步骤。  <br/> |
|准备 Active Directory 同步  <br/> |Active Directory 同步保持内部部署 Active Directory 与 Office 365 持续同步。 这样，您可以创建每个用户帐户和组的同步版本，同时实现从本地 Microsoft Exchange Server 环境到 Microsoft Exchange Online 的全局地址列表 (GAL) 同步。 有关详细信息，请参阅[目录集成工具](https://go.microsoft.com/fwlink/p/?LinkId=530320)。  <br/> > [!IMPORTANT]> 您需要在本地和联机部署之间您组织中的业务用户的所有 Skype 的同步的 AD 帐户即使用户不移到 Skype 业务 online。 如果未能同步所有用户，组织内本地用户与联机用户之间的通信将出现问题。           |
|移动试用用户  <br/> |您已完成的步骤准备和配置您的环境的 Skype 业务 online 后，您可以开始将试点用户移到 online Office 365 租户。 请参阅[移动用户从本地到业务 online Skype](move-users-from-on-premises-to-skype-for-business-online.md)。  <br/> |
|管理混合部署中的用户  <br/> |有关如何在混合部署中管理用户的详细信息，请参阅[Administering 混合部署中的用户](http://technet.microsoft.com/library/6924ed7b-30a9-4be7-b952-90655625f2c8.aspx)。  <br/> |
   

