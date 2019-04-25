---
title: 部署存档的 Skype 业务服务器
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: 摘要： 阅读本主题可了解如何部署存档的 Skype 业务服务器。
ms.openlocfilehash: 0598d1a35523cc38d85320206b065b85e025687e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233215"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>部署存档的 Skype 业务服务器
 
**摘要：** 阅读本主题可了解如何部署存档的 Skype 业务服务器。
  
对于业务服务器部署，您 Skype 中每个前端服务器上自动安装存档，但仍需要执行初始安装和配置步骤，然后才能使用它。 在开始之前，请确保您熟悉[Plan for Business Server 的 Skype 的存档](../../plan-your-deployment/archiving/archiving.md)中的概念。
  
## <a name="deployment-checklist"></a>部署清单

设置存档的方式取决于您所选的存储选项： 
  
- 如果部署中的所有用户使用 Microsoft Exchange 集成，您无需配置 Skype 的业务服务器存档策略的用户。 而是您配置 Exchange 就地保留策略以支持存档的用户驻留在 Exchange，使用他们的邮箱置于就地保留。 有关配置这些策略的详细信息，请参阅 Exchange 产品文档。
    
- 如果您执行部署中的所有用户使用 Microsoft Exchange 集成，您需要为业务 Server 存档数据库 （SQL Server 数据库） 到拓扑中，添加 Skype 发布更新的拓扑，然后配置存档策略和您的用户的的设置。 可以在部署初始拓扑的同时部署存档数据库，或在部署了至少一个前端池或 Standard Edition 服务器之后部署存档数据库。 本文档介绍如何通过将存档数据库添加到现有部署中来部署这些数据库。
    
如果在一个前端池或 Standard Edition 服务器中启用存档，则应为部署中的所有其他前端池和 Standard Edition 服务器启用存档。这是因为需要存档通信内容的用户可能会受邀参加其他池中承载的组 IM 对话或会议。如果承载对话或会议的池上没有启用存档，则无法存档完整会话。在这些情况下，仍可以为启用了存档的 IM 的用户进行存档，但不能为会议内容文件以及会议加入或离开事件存档。
  
> [!IMPORTANT]
> 如果出于合规性原因组织十分重视存档，请务必部署存档、 适当级别配置策略和其他选项，然后将打开存档所有适当的用户，这些用户启用的 Skype 之前业务服务器。 
  
下表提供在现有拓扑中部署存档所需步骤的概述。
  
|**阶段**|**步骤**|**角色和组成员身份**|**文档**|
|:-----|:-----|:-----|:-----|
|**安装必备硬件和软件** <br/> |若要使用 Microsoft Exchange 集成 （使用 Exchange 进行的部分或全部用户的存档存储），您需要一个现有的 Exchange 部署。  <br/> 若要使用单独的存档数据库（使用 SQL Server 数据库）为部分或所有用户进行存档存储，需要将存储存档数据的服务器上的 SQL Server。  <br/> 存档在企业池的前端服务器和 Standard Edition 服务器上运行。除了需要安装这些服务器外，没有额外的软硬件要求。  <br/> |属于本地 Administrators 组成员的域用户。  <br/> |[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [计划集成 Skype for Business 和 Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[For Business Server 2019 Skype 的系统要求](../../../SfBServer2019/plan/system-requirements.md) |
|**创建适当的内部拓扑以支持存档 （仅当未在部署中的所有用户使用 Microsoft Exchange 集成）** <br/> |向拓扑中，运行拓扑生成器以添加 Skype Business Server 存档数据库 （SQL Server 数据库），然后发布拓扑。  <br/> |要定义拓扑以包含存档数据库，需具有作为本地用户组的成员的帐户。  <br/> 用于 Business Server 文件存储的 Skype 的文件共享上发布拓扑，domain admins 组和 RTCUniversalServerAdmins 组的成员且具有完全控制权限 （读/写/修改） 的帐户 (以便拓扑生成器可以配置所需的 Dacl）。  <br/> |[业务服务器添加到现有部署中 Skype 的存档数据库](add-archiving-databases.md) <br/> |
|**配置服务器到服务器身份验证 （仅当使用 Microsoft Exchange 集成）** <br/> |配置服务器以启用 Skype 业务 server 和 Exchange 之间的身份验证。 建议运行**测试 CsExchangeStorageConnectivity testuser_sipUri-文件夹转储程序**验证 Exchange 存档存储连接，然后再启用存档。 <br/> |具有用于管理服务器上的证书的相应权限的帐户。  <br/> |管理服务器到服务器身份验证  <br/> |
|**配置存档选项和策略** <br/> |配置存档，包括是否使用 Microsoft Exchange 集成、 全局策略和任何站点和用户策略 （如果不使用 Microsoft Exchange 集成的所有数据存储），和特定的存档选项，如关键模式和数据导出和清除。  <br/> 如果使用 Microsoft Exchange 集成，请根据需要配置 Exchange 就地保留策略。  <br/> |RTCUniversalServerAdmins 组（仅限于 Windows PowerShell）或向 CSArchivingAdministrator 或 CSAdministrator 角色分配用户。  <br/> |[配置 Skype 业务服务器的存档的选项](configure-archiving-options.md) <br/> （如果使用 Microsoft Exchange 集成），则 exchange 产品文档。  <br/> |
   

