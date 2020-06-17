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
description: 本主题将指导您完成删除前端池或 Standard Edition 前端服务器的过程。 删除前端池时，会将属于池的每台前端服务器作为池删除过程的一部分删除。 删除 Standard Edition 前端服务器时，必须从拓扑生成器中删除 SQL 存储定义。
ms.openlocfilehash: 305a353ced45fe7e21ba479c0c3571df236aa09b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752274"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>删除前端池或 Standard Edition Server

本文将指导您完成删除前端池或 Standard Edition 前端服务器的过程。 删除前端池时，会将属于池的每台前端服务器作为池删除过程的一部分删除。 删除 Standard Edition 前端服务器时，必须从拓扑生成器中删除 SQL 存储定义。
  
## <a name="to-remove-a-front-end-server-pool"></a>删除前端服务器池

1. 打开拓扑生成器。
    
2. 导航到 "旧版" 节点。
    
3. 展开 " **Enterprise Edition 前端池**"，再展开 "前端池"，右键单击要删除的前端池，然后单击 "**删除**"。
    
4. 发布拓扑，检查复制状态，然后根据需要运行旧版部署向导。 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>删除 Standard Edition 前端服务器

1. 打开拓扑生成器。
    
2. 导航到 "旧版安装" 节点。
    
3. 展开**Standard Edition 前端服务器**，右键单击要删除的前端服务器，然后单击 "**删除**"。
    
4. 展开 " **sql 存储**"，右键单击与 Standard Edition 前端服务器关联的 SQL Server 数据库，然后单击 "**删除**"。
    
    > [!IMPORTANT]
    > 您必须从 Standard Edition 前端服务器中删除并置 SQL Server 数据库的定义。 
  
5. 发布拓扑，检查复制状态，然后根据需要运行部署向导。 
    

