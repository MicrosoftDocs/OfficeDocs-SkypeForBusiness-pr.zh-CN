---
title: 在 Skype for Business Server 2015 中部署 E9-1-1
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: 为业务服务器企业语音部署在 Skype 的 E9-1-1。 包括先决条件和部署过程清单。
ms.openlocfilehash: 0994bb3b1c0cd5b4c4ce1dcc1c0a46b4e97b76b1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-emergency-services-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中部署 E9-1-1
 
为业务服务器企业语音部署在 Skype 的 E9-1-1。 包括先决条件和部署过程清单。
  
增强型的 9-1-1 (E9-1-1) 是一项紧急通知功能，将呼叫方的电话号码与市政或街道地址相关联。 使用此信息，公共安全应答点 (PSAP) 可以迅速向需要帮助的呼叫者提供紧急服务。
  
若要支持 E9-1-1，Skype 业务服务器必须能够正确关联与客户端的位置，请确保此信息用于将路由到接近 PSAP 紧急呼叫。
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>E9-1-1 的部署先决条件

在部署 E9-1-1 之前，必须已部署您 Skype 的业务服务器的内部服务器，包括中央管理存储、 前端池或标准版服务器。 您还必须部署一个或多个中介服务器，无论它们是单机或搭配使用前端服务器。 此外，E9-1-1 部署需要指向已认证 E9-1-1 服务提供商的 SIP 中继或指向公用电话交换网 (PSTN) 的紧急位置标识号 (ELIN) 网关。
  
## <a name="deployment-process"></a>部署过程

下表概述了 E9-1-1 部署过程。
  
|**阶段**|**步骤**|**角色**|**部署文档**|
|:-----|:-----|:-----|:-----|
|配置语音用法、路由和中继配置  <br/> |1.创建一个新的 PSTN 使用记录。 这与位置策略中的**PSTN 用法**设置所用的名称相同。 <br/> 2.创建或分配到 PSTN 使用情况记录在上一步中创建的语音路由，然后指向 E9-1-1 的 SIP 中继或 ELIN 网关的网关属性。  <br/> 3.对于 SIP 中继 E9-1-1 的服务提供商，设置处理 E9-1-1 的调用通过 PIDF-LO 数据传递通过**设置 CsTrunkConfiguration EnablePIDFLOSupport** cmdlet 的 SIP 中继。 <br/> 4.另外，SIP 中继 E9-1-1 服务提供商，创建或指派本地 E9-1-1 服务提供者的 SIP 中继由未处理的呼叫 PSTN 路由。 如果与 E9-1-1 服务提供商的连接不可用，将使用此路由。 如果受 E9-1-1 服务提供商支持，则向网关分配一个中继配置规则，以便将 911 拨号字符串转换为国家和/或地区紧急呼叫响应中心 (ECRC) 的外线直拨分机 (DID) 号码。  <br/> |CSVoiceAdmin  <br/> |[在 Skype 的 E9-1-1 语音路由配置的业务服务器 2015](configure-an-e9-1-1-voice-route.md) <br/> |
|创建位置策略，并将其分配给用户和子网  <br/> |1.审查全局位置策略。  <br/> 2.创建位置策略与用户级别范围;或者，如果组织中有多个站点使用不同的用法，紧急，创建位置策略与网络级范围。  <br/> 3.将分配给网络站点的位置策略。  <br/> 4.网络站点中添加适当的子网。  <br/> 5.（可选） 指定对用户策略的位置策略。  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin（创建位置策略除外）  <br/> |[在 Skype 业务服务器 2015年创建位置策略](create-location-policies.md) <br/> [添加到 Skype 的网络站点的位置策略的业务服务器 2015](add-a-location-policy-to-a-network-site.md) <br/> [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|配置位置数据库  <br/> |1.填充数据库与网络到位置的元素的映射。  <br/> 2.对于 ELIN 网关添加到 ELINs\<公司名称\>列。  <br/> 3.验证地址配置到 E9-1-1 的服务提供商的连接。  <br/> 4.验证 E9-1-1 的服务提供商的地址。  <br/> 5.发布已更新的数据库。  <br/> 6.对于 ELIN 网关，将 ELINs 上传到 PSTN 运营商的自动位置标识 （阿里） 数据库。  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[在 Skype 的位置数据库配置的业务服务器 2015](configure-the-location-database.md) <br/> |
|配置高级功能（可选）  <br/> |1.配置 SNMP 应用程序的 URL。  <br/> 2.配置辅助位置信息服务的位置的 URL。  <br/> |CSVoiceAdmin  <br/> |[在 Skype 为业务服务器 2015年配置 SNMP 应用](configure-an-snmp-application.md) <br/> [在 Skype 为业务服务器 2015年配置辅助的位置信息服务](secondary-location-information-service.md) <br/> |
   

