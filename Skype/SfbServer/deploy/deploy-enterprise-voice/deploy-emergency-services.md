---
title: 在 Skype for Business Server 中部署紧急服务
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: 在 Skype for Business Server 企业语音 中部署 E9-1-1。 包括先决条件和部署过程清单。
ms.openlocfilehash: 8aed5b6462ecf9d5d9fecfb0ffdc5573ca4f2352
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812522"
---
# <a name="deploy-emergency-services-in-skype-for-business-server"></a>在 Skype for Business Server 中部署紧急服务
 
在 Skype for Business Server 企业语音 中部署 E9-1-1。 包括先决条件和部署过程清单。
  
增强型 9-1-1 (E9-1-1) 是一项紧急通知功能，将呼叫者的电话号码与市政地址或街道地址关联。 使用此信息，公共安全应答点 (PSAP) 可以迅速向需要帮助的呼叫者提供紧急服务。
  
为了支持 E9-1-1，Skype for Business Server 必须能够正确地将位置与客户端关联，并确保此信息用于将紧急呼叫路由到最近的 PSAP。
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>E9-1-1 的部署先决条件

在部署 E9-1-1 之前，必须已部署 Skype for Business Server 内部服务器，包括中央管理存储、前端池或 Standard Edition 服务器。 还必须部署一台或多台中介服务器（独立服务器或与前端服务器并排）。 此外，E9-1-1 部署需要指向已认证 E9-1-1 服务提供商的 SIP 中继或指向公用电话交换网 (PSTN) 的紧急位置标识号 (ELIN) 网关。
  
## <a name="deployment-process"></a>部署过程

下表概述了 E9-1-1 部署过程。
  
|**阶段**|**步骤**|**Roles**|**部署文档**|
|:-----|:-----|:-----|:-----|
|配置语音用法、路由和中继配置  <br/> |1. 创建新的 PSTN 用法记录。 这与位置策略中的“PSTN 用法”设置所用的名称相同。 <br/> 2. 创建语音路由或将语音路由分配给在上一步中创建的 PSTN 用法记录，然后将网关属性指向 E9-1-1 SIP 中继或 ELIN 网关。  <br/> 3. 对于 SIP 中继 E9-1-1 服务提供商，设置通过 SIP 处理 E9-1-1 呼叫的中继，以使用 **Set-CsTrunkConfiguration -EnablePIDFLOSupport** cmdlet 传递 PIDF-LO 数据。 <br/> 4. 或者，对于 SIP 中继 E9-1-1 服务提供商，为 E9-1-1 服务提供商的 SIP 中继未处理的呼叫创建或分配本地 PSTN 路由。 如果与 E9-1-1 服务提供商的连接不可用，将使用此路由。 如果受 E9-1-1 服务提供商支持，则向网关分配一个中继配置规则，以便将 911 拨号字符串转换为国家和/或地区紧急呼叫响应中心 (ECRC) 的外线直拨分机 (DID) 号码。  <br/> |CSVoiceAdmin  <br/> |[在 Skype for Business Server 中配置 E9-1-1 语音路由](configure-an-e9-1-1-voice-route.md) <br/> |
|创建位置策略，并将其分配给用户和子网  <br/> |1. 查看全局位置策略。  <br/> 2. 创建具有用户级别范围的位置策略;或者，如果组织具有多个具有不同的紧急用法的站点，则创建具有网络级别范围的位置策略。  <br/> 3. 将位置策略分配给网络站点。  <br/> 4. 将相应的子网添加到网络站点。  <br/> 5. (可选) 将位置策略分配给用户策略。  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin（创建位置策略除外）  <br/> |[在 Skype for Business Server 中创建位置策略](create-location-policies.md) <br/> [在 Skype for Business Server 中向网络站点添加位置策略](add-a-location-policy-to-a-network-site.md) <br/> [将子网与网络站点关联](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|配置位置数据库  <br/> |1. 使用网络元素到位置的映射填充数据库。  <br/> 2. 对于 ELIN 网关，将 ELIN 添加到 \<CompanyName\> 列。  <br/> 3. 配置与 E9-1-1 服务提供商的连接以验证地址。  <br/> 4. 使用 E9-1-1 服务提供商验证地址。  <br/> 5. 发布更新的数据库。  <br/> 6. 对于 ELIN 网关，将 ELIN 上载到 PSTN 运营商的自动位置标识 (ALI) 数据库中。  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[在 Skype for Business Server 中配置位置数据库](configure-the-location-database.md) <br/> |
|配置高级功能（可选）  <br/> |1. 配置 SNMP 应用程序的 URL。  <br/> 2. 配置辅助位置信息服务位置的 URL。  <br/> |CSVoiceAdmin  <br/> |[在 Skype for Business Server 中配置 SNMP 应用程序](configure-an-snmp-application.md) <br/> [在 Skype for Business Server 中配置辅助位置信息服务](secondary-location-information-service.md) <br/> |
   

