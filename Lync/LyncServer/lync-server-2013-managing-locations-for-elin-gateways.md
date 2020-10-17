---
title: Lync Server 2013：管理 ELIN 网关的位置
description: Lync Server 2013：管理 ELIN 网关的位置。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for ELIN gateways
ms:assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205288(v=OCS.15)
ms:contentKeyID: 48185496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94fe7797c0f25adb219512cef4a6c0fb7d84b48d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557478"
---
# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a><span data-ttu-id="8c535-103">在 Lync Server 2013 中管理 ELIN 网关的位置</span><span class="sxs-lookup"><span data-stu-id="8c535-103">Managing locations for ELIN gateways in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c535-104">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="8c535-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="8c535-105">若要让 Lync Server 自动为网络中的客户端提供位置，您需要执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="8c535-105">To have Lync Server automatically provide locations for clients within a network, you need to perform the following tasks:</span></span>

  - <span data-ttu-id="8c535-106">使用网络线路映射填充 Location 信息服务数据库，并在 "公司名称" 字段中 (Elin) 中添加紧急位置标识号。</span><span class="sxs-lookup"><span data-stu-id="8c535-106">Populate the Location Information service database with a network wiremap, and include the Emergency Location Identification Numbers (ELINs) in the CompanyName field.</span></span>

  - <span data-ttu-id="8c535-107">发布位置，以供网络中的客户端使用。</span><span class="sxs-lookup"><span data-stu-id="8c535-107">Publish the locations so that they are available for clients in your network.</span></span>

  - <span data-ttu-id="8c535-108">将 ELIN 上载到公用电话交换网 (PSTN) 运营商的自动位置标识 (ALI) 数据库。</span><span class="sxs-lookup"><span data-stu-id="8c535-108">Upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="8c535-109">有关如何执行这些任务的详细信息，请参阅部署文档中的在 [Lync Server 2013 中配置位置数据库](lync-server-2013-configure-the-location-database.md) 。</span><span class="sxs-lookup"><span data-stu-id="8c535-109">For details about how to perform these tasks, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8c535-110">在使用 Lync Server 命令行管理程序命令发布并复制到池的本地存储区中之前，添加到中心位置数据库的位置对客户端不可用。</span><span class="sxs-lookup"><span data-stu-id="8c535-110">Locations added to the central location database are not available to the client until they have been published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="8c535-111">有关详细信息，请参阅部署文档中的 <A href="lync-server-2013-publish-the-location-database.md">从 Lync Server 2013 发布位置数据库</A> 。</span><span class="sxs-lookup"><span data-stu-id="8c535-111">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="8c535-112">此部分介绍在您计划更新和维护位置数据库时应考虑的事项。</span><span class="sxs-lookup"><span data-stu-id="8c535-112">This section describes things to consider as you plan to update and maintain the location database.</span></span>

<div>

## <a name="planning-emergency-locations"></a><span data-ttu-id="8c535-113">规划紧急位置</span><span class="sxs-lookup"><span data-stu-id="8c535-113">Planning Emergency Locations</span></span>

<span data-ttu-id="8c535-114">使用 ELIN 网关时，将使用市政地址、大楼内的特定位置和每个位置至少一个 ELIN 填充位置信息服务数据库。</span><span class="sxs-lookup"><span data-stu-id="8c535-114">When you use ELIN gateways, you populate the Location Information service database with the civic address, a specific location within a building, and at least one ELIN for each location .</span></span> <span data-ttu-id="8c535-115">在规划阶段，最好确定您希望如何命名位置以及如何分配 ELIN。</span><span class="sxs-lookup"><span data-stu-id="8c535-115">During the planning phase, it is a good idea to decide how you want to name the locations and how you want to assign ELINs.</span></span>

<div>

## <a name="planning-location-names"></a><span data-ttu-id="8c535-116">规划位置名称</span><span class="sxs-lookup"><span data-stu-id="8c535-116">Planning Location Names</span></span>

<span data-ttu-id="8c535-117">"位置信息服务 **位置** " 字段用于存放建筑物内的特定位置，最大长度为20个字符 (包括空格) 。</span><span class="sxs-lookup"><span data-stu-id="8c535-117">The Location Information service **Location** field, which holds the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="8c535-118">在该限制长度内，尽量包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="8c535-118">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="8c535-p104">一个容易理解的名称，用于标识 911 呼叫者的位置，以确保紧急响应者在到达市政地址后能迅速找到具体位置。此位置名称可包含建筑物编号、楼层、建筑物标识、房间号等。应避免使用仅对员工可知的昵称，以防紧急响应者去往错误的位置。</span><span class="sxs-lookup"><span data-stu-id="8c535-p104">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames that are known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="8c535-122">位置标识符，以帮助用户轻松了解他们的 Lync 客户端是否选择了正确的位置。</span><span class="sxs-lookup"><span data-stu-id="8c535-122">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="8c535-123">Lync 客户端自动连接并在其标头中显示发现的 **Location** 和 **City** 字段。</span><span class="sxs-lookup"><span data-stu-id="8c535-123">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="8c535-124">一种好的做法是将建筑物的街道地址添加到每个位置标识符 (例如，"第一层 \<street number\> " ) 。</span><span class="sxs-lookup"><span data-stu-id="8c535-124">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="8c535-125">如果没有街道地址，那么通用的位置标识符（例如“1st Floor”）可以适用于城市中的所有建筑。</span><span class="sxs-lookup"><span data-stu-id="8c535-125">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="8c535-126">如果位置是由无线访问点确定的，则它可能不精确，此时可能需要添加词语 Near（例如，“Near 1st Floor 1234”）。</span><span class="sxs-lookup"><span data-stu-id="8c535-126">If the location is approximate because it’s determined by a wireless access point, you may want to add the word Near (for example, "Near 1st Floor 1234").</span></span>

</div>

<div>

## <a name="planning-elins"></a><span data-ttu-id="8c535-127">规划 ELIN</span><span class="sxs-lookup"><span data-stu-id="8c535-127">Planning ELINs</span></span>

<span data-ttu-id="8c535-p106">在您决定想要如何将建筑物空间分成多个位置后，需要决定为每个位置分配多少个 ELIN。例如，在多层或多租户建筑物中，可以为建筑物中不同的区域分配不同的紧急区域。通常，建筑物的每层都会被指定为一个位置。每个位置会被分配一个或多个 ELIN，这些 ELIN 用作紧急呼叫时的呼叫号码。请联系您的 PSTN 运营商以获得可用于 ELIN 的电话号码。下表提供了特定街道地址的位置示例。</span><span class="sxs-lookup"><span data-stu-id="8c535-p106">After you decide how you want to divide your building space into locations, you need to decide how many ELINs to assign to each location. For example, in a multifloor or multitenant building, different areas in the building can be assigned different emergency zones. Typically, each floor in a building is designated as a location. Each location is then assigned one or more ELINs, which are used as the calling number(s) during an emergency call. Contact your PSTN carrier for phone numbers that you can use for ELINs. The following table provides an example of locations for a specific street address.</span></span>

### <a name="sample-location-and-elin-assignments"></a><span data-ttu-id="8c535-134">位置和 ELIN 分配示例</span><span class="sxs-lookup"><span data-stu-id="8c535-134">Sample Location and ELIN Assignments</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c535-135">建筑物区域</span><span class="sxs-lookup"><span data-stu-id="8c535-135">Building Area</span></span></th>
<th><span data-ttu-id="8c535-136">位置</span><span class="sxs-lookup"><span data-stu-id="8c535-136">Location</span></span></th>
<th><span data-ttu-id="8c535-137">ELIN</span><span class="sxs-lookup"><span data-stu-id="8c535-137">ELIN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c535-138">第 1 层</span><span class="sxs-lookup"><span data-stu-id="8c535-138">First floor</span></span></p></td>
<td><p><span data-ttu-id="8c535-139">1</span><span class="sxs-lookup"><span data-stu-id="8c535-139">1</span></span></p></td>
<td><p><span data-ttu-id="8c535-140">425-555-0100</span><span class="sxs-lookup"><span data-stu-id="8c535-140">425-555-0100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c535-141">第 2 层</span><span class="sxs-lookup"><span data-stu-id="8c535-141">Second floor</span></span></p></td>
<td><p><span data-ttu-id="8c535-142">双面</span><span class="sxs-lookup"><span data-stu-id="8c535-142">2</span></span></p></td>
<td><p><span data-ttu-id="8c535-143">425-555-0111</span><span class="sxs-lookup"><span data-stu-id="8c535-143">425-555-0111</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c535-144">第 3 层</span><span class="sxs-lookup"><span data-stu-id="8c535-144">Third floor</span></span></p></td>
<td><p><span data-ttu-id="8c535-145">第三章</span><span class="sxs-lookup"><span data-stu-id="8c535-145">3</span></span></p></td>
<td><p><span data-ttu-id="8c535-146">425-555-0123</span><span class="sxs-lookup"><span data-stu-id="8c535-146">425-555-0123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8c535-147">您定义的位置应满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="8c535-147">The locations you define should meet the following requirements:</span></span>

  - <span data-ttu-id="8c535-148">在每位置最大区域和每街道地址位置数方面符合当地和国家/地区法规。</span><span class="sxs-lookup"><span data-stu-id="8c535-148">Comply with local and national/regional regulations in terms of maximum area per location and number of locations per street address.</span></span>

  - <span data-ttu-id="8c535-149">足够详细到能够轻松找到紧急呼叫者。</span><span class="sxs-lookup"><span data-stu-id="8c535-149">Are specific enough to make it easy to locate the emergency caller.</span></span>

</div>

</div>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="8c535-150">填充位置数据库</span><span class="sxs-lookup"><span data-stu-id="8c535-150">Populating the Location Database</span></span>

<span data-ttu-id="8c535-151">以下问题将帮助您确定如何填充位置数据库。</span><span class="sxs-lookup"><span data-stu-id="8c535-151">The following questions will help you determine how to will populate the location database.</span></span>

  - <span data-ttu-id="8c535-152">**使用什么过程填充位置数据库？**</span><span class="sxs-lookup"><span data-stu-id="8c535-152">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="8c535-p107">数据位于何处？采取何种步骤将数据转换为位置数据库所需的格式？是逐个添加位置，还是使用 CSV 文件批量添加？</span><span class="sxs-lookup"><span data-stu-id="8c535-p107">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="8c535-155">**是否具有已包含位置映射的第三方数据库？**</span><span class="sxs-lookup"><span data-stu-id="8c535-155">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="8c535-156">通过使用 Lync Server 的辅助位置信息服务选项连接到第三方数据库，可以使用脱机平台对位置进行分组和管理。</span><span class="sxs-lookup"><span data-stu-id="8c535-156">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="8c535-157">此方案的优势在于除了将位置与网络标识符关联外，还可以将位置与用户关联。</span><span class="sxs-lookup"><span data-stu-id="8c535-157">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="8c535-158">这意味着 Location 信息服务可将来自辅助位置信息服务的多个地址返回到 Lync Server 客户端。</span><span class="sxs-lookup"><span data-stu-id="8c535-158">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="8c535-159">然后用户可以选择最合适的位置。</span><span class="sxs-lookup"><span data-stu-id="8c535-159">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="8c535-160">若要与 Location 信息服务集成，第三方数据库必须遵循 Lync Server 位置请求/响应架构。</span><span class="sxs-lookup"><span data-stu-id="8c535-160">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="8c535-161">有关详细信息，请参阅 <https://go.microsoft.com/fwlink/p/?linkid=213819> 。</span><span class="sxs-lookup"><span data-stu-id="8c535-161">For details, see <https://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="8c535-162">有关部署辅助位置信息服务的详细信息，请参阅部署文档中的在 [Lync Server 2013 中配置辅助位置信息服务](lync-server-2013-configure-a-secondary-location-information-service.md) 。</span><span class="sxs-lookup"><span data-stu-id="8c535-162">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="8c535-163">有关填充位置数据库的详细信息，请参阅部署文档中的在 [Lync Server 2013 中配置位置数据库](lync-server-2013-configure-the-location-database.md) 。</span><span class="sxs-lookup"><span data-stu-id="8c535-163">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="8c535-164">维护位置数据库</span><span class="sxs-lookup"><span data-stu-id="8c535-164">Maintaining the Location Database</span></span>

<span data-ttu-id="8c535-p110">填充位置数据库之后，需要制定更新数据库的策略，因为网络配置发生了改变。以下问题将帮助您确定如何维护位置数据库。</span><span class="sxs-lookup"><span data-stu-id="8c535-p110">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="8c535-167">**如何更新位置数据库？**</span><span class="sxs-lookup"><span data-stu-id="8c535-167">**How will you update the location database?**</span></span>  
    <span data-ttu-id="8c535-p111">有许多方案需要更新位置数据，包括添加无线接入点 (WAP)、重新布置办公室缆线（需要不同的交换机分配）和子网扩展。是直接更新每个位置，还是使用 CSV 文件执行所有位置的批量更新？</span><span class="sxs-lookup"><span data-stu-id="8c535-p111">There are several scenarios that require an update to the location database, including adding wireless access points (WAPs), office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="8c535-170">**是否使用 SNMP 应用程序将 Lync 客户端 MAC 地址与端口和交换机标识符匹配？**</span><span class="sxs-lookup"><span data-stu-id="8c535-170">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="8c535-171">如果使用 SNMP 应用程序，需要设计用于保持 SNMP 应用程序和位置数据库之间的交换机机架和端口信息一致的手动过程。</span><span class="sxs-lookup"><span data-stu-id="8c535-171">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="8c535-172">如果 SNMP 应用程序返回的是未包含在数据库中的机箱 IP 地址或端口 ID，则位置信息服务将无法向客户端返回一个位置。</span><span class="sxs-lookup"><span data-stu-id="8c535-172">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

