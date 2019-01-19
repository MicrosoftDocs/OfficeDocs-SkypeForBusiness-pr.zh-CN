---
title: Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/19/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 摘要： 阅读本主题可了解有关硬件和软件要求对于 Persistent Chat Server in Skype 业务服务器 2015年。
ms.openlocfilehash: ce39d4c535c75517160b53f89378144c5299bebf
ms.sourcegitcommit: e53749714dcde9f7b184d5ef554bffbc77f54267
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2019
ms.locfileid: "28729419"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求
 
**摘要：** 阅读此主题以了解有关硬件和软件要求对于 Persistent Chat Server in Skype 业务服务器 2015年。
  
业务 Server 2015 Enterprise Edition 或 Standard Edition，可以使用 Skype 安装持久聊天服务器。 要求取决于您已安装的业务服务器 2015 Skype 的是哪个版本，以及您的业务的性能要求。 Enterprise Edition 最多可支持 80,000 个并发用户；Standard Edition 最多可支持 20,000 个并发用户。 持久聊天包含前端组件以及后端 SQL 数据库组件。
  
部署持久聊天服务器之前，您必须确保满足以下硬件和软件要求：
  
- 满足最低要求以支持 Skype 业务服务器 2015年、 持久聊天服务器、 数据库服务器和文件服务器的硬件。 有关详细信息，请参阅[业务服务器 2015年的 Skype 服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
    
- 支持的操作系统和数据库软件。
    
    有关支持的操作系统和数据库软件和窗口的详细信息更新要求，请参阅[业务服务器 2015年的 Skype 的服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
    
- Skype 业务 Server 2015 前端服务器。 前端服务器是基础的会话初始协议 (SIP) 路由，这将使计算机运行 Persistent Chat Server 和持久聊天功能之间的通信可能。 
    
- 消息队列软件。 如果部署 Persistent Chat Server 和持久聊天合规性服务，使用。
    
以下各节介绍对于 Persistent Chat Server 和存储的持久聊天数据的数据库的特定要求。

> [!NOTE] 
> 持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。 中团队提供了相同的功能。 有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。 如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。 
  
## <a name="front-end-server-requirements"></a>前端服务器要求

前端服务器要求取决于是否为业务 Server 2015 Enterprise Edition 或 Standard Edition 部署与 Skype 的持久聊天服务器。
  
- 如果您业务 Server 2015 Enterprise Edition 部署与 Skype 的持久聊天服务器，则可以部署持久聊天服务器前端服务器中的企业版池的一个或多个独立计算机上。 您不能将持久聊天前端服务器上的 Skype 并置的业务 Server 2015 前端服务器。 
    
    单个持久聊天服务器前端服务器可支持 20,000 活动用户。 您可以将持久聊天服务器池具有最多 4 从而支持 80,000 个并发用户，总计的活动前端。 
    
- 如果您业务 Server 2015 Standard Edition 部署与 Skype 的持久聊天服务器，可以与前端服务器的持久聊天将并置。 此单服务器部署可最多支持 20,000 个用户。 
    
## <a name="persistent-chat-server-database-requirements"></a>持久聊天服务器数据库要求

持久聊天服务器需要 SQL Server 数据库软件存储聊天室的历史记录和内容、 配置数据、 用户设置数据和其他相关的元数据。 （可选），它使用的持久聊天合规性数据库来存储合规性数据。 持久聊天数据库可与后端数据库并置在相同的 SQL Server 甚至相同的 SQL 实例上。 
  
- 如果您安装持久聊天服务器与 Skype 业务 Server 2015 Enterprise Edition，以确保获得最佳性能，建议您在安装的持久聊天文件存储。
    
- 如果您安装持久聊天服务器与 Skype 业务 Server 2015 Standard edition，您可以部署持久聊天存储后端服务器上的本地 SQL Server Express 实例。
    
- 持久聊天数据库 (mgc) 和合规性数据库 (mgccomp) 可以位于的 SQL Server 或不同 SQL 服务器上的同一实例中。
    
为准备数据库平台，务必保证每一台计算机都满足硬件要求，然后安装好必备软件。 对服务器平台的持久聊天数据库服务器需要 Skype 的相同硬件业务服务器 2015年后端数据库服务器。 有关信息，请参阅 [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
  
在数据库服务器上，确保安装了以下软件应用程序之一：

- 最新的 service pack 的 Microsoft SQL Server 2017。

- 使用 Service Pack 1 和您的 Microsoft SQL Server 2016 必须与 Skype 运行，业务 Server 累积更新 7 或更高版本。 我们建议将运行 SQL Server 2016 带有最新的 service pack。 有关如何安装 Microsoft SQL Server 2016 的详细信息，请参阅[安装 SQL Server 2016](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016)。

- Microsoft SQL Server 2014，并且您必须运行与 Skype 业务 Server 累积更新 6 或更高版本。 我们建议最新的 service pack 运行 SQL Server 2014。 有关如何安装 Microsoft SQL Server 2014 的详细信息，请参阅[安装 SQL Server 2014](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014)。

- Microsoft SQL Server 2012 （64 位版本），以及我们建议最新的 service pack 的运行。 有关如何安装 Microsoft SQL Server 2012 的详细信息，请参阅[安装 SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559)。

## <a name="persistent-chat-server-certificate-requirements"></a>持久聊天服务器证书要求

有关获取证书的详细信息，创建 SQL Server 数据库和创建文件存储，请参阅[部署的 Skype 的业务服务器 2015年](../../deploy/deploy.md)。 
  
## <a name="for-more-information"></a>有关详细信息

有关硬件和软件要求的详细信息，请参阅以下主题：
  
- [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

