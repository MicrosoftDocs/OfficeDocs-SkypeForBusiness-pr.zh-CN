---
title: 在 Skype for Business 服务器中分配位置策略范围
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: 为 Skype for Business Server Enterprise Voice 中的 E9 部署规划位置策略。
ms.openlocfilehash: 3865db146676ed64da9422d2a8731e44451ec6ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802752"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>在 Skype for Business 服务器中分配位置策略范围
 
为 Skype for Business Server Enterprise Voice 中的 E9 部署规划位置策略。
  
与其他 Skype for Business 服务器策略一样，位置策略可以在多个作用域级别分配：全局、网站和用户。 但是，用户级位置策略的作用与其他 Skype for Business 服务器策略的行为略有不同。 每个用户的位置策略不仅可以应用于终结点对象（如用户和常用的区域电话联系人对象），也可以应用于 Skype for business 服务器网络网站。 网络站点是地理位置关联的客户端子网的分组（但可能不需要所有子网位于一个中央站点或分支站点）。 连接到一个网络站点的子网的所有客户端将自动挑选分配给该网络站点的位置策略。 在将用户级别的位置策略分配给一个用户和一个网络站点的情况下，基于网络站点的位置策略将覆盖每用户策略设置。
  
每个网络站点均分配有一个位置策略，并且每个策略均分配有不同的 PSTN 用法、通知 URI 和会议 URI 值。
  
> [!NOTE]
> 此特定策略作用域行为的原因是当驻留在 office 网站的池中的用户访问另一个站点并发出紧急呼叫时，无论该用户分配到的池或站点如何，都将应用与该网络站点对应的 E9-1-1 呼叫路由设置。 
  

