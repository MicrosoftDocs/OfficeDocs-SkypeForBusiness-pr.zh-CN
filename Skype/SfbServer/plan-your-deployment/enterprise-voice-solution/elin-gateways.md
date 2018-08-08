---
title: 管理 ELIN 网关 Skype 中的业务服务器的位置
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
ms.assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
description: 所必需的规划决策位置信息数据库或类似的外部数据库中，E9-1-1 部署中的业务 Server 企业语音的 Skype 使用 ELIN 网关。
ms.openlocfilehash: ace81abc47ac401db48b7a34fe9a229a29f18881
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20974233"
---
# <a name="manage-locations-for-elin-gateways-in-skype-for-business-server"></a>管理 ELIN 网关 Skype 中的业务服务器的位置
 
所必需的规划决策位置信息数据库或类似的外部数据库中，E9-1-1 部署中的业务 Server 企业语音的 Skype 使用 ELIN 网关。
  
要让 Skype 业务服务器自动提供网络内的客户端的位置，您需要执行以下任务： 
  
- 填充用网络线路图，位置信息服务数据库并在 CompanyName 字段中包括紧急位置标识号 (Elin)。
    
- 发布位置，以供网络中的客户端使用。
    
- 将 ELIN 上载到公用电话交换网 (PSTN) 运营商的自动位置标识 (ALI) 数据库。
    
有关如何执行这些任务的详细信息，请参阅部署文档中的[Configure the Location Database](http://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) 。
  
> [!NOTE]
> 已发布业务 Server 命令行管理程序命令使用 Skype 和复制到该池的本地存储之前，位置添加到中心位置数据库不可用到客户端。 有关详细信息，请参阅部署文档中的[发布位置数据库](http://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx)。
  
本节介绍在计划更新和维护位置数据库时要考虑的事项。
  
## <a name="planning-emergency-locations"></a>规划紧急位置

使用 ELIN 网关时，您将填充的市政地址、 大厦内的特定位置与每个位置的至少一个 ELIN 位置信息服务数据库。 在规划阶段，最好决定想要如何命名位置和分配 ELIN。
  
### <a name="planning-location-names"></a>规划位置名称

保留大厦内的特定位置，该位置信息服务**位置**字段为最大长度为 20 个字符 （包括空格）。 在该限制长度内，尽量包括以下内容：
  
- 一个容易理解的名称，用于标识 911 呼叫者的位置，以确保紧急响应者在到达市政地址后能迅速找到具体位置。此位置名称可包含建筑物编号、楼层、建筑物标识、房间号等。应避免使用仅对员工可知的昵称，以防紧急响应者去往错误的位置。
    
- 一个位置标识符，帮助用户轻松判断其客户端已选择正确位置。 Skype 业务客户端自动连接和标头中显示发现的**位置**和**市/县**字段。 较好的做法是将构建的街道地址添加到每个位置标识符 (例如，"1st Floor <street number>")。 如果没有街道地址，可能对城市中的任何建筑物都应用常规位置标识符，如“1st Floor”。
    
- 如果位置是一个大概，因为它由无线访问点决定，您可能想要添加词 **[附近]** (例如，"Near 1st Floor 1234")。
    
### <a name="planning-elins"></a>规划 ELIN

在您决定想要如何将建筑物空间分成多个位置后，需要决定为每个位置分配多少个 ELIN。例如，在多层或多租户建筑物中，可以为建筑物中不同的区域分配不同的紧急区域。通常，建筑物的每层都会被指定为一个位置。每个位置会被分配一个或多个 ELIN，这些 ELIN 用作紧急呼叫时的呼叫号码。请联系您的 PSTN 运营商以获得可用于 ELIN 的电话号码。下表提供了特定街道地址的位置示例。
  
**位置和 ELIN 分配示例**

|**建筑物区域**|**位置**|**ELIN**|
|:-----|:-----|:-----|
|第一层  <br/> |1  <br/> |425-555-0100  <br/> |
|第二层  <br/> |2  <br/> |425-555-0111  <br/> |
|第三层  <br/> |3  <br/> |425-555-0123  <br/> |
   
您定义的位置应满足以下要求：
  
- 在每位置最大区域和每街道地址位置数方面符合当地和国家/地区法规。
    
- 足够详细到能够轻松找到紧急呼叫者。
    
## <a name="populating-the-location-database"></a>填充位置数据库

以下问题将帮助您确定如何填充位置数据库。
  
 **使用什么过程填充位置数据库？**
  
数据位于何处？需要采取何种步骤将数据转换为位置数据库所需的格式？是逐个添加位置，还是使用 CSV 文件批量添加？
  
 **是否有已包含位置映射的第三方数据库？**
  
通过使用辅助位置信息服务选项来连接到第三方数据库，您可以组和管理使用脱机平台的位置。 除了将位置与网络标识符关联外，此方法的优点还在于将位置与用户关联。 这意味着位置信息服务，可返回多个地址，来自业务客户端 Skype 到辅助位置信息服务。 然后，用户可以选择最适合的位置。 
  
若要将位置信息服务与相集成，第三方数据库必须执行业务服务器位置请求/响应架构 Skype。 有关详细信息，请参阅[E911 支持协议的 Web 服务](https://go.microsoft.com/fwlink/p/?linkid=213819)。 有关部署辅助位置信息服务的详细信息，请参阅部署文档中的[Configure Skype 业务服务器中的辅助位置信息服务](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md)。
  
有关填充位置数据库的详细信息，请参阅部署文档中的[Configure the Location Database](http://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) 。
  
## <a name="maintaining-the-location-database"></a>维护位置数据库

填充位置数据库之后，需要制定更新数据库的策略，因为网络配置发生了改变。以下问题将帮助您确定如何维护位置数据库。
  
 **如何更新位置数据库？**
  
有许多方案需要更新位置数据，包括添加无线接入点 (WAP)、重新布置办公室缆线（需要不同的交换机分配）和子网扩展。是直接更新每个位置，还是使用 CSV 文件执行所有位置的批量更新？
  
 **是否使用 SNMP 应用程序以匹配 Skype 业务客户端 MAC 地址与端口和交换机标识符？**
  
如果使用 SNMP 应用程序，需要设计用于保持 SNMP 应用程序和位置数据库之间的交换机机架和端口信息一致的手动过程。 如果 SNMP 应用程序返回数据库中不包含机箱 IP 地址或端口 ID，位置信息服务不能以返回到客户端的位置。
  

