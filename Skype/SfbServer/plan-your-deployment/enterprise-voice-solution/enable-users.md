---
title: 在 Skype for Business Server 中为用户启用 E9-1-1
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: 针对 Skype for Business Server 企业语音 中 E9-1-1 部署的位置策略所需的决策，包括启用哪些用户以及如何支持漫游用户。
ms.openlocfilehash: 9a2ced694357b9225555a05c10e93a1006a771b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825742"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>在 Skype for Business Server 中为用户启用 E9-1-1
 
针对 Skype for Business Server 企业语音 中 E9-1-1 部署的位置策略所需的决策，包括启用哪些用户以及如何支持漫游用户。
  
在客户端注册期间，Skype for Business Server 使用位置策略为启用企业语音 E9-1-1 属性。 此策略包含定义 E9-1-1 实现方式的设置。 例如，位置策略包含紧急拨号字符串等信息，以及如果位置信息服务未自动提供位置，是否需要用户手动输入位置。 有关位置策略的完整定义，请参阅 [规划 Skype for Business Server 的位置策略](location-policies.md)。
  
Skype for Business Server 可以基于子网将位置策略分配给客户端，也可以根据全局、每站点或每用户策略为用户分配位置策略。 为帮助确定启用用户的方式，应首先回答以下问题。
  
 **您计划启用所有用户还是限制为对企业的特定地理区域的支持？**
  
> 可以使用全局位置策略为企业中的所有用户分配位置。 但是，通过将位置策略分配给 Skype for Business Server 网络站点，然后将子网添加到该站点，可以将 E9-1-1 支持限制为企业内的选定位置，并基于每个站点指定 E9-1-1 路由行为。 
    
 **您是否计划通过用户策略启用单个用户？**
  
> 如果要自定义 E9-1-1 支持，您可以直接向特定用户或公共区域电话联系人对象分配位置策略。
    
 **当客户端在网络外漫游或从未定义的子网连接时，是否仍然应该为客户端启用 E9-1-1？**
  
> 如果为用户分配了全局、站点或每用户位置策略，则当客户端不在定义的子网中或位置信息服务未找到位置时，可能需要他们手动在客户端中输入位置。 有关详细信息，请参阅 [定义在 Skype for Business Server](manually-acquiring-a-location.md)中手动获取位置的用户体验。
    

