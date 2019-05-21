---
title: 从池中删除前端服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 前端服务器不能作为独立计算机存在。 它必须定义为前端池, 即使池中只有一台计算机。
ms.openlocfilehash: 5c1cd06e4cbe5cd6cecd8484e9c7874fb5ba590e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301137"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>从池中删除前端服务器

前端服务器不能作为独立计算机存在。 它必须定义为前端池, 即使池中只有一台计算机。
  
本主题将指导你完成从现有前端池删除单个前端服务器的过程。 如果前端服务器是池中的最后一个服务器, 或者如果你完全删除该池, 请参阅[删除前端池或标准版服务器](remove-front-end-pool-or-standard-edition-server.md)。 删除前端池之前无需删除单个前端服务器。 删除池时, 删除每个前端服务器。
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>从池中删除前端服务器

1. 在 Skype for Business 服务器2019前端服务器上, 打开拓扑生成器。
    
2. 导航到 "旧版安装" 节点。
    
3. 展开 "**企业版前端池**", 展开要删除的前端服务器的前端池, 右键单击要删除的前端服务器, 然后单击 "**删除**"。
    

