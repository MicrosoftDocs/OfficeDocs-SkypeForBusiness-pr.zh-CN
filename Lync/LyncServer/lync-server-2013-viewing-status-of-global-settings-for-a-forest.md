---
title: Lync Server 2013：查看林的全局设置状态
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
ms.openlocfilehash: 2a5381445a866da924a8ff0f511ee48353ab5c91
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a><span data-ttu-id="691b3-102">在 Lync Server 2013 中查看林的全局设置状态</span><span class="sxs-lookup"><span data-stu-id="691b3-102">View status of global settings for a forest in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="691b3-103">_**上次修改的主题：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="691b3-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="691b3-104">管理员应每月查看 Lync Server 2013 部署的全局设置。</span><span class="sxs-lookup"><span data-stu-id="691b3-104">Administrators should review the global settings for a Lync Server 2013 deployment monthly.</span></span> <span data-ttu-id="691b3-105">目标是查看针对一组已知配置实施的设置，这是一种基准配置，可帮助确保设置有效，并确定是否应更新基准文档。</span><span class="sxs-lookup"><span data-stu-id="691b3-105">The objective would be to review implemented settings against a set of known configurations—a baseline configuration to help guarantee that settings are valid and to determine whether the baseline documentation should be updated.</span></span> <span data-ttu-id="691b3-106">对全局设置所做的更改应通过应包括记录新设置的更改控制过程实现。</span><span class="sxs-lookup"><span data-stu-id="691b3-106">Changes to global setting should be implemented through a Change Control process which should include documenting the new settings.</span></span>

<span data-ttu-id="691b3-107">应查看的全局设置将在以下各节中介绍：</span><span class="sxs-lookup"><span data-stu-id="691b3-107">Global settings that should be reviewed are described in the following sections:</span></span>

<div>

## <a name="check-general-settings"></a><span data-ttu-id="691b3-108">检查常规设置</span><span class="sxs-lookup"><span data-stu-id="691b3-108">Check general settings</span></span>

<span data-ttu-id="691b3-109">检查常规设置，包括 Lync Server 2013 支持的会话初始协议（SIP）域。</span><span class="sxs-lookup"><span data-stu-id="691b3-109">Check general settings, including the supported Session Initiation Protocol (SIP) domains for Lync Server 2013.</span></span>

<span data-ttu-id="691b3-110">SIP 域信息可以通过使用 Windows PowerShell 和**CsSipDomain** cmdlet 返回。</span><span class="sxs-lookup"><span data-stu-id="691b3-110">SIP domain information can be returned by using Windows PowerShell and the **Get-CsSipDomain** cmdlet.</span></span> <span data-ttu-id="691b3-111">若要返回此信息，请`Get-CsSipDomain`运行 Windows PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="691b3-111">To return this information, run the `Get-CsSipDomain` Windows PowerShell command.</span></span>

<span data-ttu-id="691b3-112">对于所有授权的 SIP 域，CsSipDomain 将返回与以下内容类似的信息：</span><span class="sxs-lookup"><span data-stu-id="691b3-112">Get-CsSipDomain will return information similar to this for all the authorized SIP domains:</span></span>

<span data-ttu-id="691b3-113">标识名称 IsDefault</span><span class="sxs-lookup"><span data-stu-id="691b3-113">Identity Name IsDefault</span></span>

<span data-ttu-id="691b3-114">\-------- ---- ---------</span><span class="sxs-lookup"><span data-stu-id="691b3-114">\-------- ---- ---------</span></span>

<span data-ttu-id="691b3-115">fabrikam.com fabrikam.com True</span><span class="sxs-lookup"><span data-stu-id="691b3-115">fabrikam.com fabrikam.com True</span></span>

<span data-ttu-id="691b3-116">na.fabrikam.com na.fabrikam.com False</span><span class="sxs-lookup"><span data-stu-id="691b3-116">na.fabrikam.com na.fabrikam.com False</span></span>

<span data-ttu-id="691b3-117">如果 IsDefault 属性设置为 True，则相应的域是默认的 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="691b3-117">If the IsDefault property is set to True, the corresponding domain is your default SIP domain.</span></span> <span data-ttu-id="691b3-118">您可以使用 CsSipDomain cmdlet 更改组织的默认 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="691b3-118">You can use the Set-CsSipDomain cmdlet to change the default SIP domain for your organization.</span></span> <span data-ttu-id="691b3-119">但是，不能只删除默认的 SIP 域，因为这样做会导致没有默认域。</span><span class="sxs-lookup"><span data-stu-id="691b3-119">However, you can't just delete the default SIP domain because that would leave you without a default domain.</span></span> <span data-ttu-id="691b3-120">如果要删除 fabrikam.com 域（如前面的示例中所示），则必须首先将 na.fabrikam.com 配置为默认域。</span><span class="sxs-lookup"><span data-stu-id="691b3-120">If you wanted to delete the fabrikam.com domain (as shown in the previous example), you would first have to configure na.fabrikam.com to be your default domain.</span></span>

</div>

<div>

## <a name="check-meeting-settings"></a><span data-ttu-id="691b3-121">检查会议设置</span><span class="sxs-lookup"><span data-stu-id="691b3-121">Check meeting settings</span></span>

<span data-ttu-id="691b3-122">会议设置包括会议策略定义以及在会议中参与匿名用户的支持。</span><span class="sxs-lookup"><span data-stu-id="691b3-122">Meeting settings include meeting policy definitions and support for participation of anonymous users in meetings.</span></span>

<span data-ttu-id="691b3-123">可以使用 Windows PowerShell 和**get-csmeetingconfiguration** cmdlet 检索会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="691b3-123">Meeting configuration settings can be retrieved by using Windows PowerShell and the **Get-CsMeetingConfiguration** cmdlet.</span></span> <span data-ttu-id="691b3-124">例如，以下命令将返回有关全局会议配置设置的信息：</span><span class="sxs-lookup"><span data-stu-id="691b3-124">For example, this command returns information about the global meeting configuration settings:</span></span>

<span data-ttu-id="691b3-125">Get-csmeetingconfiguration –标识 "全局" 会议配置设置也可以在站点范围中进行配置。</span><span class="sxs-lookup"><span data-stu-id="691b3-125">Get-CsMeetingConfiguration –Identity "Global"Meeting configuration settings can also be configured at the site scope.</span></span> <span data-ttu-id="691b3-126">因此，您可能需要使用以下命令，该命令将返回有关所有会议配置设置的信息：</span><span class="sxs-lookup"><span data-stu-id="691b3-126">Because of that, you might want to use the following command, which returns information about all the meeting configuration settings:</span></span>

`Get-CsMeetingConfiguration`

<span data-ttu-id="691b3-127">**Get-csmeetingconfiguration** cmdlet 将返回类似于以下内容的信息：</span><span class="sxs-lookup"><span data-stu-id="691b3-127">The **Get-CsMeetingConfiguration** cmdlet returns information similar to the following:</span></span>

<span data-ttu-id="691b3-128">标识：全局</span><span class="sxs-lookup"><span data-stu-id="691b3-128">Identity : Global</span></span>

<span data-ttu-id="691b3-129">PstnCallersBypassLobby： True</span><span class="sxs-lookup"><span data-stu-id="691b3-129">PstnCallersBypassLobby : True</span></span>

<span data-ttu-id="691b3-130">EnableAssignedConferenceType： True</span><span class="sxs-lookup"><span data-stu-id="691b3-130">EnableAssignedConferenceType : True</span></span>

<span data-ttu-id="691b3-131">DesignateAsPresenter：公司</span><span class="sxs-lookup"><span data-stu-id="691b3-131">DesignateAsPresenter : Company</span></span>

<span data-ttu-id="691b3-132">AssignedConferenceTypeByDefault： True</span><span class="sxs-lookup"><span data-stu-id="691b3-132">AssignedConferenceTypeByDefault : True</span></span>

<span data-ttu-id="691b3-133">AdmitAnonymousUsersByDefault： True</span><span class="sxs-lookup"><span data-stu-id="691b3-133">AdmitAnonymousUsersByDefault : True</span></span>

<span data-ttu-id="691b3-134">同样，列表中的最后一项**AdmitAnonymousUsersByDefault**，启用或禁用匿名用户参与会议的功能。</span><span class="sxs-lookup"><span data-stu-id="691b3-134">Again, the final item in the list, **AdmitAnonymousUsersByDefault**, enables or disables the ability of anonymous users to participate in meetings.</span></span>

<span data-ttu-id="691b3-135">检查会议配置设置时，您可能会发现将当前设置与默认等效项进行比较非常有用。</span><span class="sxs-lookup"><span data-stu-id="691b3-135">When checking meeting configuration settings, you might find it useful to compare the current settings against the default equivalents.</span></span> <span data-ttu-id="691b3-136">您可以通过运行以下命令来查看默认会议配置设置：</span><span class="sxs-lookup"><span data-stu-id="691b3-136">You can view the default meeting configuration settings by running the following command:</span></span>

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="691b3-137">上一个命令创建全局会议配置设置的仅内存内部实例，该实例使用每个属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="691b3-137">The previous command creates an in-memory-only instance of the global meeting configuration settings, an instance that uses the default value for each property.</span></span> <span data-ttu-id="691b3-138">运行命令时，不会创建实际会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="691b3-138">No actual meeting configuration settings are created when you run the command.</span></span> <span data-ttu-id="691b3-139">但是，所有默认属性值都将显示在屏幕上。</span><span class="sxs-lookup"><span data-stu-id="691b3-139">However, all the default property values will be displayed on-screen.</span></span>

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a><span data-ttu-id="691b3-140">检查边缘服务器及其设置</span><span class="sxs-lookup"><span data-stu-id="691b3-140">Check Edge Servers and their settings</span></span>

<span data-ttu-id="691b3-141">可以使用 Windows PowerShell 检索边缘服务器信息。</span><span class="sxs-lookup"><span data-stu-id="691b3-141">Edge Server information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="691b3-142">此命令返回有关配置为在组织中使用的所有边缘服务器的信息：</span><span class="sxs-lookup"><span data-stu-id="691b3-142">This command returns information about all the Edge Servers configured for use in your organization:</span></span>

`Get-CsService -EdgeServer`

<span data-ttu-id="691b3-143">返回的信息包括每台边缘服务器的所有 FQDN 和端口设置：</span><span class="sxs-lookup"><span data-stu-id="691b3-143">The returned information includes all of the FQDN and port settings for each Edge Server:</span></span>

<span data-ttu-id="691b3-144">Identity： EdgeServer： dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="691b3-144">Identity : EdgeServer: dc.fabrikam.com</span></span>

<span data-ttu-id="691b3-145">注册器：注册器： LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="691b3-145">Registrar : Registrar: LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="691b3-146">AccessEdgeInternalSipPort：5061</span><span class="sxs-lookup"><span data-stu-id="691b3-146">AccessEdgeInternalSipPort : 5061</span></span>

<span data-ttu-id="691b3-147">AccessEdgeExternalSipPort：5061</span><span class="sxs-lookup"><span data-stu-id="691b3-147">AccessEdgeExternalSipPort : 5061</span></span>

<span data-ttu-id="691b3-148">AccessEdgeClientPort：443</span><span class="sxs-lookup"><span data-stu-id="691b3-148">AccessEdgeClientPort : 443</span></span>

<span data-ttu-id="691b3-149">DataPsomServerPort：8057</span><span class="sxs-lookup"><span data-stu-id="691b3-149">DataPsomServerPort : 8057</span></span>

<span data-ttu-id="691b3-150">DataPsomClientPort：444</span><span class="sxs-lookup"><span data-stu-id="691b3-150">DataPsomClientPort : 444</span></span>

<span data-ttu-id="691b3-151">MediaRelayAuthEdgePort：5062</span><span class="sxs-lookup"><span data-stu-id="691b3-151">MediaRelayAuthEdgePort : 5062</span></span>

<span data-ttu-id="691b3-152">MediaRelayAuthInternalTurnTcpPort：443</span><span class="sxs-lookup"><span data-stu-id="691b3-152">MediaRelayAuthInternalTurnTcpPort : 443</span></span>

<span data-ttu-id="691b3-153">MediaRelayAuthExternalTurnTcpPort：445</span><span class="sxs-lookup"><span data-stu-id="691b3-153">MediaRelayAuthExternalTurnTcpPort : 445</span></span>

<span data-ttu-id="691b3-154">MediaRelayAuthInternalTurnUdpPort：3478</span><span class="sxs-lookup"><span data-stu-id="691b3-154">MediaRelayAuthInternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="691b3-155">MediaRelayAuthExternalTurnUdpPort：3478</span><span class="sxs-lookup"><span data-stu-id="691b3-155">MediaRelayAuthExternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="691b3-156">MediaCommunicationPortStart：50000</span><span class="sxs-lookup"><span data-stu-id="691b3-156">MediaCommunicationPortStart : 50000</span></span>

<span data-ttu-id="691b3-157">MediaComunicationPortCount：10000</span><span class="sxs-lookup"><span data-stu-id="691b3-157">MediaComunicationPortCount : 10000</span></span>

<span data-ttu-id="691b3-158">AccessEdgeExternalFqdn： dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="691b3-158">AccessEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="691b3-159">DataEdgeExternalFqdn： dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="691b3-159">DataEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="691b3-160">AVEdgeExternalFqdn :</span><span class="sxs-lookup"><span data-stu-id="691b3-160">AVEdgeExternalFqdn :</span></span>

<span data-ttu-id="691b3-161">InternalInterfaceFqdn :</span><span class="sxs-lookup"><span data-stu-id="691b3-161">InternalInterfaceFqdn :</span></span>

<span data-ttu-id="691b3-162">ExternalMrasFqdn： dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="691b3-162">ExternalMrasFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="691b3-163">DependentServiceList： {注册器： LYNC-SE.fabrikam.com，</span><span class="sxs-lookup"><span data-stu-id="691b3-163">DependentServiceList : {Registrar:LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="691b3-164">ConferencingServer： LYNC-SE. fabrikam</span><span class="sxs-lookup"><span data-stu-id="691b3-164">ConferencingServer:LYNC-SE.fabrikam</span></span>

<span data-ttu-id="691b3-165">com，MediationServer： LYNC-SE。</span><span class="sxs-lookup"><span data-stu-id="691b3-165">com, MediationServer:LYNC-SE.</span></span>

<span data-ttu-id="691b3-166">fabrikam.com}</span><span class="sxs-lookup"><span data-stu-id="691b3-166">fabrikam.com}</span></span>

<span data-ttu-id="691b3-167">ServiceId： fabrikam.com-EdgeServer-2</span><span class="sxs-lookup"><span data-stu-id="691b3-167">ServiceId : fabrikam.com-EdgeServer-2</span></span>

<span data-ttu-id="691b3-168">SiteId： site:fabrikam</span><span class="sxs-lookup"><span data-stu-id="691b3-168">SiteId : site:fabrikam.com</span></span>

<span data-ttu-id="691b3-169">PoolFqdn： dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="691b3-169">PoolFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="691b3-170">版本：5</span><span class="sxs-lookup"><span data-stu-id="691b3-170">Version : 5</span></span>

<span data-ttu-id="691b3-171">Role： EdgeServer</span><span class="sxs-lookup"><span data-stu-id="691b3-171">Role : EdgeServer</span></span>

<div>

## <a name="check-federation-settings"></a><span data-ttu-id="691b3-172">检查联合身份验证设置</span><span class="sxs-lookup"><span data-stu-id="691b3-172">Check federation settings</span></span>

<span data-ttu-id="691b3-173">检查联合身份验证设置，如是否配置了联合身份验证设置，如果答案为 "是"，则为 FQDN 和端口。</span><span class="sxs-lookup"><span data-stu-id="691b3-173">Check Federation settings, such as whether it is configured and, if the answer is "yes,", the FQDN and port.</span></span> <span data-ttu-id="691b3-174">联合身份验证是通过使用访问边缘配置设置的全局集合启用和禁用的。</span><span class="sxs-lookup"><span data-stu-id="691b3-174">Federation is enabled and disabled by using the global collection of Access Edge configuration settings.</span></span> <span data-ttu-id="691b3-175">在其他情况下，这意味着联合是在全或无基础上配置的：为整个组织启用联盟或为整个组织禁用联盟</span><span class="sxs-lookup"><span data-stu-id="691b3-175">Among other things, these mean that federation is configured on an all-or-nothing basis: either federation is enabled for the whole organization or federation is disabled for the whole organization</span></span>

<span data-ttu-id="691b3-176">您可以使用 Windows PowerShell 返回您的访问边缘配置设置。</span><span class="sxs-lookup"><span data-stu-id="691b3-176">Your Access Edge configuration settings can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="691b3-177">为此，请运行以下 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="691b3-177">To do that, run the following Windows PowerShell command:</span></span>

`Get-CsAccessEdgeConfiguration`

<span data-ttu-id="691b3-178">反过来，该命令将返回类似于以下内容的数据：</span><span class="sxs-lookup"><span data-stu-id="691b3-178">In turn, that command will return data similar to this:</span></span>

<span data-ttu-id="691b3-179">标识：全局</span><span class="sxs-lookup"><span data-stu-id="691b3-179">Identity : Global</span></span>

<span data-ttu-id="691b3-180">AllowAnonymousUsers： False</span><span class="sxs-lookup"><span data-stu-id="691b3-180">AllowAnonymousUsers : False</span></span>

<span data-ttu-id="691b3-181">AllowFederatedUsers： False</span><span class="sxs-lookup"><span data-stu-id="691b3-181">AllowFederatedUsers : False</span></span>

<span data-ttu-id="691b3-182">AllowOutsideUsers： False</span><span class="sxs-lookup"><span data-stu-id="691b3-182">AllowOutsideUsers : False</span></span>

<span data-ttu-id="691b3-183">BeClearingHouse： False</span><span class="sxs-lookup"><span data-stu-id="691b3-183">BeClearingHouse : False</span></span>

<span data-ttu-id="691b3-184">EnablePartnerDiscovery： False</span><span class="sxs-lookup"><span data-stu-id="691b3-184">EnablePartnerDiscovery : False</span></span>

<span data-ttu-id="691b3-185">EnableArchivingDisclaimer： False</span><span class="sxs-lookup"><span data-stu-id="691b3-185">EnableArchivingDisclaimer : False</span></span>

<span data-ttu-id="691b3-186">KeepCrlsUpToDateForPeers： True</span><span class="sxs-lookup"><span data-stu-id="691b3-186">KeepCrlsUpToDateForPeers : True</span></span>

<span data-ttu-id="691b3-187">MarkSourceVerifiableOnOutgoingMessages： True</span><span class="sxs-lookup"><span data-stu-id="691b3-187">MarkSourceVerifiableOnOutgoingMessages : True</span></span>

<span data-ttu-id="691b3-188">OutgoingTlsCountForFederatedPartners：4</span><span class="sxs-lookup"><span data-stu-id="691b3-188">OutgoingTlsCountForFederatedPartners : 4</span></span>

<span data-ttu-id="691b3-189">RoutingMethod : UseDnsSrvRouting</span><span class="sxs-lookup"><span data-stu-id="691b3-189">RoutingMethod : UseDnsSrvRouting</span></span>

<span data-ttu-id="691b3-190">如果将**AllowFederatedUsers**属性设置为 True，则表示已为您的组织启用联盟。</span><span class="sxs-lookup"><span data-stu-id="691b3-190">If the **AllowFederatedUsers** property is set to True, that means that federation is enabled for your organization.</span></span> <span data-ttu-id="691b3-191">（将**AllowFederatedUsers**设置为 True 也意味着，在拆分域方案中，您的本地用户将能够与您的云中用户无缝通信。）</span><span class="sxs-lookup"><span data-stu-id="691b3-191">(Setting **AllowFederatedUsers** to True also means that, in a split domain scenario, your on-premises users will be able to communicate seamlessly with your in-the-cloud users.)</span></span>

<span data-ttu-id="691b3-192">若要检索边缘服务器的 FQDN 和端口设置，请参阅上一任务（边缘服务器及其设置）。</span><span class="sxs-lookup"><span data-stu-id="691b3-192">To retrieve the FQDN and port settings for your Edge Server, see the previous task (Edge Servers and their settings).</span></span>

<span data-ttu-id="691b3-193">在全局范围内启用联合仅意味着用户可以与联合用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="691b3-193">Enabling federation at the global scope only means that users can potentially communicate with federated users.</span></span> <span data-ttu-id="691b3-194">若要确定任何单个用户是否可以实际与联合用户通信，需要检查分配给该用户的外部用户访问策略。</span><span class="sxs-lookup"><span data-stu-id="691b3-194">To determine whether any individual users can actually communicate with federated users requires you to examine the external user access policy assigned to that user.</span></span>

<span data-ttu-id="691b3-195">可以使用 Windows PowerShell 返回外部用户访问信息。</span><span class="sxs-lookup"><span data-stu-id="691b3-195">External user access information can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="691b3-196">例如，以下命令将返回全局外部用户访问策略的信息：</span><span class="sxs-lookup"><span data-stu-id="691b3-196">For example, this command returns information for the global external user access policy:</span></span>

`Get-CsExternalAccessPolicy -Identity "Global"`

<span data-ttu-id="691b3-197">此命令将返回所有外部用户访问策略的信息：</span><span class="sxs-lookup"><span data-stu-id="691b3-197">And this command returns information for all the external user access policies:</span></span>

`Get-CsExternalAccessPolicy`

<span data-ttu-id="691b3-198">返回的信息将如下所示：</span><span class="sxs-lookup"><span data-stu-id="691b3-198">The returned information will resemble this:</span></span>

<span data-ttu-id="691b3-199">标识： False</span><span class="sxs-lookup"><span data-stu-id="691b3-199">Identity : False</span></span>

<span data-ttu-id="691b3-200">产品介绍</span><span class="sxs-lookup"><span data-stu-id="691b3-200">Description :</span></span>

<span data-ttu-id="691b3-201">EnableFederationAccess： False</span><span class="sxs-lookup"><span data-stu-id="691b3-201">EnableFederationAccess : False</span></span>

<span data-ttu-id="691b3-202">EnablePublicCloudAccess： False</span><span class="sxs-lookup"><span data-stu-id="691b3-202">EnablePublicCloudAccess : False</span></span>

<span data-ttu-id="691b3-203">EnablePublicCloudAccessAudioVideoAccess： False</span><span class="sxs-lookup"><span data-stu-id="691b3-203">EnablePublicCloudAccessAudioVideoAccess : False</span></span>

<span data-ttu-id="691b3-204">EnableOutsideAccess： False</span><span class="sxs-lookup"><span data-stu-id="691b3-204">EnableOutsideAccess : False</span></span>

<span data-ttu-id="691b3-205">如果将**EnableFederationAccess**设置为 True，则由给定策略管理的用户可以与联盟用户通信。</span><span class="sxs-lookup"><span data-stu-id="691b3-205">If **EnableFederationAccess** is set to True, then users managed by the given policy can communicate with federated users.</span></span>

</div>

</div>

<div>

## <a name="check-archiving-settings"></a><span data-ttu-id="691b3-206">检查存档设置</span><span class="sxs-lookup"><span data-stu-id="691b3-206">Check archiving settings</span></span>

<span data-ttu-id="691b3-207">检查内部和联合通信的存档设置。在验证内部存档和外部存档的设置之前，应验证是否已启用存档。</span><span class="sxs-lookup"><span data-stu-id="691b3-207">Check archiving settings for internal and federated communications.Before verifying the settings for internal and external archiving, you should verify that archiving is enabled.</span></span>

<span data-ttu-id="691b3-208">可以使用 Windows PowerShell 和 Set-csarchivingconfiguration cmdlet 来验证存档配置设置：</span><span class="sxs-lookup"><span data-stu-id="691b3-208">Archiving configuration settings can be verified by using Windows PowerShell and the Get-CsArchivingConfiguration cmdlet:</span></span>

`Get-CsArchivingConfiguration -Identity "Global"`

<span data-ttu-id="691b3-209">请注意，也可以在站点范围内配置存档设置。</span><span class="sxs-lookup"><span data-stu-id="691b3-209">Note that archiving settings can also be configured at the site scope.</span></span> <span data-ttu-id="691b3-210">若要返回有关所有存档设置的信息，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="691b3-210">To return information about all the archiving settings, use this command:</span></span>

`Get-CsArchivingConfiguration`

<span data-ttu-id="691b3-211">Set-csarchivingconfiguration cmdlet 返回与以下内容类似的数据：</span><span class="sxs-lookup"><span data-stu-id="691b3-211">The Get-CsArchivingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="691b3-212">标识：全局</span><span class="sxs-lookup"><span data-stu-id="691b3-212">Identity : Global</span></span>

<span data-ttu-id="691b3-213">EnableArchiving： False</span><span class="sxs-lookup"><span data-stu-id="691b3-213">EnableArchiving : False</span></span>

<span data-ttu-id="691b3-214">EnablePurging： False</span><span class="sxs-lookup"><span data-stu-id="691b3-214">EnablePurging : False</span></span>

<span data-ttu-id="691b3-215">PurgeExportedArchivesOnly： False</span><span class="sxs-lookup"><span data-stu-id="691b3-215">PurgeExportedArchivesOnly : False</span></span>

<span data-ttu-id="691b3-216">BlockOnArchiveFailure： False</span><span class="sxs-lookup"><span data-stu-id="691b3-216">BlockOnArchiveFailure : False</span></span>

<span data-ttu-id="691b3-217">KeepArchivingDataForDays：14</span><span class="sxs-lookup"><span data-stu-id="691b3-217">KeepArchivingDataForDays : 14</span></span>

<span data-ttu-id="691b3-218">PurgeHourOfDay：2</span><span class="sxs-lookup"><span data-stu-id="691b3-218">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="691b3-219">ArchiveDuplicateMessages： True</span><span class="sxs-lookup"><span data-stu-id="691b3-219">ArchiveDuplicateMessages : True</span></span>

<span data-ttu-id="691b3-220">CachePurgingInterval：24</span><span class="sxs-lookup"><span data-stu-id="691b3-220">CachePurgingInterval : 24</span></span>

<span data-ttu-id="691b3-221">如果将 EnableArchiving 属性设置为 False，则意味着将不会存档任何通信会话。</span><span class="sxs-lookup"><span data-stu-id="691b3-221">If the EnableArchiving property is set to False, that means that no communication sessions will be archived.</span></span> <span data-ttu-id="691b3-222">如果只想存档即时消息会话，请使用如下所示的命令来启用 IM 会话的存档：</span><span class="sxs-lookup"><span data-stu-id="691b3-222">If you want to archive instant messaging sessions only, use a command such as the following to enable the archiving of IM sessions:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="691b3-223">若要存档会议会话和即时消息会话，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="691b3-223">To archive conferencing sessions and instant messaging sessions, use this command:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="691b3-224">如果您想要将当前存档设置与默认设置进行比较，请运行以下 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="691b3-224">If you’d like to compare your current archiving settings with the default settings, run the following Windows PowerShell command:</span></span>

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="691b3-225">该命令将创建全局存档配置设置的仅内存中的实例。</span><span class="sxs-lookup"><span data-stu-id="691b3-225">That command creates an in-memory-only instance of the global archiving configuration settings.</span></span> <span data-ttu-id="691b3-226">这不是由 Lync Server 使用的真实设置集合。</span><span class="sxs-lookup"><span data-stu-id="691b3-226">This is not a real collection of settings that is used by Lync Server.</span></span> <span data-ttu-id="691b3-227">但是，它确实显示所有存档配置属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="691b3-227">However, it does display the default values for all the archiving configuration properties.</span></span>

<span data-ttu-id="691b3-228">您还可以使用此命令返回存档服务器的 FQDN：</span><span class="sxs-lookup"><span data-stu-id="691b3-228">You can also use this command to return the FQDN of your Archiving servers:</span></span>

`Get-CsService -ArchivingServer`

<span data-ttu-id="691b3-229">验证是否已启用存档后，可以查看存档策略，以确定是否正在存档内部和外部通信会话。</span><span class="sxs-lookup"><span data-stu-id="691b3-229">After you have verified that archiving is enabled, you can then view your archiving policies to determine whether internal and external communication sessions are being archived.</span></span>

<span data-ttu-id="691b3-230">可以使用 New-csarchivingpolicy cmdlet 检索存档策略信息。</span><span class="sxs-lookup"><span data-stu-id="691b3-230">Archiving policy information can be retrieved by using the Get-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="691b3-231">例如，以下命令将返回有关全局存档策略的信息：</span><span class="sxs-lookup"><span data-stu-id="691b3-231">For example, this command returns information about the global archiving policy:</span></span>

`Get-CsArchivingPolicy -Identity "Global"`

<span data-ttu-id="691b3-232">由于还可以在网站和每用户范围中配置存档策略，因此您可能还需要使用此命令，该命令将返回有关所有存档策略的信息：</span><span class="sxs-lookup"><span data-stu-id="691b3-232">Because archiving policies can also be configured at the site and the per-user scope, you might also want to use this command, which returns information about all the archiving policies:</span></span>

`Get-CsArchivingPolicy`

<span data-ttu-id="691b3-233">从 New-csarchivingpolicy 接收到的信息将与以下内容类似：</span><span class="sxs-lookup"><span data-stu-id="691b3-233">The information that you receive from Get-CsArchivingPolicy will resemble this:</span></span>

<span data-ttu-id="691b3-234">标识：全局</span><span class="sxs-lookup"><span data-stu-id="691b3-234">Identity : Global</span></span>

<span data-ttu-id="691b3-235">产品介绍</span><span class="sxs-lookup"><span data-stu-id="691b3-235">Description :</span></span>

<span data-ttu-id="691b3-236">ArchiveInternal： False</span><span class="sxs-lookup"><span data-stu-id="691b3-236">ArchiveInternal : False</span></span>

<span data-ttu-id="691b3-237">ArchiveExternal： False</span><span class="sxs-lookup"><span data-stu-id="691b3-237">ArchiveExternal : False</span></span>

<span data-ttu-id="691b3-238">请注意，默认情况下，在存档策略中禁用内部存档和外部存档。</span><span class="sxs-lookup"><span data-stu-id="691b3-238">Note that, by default, both internal and external archiving are disabled in an archiving policy.</span></span>

</div>

<div>

## <a name="check-cdr-settings"></a><span data-ttu-id="691b3-239">检查 CDR 设置</span><span class="sxs-lookup"><span data-stu-id="691b3-239">Check CDR settings</span></span>

<span data-ttu-id="691b3-240">检查对等、会议和语音呼叫详细记录的呼叫详细信息记录（CDR）设置。</span><span class="sxs-lookup"><span data-stu-id="691b3-240">Check Call Detail Record (CDR) settings for peer-to-peer, conferencing, and Voice call detail recording.</span></span> <span data-ttu-id="691b3-241">可以使用**set-cscdrconfiguration** cmdlet 返回有关 CDR 设置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="691b3-241">Detailed information about your CDR settings can be returned by using the **Get-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="691b3-242">例如，以下命令将返回有关 CDR 配置设置的全局集合的信息：</span><span class="sxs-lookup"><span data-stu-id="691b3-242">For example, this command returns information about the global collection of CDR configuration settings:</span></span>

`Get-CsCdrConfiguration -Identity "Global"`

<span data-ttu-id="691b3-243">由于也可以在站点范围配置 CDR，因此您可能还需要运行以下命令，该命令将返回有关所有 CDR 配置设置的信息：</span><span class="sxs-lookup"><span data-stu-id="691b3-243">Because CDR can also be configured at the site scope, you might also want to run this command, which returns information about all the CDR configuration settings:</span></span>

`Get-CsCdrConfiguration`

<span data-ttu-id="691b3-244">Set-cscdrconfiguration cmdlet 为每个 CDR 配置设置集合返回类似于以下内容的信息：</span><span class="sxs-lookup"><span data-stu-id="691b3-244">The Get-CsCdrConfiguration cmdlet returns information similar to this for each collection of CDR configuration settings:</span></span>

<span data-ttu-id="691b3-245">标识：全局</span><span class="sxs-lookup"><span data-stu-id="691b3-245">Identity : Global</span></span>

<span data-ttu-id="691b3-246">EnableCDR： True</span><span class="sxs-lookup"><span data-stu-id="691b3-246">EnableCDR : True</span></span>

<span data-ttu-id="691b3-247">EnablePurging： True</span><span class="sxs-lookup"><span data-stu-id="691b3-247">EnablePurging : True</span></span>

<span data-ttu-id="691b3-248">KeepCallDetailForDays：60</span><span class="sxs-lookup"><span data-stu-id="691b3-248">KeepCallDetailForDays : 60</span></span>

<span data-ttu-id="691b3-249">KeepErrorReportForDays：60</span><span class="sxs-lookup"><span data-stu-id="691b3-249">KeepErrorReportForDays : 60</span></span>

<span data-ttu-id="691b3-250">PurgeHourOfDay：2</span><span class="sxs-lookup"><span data-stu-id="691b3-250">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="691b3-251">可以通过使用 New-csqoeconfiguration cmdlet 为 QoE 监视返回类似的信息。</span><span class="sxs-lookup"><span data-stu-id="691b3-251">Similar information can be returned for QoE monitoring by using the Get-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="691b3-252">例如，以下命令将返回有关 QoE 配置设置的全局集合的信息：</span><span class="sxs-lookup"><span data-stu-id="691b3-252">For example, this command returns information about the global collection of QoE configuration settings:</span></span>

`Get-QoEConfiguration -Identity "Global"`

<span data-ttu-id="691b3-253">该信息将类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="691b3-253">That information will resemble this:</span></span>

<span data-ttu-id="691b3-254">标识：全局</span><span class="sxs-lookup"><span data-stu-id="691b3-254">Identity : Global</span></span>

<span data-ttu-id="691b3-255">ExternalConsumerIssuedCertId :</span><span class="sxs-lookup"><span data-stu-id="691b3-255">ExternalConsumerIssuedCertId :</span></span>

<span data-ttu-id="691b3-256">EnablePurging： True</span><span class="sxs-lookup"><span data-stu-id="691b3-256">EnablePurging : True</span></span>

<span data-ttu-id="691b3-257">KeepQoEDataForDays：60</span><span class="sxs-lookup"><span data-stu-id="691b3-257">KeepQoEDataForDays : 60</span></span>

<span data-ttu-id="691b3-258">PurgeHourOfDay：1</span><span class="sxs-lookup"><span data-stu-id="691b3-258">PurgeHourOfDay : 1</span></span>

<span data-ttu-id="691b3-259">EnableExternalConsumer： False</span><span class="sxs-lookup"><span data-stu-id="691b3-259">EnableExternalConsumer : False</span></span>

<span data-ttu-id="691b3-260">ExternalConsumerName :</span><span class="sxs-lookup"><span data-stu-id="691b3-260">ExternalConsumerName :</span></span>

<span data-ttu-id="691b3-261">ExternalConsumerURL :</span><span class="sxs-lookup"><span data-stu-id="691b3-261">ExternalConsumerURL :</span></span>

<span data-ttu-id="691b3-262">EnableQoE： True</span><span class="sxs-lookup"><span data-stu-id="691b3-262">EnableQoE : True</span></span>

<span data-ttu-id="691b3-263">如果要将当前 CDR 设置与默认 CDR 设置进行比较，可以通过运行以下命令来查看默认值：</span><span class="sxs-lookup"><span data-stu-id="691b3-263">If you want to compare your current CDR settings with the default CDR settings, the default values can be reviewed by running this command:</span></span>

`New-CsCdrConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="691b3-264">同样，可以使用以下命令检索 QoE monitoring 的默认值：</span><span class="sxs-lookup"><span data-stu-id="691b3-264">Likewise, the default values for QoE monitoring can be retrieved by using this command:</span></span>

`New-CsQoEConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="691b3-265">您还可以通过运行以下命令返回您的监视服务器的 FQDN：</span><span class="sxs-lookup"><span data-stu-id="691b3-265">You can also return the FQDN of your Monitoring servers by running this command:</span></span>

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a><span data-ttu-id="691b3-266">检查语音设置</span><span class="sxs-lookup"><span data-stu-id="691b3-266">Check voice settings</span></span>

<span data-ttu-id="691b3-267">语音设置对于管理员来说通常很重要的信息包含在语音策略和语音路由中：语音策略包含用于确定向单个用户公开的功能的设置（例如，转发或转移呼叫的能力），同时语音路由决定了在 PSTN 中路由呼叫的方式（和 if）。</span><span class="sxs-lookup"><span data-stu-id="691b3-267">The voice settings typically important to administrators are contained in voice policies and voice routes: voice policies contain the settings that determine the capabilities exposed to individual users (such as the ability to forward or transfer calls), while voice routes determine how (and if) calls are routed across the PSTN.</span></span>

<span data-ttu-id="691b3-268">可以使用 Windows PowerShell 检索语音策略信息。</span><span class="sxs-lookup"><span data-stu-id="691b3-268">Voice policy information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="691b3-269">例如，以下命令将返回有关全局语音策略的信息：</span><span class="sxs-lookup"><span data-stu-id="691b3-269">For example, this command returns information about the global voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global"`

<span data-ttu-id="691b3-270">此命令将返回有关已配置为在组织中使用的所有语音策略的信息：</span><span class="sxs-lookup"><span data-stu-id="691b3-270">And this command returns information about all the voice policies configured for use in the organization:</span></span>

`Get-CsVoicePolicy`

<span data-ttu-id="691b3-271">Set-csvoicepolicy cmdlet 返回的信息类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="691b3-271">The information returned by the Get-CsVoicePolicy cmdlet resembles the following:</span></span>

<span data-ttu-id="691b3-272">标识：全局</span><span class="sxs-lookup"><span data-stu-id="691b3-272">Identity : Global</span></span>

<span data-ttu-id="691b3-273">PstnUsages{}</span><span class="sxs-lookup"><span data-stu-id="691b3-273">PstnUsages : {}</span></span>

<span data-ttu-id="691b3-274">产品介绍</span><span class="sxs-lookup"><span data-stu-id="691b3-274">Description :</span></span>

<span data-ttu-id="691b3-275">AllowSimulRing： True</span><span class="sxs-lookup"><span data-stu-id="691b3-275">AllowSimulRing : True</span></span>

<span data-ttu-id="691b3-276">AllowCallForwarding： True</span><span class="sxs-lookup"><span data-stu-id="691b3-276">AllowCallForwarding : True</span></span>

<span data-ttu-id="691b3-277">AllowPSTNReRouting： True</span><span class="sxs-lookup"><span data-stu-id="691b3-277">AllowPSTNReRouting : True</span></span>

<span data-ttu-id="691b3-278">名称： DefaultPolicy</span><span class="sxs-lookup"><span data-stu-id="691b3-278">Name : DefaultPolicy</span></span>

<span data-ttu-id="691b3-279">EnableDelegation： True</span><span class="sxs-lookup"><span data-stu-id="691b3-279">EnableDelegation : True</span></span>

<span data-ttu-id="691b3-280">EnableTeamCall： True</span><span class="sxs-lookup"><span data-stu-id="691b3-280">EnableTeamCall : True</span></span>

<span data-ttu-id="691b3-281">EnableCallTransfer： True</span><span class="sxs-lookup"><span data-stu-id="691b3-281">EnableCallTransfer : True</span></span>

<span data-ttu-id="691b3-282">EnableCallPark： False</span><span class="sxs-lookup"><span data-stu-id="691b3-282">EnableCallPark : False</span></span>

<span data-ttu-id="691b3-283">EnableMaliciousCallTracing： False</span><span class="sxs-lookup"><span data-stu-id="691b3-283">EnableMaliciousCallTracing : False</span></span>

<span data-ttu-id="691b3-284">EnableBWPolicyOverride： False</span><span class="sxs-lookup"><span data-stu-id="691b3-284">EnableBWPolicyOverride : False</span></span>

<span data-ttu-id="691b3-285">PreventPSTNTollBypass： False</span><span class="sxs-lookup"><span data-stu-id="691b3-285">PreventPSTNTollBypass : False</span></span>

<span data-ttu-id="691b3-286">您还可以创建返回语音策略子集的查询。</span><span class="sxs-lookup"><span data-stu-id="691b3-286">You can also create queries that returned a subset of your voice policies.</span></span> <span data-ttu-id="691b3-287">例如，以下命令将返回所有允许呼叫转接的语音策略：</span><span class="sxs-lookup"><span data-stu-id="691b3-287">For example, this command returns all the voice policies that allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

<span data-ttu-id="691b3-288">此命令将返回不允许呼叫转接的所有语音策略：</span><span class="sxs-lookup"><span data-stu-id="691b3-288">And this command returns all the voice policies that don’t allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

<span data-ttu-id="691b3-289">在 Windows PowerShell 中，使用 CsVoiceRouting cmdlet 可返回有关语音路由的信息：</span><span class="sxs-lookup"><span data-stu-id="691b3-289">In Windows PowerShell, use the Get-CsVoiceRouting cmdlet to return information about your voice routes:</span></span>

`Get-CsVoiceRoute`

<span data-ttu-id="691b3-290">该命令将返回类似于所有语音路由的信息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="691b3-290">That command returns information such as this for all the voice routes:</span></span>

<span data-ttu-id="691b3-291">标识： LocalRoute</span><span class="sxs-lookup"><span data-stu-id="691b3-291">Identity : LocalRoute</span></span>

<span data-ttu-id="691b3-292">优先级：0</span><span class="sxs-lookup"><span data-stu-id="691b3-292">Priority : 0</span></span>

<span data-ttu-id="691b3-293">产品介绍</span><span class="sxs-lookup"><span data-stu-id="691b3-293">Description :</span></span>

<span data-ttu-id="691b3-294">NumberPattern： ^ （\\+ 1\[0-9\]{10}） $</span><span class="sxs-lookup"><span data-stu-id="691b3-294">NumberPattern : ^(\\+1\[0-9\]{10})$</span></span>

<span data-ttu-id="691b3-295">PstnUsages{}</span><span class="sxs-lookup"><span data-stu-id="691b3-295">PstnUsages : {}</span></span>

<span data-ttu-id="691b3-296">PstnGatewayList :{}</span><span class="sxs-lookup"><span data-stu-id="691b3-296">PstnGatewayList : {}</span></span>

<span data-ttu-id="691b3-297">名称： LocalRoute</span><span class="sxs-lookup"><span data-stu-id="691b3-297">Name : LocalRoute</span></span>

<span data-ttu-id="691b3-298">SuppressCallerId :</span><span class="sxs-lookup"><span data-stu-id="691b3-298">SuppressCallerId :</span></span>

<span data-ttu-id="691b3-299">AlternateCallerId :</span><span class="sxs-lookup"><span data-stu-id="691b3-299">AlternateCallerId :</span></span>

<span data-ttu-id="691b3-300">Lync Server 允许您创建没有 PSTN 用法且未指定 PSTN 网关的语音路由。</span><span class="sxs-lookup"><span data-stu-id="691b3-300">Lync Server allows you to create voice routes that do not have a PSTN usage and do not specify a PSTN gateway.</span></span> <span data-ttu-id="691b3-301">但是，不能实际通过未配置这两个属性值的语音路由路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="691b3-301">However, you can't actually route calls over a voice route that does not have these two property values configured.</span></span> <span data-ttu-id="691b3-302">因此，您可能会发现，定期运行此命令会很有用，后者将返回没有 PSTN 用法的任何语音路由的标识：</span><span class="sxs-lookup"><span data-stu-id="691b3-302">Because of that, you might find it useful to periodically run this command, which returns the identity of any voice route that does not have a PSTN usage:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

<span data-ttu-id="691b3-303">同样，此命令将返回尚未配置为具有 PSTN 网关的任何语音路由的标识：</span><span class="sxs-lookup"><span data-stu-id="691b3-303">Similarly, this command returns the identity of any voice route that has not been configured to have a PSTN gateway:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a><span data-ttu-id="691b3-304">检查会议助理设置</span><span class="sxs-lookup"><span data-stu-id="691b3-304">Check Conferencing Attendant settings</span></span>

<span data-ttu-id="691b3-305">检查 PSTN 电话拨入式会议的会议助理设置。</span><span class="sxs-lookup"><span data-stu-id="691b3-305">Check conferencing Attendant settings for PSTN dial-in conferencing.</span></span> <span data-ttu-id="691b3-306">只能使用**set-csdialinconferencingconfiguration** cmdlet 来检索会议助理设置。</span><span class="sxs-lookup"><span data-stu-id="691b3-306">Conferencing Attendant settings can only be retrieved by using the **Get-CsDialInConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="691b3-307">这些设置在 "Lync Server 控制面板" 中不可用。</span><span class="sxs-lookup"><span data-stu-id="691b3-307">These settings are not available in the Lync Server Control Panel.</span></span> <span data-ttu-id="691b3-308">若要查看会议助理设置，请使用与以下内容类似的 Windows PowerShell 命令，该命令将返回全局会议助理设置集合：</span><span class="sxs-lookup"><span data-stu-id="691b3-308">To view your Conferencing Attendant settings, use a Windows PowerShell command similar to the following, which returns the global collection of Conferencing Attendant settings:</span></span>

`Get-CsDialInConferencingConfiguration -Identity "Global"`

<span data-ttu-id="691b3-309">请注意，还可以在站点范围内配置会议助理设置。</span><span class="sxs-lookup"><span data-stu-id="691b3-309">Note that Conferencing Attendant settings can also be configured at the site scope.</span></span> <span data-ttu-id="691b3-310">若要返回有关所有会议助理设置的信息，请改为使用此命令：</span><span class="sxs-lookup"><span data-stu-id="691b3-310">To return information about all the Conferencing Attendant settings, use this command instead:</span></span>

`Get-CsDialInConferencingConfiguration`

<span data-ttu-id="691b3-311">Set-csdialinconferencingconfiguration cmdlet 返回与以下内容类似的数据：</span><span class="sxs-lookup"><span data-stu-id="691b3-311">The Get-CsDialInConferencingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="691b3-312">标识：全局</span><span class="sxs-lookup"><span data-stu-id="691b3-312">Identity : Global</span></span>

<span data-ttu-id="691b3-313">EntryExitAnnouncementsType : UseNames</span><span class="sxs-lookup"><span data-stu-id="691b3-313">EntryExitAnnouncementsType : UseNames</span></span>

<span data-ttu-id="691b3-314">EnableNameRecording： True</span><span class="sxs-lookup"><span data-stu-id="691b3-314">EnableNameRecording : True</span></span>

<span data-ttu-id="691b3-315">EntryExitAnnouncementsEnabledByDefault： False</span><span class="sxs-lookup"><span data-stu-id="691b3-315">EntryExitAnnouncementsEnabledByDefault : False</span></span>

<span data-ttu-id="691b3-316">如果 EntryExitAnnouncementsEnabledByDefault 设置为 False，则表示已禁用会议通知。</span><span class="sxs-lookup"><span data-stu-id="691b3-316">If EntryExitAnnouncementsEnabledByDefault is set to False, that means the conferencing announcements are disabled.</span></span> <span data-ttu-id="691b3-317">若要启用进入和退出通知，请运行与以下内容类似的 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="691b3-317">To enable entry and exit announcements, run a Windows PowerShell command similar to this:</span></span>

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="691b3-318">另请参阅</span><span class="sxs-lookup"><span data-stu-id="691b3-318">See Also</span></span>


[<span data-ttu-id="691b3-319">CsSipDomain</span><span class="sxs-lookup"><span data-stu-id="691b3-319">Get-CsSipDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[<span data-ttu-id="691b3-320">Get-csmeetingconfiguration</span><span class="sxs-lookup"><span data-stu-id="691b3-320">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[<span data-ttu-id="691b3-321">Get-csservice</span><span class="sxs-lookup"><span data-stu-id="691b3-321">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="691b3-322">Set-csaccessedgeconfiguration</span><span class="sxs-lookup"><span data-stu-id="691b3-322">Get-CsAccessEdgeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[<span data-ttu-id="691b3-323">Set-csexternalaccesspolicy</span><span class="sxs-lookup"><span data-stu-id="691b3-323">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="691b3-324">Set-csarchivingconfiguration</span><span class="sxs-lookup"><span data-stu-id="691b3-324">Get-CsArchivingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[<span data-ttu-id="691b3-325">Set-cscdrconfiguration</span><span class="sxs-lookup"><span data-stu-id="691b3-325">Get-CsCdrConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[<span data-ttu-id="691b3-326">New-csqoeconfiguration</span><span class="sxs-lookup"><span data-stu-id="691b3-326">Get-CsQoEConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[<span data-ttu-id="691b3-327">Set-csvoicepolicy</span><span class="sxs-lookup"><span data-stu-id="691b3-327">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="691b3-328">CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="691b3-328">Get-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[<span data-ttu-id="691b3-329">Set-csdialinconferencingconfiguration</span><span class="sxs-lookup"><span data-stu-id="691b3-329">Get-CsDialInConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

