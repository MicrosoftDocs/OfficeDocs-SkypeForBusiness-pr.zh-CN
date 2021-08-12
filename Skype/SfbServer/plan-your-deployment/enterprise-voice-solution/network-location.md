---
title: 定义用于确定位置的网络元素Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 规划将使用哪些网络组件将呼叫者映射到 E9-1-1 部署的位置所必需的决策Skype for Business Server 企业语音。
ms.openlocfilehash: fba8617643ac730d56f24e318a48cdb218b523cdceaa0cb810cc01c6c9d8a753
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281675"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a>定义用于确定位置的网络元素Skype for Business Server
 
规划将使用哪些网络组件将呼叫者映射到 E9-1-1 部署的位置所必需的决策Skype for Business Server 企业语音。
  
如果要将 Skype for Business Server 基础结构设置为支持自动客户端位置检测，则首先需要确定要使用哪些网络元素将呼叫者映射到位置。 在Skype for Business Server中，可以将以下第 2 层和第 3 层网络元素与位置关联：
  
- 无线访问点 (WAP) 基本服务集标识 (BSSID) 地址（第 2 层）
    
- LLDP 交换机端口（第 2 层）
    
- LLDP 交换机机架 ID（第 2 层）
    
- IP 子网（第 3 层）
    
- 客户端 MAC 地址（第 2 层）
    
以上网络元素是按优先顺序列出的。 如果可以使用多个网络元素来定位客户端，则Skype for Business Server按优先顺序确定要使用哪种机制。 
  
以下几节提供有关使用每个网络元素的更多详细信息。
  
> [!IMPORTANT]
> 使用网络元素将呼叫者映射到位置时，使位置信息服务数据库保持最新最为重要。 例如，如果添加或更改网络元素（例如，添加 WAP），您必须删除旧条目并在位置数据库中添加新条目。 
  
## <a name="wireless-access-point"></a>无线访问点

当客户端以无线方式连接到网络时，位置请求使用 WAP 的 BSSID 地址来确定位置。 如果客户端是漫游的，则指示的 WAP 可能不是最接近的 WAP，甚至可能选取位于建筑不同层的 WAP。 若要指示位置是近似值，可以在位置值前加 **[Near]** 或 **[Closeto]** 描述符。
  
此位置方法假定每个 WAP 的 BSSID 都是静态的。 但是，如果您的 WAP 供应商使用动态分配的 BSSID，则从 WAP 获取的 BSSID 可能会更改 (在 WAP 配置更改) 后可能会发生这种情况，并且无线客户端可能会离开他们未接收位置的情况。 为了防止这种可能性，您需要使用每个 WAP 使用的所有可能的 BSSID 地址的 ERLs 填充位置信息服务数据库。 
  
## <a name="lldp-ports-and-switches"></a>LLDP 端口和交换机

支持 Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) 的托管以太网交换机可向与 LLDP-MED 兼容的客户端播发其身份和端口信息，然后可向位置数据库查询该信息，以提供设备的位置。可以只在交换机机架 ID 上关联 ERL，或将其向下映射到端口级别。
  
> [!NOTE]
> Skype for Business Server支持使用 LLDP-MED 仅确定 Lync 电话 Edition 设备的位置，Skype for Business运行在 Windows 8。 如果你需要使用交换机级别第 2 层数据来确定其他基于 PC 的有线 Skype for Business Server 客户端的位置，则需要使用客户端 MAC 地址方法。 
  
## <a name="subnet"></a>子网

第 3 层 IP 子网提供一种受所有 Skype for Business Server 客户端支持的机制，该机制可用于自动检测客户端位置。 使用 IP 子网是配置和管理有线客户端的最简单定位方法。 但在决定使用子网之前，请使用以下问题来帮助确定子网的位置特性是否精细到足以准确找到客户端：
  
- 一个或多个客户端子网是否覆盖多个楼层？
    
- 一个或多个子网是否覆盖多座建筑？
    
- 每个客户端子网覆盖多大楼面空间？
    
如果子网覆盖的区域过于广泛，则可能需要使用其他机制来查找客户端。但作为最可行的方法，我们建议客户重新组织其 IP 子网，以满足 ERL 位置特性要求而不是引发基于 SNMP 的第三方解决方案的成本和复杂性。
  
## <a name="client-mac-address"></a>客户端 MAC 地址

若要使用客户端计算机的 MAC 地址查找呼叫者，您需要托管的以太网交换机，并且必须部署第三方 SNMP 解决方案，该解决方案可以发现连接到 (或通过) 这些交换机连接的 Skype for Business 客户端的 MAC 地址。 SNMP 解决方案会不断轮询托管交换机，以获取连接到每个端口的终结点 MAC 地址的当前映射并获取对应的端口 ID。 在Skype for Business客户端请求位置信息服务期间，位置信息服务使用客户端的 MAC 地址查询第三方应用程序，然后返回任何匹配的交换机 IP 地址和端口 ID。 位置信息服务使用此信息来查询其发布的第 2 层线路映射中是否包含匹配记录，并且将位置返回给客户端。 如果使用此选项，请确保 SNMP 应用程序与已发布的位置数据库记录之间的交换机端口标识符是一致的。
  
> [!NOTE]
> 某些第三方 SNMP 解决方案可以支持非托管访问交换机;如果为 Skype for Business 客户端服务的交换机是非托管的，但具有到托管分发交换机的上行链接，则托管交换机可以向 SNMP 应用程序返回连接到访问交换机的客户端的 MAC 地址。 利用此信息，位置信息服务可以标识用户的位置。 但是，只能向非托管交换机上的所有端口分配单个 ERL，因此位置特性仅在访问交换机的机架级别而非端口级别可用。 
  

