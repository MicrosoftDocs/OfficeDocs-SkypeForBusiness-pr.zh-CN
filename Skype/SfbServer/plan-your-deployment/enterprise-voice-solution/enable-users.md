---
title: 为用户启用 E9-1-1 在 Skype 业务服务器
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: 业务 Server 企业语音，包括启用的用户以及如何支持漫游用户的位置策略中 Skype E9-1-1 部署所需的决策。
ms.openlocfilehash: 57a84d18bec0547f1179e62013c9b957afdd2c53
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879305"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>为用户启用 E9-1-1 在 Skype 业务服务器
 
业务 Server 企业语音，包括启用的用户以及如何支持漫游用户的位置策略中 Skype E9-1-1 部署所需的决策。
  
在客户端注册过程 Skype 业务服务器使用位置策略配置 E9-1-1 属性已启用企业语音的用户。 此策略包含定义 E9-1-1 实现方式的设置。 例如，位置策略包含信息，如，紧急拨号字符串，以及要求用户手动输入位置，如果位置信息服务不会自动提供一个。 位置策略的完整定义，请参阅[Plan for Business Server Skype 的位置策略](location-policies.md)。
  
Skype 业务服务器到客户端的子网，或根据全局，用户可以分配位置策略的站点或每用户策略。 为帮助确定启用用户的方式，应首先回答以下问题。
  
 **你计划启用所有用户还是限制为对企业的特定地理区域的支持？**
  
> 可以使用全局位置策略为企业中的所有用户分配位置。 但是，通过向 Skype Business Server 网络站点分配位置策略，然后将子网添加到网站，您可以限制对所选位置将在企业内部的 E9-1-1 支持和单独对每个网站指定 E9-1-1 路由行为。 
    
 **你是否计划通过用户策略启用单个用户？**
  
> 如果要自定义 E9-1-1 支持，您可以直接向特定用户或公共区域电话联系人对象分配位置策略。
    
 **当客户端在网络外漫游或从未定义的子网连接时，是否仍然应该为客户端启用 E9-1-1？**
  
> 如果用户分配全局，网站，每用户位置策略，也可以是管理需要手动到客户端输入的位置，如果客户端不是位于定义的子网，或者没有位置已找到由位置信息服务。 有关详细信息，请参阅[定义手动获取 Skype 业务服务器中的位置的用户体验](manually-acquiring-a-location.md)。
    

