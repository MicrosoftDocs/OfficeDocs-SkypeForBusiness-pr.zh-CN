---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: Skype for Business Server 2015 中大多数服务器角色的主高可用性方案基于服务器冗余（通过池划分）。 如果运行特定服务器角色的服务器发生故障，池中运行同一角色的其他服务器将接手该服务器的负载。
ms.openlocfilehash: 53b98b72c70fcb624ab59fc7bfc3fbffadbd231a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41696287"
---
# <a name="high-availability-planning-tool"></a>High Availability (Planning Tool)
 
Skype for Business Server 2015 中大多数服务器角色的主高可用性方案基于服务器冗余（通过池划分）。 如果运行特定服务器角色的服务器发生故障，池中运行同一角色的其他服务器将接手该服务器的负载。
  
Skype for Business 服务器2015需要至少两个前端服务器才能启用高可用性。 规划工具使用以下条件来确定它是否将添加额外的服务器以支持高可用性：
  
- 如果部署包含两个或更多前端服务器，则计划工具不会添加额外的服务器。
    
- 如果部署包含 Edge 服务器，则会添加其他服务器。 
    
- 如果部署包含持久聊天，则计划工具将添加额外的服务器，但不会增加池编号。 例如，如果部署中已包含四台服务器，则计划工具将建议添加其他服务器（共5台服务器），但将维护单个池。 
    
规划工具还为所有数据库添加镜像 SQL 数据库。 例如，如果有前端 SQL Server 数据库，则计划工具将添加另一个数据库作为此数据库的镜像数据库，并将其命名为 "前端镜像 SQL 数据库。
  
有关为高可用性准备环境的更多详细信息，请参阅[Skype For Business Server 2015 中的高可用性和灾难恢复计划](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  

