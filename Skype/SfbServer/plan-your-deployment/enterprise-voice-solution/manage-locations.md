---
title: 管理 SIP 中继服务提供商在Skype for Business Server
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
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: 规划使用 SIP 中继提供商的 E9-1-1 部署的位置信息数据库或类似外部数据库所必需的决策Skype for Business Server 企业语音。
ms.openlocfilehash: 4667ea571fe3bbb022c8dd1ee1483e6195165ec9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855289"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a>管理 SIP 中继服务提供商在Skype for Business Server

规划使用 SIP 中继提供商的 E9-1-1 部署的位置信息数据库或类似外部数据库所必需的决策Skype for Business Server 企业语音。

若要配置Skype for Business Server在网络中自动定位客户端，您需要使用网络线路映射填充位置信息服务数据库并发布位置，或链接到已包含正确映射的外部数据库。 作为此过程的一部分，您需要使用 E9-1-1 服务提供商验证位置的市政地址。 有关详细信息，请参阅[部署文档中的 Configure the Location Database。](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database)

You populate the Location Information service database with an Emergency Response Location (ERL) ， which consists of a civic address and the specific address within a building. 位置信息服务 **位置** 字段是建筑物内的特定位置，最大长度为 20 个字符，包括 (空格) 。 在该有限的长度内，请尝试包括以下内容：

- 一个易于理解的、指示 911 呼叫者的位置的名称，以帮助确保紧急响应者到达市政地址后能够迅速找到具体位置。此位置名称可能包括楼号、楼层数、侧楼标识、房间号码等等。应避免使用仅员工知晓的昵称，这样可能导致紧急响应者找错位置。

- 一个位置标识符，可帮助用户轻松查看其Skype for Business客户端选取了正确的位置。 客户端Skype for Business连接，并在其标头中显示发现的 **Location** 和 **City** 字段。 一个好的做法是将建筑物的街道地址添加到每个位置标识符 (例如，"1st \<street number> Floor") 。 如果没有街道地址，那么通用的位置标识符（例如“1st Floor”）可以适用于城市中的所有建筑。

- 如果位置是近似值，因为它由无线访问点确定，您可以添加 **单词 [Near]** (例如，"Near 1st Floor 1234") 。

> [!NOTE]
> 在使用 Skype for Business Server 命令行管理程序命令发布添加到中央位置数据库的位置并复制到池的本地存储之前，这些位置对客户端不可用。 有关详细信息，请参阅部署文档中的[Publishing the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-location-database)。

以下各节讨论填充和维护位置数据库时需要考虑的注意事项。

## <a name="populating-the-location-database"></a>填充位置数据库

以下问题可以帮助您确定如何填充位置数据库。

 **使用什么过程填充位置数据库？**

数据位于何处？采取何种步骤将数据转换为位置数据库所需的格式？是逐个添加位置，还是使用 CSV 文件批量添加？

 **是否具有已包含位置映射的第三方数据库？**

通过使用辅助位置信息服务选项连接到第三方数据库，您可以使用脱机平台对位置进行分组和管理。 此方案的优势在于除了将位置与网络标识符关联外，还可以将位置与用户关联。 这意味着位置信息服务可以将来自辅助位置信息服务的多个地址返回给一个Skype for Business客户端。 然后用户可以选择最合适的位置。

若要与位置信息服务集成，第三方数据库必须遵循 Lync Server 位置请求/响应架构。 有关详细信息，请参阅["[MS-E911WS]： Web Service for E911 Support Protocol Specification"。](/openspecs/office_protocols/ms-e911ws/ab5d7449-2c15-434b-bf65-fdf38b8ffabd) 有关部署辅助位置信息服务的详细信息，请参阅部署文档中Skype for Business Server配置辅助[位置](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md)信息服务。

有关填充位置数据库的详细信息，请参阅部署文档中的 Configure [the Location Database。](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database)

## <a name="maintaining-the-location-database"></a>维护位置数据库

填充位置数据库之后，需要制定更新数据库的策略，因为网络配置发生了改变。以下问题将帮助您确定如何维护位置数据库。

 **如何更新位置数据库？**

有许多方案需要更新位置数据库，包括添加 WAP、重新布置 (导致不同的交换机分配) 和子网扩展。 是直接更新各个位置，还是使用 CSV 文件执行所有位置的批量更新？

 **是否使用 SNMP 应用程序将 Lync 客户端 MAC 地址与端口和交换机标识符进行匹配？**

如果使用 SNMP 应用程序，需要设计用于保持 SNMP 应用程序和位置数据库之间的交换机机架和端口信息一致的手动过程。 如果 SNMP 应用程序返回数据库中不包括的机架 IP 地址或端口 ID，则位置信息服务将无法向客户端返回位置。