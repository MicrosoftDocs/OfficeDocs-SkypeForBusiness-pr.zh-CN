---
title: 添加持久聊天文件存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: 必须为 Standard Edition Server 或 Enterprise Edition 前端池指定用作文件存储的文件共享。可以将现有的文件共享用作文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。
ms.openlocfilehash: f11443f8c10db35d5ffb8bfdbfc03d9826700b7c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820674"
---
# <a name="add-persistent-chat-file-store"></a>添加持久聊天文件存储
 
必须为 Standard Edition Server 或 Enterprise Edition 前端池指定用作文件存储的文件共享。可以将现有的文件共享用作文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。
  
> [!IMPORTANT]
> Skype for Business Server 的文件共享不能位于企业版前端服务器上，但可以位于标准版服务器上。 
  
> [!IMPORTANT]
> 可以先在拓扑生成器中定义文件共享，再创建文件共享，但是必须在发布拓扑前在定义的位置创建文件共享。 
  
> [!IMPORTANT]
> 将持久聊天服务器或持久聊天服务器池添加到拓扑中时，拓扑生成器必须能够设置文件存储并在要用于文件存储的文件共享上配置随机访问控制列表（Dacl）。 这就要求在运行拓扑生成器以发布新拓扑时，需使用对文件共享具有完全控制权限（读/写/修改）的帐户登录。 
  
## <a name="see-also"></a>另请参阅

[规划 Skype for Business Server 2015 中的持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[将持久聊天服务器添加到 Skype for business Server 2015 拓扑](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Skype for Business Server 2015 中持久聊天服务器的硬件和软件要求](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Skype for Business Server 2015 的拓扑基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)
