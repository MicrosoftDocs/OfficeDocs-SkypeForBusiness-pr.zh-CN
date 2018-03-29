---
title: 在 Skype for Business Server 2015 中定义用于确定位置的网络元素
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
description: 您将使用映射到业务服务器企业语音在 Skype 的 E9-1-1 部署位置的调用方的决策所需的规划的网络组件。
ms.openlocfilehash: 2d371b2abfd8e3c871f0d9f49409d2b8169268c2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中定义用于确定位置的网络元素
 
您将使用映射到业务服务器企业语音在 Skype 的 E9-1-1 部署位置的调用方的决策所需的规划的网络组件。
  
如果您正在设置业务服务器基础结构以支持自动客户端位置检测您 Skype，首先需要决定哪一个网络元素要使用映射到位置的调用方。 在 Skype 业务服务器，可以将以下第 2 层和第 3 层网络元素与位置相关联：
  
- 无线访问点 (WAP) 基本服务集标识 (BSSID) 地址（第 2 层）
    
- LLDP 交换机端口（第 2 层）
    
- LLDP 交换机机架 ID（第 2 层）
    
- IP 子网（第 3 层）
    
- 客户端 MAC 地址（第 2 层）
    
以上网络元素是按优先顺序列出的。 如果可以使用多个网络元素位于客户端，Skype 业务服务器使用优先的顺序来确定要使用哪些机制。 
  
以下几节提供有关使用每个网络元素的更多详细信息。
  
> [!IMPORTANT]
> 当您使用网络元素映射到位置的调用方时，是极其重要的您使位置信息服务数据库保持最新。 例如，如果添加或更改网络元素（例如，添加 WAP），您必须删除旧条目并在位置数据库中添加新条目。 
  
## <a name="wireless-access-point"></a>无线访问点

当客户端以无线方式连接到网络时，位置请求使用 WAP 的 BSSID 地址来确定位置。 如果漫游客户端，WAP 指示可能不是最近的一个，并且甚至可以拿起在不同的楼层建筑物的 WAP。 若要指示的位置是近似，可以预置使用**[附近]**或**[关闭]**说明符的位置值。
  
此位置方法假定每个 WAP 的 BSSID 都是静态的。 但是，如果您 WAP 的供应商使用动态分配的 BSSIDs，来自 WAP BSSID 无法更改 （这会发生下列 WAP 配置更改），并且不接收位置的情况下，无线客户端可以保留。 为了防止这种可能性，您需要填充位置信息服务与 ERLs 数据库使用的每个 WAP 的所有可能 BSSID 地址。 
  
## <a name="lldp-ports-and-switches"></a>LLDP 端口和交换机

支持 Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) 的托管以太网交换机可向与 LLDP-MED 兼容的客户端播发其身份和端口信息，然后可向位置数据库查询该信息，以提供设备的位置。可以只在交换机机架 ID 上关联 ERL，或将其向下映射到端口级别。
  
> [!NOTE]
> Skype 业务服务器支持使用 LLDP-MED 确定只的 Lync 电话版设备和 Skype 业务客户端运行在 Windows 8 上的位置。 如果您需要使用第二层交换机级别的数据来确定业务服务器客户端的基于 PC 的其他有线 Skype 的位置，您需要使用客户端的 MAC 地址的方法。 
  
## <a name="subnet"></a>子网

第 3 层 IP 子网提供一种机制，可用来自动检测客户端位置的业务服务器客户端支持所有 Skype。 使用 IP 子网是配置和管理有线客户端的最简单定位方法。 但在决定使用子网之前，请使用以下问题来帮助确定子网的位置特性是否精细到足以准确找到客户端：
  
- 一个或多个客户端子网是否覆盖多个楼层？
    
- 一个或多个子网是否覆盖多座建筑？
    
- 每个客户端子网覆盖多大楼面空间？
    
如果子网覆盖的区域过于广泛，则可能需要使用其他机制来查找客户端。但作为最可行的方法，我们建议客户重新组织其 IP 子网，以满足 ERL 位置特性要求而不是引发基于 SNMP 的第三方解决方案的成本和复杂性。
  
## <a name="client-mac-address"></a>客户端 MAC 地址

若要使用客户端计算机的 MAC 地址来查找调用方，您需要管理的以太网交换机，并且必须部署第三方 SNMP 解决方案可为企业客户端连接到 （或通过） 发现 Skype 的 MAC 地址开关。 SNMP 解决方案会不断轮询托管交换机，以获取连接到每个端口的终结点 MAC 地址的当前映射并获取对应的端口 ID。 在对的位置信息服务的业务客户端的请求 Skype，位置信息服务查询通过使用客户端的 MAC 地址，该第三方应用程序，然后返回任何匹配交换机的 IP 地址和端口 Id。 位置信息服务将使用此信息来查询其发布的第 2 层 wiremap 匹配记录的和向客户端返回的位置。 如果使用此选项，请确保 SNMP 应用程序与已发布的位置数据库记录之间的交换机端口标识符是一致的。
  
> [!NOTE]
> 某些第三方 SNMP 解决方案可以支持非托管的访问交换机;如果服务业务客户端的 Skype 的开关处于非托管状态，但有到托管的通讯交换机上行链路，托管的交换机可报告给 SNMP 应用程序连接到访问交换机的客户端的 MAC 地址。 此信息使位置信息服务，以确定用户的位置。 但是，只能向非托管交换机上的所有端口分配单个 ERL，因此位置特性仅在访问交换机的机架级别而非端口级别可用。 
  

