---
title: 在 Skype for business 服务器中启用 E9-1-1 的用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: 适用于 Skype for Business Server Enterprise Voice 中的 E9 部署的位置策略所需的决策, 包括要启用哪些用户以及如何支持漫游用户。
ms.openlocfilehash: 1e714e5296e8176c9052b50a5d4ce4f2c0d6184b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276899"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>在 Skype for business 服务器中启用 E9-1-1 的用户
 
适用于 Skype for Business Server Enterprise Voice 中的 E9 部署的位置策略所需的决策, 包括要启用哪些用户以及如何支持漫游用户。
  
在客户端注册期间, Skype for Business 服务器使用一个位置策略来配置支持企业语音的用户的 E9 属性。 此策略包含定义 E9-1-1 实现方式的设置。 例如, 位置策略包含 "紧急拨号" 字符串之类的信息, 以及是否需要用户手动输入一个位置 (如果位置信息服务不会自动提供)。 有关位置策略的完整定义, 请参阅为[Skype For Business 服务器计划位置策略](location-policies.md)。
  
Skype for Business 服务器可以基于子网将位置策略分配给客户, 也可以基于全局、每个站点或每用户策略为用户分配位置策略。 为帮助确定启用用户的方式，应首先回答以下问题。
  
 **你计划启用所有用户还是限制为对企业的特定地理区域的支持？**
  
> 可以使用全局位置策略为企业中的所有用户分配位置。 但是, 通过将位置策略分配给 Skype for business 服务器网络网站, 然后将子网添加到该网站, 你可以将 E9 支持限制到企业内选定的位置, 并以每个站点为基础指定 E9 路由行为。 
    
 **你是否计划通过用户策略启用单个用户？**
  
> 如果要自定义 E9-1-1 支持，您可以直接向特定用户或公共区域电话联系人对象分配位置策略。
    
 **当客户端在网络外漫游或从未定义的子网连接时，是否仍然应该为客户端启用 E9-1-1？**
  
> 如果为用户分配了全局、网站或每用户位置策略, 则可以在客户端不在定义的子网中或未找到位置信息服务的位置时, 将其手动输入到客户端的位置。 有关详细信息, 请参阅[定义在 Skype For Business 服务器中手动获取位置的用户体验](manually-acquiring-a-location.md)。
    

