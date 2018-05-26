---
title: 添加持久聊天文件存储
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: 必须为 Standard Edition Server 或 Enterprise Edition 前端池指定用作文件存储的文件共享。可以将现有的文件共享用作文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。
ms.openlocfilehash: 989e11adfd7059c94067dd8360527d86759ae81c
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2018
---
# <a name="add-persistent-chat-file-store"></a>添加持久聊天文件存储
 
必须为 Standard Edition Server 或 Enterprise Edition 前端池指定用作文件存储的文件共享。可以将现有的文件共享用作文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。
  
> [!IMPORTANT]
> Skype 业务服务器的文件共享不能位于 Enterprise Edition 前端服务器，但可以位于 Standard Edition server 上。 
  
> [!IMPORTANT]
> 可以先在拓扑生成器中定义文件共享，再创建文件共享，但是必须在发布拓扑前在定义的位置创建文件共享。 
  
> [!IMPORTANT]
> 当添加持久聊天服务器或池拓扑中，拓扑生成器必须能够设置文件的持久聊天服务器存储和配置随机访问控制列表 (Dacl) 用于文件存储的文件共享上。 这就要求在运行拓扑生成器以发布新拓扑时，需使用对文件共享具有完全控制权限（读/写/修改）的帐户登录。 
  
## <a name="see-also"></a>另请参阅

#### 

[规划持久聊天服务器 Skype 中的业务 Server 2015](../../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[向您 Skype 业务服务器 2015年拓扑添加持久聊天服务器](../../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[硬件和软件要求对于 Persistent Chat Server in Skype 业务服务器 2015](../../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Skype for Business Server 2015 服务器要求](../../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[拓扑的业务服务器 2015 Skype 的基础知识](../../../plan-your-deployment/topology-basics/topology-basics.md)

