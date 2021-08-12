---
title: Skype for Business Server 2015 中的持久聊天服务器的硬件和软件要求
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 摘要：阅读本主题，了解 2015 年持久聊天服务器的Skype for Business Server要求。
ms.openlocfilehash: 354ea7042cce2e413995dff242da21ce0cb5cc7aaacc35394110aab89a146383
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302286"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的持久聊天服务器的硬件和软件要求
 
**摘要：** 阅读本主题以了解 2015 年 10 月持久聊天服务器的Skype for Business Server要求。
  
持久聊天服务器可以与 Skype for Business Server 2015 Enterprise Edition或 Standard Edition 一起安装。 要求取决于您已安装的 Skype for Business Server 2015 版本，以及您的业务性能要求。 Enterprise Edition可支持多达 80，000 个并发用户;Standard Edition可支持多达 20，000 个并发用户。 持久聊天包含前端组件和后端数据库SQL组件。
  
在部署持久聊天服务器之前，必须确保满足以下硬件和软件要求：
  
- 满足支持 2015 Skype for Business Server持久聊天服务器、数据库服务器和文件服务器的最低要求的硬件。 有关详细信息，请参阅[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
    
- 支持的操作系统和数据库软件。
    
    有关支持的操作系统和数据库软件以及更新Windows的详细信息，请参阅 Server requirements for [Skype for Business Server 2015。](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- Skype for Business Server 2015 前端服务器。 前端服务器是会话初始协议 (SIP) 的基础，使运行持久聊天服务器的计算机与持久聊天功能之间的通信成为可能。 
    
- 消息队列软件。 由持久聊天服务器和持久聊天合规性服务使用（如果已部署）。
    
以下各节介绍持久聊天服务器和存储持久聊天数据的数据库的特定要求。

> [!NOTE] 
> 持久聊天在 2015 Skype for Business Server可用，但在 2019 年 2 月不再Skype for Business Server支持。 相同的功能在 Teams。 有关详细信息，请参阅[开始升级Microsoft Teams升级](/microsoftteams/upgrade-start-here)。 如果您需要使用持久聊天，您的选择是将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。 
  
## <a name="front-end-server-requirements"></a>前端服务器要求

前端服务器要求取决于您是使用 Skype for Business Server 2015 Enterprise Edition部署持久聊天Standard Edition。
  
- 如果要使用 Skype for Business Server 2015 Enterprise Edition 部署持久聊天服务器，可以在 Enterprise Edition 池中的一台或多台独立计算机上部署持久聊天服务器前端服务器。 您无法将持久聊天前端服务器并Skype for Business Server 2015 前端服务器上。 
    
    单个持久聊天服务器前端服务器可以支持 20，000 个活动用户。 您可以使用最多 4 个活动前端的持久聊天服务器池，从而总共支持 80，000 个并发用户。 
    
- 如果要将持久聊天服务器与 Skype for Business Server 2015 Standard Edition，可以将持久聊天与前端服务器并排。 此单服务器部署可支持多达 20，000 个用户。 
    
## <a name="persistent-chat-server-database-requirements"></a>持久聊天服务器数据库要求

持久聊天服务器SQL Server数据库软件来存储聊天室历史记录和内容、配置数据、用户设置数据和其他相关元数据。 （可选）它使用持久聊天合规性数据库来存储合规性数据。 持久聊天数据库可以与后端数据库并SQL Server，甚至可以与SQL实例并并。 
  
- 如果要将持久聊天服务器与 Skype for Business Server 2015 Enterprise Edition，为了确保最佳性能，建议您安装持久聊天文件存储。
    
- 如果要使用 Skype for Business Server 2015 Standard Edition 安装持久聊天服务器，可以在本地聊天存储实例上部署持久聊天存储SQL Server Express服务器。
    
- 持久聊天 (mgc) 合规性数据库 (mgccomp) 可以位于同一 SQL Server 实例中，也可以位于不同的 SQL 服务器上。
    
若要准备数据库服务器平台，请确保每台计算机都满足硬件要求，然后安装必备软件。 持久聊天数据库服务器的服务器平台需要与 Skype for Business Server 2015 后端服务器相同的数据库服务器。 有关详细信息，请参阅[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
  
在数据库服务器上，请确保安装了以下软件应用程序之一：

- Microsoft SQL Server 2017 Service Pack。

- Microsoft SQL Server Service Pack 1 的 2016 版本，并且必须运行 Skype for Business Server累积更新 7 或更高版本。 我们建议运行SQL Server Service Pack 的 2016 版本。 若要详细了解如何安装 Microsoft SQL Server 2016，请参阅 Install [SQL Server 2016。](/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016)

- Microsoft SQL Server 2014 年 10 月，并且必须使用 Skype for Business Server累积更新 6 或更高版本运行。 我们建议运行SQL Server Service Pack 的 2014 版本。 若要详细了解如何安装 Microsoft SQL Server 2014，请参阅 Install [SQL Server 2014](/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014)。

- Microsoft SQL Server 2012 (64 位) ，建议运行最新的 Service Pack。 若要详细了解如何安装 Microsoft SQL Server 2012，请参阅 Install [SQL Server 2012。](/previous-versions/sql/sql-server-2012/bb500395(v=sql.110))

## <a name="persistent-chat-server-certificate-requirements"></a>持久聊天服务器证书要求

有关获取证书、创建 SQL Server 数据库和创建文件存储的详细信息，请参阅 Deploy Skype for Business Server [2015](../../deploy/deploy.md)。 
  
## <a name="for-more-information"></a>详细信息

有关硬件和软件要求的信息，请参阅下列主题：
  
- [Skype for Business Server 2015 的服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [2015 年 Skype for Business Server 环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
