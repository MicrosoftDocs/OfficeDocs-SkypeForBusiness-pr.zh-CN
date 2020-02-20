---
title: Lync Server 2013：用于通讯簿管理的 Get-csservice
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
ms.openlocfilehash: c39520a54ae664a1eddf241cbf1d8d27fe858510
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="2a34f-102">Lync Server 2013 中的 Get-csservice for Address Book management</span><span class="sxs-lookup"><span data-stu-id="2a34f-102">Get-CsService for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a34f-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2a34f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2a34f-p101">谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 Get-CsService cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="2a34f-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsService cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

<span data-ttu-id="2a34f-106">Get-csservice 对于检索和显示基础结构定义的 Web 服务的当前配置非常有用。</span><span class="sxs-lookup"><span data-stu-id="2a34f-106">Get-CsService is valuable to retrieve and display the current configuration of your infrastructure’s defined Web Services.</span></span> <span data-ttu-id="2a34f-107">通过定义池的完全限定域名 (FQDN) 和参数 WebServer，该 cmdlet 可返回服务器提供的基于 Web 的服务，包括通讯簿处理程序和通讯组列表扩展 URI。</span><span class="sxs-lookup"><span data-stu-id="2a34f-107">By defining the pool’s fully qualified domain name (FQDN) and the parameter WebServer, the cmdlet returns the web-based services offered by your server, including the Address Book handler and distribution list expansion URIs.</span></span>

<span data-ttu-id="2a34f-108">例如：</span><span class="sxs-lookup"><span data-stu-id="2a34f-108">For example:</span></span>

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

<span data-ttu-id="2a34f-109">此 cmdlet 返回以下值：</span><span class="sxs-lookup"><span data-stu-id="2a34f-109">This cmdlet returns the following:</span></span>

<span data-ttu-id="2a34f-110">Identity： Web 网:pool01</span><span class="sxs-lookup"><span data-stu-id="2a34f-110">Identity : WebServer:pool01.contoso.net</span></span>

<span data-ttu-id="2a34f-111">:Dc01：</span><span class="sxs-lookup"><span data-stu-id="2a34f-111">FileStore : FileStore:dc01.contoso.net</span></span>

<span data-ttu-id="2a34f-112">UserServer： UserServer:pool01</span><span class="sxs-lookup"><span data-stu-id="2a34f-112">UserServer : UserServer:pool01.contoso.net</span></span>

<span data-ttu-id="2a34f-113">PrimaryHttpPort：80</span><span class="sxs-lookup"><span data-stu-id="2a34f-113">PrimaryHttpPort : 80</span></span>

<span data-ttu-id="2a34f-114">PrimaryHttpsPort：443</span><span class="sxs-lookup"><span data-stu-id="2a34f-114">PrimaryHttpsPort : 443</span></span>

<span data-ttu-id="2a34f-115">ExternalHttpPort：8080</span><span class="sxs-lookup"><span data-stu-id="2a34f-115">ExternalHttpPort : 8080</span></span>

<span data-ttu-id="2a34f-116">ExternalHttpsPort：4443</span><span class="sxs-lookup"><span data-stu-id="2a34f-116">ExternalHttpsPort : 4443</span></span>

<span data-ttu-id="2a34f-117">PublishedPrimaryHttpPort：80</span><span class="sxs-lookup"><span data-stu-id="2a34f-117">PublishedPrimaryHttpPort : 80</span></span>

<span data-ttu-id="2a34f-118">PublishedPrimaryHttpsPort：443</span><span class="sxs-lookup"><span data-stu-id="2a34f-118">PublishedPrimaryHttpsPort : 443</span></span>

<span data-ttu-id="2a34f-119">PublishedExternalHttpPort：80</span><span class="sxs-lookup"><span data-stu-id="2a34f-119">PublishedExternalHttpPort : 80</span></span>

<span data-ttu-id="2a34f-120">PublishedExternalHttpsPort：443</span><span class="sxs-lookup"><span data-stu-id="2a34f-120">PublishedExternalHttpsPort : 443</span></span>

<span data-ttu-id="2a34f-121">ReachPrimaryPsomServerPort：8060</span><span class="sxs-lookup"><span data-stu-id="2a34f-121">ReachPrimaryPsomServerPort : 8060</span></span>

<span data-ttu-id="2a34f-122">ReachExternalPsomServerPort：8061</span><span class="sxs-lookup"><span data-stu-id="2a34f-122">ReachExternalPsomServerPort : 8061</span></span>

<span data-ttu-id="2a34f-123">AppSharingPortStart：49152</span><span class="sxs-lookup"><span data-stu-id="2a34f-123">AppSharingPortStart : 49152</span></span>

<span data-ttu-id="2a34f-124">AppSharingPortCount：16383</span><span class="sxs-lookup"><span data-stu-id="2a34f-124">AppSharingPortCount : 16383</span></span>

<span data-ttu-id="2a34f-125">LIServiceInternalUri :https://internalweb.contoso.net/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="2a34f-125">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span></span>

<span data-ttu-id="2a34f-126">ABHandlerInternalUri :https://internalweb.contoso.net/abs/handler</span><span class="sxs-lookup"><span data-stu-id="2a34f-126">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span></span>

<span data-ttu-id="2a34f-127">ABHandlerExternalUri :https://csweb.contoso.com/abs/handler</span><span class="sxs-lookup"><span data-stu-id="2a34f-127">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span></span>

<span data-ttu-id="2a34f-128">DLExpansionInternalUri :https://internalweb.contoso.net/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="2a34f-128">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span></span>

<span data-ttu-id="2a34f-129">DLExpansionExternalUri :https://csweb.contoso.com/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="2a34f-129">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span></span>

<span data-ttu-id="2a34f-130">CAHandlerInternalUri :https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="2a34f-130">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="2a34f-131">CAHandlerInternalAnonUri :http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="2a34f-131">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="2a34f-132">CollabContentInternalUri :https://internalweb.contoso.net/CollabContent</span><span class="sxs-lookup"><span data-stu-id="2a34f-132">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span></span>

<span data-ttu-id="2a34f-133">CollabContentExternalUri :https://csweb.contoso.com/CollabContent</span><span class="sxs-lookup"><span data-stu-id="2a34f-133">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span></span>

<span data-ttu-id="2a34f-134">CAHandlerExternalUri :https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="2a34f-134">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="2a34f-135">DeviceUpdateDownloadInternalUri :https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="2a34f-135">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span></span>

<span data-ttu-id="2a34f-136">DeviceUpdateDownloadExternalUri :https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="2a34f-136">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span></span>

<span data-ttu-id="2a34f-137">DeviceUpdateStoreInternalUri :http://internalweb.contoso.net/RequestHandler/Files</span><span class="sxs-lookup"><span data-stu-id="2a34f-137">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span></span>

<span data-ttu-id="2a34f-138">DeviceUpdateStoreExternalUri :https://csweb.contoso.com/RequestHandlerExt/Files</span><span class="sxs-lookup"><span data-stu-id="2a34f-138">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span></span>

<span data-ttu-id="2a34f-139">RgsAgentServiceInternalUri :https://internalweb.contoso.net/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="2a34f-139">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="2a34f-140">RgsAgentServiceExternalUri :https://csweb.contoso.com/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="2a34f-140">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="2a34f-141">MeetExternalUri :https://csweb.contoso.com/Meet</span><span class="sxs-lookup"><span data-stu-id="2a34f-141">MeetExternalUri : https://csweb.contoso.com/Meet</span></span>

<span data-ttu-id="2a34f-142">DialinExternalUri :https://csweb.contoso.com/Dialin</span><span class="sxs-lookup"><span data-stu-id="2a34f-142">DialinExternalUri : https://csweb.contoso.com/Dialin</span></span>

<span data-ttu-id="2a34f-143">CscpInternalUri :https://internalweb.contoso.net/Cscp</span><span class="sxs-lookup"><span data-stu-id="2a34f-143">CscpInternalUri : https://internalweb.contoso.net/Cscp</span></span>

<span data-ttu-id="2a34f-144">ReachExternalUri :https://csweb.contoso.com/Reach</span><span class="sxs-lookup"><span data-stu-id="2a34f-144">ReachExternalUri : https://csweb.contoso.com/Reach</span></span>

<span data-ttu-id="2a34f-145">ReachInternalUri :https://internalweb.contoso.net/Reach</span><span class="sxs-lookup"><span data-stu-id="2a34f-145">ReachInternalUri : https://internalweb.contoso.net/Reach</span></span>

<span data-ttu-id="2a34f-146">WebTicketExternalUri :https://csweb.contoso.com/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="2a34f-146">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="2a34f-147">WebTicketInternalUri :https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="2a34f-147">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="2a34f-148">ExternalFqdn： csweb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2a34f-148">ExternalFqdn : csweb.contoso.com</span></span>

<span data-ttu-id="2a34f-149">InternalFqdn： internalweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2a34f-149">InternalFqdn : internalweb.contoso.net</span></span>

<span data-ttu-id="2a34f-150">DependentServiceList： {注册器:pool01，ConferencingServer:pool01}</span><span class="sxs-lookup"><span data-stu-id="2a34f-150">DependentServiceList : {Registrar:pool01.contoso.net, ConferencingServer:pool01.contoso.net}</span></span>

<span data-ttu-id="2a34f-151">ServiceId： 1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="2a34f-151">ServiceId : 1-WebServices-1</span></span>

<span data-ttu-id="2a34f-152">SiteId： Site： Redmond</span><span class="sxs-lookup"><span data-stu-id="2a34f-152">SiteId : Site:Redmond</span></span>

<span data-ttu-id="2a34f-153">PoolFqdn： pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2a34f-153">PoolFqdn : pool01.contoso.net</span></span>

<span data-ttu-id="2a34f-154">版本：5</span><span class="sxs-lookup"><span data-stu-id="2a34f-154">Version : 5</span></span>

<span data-ttu-id="2a34f-155">Role： Web Web</span><span class="sxs-lookup"><span data-stu-id="2a34f-155">Role : WebServer</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="2a34f-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a34f-156">See Also</span></span>


[<span data-ttu-id="2a34f-157">Get-csservice</span><span class="sxs-lookup"><span data-stu-id="2a34f-157">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

