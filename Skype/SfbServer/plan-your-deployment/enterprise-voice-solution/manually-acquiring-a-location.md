---
title: 在 Skype for Business Server 2015 中定义手动获取位置的用户体验
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
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: 漫游用户在使用 Skype 业务服务器企业语音的 SIP 中继提供商、 E9-1-1 部署的规划。
ms.openlocfilehash: 6a22883fb5f028288ab3fab0246d6c2b3b693987
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中定义手动获取位置的用户体验
 
漫游用户在使用 Skype 业务服务器企业语音的 SIP 中继提供商、 E9-1-1 部署的规划。
  
如果某个客户端位于网络外部或未定义的子网中，则用户可手动输入一个位置。但在紧急呼叫期间，呼叫将首先路由到国家/地区 E9-1-1 紧急呼叫响应中心 (ECRC) 调度程序，然后再路由到公共安全应答点 (PSAP)。ECRC 将口头询问呼叫者的位置，然后根据提供的信息将呼叫转接给相应的 PSAP。 
  
**应用户提示一未自动提供位置信息服务时输入的位置吗？**
  
例如，如果客户端位于未定义子网中、家中、酒店中或网络外的任何其他地方，是否应要求用户输入位置？
    
可以在位置策略中配置“**所需位置**”设置，从而定义客户端行为。将该值设为“否”表示不会提示用户输入位置。将该值设为“是”表示将提示用户输入位置，但可以消除提示。将该值设为“免责声明”表示将提示用户输入位置，并在用户试图消除提示时显示免责声明。在所有情况下，用户均可以像往常一样继续使用客户端。
    
当用户手动输入一个位置时，位置映射到客户端的网络的默认网关的 MAC 地址，并存储在客户端上每个用户表。 当用户返回到任何以前存储的位置时，Skype 业务客户端会自动将自身设置为该位置。 
  
> [!NOTE]
> 您可以修改客户端，只有当前的位置，但您也可以删除存储在本地用户的表中的任何位置。 
  

