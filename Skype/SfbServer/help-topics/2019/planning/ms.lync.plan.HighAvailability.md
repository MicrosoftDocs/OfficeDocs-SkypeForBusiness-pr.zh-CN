---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: Skype 业务服务器中的大多数服务器角色的主高可用性方案基于通过池服务器冗余性。 如果运行特定服务器角色的服务器发生故障，池中运行同一角色的其他服务器将接手该服务器的负载。
ms.openlocfilehash: 8868b86d87adaa1e9da191ae9088775f786a8d0d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32221079"
---
# <a name="high-availability-planning-tool"></a>High Availability (Planning Tool)
 
Skype 业务服务器中的大多数服务器角色的主高可用性方案基于通过池服务器冗余性。 如果运行特定服务器角色的服务器发生故障，池中运行同一角色的其他服务器将接手该服务器的负载。
  
Skype 业务服务器以实现高可用性要求至少两个前端服务器。 规划工具使用下列条件确定是否才能支持高可用性，它将添加额外的服务器：
  
- 如果部署包含两个或多个前端服务器，规划工具不添加额外的服务器。
    
- 如果部署包含边缘服务器，添加其他服务器。 
    
- 如果部署包含持久聊天，规划工具将添加额外的服务器，但会增加池数。 例如，如果已部署包含四台服务器，规划工具将建议添加其他服务器 （总共五台服务器），但将保持单个池。 

    > [!NOTE] 
    > 持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。 中团队提供了相同的功能。 有关详细信息，请参阅[为 Microsoft 团队业务的 Skype 升级](https://docs.microsoft.com/MicrosoftTeams/journey-skypeforbusiness-teams)。 如果您需要使用持久聊天，请选择要迁移要求向工作组此功能的用户或继续对业务服务器 2015年使用 Skype。 

    
规划工具还添加镜像 SQL 数据库的所有数据库。 例如，如果没有前端 SQL 服务器数据库，规划工具将作为此镜像数据库中添加其他数据库并将其命名为"前端镜像 SQL 数据库。
  
有关准备您的环境的高可用性的详细信息，请参阅[规划高可用性和灾难恢复 Skype 业务服务器中](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  

