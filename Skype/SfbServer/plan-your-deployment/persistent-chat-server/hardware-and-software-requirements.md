---
title: Skype for business Server 2015 中持久聊天服务器的硬件和软件要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 摘要：阅读本主题，了解 Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求。
ms.openlocfilehash: 39204b675feff78fef56ee02e1c7e381eb36f65f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213228"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Skype for business Server 2015 中持久聊天服务器的硬件和软件要求
 
**摘要：** 阅读本主题，了解 Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求。
  
持久聊天服务器可以与 Skype for Business Server 2015 Enterprise Edition 或 Standard Edition 一起安装。 要求取决于您安装的 Skype for Business Server 2015 的版本以及您的业务的性能要求。 企业版最高可支持80000个并发用户;Standard Edition 最高可支持20000个并发用户。 持久聊天包含一个前端组件和一个后端 SQL 数据库组件。
  
在部署持久聊天服务器之前，必须确保满足以下硬件和软件要求：
  
- 满足最低要求以支持 Skype for business Server 2015、持久聊天服务器、数据库服务器和文件服务器的硬件。 有关详细信息，请参阅[Skype for Business server 2015 的服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
    
- 支持的操作系统和数据库软件。
    
    有关受支持的操作系统和数据库软件以及 Windows 更新要求的详细信息，请参阅[Skype for Business server 2015 的服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
    
- Skype for Business Server 2015 前端服务器。 前端服务器是会话初始协议（SIP）路由的基础，它使得运行持久聊天服务器的计算机与可能的持久聊天功能之间的通信成为可能。 
    
- 消息队列软件。 由持久聊天服务器和持久聊天合规性服务使用（如果已部署）。
    
以下各节介绍持久聊天服务器和存储持久聊天数据的数据库的特定要求。

> [!NOTE] 
> Skype for business Server 2015 中提供了持久聊天，但 Skype for Business Server 2019 不再支持它。 团队中提供了相同的功能。 有关详细信息，请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。 如果你需要使用持久聊天，你的选择是将需要此功能的用户迁移到团队，或者继续使用 Skype for Business Server 2015。 
  
## <a name="front-end-server-requirements"></a>前端服务器要求

前端服务器要求取决于是否要使用 Skype for business Server 2015 Enterprise Edition 或 Standard Edition 部署持久聊天服务器。
  
- 如果要使用 Skype for Business Server 2015 Enterprise Edition 部署持久聊天服务器，则可以在企业版池中的一台或多台独立计算机上部署持久聊天服务器前端服务器。 您不能在 Skype for Business Server 2015 前端服务器上并置持久聊天前端服务器。 
    
    一个持久聊天服务器前端服务器可支持20000个活动用户。 您可以拥有一个持久聊天服务器池和最高4个活动前端，从而支持总共80000个并发用户。 
    
- 如果要部署 Skype for business Server 2015 Standard Edition 的持久聊天服务器，则可以与前端服务器并置持久聊天。 此单服务器部署最高可支持20000个用户。 
    
## <a name="persistent-chat-server-database-requirements"></a>持久聊天服务器数据库要求

持久聊天服务器要求 SQL Server 数据库软件存储聊天室历史记录和内容、配置数据、用户预配数据和其他相关元数据。 （可选）它使用持久聊天合规性数据库来存储合规性数据。 持久聊天数据库可以在与后端数据库相同的 SQL 服务器（甚至相同的 SQL 实例）上并置。 
  
- 如果要在 Skype for business Server 2015 Enterprise Edition 中安装持久聊天服务器，则建议您安装持久聊天文件存储。
    
- 如果要为 Skype for Business Server 2015 Standard edition 安装持久聊天服务器，则可以在本地 SQL Server Express 实例上部署持久聊天存储后端服务器。
    
- 持久聊天数据库（mgc）和合规性数据库（mgccomp）可以位于 SQL Server 的同一个实例中，也可以位于不同的 SQL 服务器上。
    
若要准备数据库服务器平台，请确保每台计算机都满足硬件要求，然后安装必备软件。 持久聊天数据库服务器的服务器平台需要与 Skype for Business Server 2015 后端数据库服务器相同的硬件。 有关详细信息，请参阅[Skype for Business server 2015 的服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
  
在数据库服务器上，确保安装了以下软件应用程序之一：

- Microsoft SQL Server 2017 与最新的 service pack 结合使用。

- Microsoft SQL Server 2016 Service Pack 1，必须使用 Skype for Business Server 累积更新7或更高版本运行。 我们建议使用最新的 service pack 运行 SQL Server 2016。 有关如何安装 Microsoft SQL Server 2016 的详细信息，请参阅[INSTALL SQL server 2016](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016)。

- Microsoft SQL Server 2014，必须使用 Skype for Business Server 累积更新6或更高版本运行。 我们建议使用最新的 service pack 运行 SQL Server 2014。 有关如何安装 Microsoft SQL Server 2014 的详细信息，请参阅[INSTALL SQL server 2014](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014)。

- Microsoft SQL Server 2012 （64-bit edition），我们建议使用最新的 service pack 运行。 有关如何安装 Microsoft SQL Server 2012 的详细信息，请参阅[INSTALL SQL server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559)。

## <a name="persistent-chat-server-certificate-requirements"></a>持久聊天服务器证书要求

有关获取证书、创建 SQL Server 数据库和创建文件存储的详细信息，请参阅[Deploy Skype For Business Server 2015](../../deploy/deploy.md)。 
  
## <a name="for-more-information"></a>有关详细信息

有关硬件和软件要求的详细信息，请参阅下列主题：
  
- [Skype for business Server 2015 的服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [Skype for business Server 2015 的环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

