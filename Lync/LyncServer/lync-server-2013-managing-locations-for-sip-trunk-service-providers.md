---
title: Lync Server 2013：管理 SIP 中继服务提供商的位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for SIP trunk service providers
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398959(v=OCS.15)
ms:contentKeyID: 48185548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8be19c6ca5aad78bc82487d8208fb163f62fbcb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a><span data-ttu-id="7a9ff-102">在 Lync Server 2013 中管理 SIP 中继服务提供商的位置</span><span class="sxs-lookup"><span data-stu-id="7a9ff-102">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a9ff-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="7a9ff-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="7a9ff-104">若要将 Lync Server 配置为自动在网络中查找客户端，您需要使用网络线路映射填充位置信息服务数据库并发布位置，或链接到已包含正确的外部数据库映射.</span><span class="sxs-lookup"><span data-stu-id="7a9ff-104">To configure Lync Server to automatically locate clients within a network, you need to either populate the Location Information service database with a network wiremap and publish the locations, or link to an external database that already contains the correct mappings.</span></span> <span data-ttu-id="7a9ff-105">作为此过程的一部分，您需要验证 E9-1-1 服务提供商的位置的市政地址。</span><span class="sxs-lookup"><span data-stu-id="7a9ff-105">As part of this process, you need to validate the civic addresses of the locations with your E9-1-1 service provider.</span></span> <span data-ttu-id="7a9ff-106">有关详细信息，请参阅部署文档中的在[Lync Server 2013 中配置位置数据库](lync-server-2013-configure-the-location-database.md)。</span><span class="sxs-lookup"><span data-stu-id="7a9ff-106">For details, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<span data-ttu-id="7a9ff-107">使用紧急响应位置（ERL）填充 Location 信息服务数据库，其中包含市政地址和建筑物内的特定地址。</span><span class="sxs-lookup"><span data-stu-id="7a9ff-107">You populate the Location Information service database with an Emergency Response Location (ERL), which consists of a civic address and the specific address within a building.</span></span> <span data-ttu-id="7a9ff-108">"位置信息服务**位置**" 字段是建筑物内的特定位置，最大长度为20个字符（包括空格）。</span><span class="sxs-lookup"><span data-stu-id="7a9ff-108">The Location Information service **Location** field, which is the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="7a9ff-109">在该有限的长度内，请尝试包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="7a9ff-109">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="7a9ff-p103">一个易于理解的、指示 911 呼叫者的位置的名称，以帮助确保紧急响应者到达市政地址后能够迅速找到具体位置。此位置名称可能包括楼号、楼层数、侧楼标识、房间号码等等。应避免使用仅员工知晓的昵称，这样可能导致紧急响应者找错位置。</span><span class="sxs-lookup"><span data-stu-id="7a9ff-p103">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="7a9ff-113">位置标识符，以帮助用户轻松了解他们的 Lync 客户端是否选择了正确的位置。</span><span class="sxs-lookup"><span data-stu-id="7a9ff-113">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="7a9ff-114">Lync 客户端自动连接并在其标头中显示发现的 **Location** 和 **City** 字段。</span><span class="sxs-lookup"><span data-stu-id="7a9ff-114">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="7a9ff-115">一种好的做法是将建筑物的街道地址添加到每个位置标识符（例如，"第一\<层街道\>号"）。</span><span class="sxs-lookup"><span data-stu-id="7a9ff-115">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="7a9ff-116">如果没有街道地址，那么通用的位置标识符（例如“1st Floor”）可以适用于城市中的所有建筑。</span><span class="sxs-lookup"><span data-stu-id="7a9ff-116">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="7a9ff-117">如果该位置是近似值，因为它是由无线访问点确定的，则可以将该单词添加到附近（例如，"靠近第一层 1234"）。</span><span class="sxs-lookup"><span data-stu-id="7a9ff-117">If the location is approximate because it’s determined by a wireless access point, you can add the word Near (for example, "Near 1st Floor 1234").</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a9ff-118">在使用 Lync Server 命令行管理程序命令发布添加到中心位置数据库的位置，并将这些位置复制到池的本地存储区之前，这些位置将不可用于客户端。</span><span class="sxs-lookup"><span data-stu-id="7a9ff-118">Locations added to the central location database are not available to the client until they are published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="7a9ff-119">有关详细信息，请参阅部署文档中的<A href="lync-server-2013-publish-the-location-database.md">从 Lync Server 2013 发布位置数据库</A>。</span><span class="sxs-lookup"><span data-stu-id="7a9ff-119">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="7a9ff-120">以下各节讨论在填充和维护位置数据库时需要考虑的注意事项。</span><span class="sxs-lookup"><span data-stu-id="7a9ff-120">The following sections discuss considerations that you need to take into account when populating and maintaining the location database.</span></span>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="7a9ff-121">填充位置数据库</span><span class="sxs-lookup"><span data-stu-id="7a9ff-121">Populating the Location Database</span></span>

<span data-ttu-id="7a9ff-122">以下问题可帮助您确定如何填充位置数据库。</span><span class="sxs-lookup"><span data-stu-id="7a9ff-122">The following questions can help you determine how to populate the location database.</span></span>

  - <span data-ttu-id="7a9ff-123">**使用什么过程填充位置数据库？**</span><span class="sxs-lookup"><span data-stu-id="7a9ff-123">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="7a9ff-p106">数据位于何处？采取何种步骤将数据转换为位置数据库所需的格式？是逐个添加位置，还是使用 CSV 文件批量添加？</span><span class="sxs-lookup"><span data-stu-id="7a9ff-p106">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="7a9ff-126">**是否具有已包含位置映射的第三方数据库？**</span><span class="sxs-lookup"><span data-stu-id="7a9ff-126">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="7a9ff-127">通过使用 Lync Server 的辅助位置信息服务选项连接到第三方数据库，可以使用脱机平台对位置进行分组和管理。</span><span class="sxs-lookup"><span data-stu-id="7a9ff-127">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="7a9ff-128">此方案的优势在于除了将位置与网络标识符关联外，还可以将位置与用户关联。</span><span class="sxs-lookup"><span data-stu-id="7a9ff-128">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="7a9ff-129">这意味着 Location 信息服务可将来自辅助位置信息服务的多个地址返回到 Lync Server 客户端。</span><span class="sxs-lookup"><span data-stu-id="7a9ff-129">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="7a9ff-130">然后用户可以选择最合适的位置。</span><span class="sxs-lookup"><span data-stu-id="7a9ff-130">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="7a9ff-131">若要与 Location 信息服务集成，第三方数据库必须遵循 Lync Server 位置请求/响应架构。</span><span class="sxs-lookup"><span data-stu-id="7a9ff-131">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="7a9ff-132">有关详细信息，请\[参阅中的\]"MS-Ms-e911ws： E911 的 Web 服务支持<https://go.microsoft.com/fwlink/p/?linkid=213819>协议规范"。</span><span class="sxs-lookup"><span data-stu-id="7a9ff-132">For details, see "\[MS-E911WS\]: Web Service for E911 Support Protocol Specification" at <https://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="7a9ff-133">有关部署辅助位置信息服务的详细信息，请参阅部署文档中的在[Lync Server 2013 中配置辅助位置信息服务](lync-server-2013-configure-a-secondary-location-information-service.md)。</span><span class="sxs-lookup"><span data-stu-id="7a9ff-133">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="7a9ff-134">有关填充位置数据库的详细信息，请参阅部署文档中的在[Lync Server 2013 中配置位置数据库](lync-server-2013-configure-the-location-database.md)。</span><span class="sxs-lookup"><span data-stu-id="7a9ff-134">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="7a9ff-135">维护位置数据库</span><span class="sxs-lookup"><span data-stu-id="7a9ff-135">Maintaining the Location Database</span></span>

<span data-ttu-id="7a9ff-p109">填充位置数据库之后，需要制定更新数据库的策略，因为网络配置发生了改变。以下问题将帮助您确定如何维护位置数据库。</span><span class="sxs-lookup"><span data-stu-id="7a9ff-p109">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="7a9ff-138">**如何更新位置数据库？**</span><span class="sxs-lookup"><span data-stu-id="7a9ff-138">**How will you update the location database?**</span></span>  
    <span data-ttu-id="7a9ff-139">有几种情况需要更新位置数据库，包括添加 Wap、office 缆线（导致不同的交换机分配）和子网扩展。</span><span class="sxs-lookup"><span data-stu-id="7a9ff-139">There are several scenarios that require an update to the location database, including adding WAPs, office recabling (resulting in different switch assignments), and subnet expansion.</span></span> <span data-ttu-id="7a9ff-140">是直接更新各个位置，还是使用 CSV 文件执行所有位置的批量更新？</span><span class="sxs-lookup"><span data-stu-id="7a9ff-140">Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="7a9ff-141">**是否使用 SNMP 应用程序将 Lync 客户端 MAC 地址与端口和交换机标识符进行匹配？**</span><span class="sxs-lookup"><span data-stu-id="7a9ff-141">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="7a9ff-142">如果使用 SNMP 应用程序，需要设计用于保持 SNMP 应用程序和位置数据库之间的交换机机架和端口信息一致的手动过程。</span><span class="sxs-lookup"><span data-stu-id="7a9ff-142">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="7a9ff-143">如果 SNMP 应用程序返回的是未包含在数据库中的机箱 IP 地址或端口 ID，则位置信息服务将无法向客户端返回一个位置。</span><span class="sxs-lookup"><span data-stu-id="7a9ff-143">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

