---
title: 定义用于确定 Skype for Business 服务器中的位置的网络元素
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
description: 规划要用于将呼叫者映射到 Skype for business Server 企业语音中的 E9 位置的网络组件时所需的决策。
ms.openlocfilehash: 404ac2d151f367ad391e4d5426090f20448cc383
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802662"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a>定义用于确定 Skype for Business 服务器中的位置的网络元素
 
规划要用于将呼叫者映射到 Skype for business Server 企业语音中的 E9 位置的网络组件时所需的决策。
  
如果您设置 Skype for Business 服务器基础结构以支持自动客户端位置检测，首先需要确定要用于将呼叫者映射到位置的网络元素。 在 Skype for Business Server 中，你可以将以下第2层和第3层网络元素关联到位置：
  
- 无线访问点 (WAP) 基本服务集标识 (BSSID) 地址（第 2 层）
    
- LLDP 交换机端口（第 2 层）
    
- LLDP 交换机机架 ID（第 2 层）
    
- IP 子网（第 3 层）
    
- 客户端 MAC 地址（第 2 层）
    
以上网络元素是按优先顺序列出的。 如果可以使用多个网络元素找到客户端，则 Skype for Business 服务器将使用优先级顺序确定要使用的机制。 
  
以下几节提供有关使用每个网络元素的更多详细信息。
  
> [!IMPORTANT]
> 使用网元将呼叫者映射到位置时，使位置信息服务数据库保持最新状态的重要性非常高。 例如，如果添加或更改网络元素（例如，添加 WAP），您必须删除旧条目并在位置数据库中添加新条目。 
  
## <a name="wireless-access-point"></a>无线访问点

当客户端以无线方式连接到网络时，位置请求使用 WAP 的 BSSID 地址来确定位置。 如果客户端是漫游，则表示的 WAP 可能不是最接近的，并且你甚至可以在建筑物的不同楼层上获取 WAP。 若要指示位置是近似的，可以将 location 值前置给 **[Near]** 或 **[关闭]** 描述符。
  
此位置方法假定每个 WAP 的 BSSID 都是静态的。 但是，如果 WAP 供应商使用动态分配的 BSSIDs，则从 WAP 获取的 BSSID 可能会更改（在 WAP 配置更改后可能会发生这种情况），并且无线客户端可能会在不接收位置的情况下留下。 若要防止这种可能性，你需要使用 ERLs 为每个 WAP 使用的所有可能的 BSSID 地址填充 Location 信息服务数据库。 
  
## <a name="lldp-ports-and-switches"></a>LLDP 端口和交换机

支持 Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) 的托管以太网交换机可向与 LLDP-MED 兼容的客户端播发其身份和端口信息，然后可向位置数据库查询该信息，以提供设备的位置。可以只在交换机机架 ID 上关联 ERL，或将其向下映射到端口级别。
  
> [!NOTE]
> Skype for Business 服务器支持使用 LLDP-MED-V 确定只有 Lync Phone Edition 设备和运行在 Windows 8 上的 Skype for business 客户端的位置。 如果需要使用交换机级别2数据来确定其他基于有线 PC 的 Skype for business 服务器客户端的位置，则需要使用客户端 MAC 地址方法。 
  
## <a name="subnet"></a>子网

第3层 IP 子网提供了所有 Skype for Business 服务器客户端支持的一种机制，可用于自动检测客户端位置。 使用 IP 子网是配置和管理有线客户端的最简单定位方法。 但在决定使用子网之前，请使用以下问题来帮助确定子网的位置特性是否精细到足以准确找到客户端：
  
- 一个或多个客户端子网是否覆盖多个楼层？
    
- 一个或多个子网是否覆盖多座建筑？
    
- 每个客户端子网覆盖多大楼面空间？
    
如果子网覆盖的区域过于广泛，则可能需要使用其他机制来查找客户端。但作为最可行的方法，我们建议客户重新组织其 IP 子网，以满足 ERL 位置特性要求而不是引发基于 SNMP 的第三方解决方案的成本和复杂性。
  
## <a name="client-mac-address"></a>客户端 MAC 地址

若要使用客户端计算机的 MAC 地址查找呼叫方，你需要托管以太网交换机，并且必须部署第三方 SNMP 解决方案，该解决方案可发现连接到（或通过）这些交换机的 Skype for business 客户端的 MAC 地址。 SNMP 解决方案会不断轮询托管交换机，以获取连接到每个端口的终结点 MAC 地址的当前映射并获取对应的端口 ID。 在 Skype for Business 客户端的位置信息服务请求期间，位置信息服务使用客户端的 MAC 地址查询第三方应用程序，然后返回任何匹配的交换机 IP 地址和端口 Id。 位置信息服务使用此信息查询其发布的第2层 wiremap 以查找匹配记录，并将位置返回到客户端。 如果使用此选项，请确保 SNMP 应用程序与已发布的位置数据库记录之间的交换机端口标识符是一致的。
  
> [!NOTE]
> 某些第三方 SNMP 解决方案可以支持非托管访问开关;如果为 Skype for business 客户端提供服务的开关是非托管的，但有一个指向托管分发开关的上行链路，则托管交换机可以向 SNMP 应用程序报告连接到 access 切换的客户端的 MAC 地址。 此信息使位置信息服务能够标识用户的位置。 但是，只能向非托管交换机上的所有端口分配单个 ERL，因此位置特性仅在访问交换机的机架级别而非端口级别可用。 
  

