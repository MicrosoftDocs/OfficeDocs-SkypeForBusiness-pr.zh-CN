---
title: 管理 Business Server Skype SIP 中继服务提供商的位置
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: 所必需的规划决策位置信息数据库或类似的外部数据库中，对于业务 Server 企业语音的 Skype 中使用 SIP 中继提供商，E9-1-1 部署。
ms.openlocfilehash: 079e921debe9e5b61839795e61db199a018879aa
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20996772"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a><span data-ttu-id="84df8-103">管理 Business Server Skype SIP 中继服务提供商的位置</span><span class="sxs-lookup"><span data-stu-id="84df8-103">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>
 
<span data-ttu-id="84df8-104">所必需的规划决策位置信息数据库或类似的外部数据库中，对于业务 Server 企业语音的 Skype 中使用 SIP 中继提供商，E9-1-1 部署。</span><span class="sxs-lookup"><span data-stu-id="84df8-104">Decisions necessary for planning an the location information database, or a similar external database, for an E9-1-1 deployment using SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="84df8-105">若要配置的业务服务器可以自动定位网络内的客户端的 Skype，您需要填充用网络线路图位置信息服务数据库和发布位置，或链接到外部数据库已包含正确的映射。</span><span class="sxs-lookup"><span data-stu-id="84df8-105">To configure Skype for Business Server to automatically locate clients within a network, you need to either populate the Location Information service database with a network wiremap and publish the locations, or link to an external database that already contains the correct mappings.</span></span> <span data-ttu-id="84df8-106">作为此过程的一部分，您需要通过 E9-1-1 服务提供商来验证这些位置的城市地址。</span><span class="sxs-lookup"><span data-stu-id="84df8-106">As part of this process, you need to validate the civic addresses of the locations with your E9-1-1 service provider.</span></span> <span data-ttu-id="84df8-107">有关详细信息，请参阅部署文档中的[Configure the Location Database](http://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="84df8-107">For details, see [Configure the Location Database](http://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in the Deployment documentation.</span></span>
  
<span data-ttu-id="84df8-108">您可使用紧急响应位置 (ERL) 填充位置信息服务数据库，紧急响应位置由城市地址和建筑物内的特定地址构成。</span><span class="sxs-lookup"><span data-stu-id="84df8-108">You populate the Location Information service database with an Emergency Response Location (ERL), which consists of a civic address and the specific address within a building.</span></span> <span data-ttu-id="84df8-109">是大厦内的特定位置，该位置信息服务**位置**字段为最大长度为 20 个字符 （包括空格）。</span><span class="sxs-lookup"><span data-stu-id="84df8-109">The Location Information service **Location** field, which is the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="84df8-110">在该有限长度内，尽量包含以下内容：</span><span class="sxs-lookup"><span data-stu-id="84df8-110">Within that limited length, try to include the following:</span></span>
  
- <span data-ttu-id="84df8-p103">一个易于理解的名称，用于标识 911 呼叫者的位置，以帮助确保紧急响应者在到达该城市地址后迅速找到特定位置。此位置名称可能包括建筑物编号、楼层、建筑物标识、房间号等。应避免使用仅对员工可知的昵称，否则可能导致紧急响应者去往错误的位置。</span><span class="sxs-lookup"><span data-stu-id="84df8-p103">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames known only to employees, which might cause emergency responders to go to the wrong location.</span></span>
    
- <span data-ttu-id="84df8-114">帮助用户轻松查看的商业客户端选取的正确位置其 Skype 位置标识符。</span><span class="sxs-lookup"><span data-stu-id="84df8-114">A location identifier that helps users to easily see that their Skype for Business client picked up the correct location.</span></span> <span data-ttu-id="84df8-115">Skype 业务客户端自动连接和标头中显示发现的**位置**和**市/县**字段。</span><span class="sxs-lookup"><span data-stu-id="84df8-115">The Skype for Business client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="84df8-116">较好的做法是将构建的街道地址添加到每个位置标识符 (例如，"1st Floor <street number>")。</span><span class="sxs-lookup"><span data-stu-id="84df8-116">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor <street number>").</span></span> <span data-ttu-id="84df8-117">如果没有街道地址，可能对城市中的任何建筑物都应用常规位置标识符，如“1st Floor”。</span><span class="sxs-lookup"><span data-stu-id="84df8-117">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>
    
- <span data-ttu-id="84df8-118">如果位置是一个大概，因为它由无线访问点决定，您可以添加词 **[附近]** (例如，"Near 1st Floor 1234")。</span><span class="sxs-lookup"><span data-stu-id="84df8-118">If the location is approximate because it's determined by a wireless access point, you can add the word **[Near]** (for example, "Near 1st Floor 1234").</span></span>
    
> [!NOTE]
> <span data-ttu-id="84df8-119">使用业务 Server 命令行管理程序命令 Skype 发布和复制到该池的本地存储之前，位置添加到中心位置数据库不可用到客户端。</span><span class="sxs-lookup"><span data-stu-id="84df8-119">Locations added to the central location database are not available to the client until they are published by using a Skype for Business Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="84df8-120">有关详细信息，请参阅部署文档中的[发布位置数据库](http://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx)。</span><span class="sxs-lookup"><span data-stu-id="84df8-120">For details, see [Publishing the Location Database](http://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) in the Deployment documentation.</span></span>
  
<span data-ttu-id="84df8-121">以下各节讨论填充和维护位置数据库时需要考虑的注意事项。</span><span class="sxs-lookup"><span data-stu-id="84df8-121">The following sections discuss considerations that you need to take into account when populating and maintaining the location database.</span></span>
  
## <a name="populating-the-location-database"></a><span data-ttu-id="84df8-122">填充位置数据库</span><span class="sxs-lookup"><span data-stu-id="84df8-122">Populating the Location Database</span></span>

<span data-ttu-id="84df8-123">以下问题可帮助您确定如何填充位置数据库。</span><span class="sxs-lookup"><span data-stu-id="84df8-123">The following questions can help you determine how to populate the location database.</span></span>
  
 <span data-ttu-id="84df8-124">**使用什么过程填充位置数据库？**</span><span class="sxs-lookup"><span data-stu-id="84df8-124">**What process will you use to populate the location database?**</span></span>
  
<span data-ttu-id="84df8-p106">数据位于何处？需要采取何种步骤将数据转换为位置数据库所需的格式？是逐个添加位置，还是使用 CSV 文件批量添加？</span><span class="sxs-lookup"><span data-stu-id="84df8-p106">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span> 
  
 <span data-ttu-id="84df8-127">**是否有已包含位置映射的第三方数据库？**</span><span class="sxs-lookup"><span data-stu-id="84df8-127">**Do you have a third party database that already contains a mapping of locations?**</span></span>
  
<span data-ttu-id="84df8-128">通过使用辅助位置信息服务选项来连接到第三方数据库，您可以组和管理使用脱机平台的位置。</span><span class="sxs-lookup"><span data-stu-id="84df8-128">By using the Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="84df8-129">除了将位置与网络标识符关联外，此方法的优点还在于将位置与用户关联。</span><span class="sxs-lookup"><span data-stu-id="84df8-129">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="84df8-130">这意味着位置信息服务，可返回多个地址，来自业务客户端 Skype 到辅助位置信息服务。</span><span class="sxs-lookup"><span data-stu-id="84df8-130">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Skype for Business client.</span></span> <span data-ttu-id="84df8-131">然后，用户可以选择最适合的位置。</span><span class="sxs-lookup"><span data-stu-id="84df8-131">The user can then choose the most appropriate location.</span></span> 
  
<span data-ttu-id="84df8-132">若要将位置信息服务与相集成，第三方数据库必须执行的 Lync Server 位置请求/响应架构。</span><span class="sxs-lookup"><span data-stu-id="84df8-132">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="84df8-133">有关详细信息，请参阅["[MS E911WS]: E911 支持协议规范的 Web 服务"](https://go.microsoft.com/fwlink/p/?linkid=213819)。</span><span class="sxs-lookup"><span data-stu-id="84df8-133">For details, see  ["[MS-E911WS]: Web Service for E911 Support Protocol Specification"](https://go.microsoft.com/fwlink/p/?linkid=213819).</span></span> <span data-ttu-id="84df8-134">有关部署辅助位置信息服务的详细信息，请参阅部署文档中的[Configure Skype 业务服务器中的辅助位置信息服务](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md)。</span><span class="sxs-lookup"><span data-stu-id="84df8-134">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) in the Deployment documentation.</span></span>
  
<span data-ttu-id="84df8-135">有关填充位置数据库的详细信息，请参阅部署文档中的[Configure the Location Database](http://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="84df8-135">For details about populating the location database, see [Configure the Location Database](http://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in the Deployment documentation.</span></span>
  
## <a name="maintaining-the-location-database"></a><span data-ttu-id="84df8-136">维护位置数据库</span><span class="sxs-lookup"><span data-stu-id="84df8-136">Maintaining the Location Database</span></span>

<span data-ttu-id="84df8-p109">填充位置数据库之后，需要制定更新数据库的策略，因为网络配置发生了改变。以下问题将帮助您确定如何维护位置数据库。</span><span class="sxs-lookup"><span data-stu-id="84df8-p109">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>
  
 <span data-ttu-id="84df8-139">**如何更新位置数据库？**</span><span class="sxs-lookup"><span data-stu-id="84df8-139">**How will you update the location database?**</span></span>
  
<span data-ttu-id="84df8-p110">有许多情形需要更新位置数据库，包括添加 WAP、重新布置办公室缆线（需要不同的交换机分配）和子网扩展。是直接更新每个位置，还是使用 CSV 文件执行所有位置的批量更新？</span><span class="sxs-lookup"><span data-stu-id="84df8-p110">There are several scenarios that require an update to the location database, including adding WAPs, office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>
  
 <span data-ttu-id="84df8-142">**是否使用 SNMP 应用程序将 Lync 客户端 MAC 地址与端口和交换机标识符匹配？**</span><span class="sxs-lookup"><span data-stu-id="84df8-142">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>
  
<span data-ttu-id="84df8-143">如果使用 SNMP 应用程序，需要设计用于保持 SNMP 应用程序和位置数据库之间的交换机机架和端口信息一致的手动过程。</span><span class="sxs-lookup"><span data-stu-id="84df8-143">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="84df8-144">如果 SNMP 应用程序返回数据库中不包含机箱 IP 地址或端口 ID，位置信息服务不能以返回到客户端的位置。</span><span class="sxs-lookup"><span data-stu-id="84df8-144">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>
  

