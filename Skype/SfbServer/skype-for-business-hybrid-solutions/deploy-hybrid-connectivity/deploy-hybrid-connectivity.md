---
title: 部署 Skype for Business Server 与 Skype for Business Online 之间的混合连接
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
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
description: 摘要： 请阅读本主题，以了解如何部署 Skype 业务服务器和 Skype 的在线业务之间的混合连接。
ms.openlocfilehash: 6dfe230088a2f3ecf827f3d8da9b6c9230ed4989
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-hybrid-connectivity-between-skype-for-business-server-and-skype-for-business-online"></a>部署 Skype for Business Server 与 Skype for Business Online 之间的混合连接
 
**摘要：**阅读本主题可了解如何部署 Skype for Business Server 与 Skype for Business Online 之间的混合连接。
  
执行本主题中的步骤之前, 您应阅读[计划业务服务器和 Skype 的在线业务 Skype 之间的混合连接](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)。
  
Skype 业务服务器和 Skype 的在线业务之间的混合连接意味着用户的域，如 contoso.com，都分为使用 Skype 业务服务器上部署和 Skype 的在线业务。 部分域用户驻留在本地，而另一部分用户驻留在线上。 
  
下表列出准备在线业务和 Microsoft Office 365 的 Skype 混合部署您的环境所需的步骤。 
  
|**步骤**|**说明**|
|:-----|:-----|
|创建 Office 365 的租户帐户并启用 Skype 的在线业务  <br/> |在[Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980)在线业务的了解 Office 365 和 Skype。  <br/> 若要确保您的环境是 Office 365 的准备，请参阅[系统要求](https://go.microsoft.com/fwlink/p/?LinkId=401408)。  <br/> 有关 Office 365 的设置的详细信息，请参阅[Office 365 入门知识](https://go.microsoft.com/fwlink/p/?LinkId=254982)。  <br/> |
|将您的域添加到 Office 365 租户和验证所有权  <br/> | 您必须将您的域添加到 Office 365 租户中，然后按照步骤在 Office 365 中验证域。 这是为了确认您是域的所有者。 <br/> 若要将您的域添加到 Office 365 租户，请按照[添加到 Office 365 域](https://go.microsoft.com/fwlink/p/?LinkId=254983)在所述的步骤。  <br/> |
|准备活动目录同步  <br/> |活动目录同步保持内部活动目录与 Office 365 连续同步。 这样，您可以创建每个用户帐户和组的同步版本，同时实现从本地 Microsoft Exchange Server 环境到 Microsoft Exchange Online 的全局地址列表 (GAL) 同步。 有关详细信息，请参阅[目录集成工具](https://go.microsoft.com/fwlink/p/?LinkId=530320)。  <br/> > [!IMPORTANT]> 您需要同步的所有内部部署和联机部署，您组织中的业务用户的 Skype 的 AD 帐户即使用户不移到 Skype 的在线业务。 如果未能同步所有用户，组织内本地用户与联机用户之间的通信将出现问题。           |
|移动试用用户  <br/> |准备和配置您的环境的 Skype 的在线业务的步骤完成后，您可以启动将试点项目的用户移到您在线 Office 365 租户。 请参阅[移动用户 Skype 的在线业务的场所上](move-users-from-on-premises-to-skype-for-business-online.md)。  <br/> |
|管理混合部署中的用户  <br/> |有关如何管理混合部署中的用户的详细信息，请参阅[管理混合部署中的用户](http://technet.microsoft.com/library/6924ed7b-30a9-4be7-b952-90655625f2c8.aspx)。  <br/> |
   

