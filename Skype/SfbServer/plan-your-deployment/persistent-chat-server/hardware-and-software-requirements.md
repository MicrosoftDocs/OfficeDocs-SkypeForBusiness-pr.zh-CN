---
title: Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 摘要： 请阅读本主题，以了解有关硬件和软件要求在 Skype 的持久聊天服务器的业务服务器 2015年。
ms.openlocfilehash: a56f939360edae0da47198e4a3810f70712b6ab8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求
 
**摘要：**阅读本主题以了解有关硬件和软件要求在 Skype 的持久聊天服务器的业务服务器 2015年。
  
持久的聊天服务器可以安装与 Skype 业务服务器 2015年企业版或标准版。 要求取决于您安装业务服务器 2015年的 Skype 的是哪个版本，以及您的业务的性能要求。 Enterprise Edition 最多可支持 80,000 个并发用户；Standard Edition 最多可支持 20,000 个并发用户。 持久聊天包含前端组件以及后端 SQL 数据库组件。
  
在部署持续聊天服务器之前，必须确保符合以下硬件和软件要求：
  
- 满足最低要求，以支持 Skype 业务服务器 2015年、 持久聊天服务器、 数据库服务器和文件服务器的硬件。 有关详细信息，请参阅[业务服务器 2015年的 Skype 的服务要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
    
- 支持的操作系统和数据库软件。
    
    有关受支持的操作系统和数据库软件和 Windows 更新要求、[业务服务器 2015年的 Skype 的服务要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)，请参阅。
    
- Skype 业务服务器 2015年前端服务器。 前端服务器是为会话启动协议 (SIP) 路由，这样有可能持久聊天服务器和持久聊天功能运行的计算机之间的通信的基础。 
    
- 消息队列软件。 如果部署，使用持久聊天服务器和持久聊天的法规遵从性服务。
    
以下各节描述持久聊天服务器和存储的持久聊天数据的数据库的特定要求。
  
## <a name="front-end-server-requirements"></a>前端服务器要求

前结束服务器要求取决于是否为业务服务器 2015年企业版或标准版部署 Skype 的持久聊天服务器。
  
- 如果业务服务器 2015年企业版部署 Skype 的持久聊天服务器，您可以部署持续聊天服务器前端服务器在企业版池中的一个或多个独立计算机上。 不能为业务服务器 2015年前端服务器布置持久聊天前端服务器在 Skype 上。 
    
    一个持久聊天服务器前端服务器可支持 20000 个活动用户。 您可以持久聊天服务器池与从而支持 80000 并发用户的总数将达 4 活动前结束。 
    
- 如果业务服务器 2015年标准版部署 Skype 的持久聊天服务器，可以布置与前端服务器持续聊天。 此单服务器部署可最多支持 20,000 个用户。 
    
## <a name="persistent-chat-server-database-requirements"></a>持久的聊天服务器数据库要求

持久的聊天服务器需要 SQL Server 数据库软件，以存储聊天室历史和内容、 配置数据、 用户设置数据和其他相关的元数据。 （可选），它使用持久聊天的法规遵从性数据库存储符合性数据。 持久聊天数据库可与后端数据库并置在相同的 SQL Server 甚至相同的 SQL 实例上。 
  
- 如果您正在安装持久聊天服务器使用 Skype 业务服务器 2015年企业版，以确保获得最佳性能，建议您安装永久聊天文件存储区。
    
- 如果您正在安装持久聊天服务器使用 Skype 业务服务器 2015年标准版，您可以部署持续聊天存储后端服务器上的 SQL Server Express 的本地实例。
    
- 持续聊天数据库 (mgc) 和法规遵从性数据库 (mgccomp) 可以位于相同的或不同的 SQL 服务器上的 SQL Server 实例。
    
为准备数据库平台，务必保证每一台计算机都满足硬件要求，然后安装好必备软件。 持续聊天的数据库服务器的服务器平台需要业务服务器 2015年后端数据库服务器为 Skype 相同的硬件。 有关详细信息，请参阅[业务服务器 2015年的 Skype 的服务要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
  
在数据库服务器上，确保安装了以下软件应用程序之一：
  
- Microsoft SQL Server 2012年。 有关如何安装 Microsoft SQL Server 2012年的详细信息，请参阅[安装 SQL Server 2012年](https://go.microsoft.com/fwlink/p/?LinkID=248559)。
    
- Microsoft SQL Server 2008 R2。 有关如何安装 Microsoft SQL Server 2008 R2 的详细信息，请参阅[SQL Server 安装 (SQL Server 2008 R2)](https://go.microsoft.com/fwlink/p/?LinkId=275702)。
    
## <a name="persistent-chat-server-certificate-requirements"></a>持久的聊天服务器证书要求

有关获取证书的详细信息，创建 SQL Server 数据库中，并创建文件存储区，请参阅[部署的业务服务器 2015年的 Skype](../../deploy/deploy.md)。 
  
## <a name="for-more-information"></a>有关详细信息

有关硬件和软件要求的详细信息，请参阅以下主题：
  
- [业务服务器 2015 Skype 的的服务要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [环境要求为 Skype 的业务服务器 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

