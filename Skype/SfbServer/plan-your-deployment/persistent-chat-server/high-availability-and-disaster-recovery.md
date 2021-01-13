---
title: 在 Skype for Business Server 2015 中规划持久聊天服务器的高可用性和灾难恢复
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: 摘要：阅读本主题，了解如何在 Skype for Business Server 2015 中规划持久聊天服务器的高可用性和灾难恢复。
ms.openlocfilehash: d29271b314981f3de0eb7bd0b963637c554fb26f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832352"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中规划持久聊天服务器的高可用性和灾难恢复
 
**摘要：** 阅读本主题，了解如何在 Skype for Business Server 2015 中规划持久聊天服务器的高可用性和灾难恢复。
  
持久聊天服务器的高可用性和灾难恢复需要除完整操作通常所需的额外资源外的其他资源。 
  
> [!NOTE]
> SQL持久聊天服务器数据库不支持使用 AlwaysOn 可用性组。 

> [!NOTE] 
> 持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 Teams 中也提供相同的功能。 有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。 如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。 
  
## <a name="resource-requirements"></a>资源要求

在将持久聊天服务器配置为高可用性和灾难恢复之前，请确保您具有以下其他资源。 
  
- 一个专用数据库实例，位于持久聊天服务器服务主前端所在的同一物理数据中心。 此数据库将充当SQL Server持久聊天数据库的镜像。 如果需要自动故障转移到镜像SQL Server，也可以指定其他服务器作为镜像见证。
    
- 一个位于其他物理数据中心的专用数据库实例。 此数据库将作为主SQL Server数据库的日志传输辅助数据库。
    
- 一个专用数据库实例，用作SQL Server数据库的镜像。 （可选）将SQL Server服务器指定为镜像见证。 它们都必须位于辅助数据库所在的同一物理数据中心。
    
- 如果启用持久聊天服务器合规性，则还需要另外三个专用数据库实例。 它们的分布与之前为持久聊天数据库列出的分布相同。 虽然合规性数据库可以与持久聊天SQL Server共享同一实例，但建议使用用于高可用性和灾难恢复的独立实例。
    
- 必须为日志传输事务日志创建和SQL Server文件共享。 两SQL持久聊天数据库的两个数据中心内的所有服务器都必须具有对此文件共享的读/写权限。 此共享不会定义为 FileStore 角色的一部分。
    
- 辅助数据库上的文件共享数据库服务器用作从主服务器文件共享复制SQL Server事务日志的目标文件夹。
    
## <a name="disaster-recovery-and-high-availability-solutions"></a>灾难恢复和高可用性解决方案

Skype for Business Server 支持后端服务器的多种高可用性模式，包括数据库镜像。 有关详细信息，请参阅 [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). 
  
本主题中介绍的持久聊天服务器的灾难恢复解决方案基于拉伸的持久聊天服务器池构建。 VLAN 中不需要扩展的虚拟 (区域) 。 通过拉伸持久聊天服务器池，可以逻辑地在拓扑中配置一个池，但实际将池中的服务器放在两个不同的数据中心。 您可以SQL Server配置数据库的镜像，并在同一数据中心部署数据库和镜像。 需要在辅助数据中心中配置一个备份数据库（在灾难恢复期间，用可选镜像来提供高可用性）。 这是在灾难恢复期间用于故障转移的备份数据库。 
  
若要详细了解如何为持久聊天服务器配置高可用性和灾难恢复，请参阅在 Skype [for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)中为持久聊天服务器配置高可用性和灾难恢复。 
  
下图显示了如何在两个不同的扩展池拓扑中配置持久聊天服务器池：
  
- 数据中心按地理位置分布时的扩展持久聊天服务器池（高带宽/低延迟）。
    
- 数据中心按地理位置分布时的扩展持久聊天服务器池（低带宽/高延迟）。
    
图 1 显示了拉伸持久聊天服务器池拓扑，其中数据中心位于地理位置，高带宽/低延迟。 为逻辑和物理拓扑假定以下内容：
  
- 逻辑拓扑由以下内容组成：
    
  - 跨站点 1 和站点 2 的持久聊天池，包含服务器 1 到 8。
    
  - 前端服务器池、持久聊天数据库、镜像数据库以及见证数据库（可选） (未显示在) 站点 1 上。 
    
  - 驻留在站点 2 上的第二个前端服务器池和备份数据库。
    
- 物理拓扑由站点 1 和站点 2 组成，如下所示：
    
  - 一个持久聊天池，包含站点 1 上的服务器 1 到 4、两个活动服务器、两个空闲服务器。
    
  - 一个持久聊天池，包含站点 2 上的服务器 5 到 8、两个活动服务器和两个空闲服务器。
    
  - 前端服务器池、持久聊天数据库、镜像数据库以及见证数据库（可选） (未显示在站点 1 上) 图表中显示的见证数据库池。
    
  - 站点 2 上的前端服务器池和备份数据库SQL日志寄送目标。
    
**数据中心位于地理位置时扩展的持久聊天服务器池，具有高带宽/低延迟**

![具有高带宽/低延迟的持久聊天拉伸池](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
图 2 显示了一个拉伸的持久聊天服务器池拓扑，其中数据中心位于地理位置，低带宽/高延迟。
  
- 逻辑拓扑由以下内容组成：
    
  - 跨站点 1 和站点 2 的持久聊天池，包含服务器 1 到 8。
    
  - 前端服务器池、持久聊天数据库、镜像数据库以及见证数据库（可选） (未显示在) 站点 1 上。 
    
  - 驻留在站点 2 上的第二个前端服务器池和备份数据库。
    
- 物理拓扑由站点 1 和站点 2 组成，如下所示：
    
  - 站点 1 上的持久聊天池，包含服务器 1 到 4，全部处于活动状态。
    
  - 站点 2 上的持久聊天池，包含服务器 5 到 8，所有空闲。
    
  - 前端服务器池、持久聊天数据库、镜像数据库以及见证数据库（可选） (未显示在站点 1 上) 图表中显示的见证数据库池。
    
  - 站点 2 上的前端服务器池和备份数据库SQL日志寄送目标。
    
**数据中心位于地理位置时扩展的持久聊天服务器池，低带宽/高延迟**

![低带宽/高延迟的持久聊天拉伸池](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

