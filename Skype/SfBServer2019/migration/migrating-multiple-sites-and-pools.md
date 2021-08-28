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
ms.localizationpriority: medium
description: Skype for Business Server 2019 支持多站点和多池部署。 将多个池迁移到 Skype for Business Server 2019 的过程需要考虑以下事项：
ms.openlocfilehash: 514c606b580f0602ebf8ce6b1a41e553445aa4f2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613372"
---
# <a name="migrating-multiple-sites-and-pools"></a>迁移多个站点和池

Skype for Business Server 2019 支持多站点和多池部署。 将多个池迁移到 Skype for Business Server 2019 的过程需要考虑以下事项： 
  
1. 部署 Skype for Business Server 2019 试点池后，需要定义将移动到 Skype for Business Server 2019 池的试点用户的子集，以及用于验证用户功能的方法。 例如，将用户移动到试点池后，验证该用户的会议策略已移动到 Skype for Business Server 2019。 
    
2. 在试点池中部署边缘服务器后，需要验证外部用户能否与 Skype for Business Server 2019 池通信。

3. 持久聊天、SQL 镜像和 XMPP 功能在 Skype for Business Server 2019 中已弃用，不再作为 Skype for Business Server 2019 功能提供，但如果它们以前部署在旧环境中，可以在共存环境中继续运行。 如果要继续使用这些功能，应计划继续采用共存环境，其中某些用户将保留在旧池中。
    
4. 将联盟路由的边缘服务器转换到试点 Skype for Business Server 2019 边缘服务器后，需要验证联盟用户能否与 Skype for Business Server 2019 池通信。
    
5. 移动所有用户和非用户联系人对象后，需要验证旧池是否为空。
    
6. 确认旧池为空后，可以停用该池。 
    
    若要详细了解如何停用旧池和服务器，请参阅阶段 [8：停用旧池](phase-8-decommission-legacy-pools.md)。
    

