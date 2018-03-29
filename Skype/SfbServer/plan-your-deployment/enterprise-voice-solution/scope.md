---
title: 在 Skype for Business Server 2015 中定义 E9-1-1 部署的范围
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
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: 规划业务服务器企业语音在 Skype E9-1-1 部署所需的决策。
ms.openlocfilehash: f81a2c56642557bf92a965de025aecbdbcadadcd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中定义 E9-1-1 部署的范围
 
规划业务服务器企业语音在 Skype E9-1-1 部署所需的决策。
  
在 E9-1-1 的配置 Skype 业务之前，您需要规划部署 E9-1-1。 要考虑的一些问题包括：
  
 **您的组织策略和 E9-1-1 的法律义务是什么？**
  
 E9-1-1 针对 PBX（在 E9-1-1 用语中，称为多路电话系统或 MLTS）的法律要求因州/省而异。 您应咨询法律团队了解适用于您的部署的业务相关的地区的 Skype 的义务。
    
 **需要在企业内部的哪些区域启用 E9-1-1？**
  
 可以为整个企业或选定位置启用 E9-1-1。例如，您可能对位于不同州/省的机构有不同的 E9-1-1 要求，您也可能要排除美国之外的站点。 
    
 **如何为分支站点部署 E9-1-1？**
  
 语音复原是在分支站点部署 E9-1-1 时需要理解的一个重要概念。 如果您已集中了 E-9-1-1 的 SIP 中继和 WAN 故障发生，登录的客户端可能无法获取位置信息服务中的位置或连接到紧急服务的服务提供商。 Skype 业务提供几种策略，用于处理语音留存能力在分支机构，其中包括： 具有弹性数据网络、 部署在每个分支中，SIP 中继或推出紧急电话本地网关在停机期间。 有关详细信息，请参阅[规划分支站点语音留存能力](http://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx)。
    
 **是否为在网络外部工作的用户启用 E9-1-1？**
  
 自动位置收购是仅用于客户端位于组织网络，使您的组织需要决定它是否将支持 E9-1-1 电话 Skype 业务时关闭部署的客户端。 例如，如果用户在家里或客户站点中工作，您是否允许这些用户进行紧急呼叫？ 如果客户端位于企业网络外部，则可将客户端配置为提示用户输入位置。 但由于无法根据主街道地址指南 (MSAG) 预先验证这些用户提供的位置，因此，紧急服务的服务提供商调度程序将需要在将呼叫路由至公共安全应答点 (PSAP) 之前向呼叫者口头确认该位置的有效性。
    
> [!NOTE]
> 业务客户端的用户通过 VPN 连接到组织网络的 Skype 可领取内部 IP 地址信息，但由于不能使用这些地址来标识用户的实际位置，是非常重要的排除 VPN 网从位置信息服务。 
  
 **是否向美国之外的站点提供紧急呼叫路由？**
  
 您可能需要为贵公司所在的、紧急服务的服务提供商不提供服务的一些区域（例如，国际位置）提供紧急路由。为此，请创建新的站点，然后为涉及 PSTN 用法（可通过本地 PSTN 网关路由呼叫）的站点分配语音策略。
    

