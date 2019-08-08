---
title: 迁移多个站点和池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype for Business 服务器2019支持多站点和多池部署。 将多个池迁移到 Skype for business 服务器2019的过程需要考虑以下事项:'
ms.openlocfilehash: e2577b6af1430be90e30fff3236d7ea3cf473cd5
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237872"
---
# <a name="migrating-multiple-sites-and-pools"></a>迁移多个站点和池

Skype for Business 服务器2019支持多站点和多池部署。 将多个池迁移到 Skype for business 服务器2019的过程需要考虑以下事项: 
  
1. 部署 Skype for Business Server 2019 试验池后, 你需要定义将被移动到 Skype for business Server 2019 池的试点用户的子集, 以及用于验证用户功能的方法。 例如, 将用户移动到试验池后, 请验证用户的会议策略是否已移动到 Skype for Business Server 2019。 
    
2. 在试验池中部署边缘服务器之后, 你需要验证外部用户是否可以与 Skype for Business Server 2019 池通信。

3. Skype for business Server 2019 中已弃用持续式聊天、SQL 镜像和 XMPP 功能, 并且不再以 Skype for business Server 2019 功能的形式提供, 但它们可以在共存环境中继续使用 (如果它们以前部署在旧版环境。 如果你希望继续使用这些功能, 你应该计划继续使用一个共存环境, 其中某些用户将保留在旧版池中。
    
4. 将联盟路由的边缘服务器转换为试点 Skype for business Server 2019 Edge 服务器之后, 你需要验证联盟用户是否可以与 Skype for business Server 2019 池通信。
    
5. 移动所有用户和非用户联系人对象后, 需要验证旧版池是否为空。
    
6. 验证旧版池是否为空后, 您可以停用该池。 
    
    有关如何停用旧版池和服务器的详细信息, 请参阅[第8阶段: 解除旧版池](phase-8-decommission-legacy-pools.md)。
    

