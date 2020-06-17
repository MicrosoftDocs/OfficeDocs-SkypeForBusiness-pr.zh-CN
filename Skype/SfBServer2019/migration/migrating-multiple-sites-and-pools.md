---
title: 迁移多个站点和池
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
description: Skype for Business Server 2019 支持多站点部署和多池部署。 将多个池迁移到 Skype for business Server 2019 的过程需要以下注意事项：
ms.openlocfilehash: 4906b05138d546e685a06acecc4f7adc4e88516e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752654"
---
# <a name="migrating-multiple-sites-and-pools"></a>迁移多个站点和池

Skype for Business Server 2019 支持多站点部署和多池部署。 将多个池迁移到 Skype for business Server 2019 的过程需要以下注意事项： 
  
1. 部署 Skype for Business Server 2019 试点池之后，需要定义将移动到 Skype for Business Server 2019 池的试点用户的子集，以及用于验证用户功能的方法。 例如，在将用户移动到引导池之后，验证用户的会议策略是否已移动到 Skype for Business Server 2019。 
    
2. 在引导池中部署边缘服务器之后，需要验证外部用户是否可以与 Skype for Business Server 2019 池通信。

3. Skype for Business Server 2019 中已弃用持久聊天、SQL 镜像和 XMPP 功能，并且不再作为 Skype for business Server 2019 功能提供，但它们可以在共存环境中继续进行（如果它们之前已部署在旧环境中）。 如果要继续使用这些功能，则应计划继续使用共存环境，其中某些用户将保留在旧版池中。
    
4. 将联合路由的边缘服务器转换为试点 Skype for business Server 2019 边缘服务器后，需要验证联合用户是否可以与 Skype for business Server 2019 池通信。
    
5. 移动所有用户和非用户联系人对象之后，需要验证旧版池是否为空。
    
6. 验证旧版池是否为空之后，您可以停用池。 
    
    有关如何停用旧版池和服务器的详细信息，请参阅[第8阶段：停止旧版池](phase-8-decommission-legacy-pools.md)。
    

