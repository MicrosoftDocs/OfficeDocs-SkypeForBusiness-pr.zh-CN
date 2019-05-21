---
title: 部署 Skype for Business Server 2015 中的持久聊天服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: '摘要: 阅读本主题, 了解如何部署 Skype for Business Server 2015 持久聊天服务器。'
ms.openlocfilehash: 06cc51ccbbab193e749c2f919102d7d38fde3f56
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273894"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>部署 Skype for Business Server 2015 中的持久聊天服务器
 
**摘要:** 阅读本主题, 了解如何部署 Skype for Business Server 2015 持久聊天服务器。
  
若要部署持久聊天服务器, 请执行以下操作: 
  
- 使用拓扑生成器定义或导入拓扑, 以及随后发布你要部署的组件
    
- 准备部署持久聊天服务器组件的环境
    
- 为你的部署安装和配置持久聊天服务器组件
    
在部署持久聊天服务器之前, 应[在 Skype for Business server 2015 中阅读持久聊天服务器计划](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。 该规划主题介绍了软硬件要求、可能的拓扑和并置方案。 
  
> [!NOTE] 
> Skype for business Server 2015 中提供了持久聊天, 但 Skype for business Server 2019 不再支持此功能。 团队中提供了相同的功能。 有关详细信息, 请参阅[从 Skype For Business 迁移到 Microsoft 团队](/microsoftteams/journey-skypeforbusiness-teams)。 如果需要使用持久聊天, 您可以选择将需要此功能的用户迁移到团队, 或继续使用 Skype for Business Server 2015。 

## <a name="deployment-checklist"></a>部署清单

部署初始拓扑 (包括至少一个 Skype for business Server 前端池或一个 Skype for business 标准版服务器) 后, 你可以部署持久聊天服务器。 部署清单描述部署持久聊天服务器所需的基本步骤, 并提供有关更多详细信息的链接。
  
**持久聊天服务器部署过程**

|**Task**|**步骤**|**所需角色和组成员身份**|**相关主题**|
|:-----|:-----|:-----|:-----|
|**安装必备硬件和软件** <br/> | 在满足系统要求的硬件上安装以下内容： <br/>  在持久聊天服务器前端服务器上: <br/>  满足系统要求的操作系统 <br/>  运行 Skype for Business Server 的计算机的软件先决条件 <br/>  在将承载持久聊天服务器数据库的服务器上: <br/>  支持的 SQL Server 版本 <br/>  如果需要持久聊天服务器合规性, 请执行以下操作: <br/>  将托管持久聊天服务器合规性数据库的服务器上的 SQL Server <br/> |属于本地 Administrators 组成员的任何用户。  <br/> |[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**创建适当的内部拓扑以支持持久聊天服务器 (以及持续聊天合规性)** <br/> | 运行拓扑生成器以将持久聊天服务器池添加到拓扑中: <br/>  向拓扑添加持久聊天服务器组件 <br/>  为持久聊天服务器存储创建 SQL Server 数据库 (以及用于灾难恢复的备份 SQL Server) <br/>  定义新的 Skype for Business 文件存储或对持久聊天服务器文件使用现有 Skype for business 文件存储 <br/>  关联的 Skype for Business 服务器池可将请求路由到此持久聊天服务器池 <br/>  如果需要持久聊天合规性： <br/>  添加持久聊天合规性存储 <br/>  单击 "持久聊天服务器池定义" 复选框以启用合规性 <br/>  发布拓扑。 <br/>  如果在标准版上安装持久聊天服务器, 则持久聊天服务器池的完全限定的域名 (FQDN) 必须与标准版服务器匹配, 并且 SQL Server 数据库在标准版的 SQL Server Express 实例上 collocatedEdition 服务器 <br/> |要定义拓扑，需要具有本地 Users 组成员身份的帐户。  <br/> 若要发布拓扑 (属于 "域管理员" 组和 "RTCUniversalServerAdmins" 组的成员), 用户还应该对持久聊天服务器文件具有 "Skype for Business 文件存储" 的 "完全控制" 权限 (读/写/修改)拓扑生成器可以配置所需的 Dacl。  <br/> |[在 Skype for Business Server 2015 中创建和发布新拓扑](../../deploy/install/create-and-publish-new-topology.md) <br/> [将持久聊天服务器添加到 Skype for business Server 2015 拓扑](add-persistent-chat-server.md) <br/> |
|**部署持久聊天服务器** <br/> | 在运行持久聊天服务器的所有计算机上运行 Skype for Business 服务器设置。 持久聊天服务器设置集成到 Skype for Business 服务器部署向导中, 该向导提供以下说明: <br/>  部署本地管理存储 <br/>  安装持久聊天服务 <br/>  请求和分配证书 <br/>  运行并启动服务 <br/> |属于本地 Administrators 组成员的任何用户。  <br/> |[部署 Skype for Business Server 2015 中的 Persistent Chat Server](deploy-persistent-chat-server.md) <br/> |
|**创建持久聊天管理员** <br/> |将用户添加到 CsPersistentChatAdministrator 安全组。  <br/> |属于域管理员成员的任何用户。  <br/> |[在 Skype for Business Server 2015 中创建持久聊天管理员](create-a-persistent-chat-administrator.md) <br/> |
|**配置持久聊天服务器** <br/> | 配置用户： <br/>  必须通过策略启用用户才能访问持久聊天服务器。 默认情况下，该策略对所有用户都处于关闭状态，并且可以在全局/站点/池/用户范围进行定义。 <br/>  配置设置 <br/> |用户必须是 CsPersistentChatAdministrator 的成员。要更改策略，用户必须至少属于 CsUserAdministrator。  <br/> |[管理 Skype for Business Server 2015 中的持久聊天服务器](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

