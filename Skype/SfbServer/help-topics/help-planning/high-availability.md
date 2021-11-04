---
title: Skype for Business Server高可用性规划工具
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 4/8/2016
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
description: Skype for Business Server 2015 中大多数服务器角色的主要高可用性方案基于通过池实现的服务器冗余。 如果运行特定服务器角色的服务器发生故障，那么池中运行同一角色的其他服务器将接纳该服务器的负荷。
ms.openlocfilehash: 6a39d065349fb392dd54a7ff0d1872acc91e89cd
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774192"
---
# <a name="skype-for-business-server-high-availability-planning-tool"></a>Skype for Business Server高可用性规划工具
 
Skype for Business Server 2015 中大多数服务器角色的主要高可用性方案基于通过池实现的服务器冗余。 如果运行特定服务器角色的服务器发生故障，那么池中运行同一角色的其他服务器将接纳该服务器的负荷。
  
Skype for Business Server 2015 至少需要两台前端服务器才能实现高可用性。 规划工具使用下列条件来确定它是否将添加额外的服务器以支持高可用性：
  
- 如果部署包含两台或多台前端服务器，则规划工具不会添加额外的服务器。
    
- 如果部署包含边缘服务器，则添加另一台服务器。 
    
- 如果部署包含持久聊天，则规划工具将添加一台额外的服务器，但不增加池数量。 例如，如果部署中已包含四台服务器，规划工具将建议添加另一台服务器 (，以总共五台服务器) 维护一个池。 
    
规划工具还会添加一个SQL数据库的镜像数据库。 例如，如果有前端 SQL Server 数据库，规划工具将添加另一个数据库作为此数据库的镜像数据库，并将其名称为"前端镜像SQL数据库。
  
有关为高可用性准备环境的详细信息，请参阅 Plan for [high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  

