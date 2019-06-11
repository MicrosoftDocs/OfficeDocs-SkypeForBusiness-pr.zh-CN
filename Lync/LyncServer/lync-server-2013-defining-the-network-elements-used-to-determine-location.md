---
title: 'Lync Server 2013: 定义用于确定位置的网元'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining the network elements used to determine location
ms:assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398567(v=OCS.15)
ms:contentKeyID: 48184508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 572e7e5392390e659b52853cb47e30f696c65e91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-network-elements-used-to-determine-location-in-lync-server-2013"></a>定义用于确定 Lync Server 2013 中的位置的网络元素

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-29_

如果你将 Lync Server 基础结构设置为支持自动客户端位置检测, 首先需要确定要用于将呼叫者映射到位置的网络元素。 在 Lync Server 2013 中, 你可以将以下第2层和第3层网络元素与位置关联:

  - 无线访问点 (WAP) 基本服务集标识 (BSSID) 地址（第 2 层）

  - LLDP 交换机端口（第 2 层）

  - LLDP 交换机机架 ID（第 2 层）

  - IP 子网（第 3 层）

  - 客户端 MAC 地址（第 2 层）

以上网络元素是按优先顺序列出的。 如果可以使用多个网络元素找到客户端, 则 Lync Server 将使用优先级顺序确定要使用的机制。

以下几节提供有关使用每个网络元素的更多详细信息。

<div>


> [!IMPORTANT]  
> 使用网元将呼叫者映射到位置时, 使位置信息服务数据库保持最新状态的重要性非常高。 例如，如果添加或更改网络元素（例如，添加 WAP），您必须删除旧条目并在位置数据库中添加新条目。



</div>

<div>

## <a name="wireless-access-point"></a>无线访问点

当客户端以无线方式连接到网络时，位置请求使用 WAP 的 BSSID 地址来确定位置。 如果客户端处于漫游状态，则指明的 WAP 可能不是最近的 WAP，甚至可能选取在建筑的其他层的 WAP。 若要指示该位置是近似的，您可以将 Near 或 Close to 描述符附加到位置值的前面。

此位置方法假定每个 WAP 的 BSSID 都是静态的。 但如果 WAP 供应商使用动态分配的 BSSID，则从 WAP 获取的 BSSID 可能会发生更改（此情况会在 WAP 配置发生更改之后出现），并且无线客户端可以处于不接收位置的情况。 若要防止这种可能性, 你需要使用 ERLs 为每个 WAP 使用的所有可能的 BSSID 地址填充 Location 信息服务数据库。

</div>

<div>

## <a name="lldp-ports-and-switches"></a>LLDP 端口和交换机

支持 Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) 的托管以太网交换机可向与 LLDP-MED 兼容的客户端播发其身份和端口信息，然后可向位置数据库查询该信息，以提供设备的位置。可以只在交换机机架 ID 上关联 ERL，或将其向下映射到端口级别。

<div>


> [!NOTE]  
> Lync Server 2013 支持使用 LLDP-MED-V 确定只有 Lync Phone Edition 设备和运行在 Windows 8 上的 Lync 2013 的位置。 如果需要使用交换机级别2数据来确定其他基于有线 PC 的 Lync 客户端的位置, 则需要使用客户端 MAC 地址方法。



</div>

</div>

<div>

## <a name="subnet"></a>子网

第3层 IP 子网提供由所有 Lync Server 客户端支持的一种机制, 可用于自动检测客户端位置。 使用 IP 子网是配置和管理有线客户端的最简单定位方法。 但在决定使用子网之前，请使用以下问题来帮助确定子网的位置特性是否精细到足以准确找到客户端：

  - 一个或多个客户端子网是否覆盖多个楼层？

  - 一个或多个子网是否覆盖多座建筑？

  - 每个客户端子网覆盖多大楼面空间？

如果子网覆盖的区域过于广泛，则可能需要使用其他机制来查找客户端。但作为最可行的方法，我们建议客户重新组织其 IP 子网，以满足 ERL 位置特性要求而不是引发基于 SNMP 的第三方解决方案的成本和复杂性。

</div>

<div>

## <a name="client-mac-address"></a>客户端 MAC 地址

若要使用客户端计算机的 MAC 地址查找呼叫方, 你需要托管以太网交换机, 并且必须部署第三方 SNMP 解决方案, 该解决方案能够发现连接到 (或通过) 这些交换机的 Lync 客户端的 MAC 地址。 SNMP 解决方案会不断轮询托管交换机，以获取连接到每个端口的终结点 MAC 地址的当前映射并获取对应的端口 ID。 在 Lync 客户端的位置信息服务请求期间, 位置信息服务使用客户端的 MAC 地址查询第三方应用程序, 然后返回任何匹配的交换机 IP 地址和端口 Id。 位置信息服务使用此信息查询其发布的第2层 wiremap 以查找匹配记录, 并将位置返回到客户端。 如果使用此选项，请确保 SNMP 应用程序与已发布的位置数据库记录之间的交换机端口标识符是一致的。

<div>


> [!NOTE]  
> 某些第三方 SNMP 解决方案可以支持非托管访问开关;如果为 Lync 客户端提供服务但具有指向托管分发切换器的上行的切换, 则托管交换机可以向 SNMP 应用程序报告连接到访问交换机的客户端的 MAC 地址。 此信息使位置信息服务能够标识用户的位置。 但是，只能向非托管交换机上的所有端口分配单个 ERL，因此位置特性仅在访问交换机的机架级别而非端口级别可用。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

