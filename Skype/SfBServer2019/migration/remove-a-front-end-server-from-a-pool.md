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
ms.localizationpriority: medium
description: 前端服务器不能作为独立计算机存在。 它必须定义为前端池，即使池中只有一台计算机。
ms.openlocfilehash: b52954421034d83191e479e59d1efeeda8972868
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594996"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>从池中删除前端服务器

前端服务器不能作为独立计算机存在。 它必须定义为前端池，即使池中只有一台计算机。
  
本主题指导您完成从现有前端池删除单个前端服务器的过程。 如果前端服务器是池中的最后一台服务器，或者要完全删除该池，请参阅删除前端池或Standard Edition[服务器](remove-front-end-pool-or-standard-edition-server.md)。 在删除前端池之前，无需删除各个前端服务器。 删除池时，将删除每个前端服务器。
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>从池中删除前端服务器

1. 在 Skype for Business Server 2019 前端服务器上，打开拓扑生成器。
    
2. 导航到旧安装节点。
    
3. 展开 **Enterprise Edition** 前端池"，展开具有要删除的前端服务器的前端池，右键单击要删除的前端服务器，然后单击"删除 **"。**
    

