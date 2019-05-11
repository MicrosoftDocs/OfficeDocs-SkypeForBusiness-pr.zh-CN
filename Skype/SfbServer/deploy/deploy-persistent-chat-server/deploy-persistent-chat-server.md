---
title: 部署 Skype for Business Server 2015 中的持久聊天服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: 摘要： 阅读本主题可了解如何部署 Skype 业务 2015年持久聊天服务器。
ms.openlocfilehash: 2b88d20437a85c9a634bf8a156a3dcec214c60fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894463"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>部署 Skype for Business Server 2015 中的持久聊天服务器
 
**摘要：** 阅读本主题可了解如何部署 Skype 业务 2015年持久聊天服务器。
  
部署持久聊天服务器，您： 
  
- 使用拓扑生成器定义，或导入，并随后发布您的拓扑和要部署的组件
    
- 准备您的环境部署持久聊天服务器组件
    
- 安装和配置要部署的持久聊天服务器组件
    
部署持久聊天服务器之前，您应阅读[Plan for Persistent Chat Server in Skype 的业务服务器 2015年](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。 该规划主题介绍了软硬件要求、可能的拓扑和并置方案。 
  
> [!NOTE] 
> 持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。 中团队提供了相同的功能。 有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。 如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。 

## <a name="deployment-checklist"></a>部署清单

在部署初始拓扑，包括至少一个 Skype 业务 Server 前端池或一个 Skype 的业务 Standard Edition Server 后，您可以部署持久聊天服务器。 部署检查表介绍部署持久聊天服务器所需的基本步骤，并提供了更多详细信息的链接。
  
**持久聊天服务器的部署过程**

|**Task**|**步骤**|**所需角色和组成员身份**|**相关主题**|
|:-----|:-----|:-----|:-----|
|**安装必备硬件和软件** <br/> | 在满足系统要求的硬件上安装以下内容： <br/>  对持久聊天服务器前端服务器： <br/>  满足系统要求的操作系统 <br/>  运行 Business Server Skype 的计算机的必备软件 <br/>  在服务器上将承载 Persistent Chat Server 数据库： <br/>  支持的 SQL Server 版本 <br/>  如果需要持久聊天服务器合规性： <br/>  将承载持久聊天服务器合规性数据库的服务器上的 SQL Server <br/> |属于本地 Administrators 组成员的任何用户。  <br/> |[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**创建适当的内部拓扑以支持持久聊天服务器 （和 （可选） 持久聊天合规性）** <br/> | 运行拓扑生成器向拓扑添加持久聊天服务器池： <br/>  向拓扑添加持久聊天服务器组件 <br/>  创建 SQL Server 数据库对于 Persistent Chat Server 存储 （和灾难恢复备份 SQL Server） <br/>  定义业务文件存储的新 Skype 或用于现有 Skype 业务文件存储对于 Persistent Chat Server 文件 <br/>  关联可将请求路由到此持久聊天服务器池的业务服务器池的 Skype <br/>  如果需要持久聊天合规性： <br/>  添加持久聊天合规性存储 <br/>  单击以启用合规性的持久聊天服务器池定义复选框 <br/>  发布拓扑。 <br/>  如果在 Standard Edition 上安装持久聊天服务器，持久聊天服务器池的完全限定的域名 (FQDN) 必须匹配 Standard Edition server，并对标准的 SQL Server Express 实例上并置的 SQL Server 数据库版服务器 <br/> |要定义拓扑，需要具有本地 Users 组成员身份的帐户。  <br/> 若要发布拓扑，Domain Admins 组和 RTCUniversalServerAdmins 组和用户的成员的帐户应还拥有完全控制权限 （读/写/修改） 上业务文件存储的 Skype 对于 Persistent Chat Server 文件 （是这样该拓扑生成器可以配置所需的 Dacl）。  <br/> |[在 Skype for Business Server 2015 中创建和发布新拓扑](../../deploy/install/create-and-publish-new-topology.md) <br/> [向您 Skype 业务服务器 2015年拓扑添加持久聊天服务器](add-persistent-chat-server.md) <br/> |
|**部署持久聊天服务器** <br/> | 运行持久聊天服务器的所有计算机上运行的业务服务器安装程序 Skype。 持久聊天服务器安装已集成到业务 Server 部署向导提供以下说明 Skype: <br/>  部署本地管理存储 <br/>  安装持久聊天服务 <br/>  请求和分配证书 <br/>  运行并启动服务 <br/> |属于本地 Administrators 组成员的任何用户。  <br/> |[部署 Skype for Business Server 2015 中的 Persistent Chat Server](deploy-persistent-chat-server.md) <br/> |
|**创建持久聊天管理员** <br/> |将用户添加到 CsPersistentChatAdministrator 安全组。  <br/> |属于域管理员成员的任何用户。  <br/> |[在 Skype for Business Server 2015 中创建持久聊天管理员](create-a-persistent-chat-administrator.md) <br/> |
|**配置持久聊天服务器** <br/> | 配置用户： <br/>  用户必须由策略启用访问 Persistent Chat Server。 默认情况下，该策略对所有用户都处于关闭状态，并且可以在全局/站点/池/用户范围进行定义。 <br/>  配置设置 <br/> |用户必须是 CsPersistentChatAdministrator 的成员。要更改策略，用户必须至少属于 CsUserAdministrator。  <br/> |[管理 Skype for Business Server 2015 中的持久聊天服务器](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

