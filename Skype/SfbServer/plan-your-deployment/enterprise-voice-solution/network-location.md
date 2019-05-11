---
title: 定义用于确定业务服务器中 Skype 位置的网络元素
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 795856b1377fc4a29744b7fdf1dd285359798a2f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913730"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a><span data-ttu-id="ac6fd-103">定义用于确定业务服务器中 Skype 位置的网络元素</span><span class="sxs-lookup"><span data-stu-id="ac6fd-103">Define the network elements used to determine location in Skype for Business Server</span></span>
 
<span data-ttu-id="ac6fd-104">将用于将呼叫者映射到 E9-1-1 部署中 Skype 业务 Server 企业语音的位置的决策所必需的规划的网络组件。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-104">Decisions necessary for planning which network components you will use to map callers to locations for E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="ac6fd-105">如果要设置业务服务器基础结构支持自动客户端位置检测您 Skype，首先需要决定哪些网络元素您打算用于将呼叫者映射到的位置。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-105">If you are setting up your Skype for Business Server infrastructure to support automatic client location detection, you first need to decide which network elements you are going to use to map callers to locations.</span></span> <span data-ttu-id="ac6fd-106">在业务服务器 Skype，可以将以下层 2 和第 3 层网络元素与位置相关联：</span><span class="sxs-lookup"><span data-stu-id="ac6fd-106">In Skype for Business Server, you can associate the following Layer 2 and Layer 3 network elements with locations:</span></span>
  
- <span data-ttu-id="ac6fd-107">无线访问点 (WAP) 基本服务集标识 (BSSID) 地址（第 2 层）</span><span class="sxs-lookup"><span data-stu-id="ac6fd-107">Wireless access point (WAP) Basic Service Set Identification (BSSID) addresses (Layer 2)</span></span>
    
- <span data-ttu-id="ac6fd-108">LLDP 交换机端口（第 2 层）</span><span class="sxs-lookup"><span data-stu-id="ac6fd-108">LLDP switch port (Layer 2)</span></span>
    
- <span data-ttu-id="ac6fd-109">LLDP 交换机机架 ID（第 2 层）</span><span class="sxs-lookup"><span data-stu-id="ac6fd-109">LLDP switch chassis IDs (Layer 2)</span></span>
    
- <span data-ttu-id="ac6fd-110">IP 子网（第 3 层）</span><span class="sxs-lookup"><span data-stu-id="ac6fd-110">IP subnets (Layer 3)</span></span>
    
- <span data-ttu-id="ac6fd-111">客户端 MAC 地址（第 2 层）</span><span class="sxs-lookup"><span data-stu-id="ac6fd-111">Client MAC addresses (Layer 2)</span></span>
    
<span data-ttu-id="ac6fd-112">以上网络元素是按优先顺序列出的。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-112">The network elements are listed in order of precedence.</span></span> <span data-ttu-id="ac6fd-113">如果客户端可以通过使用多个网络元素位于，Skype 业务服务器使用优先级的顺序确定要使用的机制。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-113">If a client can be located by using more than one network element, Skype for Business Server uses the order of precedence to determine which mechanism to use.</span></span> 
  
<span data-ttu-id="ac6fd-114">以下几节提供有关使用每个网络元素的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-114">The following sections provide more details for using each network element.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ac6fd-115">使用网络元素到位置映射呼叫者，时，最重要的您保持最新的位置信息服务数据库。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-115">When you use network elements to map callers to locations, it is of utmost importance that you keep the Location Information service database up-to-date.</span></span> <span data-ttu-id="ac6fd-116">例如，如果添加或更改网络元素（例如，添加 WAP），您必须删除旧条目并在位置数据库中添加新条目。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-116">For example, if you add or change a network element, such as adding a WAP, you must delete the old entry and add the new entry in the location database.</span></span> 
  
## <a name="wireless-access-point"></a><span data-ttu-id="ac6fd-117">无线访问点</span><span class="sxs-lookup"><span data-stu-id="ac6fd-117">Wireless Access Point</span></span>

<span data-ttu-id="ac6fd-118">当客户端以无线方式连接到网络时，位置请求使用 WAP 的 BSSID 地址来确定位置。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-118">When a client connects to the network wirelessly, the location request uses the BSSID address of the WAP to determine its location.</span></span> <span data-ttu-id="ac6fd-119">如果客户端漫游，指示 WAP 可能不到最近的一个，甚至可以拿起上构建的不同基底的 WAP。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-119">If the client is roaming, the WAP indicated may not be the closest one, and it's even possible to pick up a WAP that is on a different floor of the building.</span></span> <span data-ttu-id="ac6fd-120">若要指示位置是一个大概，可以附加 **[附近]** 或 **[关闭以]** 描述符与位置值。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-120">To indicate that the location is approximate, you can prepend the location value with a **[Near]** or **[Closeto]** descriptor.</span></span>
  
<span data-ttu-id="ac6fd-121">此位置方法假定每个 WAP 的 BSSID 都是静态的。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-121">This location method assumes that the BSSID of each WAP is static.</span></span> <span data-ttu-id="ac6fd-122">但是，如果您 WAP 供应商，使用动态分配 BSSIDs，获取从 WAP BSSID 可能发生更改 （这会发生以下 WAP 配置更改），并且无法在不接收位置的情况下左无线客户端。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-122">However, if your WAP vendor uses dynamically-assigned BSSIDs, the BSSID that is obtained from a WAP could change (this can happen following a WAP configuration change), and wireless clients could be left in a situation where they don't receive a location.</span></span> <span data-ttu-id="ac6fd-123">若要防止这种可能性，您需要填充所有可能的 BSSID 地址由每个 WAP 与 Erl 的位置信息服务数据库。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-123">To prevent this possibility, you need to populate the Location Information service database with ERLs for all possible BSSID addresses used by each WAP.</span></span> 
  
## <a name="lldp-ports-and-switches"></a><span data-ttu-id="ac6fd-124">LLDP 端口和交换机</span><span class="sxs-lookup"><span data-stu-id="ac6fd-124">LLDP Ports and Switches</span></span>

<span data-ttu-id="ac6fd-p106">支持 Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) 的托管以太网交换机可向与 LLDP-MED 兼容的客户端播发其身份和端口信息，然后可向位置数据库查询该信息，以提供设备的位置。可以只在交换机机架 ID 上关联 ERL，或将其向下映射到端口级别。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-p106">Managed Ethernet switches that support Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) can advertise their identity and port information to LLDP-MED compatible clients, which then can be queried against the location database to provide the location of the device. You can associate ERLs solely on the switch chassis ID, or you can map them down to the port level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ac6fd-127">Skype 业务服务器支持使用 LLDP-MED 用于确定 Windows 8 上运行的业务客户端的 Lync Phone Edition 设备和 Skype 的仅的位置。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-127">Skype for Business Server supports using LLDP-MED for determining locations only of Lync Phone Edition devices and Skype for Business clients running on Windows 8.</span></span> <span data-ttu-id="ac6fd-128">如果您需要使用开关级第 2 层数据来确定业务 Server 客户端的其他有线基于 PC 的 Skype 的位置，您需要使用客户端 MAC 地址方法。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-128">If you need to use switch-level Layer 2 data to determine the location of other wired PC-based Skype for Business Server clients, you need to use the client MAC address method.</span></span> 
  
## <a name="subnet"></a><span data-ttu-id="ac6fd-129">子网</span><span class="sxs-lookup"><span data-stu-id="ac6fd-129">Subnet</span></span>

<span data-ttu-id="ac6fd-130">第 3 层 IP 子网提供可用于自动检测客户端位置的业务服务器客户端支持的所有 Skype 的机制。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-130">Layer 3 IP subnets provide a mechanism supported by all Skype for Business Server clients that can be used to automatically detect client location.</span></span> <span data-ttu-id="ac6fd-131">使用 IP 子网是配置和管理有线客户端的最简单定位方法。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-131">Using IP subnets is the easiest location method to configure and manage wired clients.</span></span> <span data-ttu-id="ac6fd-132">但在决定使用子网之前，请使用以下问题来帮助确定子网的位置特性是否精细到足以准确找到客户端：</span><span class="sxs-lookup"><span data-stu-id="ac6fd-132">Before you decide to use subnets, however, use the following questions to help determine if the location specificity of the subnet is sufficiently fine to accurately locate a client:</span></span>
  
- <span data-ttu-id="ac6fd-133">一个或多个客户端子网是否覆盖多个楼层？</span><span class="sxs-lookup"><span data-stu-id="ac6fd-133">Do one or more client subnets cover multiple floors?</span></span>
    
- <span data-ttu-id="ac6fd-134">一个或多个子网是否覆盖多座建筑？</span><span class="sxs-lookup"><span data-stu-id="ac6fd-134">Do one or more subnets cover more than one building?</span></span>
    
- <span data-ttu-id="ac6fd-135">每个客户端子网覆盖多大楼面空间？</span><span class="sxs-lookup"><span data-stu-id="ac6fd-135">How much floor space is covered by each client subnet?</span></span>
    
<span data-ttu-id="ac6fd-p109">如果子网覆盖的区域过于广泛，则可能需要使用其他机制来查找客户端。但作为最可行的方法，我们建议客户重新组织其 IP 子网，以满足 ERL 位置特性要求而不是引发基于 SNMP 的第三方解决方案的成本和复杂性。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-p109">If the subnet covers too broad an area, you may need to use another mechanism to locate clients. However, if at all practical, we recommend that customers reorganize their IP subnetting to meet the ERL location specificity requirements rather than incurring the cost and complexity of third-party SNMP-based solutions.</span></span>
  
## <a name="client-mac-address"></a><span data-ttu-id="ac6fd-138">客户端 MAC 地址</span><span class="sxs-lookup"><span data-stu-id="ac6fd-138">Client MAC Address</span></span>

<span data-ttu-id="ac6fd-139">若要使用的客户端计算机的 MAC 地址找到呼叫者，您需要托管以太网开关，并且必须部署业务连接到 （或通过） 的客户端可以发现 Skype 的 MAC 地址的第三方 SNMP 解决方案这些开关。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-139">To use a client computer's MAC address to locate a caller, you need managed Ethernet switches, and you must deploy a third-party SNMP solution that can discover the MAC addresses of Skype for Business clients connected to (or through) those switches.</span></span> <span data-ttu-id="ac6fd-140">SNMP 解决方案会不断轮询托管交换机，以获取连接到每个端口的终结点 MAC 地址的当前映射并获取对应的端口 ID。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-140">The SNMP solution continually polls the managed switches to get the current mappings of the endpoint MAC addresses connected to each port and obtains the corresponding port IDs.</span></span> <span data-ttu-id="ac6fd-141">期间对位置信息服务的业务客户端的请求 Skype，位置信息服务查询的第三方应用程序使用的客户端 MAC 地址，，，然后返回任何匹配开关 IP 地址和端口 Id。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-141">During a Skype for Business client's request to the Location Information service, the Location Information service queries the third-party application by using the client's MAC address, and then returns any matching switch IP addresses and port IDs.</span></span> <span data-ttu-id="ac6fd-142">位置信息服务使用此信息来查询匹配记录其已发布的第 2 层线路映射，并返回到客户端的位置。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-142">The Location Information service uses this information to query its published Layer 2 wiremap for a matching record and returns the location to the client.</span></span> <span data-ttu-id="ac6fd-143">如果使用此选项，请确保 SNMP 应用程序与已发布的位置数据库记录之间的交换机端口标识符是一致的。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-143">If you use this option, make sure that the switch port identifiers are consistent between the SNMP application and the published location database records.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ac6fd-144">某些第三方 SNMP 解决方案可以支持非托管的访问开关;如果服务业务客户端 Skype 开关是非托管，但具有上行于托管的分发开关，托管的开关可以报告返回到 SNMP 应用程序连接到访问交换机的客户端 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-144">Some third-party SNMP solutions can support unmanaged access switches; if the switch that services the Skype for Business client is unmanaged but has an uplink to a managed distribution switch, the managed switch can report back to the SNMP application the MAC addresses of the clients connected to the access switch.</span></span> <span data-ttu-id="ac6fd-145">此信息启用位置信息服务来标识用户的位置。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-145">This information enables the Location Information service to identify the location of the user.</span></span> <span data-ttu-id="ac6fd-146">但是，只能向非托管交换机上的所有端口分配单个 ERL，因此位置特性仅在访问交换机的机架级别而非端口级别可用。</span><span class="sxs-lookup"><span data-stu-id="ac6fd-146">However, it is possible to assign only a single ERL to all ports on the unmanaged switch, so the location specificity is available only at the chassis level of the access switch, not the port level.</span></span> 
  

