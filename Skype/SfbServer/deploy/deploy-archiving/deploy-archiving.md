---
title: 为 Skype for Business Server 部署存档
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: '摘要: 阅读本主题, 了解如何为 Skype for Business Server 部署存档。'
ms.openlocfilehash: 813911dba5bfc662ee1c6bea9dab99e34c031e98
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286525"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>为 Skype for Business Server 部署存档
 
**摘要:** 阅读本主题, 了解如何为 Skype for Business Server 部署存档。
  
存档将自动安装在 Skype for Business Server 部署中的每个前端服务器上, 但你仍需要先执行初始设置和配置步骤, 然后才能使用它。 开始之前, 请确保熟悉[Skype for Business 服务器中的存档计划](../../plan-your-deployment/archiving/archiving.md)中的概念。
  
## <a name="deployment-checklist"></a>部署清单

设置存档的方式取决于您所选的存储选项： 
  
- 如果你对部署中的所有用户使用 Microsoft Exchange 集成, 则无需为你的用户配置 Skype for Business 服务器存档策略。 而是配置 Exchange 就地保留策略以支持驻留在 Exchange 上的用户的存档, 并将其邮箱置于就地保留。 有关配置这些策略的详细信息, 请参阅 Exchange 产品文档。
    
- 如果你不为部署中的所有用户使用 Microsoft Exchange 集成, 你需要向拓扑中添加 Skype for Business 服务器存档数据库 (SQL Server 数据库), 发布更新的拓扑, 然后配置存档策略和用户的设置。 可以在部署初始拓扑的同时部署存档数据库，或在部署了至少一个前端池或 Standard Edition 服务器之后部署存档数据库。 本文档介绍如何通过将存档数据库添加到现有部署中来部署这些数据库。
    
如果在一个前端池或 Standard Edition 服务器中启用存档，则应为部署中的所有其他前端池和 Standard Edition 服务器启用存档。这是因为需要存档通信内容的用户可能会受邀参加其他池中承载的组 IM 对话或会议。如果承载对话或会议的池上没有启用存档，则无法存档完整会话。在这些情况下，仍可以为启用了存档的 IM 的用户进行存档，但不能为会议内容文件以及会议加入或离开事件存档。
  
> [!IMPORTANT]
> 如果出于合规性原因, 存档在你的组织中非常重要, 请确保在相应级别部署存档、配置策略和其他选项, 然后为所有适当的用户打开存档, 然后再为 Skype 启用这些用户企业服务器。 
  
下表提供在现有拓扑中部署存档所需步骤的概述。
  
|**阶段**|**步骤**|**角色和组成员身份**|**文档**|
|:-----|:-----|:-----|:-----|
|**安装必备硬件和软件** <br/> |若要使用 Microsoft Exchange 集成 (使用 Exchange 存档某些或所有用户的存储), 需要现有 Exchange 部署。  <br/> 若要使用单独的存档数据库（使用 SQL Server 数据库）为部分或所有用户进行存档存储，需要将存储存档数据的服务器上的 SQL Server。  <br/> 存档在企业池的前端服务器和 Standard Edition 服务器上运行。除了需要安装这些服务器外，没有额外的软硬件要求。  <br/> |属于本地 Administrators 组成员的域用户。  <br/> |[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [计划集成 Skype for Business 和 Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[Skype for business Server 2019 的系统要求](../../../SfBServer2019/plan/system-requirements.md) |
|**创建适当的内部拓扑以支持存档 (仅在未对部署中的所有用户使用 Microsoft Exchange 集成时)** <br/> |运行拓扑生成器以向拓扑中添加 Skype for Business 服务器存档数据库 (SQL Server 数据库), 然后发布拓扑。  <br/> |要定义拓扑以包含存档数据库，需具有作为本地用户组的成员的帐户。  <br/> 若要发布拓扑, 作为域管理员组和 RTCUniversalServerAdmins 组的成员的帐户, 并且具有对 Skype for business Server 文件存储使用的文件共享的完全控制权限 (读/写/修改), 以便该拓扑生成器可以配置所需的 Dacl)。  <br/> |[将存档数据库添加到 Skype for Business 服务器中的现有部署](add-archiving-databases.md) <br/> |
|**配置服务器到服务器身份验证 (仅当使用 Microsoft Exchange 集成时)** <br/> |将服务器配置为在 Skype for Business 服务器和 Exchange 之间启用身份验证。 我们建议在启用存档之前, 运行**CsExchangeStorageConnectivity testuser_sipUri-Folder Dumpster**以验证 Exchange 存档存储连接。 <br/> |具有用于管理服务器上的证书的相应权限的帐户。  <br/> |管理服务器到服务器身份验证  <br/> |
|**配置存档选项和策略** <br/> |配置存档, 包括是否使用 Microsoft Exchange 集成、全局策略和任何网站和用户策略 (不使用 Microsoft Exchange 集成进行所有数据存储) 和特定的存档选项 (如关键模式和数据)导出和清除。  <br/> 如果使用 Microsoft Exchange 集成, 请根据需要配置 Exchange 就地保留策略。  <br/> |RTCUniversalServerAdmins 组（仅限于 Windows PowerShell）或向 CSArchivingAdministrator 或 CSAdministrator 角色分配用户。  <br/> |[配置 Skype for Business 服务器的存档选项](configure-archiving-options.md) <br/> Exchange 产品文档 (如果使用的是 Microsoft Exchange 集成)。  <br/> |
   

