---
title: 删除前端池或 Standard Edition Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本主题将指导你完成删除前端池或标准版前端服务器的过程。 删除前端池时, 将在池删除过程中删除属于该池的每个前端服务器。 删除标准版前端服务器时, 必须从拓扑生成器中删除 SQL 应用商店定义。
ms.openlocfilehash: fd43682fca67b961ac93c01813ca6ea9e702b644
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301130"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>删除前端池或 Standard Edition Server

本文将引导你完成删除前端池或标准版前端服务器的过程。 删除前端池时, 将在池删除过程中删除属于该池的每个前端服务器。 删除标准版前端服务器时, 必须从拓扑生成器中删除 SQL 应用商店定义。
  
## <a name="to-remove-a-front-end-server-pool"></a>删除前端服务器池

1. 打开拓扑生成器。
    
2. 导航到 "旧版" 节点。
    
3. 展开 "**企业版前端池**", 展开 "前端池", 右键单击要删除的前端池, 然后单击 "**删除**"。
    
4. 发布拓扑, 检查复制状态, 然后根据需要运行旧版部署向导。 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>删除标准版前端服务器

1. 打开拓扑生成器。
    
2. 导航到 "旧版安装" 节点。
    
3. 展开**标准版前端服务器**, 右键单击要删除的前端服务器, 然后单击 "**删除**"。
    
4. 展开 " **sql 存储**", 右键单击与标准版前端服务器关联的 SQL Server 数据库, 然后单击 "**删除**"。
    
    > [!IMPORTANT]
    > 必须从标准版前端服务器中删除 collocated SQL Server 数据库的定义。 
  
5. 发布拓扑, 检查复制状态, 然后根据需要运行部署向导。 
    

