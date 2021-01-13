---
title: 为 Skype for Business Server 部署存档
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: 摘要：阅读本主题，了解如何为 Skype for Business Server 部署存档。
ms.openlocfilehash: 32b25b373bd5399928d5e5eaed063c194942f697
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825212"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>为 Skype for Business Server 部署存档
 
**摘要：** 阅读本主题，了解如何为 Skype for Business Server 部署存档。
  
存档会自动安装在 Skype for Business Server 部署中的每台前端服务器上，但你仍然需要执行初始安装和配置步骤，然后才能使用它。 开始之前，请确保你熟悉在 Skype for Business [Server 中规划存档的概念](../../plan-your-deployment/archiving/archiving.md)。
  
## <a name="deployment-checklist"></a>部署清单

如何设置存档取决于选择哪个存储选项： 
  
- 如果在部署中为所有用户使用 Microsoft Exchange 集成，则无需为用户配置 Skype for Business Server 存档策略。 相反，您可以配置 Exchange In-Place 保留策略以支持对 Exchange 上用户进行存档，其邮箱将置于In-Place保留状态。 有关配置这些策略的详细信息，请参阅 Exchange 产品文档。
    
- 如果未对部署中的所有用户使用 Microsoft Exchange 集成，则需要将 Skype for Business Server 存档数据库 (SQL Server 数据库) 添加到拓扑中，发布更新后的拓扑，然后为用户配置存档策略和设置。 可以在部署初始拓扑的同时或部署至少一个前端池或 Standard Edition Server 之后部署存档数据库。 本文档介绍如何通过将存档数据库添加到现有部署来部署存档数据库。
    
如果在一个前端池或 Standard Edition Server 上启用存档，应为部署中的所有其他前端池和 Standard Edition Server 启用存档。 这是因为需要存档通信内容的用户可能会受邀参加其他池中承载的组 IM 对话或会议。 如果承载对话或会议的池上没有启用存档，则无法存档完整会话。 在这些情况下，仍可以为启用了存档的 IM 的用户进行存档，但不能为会议内容文件以及会议加入或离开事件存档。
  
> [!IMPORTANT]
> 如果出于合规性原因，存档在组织中至关重要，请确保在适当的级别部署存档、配置策略和其他选项，然后为所有用户启用存档，然后再为这些用户启用 Skype for Business Server。 
  
下表提供在现有拓扑中部署存档所需步骤的概述。
  
|**阶段**|**步骤**|**角色和组成员身份**|**文档**|
|:-----|:-----|:-----|:-----|
|**安装必备软硬件** <br/> |若要使用 Microsoft Exchange 集成 (Exchange 为部分或所有用户存档存储) ，您需要现有 Exchange 部署。  <br/> 若要使用单独的存档 (数据库SQL Server数据库) 用于某些或所有用户的存档存储，SQL Server将存储存档数据的服务器上。  <br/> 存档在企业池的前端服务器和 Standard Edition Servers 上运行。 除了需要安装这些服务器外，没有额外的软硬件要求。  <br/> |属于本地 Administrators 组成员的域用户。  <br/> |[Skype for Business Server 2015 的服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Skype for Business Server 2015 的环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [计划集成 Skype for Business 和 Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[Skype for Business Server 2019 的系统要求](../../../SfBServer2019/plan/system-requirements.md) |
|**创建适当的内部拓扑以支持存档 (仅在未针对部署部署中的所有用户使用 Microsoft Exchange 集成时)** <br/> |运行拓扑生成器，将 Skype for Business Server 存档 (SQL Server添加到) 数据库，然后发布拓扑。  <br/> |要定义要合并存档数据库的拓扑，需要一个作为本地用户组的成员的帐户。  <br/> 要发布拓扑，帐户是 Domain admins 组和 RTCUniversalServerAdmins 组的成员，并且对要用于 Skype for Business Server 文件存储 (的文件共享具有完全控制权限 (可读/写/修改) ，以便拓扑生成器可以配置所需的 DACLs) 。  <br/> |[将存档数据库添加到 Skype for Business Server 中的现有部署](add-archiving-databases.md) <br/> |
|**仅在使用 Microsoft Exchange 集成 (配置服务器到服务器身份验证)** <br/> |配置服务器以启用 Skype for Business Server 和 Exchange 之间的身份验证。 我们建议运行 **Test-CsExchangeStorageConnectivity testuser_sipUri -Folder Dumpster，** 以在启用存档之前验证 Exchange 存档存储连接。 <br/> |具有用于管理服务器上的证书的相应权限的帐户。  <br/> |管理服务器到服务器身份验证  <br/> |
|**配置存档选项和策略** <br/> |配置存档，包括是否在所有数据存储) 使用 Microsoft Exchange 集成时，是否使用 Microsoft Exchange 集成、全局策略以及任何站点和用户策略 (，以及特定的存档选项（如临界模式和数据导出和清除）。  <br/> 如果使用 Microsoft Exchange 集成，请In-Place Exchange 保留策略。  <br/> |RTCUniversalServerAdmins 组（仅限于 Windows PowerShell）或向 CSArchivingAdministrator 或 CSAdministrator 角色分配用户。  <br/> |[配置 Skype for Business Server 的存档选项](configure-archiving-options.md) <br/> 如果使用 Microsoft Exchange 集成 (Exchange 产品文档) 。  <br/> |
   

