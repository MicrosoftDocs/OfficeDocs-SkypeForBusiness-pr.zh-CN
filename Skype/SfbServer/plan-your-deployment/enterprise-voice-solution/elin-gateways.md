---
title: 在 Skype for Business Server 2015 中管理 ELIN 网关的位置
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/17/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
description: 所必需的规划决策位置信息数据库或类似的外部数据库中，E9-1-1 部署中的业务 Server 企业语音的 Skype 使用 ELIN 网关。
ms.openlocfilehash: c89f09af2011d316485094f9fc817580b56d1d81
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="manage-locations-for-elin-gateways-in-skype-for-business-server-2015"></a><span data-ttu-id="e2dda-103">在 Skype for Business Server 2015 中管理 ELIN 网关的位置</span><span class="sxs-lookup"><span data-stu-id="e2dda-103">Manage locations for ELIN gateways in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e2dda-104">所必需的规划决策位置信息数据库或类似的外部数据库中，E9-1-1 部署中的业务 Server 企业语音的 Skype 使用 ELIN 网关。</span><span class="sxs-lookup"><span data-stu-id="e2dda-104">Decisions necessary for planning an the location information database, or a similar external database, for an E9-1-1 deployment using ELIN gateways, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="e2dda-105">要让 Skype 业务服务器自动提供网络内的客户端的位置，您需要执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="e2dda-105">To have Skype for Business Server automatically provide locations for clients within a network, you need to perform the following tasks:</span></span> 
  
- <span data-ttu-id="e2dda-106">填充用网络线路图，位置信息服务数据库并在 CompanyName 字段中包括紧急位置标识号 (Elin)。</span><span class="sxs-lookup"><span data-stu-id="e2dda-106">Populate the Location Information service database with a network wiremap, and include the Emergency Location Identification Numbers (ELINs) in the CompanyName field.</span></span>
    
- <span data-ttu-id="e2dda-107">发布位置，以供网络中的客户端使用。</span><span class="sxs-lookup"><span data-stu-id="e2dda-107">Publish the locations so that they are available for clients in your network.</span></span>
    
- <span data-ttu-id="e2dda-108">将 ELIN 上载到公用电话交换网 (PSTN) 运营商的自动位置标识 (ALI) 数据库。</span><span class="sxs-lookup"><span data-stu-id="e2dda-108">Upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span>
    
<span data-ttu-id="e2dda-109">有关如何执行这些任务的详细信息，请参阅部署文档中的[Configure the Location Database](http://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="e2dda-109">For details about how to perform these tasks, see [Configure the Location Database](http://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in the Deployment documentation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e2dda-110">已发布业务 Server 命令行管理程序命令使用 Skype 和复制到该池的本地存储之前，位置添加到中心位置数据库不可用到客户端。</span><span class="sxs-lookup"><span data-stu-id="e2dda-110">Locations added to the central location database are not available to the client until they have been published by using a Skype for Business Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="e2dda-111">有关详细信息，请参阅部署文档中的[发布位置数据库](http://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e2dda-111">For details, see [Publishing the Location Database](http://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) in the Deployment documentation.</span></span>
  
<span data-ttu-id="e2dda-112">本节介绍在计划更新和维护位置数据库时要考虑的事项。</span><span class="sxs-lookup"><span data-stu-id="e2dda-112">This section describes things to consider as you plan to update and maintain the location database.</span></span>
  
## <a name="planning-emergency-locations"></a><span data-ttu-id="e2dda-113">规划紧急位置</span><span class="sxs-lookup"><span data-stu-id="e2dda-113">Planning Emergency Locations</span></span>

<span data-ttu-id="e2dda-114">使用 ELIN 网关时，您将填充的市政地址、 大厦内的特定位置与每个位置的至少一个 ELIN 位置信息服务数据库。</span><span class="sxs-lookup"><span data-stu-id="e2dda-114">When you use ELIN gateways, you populate the Location Information service database with the civic address, a specific location within a building, and at least one ELIN for each location .</span></span> <span data-ttu-id="e2dda-115">在规划阶段，最好决定想要如何命名位置和分配 ELIN。</span><span class="sxs-lookup"><span data-stu-id="e2dda-115">During the planning phase, it is a good idea to decide how you want to name the locations and how you want to assign ELINs.</span></span>
  
### <a name="planning-location-names"></a><span data-ttu-id="e2dda-116">规划位置名称</span><span class="sxs-lookup"><span data-stu-id="e2dda-116">Planning Location Names</span></span>

<span data-ttu-id="e2dda-117">保留大厦内的特定位置，该位置信息服务**位置**字段为最大长度为 20 个字符 （包括空格）。</span><span class="sxs-lookup"><span data-stu-id="e2dda-117">The Location Information service **Location** field, which holds the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="e2dda-118">在该限制长度内，尽量包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="e2dda-118">Within that limited length, try to include the following:</span></span>
  
- <span data-ttu-id="e2dda-p104">一个容易理解的名称，用于标识 911 呼叫者的位置，以确保紧急响应者在到达市政地址后能迅速找到具体位置。此位置名称可包含建筑物编号、楼层、建筑物标识、房间号等。应避免使用仅对员工可知的昵称，以防紧急响应者去往错误的位置。</span><span class="sxs-lookup"><span data-stu-id="e2dda-p104">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames that are known only to employees, which might cause emergency responders to go to the wrong location.</span></span>
    
- <span data-ttu-id="e2dda-122">一个位置标识符，帮助用户轻松判断其客户端已选择正确位置。</span><span class="sxs-lookup"><span data-stu-id="e2dda-122">A location identifier that helps users to easily see that their client picked up the correct location.</span></span> <span data-ttu-id="e2dda-123">Skype 业务客户端自动连接和标头中显示发现的**位置**和**市/县**字段。</span><span class="sxs-lookup"><span data-stu-id="e2dda-123">The Skype for Business client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="e2dda-124">较好的做法是将构建的街道地址添加到每个位置标识符 (例如，"1st Floor <street number>")。</span><span class="sxs-lookup"><span data-stu-id="e2dda-124">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor <street number>").</span></span> <span data-ttu-id="e2dda-125">如果没有街道地址，可能对城市中的任何建筑物都应用常规位置标识符，如“1st Floor”。</span><span class="sxs-lookup"><span data-stu-id="e2dda-125">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>
    
- <span data-ttu-id="e2dda-126">如果位置是一个大概，因为它由无线访问点决定，您可能想要添加词 **[附近]** (例如，"Near 1st Floor 1234")。</span><span class="sxs-lookup"><span data-stu-id="e2dda-126">If the location is approximate because it's determined by a wireless access point, you may want to add the word **[Near]** (for example, "Near 1st Floor 1234").</span></span>
    
### <a name="planning-elins"></a><span data-ttu-id="e2dda-127">规划 ELIN</span><span class="sxs-lookup"><span data-stu-id="e2dda-127">Planning ELINs</span></span>

<span data-ttu-id="e2dda-p106">在您决定想要如何将建筑物空间分成多个位置后，需要决定为每个位置分配多少个 ELIN。例如，在多层或多租户建筑物中，可以为建筑物中不同的区域分配不同的紧急区域。通常，建筑物的每层都会被指定为一个位置。每个位置会被分配一个或多个 ELIN，这些 ELIN 用作紧急呼叫时的呼叫号码。请联系您的 PSTN 运营商以获得可用于 ELIN 的电话号码。下表提供了特定街道地址的位置示例。</span><span class="sxs-lookup"><span data-stu-id="e2dda-p106">After you decide how you want to divide your building space into locations, you need to decide how many ELINs to assign to each location. For example, in a multifloor or multitenant building, different areas in the building can be assigned different emergency zones. Typically, each floor in a building is designated as a location. Each location is then assigned one or more ELINs, which are used as the calling number(s) during an emergency call. Contact your PSTN carrier for phone numbers that you can use for ELINs. The following table provides an example of locations for a specific street address.</span></span>
  
<span data-ttu-id="e2dda-134">**示例位置和 ELIN 分配**</span><span class="sxs-lookup"><span data-stu-id="e2dda-134">**Sample Location and ELIN Assignments**</span></span>

|<span data-ttu-id="e2dda-135">**建筑物区域**</span><span class="sxs-lookup"><span data-stu-id="e2dda-135">**Building Area**</span></span>|<span data-ttu-id="e2dda-136">**位置**</span><span class="sxs-lookup"><span data-stu-id="e2dda-136">**Location**</span></span>|<span data-ttu-id="e2dda-137">**ELIN**</span><span class="sxs-lookup"><span data-stu-id="e2dda-137">**ELIN**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e2dda-138">第一层</span><span class="sxs-lookup"><span data-stu-id="e2dda-138">First floor</span></span>  <br/> |<span data-ttu-id="e2dda-139">1</span><span class="sxs-lookup"><span data-stu-id="e2dda-139">1</span></span>  <br/> |<span data-ttu-id="e2dda-140">425-555-0100</span><span class="sxs-lookup"><span data-stu-id="e2dda-140">425-555-0100</span></span>  <br/> |
|<span data-ttu-id="e2dda-141">第二层</span><span class="sxs-lookup"><span data-stu-id="e2dda-141">Second floor</span></span>  <br/> |<span data-ttu-id="e2dda-142">2</span><span class="sxs-lookup"><span data-stu-id="e2dda-142">2</span></span>  <br/> |<span data-ttu-id="e2dda-143">425-555-0111</span><span class="sxs-lookup"><span data-stu-id="e2dda-143">425-555-0111</span></span>  <br/> |
|<span data-ttu-id="e2dda-144">第三层</span><span class="sxs-lookup"><span data-stu-id="e2dda-144">Third floor</span></span>  <br/> |<span data-ttu-id="e2dda-145">3</span><span class="sxs-lookup"><span data-stu-id="e2dda-145">3</span></span>  <br/> |<span data-ttu-id="e2dda-146">425-555-0123</span><span class="sxs-lookup"><span data-stu-id="e2dda-146">425-555-0123</span></span>  <br/> |
   
<span data-ttu-id="e2dda-147">您定义的位置应满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="e2dda-147">The locations you define should meet the following requirements:</span></span>
  
- <span data-ttu-id="e2dda-148">在每位置最大区域和每街道地址位置数方面符合当地和国家/地区法规。</span><span class="sxs-lookup"><span data-stu-id="e2dda-148">Comply with local and national/regional regulations in terms of maximum area per location and number of locations per street address.</span></span>
    
- <span data-ttu-id="e2dda-149">足够详细到能够轻松找到紧急呼叫者。</span><span class="sxs-lookup"><span data-stu-id="e2dda-149">Are specific enough to make it easy to locate the emergency caller.</span></span>
    
## <a name="populating-the-location-database"></a><span data-ttu-id="e2dda-150">填充位置数据库</span><span class="sxs-lookup"><span data-stu-id="e2dda-150">Populating the Location Database</span></span>

<span data-ttu-id="e2dda-151">以下问题将帮助您确定如何填充位置数据库。</span><span class="sxs-lookup"><span data-stu-id="e2dda-151">The following questions will help you determine how to will populate the location database.</span></span>
  
 <span data-ttu-id="e2dda-152">**使用什么过程填充位置数据库？**</span><span class="sxs-lookup"><span data-stu-id="e2dda-152">**What process will you use to populate the location database?**</span></span>
  
<span data-ttu-id="e2dda-p107">数据位于何处？需要采取何种步骤将数据转换为位置数据库所需的格式？是逐个添加位置，还是使用 CSV 文件批量添加？</span><span class="sxs-lookup"><span data-stu-id="e2dda-p107">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>
  
 <span data-ttu-id="e2dda-155">**是否有已包含位置映射的第三方数据库？**</span><span class="sxs-lookup"><span data-stu-id="e2dda-155">**Do you have a third party database that already contains a mapping of locations?**</span></span>
  
<span data-ttu-id="e2dda-156">通过使用辅助位置信息服务选项来连接到第三方数据库，您可以组和管理使用脱机平台的位置。</span><span class="sxs-lookup"><span data-stu-id="e2dda-156">By using the Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="e2dda-157">除了将位置与网络标识符关联外，此方法的优点还在于将位置与用户关联。</span><span class="sxs-lookup"><span data-stu-id="e2dda-157">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="e2dda-158">这意味着位置信息服务，可返回多个地址，来自业务客户端 Skype 到辅助位置信息服务。</span><span class="sxs-lookup"><span data-stu-id="e2dda-158">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Skype for Business client.</span></span> <span data-ttu-id="e2dda-159">然后，用户可以选择最适合的位置。</span><span class="sxs-lookup"><span data-stu-id="e2dda-159">The user can then choose the most appropriate location.</span></span> 
  
<span data-ttu-id="e2dda-160">若要将位置信息服务与相集成，第三方数据库必须执行业务服务器位置请求/响应架构 Skype。</span><span class="sxs-lookup"><span data-stu-id="e2dda-160">To integrate with the Location Information service, the third-party database must follow the Skype for Business Server Location Request/Response schema.</span></span> <span data-ttu-id="e2dda-161">有关详细信息，请参阅[E911 支持协议的 Web 服务](https://go.microsoft.com/fwlink/p/?linkid=213819)。</span><span class="sxs-lookup"><span data-stu-id="e2dda-161">For details, see [Web Service for E911 Support Protocol](https://go.microsoft.com/fwlink/p/?linkid=213819).</span></span> <span data-ttu-id="e2dda-162">有关部署辅助位置信息服务的详细信息，请参阅部署文档中的[配置中的业务服务器 2015 Skype 的辅助位置信息服务](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md)。</span><span class="sxs-lookup"><span data-stu-id="e2dda-162">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) in the Deployment documentation.</span></span>
  
<span data-ttu-id="e2dda-163">有关填充位置数据库的详细信息，请参阅部署文档中的[Configure the Location Database](http://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="e2dda-163">For details about populating the location database, see [Configure the Location Database](http://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in the Deployment documentation.</span></span>
  
## <a name="maintaining-the-location-database"></a><span data-ttu-id="e2dda-164">维护位置数据库</span><span class="sxs-lookup"><span data-stu-id="e2dda-164">Maintaining the Location Database</span></span>

<span data-ttu-id="e2dda-p110">填充位置数据库之后，需要制定更新数据库的策略，因为网络配置发生了改变。以下问题将帮助您确定如何维护位置数据库。</span><span class="sxs-lookup"><span data-stu-id="e2dda-p110">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>
  
 <span data-ttu-id="e2dda-167">**如何更新位置数据库？**</span><span class="sxs-lookup"><span data-stu-id="e2dda-167">**How will you update the location database?**</span></span>
  
<span data-ttu-id="e2dda-p111">有许多方案需要更新位置数据，包括添加无线接入点 (WAP)、重新布置办公室缆线（需要不同的交换机分配）和子网扩展。是直接更新每个位置，还是使用 CSV 文件执行所有位置的批量更新？</span><span class="sxs-lookup"><span data-stu-id="e2dda-p111">There are several scenarios that require an update to the location database, including adding wireless access points (WAPs), office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>
  
 <span data-ttu-id="e2dda-170">**是否使用 SNMP 应用程序以匹配 Skype 业务客户端 MAC 地址与端口和交换机标识符？**</span><span class="sxs-lookup"><span data-stu-id="e2dda-170">**Will you use an SNMP application to match Skype for Business client MAC addresses to port and switch identifiers?**</span></span>
  
<span data-ttu-id="e2dda-171">如果使用 SNMP 应用程序，需要设计用于保持 SNMP 应用程序和位置数据库之间的交换机机架和端口信息一致的手动过程。</span><span class="sxs-lookup"><span data-stu-id="e2dda-171">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="e2dda-172">如果 SNMP 应用程序返回数据库中不包含机箱 IP 地址或端口 ID，位置信息服务不能以返回到客户端的位置。</span><span class="sxs-lookup"><span data-stu-id="e2dda-172">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>
  

