---
title: 定义手动获取业务服务器的 Skype 中的位置的用户体验
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: 规划漫游业务 Server 企业语音的 Skype 中使用 SIP 中继提供商，E9-1-1 部署中的用户。
ms.openlocfilehash: 0b439cc52a5724f5642bd8c61288cededefe754c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20988477"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a>定义手动获取业务服务器的 Skype 中的位置的用户体验
 
规划漫游业务 Server 企业语音的 Skype 中使用 SIP 中继提供商，E9-1-1 部署中的用户。
  
如果某个客户端位于网络外部或未定义的子网中，则用户可手动输入一个位置。但在紧急呼叫期间，呼叫将首先路由到国家/地区 E9-1-1 紧急呼叫响应中心 (ECRC) 调度程序，然后再路由到公共安全应答点 (PSAP)。ECRC 将口头询问呼叫者的位置，然后根据提供的信息将呼叫转接给相应的 PSAP。 
  
**应提示用户输入位置时未自动提供位置信息服务？**
  
例如，如果客户端位于未定义子网中、家中、酒店中或网络外的任何其他地方，是否应要求用户输入位置？
    
可以在位置策略中配置“**所需位置**”设置，从而定义客户端行为。将该值设为“否”表示不会提示用户输入位置。将该值设为“是”表示将提示用户输入位置，但可以消除提示。将该值设为“免责声明”表示将提示用户输入位置，并在用户试图消除提示时显示免责声明。在所有情况下，用户均可以像往常一样继续使用客户端。
    
当用户手动输入位置时，位置映射到客户端的网络的默认网关的 MAC 地址和存储在客户端上位于每个用户表中。 当用户返回到以前存储的任何位置时，业务客户端 Skype 自动将自身设置为该位置。 
  
> [!NOTE]
> 您可以修改仅您的客户端的当前位置，但您也可以删除本地用户表中存储的任何位置。 
  

