---
title: 为业务服务器分配位置策略作用域中 Skype
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
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: 规划业务 Server 企业语音中 Skype E9-1-1 部署的位置策略。
ms.openlocfilehash: 28759d88be1586149b0dd482d934c5bbc89a1853
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881880"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>为业务服务器分配位置策略作用域中 Skype
 
规划业务 Server 企业语音中 Skype E9-1-1 部署的位置策略。
  
为多个范围级别可以与其他 Skype Business Server 策略，分配位置策略： 全局、 站点和用户。 但是，用户级位置策略的作用域的行为不同于与其他 Skype Business Server 策略一位。 不仅可以每用户位置策略应用于 （如用户和公用区域电话联系对象） 的终结点对象，它们也可以应用到 Skype for Business Server 网络站点。 网络站点是地理位置关联的客户端子网的分组（但可能不需要所有子网位于一个中央站点或分支站点）。 连接到一个网络站点的子网的所有客户端将自动挑选分配给该网络站点的位置策略。 在将用户级别的位置策略分配给一个用户和一个网络站点的情况下，基于网络站点的位置策略将覆盖每用户策略设置。
  
每个网络站点均分配有一个位置策略，并且每个策略均分配有不同的 PSTN 用法、通知 URI 和会议 URI 值。
  
> [!NOTE]
> 此特定策略作用域行为的原因是当驻留在 office 网站的池中的用户访问另一个站点并发出紧急呼叫时，无论该用户分配到的池或站点如何，都将应用与该网络站点对应的 E9-1-1 呼叫路由设置。 
  

