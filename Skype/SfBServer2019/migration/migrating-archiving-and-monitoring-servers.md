---
title: 迁移存档和监控服务器
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
description: 如果在旧环境中部署了存档服务器和监控服务器，您可以在迁移前端池后在 Skype for Business Server 2019 环境中部署这些服务器。 但是，如果存档和监控功能对您的组织至关重要，您应在迁移之前将存档和监控添加到 Skype for Business Server 2019 试点池，以便该功能在迁移过程中可用。
ms.openlocfilehash: b1f497019d2043a7ea43c1134af615ae4db6183cd3d16593bfab6e835fa4db32
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303546"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>迁移存档和监控服务器

如果在旧环境中部署了存档服务器和监控服务器，您可以在迁移前端池后在 Skype for Business Server 2019 环境中部署这些服务器。 但是，如果存档和监控功能对您的组织至关重要，您应在迁移之前将存档和监控添加到 Skype for Business Server 2019 试点池，以便该功能在迁移过程中可用。 
  
如果迁移过程中需要存档和监控功能，应注意以下问题：
  
- 存档数据和监控数据不会移至 Skype for Business Server 2019 部署。 在停用旧环境之前备份的数据将成为旧环境中的活动历史记录。
    
- 存档服务器和监控服务器的旧版本只能与旧版前端池关联。 在 Skype for Business Server 2019 中，存档和监控不再是服务器角色，而是集成到 Skype for Business Server 2019 前端池中的服务。
    
- 在旧部署和 Skype for Business Server 2019 部署共存期间，旧版存档服务器和监控服务器收集旧池上用户的数据。 Skype for Business Server 2019 中的存档和监控收集 2019 池中Skype for Business Server用户的数据。
    
    > [!NOTE]
    > 在迁移阶段（当您仍将旧边缘服务器与新的 Skype for Business Server 2019 试点池一同使用）期间，旧版存档服务器将继续收集旧池上用户的数据，而 Skype for Business Server 2019 中的存档功能会收集 Skype for Business Server 2019 池中用户的数据。 
  
- 如果将第三方存档和监控解决方案与 Skype for Business Server 2019 中的存档和监控结合使用，请咨询您的供应商，了解何时以及如何将第三方解决方案与 Skype for Business Server 2019 集成。
    

