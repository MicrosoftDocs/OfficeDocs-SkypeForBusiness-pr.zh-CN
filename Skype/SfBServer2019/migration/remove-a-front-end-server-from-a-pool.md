---
title: 从池中删除前端服务器
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
description: 前端服务器不能作为独立计算机存在。 必须将其定义为前端池，即使池中只有一台计算机也是如此。
ms.openlocfilehash: 7675ba119fa2937d765d5f4e497fca0a040b3b62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752314"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>从池中删除前端服务器

前端服务器不能作为独立计算机存在。 必须将其定义为前端池，即使池中只有一台计算机也是如此。
  
本主题将指导您完成从现有前端池删除单个前端服务器的过程。 如果前端服务器是池中的最后一台服务器，或者如果要完全删除池，请参阅[删除前端池或 Standard Edition Server](remove-front-end-pool-or-standard-edition-server.md)。 在删除前端池之前，无需删除单个前端服务器。 删除池时，会删除每个前端服务器。
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>从池中删除前端服务器

1. 在 Skype for Business Server 2019 前端服务器上，打开拓扑生成器。
    
2. 导航到旧版安装节点。
    
3. 展开 " **Enterprise Edition 前端池**"，再展开要删除的前端服务器的前端池，右键单击要删除的前端服务器，然后单击 "**删除**"。
    

