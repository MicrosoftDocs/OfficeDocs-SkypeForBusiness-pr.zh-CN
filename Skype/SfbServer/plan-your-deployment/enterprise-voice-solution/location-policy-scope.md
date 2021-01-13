---
title: 在 Skype for Business Server 中分配位置策略作用域
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
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: 规划 Skype for Business Server 企业语音 中的 E9-1-1 部署的位置企业语音。
ms.openlocfilehash: 586aabe919ea4236dc724446da717b5f300d88e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825522"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>在 Skype for Business Server 中分配位置策略作用域
 
规划 Skype for Business Server 企业语音 中的 E9-1-1 部署的位置企业语音。
  
与其他 Skype for Business Server 策略一样，可在多个范围级别分配位置策略：全局、站点和用户。 但是，用户级别位置策略的范围与其他 Skype for Business Server 策略的行为有点不同。 不仅可以将每用户位置策略应用于终结点对象 (例如用户和公用区域电话联系对象) ，还可以应用于 Skype for Business Server 网络站点。 网络站点是与地理位置关联的客户端子网的分组（但是不一定全部都为整个中央站点或分支站点中的子网）。 任何连接到网络站点子网的客户端都自动拾取分配给该网络站点的位置策略。 如果用户级别的位置策略同时分配给用户和网络站点，则基于网络站点的位置策略将覆盖任何每用户策略设置。
  
每个网络站点都有为其分配的位置策略，而且每个策略都有为其分配的不同 PSTN 用途、通知 URI 和会议 URI 值。
  
> [!NOTE]
> 此特殊策略作用域行为的原因是，当一个位于一个办公室站点的池中的用户访问另一个站点并必须进行紧急呼叫时，无论用户分配到了哪一个池或站点，适用于该网络站点的 E9-1-1 呼叫路由设置都将适用。 
  

