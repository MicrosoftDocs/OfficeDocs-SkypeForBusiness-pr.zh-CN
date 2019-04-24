---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/8/2016
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: 通过池服务器冗余性基于业务服务器 2015年的 Skype 中的大多数服务器角色的主高可用性方案。 如果运行特定服务器角色的服务器发生故障，池中运行同一角色的其他服务器将接手该服务器的负载。
ms.openlocfilehash: 50cc5f371e4964555aae2a7f50ce3d1431f4f10c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200272"
---
# <a name="high-availability-planning-tool"></a>High Availability (Planning Tool)
 
通过池服务器冗余性基于业务服务器 2015年的 Skype 中的大多数服务器角色的主高可用性方案。 如果运行特定服务器角色的服务器发生故障，池中运行同一角色的其他服务器将接手该服务器的负载。
  
Skype 的业务服务器 2015年为了实现高可用性要求至少两个前端服务器。 规划工具使用下列条件确定是否才能支持高可用性，它将添加额外的服务器：
  
- 如果部署包含两个或多个前端服务器，规划工具不添加额外的服务器。
    
- 如果部署包含边缘服务器，添加其他服务器。 
    
- 如果部署包含持久聊天，规划工具将添加额外的服务器，但会增加池数。 例如，如果已部署包含四台服务器，规划工具将建议添加其他服务器 （总共五台服务器），但将保持单个池。 
    
规划工具还添加镜像 SQL 数据库的所有数据库。 例如，如果没有前端 SQL 服务器数据库，规划工具将作为此镜像数据库中添加其他数据库并将其命名为"前端镜像 SQL 数据库。
  
有关准备您的环境的高可用性的详细信息，请参阅[规划高可用性和灾难恢复的业务服务器 2015 Skype 中](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  

