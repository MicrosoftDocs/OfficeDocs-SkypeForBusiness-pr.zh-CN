---
title: 管理 ELIN 网关在Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
description: 规划使用 ELIN 网关的 E9-1-1 部署的位置信息数据库或类似外部数据库所必需的决策Skype for Business Server 企业语音。
ms.openlocfilehash: bb0656909866a793bc8d64635b17785020dd646d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596502"
---
# <a name="manage-locations-for-elin-gateways-in-skype-for-business-server"></a>管理 ELIN 网关在Skype for Business Server

规划使用 ELIN 网关的 E9-1-1 部署的位置信息数据库或类似外部数据库所必需的决策Skype for Business Server 企业语音。

若要Skype for Business Server为网络内的客户端提供位置，需要执行以下任务：

- 使用网络线路映射填充位置信息服务数据库，并在 CompanyName (包含紧急) 标识号。

- 发布位置，以供网络中的客户端使用。

- 将 ELIN 上载到公用电话交换网 (PSTN) 运营商的自动位置标识 (ALI) 数据库。

有关如何执行这些任务的详细信息，请参阅部署文档中的[Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database)。

> [!NOTE]
> 添加到中央位置数据库的位置在通过使用 Skype for Business Server 命令行管理程序命令发布并复制到池的本地存储之前，对客户端不可用。 有关详细信息，请参阅部署文档中的[Publishing the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-location-database)。

此部分介绍在您计划更新和维护位置数据库时应考虑的事项。

## <a name="planning-emergency-locations"></a>规划紧急位置

使用 ELIN 网关时，使用市政地址、建筑物内的特定位置以及每个位置至少一个 ELIN 填充位置信息服务数据库。 在规划阶段，最好确定您希望如何命名位置以及如何分配 ELIN。

### <a name="planning-location-names"></a>规划位置名称

位置信息服务 **位置** 字段包含建筑物内的特定位置，最大长度为 20 个字符， (包括) 。 在该限制长度内，尽量包括以下内容：

- 一个容易理解的名称，用于标识 911 呼叫者的位置，以确保紧急响应者在到达市政地址后能迅速找到具体位置。此位置名称可包含建筑物编号、楼层、建筑物标识、房间号等。应避免使用仅对员工可知的昵称，以防紧急响应者去往错误的位置。

- 一个位置标识符，可帮助用户轻松查看其客户端选取了正确的位置。 客户端Skype for Business连接并在其标头中显示发现的 **Location** 和 **City** 字段。 一个好的做法是将建筑物的街道地址添加到每个位置标识符 (例如，"1st <street number> Floor") 。 如果没有街道地址，那么通用的位置标识符（例如“1st Floor”）可以适用于城市中的所有建筑。

- 如果位置是近似值，因为它由无线接入点决定，您可能需要添加 **单词 [Near]** (例如，"Near 1st Floor 1234") 。

### <a name="planning-elins"></a>规划 ELIN

在您决定想要如何将建筑物空间分成多个位置后，需要决定为每个位置分配多少个 ELIN。例如，在多层或多租户建筑物中，可以为建筑物中不同的区域分配不同的紧急区域。通常，建筑物的每层都会被指定为一个位置。每个位置会被分配一个或多个 ELIN，这些 ELIN 用作紧急呼叫时的呼叫号码。请联系您的 PSTN 运营商以获得可用于 ELIN 的电话号码。下表提供了特定街道地址的位置示例。

**位置和 ELIN 分配示例**

|**建筑区域**|**Location**|**ELIN**|
|:-----|:-----|:-----|
|第 1 层  <br/> |1   <br/> |425-555-0100  <br/> |
|第 2 层  <br/> |2   <br/> |425-555-0111  <br/> |
|第 3 层  <br/> |3   <br/> |425-555-0123  <br/> |

您定义的位置应满足以下要求：

- 在每位置最大区域和每街道地址位置数方面符合当地和国家/地区法规。

- 足够详细到能够轻松找到紧急呼叫者。

## <a name="populating-the-location-database"></a>填充位置数据库

以下问题将帮助您确定如何填充位置数据库。

 **使用什么过程填充位置数据库？**

数据位于何处？采取何种步骤将数据转换为位置数据库所需的格式？是逐个添加位置，还是使用 CSV 文件批量添加？

 **是否具有已包含位置映射的第三方数据库？**

通过使用辅助位置信息服务选项连接到第三方数据库，您可以使用脱机平台对位置进行分组和管理。 此方案的优势在于除了将位置与网络标识符关联外，还可以将位置与用户关联。 这意味着位置信息服务可以将来自辅助位置信息服务的多个地址返回给一个Skype for Business客户端。 然后用户可以选择最合适的位置。

若要与位置信息服务集成，第三方数据库必须遵循Skype for Business Server请求/响应架构。 有关详细信息，请参阅[Web Service for E911 Support Protocol。](/openspecs/office_protocols/ms-e911ws/ab5d7449-2c15-434b-bf65-fdf38b8ffabd) 有关部署辅助位置信息服务的详细信息，请参阅部署文档中Skype for Business Server配置辅助[位置](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md)信息服务。

有关填充位置数据库的详细信息，请参阅部署文档中的 Configure [the Location Database。](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database)

## <a name="maintaining-the-location-database"></a>维护位置数据库

填充位置数据库之后，需要制定更新数据库的策略，因为网络配置发生了改变。以下问题将帮助您确定如何维护位置数据库。

 **如何更新位置数据库？**

有许多方案需要更新位置数据，包括添加无线接入点 (WAP)、重新布置办公室缆线（需要不同的交换机分配）和子网扩展。是直接更新每个位置，还是使用 CSV 文件执行所有位置的批量更新？

 **您是否将使用 SNMP 应用程序将客户端 MAC Skype for Business与端口和交换机标识符相匹配？**

如果使用 SNMP 应用程序，需要设计用于保持 SNMP 应用程序和位置数据库之间的交换机机架和端口信息一致的手动过程。 如果 SNMP 应用程序返回数据库中不包括的机架 IP 地址或端口 ID，则位置信息服务将无法向客户端返回位置。