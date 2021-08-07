---
title: 删除前端池或 Standard Edition Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 本主题指导您完成删除前端池或前端Standard Edition的过程。 删除前端池时，会作为池删除过程的一部分删除属于该池的每个前端服务器。 删除前端Standard Edition时，必须从拓扑生成器SQL存储定义。
ms.openlocfilehash: 97407c05afc6055c02b7b54343bbd551c88e6a04236528a74da91f326bf9e25c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54304724"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>删除前端池或 Standard Edition Server

本文将指导您完成删除前端池或前端Standard Edition的过程。 删除前端池时，会作为池删除过程的一部分删除属于该池的每个前端服务器。 删除前端Standard Edition时，必须从拓扑生成器SQL存储定义。
  
## <a name="to-remove-a-front-end-server-pool"></a>删除前端服务器池

1. 打开拓扑生成器。
    
2. 导航到旧节点。
    
3. 展开 **Enterprise Edition前端池"，** 展开"前端池"，右键单击要删除的前端池，然后单击"删除 **"。**
    
4. 发布拓扑，检查复制状态，然后根据需要运行旧部署向导。 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>删除 Standard Edition 前端服务器

1. 打开拓扑生成器。
    
2. 导航到旧安装节点。
    
3. 展开 **Standard Edition前端服务器"，** 右键单击要删除的前端服务器，然后单击"删除 **"。**
    
4. 展开 **SQL存储"，** 右键单击SQL Server前端服务器关联的 Standard Edition 数据库，然后单击"删除 **"。**
    
    > [!IMPORTANT]
    > 必须从前端服务器中删除并SQL Server数据库Standard Edition的定义。 
  
5. 发布拓扑，检查复制状态，然后根据需要运行部署向导。 
    

