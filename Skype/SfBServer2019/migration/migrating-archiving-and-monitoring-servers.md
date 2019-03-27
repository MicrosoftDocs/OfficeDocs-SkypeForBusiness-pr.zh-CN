---
title: 迁移存档和监控服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 如果旧环境中部署存档服务器与监控服务器，可以在迁移前端池后在您 Skype 业务服务器 2019年环境中部署这些服务器。 但是，如果存档和监控功能对组织至关重要，应添加存档和监控业务服务器 2019年试点池您 Skype 到迁移，以便该功能，在迁移过程之前。
ms.openlocfilehash: 24dc3e3007fd9a58c23f9c15a31cccc766d45e83
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896090"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>迁移存档和监控服务器

如果旧环境中部署存档服务器与监控服务器，可以在迁移前端池后在您 Skype 业务服务器 2019年环境中部署这些服务器。 但是，如果存档和监控功能对组织至关重要，应添加存档和监控业务服务器 2019年试点池您 Skype 到迁移，以便该功能，在迁移过程之前。 
  
如果您希望在迁移过程中的存档和监控功能，请记住以下注意事项：
  
- 存档数据和监控数据不移到 Skype 业务服务器 2019年部署。 停用旧环境之前备份的数据将旧环境中的活动的历史记录。
    
- 存档服务器与监控服务器的旧版本可以仅与旧的前端池相关联。 中的业务服务器 2019 Skype，存档和监控不再服务器角色，但集成到业务 Server 2019 前端池的 Skype 的服务。
    
- 在时间的旧式和 Skype 业务服务器 2019年部署共存，存档服务器与监控服务器的旧版本的用户驻留在旧池上收集数据。 存档和监控业务服务器 2019年的 Skype 中收集用户的数据的业务服务器 2019年池驻留在 Skype。
    
    > [!NOTE]
    > 阶段的迁移后仍使用与业务服务器 2019 试点池，存档服务器的旧版本继续收集用户的数据的新 Skype 旧版边缘服务器驻留在旧池和 Skype for Business 中的存档服务器 2019年收集用户的数据的业务服务器 2019年池驻留在 Skype。 
  
- 如果您使用第三方存档和监控业务服务器 2019年与存档和监控 Skype 中的结合使用的解决方案，请咨询您供应商联系时间和方式需要与 Skype 的第三方解决方案集成的业务服务器 2019年。
    

