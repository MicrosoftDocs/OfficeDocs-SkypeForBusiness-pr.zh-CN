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
ms.openlocfilehash: 76b116d469bf6369174815d6b396a64149518f17
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-persistent-chat-file-store"></a>添加持久聊天文件存储
 
必须为 Standard Edition Server 或 Enterprise Edition 前端池指定用作文件存储的文件共享。可以将现有的文件共享用作文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。
  
> [!IMPORTANT]
> Skype 业务服务器的文件共享不能位于企业版前端服务器，但可以位于标准版服务器上。 
  
> [!IMPORTANT]
> 可以先在拓扑生成器中定义文件共享，再创建文件共享，但是必须在发布拓扑前在定义的位置创建文件共享。 
  
> [!IMPORTANT]
> 当添加持久性的聊天服务器或池对拓扑，拓扑生成器必须能够设置文件的持久聊天服务器存储和配置自由访问控制列表 (Dacl) 用于文件存储的文件共享上。 这就要求在运行拓扑生成器以发布新拓扑时，需使用对文件共享具有完全控制权限（读/写/修改）的帐户登录。 
  
## <a name="see-also"></a>另请参阅

#### 

[在 Skype 的持久聊天服务器业务服务器 2015年计划](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[持久的聊天服务器添加到您的 Skype 业务服务器 2015年拓扑](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[硬件和软件要求在 Skype 的持久聊天服务器的业务服务器 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[业务服务器 2015 Skype 的的服务要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Skype 业务服务器 2015年拓扑结构基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)

