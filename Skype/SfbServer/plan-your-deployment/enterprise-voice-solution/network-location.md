---
title: 定义用于确定业务服务器中 Skype 位置的网络元素
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
description: 将用于将呼叫者映射到 E9-1-1 部署中 Skype 业务 Server 企业语音的位置的决策所必需的规划的网络组件。
ms.openlocfilehash: 1a454c8391f67a1a20d50896bb79c47466f417f2
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882073"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a>定义用于确定业务服务器中 Skype 位置的网络元素
 
将用于将呼叫者映射到 E9-1-1 部署中 Skype 业务 Server 企业语音的位置的决策所必需的规划的网络组件。
  
如果要设置业务服务器基础结构支持自动客户端位置检测您 Skype，首先需要决定哪些网络元素您打算用于将呼叫者映射到的位置。 在业务服务器 Skype，可以将以下层 2 和第 3 层网络元素与位置相关联：
  
- 无线访问点 (WAP) 基本服务集标识 (BSSID) 地址（第 2 层）
    
- LLDP 交换机端口（第 2 层）
    
- LLDP 交换机机架 ID（第 2 层）
    
- IP 子网（第 3 层）
    
- 客户端 MAC 地址（第 2 层）
    
以上网络元素是按优先顺序列出的。 如果客户端可以通过使用多个网络元素位于，Skype 业务服务器使用优先级的顺序确定要使用的机制。 
  
以下几节提供有关使用每个网络元素的更多详细信息。
  
> [!IMPORTANT]
> 使用网络元素到位置映射呼叫者，时，最重要的您保持最新的位置信息服务数据库。 例如，如果添加或更改网络元素（例如，添加 WAP），您必须删除旧条目并在位置数据库中添加新条目。 
  
## <a name="wireless-access-point"></a>无线访问点

当客户端以无线方式连接到网络时，位置请求使用 WAP 的 BSSID 地址来确定位置。 如果客户端漫游，指示 WAP 可能不到最近的一个，甚至可以拿起上构建的不同基底的 WAP。 若要指示位置是一个大概，可以附加 **[附近]** 或 **[关闭以]** 描述符与位置值。
  
此位置方法假定每个 WAP 的 BSSID 都是静态的。 但是，如果您 WAP 供应商，使用动态分配 BSSIDs，获取从 WAP BSSID 可能发生更改 （这会发生以下 WAP 配置更改），并且无法在不接收位置的情况下左无线客户端。 若要防止这种可能性，您需要填充所有可能的 BSSID 地址由每个 WAP 与 Erl 的位置信息服务数据库。 
  
## <a name="lldp-ports-and-switches"></a>LLDP 端口和交换机

支持 Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) 的托管以太网交换机可向与 LLDP-MED 兼容的客户端播发其身份和端口信息，然后可向位置数据库查询该信息，以提供设备的位置。可以只在交换机机架 ID 上关联 ERL，或将其向下映射到端口级别。
  
> [!NOTE]
> Skype 业务服务器支持使用 LLDP-MED 用于确定 Windows 8 上运行的业务客户端的 Lync Phone Edition 设备和 Skype 的仅的位置。 如果您需要使用开关级第 2 层数据来确定业务 Server 客户端的其他有线基于 PC 的 Skype 的位置，您需要使用客户端 MAC 地址方法。 
  
## <a name="subnet"></a>子网

第 3 层 IP 子网提供可用于自动检测客户端位置的业务服务器客户端支持的所有 Skype 的机制。 使用 IP 子网是配置和管理有线客户端的最简单定位方法。 但在决定使用子网之前，请使用以下问题来帮助确定子网的位置特性是否精细到足以准确找到客户端：
  
- 一个或多个客户端子网是否覆盖多个楼层？
    
- 一个或多个子网是否覆盖多座建筑？
    
- 每个客户端子网覆盖多大楼面空间？
    
如果子网覆盖的区域过于广泛，则可能需要使用其他机制来查找客户端。但作为最可行的方法，我们建议客户重新组织其 IP 子网，以满足 ERL 位置特性要求而不是引发基于 SNMP 的第三方解决方案的成本和复杂性。
  
## <a name="client-mac-address"></a>客户端 MAC 地址

若要使用的客户端计算机的 MAC 地址找到呼叫者，您需要托管以太网开关，并且必须部署业务连接到 （或通过） 的客户端可以发现 Skype 的 MAC 地址的第三方 SNMP 解决方案这些开关。 SNMP 解决方案会不断轮询托管交换机，以获取连接到每个端口的终结点 MAC 地址的当前映射并获取对应的端口 ID。 期间对位置信息服务的业务客户端的请求 Skype，位置信息服务查询的第三方应用程序使用的客户端 MAC 地址，，，然后返回任何匹配开关 IP 地址和端口 Id。 位置信息服务使用此信息来查询匹配记录其已发布的第 2 层线路映射，并返回到客户端的位置。 如果使用此选项，请确保 SNMP 应用程序与已发布的位置数据库记录之间的交换机端口标识符是一致的。
  
> [!NOTE]
> 某些第三方 SNMP 解决方案可以支持非托管的访问开关;如果服务业务客户端 Skype 开关是非托管，但具有上行于托管的分发开关，托管的开关可以报告返回到 SNMP 应用程序连接到访问交换机的客户端 MAC 地址。 此信息启用位置信息服务来标识用户的位置。 但是，只能向非托管交换机上的所有端口分配单个 ERL，因此位置特性仅在访问交换机的机架级别而非端口级别可用。 
  

