---
title: Skype for Business Server 2015 中的存档的硬件和软件要求
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
description: 摘要： 请阅读本主题，以了解有关硬件和软件要求的存档在 Skype 业务服务器 2015年。
ms.openlocfilehash: d8d8039e95a3b578551d0db6ff219fe8f3c1e5c5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的存档的硬件和软件要求
 
**摘要：**阅读本主题以了解有关硬件和软件要求的存档在 Skype 业务服务器 2015年。
  
Skype 业务服务器 2015年存档现在位于前端角色中，因此您不需要安装单独的服务器。 但是，执行此操作，需要考虑以下要求：
  
- 基础结构要求
    
- 必备软件要求
    
- 数据存储要求
    
## <a name="infrastructure-requirements"></a>基础结构要求

Skype 的业务服务器归档基础架构的要求是一样的 Skype 业务服务器的部署。 有关详细信息，请参阅[您的业务环境的 Skype 的要求](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)。 
  
## <a name="prerequisite-software-requirements"></a>必备软件要求

存档的 Skype 业务服务器的前提条件是比早期版本的 Lync Server 简单由于以下原因： 
  
- 因为存档不再是一个服务器角色，您不需要安装单独的服务器进行存档。 而是在每个 Enterprise Edition 前端池和每台 Standard Edition 服务器上自动安装和激活统一数据收集代理。 您需要使用拓扑生成器启用和发布存档拓扑。
    
- 归档使用 Skype 业务服务器用于临时存储会议内容的文件，因此不会设置一个单独的文件存储存档的文件存储。
    
- 在 Skype 业务服务器，Microsoft 消息队列不需要。
    
## <a name="data-storage-requirements"></a>数据存储要求

您需要为存档存储设置基础结构。这包括选择以下一个或两个选项：
  
- **Microsoft Exchange 存储**。 会议内容文件（比如 PowerPoint 演示文稿）都作为附件进行存档。 如果您想要存储 Skype 业务与法规遵从性的 Exchange 数据的存档数据，必须使用您的 Exchange 部署的 Exchange，并确保最大存储容量支持会议内容文件的存储。 您必须部署 Exchange 部署和启用存档使用 Microsoft Exchange 集成选项之前。 
    
    如果您选择使用 Exchange 存储，您不需要部署单独的 SQL Server 数据库的存档，除非您的业务用户没有驻留在 Exchange 服务器有 Skype。 如果您部署存档使用 Microsoft Exchange 集成选项，Skype 业务存档数据仅用于驻留在您的 Exchange 服务器的用户交换法规遵从性数据一起存储。 
    
- **Skype 业务服务器存档存储**。 为没有驻留在 Exchange 服务器的用户提供支持或如果您不想使用 Microsoft Exchange 集成选项，您必须部署使用的是 SQL Server 数据库的存档存储。 Skype 业务服务器支持下面的 SQL Server 的 64 位版本：
    
  - Microsoft SQL Server 2008 R2 企业
    
  - Microsoft SQL Server 2008 R2 标准
    
  - Microsoft SQL Server 2012年企业
    
  - Microsoft SQL Server 2012年标准
    
  - Microsoft SQL Server 2014年企业
    
  - Microsoft SQL Server 2014年标准
    
    > [!NOTE]
    > Microsoft SQL Server Express 版本不支持存档。 不支持 32 位版本的 SQL Server。 其他 SQL Server 要求和限制，请参阅[您的业务环境的 Skype 的要求](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)。 
  
    您必须设置然后再部署和启用存档的 SQL Server 平台。 如果用于发布拓扑的帐户具有适当的管理员权限，则可在发布拓扑时创建存档数据库 (LcsLog)。 您稍后还可创建数据库（包括在安装过程中）。 有关 SQL Server 的详细信息，请参阅[SQL Server 技术中心](https://go.microsoft.com/fwlink/p/?linkID=129045)。
    
    存档带来的负载提升可能非常显著。 因此，您应该确保磁盘空间适合前端服务器在其启用存档。
    

