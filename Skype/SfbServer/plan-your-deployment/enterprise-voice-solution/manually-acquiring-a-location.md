---
title: 定义在用户位置中手动获取位置的Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: 在 E9-1-1 部署中规划使用 SIP 中继提供商的漫游Skype for Business Server 企业语音。
ms.openlocfilehash: d412c3368dc6f3e302ab8f589aaed1585ea0b233
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855279"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a>定义在用户位置中手动获取位置的Skype for Business Server
 
在 E9-1-1 部署中规划使用 SIP 中继提供商的漫游Skype for Business Server 企业语音。
  
如果某个客户端位于网络外部或未定义的子网中，则用户可手动输入一个位置。但在紧急呼叫期间，呼叫将首先路由到国家/地区 E9-1-1 紧急呼叫响应中心 (ECRC) 调度程序，然后再路由到公共安全应答点 (PSAP)。ECRC 将口头询问呼叫者的位置，然后根据提供的信息将呼叫转接给相应的 PSAP。 
  
**当位置信息服务未自动提供位置时，应提示用户输入位置吗？**
  
例如，如果客户端位于未定义子网中、家中、酒店中或网络外的任何其他地方，是否应要求用户输入位置？
    
可以在位置策略中配置“所需位置”设置，从而定义客户端行为。将该值设为“否”表示不会提示用户输入位置。将该值设为“是”表示将提示用户输入位置，但可以消除提示。将该值设为“免责声明”表示将提示用户输入位置，并在用户试图消除提示时显示免责声明。在所有情况下，用户均可以像往常一样继续使用客户端。
    
当用户手动输入位置时，该位置将映射到客户端网络的默认网关的 MAC 地址，并存储在位于客户端上的每用户表中。 当用户返回到之前存储的任何位置时，Skype for Business客户端会自动将自身设置到该位置。 
  
> [!NOTE]
> 只能修改客户端的当前位置，但也可以删除本地用户表中存储的任何位置。 
  

