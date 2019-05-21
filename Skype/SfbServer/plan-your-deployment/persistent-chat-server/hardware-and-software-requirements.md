---
title: Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: '摘要: 阅读本主题, 了解 Skype for business Server 2015 中持久聊天服务器的硬件和软件要求。'
ms.openlocfilehash: 8dfd21426cee6b32e6f06c35297ccd5fd8dc534e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297097"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求
 
**摘要:** 阅读本主题, 了解 Skype for business Server 2015 中持久聊天服务器的硬件和软件要求。
  
持久聊天服务器可以与 Skype for business Server 2015 企业版或标准版一起安装。 要求取决于你已安装的 Skype for business Server 2015 版本以及你的企业的性能要求。 Enterprise Edition 最多可支持 80,000 个并发用户；Standard Edition 最多可支持 20,000 个并发用户。 持久聊天包含前端组件以及后端 SQL 数据库组件。
  
在部署持久聊天服务器之前, 必须确保满足以下硬件和软件要求:
  
- 满足最低要求以支持 Skype for Business Server 2015、持久聊天服务器、数据库服务器和文件服务器的硬件。 有关详细信息, 请参阅[Skype for Business server 2015 的服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
    
- 支持的操作系统和数据库软件。
    
    有关受支持的操作系统和数据库软件以及 Windows 更新要求的详细信息, 请参阅[Skype for Business server 2015 的服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
    
- Skype for Business 服务器2015前端服务器。 前端服务器是会话初始协议 (SIP) 路由的基础, 用于在运行持久聊天服务器的计算机与可能的持久聊天功能之间进行通信。 
    
- 消息队列软件。 如果已部署, 则为持久聊天服务器和持久聊天合规性服务使用。
    
以下部分介绍持久聊天服务器和存储持久聊天数据的数据库的特定要求。

> [!NOTE] 
> Skype for business Server 2015 中提供了持久聊天, 但 Skype for business Server 2019 不再支持此功能。 团队中提供了相同的功能。 有关详细信息, 请参阅[从 Skype For Business 迁移到 Microsoft 团队](/microsoftteams/journey-skypeforbusiness-teams)。 如果需要使用持久聊天, 您可以选择将需要此功能的用户迁移到团队, 或继续使用 Skype for Business Server 2015。 
  
## <a name="front-end-server-requirements"></a>前端服务器要求

前端服务器要求取决于您是否要部署 Skype for business Server 2015 企业版或标准版的持久聊天服务器。
  
- 如果要为 Skype for Business Server 2015 企业版部署持久聊天服务器, 可以在企业版池中的一台或多台独立计算机上部署持久聊天服务器前端服务器。 您不能在 Skype for Business Server 2015 前端服务器上 collocate 持久聊天前端服务器。 
    
    单个持久聊天服务器前端服务器可以支持20000活动用户。 你可以拥有最多4个活动前端的持久聊天服务器池, 从而支持总共80000并发用户。 
    
- 如果你要部署 Skype for business Server 2015 标准版的持久聊天服务器, 你可以与前端服务器 collocate 持久聊天。 此单服务器部署可最多支持 20,000 个用户。 
    
## <a name="persistent-chat-server-database-requirements"></a>持久聊天服务器数据库要求

持久聊天服务器要求 SQL Server 数据库软件存储聊天室历史记录和内容、配置数据、用户预配数据以及其他相关的元数据。 或者, 它使用持久聊天合规数据库来存储合规性数据。 持久聊天数据库可与后端数据库并置在相同的 SQL Server 甚至相同的 SQL 实例上。 
  
- 如果要在 Skype for Business Server 2015 企业版中安装持久聊天服务器, 以确保获得最佳性能, 建议安装持久聊天文件存储。
    
- 如果你要安装 Skype for Business Server 2015 标准版的持久聊天服务器, 你可以在本地 SQL Server Express 实例上部署持久的聊天应用商店后端服务器。
    
- 持久聊天数据库 (mgc) 和合规性数据库 (mgccomp) 可以位于 SQL Server 的同一实例中, 也可以位于不同的 SQL Server 上。
    
为准备数据库平台，务必保证每一台计算机都满足硬件要求，然后安装好必备软件。 持久聊天数据库服务器的服务器平台需要与 Skype for Business Server 2015 后端数据库服务器相同的硬件。 有关信息，请参阅 [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
  
在数据库服务器上，确保安装了以下软件应用程序之一：

- Microsoft SQL Server 2017 和最新服务包。

- Microsoft SQL Server 2016 Service Pack 1, 必须运行 Skype for Business Server 累积更新7或更高版本。 我们建议使用最新的 service pack 运行 SQL Server 2016。 有关如何安装 Microsoft SQL Server 2016 的详细信息, 请参阅[安装 SQL server 2016](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016)。

- Microsoft SQL Server 2014, 必须运行 Skype for Business Server 累积更新6或更高版本。 我们建议使用最新的 service pack 运行 SQL Server 2014。 有关如何安装 Microsoft SQL Server 2014 的详细信息, 请参阅[安装 SQL server 2014](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014)。

- Microsoft SQL Server 2012 (64 位版), 我们建议使用最新的 service pack 运行。 有关如何安装 Microsoft SQL Server 2012 的详细信息, 请参阅[安装 SQL server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559)。

## <a name="persistent-chat-server-certificate-requirements"></a>持久聊天服务器证书要求

有关获取证书、创建 SQL Server 数据库和创建文件存储的详细信息, 请参阅[部署 Skype For Business Server 2015](../../deploy/deploy.md)。 
  
## <a name="for-more-information"></a>有关详细信息

有关硬件和软件要求的详细信息，请参阅以下主题：
  
- [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

