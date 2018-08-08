---
title: 为业务服务器部署中 Skype 的紧急服务
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: 为业务 Server 企业语音部署中 Skype E9-1-1。 包括先决条件和部署过程清单。
ms.openlocfilehash: 1ae67f58a4a5afb6eff9ea9eaee2e456469f0e25
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21018961"
---
# <a name="deploy-emergency-services-in-skype-for-business-server"></a>为业务服务器部署中 Skype 的紧急服务
 
为业务 Server 企业语音部署中 Skype E9-1-1。 包括先决条件和部署过程清单。
  
增强型的 9-1-1 (E9-1-1) 是一个紧急通知功能，将呼叫方的电话号码与市政或街道地址相关联。 使用此信息，公共安全应答点 (PSAP) 可以迅速向需要帮助的呼叫者提供紧急服务。
  
若要支持 E9-1-1，Skype 业务服务器必须能够在将某个位置与客户端正确关联，并以确保此信息用于将紧急呼叫路由到最接近的 PSAP。
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>E9-1-1 的部署先决条件

在部署 E9-1-1 之前，必须已部署您的业务服务器的内部服务器，包括中央管理存储、 前端池或 Standard Edition server 的 Skype。 您还必须部署一个或多个中介服务器，或者是独立或与前端服务器并置。 此外，E9-1-1 部署需要指向已认证 E9-1-1 服务提供商的 SIP 中继或指向公用电话交换网 (PSTN) 的紧急位置标识号 (ELIN) 网关。
  
## <a name="deployment-process"></a>部署过程

下表概述了 E9-1-1 部署过程。
  
|**阶段**|**步骤**|**角色**|**部署文档**|
|:-----|:-----|:-----|:-----|
|配置语音用法、路由和中继配置  <br/> |1.创建新的 PSTN 用法记录。 这与位置策略中的**PSTN 用法**设置所用的名称相同。 <br/> 2.创建或分配一个语音路由到上一步骤中创建的 PSTN 用法记录，然后将网关属性指向 E9-1-1 SIP 中继或 ELIN 网关。  <br/> 3.对于 SIP 中继 E9-1-1 服务提供商，设置将处理 E9-1-1 呼叫通过 SIP 使用**Set-cstrunkconfiguration EnablePIDFLOSupport** cmdlet 传递 PIDF-LO 数据的中继。 <br/> 4.（可选） 为 SIP 中继 E9-1-1 服务提供程序创建或分配的 E9-1-1 服务提供商的 SIP 中继不会处理呼叫的本地 PSTN 路由。 如果与 E9-1-1 服务提供商的连接不可用，将使用此路由。 如果受 E9-1-1 服务提供商支持，则向网关分配一个中继配置规则，以便将 911 拨号字符串转换为国家和/或地区紧急呼叫响应中心 (ECRC) 的外线直拨分机 (DID) 号码。  <br/> |CSVoiceAdmin  <br/> |[在 Skype for Business Server 中配置 E9-1-1 语音路由](configure-an-e9-1-1-voice-route.md) <br/> |
|创建位置策略，并将其分配给用户和子网  <br/> |1.查看全局位置策略。  <br/> 2.使用用户级范围; 创建位置策略或者，如果组织具有包含不同紧急情况用法的多个站点，可以使用网络级范围创建位置策略。  <br/> 3.将位置策略分配给网络站点。  <br/> 4.将相应的子网添加到网络站点。  <br/> 5.（可选） 将分配到用户策略的位置策略。  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin（创建位置策略除外）  <br/> |[为 Business Server Skype 创建位置策略](create-location-policies.md) <br/> [业务服务器添加到网络站点中 Skype 位置策略](add-a-location-policy-to-a-network-site.md) <br/> [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|配置位置数据库  <br/> |1.填充的网络元素到位置映射数据库。  <br/> 2.对于 ELIN 网关，将添加到 Elin \<CompanyName\>列。  <br/> 3.配置与 E9-1-1 服务提供商的连接来验证地址。  <br/> 4.验证 E9-1-1 服务提供商的地址。  <br/> 5.发布更新的数据库。  <br/> 6.对于 ELIN 网关，将 Elin 上载到 PSTN 运营商的自动位置识别 (ALI) 数据库。  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[在 Skype for Business Server 中配置位置数据库](configure-the-location-database.md) <br/> |
|配置高级功能（可选）  <br/> |1.配置 SNMP 应用程序的 URL。  <br/> 2.配置辅助位置信息服务的位置的 URL。  <br/> |CSVoiceAdmin  <br/> |[在 Skype for Business Server 中配置 SNMP 应用程序](configure-an-snmp-application.md) <br/> [在 Skype for Business Server 中配置的辅助位置信息服务](secondary-location-information-service.md) <br/> |
   

