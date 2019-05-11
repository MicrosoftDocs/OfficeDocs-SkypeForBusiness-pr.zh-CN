---
title: 规划高可用性和灾难恢复对于 Persistent Chat Server in Skype 业务服务器 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/17/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: 摘要： 阅读本主题可了解如何规划高可用性和灾难恢复对于 Persistent Chat Server in Skype 业务服务器 2015年。
ms.openlocfilehash: d2114faf7c4da205697a8bccd5a1ce299a627be5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924463"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>规划高可用性和灾难恢复对于 Persistent Chat Server in Skype 业务服务器 2015
 
**摘要：** 阅读本主题可了解如何规划高可用性和灾难恢复对于 Persistent Chat Server in Skype 业务服务器 2015年。
  
高可用性和灾难恢复 for Persistent Chat Server 需要超出通常需要完整的操作的其他资源。 
  
> [!NOTE]
> 不支持为持久聊天服务器数据库使用 SQL AlwaysOn 高可用性组。 

> [!NOTE] 
> 持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。 中团队提供了相同的功能。 有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。 如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。 
  
## <a name="resource-requirements"></a>资源要求

配置持久聊天服务器的高可用性和灾难恢复之前, 确保您具有以下附加资源。 
  
- 位于主页前端的持久聊天服务器服务所在的同一物理数据中心中的一个专用的数据库实例。 此数据库可作为主持久聊天数据库的 SQL Server 镜像。 （可选） 指定附加的 SQL Server 充当镜像见证，如果您希望自动故障转移到镜像数据库。
    
- 一个位于其他物理数据中心的专用数据库实例。 此数据库可作为主数据中心中的数据库的 SQL Server 日志传送辅助数据库。
    
- 一个专用的数据库实例以用作辅助数据库的 SQL Server 镜像。 （可选） 指定为镜像见证的服务器到其他 SQL Server。 它们都必须位于辅助数据库所在的同一物理数据中心。
    
- 如果启用持久聊天服务器合规性，则其他三个专用的数据库实例是必需的。 其通讯组是前面介绍的持久聊天数据库相同。 可能要共享与持久聊天数据库的同一 SQL Server 实例的合规性数据库时，建议使用的高可用性和灾难恢复的独立实例。
    
- 必须创建并指定的 SQL Server 日志传送事务日志文件共享。 运行持久聊天数据库这两个数据中心中的所有 SQL 服务器必须都具有对此文件共享的读/写访问。 此共享不会定义为 FileStore 角色的一部分。
    
- 文件共享，用作从主服务器文件共享中复制的 SQL Server 事务日志的目标文件夹的辅助数据库服务器上。
    
## <a name="disaster-recovery-and-high-availability-solutions"></a>灾难恢复和高可用性解决方案

Skype 业务服务器支持的后端服务器，包括数据库镜像高可用性的多个的模式。 有关详细信息，请参阅[Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。 
  
本主题中描述的持久聊天服务器的灾难恢复解决方案是基于拉伸的持久聊天服务器池。 这不要求具有扩展的虚拟局域网 (VLAN)。 通过拉伸的持久聊天服务器池，在逻辑上，配置一个池拓扑中，但实际放置在两个不同数据中心中的库中的服务器。 你以相同方式为数据库配置 SQL Server 镜像，并在同一数据中心中部署数据库和镜像。 需要在辅助数据中心中配置一个备份数据库（在灾难恢复期间，用可选镜像来提供高可用性）。 这是在灾难恢复期间用于故障转移的备份数据库。 
  
有关如何 for Persistent Chat Server 配置高可用性和灾难恢复的详细信息，请参阅[配置高可用性和灾难恢复对于 Persistent Chat Server in Skype 的业务服务器 2015年](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)。 
  
下图显示如何在两个不同的扩展的池拓扑中配置持久聊天服务器池：
  
- 时的扩展持久聊天服务器池数据中心按地理位置分布的高带宽/低延迟。
    
- 时的扩展持久聊天服务器池数据中心按地理位置分布的低带宽/高延迟。
    
图 1 显示了数据中心按地理位置分布的高带宽/低延迟的扩展持久聊天服务器池拓扑。 假设以下的逻辑和物理拓扑：
  
- 逻辑拓扑包含以下组件：
    
  - 跨站点 1 和 2 的持久聊天池，包含服务器 1 到 8。
    
  - 前端服务器池、 持久聊天数据库镜像的数据库，以及 （不在图表中所示） 见证数据库 （可选） 从物理上隔离驻留在站点 1 上。 
    
  - 物理驻留在站点 2 上的第二个前端服务器池和一个备份数据库。
    
- 物理拓扑结构组成网站 1 和 2，如下所示：
    
  - 站点 1 上的持久聊天池，包含服务器 1 到 4，两台活动，两台空闲。
    
  - 站点 5 上的持久聊天池，包含服务器 2 到 8，两台活动，两台空闲。
    
  - 前端服务器池、 持久聊天数据库镜像的数据库，和 （可选） 见证上的数据库 （不在图表中所示） 站点 1。
    
  - 站点 2 上的一个前端服务器池和一个备份数据库（作为 SQL 日志传送目标）。
    
**数据中心按地理位置分布时的扩展持久聊天服务器池（高带宽/低延迟）**

![持久聊天拉伸的池，含高带宽/低延迟](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
图 2 显示了数据中心按地理位置分布的低带宽/高延迟的扩展持久聊天服务器池拓扑。
  
- 逻辑拓扑包含以下组件：
    
  - 跨站点 1 和 2 的持久聊天池，包含服务器 1 到 8。
    
  - 前端服务器池、 持久聊天数据库镜像的数据库，以及 （不在图表中所示） 见证数据库 （可选） 从物理上隔离驻留在站点 1 上。 
    
  - 物理驻留在站点 2 上的第二个前端服务器池和一个备份数据库。
    
- 物理拓扑结构组成网站 1 和 2，如下所示：
    
  - 站点 1 上的持久聊天池，包含服务器 1 到 4，全部处于活动状态。
    
  - 站点 2 上的持久聊天池，包含服务器 5 到 8，全部处于空闲状态。
    
  - 前端服务器池、 持久聊天数据库镜像的数据库，和 （可选） 见证上的数据库 （不在图表中所示） 站点 1。
    
  - 站点 2 上的一个前端服务器池和一个备份数据库（作为 SQL 日志传送目标）。
    
**数据中心按地理位置分布时的扩展持久聊天服务器池（低带宽/高延迟）**

![持久聊天拉伸的池，含低带宽/高延迟](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

