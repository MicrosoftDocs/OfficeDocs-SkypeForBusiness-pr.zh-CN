---
title: '高可用性 (规划工具) '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: Skype for Business Server 中大多数服务器角色的主要高可用性方案基于通过池实现的服务器冗余。 如果运行特定服务器角色的服务器发生故障，那么池中运行同一角色的其他服务器将接纳该服务器的负荷。
ms.openlocfilehash: 36b2d9fad34e16daf11fb7539f73c815264a55a6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093310"
---
# <a name="high-availability-planning-tool"></a>高可用性 (规划工具) 
 
Skype for Business Server 中大多数服务器角色的主要高可用性方案基于通过池实现的服务器冗余。 如果运行特定服务器角色的服务器发生故障，那么池中运行同一角色的其他服务器将接纳该服务器的负荷。
  
Skype for Business Server 需要至少两台前端服务器才能实现高可用性。 规划工具使用下列条件来确定它是否将添加额外的服务器以支持高可用性：
  
- 如果部署包含两台或多台前端服务器，则规划工具不会添加额外的服务器。
    
- 如果部署包含边缘服务器，则添加其他服务器。 
    
- 如果部署包含持久聊天，则规划工具将添加一台额外的服务器，但不增加池数量。 例如，如果部署已包含四台服务器，规划工具将建议为总共 5 台服务器 (添加一个额外的服务器) 但会维护一个池。 

    > [!NOTE] 
    > 持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 Teams 中提供了相同的功能。 有关详细信息，请参阅 [Skype for Business 到 Microsoft Teams 的升级](/MicrosoftTeams/upgrade-start-here)。 如果需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。 

    
规划工具还会添加一个SQL数据库的镜像数据库。 例如，如果存在前端 SQL Server数据库，则规划工具将另一个数据库添加为此数据库的镜像数据库，并将其名称为"前端镜像SQL数据库。
  
有关为高可用性准备环境的详细信息，请参阅 Plan for [high availability and disaster recovery in Skype for Business Server。](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
