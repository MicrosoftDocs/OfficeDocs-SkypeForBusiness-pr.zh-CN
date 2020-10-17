---
title: Lync Server 2013：查看林的全局设置状态
description: Lync Server 2013：查看林的全局设置状态。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9f722ea66f6c54c816703bd1af1d3def57bbd84
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567588"
---
# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a><span data-ttu-id="2d523-103">在 Lync Server 2013 中查看林的全局设置状态</span><span class="sxs-lookup"><span data-stu-id="2d523-103">View status of global settings for a forest in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d523-104">_**上次修改的主题：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="2d523-104">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="2d523-105">管理员应每月查看 Lync Server 2013 部署的全局设置。</span><span class="sxs-lookup"><span data-stu-id="2d523-105">Administrators should review the global settings for a Lync Server 2013 deployment monthly.</span></span> <span data-ttu-id="2d523-106">目标是查看针对一组已知配置实施的设置，这是一种基准配置，可帮助确保设置有效，并确定是否应更新基准文档。</span><span class="sxs-lookup"><span data-stu-id="2d523-106">The objective would be to review implemented settings against a set of known configurations—a baseline configuration to help guarantee that settings are valid and to determine whether the baseline documentation should be updated.</span></span> <span data-ttu-id="2d523-107">对全局设置所做的更改应通过应包括记录新设置的更改控制过程实现。</span><span class="sxs-lookup"><span data-stu-id="2d523-107">Changes to global setting should be implemented through a Change Control process which should include documenting the new settings.</span></span>

<span data-ttu-id="2d523-108">应查看的全局设置将在以下各节中介绍：</span><span class="sxs-lookup"><span data-stu-id="2d523-108">Global settings that should be reviewed are described in the following sections:</span></span>

<div>

## <a name="check-general-settings"></a><span data-ttu-id="2d523-109">检查常规设置</span><span class="sxs-lookup"><span data-stu-id="2d523-109">Check general settings</span></span>

<span data-ttu-id="2d523-110">检查 "常规设置"，包括 Lync Server 2013 (SIP) 域的受支持的会话初始协议。</span><span class="sxs-lookup"><span data-stu-id="2d523-110">Check general settings, including the supported Session Initiation Protocol (SIP) domains for Lync Server 2013.</span></span>

<span data-ttu-id="2d523-111">SIP 域信息可以通过使用 Windows PowerShell 和 **CsSipDomain** cmdlet 返回。</span><span class="sxs-lookup"><span data-stu-id="2d523-111">SIP domain information can be returned by using Windows PowerShell and the **Get-CsSipDomain** cmdlet.</span></span> <span data-ttu-id="2d523-112">若要返回此信息，请运行 `Get-CsSipDomain` Windows PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="2d523-112">To return this information, run the `Get-CsSipDomain` Windows PowerShell command.</span></span>

<span data-ttu-id="2d523-113">对于所有授权的 SIP 域，Get-CsSipDomain 将返回与以下内容类似的信息：</span><span class="sxs-lookup"><span data-stu-id="2d523-113">Get-CsSipDomain will return information similar to this for all the authorized SIP domains:</span></span>

<span data-ttu-id="2d523-114">标识名称 IsDefault</span><span class="sxs-lookup"><span data-stu-id="2d523-114">Identity Name IsDefault</span></span>

<span data-ttu-id="2d523-115">\-------- ---- ---------</span><span class="sxs-lookup"><span data-stu-id="2d523-115">\-------- ---- ---------</span></span>

<span data-ttu-id="2d523-116">fabrikam.com fabrikam.com True</span><span class="sxs-lookup"><span data-stu-id="2d523-116">fabrikam.com fabrikam.com True</span></span>

<span data-ttu-id="2d523-117">na.fabrikam.com na.fabrikam.com False</span><span class="sxs-lookup"><span data-stu-id="2d523-117">na.fabrikam.com na.fabrikam.com False</span></span>

<span data-ttu-id="2d523-118">如果 IsDefault 属性设置为 True，则相应的域是默认的 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="2d523-118">If the IsDefault property is set to True, the corresponding domain is your default SIP domain.</span></span> <span data-ttu-id="2d523-119">您可以使用 Set-CsSipDomain cmdlet 更改组织的默认 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="2d523-119">You can use the Set-CsSipDomain cmdlet to change the default SIP domain for your organization.</span></span> <span data-ttu-id="2d523-120">但是，不能只删除默认的 SIP 域，因为这样做会导致没有默认域。</span><span class="sxs-lookup"><span data-stu-id="2d523-120">However, you can't just delete the default SIP domain because that would leave you without a default domain.</span></span> <span data-ttu-id="2d523-121">如果要删除 fabrikam.com 域 (如前面的示例) 中所示，则必须首先将 na.fabrikam.com 配置为默认域。</span><span class="sxs-lookup"><span data-stu-id="2d523-121">If you wanted to delete the fabrikam.com domain (as shown in the previous example), you would first have to configure na.fabrikam.com to be your default domain.</span></span>

</div>

<div>

## <a name="check-meeting-settings"></a><span data-ttu-id="2d523-122">检查会议设置</span><span class="sxs-lookup"><span data-stu-id="2d523-122">Check meeting settings</span></span>

<span data-ttu-id="2d523-123">会议设置包括会议策略定义以及在会议中参与匿名用户的支持。</span><span class="sxs-lookup"><span data-stu-id="2d523-123">Meeting settings include meeting policy definitions and support for participation of anonymous users in meetings.</span></span>

<span data-ttu-id="2d523-124">可以使用 Windows PowerShell 和 **get-csmeetingconfiguration** cmdlet 检索会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="2d523-124">Meeting configuration settings can be retrieved by using Windows PowerShell and the **Get-CsMeetingConfiguration** cmdlet.</span></span> <span data-ttu-id="2d523-125">例如，以下命令将返回有关全局会议配置设置的信息：</span><span class="sxs-lookup"><span data-stu-id="2d523-125">For example, this command returns information about the global meeting configuration settings:</span></span>

<span data-ttu-id="2d523-126">Get-CsMeetingConfiguration –也可以在站点范围配置标识 "全局" 会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="2d523-126">Get-CsMeetingConfiguration –Identity "Global"Meeting configuration settings can also be configured at the site scope.</span></span> <span data-ttu-id="2d523-127">因此，您可能需要使用以下命令，该命令将返回有关所有会议配置设置的信息：</span><span class="sxs-lookup"><span data-stu-id="2d523-127">Because of that, you might want to use the following command, which returns information about all the meeting configuration settings:</span></span>

`Get-CsMeetingConfiguration`

<span data-ttu-id="2d523-128">**Get-csmeetingconfiguration** cmdlet 将返回类似于以下内容的信息：</span><span class="sxs-lookup"><span data-stu-id="2d523-128">The **Get-CsMeetingConfiguration** cmdlet returns information similar to the following:</span></span>

<span data-ttu-id="2d523-129">标识：全局</span><span class="sxs-lookup"><span data-stu-id="2d523-129">Identity : Global</span></span>

<span data-ttu-id="2d523-130">PstnCallersBypassLobby： True</span><span class="sxs-lookup"><span data-stu-id="2d523-130">PstnCallersBypassLobby : True</span></span>

<span data-ttu-id="2d523-131">EnableAssignedConferenceType： True</span><span class="sxs-lookup"><span data-stu-id="2d523-131">EnableAssignedConferenceType : True</span></span>

<span data-ttu-id="2d523-132">DesignateAsPresenter：公司</span><span class="sxs-lookup"><span data-stu-id="2d523-132">DesignateAsPresenter : Company</span></span>

<span data-ttu-id="2d523-133">AssignedConferenceTypeByDefault： True</span><span class="sxs-lookup"><span data-stu-id="2d523-133">AssignedConferenceTypeByDefault : True</span></span>

<span data-ttu-id="2d523-134">AdmitAnonymousUsersByDefault： True</span><span class="sxs-lookup"><span data-stu-id="2d523-134">AdmitAnonymousUsersByDefault : True</span></span>

<span data-ttu-id="2d523-135">同样，列表中的最后一项 **AdmitAnonymousUsersByDefault**，启用或禁用匿名用户参与会议的功能。</span><span class="sxs-lookup"><span data-stu-id="2d523-135">Again, the final item in the list, **AdmitAnonymousUsersByDefault**, enables or disables the ability of anonymous users to participate in meetings.</span></span>

<span data-ttu-id="2d523-136">检查会议配置设置时，您可能会发现将当前设置与默认等效项进行比较非常有用。</span><span class="sxs-lookup"><span data-stu-id="2d523-136">When checking meeting configuration settings, you might find it useful to compare the current settings against the default equivalents.</span></span> <span data-ttu-id="2d523-137">您可以通过运行以下命令来查看默认会议配置设置：</span><span class="sxs-lookup"><span data-stu-id="2d523-137">You can view the default meeting configuration settings by running the following command:</span></span>

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="2d523-138">上一个命令创建全局会议配置设置的仅内存内部实例，该实例使用每个属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="2d523-138">The previous command creates an in-memory-only instance of the global meeting configuration settings, an instance that uses the default value for each property.</span></span> <span data-ttu-id="2d523-139">运行命令时，不会创建实际会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="2d523-139">No actual meeting configuration settings are created when you run the command.</span></span> <span data-ttu-id="2d523-140">但是，所有默认属性值都将显示在屏幕上。</span><span class="sxs-lookup"><span data-stu-id="2d523-140">However, all the default property values will be displayed on-screen.</span></span>

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a><span data-ttu-id="2d523-141">检查边缘服务器及其设置</span><span class="sxs-lookup"><span data-stu-id="2d523-141">Check Edge Servers and their settings</span></span>

<span data-ttu-id="2d523-142">可以使用 Windows PowerShell 检索边缘服务器信息。</span><span class="sxs-lookup"><span data-stu-id="2d523-142">Edge Server information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="2d523-143">此命令返回有关配置为在组织中使用的所有边缘服务器的信息：</span><span class="sxs-lookup"><span data-stu-id="2d523-143">This command returns information about all the Edge Servers configured for use in your organization:</span></span>

`Get-CsService -EdgeServer`

<span data-ttu-id="2d523-144">返回的信息包括每台边缘服务器的所有 FQDN 和端口设置：</span><span class="sxs-lookup"><span data-stu-id="2d523-144">The returned information includes all of the FQDN and port settings for each Edge Server:</span></span>

<span data-ttu-id="2d523-145">Identity： EdgeServer： dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="2d523-145">Identity : EdgeServer: dc.fabrikam.com</span></span>

<span data-ttu-id="2d523-146">注册器：注册器： LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="2d523-146">Registrar : Registrar: LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="2d523-147">AccessEdgeInternalSipPort：5061</span><span class="sxs-lookup"><span data-stu-id="2d523-147">AccessEdgeInternalSipPort : 5061</span></span>

<span data-ttu-id="2d523-148">AccessEdgeExternalSipPort：5061</span><span class="sxs-lookup"><span data-stu-id="2d523-148">AccessEdgeExternalSipPort : 5061</span></span>

<span data-ttu-id="2d523-149">AccessEdgeClientPort：443</span><span class="sxs-lookup"><span data-stu-id="2d523-149">AccessEdgeClientPort : 443</span></span>

<span data-ttu-id="2d523-150">DataPsomServerPort：8057</span><span class="sxs-lookup"><span data-stu-id="2d523-150">DataPsomServerPort : 8057</span></span>

<span data-ttu-id="2d523-151">DataPsomClientPort：444</span><span class="sxs-lookup"><span data-stu-id="2d523-151">DataPsomClientPort : 444</span></span>

<span data-ttu-id="2d523-152">MediaRelayAuthEdgePort：5062</span><span class="sxs-lookup"><span data-stu-id="2d523-152">MediaRelayAuthEdgePort : 5062</span></span>

<span data-ttu-id="2d523-153">MediaRelayAuthInternalTurnTcpPort：443</span><span class="sxs-lookup"><span data-stu-id="2d523-153">MediaRelayAuthInternalTurnTcpPort : 443</span></span>

<span data-ttu-id="2d523-154">MediaRelayAuthExternalTurnTcpPort：445</span><span class="sxs-lookup"><span data-stu-id="2d523-154">MediaRelayAuthExternalTurnTcpPort : 445</span></span>

<span data-ttu-id="2d523-155">MediaRelayAuthInternalTurnUdpPort：3478</span><span class="sxs-lookup"><span data-stu-id="2d523-155">MediaRelayAuthInternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="2d523-156">MediaRelayAuthExternalTurnUdpPort：3478</span><span class="sxs-lookup"><span data-stu-id="2d523-156">MediaRelayAuthExternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="2d523-157">MediaCommunicationPortStart：50000</span><span class="sxs-lookup"><span data-stu-id="2d523-157">MediaCommunicationPortStart : 50000</span></span>

<span data-ttu-id="2d523-158">MediaComunicationPortCount：10000</span><span class="sxs-lookup"><span data-stu-id="2d523-158">MediaComunicationPortCount : 10000</span></span>

<span data-ttu-id="2d523-159">AccessEdgeExternalFqdn： dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="2d523-159">AccessEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="2d523-160">DataEdgeExternalFqdn： dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="2d523-160">DataEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="2d523-161">AVEdgeExternalFqdn :</span><span class="sxs-lookup"><span data-stu-id="2d523-161">AVEdgeExternalFqdn :</span></span>

<span data-ttu-id="2d523-162">InternalInterfaceFqdn :</span><span class="sxs-lookup"><span data-stu-id="2d523-162">InternalInterfaceFqdn :</span></span>

<span data-ttu-id="2d523-163">ExternalMrasFqdn： dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="2d523-163">ExternalMrasFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="2d523-164">DependentServiceList： {注册器： LYNC-SE.fabrikam.com，</span><span class="sxs-lookup"><span data-stu-id="2d523-164">DependentServiceList : {Registrar:LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="2d523-165">ConferencingServer： LYNC-SE. fabrikam</span><span class="sxs-lookup"><span data-stu-id="2d523-165">ConferencingServer:LYNC-SE.fabrikam</span></span>

<span data-ttu-id="2d523-166">com，MediationServer： LYNC-SE。</span><span class="sxs-lookup"><span data-stu-id="2d523-166">com, MediationServer:LYNC-SE.</span></span>

<span data-ttu-id="2d523-167">fabrikam.com}</span><span class="sxs-lookup"><span data-stu-id="2d523-167">fabrikam.com}</span></span>

<span data-ttu-id="2d523-168">ServiceId： fabrikam.com-EdgeServer-2</span><span class="sxs-lookup"><span data-stu-id="2d523-168">ServiceId : fabrikam.com-EdgeServer-2</span></span>

<span data-ttu-id="2d523-169">SiteId： site:fabrikam</span><span class="sxs-lookup"><span data-stu-id="2d523-169">SiteId : site:fabrikam.com</span></span>

<span data-ttu-id="2d523-170">PoolFqdn： dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="2d523-170">PoolFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="2d523-171">版本：5</span><span class="sxs-lookup"><span data-stu-id="2d523-171">Version : 5</span></span>

<span data-ttu-id="2d523-172">Role： EdgeServer</span><span class="sxs-lookup"><span data-stu-id="2d523-172">Role : EdgeServer</span></span>

<div>

## <a name="check-federation-settings"></a><span data-ttu-id="2d523-173">检查联合身份验证设置</span><span class="sxs-lookup"><span data-stu-id="2d523-173">Check federation settings</span></span>

<span data-ttu-id="2d523-174">检查联合身份验证设置，如是否配置了联合身份验证设置，如果答案为 "是"，则为 FQDN 和端口。</span><span class="sxs-lookup"><span data-stu-id="2d523-174">Check Federation settings, such as whether it is configured and, if the answer is "yes,", the FQDN and port.</span></span> <span data-ttu-id="2d523-175">联合身份验证是通过使用访问边缘配置设置的全局集合启用和禁用的。</span><span class="sxs-lookup"><span data-stu-id="2d523-175">Federation is enabled and disabled by using the global collection of Access Edge configuration settings.</span></span> <span data-ttu-id="2d523-176">在其他情况下，这意味着联合是在全或无基础上配置的：为整个组织启用联盟或为整个组织禁用联盟</span><span class="sxs-lookup"><span data-stu-id="2d523-176">Among other things, these mean that federation is configured on an all-or-nothing basis: either federation is enabled for the whole organization or federation is disabled for the whole organization</span></span>

<span data-ttu-id="2d523-177">您可以使用 Windows PowerShell 返回您的访问边缘配置设置。</span><span class="sxs-lookup"><span data-stu-id="2d523-177">Your Access Edge configuration settings can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="2d523-178">为此，请运行以下 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="2d523-178">To do that, run the following Windows PowerShell command:</span></span>

`Get-CsAccessEdgeConfiguration`

<span data-ttu-id="2d523-179">反过来，该命令将返回类似于以下内容的数据：</span><span class="sxs-lookup"><span data-stu-id="2d523-179">In turn, that command will return data similar to this:</span></span>

<span data-ttu-id="2d523-180">标识：全局</span><span class="sxs-lookup"><span data-stu-id="2d523-180">Identity : Global</span></span>

<span data-ttu-id="2d523-181">AllowAnonymousUsers： False</span><span class="sxs-lookup"><span data-stu-id="2d523-181">AllowAnonymousUsers : False</span></span>

<span data-ttu-id="2d523-182">AllowFederatedUsers： False</span><span class="sxs-lookup"><span data-stu-id="2d523-182">AllowFederatedUsers : False</span></span>

<span data-ttu-id="2d523-183">AllowOutsideUsers： False</span><span class="sxs-lookup"><span data-stu-id="2d523-183">AllowOutsideUsers : False</span></span>

<span data-ttu-id="2d523-184">BeClearingHouse： False</span><span class="sxs-lookup"><span data-stu-id="2d523-184">BeClearingHouse : False</span></span>

<span data-ttu-id="2d523-185">EnablePartnerDiscovery： False</span><span class="sxs-lookup"><span data-stu-id="2d523-185">EnablePartnerDiscovery : False</span></span>

<span data-ttu-id="2d523-186">EnableArchivingDisclaimer： False</span><span class="sxs-lookup"><span data-stu-id="2d523-186">EnableArchivingDisclaimer : False</span></span>

<span data-ttu-id="2d523-187">KeepCrlsUpToDateForPeers： True</span><span class="sxs-lookup"><span data-stu-id="2d523-187">KeepCrlsUpToDateForPeers : True</span></span>

<span data-ttu-id="2d523-188">MarkSourceVerifiableOnOutgoingMessages： True</span><span class="sxs-lookup"><span data-stu-id="2d523-188">MarkSourceVerifiableOnOutgoingMessages : True</span></span>

<span data-ttu-id="2d523-189">OutgoingTlsCountForFederatedPartners：4</span><span class="sxs-lookup"><span data-stu-id="2d523-189">OutgoingTlsCountForFederatedPartners : 4</span></span>

<span data-ttu-id="2d523-190">RoutingMethod : UseDnsSrvRouting</span><span class="sxs-lookup"><span data-stu-id="2d523-190">RoutingMethod : UseDnsSrvRouting</span></span>

<span data-ttu-id="2d523-191">如果将 **AllowFederatedUsers** 属性设置为 True，则表示已为您的组织启用联盟。</span><span class="sxs-lookup"><span data-stu-id="2d523-191">If the **AllowFederatedUsers** property is set to True, that means that federation is enabled for your organization.</span></span> <span data-ttu-id="2d523-192"> (将 **AllowFederatedUsers** 设置为 True 也意味着，在拆分域方案中，您的本地用户将能够与云用户进行无缝通信。 ) </span><span class="sxs-lookup"><span data-stu-id="2d523-192">(Setting **AllowFederatedUsers** to True also means that, in a split domain scenario, your on-premises users will be able to communicate seamlessly with your in-the-cloud users.)</span></span>

<span data-ttu-id="2d523-193">若要检索边缘服务器的 FQDN 和端口设置，请参阅上一项任务 (边缘服务器及其设置) 。</span><span class="sxs-lookup"><span data-stu-id="2d523-193">To retrieve the FQDN and port settings for your Edge Server, see the previous task (Edge Servers and their settings).</span></span>

<span data-ttu-id="2d523-194">在全局范围内启用联合仅意味着用户可以与联合用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="2d523-194">Enabling federation at the global scope only means that users can potentially communicate with federated users.</span></span> <span data-ttu-id="2d523-195">若要确定任何单个用户是否可以实际与联合用户通信，需要检查分配给该用户的外部用户访问策略。</span><span class="sxs-lookup"><span data-stu-id="2d523-195">To determine whether any individual users can actually communicate with federated users requires you to examine the external user access policy assigned to that user.</span></span>

<span data-ttu-id="2d523-196">可以使用 Windows PowerShell 返回外部用户访问信息。</span><span class="sxs-lookup"><span data-stu-id="2d523-196">External user access information can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="2d523-197">例如，以下命令将返回全局外部用户访问策略的信息：</span><span class="sxs-lookup"><span data-stu-id="2d523-197">For example, this command returns information for the global external user access policy:</span></span>

`Get-CsExternalAccessPolicy -Identity "Global"`

<span data-ttu-id="2d523-198">此命令将返回所有外部用户访问策略的信息：</span><span class="sxs-lookup"><span data-stu-id="2d523-198">And this command returns information for all the external user access policies:</span></span>

`Get-CsExternalAccessPolicy`

<span data-ttu-id="2d523-199">返回的信息将如下所示：</span><span class="sxs-lookup"><span data-stu-id="2d523-199">The returned information will resemble this:</span></span>

<span data-ttu-id="2d523-200">标识： False</span><span class="sxs-lookup"><span data-stu-id="2d523-200">Identity : False</span></span>

<span data-ttu-id="2d523-201">产品介绍</span><span class="sxs-lookup"><span data-stu-id="2d523-201">Description :</span></span>

<span data-ttu-id="2d523-202">EnableFederationAccess： False</span><span class="sxs-lookup"><span data-stu-id="2d523-202">EnableFederationAccess : False</span></span>

<span data-ttu-id="2d523-203">EnablePublicCloudAccess： False</span><span class="sxs-lookup"><span data-stu-id="2d523-203">EnablePublicCloudAccess : False</span></span>

<span data-ttu-id="2d523-204">EnablePublicCloudAccessAudioVideoAccess： False</span><span class="sxs-lookup"><span data-stu-id="2d523-204">EnablePublicCloudAccessAudioVideoAccess : False</span></span>

<span data-ttu-id="2d523-205">EnableOutsideAccess： False</span><span class="sxs-lookup"><span data-stu-id="2d523-205">EnableOutsideAccess : False</span></span>

<span data-ttu-id="2d523-206">如果将 **EnableFederationAccess** 设置为 True，则由给定策略管理的用户可以与联盟用户通信。</span><span class="sxs-lookup"><span data-stu-id="2d523-206">If **EnableFederationAccess** is set to True, then users managed by the given policy can communicate with federated users.</span></span>

</div>

</div>

<div>

## <a name="check-archiving-settings"></a><span data-ttu-id="2d523-207">检查存档设置</span><span class="sxs-lookup"><span data-stu-id="2d523-207">Check archiving settings</span></span>

<span data-ttu-id="2d523-208">检查内部和联合通信的存档设置。在验证内部存档和外部存档的设置之前，应验证是否已启用存档。</span><span class="sxs-lookup"><span data-stu-id="2d523-208">Check archiving settings for internal and federated communications.Before verifying the settings for internal and external archiving, you should verify that archiving is enabled.</span></span>

<span data-ttu-id="2d523-209">可以使用 Windows PowerShell 和 Get-CsArchivingConfiguration cmdlet 来验证存档配置设置：</span><span class="sxs-lookup"><span data-stu-id="2d523-209">Archiving configuration settings can be verified by using Windows PowerShell and the Get-CsArchivingConfiguration cmdlet:</span></span>

`Get-CsArchivingConfiguration -Identity "Global"`

<span data-ttu-id="2d523-210">请注意，也可以在站点范围内配置存档设置。</span><span class="sxs-lookup"><span data-stu-id="2d523-210">Note that archiving settings can also be configured at the site scope.</span></span> <span data-ttu-id="2d523-211">若要返回有关所有存档设置的信息，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="2d523-211">To return information about all the archiving settings, use this command:</span></span>

`Get-CsArchivingConfiguration`

<span data-ttu-id="2d523-212">Get-CsArchivingConfiguration cmdlet 返回与以下内容类似的数据：</span><span class="sxs-lookup"><span data-stu-id="2d523-212">The Get-CsArchivingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="2d523-213">标识：全局</span><span class="sxs-lookup"><span data-stu-id="2d523-213">Identity : Global</span></span>

<span data-ttu-id="2d523-214">EnableArchiving： False</span><span class="sxs-lookup"><span data-stu-id="2d523-214">EnableArchiving : False</span></span>

<span data-ttu-id="2d523-215">EnablePurging： False</span><span class="sxs-lookup"><span data-stu-id="2d523-215">EnablePurging : False</span></span>

<span data-ttu-id="2d523-216">PurgeExportedArchivesOnly： False</span><span class="sxs-lookup"><span data-stu-id="2d523-216">PurgeExportedArchivesOnly : False</span></span>

<span data-ttu-id="2d523-217">BlockOnArchiveFailure： False</span><span class="sxs-lookup"><span data-stu-id="2d523-217">BlockOnArchiveFailure : False</span></span>

<span data-ttu-id="2d523-218">KeepArchivingDataForDays：14</span><span class="sxs-lookup"><span data-stu-id="2d523-218">KeepArchivingDataForDays : 14</span></span>

<span data-ttu-id="2d523-219">PurgeHourOfDay：2</span><span class="sxs-lookup"><span data-stu-id="2d523-219">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="2d523-220">ArchiveDuplicateMessages： True</span><span class="sxs-lookup"><span data-stu-id="2d523-220">ArchiveDuplicateMessages : True</span></span>

<span data-ttu-id="2d523-221">CachePurgingInterval：24</span><span class="sxs-lookup"><span data-stu-id="2d523-221">CachePurgingInterval : 24</span></span>

<span data-ttu-id="2d523-222">如果将 EnableArchiving 属性设置为 False，则意味着将不会存档任何通信会话。</span><span class="sxs-lookup"><span data-stu-id="2d523-222">If the EnableArchiving property is set to False, that means that no communication sessions will be archived.</span></span> <span data-ttu-id="2d523-223">如果只想存档即时消息会话，请使用如下所示的命令来启用 IM 会话的存档：</span><span class="sxs-lookup"><span data-stu-id="2d523-223">If you want to archive instant messaging sessions only, use a command such as the following to enable the archiving of IM sessions:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="2d523-224">若要存档会议会话和即时消息会话，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="2d523-224">To archive conferencing sessions and instant messaging sessions, use this command:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="2d523-225">如果您想要将当前存档设置与默认设置进行比较，请运行以下 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="2d523-225">If you’d like to compare your current archiving settings with the default settings, run the following Windows PowerShell command:</span></span>

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="2d523-226">该命令将创建全局存档配置设置的仅内存中的实例。</span><span class="sxs-lookup"><span data-stu-id="2d523-226">That command creates an in-memory-only instance of the global archiving configuration settings.</span></span> <span data-ttu-id="2d523-227">这不是由 Lync Server 使用的真实设置集合。</span><span class="sxs-lookup"><span data-stu-id="2d523-227">This is not a real collection of settings that is used by Lync Server.</span></span> <span data-ttu-id="2d523-228">但是，它确实显示所有存档配置属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="2d523-228">However, it does display the default values for all the archiving configuration properties.</span></span>

<span data-ttu-id="2d523-229">您还可以使用此命令返回存档服务器的 FQDN：</span><span class="sxs-lookup"><span data-stu-id="2d523-229">You can also use this command to return the FQDN of your Archiving servers:</span></span>

`Get-CsService -ArchivingServer`

<span data-ttu-id="2d523-230">验证是否已启用存档后，可以查看存档策略，以确定是否正在存档内部和外部通信会话。</span><span class="sxs-lookup"><span data-stu-id="2d523-230">After you have verified that archiving is enabled, you can then view your archiving policies to determine whether internal and external communication sessions are being archived.</span></span>

<span data-ttu-id="2d523-231">可以使用 Get-CsArchivingPolicy cmdlet 检索存档策略信息。</span><span class="sxs-lookup"><span data-stu-id="2d523-231">Archiving policy information can be retrieved by using the Get-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="2d523-232">例如，以下命令将返回有关全局存档策略的信息：</span><span class="sxs-lookup"><span data-stu-id="2d523-232">For example, this command returns information about the global archiving policy:</span></span>

`Get-CsArchivingPolicy -Identity "Global"`

<span data-ttu-id="2d523-233">由于还可以在网站和每用户范围中配置存档策略，因此您可能还需要使用此命令，该命令将返回有关所有存档策略的信息：</span><span class="sxs-lookup"><span data-stu-id="2d523-233">Because archiving policies can also be configured at the site and the per-user scope, you might also want to use this command, which returns information about all the archiving policies:</span></span>

`Get-CsArchivingPolicy`

<span data-ttu-id="2d523-234">您从 Get-CsArchivingPolicy 收到的信息将与以下内容类似：</span><span class="sxs-lookup"><span data-stu-id="2d523-234">The information that you receive from Get-CsArchivingPolicy will resemble this:</span></span>

<span data-ttu-id="2d523-235">标识：全局</span><span class="sxs-lookup"><span data-stu-id="2d523-235">Identity : Global</span></span>

<span data-ttu-id="2d523-236">产品介绍</span><span class="sxs-lookup"><span data-stu-id="2d523-236">Description :</span></span>

<span data-ttu-id="2d523-237">ArchiveInternal： False</span><span class="sxs-lookup"><span data-stu-id="2d523-237">ArchiveInternal : False</span></span>

<span data-ttu-id="2d523-238">ArchiveExternal： False</span><span class="sxs-lookup"><span data-stu-id="2d523-238">ArchiveExternal : False</span></span>

<span data-ttu-id="2d523-239">请注意，默认情况下，在存档策略中禁用内部存档和外部存档。</span><span class="sxs-lookup"><span data-stu-id="2d523-239">Note that, by default, both internal and external archiving are disabled in an archiving policy.</span></span>

</div>

<div>

## <a name="check-cdr-settings"></a><span data-ttu-id="2d523-240">检查 CDR 设置</span><span class="sxs-lookup"><span data-stu-id="2d523-240">Check CDR settings</span></span>

<span data-ttu-id="2d523-241">检查呼叫详细记录 (CDR) 设置对等、会议和语音呼叫详细记录。</span><span class="sxs-lookup"><span data-stu-id="2d523-241">Check Call Detail Record (CDR) settings for peer-to-peer, conferencing, and Voice call detail recording.</span></span> <span data-ttu-id="2d523-242">可以使用 **set-cscdrconfiguration** cmdlet 返回有关 CDR 设置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2d523-242">Detailed information about your CDR settings can be returned by using the **Get-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="2d523-243">例如，以下命令将返回有关 CDR 配置设置的全局集合的信息：</span><span class="sxs-lookup"><span data-stu-id="2d523-243">For example, this command returns information about the global collection of CDR configuration settings:</span></span>

`Get-CsCdrConfiguration -Identity "Global"`

<span data-ttu-id="2d523-244">由于也可以在站点范围配置 CDR，因此您可能还需要运行以下命令，该命令将返回有关所有 CDR 配置设置的信息：</span><span class="sxs-lookup"><span data-stu-id="2d523-244">Because CDR can also be configured at the site scope, you might also want to run this command, which returns information about all the CDR configuration settings:</span></span>

`Get-CsCdrConfiguration`

<span data-ttu-id="2d523-245">Get-CsCdrConfiguration cmdlet 为每个 CDR 配置设置集合返回类似以下内容的信息：</span><span class="sxs-lookup"><span data-stu-id="2d523-245">The Get-CsCdrConfiguration cmdlet returns information similar to this for each collection of CDR configuration settings:</span></span>

<span data-ttu-id="2d523-246">标识：全局</span><span class="sxs-lookup"><span data-stu-id="2d523-246">Identity : Global</span></span>

<span data-ttu-id="2d523-247">EnableCDR： True</span><span class="sxs-lookup"><span data-stu-id="2d523-247">EnableCDR : True</span></span>

<span data-ttu-id="2d523-248">EnablePurging： True</span><span class="sxs-lookup"><span data-stu-id="2d523-248">EnablePurging : True</span></span>

<span data-ttu-id="2d523-249">KeepCallDetailForDays：60</span><span class="sxs-lookup"><span data-stu-id="2d523-249">KeepCallDetailForDays : 60</span></span>

<span data-ttu-id="2d523-250">KeepErrorReportForDays：60</span><span class="sxs-lookup"><span data-stu-id="2d523-250">KeepErrorReportForDays : 60</span></span>

<span data-ttu-id="2d523-251">PurgeHourOfDay：2</span><span class="sxs-lookup"><span data-stu-id="2d523-251">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="2d523-252">可以通过使用 Get-CsQoEConfiguration cmdlet，为 QoE 监视返回类似的信息。</span><span class="sxs-lookup"><span data-stu-id="2d523-252">Similar information can be returned for QoE monitoring by using the Get-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="2d523-253">例如，以下命令将返回有关 QoE 配置设置的全局集合的信息：</span><span class="sxs-lookup"><span data-stu-id="2d523-253">For example, this command returns information about the global collection of QoE configuration settings:</span></span>

`Get-QoEConfiguration -Identity "Global"`

<span data-ttu-id="2d523-254">该信息将类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="2d523-254">That information will resemble this:</span></span>

<span data-ttu-id="2d523-255">标识：全局</span><span class="sxs-lookup"><span data-stu-id="2d523-255">Identity : Global</span></span>

<span data-ttu-id="2d523-256">ExternalConsumerIssuedCertId :</span><span class="sxs-lookup"><span data-stu-id="2d523-256">ExternalConsumerIssuedCertId :</span></span>

<span data-ttu-id="2d523-257">EnablePurging： True</span><span class="sxs-lookup"><span data-stu-id="2d523-257">EnablePurging : True</span></span>

<span data-ttu-id="2d523-258">KeepQoEDataForDays：60</span><span class="sxs-lookup"><span data-stu-id="2d523-258">KeepQoEDataForDays : 60</span></span>

<span data-ttu-id="2d523-259">PurgeHourOfDay：1</span><span class="sxs-lookup"><span data-stu-id="2d523-259">PurgeHourOfDay : 1</span></span>

<span data-ttu-id="2d523-260">EnableExternalConsumer： False</span><span class="sxs-lookup"><span data-stu-id="2d523-260">EnableExternalConsumer : False</span></span>

<span data-ttu-id="2d523-261">ExternalConsumerName :</span><span class="sxs-lookup"><span data-stu-id="2d523-261">ExternalConsumerName :</span></span>

<span data-ttu-id="2d523-262">ExternalConsumerURL :</span><span class="sxs-lookup"><span data-stu-id="2d523-262">ExternalConsumerURL :</span></span>

<span data-ttu-id="2d523-263">EnableQoE： True</span><span class="sxs-lookup"><span data-stu-id="2d523-263">EnableQoE : True</span></span>

<span data-ttu-id="2d523-264">如果要将当前 CDR 设置与默认 CDR 设置进行比较，可以通过运行以下命令来查看默认值：</span><span class="sxs-lookup"><span data-stu-id="2d523-264">If you want to compare your current CDR settings with the default CDR settings, the default values can be reviewed by running this command:</span></span>

`New-CsCdrConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="2d523-265">同样，可以使用以下命令检索 QoE monitoring 的默认值：</span><span class="sxs-lookup"><span data-stu-id="2d523-265">Likewise, the default values for QoE monitoring can be retrieved by using this command:</span></span>

`New-CsQoEConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="2d523-266">您还可以通过运行以下命令返回您的监视服务器的 FQDN：</span><span class="sxs-lookup"><span data-stu-id="2d523-266">You can also return the FQDN of your Monitoring servers by running this command:</span></span>

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a><span data-ttu-id="2d523-267">检查语音设置</span><span class="sxs-lookup"><span data-stu-id="2d523-267">Check voice settings</span></span>

<span data-ttu-id="2d523-268">语音设置对于管理员而言通常包含在语音策略和语音路由中：语音策略包含用于确定向单个用户公开的功能的设置 (例如，转发或转移呼叫的能力) ，而语音路由决定了在 PSTN 中路由) 呼叫的方式 (和。</span><span class="sxs-lookup"><span data-stu-id="2d523-268">The voice settings typically important to administrators are contained in voice policies and voice routes: voice policies contain the settings that determine the capabilities exposed to individual users (such as the ability to forward or transfer calls), while voice routes determine how (and if) calls are routed across the PSTN.</span></span>

<span data-ttu-id="2d523-269">可以使用 Windows PowerShell 检索语音策略信息。</span><span class="sxs-lookup"><span data-stu-id="2d523-269">Voice policy information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="2d523-270">例如，以下命令将返回有关全局语音策略的信息：</span><span class="sxs-lookup"><span data-stu-id="2d523-270">For example, this command returns information about the global voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global"`

<span data-ttu-id="2d523-271">此命令将返回有关已配置为在组织中使用的所有语音策略的信息：</span><span class="sxs-lookup"><span data-stu-id="2d523-271">And this command returns information about all the voice policies configured for use in the organization:</span></span>

`Get-CsVoicePolicy`

<span data-ttu-id="2d523-272">Get-CsVoicePolicy cmdlet 返回的信息类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="2d523-272">The information returned by the Get-CsVoicePolicy cmdlet resembles the following:</span></span>

<span data-ttu-id="2d523-273">标识：全局</span><span class="sxs-lookup"><span data-stu-id="2d523-273">Identity : Global</span></span>

<span data-ttu-id="2d523-274">PstnUsages {}</span><span class="sxs-lookup"><span data-stu-id="2d523-274">PstnUsages : {}</span></span>

<span data-ttu-id="2d523-275">产品介绍</span><span class="sxs-lookup"><span data-stu-id="2d523-275">Description :</span></span>

<span data-ttu-id="2d523-276">AllowSimulRing： True</span><span class="sxs-lookup"><span data-stu-id="2d523-276">AllowSimulRing : True</span></span>

<span data-ttu-id="2d523-277">AllowCallForwarding： True</span><span class="sxs-lookup"><span data-stu-id="2d523-277">AllowCallForwarding : True</span></span>

<span data-ttu-id="2d523-278">AllowPSTNReRouting： True</span><span class="sxs-lookup"><span data-stu-id="2d523-278">AllowPSTNReRouting : True</span></span>

<span data-ttu-id="2d523-279">名称： DefaultPolicy</span><span class="sxs-lookup"><span data-stu-id="2d523-279">Name : DefaultPolicy</span></span>

<span data-ttu-id="2d523-280">EnableDelegation： True</span><span class="sxs-lookup"><span data-stu-id="2d523-280">EnableDelegation : True</span></span>

<span data-ttu-id="2d523-281">EnableTeamCall： True</span><span class="sxs-lookup"><span data-stu-id="2d523-281">EnableTeamCall : True</span></span>

<span data-ttu-id="2d523-282">EnableCallTransfer： True</span><span class="sxs-lookup"><span data-stu-id="2d523-282">EnableCallTransfer : True</span></span>

<span data-ttu-id="2d523-283">EnableCallPark： False</span><span class="sxs-lookup"><span data-stu-id="2d523-283">EnableCallPark : False</span></span>

<span data-ttu-id="2d523-284">EnableMaliciousCallTracing： False</span><span class="sxs-lookup"><span data-stu-id="2d523-284">EnableMaliciousCallTracing : False</span></span>

<span data-ttu-id="2d523-285">EnableBWPolicyOverride： False</span><span class="sxs-lookup"><span data-stu-id="2d523-285">EnableBWPolicyOverride : False</span></span>

<span data-ttu-id="2d523-286">PreventPSTNTollBypass： False</span><span class="sxs-lookup"><span data-stu-id="2d523-286">PreventPSTNTollBypass : False</span></span>

<span data-ttu-id="2d523-287">您还可以创建返回语音策略子集的查询。</span><span class="sxs-lookup"><span data-stu-id="2d523-287">You can also create queries that returned a subset of your voice policies.</span></span> <span data-ttu-id="2d523-288">例如，以下命令将返回所有允许呼叫转接的语音策略：</span><span class="sxs-lookup"><span data-stu-id="2d523-288">For example, this command returns all the voice policies that allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

<span data-ttu-id="2d523-289">此命令将返回不允许呼叫转接的所有语音策略：</span><span class="sxs-lookup"><span data-stu-id="2d523-289">And this command returns all the voice policies that don’t allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

<span data-ttu-id="2d523-290">在 Windows PowerShell 中，使用 Get-CsVoiceRouting cmdlet 可返回有关语音路由的信息：</span><span class="sxs-lookup"><span data-stu-id="2d523-290">In Windows PowerShell, use the Get-CsVoiceRouting cmdlet to return information about your voice routes:</span></span>

`Get-CsVoiceRoute`

<span data-ttu-id="2d523-291">该命令将返回类似于所有语音路由的信息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2d523-291">That command returns information such as this for all the voice routes:</span></span>

<span data-ttu-id="2d523-292">标识： LocalRoute</span><span class="sxs-lookup"><span data-stu-id="2d523-292">Identity : LocalRoute</span></span>

<span data-ttu-id="2d523-293">优先级：0</span><span class="sxs-lookup"><span data-stu-id="2d523-293">Priority : 0</span></span>

<span data-ttu-id="2d523-294">产品介绍</span><span class="sxs-lookup"><span data-stu-id="2d523-294">Description :</span></span>

<span data-ttu-id="2d523-295">NumberPattern： ^ (\\ + 1 \[ 0-9 \] {10}) $</span><span class="sxs-lookup"><span data-stu-id="2d523-295">NumberPattern : ^(\\+1\[0-9\]{10})$</span></span>

<span data-ttu-id="2d523-296">PstnUsages {}</span><span class="sxs-lookup"><span data-stu-id="2d523-296">PstnUsages : {}</span></span>

<span data-ttu-id="2d523-297">PstnGatewayList : {}</span><span class="sxs-lookup"><span data-stu-id="2d523-297">PstnGatewayList : {}</span></span>

<span data-ttu-id="2d523-298">名称： LocalRoute</span><span class="sxs-lookup"><span data-stu-id="2d523-298">Name : LocalRoute</span></span>

<span data-ttu-id="2d523-299">SuppressCallerId :</span><span class="sxs-lookup"><span data-stu-id="2d523-299">SuppressCallerId :</span></span>

<span data-ttu-id="2d523-300">AlternateCallerId :</span><span class="sxs-lookup"><span data-stu-id="2d523-300">AlternateCallerId :</span></span>

<span data-ttu-id="2d523-301">Lync Server 允许您创建没有 PSTN 用法且未指定 PSTN 网关的语音路由。</span><span class="sxs-lookup"><span data-stu-id="2d523-301">Lync Server allows you to create voice routes that do not have a PSTN usage and do not specify a PSTN gateway.</span></span> <span data-ttu-id="2d523-302">但是，不能实际通过未配置这两个属性值的语音路由路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="2d523-302">However, you can't actually route calls over a voice route that does not have these two property values configured.</span></span> <span data-ttu-id="2d523-303">因此，您可能会发现，定期运行此命令会很有用，后者将返回没有 PSTN 用法的任何语音路由的标识：</span><span class="sxs-lookup"><span data-stu-id="2d523-303">Because of that, you might find it useful to periodically run this command, which returns the identity of any voice route that does not have a PSTN usage:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

<span data-ttu-id="2d523-304">同样，此命令将返回尚未配置为具有 PSTN 网关的任何语音路由的标识：</span><span class="sxs-lookup"><span data-stu-id="2d523-304">Similarly, this command returns the identity of any voice route that has not been configured to have a PSTN gateway:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a><span data-ttu-id="2d523-305">检查会议助理设置</span><span class="sxs-lookup"><span data-stu-id="2d523-305">Check Conferencing Attendant settings</span></span>

<span data-ttu-id="2d523-306">检查 PSTN 电话拨入式会议的会议助理设置。</span><span class="sxs-lookup"><span data-stu-id="2d523-306">Check conferencing Attendant settings for PSTN dial-in conferencing.</span></span> <span data-ttu-id="2d523-307">只能使用 **set-csdialinconferencingconfiguration** cmdlet 来检索会议助理设置。</span><span class="sxs-lookup"><span data-stu-id="2d523-307">Conferencing Attendant settings can only be retrieved by using the **Get-CsDialInConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="2d523-308">这些设置在 "Lync Server 控制面板" 中不可用。</span><span class="sxs-lookup"><span data-stu-id="2d523-308">These settings are not available in the Lync Server Control Panel.</span></span> <span data-ttu-id="2d523-309">若要查看会议助理设置，请使用与以下内容类似的 Windows PowerShell 命令，该命令将返回全局会议助理设置集合：</span><span class="sxs-lookup"><span data-stu-id="2d523-309">To view your Conferencing Attendant settings, use a Windows PowerShell command similar to the following, which returns the global collection of Conferencing Attendant settings:</span></span>

`Get-CsDialInConferencingConfiguration -Identity "Global"`

<span data-ttu-id="2d523-310">请注意，还可以在站点范围内配置会议助理设置。</span><span class="sxs-lookup"><span data-stu-id="2d523-310">Note that Conferencing Attendant settings can also be configured at the site scope.</span></span> <span data-ttu-id="2d523-311">若要返回有关所有会议助理设置的信息，请改为使用此命令：</span><span class="sxs-lookup"><span data-stu-id="2d523-311">To return information about all the Conferencing Attendant settings, use this command instead:</span></span>

`Get-CsDialInConferencingConfiguration`

<span data-ttu-id="2d523-312">Get-CsDialInConferencingConfiguration cmdlet 返回与以下内容类似的数据：</span><span class="sxs-lookup"><span data-stu-id="2d523-312">The Get-CsDialInConferencingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="2d523-313">标识：全局</span><span class="sxs-lookup"><span data-stu-id="2d523-313">Identity : Global</span></span>

<span data-ttu-id="2d523-314">EntryExitAnnouncementsType : UseNames</span><span class="sxs-lookup"><span data-stu-id="2d523-314">EntryExitAnnouncementsType : UseNames</span></span>

<span data-ttu-id="2d523-315">EnableNameRecording： True</span><span class="sxs-lookup"><span data-stu-id="2d523-315">EnableNameRecording : True</span></span>

<span data-ttu-id="2d523-316">EntryExitAnnouncementsEnabledByDefault： False</span><span class="sxs-lookup"><span data-stu-id="2d523-316">EntryExitAnnouncementsEnabledByDefault : False</span></span>

<span data-ttu-id="2d523-317">如果 EntryExitAnnouncementsEnabledByDefault 设置为 False，则表示已禁用会议通知。</span><span class="sxs-lookup"><span data-stu-id="2d523-317">If EntryExitAnnouncementsEnabledByDefault is set to False, that means the conferencing announcements are disabled.</span></span> <span data-ttu-id="2d523-318">若要启用进入和退出通知，请运行与以下内容类似的 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="2d523-318">To enable entry and exit announcements, run a Windows PowerShell command similar to this:</span></span>

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2d523-319">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d523-319">See Also</span></span>


[<span data-ttu-id="2d523-320">CsSipDomain</span><span class="sxs-lookup"><span data-stu-id="2d523-320">Get-CsSipDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[<span data-ttu-id="2d523-321">Get-csmeetingconfiguration</span><span class="sxs-lookup"><span data-stu-id="2d523-321">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[<span data-ttu-id="2d523-322">Get-csservice</span><span class="sxs-lookup"><span data-stu-id="2d523-322">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="2d523-323">Set-csaccessedgeconfiguration</span><span class="sxs-lookup"><span data-stu-id="2d523-323">Get-CsAccessEdgeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[<span data-ttu-id="2d523-324">Set-csexternalaccesspolicy</span><span class="sxs-lookup"><span data-stu-id="2d523-324">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="2d523-325">Set-csarchivingconfiguration</span><span class="sxs-lookup"><span data-stu-id="2d523-325">Get-CsArchivingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[<span data-ttu-id="2d523-326">Set-cscdrconfiguration</span><span class="sxs-lookup"><span data-stu-id="2d523-326">Get-CsCdrConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[<span data-ttu-id="2d523-327">New-csqoeconfiguration</span><span class="sxs-lookup"><span data-stu-id="2d523-327">Get-CsQoEConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[<span data-ttu-id="2d523-328">Set-csvoicepolicy</span><span class="sxs-lookup"><span data-stu-id="2d523-328">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="2d523-329">CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="2d523-329">Get-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[<span data-ttu-id="2d523-330">Set-csdialinconferencingconfiguration</span><span class="sxs-lookup"><span data-stu-id="2d523-330">Get-CsDialInConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

