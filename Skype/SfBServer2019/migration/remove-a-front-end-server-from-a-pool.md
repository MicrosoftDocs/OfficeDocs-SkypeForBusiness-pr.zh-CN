---
title: 从池中删除前端服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 前端服务器不能作为独立计算机上存在。 它必须被定义为前端池，即使池中只有一台计算机。
ms.openlocfilehash: a9f0adc991355b6f79b20365795ffaf92fa230e2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028941"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>从池中删除前端服务器

前端服务器不能作为独立计算机上存在。 它必须被定义为前端池，即使池中只有一台计算机。
  
本主题将指导您完成从现有的前端池删除单个前端服务器的过程。 如果在前端服务器池中的最后一个服务器或要完全删除该池，请参阅[删除前端池或 Standard Edition server](remove-front-end-pool-or-standard-edition-server.md)。 没有无需删除单个前端服务器，之前先删除前端池。 删除池时，您将删除每个前端服务器。
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>若要从池中删除前端服务器

1. 在业务 Server 2019 前端服务器的 Skype，打开拓扑生成器。
    
2. 导航到旧的安装节点。
    
3. 展开**Enterprise Edition 前端池**，展开前端池与前端服务器所需若要删除，右键单击前端服务器要删除，然后单击**删除**。
    

