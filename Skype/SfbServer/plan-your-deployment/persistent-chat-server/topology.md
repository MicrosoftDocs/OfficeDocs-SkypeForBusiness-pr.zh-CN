---
title: 规划持久聊天服务器拓扑
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 5/17/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: 'Summary: Read this topic to learn about Persistent Chat Server components and topologies in Skype for Business Server 2015.'
ms.openlocfilehash: b5da90b6753a534ae705af96dcf871663017ea55
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="plan-persistent-chat-server-topology"></a>规划持久聊天服务器拓扑
 
**Summary:** Read this topic to learn about Persistent Chat Server components and topologies in Skype for Business Server 2015.
  
Persistent Chat Server supports both single-server and multiple-server configurations. You can install Persistent Chat Server on either a Skype for Business Server 2015 Enterprise Edition or Standard Edition Server. 
  
## <a name="persistent-chat-server-components"></a>Persistent Chat Server components

持久聊天服务器由以下组件组成：
  
- One or more computers running Persistent Chat Server and providing the following services:
    
  - Persistent Chat service
    
  - 合规性服务，在启用合规性时打开
    
- One or more servers (more than one if mirroring is used) running the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.
    
    > [!NOTE]
    > The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created. 
  
- If compliance is enabled, one or more servers (more than one if mirroring is used) running the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.
    
For details about hardware and software requirements for Persistent Chat Server, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015](hardware-and-software-requirements.md). 
  
## <a name="persistent-chat-server-topologies"></a>Persistent Chat Server topologies

You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology. Persistent Chat Server supports the following topologies:
  
-  Standard Edition Server 与持久聊天服务器并置在前端服务器上
    
-  Standard Edition Server with Persistent Chat Server on a separate server
    
-  Enterprise Edition Server with a single Persistent Chat Server on a separate server
    
-  Enterprise Edition Server with more than one Persistent Chat Server on separate servers
    
Although you can deploy Persistent Chat Server on a Standard Edition Server, be aware that performance and scale will be affected, and high availability is not an option. Therefore, it is recommended that you deploy Persistent Chat on a Standard Edition Server primarily for proof of concept and evaluation purposes. 
  
Skype for Business Server 2015 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance). You should consider scalability factors before deciding whether to collocate components. Collocation scenarios differ for Skype for Business Server 2015 Enterprise Edition and Standard Edition servers. 
  
以下几节更为具体地介绍了拓扑，包括并置方案和后端数据库服务器选项。 For details about collocation of all server roles and databases, see [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a>Standard Edition Server 与持久聊天服务器并置在前端服务器上

使用 Standard Edition，可以将持久聊天并置在前端服务器上。 这是最简单也最基本的配置。 You must make sure that the existing Front End Server has enough capacity in terms of physical resources: CPU, memory, disk space, and so on.
  
In addition, you can collocate the Persistent Chat Server back-end server and the Persistent Chat Compliance database (if enabled) on the local SQL Server Express back-end server. 还可以选择使用独立的 SQL Server 及专用实例。 
  
> [!IMPORTANT]
> You cannot add additional servers to a Persistent Chat Server pool if the first Persistent Chat Server is collocated with a Standard Edition Front End Server. It is recommended that you install the first server as a standalone instance so that you can add more servers later, if needed. 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a>Standard Edition Server 与持久聊天服务器安装在不同的服务器上

使用 Standard Edition，您可以将持久聊天服务器作为独立实例安装，随后按需添加更多服务器。   
  
You can collocate the Persistent Chat Server back-end server and the Persistent Chat Compliance database (if enabled) on the local SQL Server Express back-end server. 还可以选择使用独立的 SQL Server 及专用实例。 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a>Enterprise Edition Server 与一个持久聊天服务器

使用 Enterprise Edition 时，必须将持久聊天服务器安装在不同的计算机上。 也就是说，不能将持久聊天服务器并置在 Enterprise Edition 前端服务器上。 This deployment requires a separate server that runs Persistent Chat Server and the Compliance service (if enabled).
  
You can, however, collocate the SQL Server database for Persistent Chat Server on the back-end database of an Enterprise Edition Front End pool.
  
> [!NOTE]
> 如果计划为 HA DR 使用 SQL AlwaysOn 可用性组，请注意它不受持久聊天服务器数据库支持。 
  
If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database.
  
> [!IMPORTANT]
> The server hosting the Persistent Chat database can host other databases. However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large. For this reason, we do not recommend collocating the Persistent Chat database with the back-end database. 
  
The following figure shows all components of a topology for a single Persistent Chat Server with compliance enabled (optional).
  
**Single Server Topology**

![持久聊天服务器 - 单服务器拓扑](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a>Enterprise Edition Server 与多个持久聊天服务器

With Enterprise Edition, you can deploy a multiple-server topology for greater capacity and reliability. A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher. The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby). Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers. Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Skype for Business Server and the Compliance service.
  
The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.
  
**Multiple Server Topology**

![持久聊天服务器 - 多服务器拓扑](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
多服务器拓扑提供了服务器池功能。 In a server pool, the Persistent Chat services communicate and share data. For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system. A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service. Users can be connected to different Persistent Chat Server Front End Servers and can be communicating with each other. The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat services to communicate between themselves, or for administrative purposes.
  
For example, in a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to Persistent Chat, the load is distributed evenly at 20,000 users per server. If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server. 断开连接的用户将自动转移到其他服务器，直至不可用服务器恢复为止。 
  

