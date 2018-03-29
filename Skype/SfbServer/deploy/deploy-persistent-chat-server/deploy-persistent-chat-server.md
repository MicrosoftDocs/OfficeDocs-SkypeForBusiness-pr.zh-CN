---
title: 部署 Skype for Business Server 2015 中的持久聊天服务器
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: 摘要： 阅读本主题，以了解如何为企业 2015年持久聊天服务器部署 Skype。
ms.openlocfilehash: c2dedae876c61f84d672f8cf457e1b6c4baeff43
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>部署 Skype for Business Server 2015 中的持久聊天服务器
 
**摘要：**阅读本主题，以了解如何为企业 2015年持久聊天服务器部署 Skype。
  
要部署持续聊天服务器，您： 
  
- 使用拓扑生成器来定义，或导入，并随后发布您的拓扑结构和您要部署的组件
    
- 准备您的环境部署持续聊天服务器组件
    
- 安装和配置您的部署的持久聊天服务器组件
    
部署持续聊天服务器之前，您应该阅读[规划业务服务器 2015年的 Skype 的持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。 该规划主题介绍了软硬件要求、可能的拓扑和并置方案。 
  
## <a name="deployment-checklist"></a>部署清单

在部署您的初始拓扑，其中包括至少一个 Skype 业务服务器前端池或一个 Skype 业务标准版服务器之后，您可以部署持续聊天服务器。 部署清单描述持久聊天服务器部署所需的基本步骤，并提供更多详细信息的链接。
  
**持久的聊天服务器部署过程**

|**任务**|**步骤**|**必需的角色和组成员身份**|**相关的主题**|
|:-----|:-----|:-----|:-----|
|**安装必备硬件和软件** <br/> | 在满足系统要求的硬件上安装以下内容： <br/>  在持久聊天服务器的前端服务器： <br/>  满足系统要求的操作系统 <br/>  软件运行 Skype 业务服务器的计算机的系统必备组件 <br/>  在服务器上将承载持久聊天服务器数据库： <br/>  支持的 SQL Server 版本 <br/>  如果持续聊天服务器的符合性是必需的： <br/>  SQL Server 将承载持久聊天服务器的法规遵从性数据库的服务器上 <br/> |属于本地 Administrators 组成员的任何用户。  <br/> |[业务服务器 2015 Skype 的的服务要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [环境要求为 Skype 的业务服务器 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [硬件和软件要求在 Skype 的持久聊天服务器的业务服务器 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**创建相应的内部拓扑结构，以支持持久聊天服务器 （和 （可选） 持续聊天的法规遵从性）** <br/> | 运行拓扑生成器将持续聊天服务器池添加到您的拓扑： <br/>  添加到拓扑结构中的持久聊天服务器组件 <br/>  创建持久聊天服务器存储库 （以及灾难恢复备份 SQL Server） 的 SQL Server 数据库 <br/>  定义新的 Skype 业务文件存储或用于持久聊天服务器文件现有的 Skype 业务文件存储 <br/>  将相关联业务服务器可以将请求路由到此持续聊天服务器池的池的 Skype <br/>  如果需要持久聊天合规性： <br/>  添加永久聊天的法规遵从性存储 <br/>  单击用于实现法规遵从性的持久聊天服务器池定义复选框 <br/>  发布拓扑。 <br/>  如果您在标准版上安装了永久性的聊天服务器，持久聊天服务器池完全限定的域名 (FQDN) 必须匹配标准版服务器上，并且对标准的 SQL Server Express 实例上搭配使用的 SQL Server 数据库版本服务器 <br/> |要定义拓扑，需要具有本地 Users 组成员身份的帐户。  <br/> 若要发布拓扑结构，属于域管理员组和 RTCUniversalServerAdmins 组和用户帐户应还拥有完全控制权限 （读/写/修改） 业务文件存储为 Skype 上持久聊天服务器文件 （这样该拓扑生成器可以配置所需的 Dacl）。  <br/> |[创建并发布新的拓扑结构在 Skype 业务服务器 2015](../../deploy/install/create-and-publish-new-topology.md) <br/> [持久的聊天服务器添加到您的 Skype 业务服务器 2015年拓扑](add-persistent-chat-server.md) <br/> |
|**持久的聊天服务器部署** <br/> | 运行持续聊天服务器的所有计算机上运行的业务服务器安装 Skype。 持久的聊天服务器安装程序已集成到 Skype 业务服务器部署向导提供了下列指导： <br/>  部署本地管理存储 <br/>  安装永久聊天服务 <br/>  请求和分配证书 <br/>  运行并启动服务 <br/> |属于本地 Administrators 组成员的任何用户。  <br/> |[为业务服务器 2015年部署在 Skype 的持久聊天服务器](deploy-persistent-chat-server.md) <br/> |
|**创建一个持久聊天管理员** <br/> |将用户添加到 CsPersistentChatAdministrator 安全组。  <br/> |属于域管理员成员的任何用户。  <br/> |[在 Skype 业务服务器 2015年创建持久聊天的管理员](create-a-persistent-chat-administrator.md) <br/> |
|**配置持久聊天服务器** <br/> | 配置用户： <br/>  用户已启用策略访问持久聊天服务器。 默认情况下，该策略对所有用户都处于关闭状态，并且可以在全局/站点/池/用户范围进行定义。 <br/>  配置设置 <br/> |用户必须是 CsPersistentChatAdministrator 的成员。要更改策略，用户必须至少属于 CsUserAdministrator。  <br/> |[管理业务服务器 2015年在 Skype 的持久聊天服务器](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

