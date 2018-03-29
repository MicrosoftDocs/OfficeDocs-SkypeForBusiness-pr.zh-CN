---
title: 在 Skype for Business Server 2015 中管理 SIP 中继服务提供商的位置
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/17/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: 所需的规划决策位置信息数据库或类似的外部数据库，使用 Skype 业务服务器企业语音的 SIP 中继提供商、 E9-1-1 部署。
ms.openlocfilehash: e4337a6aaa37a7105b5ab9fbbcc8242237a6954c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中管理 SIP 中继服务提供商的位置
 
所需的规划决策位置信息数据库或类似的外部数据库，使用 Skype 业务服务器企业语音的 SIP 中继提供商、 E9-1-1 部署。
  
若要配置 Skype 业务服务器自动查找网络中的客户端，您需要填充位置信息服务数据库与网络 wiremap，并发布位置，或链接到外部数据库已包含正确的映射。 作为此过程的一部分，您需要通过 E9-1-1 服务提供商来验证这些位置的城市地址。 有关详细信息，请参阅部署文档中的[配置位置数据库](http://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx)。
  
您可使用紧急响应位置 (ERL) 填充位置信息服务数据库，紧急响应位置由城市地址和建筑物内的特定地址构成。 位置信息服务**位置**字段，该字段是在一幢建筑物内的特定位置，最大长度为 20 个字符 （包括空格）。 在该有限长度内，尽量包含以下内容：
  
- 一个易于理解的名称，用于标识 911 呼叫者的位置，以帮助确保紧急响应者在到达该城市地址后迅速找到特定位置。此位置名称可能包括建筑物编号、楼层、建筑物标识、房间号等。应避免使用仅对员工可知的昵称，否则可能导致紧急响应者去往错误的位置。
    
- 帮助他们 Skype 业务客户提货的正确位置的用户可以很容易地看到，一个位置标识符。 Skype 业务客户端自动连接，并显示其标头中发现的**位置**和**城市**字段。 一个好的做法是将建筑物的街道地址添加到每个位置标识符 (例如，"一层<street number>")。 如果没有街道地址，可能对城市中的任何建筑物都应用常规位置标识符，如“1st Floor”。
    
- 如果位置是近似的因为它由一个无线访问点，则可以添加**[附近]** （例如，"在附近一层 1234年"） 一词。
    
> [!NOTE]
> 直到它们通过 Skype 业务服务器管理外壳程序命令发布到该池的本地存储被复制，而无法供客户端添加到中心位置数据库的位置。 有关详细信息，请参阅部署文档中的[发布位置数据库](http://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx)。
  
以下各节讨论填充和维护位置数据库时需要考虑的注意事项。
  
## <a name="populating-the-location-database"></a>填充位置数据库

以下问题可帮助您确定如何填充位置数据库。
  
 **使用什么过程填充位置数据库？**
  
数据位于何处？需要采取何种步骤将数据转换为位置数据库所需的格式？是逐个添加位置，还是使用 CSV 文件批量添加？ 
  
 **是否有已包含位置映射的第三方数据库？**
  
通过使用辅助位置信息服务选项以连接到第三方数据库，可以分组和管理使用脱机平台的位置。 除了将位置与网络标识符关联外，此方法的优点还在于将位置与用户关联。 这意味着位置信息服务可以返回多个地址，源自辅助位置信息服务，向业务客户端的 Skype。 然后，用户可以选择最适合的位置。 
  
要将位置信息服务相结合，第三方数据库必须按照 Lync 服务器位置请求/响应模式。 有关详细信息，请参阅["[MS E911WS]: E911 支持协议规范的 Web 服务"](https://go.microsoft.com/fwlink/p/?linkid=213819)。 有关部署辅助位置信息服务的详细信息，请参阅部署文档中的[配置中业务服务器 2015年的 Skype 的辅助位置信息服务](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md)。
  
有关填充位置数据库的详细信息，请参阅部署文档中的[配置位置数据库](http://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx)。
  
## <a name="maintaining-the-location-database"></a>维护位置数据库

填充位置数据库之后，需要制定更新数据库的策略，因为网络配置发生了改变。以下问题将帮助您确定如何维护位置数据库。
  
 **如何更新位置数据库？**
  
有许多情形需要更新位置数据库，包括添加 WAP、重新布置办公室缆线（需要不同的交换机分配）和子网扩展。是直接更新每个位置，还是使用 CSV 文件执行所有位置的批量更新？
  
 **是否使用 SNMP 应用程序将 Lync 客户端 MAC 地址与端口和交换机标识符匹配？**
  
如果使用 SNMP 应用程序，需要设计用于保持 SNMP 应用程序和位置数据库之间的交换机机架和端口信息一致的手动过程。 如果 SNMP 应用程序返回不包含数据库中的机箱 IP 地址或端口 ID，位置信息服务将不能返回到客户端的位置。
  

