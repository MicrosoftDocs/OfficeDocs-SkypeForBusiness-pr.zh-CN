---
title: 在 Skype for Business 服务器中部署紧急服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: 在 Skype for business Server Enterprise Voice 中部署 E9-1。 包括先决条件和部署过程清单。
ms.openlocfilehash: a96d425f39b53c970047eb220e0ae9f61b515089
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233290"
---
# <a name="deploy-emergency-services-in-skype-for-business-server"></a>在 Skype for Business 服务器中部署紧急服务
 
在 Skype for business Server Enterprise Voice 中部署 E9-1。 包括先决条件和部署过程清单。
  
增强的 9-1-1 (E9-1) 是紧急通知功能, 用于将呼叫方的电话号码与市政或街道地址相关联。 使用此信息，公共安全应答点 (PSAP) 可以迅速向需要帮助的呼叫者提供紧急服务。
  
若要支持 E9-1, Skype for business 服务器必须能够将某个位置与客户端正确关联, 并确保使用此信息将紧急呼叫路由到最近的 PSAP。
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>E9-1-1 的部署先决条件

在部署 E9-1 之前, 您必须已部署了 Skype for Business 服务器内部服务器, 包括中央管理存储、前端池或标准版服务器。 还必须在前端服务器上部署一个或多个中介服务器, 无论是独立还是 collocated。 此外，E9-1-1 部署需要指向已认证 E9-1-1 服务提供商的 SIP 中继或指向公用电话交换网 (PSTN) 的紧急位置标识号 (ELIN) 网关。
  
## <a name="deployment-process"></a>部署过程

下表概述了 E9-1-1 部署过程。
  
|**阶段**|**步骤**|**Roles**|**部署文档**|
|:-----|:-----|:-----|:-----|
|配置语音用法、路由和中继配置  <br/> |1. 创建新的 PSTN 使用记录。 这与位置策略中的**PSTN 用法**设置所用的名称相同。 <br/> 2. 为在上一步中创建的 PSTN 使用记录创建或分配一个语音路由, 然后将网关属性指向 E9 SIP 主干或 ELIN 网关。  <br/> 3. 对于 SIP trunk E9 服务提供商, 请将要处理的 E9 调用的主干设置为使用**new-cstrunkconfiguration-EnablePIDFLOSupport** CMDLET 传递 PIDF-1 的数据。 <br/> 4. (可选) 对于 SIP trunk E9 服务提供商, 为未由 E9 服务提供商的 SIP 主干处理的呼叫创建或分配本地 PSTN 路由。 如果与 E9-1-1 服务提供商的连接不可用，将使用此路由。 如果受 E9-1-1 服务提供商支持，则向网关分配一个中继配置规则，以便将 911 拨号字符串转换为国家和/或地区紧急呼叫响应中心 (ECRC) 的外线直拨分机 (DID) 号码。  <br/> |CSVoiceAdmin  <br/> |[在 Skype for Business 服务器中配置 E9-1 个语音路由](configure-an-e9-1-1-voice-route.md) <br/> |
|创建位置策略，并将其分配给用户和子网  <br/> |1. 查看全局位置策略。  <br/> 2. 使用用户级范围创建位置策略;或者, 如果组织具有多个具有不同的紧急使用情况的网站, 请使用网络级别范围创建一个位置策略。  <br/> 3. 将位置策略分配给网络站点。  <br/> 4. 将相应子网添加到网络站点。  <br/> 5. (可选) 将位置策略分配给用户策略。  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin（创建位置策略除外）  <br/> |[在 Skype for Business 服务器中创建位置策略](create-location-policies.md) <br/> [在 Skype for Business 服务器中将位置策略添加到网络网站](add-a-location-policy-to-a-network-site.md) <br/> [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|配置位置数据库  <br/> |1. 通过将网络元素映射到位置来填充数据库。  <br/> 2. 对于 ELIN 网关, 将 ELINs 添加到\<"\>公司名称" 列。  <br/> 3. 配置与用于验证地址的 E9 服务提供商的连接。  <br/> 4. 通过 E9 服务提供商验证地址。  <br/> 5. 发布更新后的数据库。  <br/> 6. 对于 ELIN 网关, 请将 ELINs 上载到 PSTN 运营商的自动位置标识 (阿里) 数据库。  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[在 Skype for Business 服务器中配置位置数据库](configure-the-location-database.md) <br/> |
|配置高级功能（可选）  <br/> |1. 配置 SNMP 应用程序的 URL。  <br/> 2. 配置辅助位置信息服务位置的 URL。  <br/> |CSVoiceAdmin  <br/> |[在 Skype for Business 服务器中配置 SNMP 应用程序](configure-an-snmp-application.md) <br/> [在 Skype for Business 服务器中配置辅助位置信息服务](secondary-location-information-service.md) <br/> |
   

