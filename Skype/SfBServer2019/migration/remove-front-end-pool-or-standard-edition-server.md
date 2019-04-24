---
title: 删除前端池或 Standard Edition Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本主题将指导您完成删除前端池或 Standard Edition 前端服务器的过程。 删除前端池时，您删除每个前端服务器池删除过程一部分属于池。 删除 Standard Edition 前端服务器时，您必须从拓扑生成器删除 SQL 存储定义。
ms.openlocfilehash: 394edcd6f5c89478ed98abebe0be29720d009107
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231544"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>删除前端池或 Standard Edition Server

本文将指导您完成删除前端池或 Standard Edition 前端服务器的过程。 删除前端池时，您删除每个前端服务器池删除过程一部分属于池。 删除 Standard Edition 前端服务器时，您必须从拓扑生成器删除 SQL 存储定义。
  
## <a name="to-remove-a-front-end-server-pool"></a>删除前端服务器池

1. 打开拓扑生成器。
    
2. 导航到旧节点。
    
3. 展开**Enterprise Edition 前端池**，展开前端池，右键单击您想要删除的前端池，然后单击**删除**。
    
4. 发布拓扑，检查复制状态，并根据需要运行旧部署向导。 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>删除 Standard Edition 前端服务器

1. 打开拓扑生成器。
    
2. 导航到旧的安装节点。
    
3. 展开**Standard Edition 前端服务器**，右键单击您想要删除的前端最终服务器，然后单击**删除**。
    
4. 展开**SQL 存储**，右键单击与 Standard Edition 前端服务器关联的 SQL Server 数据库，然后单击**删除**。
    
    > [!IMPORTANT]
    > 必须从 Standard Edition 前端服务器中删除的并置的 SQL Server 数据库的定义。 
  
5. 发布拓扑，检查复制状态，并根据需要然后运行部署向导。 
    

