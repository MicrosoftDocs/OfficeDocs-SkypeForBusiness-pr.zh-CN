---
title: Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: 摘要：阅读本主题，了解如何在 Skype for Business Server 2015 中规划持久聊天服务器的高可用性和灾难恢复。
ms.openlocfilehash: 042080aebf57a14554820eea9b5bb9d5c9bb1f71
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836224"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015
 
**摘要：** 阅读本主题，了解如何在 2015 年规划持久聊天服务器的高可用性Skype for Business Server灾难恢复。
  
持久聊天服务器的高可用性和灾难恢复需要除完整操作通常所需的资源之外的其他资源。 
  
> [!NOTE]
> 不支持SQL持久聊天服务器数据库使用 AlwaysOn 可用性组。 

> [!NOTE] 
> 持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 相同的功能在 Teams。 有关详细信息，请参阅开始[升级Microsoft Teams升级](/microsoftteams/upgrade-start-here)。 如果您需要使用持久聊天，您的选择是迁移需要此功能的用户以Teams或继续使用 Skype for Business Server 2015。 
  
## <a name="resource-requirements"></a>资源要求

在配置持久聊天服务器实现高可用性和灾难恢复之前，请确保您具有以下其他资源。 
  
- 一个专用数据库实例，位于持久聊天服务器服务主前端所在的同一物理数据中心。 此数据库将充当SQL Server持久聊天数据库的镜像。 如果需要自动故障转移到镜像SQL Server，也可以指定一个额外的服务器作为镜像见证。
    
- 一个位于其他物理数据中心的专用数据库实例。 此数据库将作为主SQL Server数据库的日志传输辅助数据库。
    
- 一个专用数据库实例，用作SQL Server数据库的镜像。 （可选）将SQL Server服务器的其他服务器指定为镜像见证。 它们都必须位于辅助数据库所在的同一物理数据中心。
    
- 如果启用了持久聊天服务器合规性，则还需要另外三个专用数据库实例。 它们的分布与之前为持久聊天数据库概述的分布相同。 尽管合规性数据库可以与持久聊天数据库共享SQL Server实例，但建议使用高可用性和灾难恢复的独立实例。
    
- 必须为日志传输事务日志创建SQL Server文件共享。 两SQL持久聊天数据库的两个数据中心内的所有服务器都必须具有对此文件共享的读/写访问权限。 此共享不会定义为 FileStore 角色的一部分。
    
- 辅助数据库上的文件共享数据库服务器用作从主服务器文件共享中复制SQL Server事务日志的目标文件夹。
    
## <a name="disaster-recovery-and-high-availability-solutions"></a>灾难恢复和高可用性解决方案

Skype for Business Server支持多种模式的后端服务器高可用性，包括数据库镜像。 有关详细信息，请参阅[Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。 
  
本主题中介绍的持久聊天服务器的灾难恢复解决方案是在拉伸的持久聊天服务器池上构建的。 VLAN 部署不需要扩展的虚拟 (网络) 。 通过拉伸持久聊天服务器池，可以逻辑地在拓扑中配置一个池，但实际将池中的服务器放在两个不同的数据中心。 您可以SQL Server配置数据库的镜像，并在同一数据中心部署数据库和镜像。 需要在辅助数据中心中配置一个备份数据库（在灾难恢复期间，用可选镜像来提供高可用性）。 这是在灾难恢复期间用于故障转移的备份数据库。 
  
若要详细了解如何为持久聊天服务器配置高可用性和灾难恢复，请参阅在 Skype for Business Server [2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)中为持久聊天服务器配置高可用性和灾难恢复。 
  
下图显示了如何在两个不同的扩展池拓扑中配置持久聊天服务器池：
  
- 数据中心按地理位置分布时的扩展持久聊天服务器池（高带宽/低延迟）。
    
- 数据中心按地理位置分布时的扩展持久聊天服务器池（低带宽/高延迟）。
    
图 1 显示了数据中心按地理位置（高带宽/低延迟）的拉伸持久聊天服务器池拓扑。 假定逻辑拓扑和物理拓扑如下：
  
- 逻辑拓扑由以下内容组成：
    
  - 站点 1 和站点 2 中的持久聊天池，包含服务器 1 到服务器 8。
    
  - 前端服务器池、持久聊天数据库、镜像数据库以及见证数据库（可选） (未显示在) 物理上驻留在站点 1 上。 
    
  - 物理上驻留在站点 2 上的第二个前端服务器池和备份数据库。
    
- 物理拓扑由站点 1 和站点 2 组成，如下所示：
    
  - 一个持久聊天池，包含站点 1 上的服务器 1 到 4、两个活动服务器、两个空闲服务器。
    
  - 站点 2 上包含服务器 5 到 8、两个活动、两个空闲的持久聊天池。
    
  - 前端服务器池、持久聊天数据库、镜像数据库以及见证数据库（可选） (图 1 上未) 显示。
    
  - 站点 2 上的前端服务器池和备份数据库（SQL日志寄送目标）。
    
**数据中心地理位置时扩展的持久聊天服务器池（高带宽/低延迟）**

![持久聊天拉伸池，具有高带宽/低延迟。](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
图 2 显示了数据中心按地理位置的扩展持久聊天服务器池拓扑，低带宽/高延迟。
  
- 逻辑拓扑由以下内容组成：
    
  - 站点 1 和站点 2 中的持久聊天池，包含服务器 1 到服务器 8。
    
  - 前端服务器池、持久聊天数据库、镜像数据库以及见证数据库（可选） (未显示在) 物理上驻留在站点 1 上。 
    
  - 物理上驻留在站点 2 上的第二个前端服务器池和备份数据库。
    
- 物理拓扑由站点 1 和站点 2 组成，如下所示：
    
  - 站点 1 上的持久聊天池，包含服务器 1 到 4，全部处于活动状态。
    
  - 站点 2 上的持久聊天池，包含服务器 5 到 8，全部处于空闲状态。
    
  - 前端服务器池、持久聊天数据库、镜像数据库以及见证数据库（可选） (图 1 上未) 显示。
    
  - 站点 2 上的前端服务器池和备份数据库SQL日志寄送目标。
    
**数据中心位于地理位置时扩展的持久聊天服务器池，低带宽/高延迟**

![持久聊天拉伸池，具有低带宽/高延迟。](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

