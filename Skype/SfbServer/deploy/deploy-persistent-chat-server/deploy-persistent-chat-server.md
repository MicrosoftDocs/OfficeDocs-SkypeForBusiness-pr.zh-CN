---
title: Deploy Persistent Chat Server in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: 摘要：阅读本主题，了解如何Skype for Business Server 2015 持久聊天服务器。
ms.openlocfilehash: ad0b78366613355859f8fec512d427ef3e3d5bdb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619198"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>Deploy Persistent Chat Server in Skype for Business Server 2015
 
**摘要：** 阅读本主题，了解如何部署 2015 Skype for Business Server持久聊天服务器。
  
若要部署持久聊天服务器，您需要： 
  
- 使用拓扑生成器定义、导入和随后发布拓扑和要部署的组件
    
- 准备部署持久聊天服务器组件的环境
    
- 安装和配置部署的持久聊天服务器组件
    
在部署持久聊天服务器之前，应阅读 Plan [for Persistent Chat Server in Skype for Business Server 2015。](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md) 规划主题介绍硬件和软件要求、可能的拓扑和并置方案。 
  
> [!NOTE] 
> 持久聊天在 Skype for Business Server 2015 中可用，但在 2019 年 2 Skype for Business Server不再受支持。 相同的功能在 Teams。 有关详细信息，请参阅[开始升级Microsoft Teams升级](/microsoftteams/upgrade-start-here)。 如果您需要使用持久聊天，则选择将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。 

## <a name="deployment-checklist"></a>部署清单

可以在部署初始拓扑后部署持久聊天服务器，包括至少一个Skype for Business Server前端池或一Skype for Business Standard Edition服务器。 部署清单介绍部署持久聊天服务器所需的基本步骤，并提供更多详细信息的链接。
  
**持久聊天服务器部署过程**

|**任务**|**步骤**|**所需角色和组成员身份**|**相关主题**|
|:-----|:-----|:-----|:-----|
|**安装必备软硬件** <br/> | 在满足系统要求的硬件上安装以下内容： <br/>  在持久聊天服务器前端服务器上： <br/>  满足系统要求的操作系统 <br/>  运行 Skype for Business Server <br/>  在将承载持久聊天服务器数据库的服务器上： <br/>  支持的版本SQL Server <br/>  如果需要持久聊天服务器合规性： <br/>  SQL Server持久聊天服务器合规性数据库的服务器上运行 <br/> |属于本地 Administrators 组成员的任何用户。  <br/> |[Skype for Business Server 2015 的服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [2015 年 Skype for Business Server 环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Skype for Business Server 2015 中的持久聊天服务器的硬件和软件要求](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**创建相应的内部拓扑以支持持久聊天服务器 (（可选）持久聊天合规性)** <br/> | 运行拓扑生成器以将持久聊天服务器池添加到拓扑： <br/>  将持久聊天服务器组件添加到拓扑 <br/>  为持久SQL Server服务器存储数据库创建一个 (，并创建一SQL Server备份数据库)  <br/>  定义新的Skype for Business文件存储或使用持久Skype for Business服务器文件的现有文件存储 <br/>  将可以将Skype for Business Server路由到此持久聊天服务器池的持久聊天服务器池关联 <br/>  如果需要持久聊天合规性： <br/>  添加持久聊天合规性存储 <br/>  单击"持久聊天服务器池定义"复选框以启用合规性 <br/>  发布拓扑。 <br/>  如果在 Standard Edition 上安装持久聊天服务器，则持久聊天服务器池的完全限定域名 (FQDN) 必须与 Standard Edition 服务器匹配，并且 SQL Server 数据库并位于 Standard Edition 服务器的 SQL Server Express 实例上 <br/> |要定义拓扑，需要具有本地 Users 组成员身份的帐户。  <br/> 要发布拓扑，需具有 Domain Admins 组和 RTCUniversalServerAdmins 组的成员的帐户，并且用户还应具有对 Skype for Business 文件存储（对于持久聊天服务器文件 (）的 (读/写/修改) 的完全控制权限，以便拓扑生成器可以配置所需的 DACLs) 。  <br/> |[在 2015 年 10 月Skype for Business Server拓扑](../../deploy/install/create-and-publish-new-topology.md) <br/> [将持久聊天服务器添加到 Skype for Business Server 2015 拓扑](add-persistent-chat-server.md) <br/> |
|**部署持久聊天服务器** <br/> | 在Skype for Business Server持久聊天服务器的所有计算机上运行该安装程序。 持久聊天服务器设置已集成到 Skype for Business Server 部署向导中，该向导提供以下说明： <br/>  部署本地管理存储 <br/>  安装持久聊天服务 <br/>  请求和分配证书 <br/>  运行并启动服务 <br/> |属于本地 Administrators 组成员的任何用户。  <br/> |[Deploy Persistent Chat Server in Skype for Business Server 2015](deploy-persistent-chat-server.md) <br/> |
|**创建持久聊天管理员** <br/> |将用户添加到 CsPersistentChatAdministrator 安全组。  <br/> |属于域管理员成员的任何用户。  <br/> |[在 2015 Skype for Business Server持久聊天管理员](create-a-persistent-chat-administrator.md) <br/> |
|**配置持久聊天服务器** <br/> | 配置用户： <br/>  用户必须启用策略，以访问持久聊天服务器。 默认情况下，该策略对所有用户都处于关闭状态，并且可以在全局/站点/池/用户范围进行定义。 <br/>  配置设置 <br/> |用户必须是 CsPersistentChatAdministrator 的成员。要更改策略，用户必须至少属于 CsUserAdministrator。  <br/> |[Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

