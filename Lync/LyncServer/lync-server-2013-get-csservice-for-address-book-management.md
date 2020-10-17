---
title: Lync Server 2013：用于通讯簿管理的 Get-CsService
description: Lync Server 2013：用于通讯簿管理的 Get-CsService。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsService for Address Book management
ms:assetid: 373b717d-5efa-4c36-a899-a23a5bd922b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429698(v=OCS.15)
ms:contentKeyID: 48183853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e46173429988d87022c13fab33e3778279dd0e9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554648"
---
# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="4a2a1-103">Lync Server 2013 中的通讯簿管理 Get-CsService</span><span class="sxs-lookup"><span data-stu-id="4a2a1-103">Get-CsService for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a2a1-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4a2a1-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4a2a1-p101">谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 Get-CsService cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4a2a1-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsService cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

<span data-ttu-id="4a2a1-107">Get-CsService 非常有价值，可以检索和显示基础结构定义的 Web 服务的当前配置。</span><span class="sxs-lookup"><span data-stu-id="4a2a1-107">Get-CsService is valuable to retrieve and display the current configuration of your infrastructure’s defined Web Services.</span></span> <span data-ttu-id="4a2a1-108">通过定义池的完全限定域名 (FQDN) 和参数 WebServer，该 cmdlet 可返回服务器提供的基于 Web 的服务，包括通讯簿处理程序和通讯组列表扩展 URI。</span><span class="sxs-lookup"><span data-stu-id="4a2a1-108">By defining the pool’s fully qualified domain name (FQDN) and the parameter WebServer, the cmdlet returns the web-based services offered by your server, including the Address Book handler and distribution list expansion URIs.</span></span>

<span data-ttu-id="4a2a1-109">例如：</span><span class="sxs-lookup"><span data-stu-id="4a2a1-109">For example:</span></span>

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

<span data-ttu-id="4a2a1-110">此 cmdlet 返回以下值：</span><span class="sxs-lookup"><span data-stu-id="4a2a1-110">This cmdlet returns the following:</span></span>

<span data-ttu-id="4a2a1-111">Identity： Web 网:pool01</span><span class="sxs-lookup"><span data-stu-id="4a2a1-111">Identity : WebServer:pool01.contoso.net</span></span>

<span data-ttu-id="4a2a1-112">:Dc01：</span><span class="sxs-lookup"><span data-stu-id="4a2a1-112">FileStore : FileStore:dc01.contoso.net</span></span>

<span data-ttu-id="4a2a1-113">UserServer： UserServer:pool01</span><span class="sxs-lookup"><span data-stu-id="4a2a1-113">UserServer : UserServer:pool01.contoso.net</span></span>

<span data-ttu-id="4a2a1-114">PrimaryHttpPort：80</span><span class="sxs-lookup"><span data-stu-id="4a2a1-114">PrimaryHttpPort : 80</span></span>

<span data-ttu-id="4a2a1-115">PrimaryHttpsPort：443</span><span class="sxs-lookup"><span data-stu-id="4a2a1-115">PrimaryHttpsPort : 443</span></span>

<span data-ttu-id="4a2a1-116">ExternalHttpPort：8080</span><span class="sxs-lookup"><span data-stu-id="4a2a1-116">ExternalHttpPort : 8080</span></span>

<span data-ttu-id="4a2a1-117">ExternalHttpsPort：4443</span><span class="sxs-lookup"><span data-stu-id="4a2a1-117">ExternalHttpsPort : 4443</span></span>

<span data-ttu-id="4a2a1-118">PublishedPrimaryHttpPort：80</span><span class="sxs-lookup"><span data-stu-id="4a2a1-118">PublishedPrimaryHttpPort : 80</span></span>

<span data-ttu-id="4a2a1-119">PublishedPrimaryHttpsPort：443</span><span class="sxs-lookup"><span data-stu-id="4a2a1-119">PublishedPrimaryHttpsPort : 443</span></span>

<span data-ttu-id="4a2a1-120">PublishedExternalHttpPort：80</span><span class="sxs-lookup"><span data-stu-id="4a2a1-120">PublishedExternalHttpPort : 80</span></span>

<span data-ttu-id="4a2a1-121">PublishedExternalHttpsPort：443</span><span class="sxs-lookup"><span data-stu-id="4a2a1-121">PublishedExternalHttpsPort : 443</span></span>

<span data-ttu-id="4a2a1-122">ReachPrimaryPsomServerPort：8060</span><span class="sxs-lookup"><span data-stu-id="4a2a1-122">ReachPrimaryPsomServerPort : 8060</span></span>

<span data-ttu-id="4a2a1-123">ReachExternalPsomServerPort：8061</span><span class="sxs-lookup"><span data-stu-id="4a2a1-123">ReachExternalPsomServerPort : 8061</span></span>

<span data-ttu-id="4a2a1-124">AppSharingPortStart：49152</span><span class="sxs-lookup"><span data-stu-id="4a2a1-124">AppSharingPortStart : 49152</span></span>

<span data-ttu-id="4a2a1-125">AppSharingPortCount：16383</span><span class="sxs-lookup"><span data-stu-id="4a2a1-125">AppSharingPortCount : 16383</span></span>

<span data-ttu-id="4a2a1-126">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="4a2a1-126">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span></span>

<span data-ttu-id="4a2a1-127">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span><span class="sxs-lookup"><span data-stu-id="4a2a1-127">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span></span>

<span data-ttu-id="4a2a1-128">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span><span class="sxs-lookup"><span data-stu-id="4a2a1-128">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span></span>

<span data-ttu-id="4a2a1-129">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="4a2a1-129">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span></span>

<span data-ttu-id="4a2a1-130">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="4a2a1-130">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span></span>

<span data-ttu-id="4a2a1-131">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="4a2a1-131">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="4a2a1-132">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="4a2a1-132">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="4a2a1-133">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span><span class="sxs-lookup"><span data-stu-id="4a2a1-133">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span></span>

<span data-ttu-id="4a2a1-134">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span><span class="sxs-lookup"><span data-stu-id="4a2a1-134">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span></span>

<span data-ttu-id="4a2a1-135">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="4a2a1-135">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="4a2a1-136">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="4a2a1-136">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span></span>

<span data-ttu-id="4a2a1-137">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="4a2a1-137">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span></span>

<span data-ttu-id="4a2a1-138">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span><span class="sxs-lookup"><span data-stu-id="4a2a1-138">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span></span>

<span data-ttu-id="4a2a1-139">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span><span class="sxs-lookup"><span data-stu-id="4a2a1-139">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span></span>

<span data-ttu-id="4a2a1-140">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="4a2a1-140">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="4a2a1-141">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="4a2a1-141">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="4a2a1-142">MeetExternalUri : https://csweb.contoso.com/Meet</span><span class="sxs-lookup"><span data-stu-id="4a2a1-142">MeetExternalUri : https://csweb.contoso.com/Meet</span></span>

<span data-ttu-id="4a2a1-143">DialinExternalUri : https://csweb.contoso.com/Dialin</span><span class="sxs-lookup"><span data-stu-id="4a2a1-143">DialinExternalUri : https://csweb.contoso.com/Dialin</span></span>

<span data-ttu-id="4a2a1-144">CscpInternalUri : https://internalweb.contoso.net/Cscp</span><span class="sxs-lookup"><span data-stu-id="4a2a1-144">CscpInternalUri : https://internalweb.contoso.net/Cscp</span></span>

<span data-ttu-id="4a2a1-145">ReachExternalUri : https://csweb.contoso.com/Reach</span><span class="sxs-lookup"><span data-stu-id="4a2a1-145">ReachExternalUri : https://csweb.contoso.com/Reach</span></span>

<span data-ttu-id="4a2a1-146">ReachInternalUri : https://internalweb.contoso.net/Reach</span><span class="sxs-lookup"><span data-stu-id="4a2a1-146">ReachInternalUri : https://internalweb.contoso.net/Reach</span></span>

<span data-ttu-id="4a2a1-147">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="4a2a1-147">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="4a2a1-148">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="4a2a1-148">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="4a2a1-149">ExternalFqdn： csweb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4a2a1-149">ExternalFqdn : csweb.contoso.com</span></span>

<span data-ttu-id="4a2a1-150">InternalFqdn： internalweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="4a2a1-150">InternalFqdn : internalweb.contoso.net</span></span>

<span data-ttu-id="4a2a1-151">DependentServiceList： {注册器:pool01，ConferencingServer:pool01}</span><span class="sxs-lookup"><span data-stu-id="4a2a1-151">DependentServiceList : {Registrar:pool01.contoso.net, ConferencingServer:pool01.contoso.net}</span></span>

<span data-ttu-id="4a2a1-152">ServiceId： 1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="4a2a1-152">ServiceId : 1-WebServices-1</span></span>

<span data-ttu-id="4a2a1-153">SiteId： Site： Redmond</span><span class="sxs-lookup"><span data-stu-id="4a2a1-153">SiteId : Site:Redmond</span></span>

<span data-ttu-id="4a2a1-154">PoolFqdn： pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="4a2a1-154">PoolFqdn : pool01.contoso.net</span></span>

<span data-ttu-id="4a2a1-155">版本：5</span><span class="sxs-lookup"><span data-stu-id="4a2a1-155">Version : 5</span></span>

<span data-ttu-id="4a2a1-156">Role： Web Web</span><span class="sxs-lookup"><span data-stu-id="4a2a1-156">Role : WebServer</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4a2a1-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a2a1-157">See Also</span></span>


[<span data-ttu-id="4a2a1-158">Get-csservice</span><span class="sxs-lookup"><span data-stu-id="4a2a1-158">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

