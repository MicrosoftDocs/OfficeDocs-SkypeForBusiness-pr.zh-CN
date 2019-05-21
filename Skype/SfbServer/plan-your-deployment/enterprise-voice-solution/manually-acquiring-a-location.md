---
title: 定义在 Skype for Business 服务器中手动获取位置的用户体验
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
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: 在 Skype for Business Server 企业版中使用 SIP 中继提供商在 E9 部署中规划漫游用户。
ms.openlocfilehash: 221c123c9630996d487644d0f5358b95d65fe1a6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276717"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a>定义在 Skype for Business 服务器中手动获取位置的用户体验
 
在 Skype for Business Server 企业版中使用 SIP 中继提供商在 E9 部署中规划漫游用户。
  
如果某个客户端位于网络外部或未定义的子网中，则用户可手动输入一个位置。但在紧急呼叫期间，呼叫将首先路由到国家/地区 E9-1-1 紧急呼叫响应中心 (ECRC) 调度程序，然后再路由到公共安全应答点 (PSAP)。ECRC 将口头询问呼叫者的位置，然后根据提供的信息将呼叫转接给相应的 PSAP。 
  
**如果用户不是位置信息服务自动提供的位置, 是否应提示用户输入一个位置？**
  
例如，如果客户端位于未定义子网中、家中、酒店中或网络外的任何其他地方，是否应要求用户输入位置？
    
可以在位置策略中配置“**所需位置**”设置，从而定义客户端行为。将该值设为“否”表示不会提示用户输入位置。将该值设为“是”表示将提示用户输入位置，但可以消除提示。将该值设为“免责声明”表示将提示用户输入位置，并在用户试图消除提示时显示免责声明。在所有情况下，用户均可以像往常一样继续使用客户端。
    
当用户手动输入位置时, 该位置将映射到客户端网络的默认网关的 MAC 地址, 并存储在客户端上每个用户的表中。 当用户返回到任何以前存储的位置时, Skype for Business 客户端会自动将自己设置到该位置。 
  
> [!NOTE]
> 你只能修改客户端的当前位置, 但也可以删除本地用户的表中存储的任何位置。 
  

