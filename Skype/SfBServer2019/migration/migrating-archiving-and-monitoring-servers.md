---
title: 迁移存档和监视服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 如果你在旧版环境中部署了存档服务器和监视服务器, 则可以在迁移前端池后在 Skype for Business Server 2019 环境中部署这些服务器。 但是, 如果存档和监视功能对你的组织至关重要, 则应在迁移之前将存档和监视添加到 Skype for business Server 2019 试验池, 以便在迁移过程中使用该功能。
ms.openlocfilehash: 94a3d21b9b76d18f63fdf7db53144b1d51deb53c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298195"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>迁移存档和监视服务器

如果你在旧版环境中部署了存档服务器和监视服务器, 则可以在迁移前端池后在 Skype for Business Server 2019 环境中部署这些服务器。 但是, 如果存档和监视功能对你的组织至关重要, 则应在迁移之前将存档和监视添加到 Skype for business Server 2019 试验池, 以便在迁移过程中使用该功能。 
  
如果在迁移过程中需要存档和监视功能, 请记住以下注意事项:
  
- 存档数据和监视数据不会迁移到 Skype for business Server 2019 部署。 您在取消旧版环境之前备份的数据将成为旧环境中的活动历史记录。
    
- 旧版本的存档服务器和监视服务器只能与旧版前端池关联。 在 Skype for Business Server 2019 中, 存档和监控不再是服务器角色, 而是集成到 Skype for business Server 2019 前端池的服务。
    
- 在旧版本和 Skype for business Server 2019 部署共存期间, 旧版本的存档服务器和监视服务器会为驻留在旧版池中的用户收集数据。 Skype for business Server 2019 中的存档和监视为驻留在 Skype for business Server 2019 池中的用户收集数据。
    
    > [!NOTE]
    > 在迁移阶段, 当你仍将旧式 Edge 服务器与新的 Skype for business Server 2019 试验池配合使用时, 旧版本的存档服务器会继续为驻留在旧版池中的用户收集数据, 并在 Skype for business 中存档服务器2019为驻留在 Skype for business Server 2019 池的用户收集数据。 
  
- 如果在 Skype for business Server 2019 中结合使用第三方存档和监视解决方案, 请与供应商联系, 了解何时以及如何使用 Skype for business Server 2019 集成第三方解决方案。
    

