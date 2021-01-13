---
title: 在 Skype for Business Server 中管理 SIP 中继服务提供商的位置
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
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: 在 Skype for Business Server 企业语音 中，为使用 SIP 中继提供程序规划 E9-1-1 部署的位置信息数据库或类似外部数据库企业语音。
ms.openlocfilehash: 9918fc2cb6bc9d05166d648ab3285a964d15f290
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825432"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a><span data-ttu-id="e0458-103">在 Skype for Business Server 中管理 SIP 中继服务提供商的位置</span><span class="sxs-lookup"><span data-stu-id="e0458-103">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>

<span data-ttu-id="e0458-104">在 Skype for Business Server 企业语音 中，为使用 SIP 中继提供程序规划 E9-1-1 部署的位置信息数据库或类似外部数据库企业语音。</span><span class="sxs-lookup"><span data-stu-id="e0458-104">Decisions necessary for planning an the location information database, or a similar external database, for an E9-1-1 deployment using SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="e0458-105">若要将 Skype for Business Server 配置为自动定位网络内的客户端，您需要使用网络线路映射填充位置信息服务数据库并发布位置，或链接到已包含正确映射的外部数据库。</span><span class="sxs-lookup"><span data-stu-id="e0458-105">To configure Skype for Business Server to automatically locate clients within a network, you need to either populate the Location Information service database with a network wiremap and publish the locations, or link to an external database that already contains the correct mappings.</span></span> <span data-ttu-id="e0458-106">作为此过程的一部分，您需要使用 E9-1-1 服务提供商验证位置的市政地址。</span><span class="sxs-lookup"><span data-stu-id="e0458-106">As part of this process, you need to validate the civic addresses of the locations with your E9-1-1 service provider.</span></span> <span data-ttu-id="e0458-107">有关详细信息，请参阅 [部署文档中的"](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) 配置位置数据库"。</span><span class="sxs-lookup"><span data-stu-id="e0458-107">For details, see [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in the Deployment documentation.</span></span>

<span data-ttu-id="e0458-108">You populate the Location Information Service database with an Emergency Response Location (ERL) ， which consists of a市政 address and the specific address within a building.</span><span class="sxs-lookup"><span data-stu-id="e0458-108">You populate the Location Information service database with an Emergency Response Location (ERL), which consists of a civic address and the specific address within a building.</span></span> <span data-ttu-id="e0458-109">位置信息服务 **位置** 字段是建筑物内的特定位置，最大长度为 20 个字符， (空格) 。</span><span class="sxs-lookup"><span data-stu-id="e0458-109">The Location Information service **Location** field, which is the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="e0458-110">在该有限的长度内，请尝试包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="e0458-110">Within that limited length, try to include the following:</span></span>

- <span data-ttu-id="e0458-p103">一个易于理解的、指示 911 呼叫者的位置的名称，以帮助确保紧急响应者到达市政地址后能够迅速找到具体位置。此位置名称可能包括楼号、楼层数、侧楼标识、房间号码等等。应避免使用仅员工知晓的昵称，这样可能导致紧急响应者找错位置。</span><span class="sxs-lookup"><span data-stu-id="e0458-p103">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

- <span data-ttu-id="e0458-114">一个位置标识符，可帮助用户轻松查看其 Skype for Business 客户端选取了正确的位置。</span><span class="sxs-lookup"><span data-stu-id="e0458-114">A location identifier that helps users to easily see that their Skype for Business client picked up the correct location.</span></span> <span data-ttu-id="e0458-115">Skype for Business 客户端会自动连接并在其标头中显示发现的 **"位置**"和"城市"字段。 </span><span class="sxs-lookup"><span data-stu-id="e0458-115">The Skype for Business client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="e0458-116">一个好的做法是将建筑物的街道地址添加到每个位置标识符 (例如，"1st <street number> Floor") 。</span><span class="sxs-lookup"><span data-stu-id="e0458-116">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor <street number>").</span></span> <span data-ttu-id="e0458-117">如果没有街道地址，那么通用的位置标识符（例如“1st Floor”）可以适用于城市中的所有建筑。</span><span class="sxs-lookup"><span data-stu-id="e0458-117">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

- <span data-ttu-id="e0458-118">如果位置是近似位置，因为它由无线访问点确定，您可以添加 **[Near]** (例如，"Near 1st Floor 1234") 。</span><span class="sxs-lookup"><span data-stu-id="e0458-118">If the location is approximate because it's determined by a wireless access point, you can add the word **[Near]** (for example, "Near 1st Floor 1234").</span></span>

> [!NOTE]
> <span data-ttu-id="e0458-119">在通过使用 Skype for Business Server 命令行管理程序命令发布添加到中央位置数据库的位置并复制到池的本地存储之前，这些位置对客户端不可用。</span><span class="sxs-lookup"><span data-stu-id="e0458-119">Locations added to the central location database are not available to the client until they are published by using a Skype for Business Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="e0458-120">有关详细信息，请参阅部署文档中的[Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e0458-120">For details, see [Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) in the Deployment documentation.</span></span>

<span data-ttu-id="e0458-121">以下各节讨论了在填充和维护位置数据库时需要考虑的注意事项。</span><span class="sxs-lookup"><span data-stu-id="e0458-121">The following sections discuss considerations that you need to take into account when populating and maintaining the location database.</span></span>

## <a name="populating-the-location-database"></a><span data-ttu-id="e0458-122">填充位置数据库</span><span class="sxs-lookup"><span data-stu-id="e0458-122">Populating the Location Database</span></span>

<span data-ttu-id="e0458-123">以下问题可以帮助您确定如何填充位置数据库。</span><span class="sxs-lookup"><span data-stu-id="e0458-123">The following questions can help you determine how to populate the location database.</span></span>

 <span data-ttu-id="e0458-124">**使用什么过程填充位置数据库？**</span><span class="sxs-lookup"><span data-stu-id="e0458-124">**What process will you use to populate the location database?**</span></span>

<span data-ttu-id="e0458-p106">数据位于何处？采取何种步骤将数据转换为位置数据库所需的格式？是逐个添加位置，还是使用 CSV 文件批量添加？</span><span class="sxs-lookup"><span data-stu-id="e0458-p106">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

 <span data-ttu-id="e0458-127">**是否具有已包含位置映射的第三方数据库？**</span><span class="sxs-lookup"><span data-stu-id="e0458-127">**Do you have a third party database that already contains a mapping of locations?**</span></span>

<span data-ttu-id="e0458-128">通过使用辅助位置信息服务选项连接到第三方数据库，您可以使用脱机平台对位置进行分组和管理。</span><span class="sxs-lookup"><span data-stu-id="e0458-128">By using the Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="e0458-129">此方案的优势在于除了将位置与网络标识符关联外，还可以将位置与用户关联。</span><span class="sxs-lookup"><span data-stu-id="e0458-129">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="e0458-130">这意味着位置信息服务可以将源自辅助位置信息服务的多个地址返回到 Skype for Business 客户端。</span><span class="sxs-lookup"><span data-stu-id="e0458-130">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Skype for Business client.</span></span> <span data-ttu-id="e0458-131">然后用户可以选择最合适的位置。</span><span class="sxs-lookup"><span data-stu-id="e0458-131">The user can then choose the most appropriate location.</span></span>

<span data-ttu-id="e0458-132">若要与位置信息服务集成，第三方数据库必须遵循 Lync Server 位置请求/响应架构。</span><span class="sxs-lookup"><span data-stu-id="e0458-132">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="e0458-133">有关详细信息，请参阅["[MS-E911WS]： Web Service for E911 Support Protocol Specification"。](https://go.microsoft.com/fwlink/p/?linkid=213819)</span><span class="sxs-lookup"><span data-stu-id="e0458-133">For details, see  ["[MS-E911WS]: Web Service for E911 Support Protocol Specification"](https://go.microsoft.com/fwlink/p/?linkid=213819).</span></span> <span data-ttu-id="e0458-134">有关部署辅助位置信息服务的详细信息，请参阅部署文档中的 ["在 Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) 中配置辅助位置信息服务"。</span><span class="sxs-lookup"><span data-stu-id="e0458-134">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e0458-135">有关填充位置数据库的详细信息，请参阅 [部署文档中](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) 的"配置位置数据库"。</span><span class="sxs-lookup"><span data-stu-id="e0458-135">For details about populating the location database, see [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in the Deployment documentation.</span></span>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="e0458-136">维护位置数据库</span><span class="sxs-lookup"><span data-stu-id="e0458-136">Maintaining the Location Database</span></span>

<span data-ttu-id="e0458-p109">填充位置数据库之后，需要制定更新数据库的策略，因为网络配置发生了改变。以下问题将帮助您确定如何维护位置数据库。</span><span class="sxs-lookup"><span data-stu-id="e0458-p109">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

 <span data-ttu-id="e0458-139">**如何更新位置数据库？**</span><span class="sxs-lookup"><span data-stu-id="e0458-139">**How will you update the location database?**</span></span>

<span data-ttu-id="e0458-140">有几种情况需要更新位置数据库，包括添加 WAP、重新布置 (导致不同的交换机分配) 和子网扩展。</span><span class="sxs-lookup"><span data-stu-id="e0458-140">There are several scenarios that require an update to the location database, including adding WAPs, office recabling (resulting in different switch assignments), and subnet expansion.</span></span> <span data-ttu-id="e0458-141">是直接更新各个位置，还是使用 CSV 文件执行所有位置的批量更新？</span><span class="sxs-lookup"><span data-stu-id="e0458-141">Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

 <span data-ttu-id="e0458-142">**是否使用 SNMP 应用程序将 Lync 客户端 MAC 地址与端口和交换机标识符进行匹配？**</span><span class="sxs-lookup"><span data-stu-id="e0458-142">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>

<span data-ttu-id="e0458-143">如果使用 SNMP 应用程序，需要设计用于保持 SNMP 应用程序和位置数据库之间的交换机机架和端口信息一致的手动过程。</span><span class="sxs-lookup"><span data-stu-id="e0458-143">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="e0458-144">如果 SNMP 应用程序返回数据库中不包括的机架 IP 地址或端口 ID，则位置信息服务将无法将位置返回给客户端。</span><span class="sxs-lookup"><span data-stu-id="e0458-144">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>


