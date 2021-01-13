---
title: 定义用于确定 Skype for Business Server 中位置的网络元素
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
description: 规划将使用哪些网络组件将呼叫者映射到 Skype for Business Server 企业语音 中的 E9-1-1 部署位置所必需的决策。
ms.openlocfilehash: 473ef9efc8598b303d6c7a05b902d57e0ad8ffd5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813632"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a><span data-ttu-id="8ce6c-103">定义用于确定 Skype for Business Server 中位置的网络元素</span><span class="sxs-lookup"><span data-stu-id="8ce6c-103">Define the network elements used to determine location in Skype for Business Server</span></span>
 
<span data-ttu-id="8ce6c-104">规划将使用哪些网络组件将呼叫者映射到 Skype for Business Server 企业语音 中的 E9-1-1 部署位置所必需的决策。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-104">Decisions necessary for planning which network components you will use to map callers to locations for E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="8ce6c-105">如果要将 Skype for Business Server 基础结构设置为支持自动客户端位置检测，则首先需要确定要使用哪些网络元素将呼叫者映射到位置。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-105">If you are setting up your Skype for Business Server infrastructure to support automatic client location detection, you first need to decide which network elements you are going to use to map callers to locations.</span></span> <span data-ttu-id="8ce6c-106">在 Skype for Business Server 中，可以将以下第 2 层和第 3 层网络元素与位置关联：</span><span class="sxs-lookup"><span data-stu-id="8ce6c-106">In Skype for Business Server, you can associate the following Layer 2 and Layer 3 network elements with locations:</span></span>
  
- <span data-ttu-id="8ce6c-107">无线访问点 (WAP) 基本服务集标识 (BSSID) 地址（第 2 层）</span><span class="sxs-lookup"><span data-stu-id="8ce6c-107">Wireless access point (WAP) Basic Service Set Identification (BSSID) addresses (Layer 2)</span></span>
    
- <span data-ttu-id="8ce6c-108">LLDP 交换机端口（第 2 层）</span><span class="sxs-lookup"><span data-stu-id="8ce6c-108">LLDP switch port (Layer 2)</span></span>
    
- <span data-ttu-id="8ce6c-109">LLDP 交换机机架 ID（第 2 层）</span><span class="sxs-lookup"><span data-stu-id="8ce6c-109">LLDP switch chassis IDs (Layer 2)</span></span>
    
- <span data-ttu-id="8ce6c-110">IP 子网（第 3 层）</span><span class="sxs-lookup"><span data-stu-id="8ce6c-110">IP subnets (Layer 3)</span></span>
    
- <span data-ttu-id="8ce6c-111">客户端 MAC 地址（第 2 层）</span><span class="sxs-lookup"><span data-stu-id="8ce6c-111">Client MAC addresses (Layer 2)</span></span>
    
<span data-ttu-id="8ce6c-112">以上网络元素是按优先顺序列出的。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-112">The network elements are listed in order of precedence.</span></span> <span data-ttu-id="8ce6c-113">如果客户端可以使用多个网络元素来定位，Skype for Business Server 将使用优先顺序来确定要使用哪种机制。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-113">If a client can be located by using more than one network element, Skype for Business Server uses the order of precedence to determine which mechanism to use.</span></span> 
  
<span data-ttu-id="8ce6c-114">以下几节提供有关使用每个网络元素的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-114">The following sections provide more details for using each network element.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8ce6c-115">使用网络元素将呼叫者映射到位置时，使位置信息服务数据库保持最新最为重要。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-115">When you use network elements to map callers to locations, it is of utmost importance that you keep the Location Information service database up-to-date.</span></span> <span data-ttu-id="8ce6c-116">例如，如果添加或更改网络元素（例如，添加 WAP），您必须删除旧条目并在位置数据库中添加新条目。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-116">For example, if you add or change a network element, such as adding a WAP, you must delete the old entry and add the new entry in the location database.</span></span> 
  
## <a name="wireless-access-point"></a><span data-ttu-id="8ce6c-117">无线访问点</span><span class="sxs-lookup"><span data-stu-id="8ce6c-117">Wireless Access Point</span></span>

<span data-ttu-id="8ce6c-118">当客户端以无线方式连接到网络时，位置请求使用 WAP 的 BSSID 地址来确定位置。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-118">When a client connects to the network wirelessly, the location request uses the BSSID address of the WAP to determine its location.</span></span> <span data-ttu-id="8ce6c-119">如果客户端正在漫游，则指示的 WAP 可能不是最接近的 WAP，甚至可以选取位于建筑物不同楼层的 WAP。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-119">If the client is roaming, the WAP indicated may not be the closest one, and it's even possible to pick up a WAP that is on a different floor of the building.</span></span> <span data-ttu-id="8ce6c-120">若要指示位置是近似值，可以在位置值前加 **[Near]** 或 **[Closeto]** 描述符。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-120">To indicate that the location is approximate, you can prepend the location value with a **[Near]** or **[Closeto]** descriptor.</span></span>
  
<span data-ttu-id="8ce6c-121">此位置方法假定每个 WAP 的 BSSID 都是静态的。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-121">This location method assumes that the BSSID of each WAP is static.</span></span> <span data-ttu-id="8ce6c-122">但是，如果您的 WAP 供应商使用动态分配的 BSSID，则从 WAP 获取的 BSSID 可能会更改 (在 WAP 配置更改) 之后可能会发生这种情况，并且无线客户端可能会离开它们无法接收位置的情况。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-122">However, if your WAP vendor uses dynamically-assigned BSSIDs, the BSSID that is obtained from a WAP could change (this can happen following a WAP configuration change), and wireless clients could be left in a situation where they don't receive a location.</span></span> <span data-ttu-id="8ce6c-123">若要避免这种可能性，您需要使用每个 WAP 使用的所有可能的 BSSID 地址的 ERLs 填充位置信息服务数据库。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-123">To prevent this possibility, you need to populate the Location Information service database with ERLs for all possible BSSID addresses used by each WAP.</span></span> 
  
## <a name="lldp-ports-and-switches"></a><span data-ttu-id="8ce6c-124">LLDP 端口和交换机</span><span class="sxs-lookup"><span data-stu-id="8ce6c-124">LLDP Ports and Switches</span></span>

<span data-ttu-id="8ce6c-p106">支持 Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) 的托管以太网交换机可向与 LLDP-MED 兼容的客户端播发其身份和端口信息，然后可向位置数据库查询该信息，以提供设备的位置。可以只在交换机机架 ID 上关联 ERL，或将其向下映射到端口级别。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-p106">Managed Ethernet switches that support Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) can advertise their identity and port information to LLDP-MED compatible clients, which then can be queried against the location database to provide the location of the device. You can associate ERLs solely on the switch chassis ID, or you can map them down to the port level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8ce6c-127">Skype for Business Server 支持使用 LLDP-MED 来确定仅 Lync Phone Edition 设备和在 Windows 8 上运行的 Skype for Business 客户端的位置。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-127">Skype for Business Server supports using LLDP-MED for determining locations only of Lync Phone Edition devices and Skype for Business clients running on Windows 8.</span></span> <span data-ttu-id="8ce6c-128">如果你需要使用交换机级别第 2 层数据来确定其他基于 PC 的有线 Skype for Business Server 客户端的位置，则需要使用客户端 MAC 地址方法。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-128">If you need to use switch-level Layer 2 data to determine the location of other wired PC-based Skype for Business Server clients, you need to use the client MAC address method.</span></span> 
  
## <a name="subnet"></a><span data-ttu-id="8ce6c-129">子网</span><span class="sxs-lookup"><span data-stu-id="8ce6c-129">Subnet</span></span>

<span data-ttu-id="8ce6c-130">第 3 层 IP 子网提供一种受所有 Skype for Business Server 客户端支持的机制，可用于自动检测客户端位置。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-130">Layer 3 IP subnets provide a mechanism supported by all Skype for Business Server clients that can be used to automatically detect client location.</span></span> <span data-ttu-id="8ce6c-131">使用 IP 子网是配置和管理有线客户端的最简单定位方法。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-131">Using IP subnets is the easiest location method to configure and manage wired clients.</span></span> <span data-ttu-id="8ce6c-132">但在决定使用子网之前，请使用以下问题来帮助确定子网的位置特性是否精细到足以准确找到客户端：</span><span class="sxs-lookup"><span data-stu-id="8ce6c-132">Before you decide to use subnets, however, use the following questions to help determine if the location specificity of the subnet is sufficiently fine to accurately locate a client:</span></span>
  
- <span data-ttu-id="8ce6c-133">一个或多个客户端子网是否覆盖多个楼层？</span><span class="sxs-lookup"><span data-stu-id="8ce6c-133">Do one or more client subnets cover multiple floors?</span></span>
    
- <span data-ttu-id="8ce6c-134">一个或多个子网是否覆盖多座建筑？</span><span class="sxs-lookup"><span data-stu-id="8ce6c-134">Do one or more subnets cover more than one building?</span></span>
    
- <span data-ttu-id="8ce6c-135">每个客户端子网覆盖多大楼面空间？</span><span class="sxs-lookup"><span data-stu-id="8ce6c-135">How much floor space is covered by each client subnet?</span></span>
    
<span data-ttu-id="8ce6c-p109">如果子网覆盖的区域过于广泛，则可能需要使用其他机制来查找客户端。但作为最可行的方法，我们建议客户重新组织其 IP 子网，以满足 ERL 位置特性要求而不是引发基于 SNMP 的第三方解决方案的成本和复杂性。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-p109">If the subnet covers too broad an area, you may need to use another mechanism to locate clients. However, if at all practical, we recommend that customers reorganize their IP subnetting to meet the ERL location specificity requirements rather than incurring the cost and complexity of third-party SNMP-based solutions.</span></span>
  
## <a name="client-mac-address"></a><span data-ttu-id="8ce6c-138">客户端 MAC 地址</span><span class="sxs-lookup"><span data-stu-id="8ce6c-138">Client MAC Address</span></span>

<span data-ttu-id="8ce6c-139">若要使用客户端计算机的 MAC 地址查找呼叫者，你需要托管的以太网交换机，并且必须部署第三方 SNMP 解决方案，该解决方案可以发现连接到 (或通过) 这些交换机的 Skype for Business 客户端的 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-139">To use a client computer's MAC address to locate a caller, you need managed Ethernet switches, and you must deploy a third-party SNMP solution that can discover the MAC addresses of Skype for Business clients connected to (or through) those switches.</span></span> <span data-ttu-id="8ce6c-140">SNMP 解决方案会不断轮询托管交换机，以获取连接到每个端口的终结点 MAC 地址的当前映射并获取对应的端口 ID。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-140">The SNMP solution continually polls the managed switches to get the current mappings of the endpoint MAC addresses connected to each port and obtains the corresponding port IDs.</span></span> <span data-ttu-id="8ce6c-141">在 Skype for Business 客户端请求位置信息服务期间，位置信息服务使用客户端的 MAC 地址查询第三方应用程序，然后返回任何匹配的交换机 IP 地址和端口 ID。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-141">During a Skype for Business client's request to the Location Information service, the Location Information service queries the third-party application by using the client's MAC address, and then returns any matching switch IP addresses and port IDs.</span></span> <span data-ttu-id="8ce6c-142">位置信息服务使用此信息查询其发布的第 2 层线路映射，以寻找匹配的记录，并返回位置给客户端。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-142">The Location Information service uses this information to query its published Layer 2 wiremap for a matching record and returns the location to the client.</span></span> <span data-ttu-id="8ce6c-143">如果使用此选项，请确保 SNMP 应用程序与已发布的位置数据库记录之间的交换机端口标识符是一致的。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-143">If you use this option, make sure that the switch port identifiers are consistent between the SNMP application and the published location database records.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8ce6c-144">某些第三方 SNMP 解决方案可以支持非托管访问交换机;如果为 Skype for Business 客户端服务的交换机是非托管的，但具有到托管分发交换机的上行链接，则托管交换机可以将连接到访问交换机的客户端的 MAC 地址报告回 SNMP 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-144">Some third-party SNMP solutions can support unmanaged access switches; if the switch that services the Skype for Business client is unmanaged but has an uplink to a managed distribution switch, the managed switch can report back to the SNMP application the MAC addresses of the clients connected to the access switch.</span></span> <span data-ttu-id="8ce6c-145">利用此信息，位置信息服务可以标识用户的位置。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-145">This information enables the Location Information service to identify the location of the user.</span></span> <span data-ttu-id="8ce6c-146">但是，只能向非托管交换机上的所有端口分配单个 ERL，因此位置特性仅在访问交换机的机架级别而非端口级别可用。</span><span class="sxs-lookup"><span data-stu-id="8ce6c-146">However, it is possible to assign only a single ERL to all ports on the unmanaged switch, so the location specificity is available only at the chassis level of the access switch, not the port level.</span></span> 
  

