---
title: 在任务分配位置策略Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
ms.custom: null
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: 规划 E9-1-1 部署的位置Skype for Business Server 企业语音。
---

# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>在任务分配位置策略Skype for Business Server
 
规划 E9-1-1 部署的位置Skype for Business Server 企业语音。
  
与其他策略Skype for Business Server一样，可在多个范围级别分配位置策略：全局、站点和用户。 但是，用户级别位置策略的范围与其他位置策略的行为Skype for Business Server不同。 不仅可以将每用户位置策略应用于终结点对象 (如用户和公用区域 电话 联系) ，还可以应用于Skype for Business Server网络站点。 网络站点是与地理位置关联的客户端子网的分组（但是不一定全部都为整个中央站点或分支站点中的子网）。 任何连接到网络站点子网的客户端都自动拾取分配给该网络站点的位置策略。 如果同时将用户级别的位置策略分配给用户和网络站点，则基于网络站点的位置策略将覆盖任何每用户策略设置。
  
每个网络站点都有为其分配的位置策略，而且每个策略都有为其分配的不同 PSTN 用途、通知 URI 和会议 URI 值。
  
> [!NOTE]
> 此特殊策略范围行为的原因是，当位于一个办公室站点的池中的用户访问另一个站点并必须进行紧急呼叫时，无论用户分配到什么池或站点，适用于该网络站点的 E9-1-1 呼叫路由设置都将适用。 
  

