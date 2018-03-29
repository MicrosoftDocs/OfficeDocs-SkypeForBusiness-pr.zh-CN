---
title: 为 Skype for Business Server 2015 部署存档
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: 摘要： 阅读本主题，以了解如何部署 Skype 业务服务器 2015年的存档。
ms.openlocfilehash: d218c59038b599f016f99cbce453f0bf1830a6f8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-archiving-for-skype-for-business-server-2015"></a>为 Skype for Business Server 2015 部署存档
 
**摘要：**阅读本主题，以了解如何部署 Skype 业务服务器 2015年的存档。
  
存档将自动安装您 Skype 业务服务器 2015年部署中每个前端服务器上，但您仍需要执行初始安装和配置步骤，然后才能使用它。 在开始之前，请确保您熟悉[规划业务服务器 2015年的 Skype 在归档](../../plan-your-deployment/archiving/archiving.md)中的概念。
  
## <a name="deployment-checklist"></a>部署清单

设置存档的方式取决于您所选的存储选项： 
  
- 如果部署中的所有用户使用 Microsoft Exchange 集成，您不需要为业务服务器归档策略，为您的用户配置 Skype。 相反，您可以配置支持归档的放在原位保存其邮箱上交换，驻留用户交换就地保存策略。 有关配置这些策略的详细信息，请参阅 Exchange 产品文档。
    
- 如果您不使用 Microsoft Exchange 集成为所有用户在您的部署中，您需要将 Skype 业务服务器存档的数据库 （SQL Server 数据库） 到您的拓扑结构，发布了更新的拓扑，然后配置归档策略和您的用户的设置。 可以在部署初始拓扑的同时部署存档数据库，或在部署了至少一个前端池或 Standard Edition 服务器之后部署存档数据库。 本文档介绍如何通过将存档数据库添加到现有部署中来部署这些数据库。
    
如果在一个前端池或 Standard Edition 服务器中启用存档，则应为部署中的所有其他前端池和 Standard Edition 服务器启用存档。这是因为需要存档通信内容的用户可能会受邀参加其他池中承载的组 IM 对话或会议。如果承载对话或会议的池上没有启用存档，则无法存档完整会话。在这些情况下，仍可以为启用了存档的 IM 的用户进行存档，但不能为会议内容文件以及会议加入或离开事件存档。
  
> [!IMPORTANT]
> 如果存档非常重要在您的组织为法规遵从性目的，一定要部署存档，在适当的级别配置策略和其他选项，然后将打开之前您启用这些用户的 Skype 的归档的所有适当的用户，企业服务器。 
  
下表提供在现有拓扑中部署存档所需步骤的概述。
  
|**阶段**|**步骤**|**角色和组成员身份**|**文档**|
|:-----|:-----|:-----|:-----|
|**安装必备硬件和软件** <br/> |若要使用 Microsoft Exchange 集成 （为部分或全部用户的存档存储，使用 Exchange），您需要现有 Exchange 部署。  <br/> 若要使用单独的存档数据库（使用 SQL Server 数据库）为部分或所有用户进行存档存储，需要将存储存档数据的服务器上的 SQL Server。  <br/> 存档在企业池的前端服务器和 Standard Edition 服务器上运行。除了需要安装这些服务器外，没有额外的软硬件要求。  <br/> |属于本地 Administrators 组成员的域用户。  <br/> |[业务服务器 2015 Skype 的的服务要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [环境要求为 Skype 的业务服务器 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [存档在 Skype 的业务服务器 2015年的硬件和软件要求](../../plan-your-deployment/archiving/hardware-and-software-requirements.md) <br/> [计划以落实 Skype 业务和交换](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/> |
|**创建适当的内部拓扑支持归档 （仅当不在您的部署中的所有用户使用 Microsoft Exchange 集成）** <br/> |对拓扑中，运行拓扑生成器将 Skype 业务服务器存档的数据库 （SQL Server 数据库），然后发布拓扑结构。  <br/> |要定义拓扑以包含存档数据库，需具有作为本地用户组的成员的帐户。  <br/> 在文件共享用于业务服务器文件存储为 Skype 发布拓扑，帐户是域管理员组和 RTCUniversalServerAdmins 组的成员并具有完全控制权限 （读/写/修改） (以便拓扑生成器可以配置所需的 Dacl）。  <br/> |[存档数据库添加到现有部署在 Skype 业务服务器 2015](add-archiving-databases.md) <br/> |
|**配置服务器的身份验证 （仅当使用 Microsoft Exchange 集成）** <br/> |将服务器配置为 Skype 业务服务器和 Exchange 之间启用身份验证。 建议运行**测试 CsExchangeStorageConnectivity testuser_sipUri-文件夹垃圾站**来验证 Exchange 之前启用存档存档存储连接。 <br/> |具有用于管理服务器上的证书的相应权限的帐户。  <br/> |管理服务器到服务器身份验证  <br/> |
|**配置存档选项和策略** <br/> |配置存档，包括是否使用 Microsoft Exchange 集成、 全球政策和任何网站和用户策略 （当不使用 Microsoft Exchange 集成的所有数据存储），以及特定的归档选项，如关键模式和数据导出和清除。  <br/> 如果使用 Microsoft Exchange 集成，根据需要配置 Exchange 就地保存策略。  <br/> |RTCUniversalServerAdmins 组（仅限于 Windows PowerShell）或向 CSArchivingAdministrator 或 CSAdministrator 角色分配用户。  <br/> |[配置为 Skype 业务服务器 2015年的存档选项](configure-archiving-options.md) <br/> （如果使用 Microsoft Exchange 集成） 交换产品文档。  <br/> |
   

