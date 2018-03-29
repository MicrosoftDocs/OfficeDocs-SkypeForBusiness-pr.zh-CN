---
title: 在 Skype for Business Server 2015 中为用户启用 E9-1-1
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: 业务企业语音，包括哪些用户能够以及如何支持漫游用户所需的 Skype 在 E9-1-1 部署的位置策略的决策。
ms.openlocfilehash: 966344f2cfc7a964c9dda0898b4ba99c42e03193
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中为用户启用 E9-1-1
 
业务企业语音，包括哪些用户能够以及如何支持漫游用户所需的 Skype 在 E9-1-1 部署的位置策略的决策。
  
在客户注册过程 Skype 业务服务器使用位置策略来配置企业语音启用用户 E9-1-1 的属性。 此策略包含定义 E9-1-1 实现方式的设置。 例如，位置策略包含的信息，如，紧急拨号字符串，以及要求用户手动输入的位置，如果该位置信息服务不会自动提供一个。 位置策略的完整定义，请参阅[规划业务服务器 2015年的 Skype 的位置策略](location-policies.md)。
  
Skype 业务服务器可以将位置策略分配给客户端的子网，或根据全局用户每个站点或每用户策略。 为帮助确定启用用户的方式，应首先回答以下问题。
  
 **你计划启用所有用户还是限制为对企业的特定地理区域的支持？**
  
> 可以使用全局位置策略为企业中的所有用户分配位置。 但是，为 Skype 业务服务器网络站点分配位置策略，然后将子网添加到站点，可以限制 E9-1-1 支持添加到所选位置在企业内部，并在每个站点的基础上指定 E9-1-1 的路由行为。 
    
 **你是否计划通过用户策略启用单个用户？**
  
> 如果要自定义 E9-1-1 支持，您可以直接向特定用户或公共区域电话联系人对象分配位置策略。
    
 **当客户端在网络外漫游或从未定义的子网连接时，是否仍然应该为客户端启用 E9-1-1？**
  
> 如果用户指定全局或本地，站点，或每用户位置策略，可能需要手动为客户端输入的位置，如果客户端不在定义的子网中的位置或已没有位置找到位置信息服务。 有关详细信息，请参阅[定义手动获取业务服务器 2015年的 Skype 在一个位置的用户体验](manually-acquiring-a-location.md)。
    

