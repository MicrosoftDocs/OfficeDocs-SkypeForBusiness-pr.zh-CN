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
ms.localizationpriority: medium
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: 服务器上大多数服务器角色的主要高可用性方案Skype for Business Server通过池实现的服务器冗余。 如果运行特定服务器角色的服务器发生故障，那么池中运行同一角色的其他服务器将接纳该服务器的负荷。
ms.openlocfilehash: 173f6313e0f70a1f2deef26e94256bcb281face3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593946"
---
# <a name="high-availability-planning-tool"></a>高可用性 (规划工具) 
 
服务器上大多数服务器角色的主要高可用性方案Skype for Business Server通过池实现的服务器冗余。 如果运行特定服务器角色的服务器发生故障，那么池中运行同一角色的其他服务器将接纳该服务器的负荷。
  
Skype for Business Server至少需要两台前端服务器才能实现高可用性。 规划工具使用下列条件来确定它是否将添加额外的服务器以支持高可用性：
  
- 如果部署包含两台或多台前端服务器，则规划工具不会添加额外的服务器。
    
- 如果部署包含边缘服务器，则添加其他服务器。 
    
- 如果部署包含持久聊天，则规划工具将添加一台额外的服务器，但不增加池数量。 例如，如果部署已包含四台服务器，规划工具将建议添加一个额外的服务器 (，以总共五台服务器) 维护一个池。 

    > [!NOTE] 
    > 持久聊天在 Skype for Business Server 2015 中可用，但在 2019 年 2 Skype for Business Server不再受支持。 相同的功能在 Teams。 有关详细信息，请参阅[Skype for Business Microsoft Teams升级](/MicrosoftTeams/upgrade-start-here)。 如果您需要使用持久聊天，您的选择是迁移需要此功能的用户以Teams或继续使用 Skype for Business Server 2015。 

    
规划工具还会添加所有SQL数据库的镜像数据库。 例如，如果存在前端 SQL Server数据库，规划工具将添加另一个数据库作为此数据库的镜像数据库，并将其名称为"前端镜像SQL数据库。
  
有关准备环境实现高可用性的更多详细信息，请参阅在 Skype for Business Server 中规划[高可用性和灾难恢复](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
