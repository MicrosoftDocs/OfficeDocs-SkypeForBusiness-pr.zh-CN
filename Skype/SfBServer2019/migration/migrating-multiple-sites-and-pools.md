---
title: 迁移多个站点和池
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype 的业务服务器 2019年支持多站点和多池部署。 迁移到 Skype for Business Server 2019 的多个池的过程需要考虑以下事项：
ms.openlocfilehash: ecd7e795c7cde9265f26c9c7533fcfd6ec87d684
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26293546"
---
# <a name="migrating-multiple-sites-and-pools"></a>迁移多个站点和池

Skype 的业务服务器 2019年支持多站点和多池部署。 迁移到 Skype for Business Server 2019 的多个池的过程需要考虑以下事项： 
  
1. 部署后的业务服务器 2019年试点池 Skype，您需要定义业务服务器 2019年池，和用于验证用户的功能的方法将被移动到 Skype 的试生产用户的子集。 例如后将用户移动到试点池，, 验证已由用户的会议策略的业务服务器 2019年移动到 Skype。 
    
2. 部署边缘服务器在试点池中后，您需要验证外部用户可以相互业务服务器 2019年池 Skype。

3. 持久聊天、 SQL 镜像，和 XMPP 功能是业务服务器 2019年的 Skype 中已弃用和 Skype 作为业务服务器 2019年功能不再可用，但它们可以继续使用在共存环境中如果先前已部署中旧环境。 如果您想要继续使用这些功能，您应计划继续共存环境其中某些用户将保留在旧池。
    
4. 为业务 Server 2019 边缘服务器切换到试点 Skype 的联盟的路由的边缘服务器后，您需要验证联盟的用户可以相互业务服务器 2019年池 Skype。
    
5. 移动所有用户和非用户联系对象后，您需要验证旧池为空。
    
6. 确认旧池为空后，可以停用该池。 
    
    有关如何停用旧旧池和服务器的详细信息，请参阅[第 8 阶段： 停用旧池](phase-8-decommission-legacy-pools.md)。
    

