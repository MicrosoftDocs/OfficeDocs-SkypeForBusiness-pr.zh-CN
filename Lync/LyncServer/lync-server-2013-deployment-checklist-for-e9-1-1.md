---
title: Lync Server 2013： E9 的部署清单-1-1
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for E9-1-1
ms:assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398864(v=OCS.15)
ms:contentKeyID: 48185655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5efe5c55386eb431c91e798ad960cc510ce33ce1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="ea503-102">Lync Server 2013 中的 E9 的部署清单-1</span><span class="sxs-lookup"><span data-stu-id="ea503-102">Deployment checklist for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea503-103">_**主题上次修改时间：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="ea503-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="ea503-104">若要有效规划增强的9-1-1 （E9-1-1），请确保包含以下部署要求：</span><span class="sxs-lookup"><span data-stu-id="ea503-104">To plan effectively for Enhanced 9-1-1 (E9-1-1), be sure to include the following deployment requirements:</span></span>

  - <span data-ttu-id="ea503-105">部署 E9 的先决条件-1-1。</span><span class="sxs-lookup"><span data-stu-id="ea503-105">Prerequisites for deploying E9-1-1.</span></span>

  - <span data-ttu-id="ea503-106">部署 E9 所需的步骤 1-1。</span><span class="sxs-lookup"><span data-stu-id="ea503-106">Steps that are required to deploy E9-1-1.</span></span>

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a><span data-ttu-id="ea503-107">E9-1-1 的部署先决条件</span><span class="sxs-lookup"><span data-stu-id="ea503-107">Deployment Prerequisites for E9-1-1</span></span>

<span data-ttu-id="ea503-108">在部署 E9-1 之前，你必须已部署 Lync Server 内部服务器，包括中央管理存储、前端池或标准版服务器、一个或多个中介服务器或中介服务器池以及 Lync Server 客户端。</span><span class="sxs-lookup"><span data-stu-id="ea503-108">Before you deploy E9-1-1, you must already have deployed your Lync Server internal servers, including a Central Management store, a Front End pool or a Standard Edition server, one or more Mediation Servers or Mediation Server pools, and Lync Server clients.</span></span> <span data-ttu-id="ea503-109">此外，E9-1-1 部署需要指向已认证 E9-1-1 服务提供商的 SIP 中继或指向公用电话交换网 (PSTN) 的紧急位置标识号 (ELIN) 网关。</span><span class="sxs-lookup"><span data-stu-id="ea503-109">In addition, an E9-1-1 deployment requires a SIP trunk to a qualified E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway to your public switched telephone network (PSTN).</span></span> <span data-ttu-id="ea503-110">Lync Server 支持仅在美国境内使用 E9 服务提供商。</span><span class="sxs-lookup"><span data-stu-id="ea503-110">Lync Server supports using E9-1-1 service providers only inside the United States.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="ea503-111">部署过程</span><span class="sxs-lookup"><span data-stu-id="ea503-111">Deployment Process</span></span>

<span data-ttu-id="ea503-112">下表概述了 E9-1-1 部署过程。</span><span class="sxs-lookup"><span data-stu-id="ea503-112">The following table provides an overview of the E9-1-1 deployment process.</span></span> <span data-ttu-id="ea503-113">有关部署步骤的详细信息，请参阅部署文档中[Lync Server 2013 中的 "配置增强的 9-1-1](lync-server-2013-configure-enhanced-9-1-1.md) "。</span><span class="sxs-lookup"><span data-stu-id="ea503-113">For details about deployment steps, see [Configure Enhanced 9-1-1 in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea503-114">阶段</span><span class="sxs-lookup"><span data-stu-id="ea503-114">Phase</span></span></th>
<th><span data-ttu-id="ea503-115">步骤</span><span class="sxs-lookup"><span data-stu-id="ea503-115">Steps</span></span></th>
<th><span data-ttu-id="ea503-116">角色</span><span class="sxs-lookup"><span data-stu-id="ea503-116">Roles</span></span></th>
<th><span data-ttu-id="ea503-117">部署文档</span><span class="sxs-lookup"><span data-stu-id="ea503-117">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea503-118">配置语音用法、路由和中继配置</span><span class="sxs-lookup"><span data-stu-id="ea503-118">Configure voice usages, routes, and trunk configurations</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="ea503-p103">创建新的 PSTN 用法记录。这与位置策略中的<strong>PSTN 用法</strong>设置所用的名称相同。</span><span class="sxs-lookup"><span data-stu-id="ea503-p103">Create a new PSTN usage record. This is the same name that is used for the <strong>PSTN Usage</strong> setting in the location policy.</span></span></p></li>
<li><p><span data-ttu-id="ea503-121">创建或分配一个语音路由给上一步中创建的 PSTN 用法记录，然后将网关属性指向 E9-1-1 SIP 中继或 ELIN 网关。 </span><span class="sxs-lookup"><span data-stu-id="ea503-121">Create or assign a voice route to the PSTN usage record created in the previous step and then point the gateway attribute to the E9-1-1 SIP trunk or ELIN gateway.</span></span></p></li>
<li><p><span data-ttu-id="ea503-122">对于 SIP 中继 E9-1-1 服务提供商，设置将使用 <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong> cmdlet 处理 SIP 上的 E9-1-1 呼叫以传递 PIDF-LO 数据的中继。</span><span class="sxs-lookup"><span data-stu-id="ea503-122">For a SIP trunk E9-1-1 service provider, set the trunk that will be handling E9-1-1 calls over the SIP to pass PIDF-LO data by using the <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong> cmdlet.</span></span></p></li>
<li><p><span data-ttu-id="ea503-p104">（可选）对于 SIP 中继 E9-1-1 服务提供商，为未被 E9-1-1 服务提供商的 SIP 中继处理的呼叫创建并分配本地 PSTN 路由。如果与 E9-1-1 服务提供商的连接不可用，将使用此路由。如果受 E9-1-1 服务提供商支持，则向网关分配一个中继配置规则，以便将 911 拨号字符串转换为国家和/或地区紧急呼叫响应中心 (ECRC) 的外线直拨分机 (DID) 号码。</span><span class="sxs-lookup"><span data-stu-id="ea503-p104">Optionally, for a SIP trunk E9-1-1 service provider, create or assign a local PSTN route for calls that are not handled by the E9-1-1 service provider’s SIP trunk. This route will be used if the connection to the E9-1-1 service provider is not available. If supported by your E9-1-1 service provider, assign a trunk configuration rule to the gateway that translates the 911 dial string into the direct inward dialing (DID) number of the national/regional Emergency Call Response Center (ECRC).</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="ea503-126">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="ea503-126">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="ea503-127"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">在 Lync Server 2013 中配置 E9-1 个语音路由</a></span><span class="sxs-lookup"><span data-stu-id="ea503-127"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Configure an E9-1-1 voice route in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea503-128">创建位置策略，并将其分配给用户和子网</span><span class="sxs-lookup"><span data-stu-id="ea503-128">Create location policies and assign them to users and subnets</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="ea503-129">查看全局位置策略。</span><span class="sxs-lookup"><span data-stu-id="ea503-129">Review the global location policy.</span></span></p></li>
<li><p><span data-ttu-id="ea503-130">创建包含用户级范围的位置策略；或者，如果组织具有包含不同紧急情况用法的多个站点，则创建包含网络级范围的位置策略。</span><span class="sxs-lookup"><span data-stu-id="ea503-130">Create a location policy with a user-level scope; or, if the organization has more than one site with different emergency usages, create a location policy with a network-level scope.</span></span></p></li>
<li><p><span data-ttu-id="ea503-131">将位置策略分配给网络站点。</span><span class="sxs-lookup"><span data-stu-id="ea503-131">Assign the location policy to network sites.</span></span></p></li>
<li><p><span data-ttu-id="ea503-132">将相应的子网添加到网络站点。</span><span class="sxs-lookup"><span data-stu-id="ea503-132">Add the appropriate subnets to the network site.</span></span></p></li>
<li><p><span data-ttu-id="ea503-133">（可选）将位置策略分配到用户策略。</span><span class="sxs-lookup"><span data-stu-id="ea503-133">(Optional) Assign the location policy to user policies.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="ea503-134">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="ea503-134">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="ea503-135">CSLocationAdmin（创建位置策略除外）</span><span class="sxs-lookup"><span data-stu-id="ea503-135">CSLocationAdmin (except for creating Location Policies)</span></span></p></td>
<td><p><span data-ttu-id="ea503-136"><a href="lync-server-2013-create-location-policies.md">在 Lync Server 2013 中创建位置策略</a></span><span class="sxs-lookup"><span data-stu-id="ea503-136"><a href="lync-server-2013-create-location-policies.md">Create location policies in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="ea503-137"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">在 Lync Server 2013 中将位置策略添加到网络网站</a></span><span class="sxs-lookup"><span data-stu-id="ea503-137"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Add a location policy to a network site in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="ea503-138"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">在 Lync Server 2013 中将子网与 E9 的网络站点相关联-1</a></span><span class="sxs-lookup"><span data-stu-id="ea503-138"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Associate subnets with network sites for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea503-139">配置位置数据库</span><span class="sxs-lookup"><span data-stu-id="ea503-139">Configure the location database</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="ea503-140">使用网络元素到位置的映射填充数据库。</span><span class="sxs-lookup"><span data-stu-id="ea503-140">Populate the database with a mapping of network elements to locations.</span></span></p></li>
<li><p><span data-ttu-id="ea503-141">对于 ELIN 网关，将 ELINs 添加到&lt;"&gt;公司名称" 列。</span><span class="sxs-lookup"><span data-stu-id="ea503-141">For ELIN gateways, add the ELINs to the &lt;CompanyName&gt; column.</span></span></p></li>
<li><p><span data-ttu-id="ea503-142">配置与 E9-1-1 服务提供商的连接以验证地址。</span><span class="sxs-lookup"><span data-stu-id="ea503-142">Configure the connection to the E9-1-1 service provider for validating addresses.</span></span></p></li>
<li><p><span data-ttu-id="ea503-143">验证 E9-1-1 服务提供商的地址。</span><span class="sxs-lookup"><span data-stu-id="ea503-143">Validate the addresses with the E9-1-1 service provider.</span></span></p></li>
<li><p><span data-ttu-id="ea503-144">发布更新的数据库。</span><span class="sxs-lookup"><span data-stu-id="ea503-144">Publish the updated database.</span></span></p></li>
<li><p><span data-ttu-id="ea503-145">对于 ELIN 网关，将 ELIN 上传到 PSTN 运营商的自动位置标识 (ALI) 数据库。</span><span class="sxs-lookup"><span data-stu-id="ea503-145">For ELIN gateways, upload the ELINs to your PSTN carrier's Automatic Location Identification (ALI) database.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="ea503-146">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="ea503-146">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="ea503-147">CSLocationAdmin</span><span class="sxs-lookup"><span data-stu-id="ea503-147">CSLocationAdmin</span></span></p></td>
<td><p><span data-ttu-id="ea503-148"><a href="lync-server-2013-configure-the-location-database.md">Configure the location database in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ea503-148"><a href="lync-server-2013-configure-the-location-database.md">Configure the location database in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea503-149">配置高级功能（可选）</span><span class="sxs-lookup"><span data-stu-id="ea503-149">Configure Advanced Features (optional)</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="ea503-150">配置 SNMP 应用程序的 URL。</span><span class="sxs-lookup"><span data-stu-id="ea503-150">Configure the URL for the SNMP application.</span></span></p></li>
<li><p><span data-ttu-id="ea503-151">配置辅助位置信息服务的位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="ea503-151">Configure the URL for the location of the Secondary Location Information service.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="ea503-152">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="ea503-152">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="ea503-153"><a href="lync-server-2013-configure-an-snmp-application.md">在 Lync Server 2013 中配置 SNMP 应用程序</a></span><span class="sxs-lookup"><span data-stu-id="ea503-153"><a href="lync-server-2013-configure-an-snmp-application.md">Configure an SNMP application in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="ea503-154"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">在 Lync Server 2013 中配置辅助位置信息服务</a></span><span class="sxs-lookup"><span data-stu-id="ea503-154"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

