---
title: 在 Skype for Business Server 中为用户启用 E9-1-1
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: 部署中的 E9-1-1 部署的位置策略所必需的决策Skype for Business Server 企业语音包括启用哪些用户以及如何支持漫游用户。
ms.openlocfilehash: 61f545018def3268c92729bb52edbbf6e2a5ed29
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765280"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>在 Skype for Business Server 中为用户启用 E9-1-1
 
部署中的 E9-1-1 部署的位置策略所必需的决策Skype for Business Server 企业语音包括启用哪些用户以及如何支持漫游用户。
  
在客户端注册期间，Skype for Business Server使用位置策略为启用 E9-1-1 企业语音配置 E9-1-1 属性。 此策略包含定义 E9-1-1 实现方式的设置。 例如，位置策略包含诸如紧急拨号串以及是否要求用户手动输入位置（如果位置信息服务未自动提供位置）的信息。 有关位置策略的完整定义，请参阅 Plan [location policies for Skype for Business Server](location-policies.md)。
  
Skype for Business Server可以基于子网向客户端分配位置策略，也可以根据全局策略、每站点策略或每用户策略向用户分配位置策略。 为帮助确定启用用户的方式，应首先回答以下问题。
  
 **您计划启用所有用户还是限制为对企业的特定地理区域的支持？**
  
> 可以使用全局位置策略为企业中的所有用户分配位置。 但是，通过将位置策略分配给 Skype for Business Server 网络站点，然后将子网添加到该站点，可以将 E9-1-1 支持限制为企业内的选定位置，并基于每个站点指定 E9-1-1 路由行为。 
    
 **您是否计划通过用户策略启用单个用户？**
  
> 如果要自定义 E9-1-1 支持，您可以直接向特定用户或公共区域电话联系人对象分配位置策略。
    
 **当客户端在网络外漫游或从未定义的子网连接时，是否仍然应该为客户端启用 E9-1-1？**
  
> 如果为用户分配了全局、站点或每用户位置策略，则当客户端不在定义的子网中或位置信息服务未找到位置时，可能需要他们手动在客户端中输入位置。 有关详细信息，请参阅[Define the user experience for manually acquiring a location in Skype for Business Server](manually-acquiring-a-location.md)。
    

