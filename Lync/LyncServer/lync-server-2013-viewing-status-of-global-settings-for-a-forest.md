---
title: 'Lync Server 2013: 查看林全局设置的状态'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2215e0514f019e94467a204ae86e604dcc0da61
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a><span data-ttu-id="d812e-102">查看 Lync Server 2013 中的林全局设置的状态</span><span class="sxs-lookup"><span data-stu-id="d812e-102">View status of global settings for a forest in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d812e-103">_**主题上次修改时间:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="d812e-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="d812e-104">管理员应每月查看 Lync Server 2013 部署的全局设置。</span><span class="sxs-lookup"><span data-stu-id="d812e-104">Administrators should review the global settings for a Lync Server 2013 deployment monthly.</span></span> <span data-ttu-id="d812e-105">目标是针对一组已知的配置查看实施的设置-基准配置, 以帮助确保设置有效, 并确定是否应更新基准文档。</span><span class="sxs-lookup"><span data-stu-id="d812e-105">The objective would be to review implemented settings against a set of known configurations—a baseline configuration to help guarantee that settings are valid and to determine whether the baseline documentation should be updated.</span></span> <span data-ttu-id="d812e-106">对全局设置所做的更改应通过更改控制过程实现, 该过程应包括记录新设置。</span><span class="sxs-lookup"><span data-stu-id="d812e-106">Changes to global setting should be implemented through a Change Control process which should include documenting the new settings.</span></span>

<span data-ttu-id="d812e-107">应查看的全局设置将在以下部分中介绍:</span><span class="sxs-lookup"><span data-stu-id="d812e-107">Global settings that should be reviewed are described in the following sections:</span></span>

<div>

## <a name="check-general-settings"></a><span data-ttu-id="d812e-108">检查常规设置</span><span class="sxs-lookup"><span data-stu-id="d812e-108">Check general settings</span></span>

<span data-ttu-id="d812e-109">检查常规设置, 包括 Lync Server 2013 受支持的会话初始协议 (SIP) 域。</span><span class="sxs-lookup"><span data-stu-id="d812e-109">Check general settings, including the supported Session Initiation Protocol (SIP) domains for Lync Server 2013.</span></span>

<span data-ttu-id="d812e-110">SIP 域信息可通过使用 Windows PowerShell 和**CsSipDomain** cmdlet 返回。</span><span class="sxs-lookup"><span data-stu-id="d812e-110">SIP domain information can be returned by using Windows PowerShell and the **Get-CsSipDomain** cmdlet.</span></span> <span data-ttu-id="d812e-111">若要返回此信息, 请`Get-CsSipDomain`运行 Windows PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="d812e-111">To return this information, run the `Get-CsSipDomain` Windows PowerShell command.</span></span>

<span data-ttu-id="d812e-112">对于所有授权 SIP 域, CsSipDomain 将返回与以下内容类似的信息:</span><span class="sxs-lookup"><span data-stu-id="d812e-112">Get-CsSipDomain will return information similar to this for all the authorized SIP domains:</span></span>

<span data-ttu-id="d812e-113">标识名称 IsDefault</span><span class="sxs-lookup"><span data-stu-id="d812e-113">Identity Name IsDefault</span></span>

<span data-ttu-id="d812e-114">\-------- ---- ---------</span><span class="sxs-lookup"><span data-stu-id="d812e-114"></span></span>

<span data-ttu-id="d812e-115">fabrikam.com fabrikam.com True</span><span class="sxs-lookup"><span data-stu-id="d812e-115">fabrikam.com fabrikam.com True</span></span>

<span data-ttu-id="d812e-116">na.fabrikam.com na.fabrikam.com False</span><span class="sxs-lookup"><span data-stu-id="d812e-116">na.fabrikam.com na.fabrikam.com False</span></span>

<span data-ttu-id="d812e-117">如果 IsDefault 属性设置为 True, 则相应的域是默认 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="d812e-117">If the IsDefault property is set to True, the corresponding domain is your default SIP domain.</span></span> <span data-ttu-id="d812e-118">你可以使用 CsSipDomain cmdlet 更改你的组织的默认 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="d812e-118">You can use the Set-CsSipDomain cmdlet to change the default SIP domain for your organization.</span></span> <span data-ttu-id="d812e-119">但是, 不能只是删除默认 SIP 域, 因为这样做将不使用默认域。</span><span class="sxs-lookup"><span data-stu-id="d812e-119">However, you can't just delete the default SIP domain because that would leave you without a default domain.</span></span> <span data-ttu-id="d812e-120">如果想要删除 fabrikam.com 域 (如前面的示例所示), 则必须首先将 na.fabrikam.com 配置为默认域。</span><span class="sxs-lookup"><span data-stu-id="d812e-120">If you wanted to delete the fabrikam.com domain (as shown in the previous example), you would first have to configure na.fabrikam.com to be your default domain.</span></span>

</div>

<div>

## <a name="check-meeting-settings"></a><span data-ttu-id="d812e-121">检查会议设置</span><span class="sxs-lookup"><span data-stu-id="d812e-121">Check meeting settings</span></span>

<span data-ttu-id="d812e-122">会议设置包括会议策略定义和在会议中参与匿名用户的支持。</span><span class="sxs-lookup"><span data-stu-id="d812e-122">Meeting settings include meeting policy definitions and support for participation of anonymous users in meetings.</span></span>

<span data-ttu-id="d812e-123">可使用 Windows PowerShell 和**CsMeetingConfiguration** cmdlet 检索会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="d812e-123">Meeting configuration settings can be retrieved by using Windows PowerShell and the **Get-CsMeetingConfiguration** cmdlet.</span></span> <span data-ttu-id="d812e-124">例如, 以下命令将返回有关全局会议配置设置的信息:</span><span class="sxs-lookup"><span data-stu-id="d812e-124">For example, this command returns information about the global meeting configuration settings:</span></span>

<span data-ttu-id="d812e-125">CsMeetingConfiguration –标识 "全局" 会议配置设置也可以在网站范围内进行配置。</span><span class="sxs-lookup"><span data-stu-id="d812e-125">Get-CsMeetingConfiguration –Identity "Global"Meeting configuration settings can also be configured at the site scope.</span></span> <span data-ttu-id="d812e-126">因此, 你可能需要使用以下命令, 该命令将返回有关所有会议配置设置的信息:</span><span class="sxs-lookup"><span data-stu-id="d812e-126">Because of that, you might want to use the following command, which returns information about all the meeting configuration settings:</span></span>

`Get-CsMeetingConfiguration`

<span data-ttu-id="d812e-127">**CsMeetingConfiguration** cmdlet 返回类似于以下内容的信息:</span><span class="sxs-lookup"><span data-stu-id="d812e-127">The **Get-CsMeetingConfiguration** cmdlet returns information similar to the following:</span></span>

<span data-ttu-id="d812e-128">标识: 全局</span><span class="sxs-lookup"><span data-stu-id="d812e-128">Identity : Global</span></span>

<span data-ttu-id="d812e-129">PstnCallersBypassLobby: True</span><span class="sxs-lookup"><span data-stu-id="d812e-129">PstnCallersBypassLobby : True</span></span>

<span data-ttu-id="d812e-130">EnableAssignedConferenceType: True</span><span class="sxs-lookup"><span data-stu-id="d812e-130">EnableAssignedConferenceType : True</span></span>

<span data-ttu-id="d812e-131">DesignateAsPresenter: 公司</span><span class="sxs-lookup"><span data-stu-id="d812e-131">DesignateAsPresenter : Company</span></span>

<span data-ttu-id="d812e-132">AssignedConferenceTypeByDefault: True</span><span class="sxs-lookup"><span data-stu-id="d812e-132">AssignedConferenceTypeByDefault : True</span></span>

<span data-ttu-id="d812e-133">AdmitAnonymousUsersByDefault: True</span><span class="sxs-lookup"><span data-stu-id="d812e-133">AdmitAnonymousUsersByDefault : True</span></span>

<span data-ttu-id="d812e-134">同样, **AdmitAnonymousUsersByDefault**列表中的最后一个项目可启用或禁用匿名用户参与会议的能力。</span><span class="sxs-lookup"><span data-stu-id="d812e-134">Again, the final item in the list, **AdmitAnonymousUsersByDefault**, enables or disables the ability of anonymous users to participate in meetings.</span></span>

<span data-ttu-id="d812e-135">检查会议配置设置时, 你可能会发现将当前设置与默认等效项进行比较非常有用。</span><span class="sxs-lookup"><span data-stu-id="d812e-135">When checking meeting configuration settings, you might find it useful to compare the current settings against the default equivalents.</span></span> <span data-ttu-id="d812e-136">可以通过运行以下命令来查看默认会议配置设置:</span><span class="sxs-lookup"><span data-stu-id="d812e-136">You can view the default meeting configuration settings by running the following command:</span></span>

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="d812e-137">上一个命令创建全局会议配置设置的仅内存实例, 该实例使用每个属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="d812e-137">The previous command creates an in-memory-only instance of the global meeting configuration settings, an instance that uses the default value for each property.</span></span> <span data-ttu-id="d812e-138">运行命令时, 不会创建实际会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="d812e-138">No actual meeting configuration settings are created when you run the command.</span></span> <span data-ttu-id="d812e-139">但是, 所有默认属性值都将显示在屏幕上。</span><span class="sxs-lookup"><span data-stu-id="d812e-139">However, all the default property values will be displayed on-screen.</span></span>

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a><span data-ttu-id="d812e-140">检查边缘服务器及其设置</span><span class="sxs-lookup"><span data-stu-id="d812e-140">Check Edge Servers and their settings</span></span>

<span data-ttu-id="d812e-141">可以使用 Windows PowerShell 检索边缘服务器信息。</span><span class="sxs-lookup"><span data-stu-id="d812e-141">Edge Server information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="d812e-142">此命令将返回有关所有配置为在你的组织中使用的边缘服务器的信息:</span><span class="sxs-lookup"><span data-stu-id="d812e-142">This command returns information about all the Edge Servers configured for use in your organization:</span></span>

`Get-CsService -EdgeServer`

<span data-ttu-id="d812e-143">返回的信息包括每台边缘服务器的所有 FQDN 和端口设置:</span><span class="sxs-lookup"><span data-stu-id="d812e-143">The returned information includes all of the FQDN and port settings for each Edge Server:</span></span>

<span data-ttu-id="d812e-144">标识: EdgeServer: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d812e-144">Identity : EdgeServer: dc.fabrikam.com</span></span>

<span data-ttu-id="d812e-145">注册机构: 注册机构: LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d812e-145">Registrar : Registrar: LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="d812e-146">AccessEdgeInternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="d812e-146">AccessEdgeInternalSipPort : 5061</span></span>

<span data-ttu-id="d812e-147">AccessEdgeExternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="d812e-147">AccessEdgeExternalSipPort : 5061</span></span>

<span data-ttu-id="d812e-148">AccessEdgeClientPort: 443</span><span class="sxs-lookup"><span data-stu-id="d812e-148">AccessEdgeClientPort : 443</span></span>

<span data-ttu-id="d812e-149">DataPsomServerPort: 8057</span><span class="sxs-lookup"><span data-stu-id="d812e-149">DataPsomServerPort : 8057</span></span>

<span data-ttu-id="d812e-150">DataPsomClientPort: 444</span><span class="sxs-lookup"><span data-stu-id="d812e-150">DataPsomClientPort : 444</span></span>

<span data-ttu-id="d812e-151">MediaRelayAuthEdgePort: 5062</span><span class="sxs-lookup"><span data-stu-id="d812e-151">MediaRelayAuthEdgePort : 5062</span></span>

<span data-ttu-id="d812e-152">MediaRelayAuthInternalTurnTcpPort: 443</span><span class="sxs-lookup"><span data-stu-id="d812e-152">MediaRelayAuthInternalTurnTcpPort : 443</span></span>

<span data-ttu-id="d812e-153">MediaRelayAuthExternalTurnTcpPort: 445</span><span class="sxs-lookup"><span data-stu-id="d812e-153">MediaRelayAuthExternalTurnTcpPort : 445</span></span>

<span data-ttu-id="d812e-154">MediaRelayAuthInternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="d812e-154">MediaRelayAuthInternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="d812e-155">MediaRelayAuthExternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="d812e-155">MediaRelayAuthExternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="d812e-156">MediaCommunicationPortStart: 50000</span><span class="sxs-lookup"><span data-stu-id="d812e-156">MediaCommunicationPortStart : 50000</span></span>

<span data-ttu-id="d812e-157">MediaComunicationPortCount: 10000</span><span class="sxs-lookup"><span data-stu-id="d812e-157">MediaComunicationPortCount : 10000</span></span>

<span data-ttu-id="d812e-158">AccessEdgeExternalFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d812e-158">AccessEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="d812e-159">DataEdgeExternalFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d812e-159">DataEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="d812e-160">AVEdgeExternalFqdn :</span><span class="sxs-lookup"><span data-stu-id="d812e-160">AVEdgeExternalFqdn :</span></span>

<span data-ttu-id="d812e-161">InternalInterfaceFqdn :</span><span class="sxs-lookup"><span data-stu-id="d812e-161">InternalInterfaceFqdn :</span></span>

<span data-ttu-id="d812e-162">ExternalMrasFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d812e-162">ExternalMrasFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="d812e-163">DependentServiceList: {注册机构: LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="d812e-163">DependentServiceList : {Registrar:LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="d812e-164">ConferencingServer: LYNC-SE</span><span class="sxs-lookup"><span data-stu-id="d812e-164">ConferencingServer:LYNC-SE.fabrikam</span></span>

<span data-ttu-id="d812e-165">com, MediationServer: LYNC-SE。</span><span class="sxs-lookup"><span data-stu-id="d812e-165">com, MediationServer:LYNC-SE.</span></span>

<span data-ttu-id="d812e-166">fabrikam.com}</span><span class="sxs-lookup"><span data-stu-id="d812e-166">fabrikam.com}</span></span>

<span data-ttu-id="d812e-167">ServiceId: fabrikam.com-EdgeServer-2</span><span class="sxs-lookup"><span data-stu-id="d812e-167">ServiceId : fabrikam.com-EdgeServer-2</span></span>

<span data-ttu-id="d812e-168">SiteId: site:fabrikam</span><span class="sxs-lookup"><span data-stu-id="d812e-168">SiteId : site:fabrikam.com</span></span>

<span data-ttu-id="d812e-169">PoolFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d812e-169">PoolFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="d812e-170">版本: 5</span><span class="sxs-lookup"><span data-stu-id="d812e-170">Version : 5</span></span>

<span data-ttu-id="d812e-171">角色: EdgeServer</span><span class="sxs-lookup"><span data-stu-id="d812e-171">Role : EdgeServer</span></span>

<div>

## <a name="check-federation-settings"></a><span data-ttu-id="d812e-172">检查联盟设置</span><span class="sxs-lookup"><span data-stu-id="d812e-172">Check federation settings</span></span>

<span data-ttu-id="d812e-173">检查联盟设置, 例如是否已配置, 如果答案为 "是", 则为 FQDN 和端口。</span><span class="sxs-lookup"><span data-stu-id="d812e-173">Check Federation settings, such as whether it is configured and, if the answer is "yes,", the FQDN and port.</span></span> <span data-ttu-id="d812e-174">通过使用访问边缘配置设置的全局集合启用和禁用联盟。</span><span class="sxs-lookup"><span data-stu-id="d812e-174">Federation is enabled and disabled by using the global collection of Access Edge configuration settings.</span></span> <span data-ttu-id="d812e-175">在其他情况下, 这些意味着联盟是在全或全基础上配置的: 为整个组织启用联盟或对整个组织禁用联盟</span><span class="sxs-lookup"><span data-stu-id="d812e-175">Among other things, these mean that federation is configured on an all-or-nothing basis: either federation is enabled for the whole organization or federation is disabled for the whole organization</span></span>

<span data-ttu-id="d812e-176">你的访问边缘配置设置可通过使用 Windows PowerShell 返回。</span><span class="sxs-lookup"><span data-stu-id="d812e-176">Your Access Edge configuration settings can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="d812e-177">若要执行此操作, 请运行以下 Windows PowerShell 命令:</span><span class="sxs-lookup"><span data-stu-id="d812e-177">To do that, run the following Windows PowerShell command:</span></span>

`Get-CsAccessEdgeConfiguration`

<span data-ttu-id="d812e-178">因此, 该命令将返回类似于以下内容的数据:</span><span class="sxs-lookup"><span data-stu-id="d812e-178">In turn, that command will return data similar to this:</span></span>

<span data-ttu-id="d812e-179">标识: 全局</span><span class="sxs-lookup"><span data-stu-id="d812e-179">Identity : Global</span></span>

<span data-ttu-id="d812e-180">AllowAnonymousUsers: False</span><span class="sxs-lookup"><span data-stu-id="d812e-180">AllowAnonymousUsers : False</span></span>

<span data-ttu-id="d812e-181">AllowFederatedUsers: False</span><span class="sxs-lookup"><span data-stu-id="d812e-181">AllowFederatedUsers : False</span></span>

<span data-ttu-id="d812e-182">AllowOutsideUsers: False</span><span class="sxs-lookup"><span data-stu-id="d812e-182">AllowOutsideUsers : False</span></span>

<span data-ttu-id="d812e-183">BeClearingHouse: False</span><span class="sxs-lookup"><span data-stu-id="d812e-183">BeClearingHouse : False</span></span>

<span data-ttu-id="d812e-184">EnablePartnerDiscovery: False</span><span class="sxs-lookup"><span data-stu-id="d812e-184">EnablePartnerDiscovery : False</span></span>

<span data-ttu-id="d812e-185">EnableArchivingDisclaimer: False</span><span class="sxs-lookup"><span data-stu-id="d812e-185">EnableArchivingDisclaimer : False</span></span>

<span data-ttu-id="d812e-186">KeepCrlsUpToDateForPeers: True</span><span class="sxs-lookup"><span data-stu-id="d812e-186">KeepCrlsUpToDateForPeers : True</span></span>

<span data-ttu-id="d812e-187">MarkSourceVerifiableOnOutgoingMessages: True</span><span class="sxs-lookup"><span data-stu-id="d812e-187">MarkSourceVerifiableOnOutgoingMessages : True</span></span>

<span data-ttu-id="d812e-188">OutgoingTlsCountForFederatedPartners: 4</span><span class="sxs-lookup"><span data-stu-id="d812e-188">OutgoingTlsCountForFederatedPartners : 4</span></span>

<span data-ttu-id="d812e-189">RoutingMethod : UseDnsSrvRouting</span><span class="sxs-lookup"><span data-stu-id="d812e-189">RoutingMethod : UseDnsSrvRouting</span></span>

<span data-ttu-id="d812e-190">如果**AllowFederatedUsers**属性设置为 True, 则表示已为你的组织启用联盟。</span><span class="sxs-lookup"><span data-stu-id="d812e-190">If the **AllowFederatedUsers** property is set to True, that means that federation is enabled for your organization.</span></span> <span data-ttu-id="d812e-191">(将**AllowFederatedUsers**设置为 True 还意味着, 在拆分域方案中, 你的本地用户将能够与云用户无缝通信。)</span><span class="sxs-lookup"><span data-stu-id="d812e-191">(Setting **AllowFederatedUsers** to True also means that, in a split domain scenario, your on-premises users will be able to communicate seamlessly with your in-the-cloud users.)</span></span>

<span data-ttu-id="d812e-192">若要检索 Edge 服务器的 FQDN 和端口设置, 请参阅上一任务 (边缘服务器及其设置)。</span><span class="sxs-lookup"><span data-stu-id="d812e-192">To retrieve the FQDN and port settings for your Edge Server, see the previous task (Edge Servers and their settings).</span></span>

<span data-ttu-id="d812e-193">在全局范围内启用联盟意味着用户可能与联盟用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="d812e-193">Enabling federation at the global scope only means that users can potentially communicate with federated users.</span></span> <span data-ttu-id="d812e-194">若要确定任何单个用户是否可以与联盟用户进行实际通信, 需要检查分配给该用户的外部用户访问策略。</span><span class="sxs-lookup"><span data-stu-id="d812e-194">To determine whether any individual users can actually communicate with federated users requires you to examine the external user access policy assigned to that user.</span></span>

<span data-ttu-id="d812e-195">可使用 Windows PowerShell 返回外部用户访问信息。</span><span class="sxs-lookup"><span data-stu-id="d812e-195">External user access information can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="d812e-196">例如, 此命令返回全局外部用户访问策略的信息:</span><span class="sxs-lookup"><span data-stu-id="d812e-196">For example, this command returns information for the global external user access policy:</span></span>

`Get-CsExternalAccessPolicy -Identity "Global"`

<span data-ttu-id="d812e-197">此命令返回所有外部用户访问策略的信息:</span><span class="sxs-lookup"><span data-stu-id="d812e-197">And this command returns information for all the external user access policies:</span></span>

`Get-CsExternalAccessPolicy`

<span data-ttu-id="d812e-198">返回的信息将如下所示:</span><span class="sxs-lookup"><span data-stu-id="d812e-198">The returned information will resemble this:</span></span>

<span data-ttu-id="d812e-199">标识: False</span><span class="sxs-lookup"><span data-stu-id="d812e-199">Identity : False</span></span>

<span data-ttu-id="d812e-200">介绍</span><span class="sxs-lookup"><span data-stu-id="d812e-200">Description :</span></span>

<span data-ttu-id="d812e-201">EnableFederationAccess: False</span><span class="sxs-lookup"><span data-stu-id="d812e-201">EnableFederationAccess : False</span></span>

<span data-ttu-id="d812e-202">EnablePublicCloudAccess: False</span><span class="sxs-lookup"><span data-stu-id="d812e-202">EnablePublicCloudAccess : False</span></span>

<span data-ttu-id="d812e-203">EnablePublicCloudAccessAudioVideoAccess: False</span><span class="sxs-lookup"><span data-stu-id="d812e-203">EnablePublicCloudAccessAudioVideoAccess : False</span></span>

<span data-ttu-id="d812e-204">EnableOutsideAccess: False</span><span class="sxs-lookup"><span data-stu-id="d812e-204">EnableOutsideAccess : False</span></span>

<span data-ttu-id="d812e-205">如果**EnableFederationAccess**设置为 True, 则由给定策略管理的用户可以与联盟用户通信。</span><span class="sxs-lookup"><span data-stu-id="d812e-205">If **EnableFederationAccess** is set to True, then users managed by the given policy can communicate with federated users.</span></span>

</div>

</div>

<div>

## <a name="check-archiving-settings"></a><span data-ttu-id="d812e-206">检查存档设置</span><span class="sxs-lookup"><span data-stu-id="d812e-206">Check archiving settings</span></span>

<span data-ttu-id="d812e-207">检查内部和联盟通信的存档设置。在验证内部和外部存档的设置之前, 应验证是否已启用存档。</span><span class="sxs-lookup"><span data-stu-id="d812e-207">Check archiving settings for internal and federated communications.Before verifying the settings for internal and external archiving, you should verify that archiving is enabled.</span></span>

<span data-ttu-id="d812e-208">可以使用 Windows PowerShell 和 CsArchivingConfiguration cmdlet 验证存档配置设置:</span><span class="sxs-lookup"><span data-stu-id="d812e-208">Archiving configuration settings can be verified by using Windows PowerShell and the Get-CsArchivingConfiguration cmdlet:</span></span>

`Get-CsArchivingConfiguration -Identity "Global"`

<span data-ttu-id="d812e-209">请注意, 也可以在网站范围内配置存档设置。</span><span class="sxs-lookup"><span data-stu-id="d812e-209">Note that archiving settings can also be configured at the site scope.</span></span> <span data-ttu-id="d812e-210">若要返回有关所有存档设置的信息, 请使用以下命令:</span><span class="sxs-lookup"><span data-stu-id="d812e-210">To return information about all the archiving settings, use this command:</span></span>

`Get-CsArchivingConfiguration`

<span data-ttu-id="d812e-211">CsArchivingConfiguration cmdlet 返回与以下内容类似的数据:</span><span class="sxs-lookup"><span data-stu-id="d812e-211">The Get-CsArchivingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="d812e-212">标识: 全局</span><span class="sxs-lookup"><span data-stu-id="d812e-212">Identity : Global</span></span>

<span data-ttu-id="d812e-213">EnableArchiving: False</span><span class="sxs-lookup"><span data-stu-id="d812e-213">EnableArchiving : False</span></span>

<span data-ttu-id="d812e-214">EnablePurging: False</span><span class="sxs-lookup"><span data-stu-id="d812e-214">EnablePurging : False</span></span>

<span data-ttu-id="d812e-215">PurgeExportedArchivesOnly: False</span><span class="sxs-lookup"><span data-stu-id="d812e-215">PurgeExportedArchivesOnly : False</span></span>

<span data-ttu-id="d812e-216">BlockOnArchiveFailure: False</span><span class="sxs-lookup"><span data-stu-id="d812e-216">BlockOnArchiveFailure : False</span></span>

<span data-ttu-id="d812e-217">KeepArchivingDataForDays:14</span><span class="sxs-lookup"><span data-stu-id="d812e-217">KeepArchivingDataForDays : 14</span></span>

<span data-ttu-id="d812e-218">PurgeHourOfDay: 2</span><span class="sxs-lookup"><span data-stu-id="d812e-218">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="d812e-219">ArchiveDuplicateMessages: True</span><span class="sxs-lookup"><span data-stu-id="d812e-219">ArchiveDuplicateMessages : True</span></span>

<span data-ttu-id="d812e-220">CachePurgingInterval:24</span><span class="sxs-lookup"><span data-stu-id="d812e-220">CachePurgingInterval : 24</span></span>

<span data-ttu-id="d812e-221">如果 EnableArchiving 属性设置为 False, 则表示不会存档任何通信会话。</span><span class="sxs-lookup"><span data-stu-id="d812e-221">If the EnableArchiving property is set to False, that means that no communication sessions will be archived.</span></span> <span data-ttu-id="d812e-222">如果只想存档即时消息会话, 请使用如下所示的命令来启用 IM 会话的存档:</span><span class="sxs-lookup"><span data-stu-id="d812e-222">If you want to archive instant messaging sessions only, use a command such as the following to enable the archiving of IM sessions:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="d812e-223">若要将会议会话和即时消息会话存档, 请使用以下命令:</span><span class="sxs-lookup"><span data-stu-id="d812e-223">To archive conferencing sessions and instant messaging sessions, use this command:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="d812e-224">如果你想要将当前存档设置与默认设置进行比较, 请运行以下 Windows PowerShell 命令:</span><span class="sxs-lookup"><span data-stu-id="d812e-224">If you’d like to compare your current archiving settings with the default settings, run the following Windows PowerShell command:</span></span>

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="d812e-225">该命令将创建全局存档配置设置的仅内存内部实例。</span><span class="sxs-lookup"><span data-stu-id="d812e-225">That command creates an in-memory-only instance of the global archiving configuration settings.</span></span> <span data-ttu-id="d812e-226">这不是由 Lync Server 使用的真实设置集合。</span><span class="sxs-lookup"><span data-stu-id="d812e-226">This is not a real collection of settings that is used by Lync Server.</span></span> <span data-ttu-id="d812e-227">但是, 它会显示所有存档配置属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="d812e-227">However, it does display the default values for all the archiving configuration properties.</span></span>

<span data-ttu-id="d812e-228">你还可以使用此命令返回存档服务器的 FQDN:</span><span class="sxs-lookup"><span data-stu-id="d812e-228">You can also use this command to return the FQDN of your Archiving servers:</span></span>

`Get-CsService -ArchivingServer`

<span data-ttu-id="d812e-229">验证已启用存档后, 您可以查看存档策略以确定是否正在存档内部和外部通信会话。</span><span class="sxs-lookup"><span data-stu-id="d812e-229">After you have verified that archiving is enabled, you can then view your archiving policies to determine whether internal and external communication sessions are being archived.</span></span>

<span data-ttu-id="d812e-230">可通过使用 CsArchivingPolicy cmdlet 检索存档策略信息。</span><span class="sxs-lookup"><span data-stu-id="d812e-230">Archiving policy information can be retrieved by using the Get-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="d812e-231">例如, 此命令返回有关全局存档策略的信息:</span><span class="sxs-lookup"><span data-stu-id="d812e-231">For example, this command returns information about the global archiving policy:</span></span>

`Get-CsArchivingPolicy -Identity "Global"`

<span data-ttu-id="d812e-232">由于还可以在网站和每用户范围内配置存档策略, 因此你可能还希望使用此命令, 该命令将返回有关所有存档策略的信息:</span><span class="sxs-lookup"><span data-stu-id="d812e-232">Because archiving policies can also be configured at the site and the per-user scope, you might also want to use this command, which returns information about all the archiving policies:</span></span>

`Get-CsArchivingPolicy`

<span data-ttu-id="d812e-233">从 CsArchivingPolicy 接收的信息将如下所示:</span><span class="sxs-lookup"><span data-stu-id="d812e-233">The information that you receive from Get-CsArchivingPolicy will resemble this:</span></span>

<span data-ttu-id="d812e-234">标识: 全局</span><span class="sxs-lookup"><span data-stu-id="d812e-234">Identity : Global</span></span>

<span data-ttu-id="d812e-235">介绍</span><span class="sxs-lookup"><span data-stu-id="d812e-235">Description :</span></span>

<span data-ttu-id="d812e-236">ArchiveInternal: False</span><span class="sxs-lookup"><span data-stu-id="d812e-236">ArchiveInternal : False</span></span>

<span data-ttu-id="d812e-237">ArchiveExternal: False</span><span class="sxs-lookup"><span data-stu-id="d812e-237">ArchiveExternal : False</span></span>

<span data-ttu-id="d812e-238">请注意, 默认情况下, 存档策略中禁用内部和外部存档。</span><span class="sxs-lookup"><span data-stu-id="d812e-238">Note that, by default, both internal and external archiving are disabled in an archiving policy.</span></span>

</div>

<div>

## <a name="check-cdr-settings"></a><span data-ttu-id="d812e-239">检查 CDR 设置</span><span class="sxs-lookup"><span data-stu-id="d812e-239">Check CDR settings</span></span>

<span data-ttu-id="d812e-240">检查对等、会议和语音呼叫详细记录的呼叫详细记录 (CDR) 设置。</span><span class="sxs-lookup"><span data-stu-id="d812e-240">Check Call Detail Record (CDR) settings for peer-to-peer, conferencing, and Voice call detail recording.</span></span> <span data-ttu-id="d812e-241">可通过使用**CsCdrConfiguration** cmdlet 返回有关 CDR 设置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d812e-241">Detailed information about your CDR settings can be returned by using the **Get-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="d812e-242">例如, 此命令返回有关 CDR 配置设置的全局集合的信息:</span><span class="sxs-lookup"><span data-stu-id="d812e-242">For example, this command returns information about the global collection of CDR configuration settings:</span></span>

`Get-CsCdrConfiguration -Identity "Global"`

<span data-ttu-id="d812e-243">由于 CDR 也可以在网站范围内配置, 因此你可能还希望运行此命令, 该命令将返回有关所有 CDR 配置设置的信息:</span><span class="sxs-lookup"><span data-stu-id="d812e-243">Because CDR can also be configured at the site scope, you might also want to run this command, which returns information about all the CDR configuration settings:</span></span>

`Get-CsCdrConfiguration`

<span data-ttu-id="d812e-244">CsCdrConfiguration cmdlet 针对 CDR 配置设置的每个集合返回类似于以下内容的信息:</span><span class="sxs-lookup"><span data-stu-id="d812e-244">The Get-CsCdrConfiguration cmdlet returns information similar to this for each collection of CDR configuration settings:</span></span>

<span data-ttu-id="d812e-245">标识: 全局</span><span class="sxs-lookup"><span data-stu-id="d812e-245">Identity : Global</span></span>

<span data-ttu-id="d812e-246">EnableCDR: True</span><span class="sxs-lookup"><span data-stu-id="d812e-246">EnableCDR : True</span></span>

<span data-ttu-id="d812e-247">EnablePurging: True</span><span class="sxs-lookup"><span data-stu-id="d812e-247">EnablePurging : True</span></span>

<span data-ttu-id="d812e-248">KeepCallDetailForDays:60</span><span class="sxs-lookup"><span data-stu-id="d812e-248">KeepCallDetailForDays : 60</span></span>

<span data-ttu-id="d812e-249">KeepErrorReportForDays:60</span><span class="sxs-lookup"><span data-stu-id="d812e-249">KeepErrorReportForDays : 60</span></span>

<span data-ttu-id="d812e-250">PurgeHourOfDay: 2</span><span class="sxs-lookup"><span data-stu-id="d812e-250">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="d812e-251">通过使用 CsQoEConfiguration cmdlet, 可以为 QoE 监视返回类似信息。</span><span class="sxs-lookup"><span data-stu-id="d812e-251">Similar information can be returned for QoE monitoring by using the Get-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="d812e-252">例如, 此命令返回有关 QoE 配置设置的全局集合的信息:</span><span class="sxs-lookup"><span data-stu-id="d812e-252">For example, this command returns information about the global collection of QoE configuration settings:</span></span>

`Get-QoEConfiguration -Identity "Global"`

<span data-ttu-id="d812e-253">该信息将如下所示:</span><span class="sxs-lookup"><span data-stu-id="d812e-253">That information will resemble this:</span></span>

<span data-ttu-id="d812e-254">标识: 全局</span><span class="sxs-lookup"><span data-stu-id="d812e-254">Identity : Global</span></span>

<span data-ttu-id="d812e-255">ExternalConsumerIssuedCertId :</span><span class="sxs-lookup"><span data-stu-id="d812e-255">ExternalConsumerIssuedCertId :</span></span>

<span data-ttu-id="d812e-256">EnablePurging: True</span><span class="sxs-lookup"><span data-stu-id="d812e-256">EnablePurging : True</span></span>

<span data-ttu-id="d812e-257">KeepQoEDataForDays:60</span><span class="sxs-lookup"><span data-stu-id="d812e-257">KeepQoEDataForDays : 60</span></span>

<span data-ttu-id="d812e-258">PurgeHourOfDay: 1</span><span class="sxs-lookup"><span data-stu-id="d812e-258">PurgeHourOfDay : 1</span></span>

<span data-ttu-id="d812e-259">EnableExternalConsumer: False</span><span class="sxs-lookup"><span data-stu-id="d812e-259">EnableExternalConsumer : False</span></span>

<span data-ttu-id="d812e-260">ExternalConsumerName :</span><span class="sxs-lookup"><span data-stu-id="d812e-260">ExternalConsumerName :</span></span>

<span data-ttu-id="d812e-261">ExternalConsumerURL :</span><span class="sxs-lookup"><span data-stu-id="d812e-261">ExternalConsumerURL :</span></span>

<span data-ttu-id="d812e-262">EnableQoE: True</span><span class="sxs-lookup"><span data-stu-id="d812e-262">EnableQoE : True</span></span>

<span data-ttu-id="d812e-263">如果要将当前 CDR 设置与默认的 CDR 设置进行比较, 可以通过运行以下命令来查看默认值:</span><span class="sxs-lookup"><span data-stu-id="d812e-263">If you want to compare your current CDR settings with the default CDR settings, the default values can be reviewed by running this command:</span></span>

`New-CsCdrConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="d812e-264">同样, 可以使用以下命令检索 QoE 监视的默认值:</span><span class="sxs-lookup"><span data-stu-id="d812e-264">Likewise, the default values for QoE monitoring can be retrieved by using this command:</span></span>

`New-CsQoEConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="d812e-265">您也可以通过运行以下命令返回监视服务器的 FQDN:</span><span class="sxs-lookup"><span data-stu-id="d812e-265">You can also return the FQDN of your Monitoring servers by running this command:</span></span>

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a><span data-ttu-id="d812e-266">检查语音设置</span><span class="sxs-lookup"><span data-stu-id="d812e-266">Check voice settings</span></span>

<span data-ttu-id="d812e-267">语音设置通常对管理员非常重要, 因为它包含在语音策略和语音路由中: 语音策略包含确定向单个用户公开的功能 (如转发或转移呼叫能力) 的设置。语音路由确定如何 (和 if) 呼叫通过 PSTN 路由。</span><span class="sxs-lookup"><span data-stu-id="d812e-267">The voice settings typically important to administrators are contained in voice policies and voice routes: voice policies contain the settings that determine the capabilities exposed to individual users (such as the ability to forward or transfer calls), while voice routes determine how (and if) calls are routed across the PSTN.</span></span>

<span data-ttu-id="d812e-268">可以使用 Windows PowerShell 检索语音策略信息。</span><span class="sxs-lookup"><span data-stu-id="d812e-268">Voice policy information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="d812e-269">例如, 此命令返回有关全局语音策略的信息:</span><span class="sxs-lookup"><span data-stu-id="d812e-269">For example, this command returns information about the global voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global"`

<span data-ttu-id="d812e-270">此命令将返回有关已配置为在组织中使用的所有语音策略的信息:</span><span class="sxs-lookup"><span data-stu-id="d812e-270">And this command returns information about all the voice policies configured for use in the organization:</span></span>

`Get-CsVoicePolicy`

<span data-ttu-id="d812e-271">CsVoicePolicy cmdlet 返回的信息如下所示:</span><span class="sxs-lookup"><span data-stu-id="d812e-271">The information returned by the Get-CsVoicePolicy cmdlet resembles the following:</span></span>

<span data-ttu-id="d812e-272">标识: 全局</span><span class="sxs-lookup"><span data-stu-id="d812e-272">Identity : Global</span></span>

<span data-ttu-id="d812e-273">PstnUsages :{}</span><span class="sxs-lookup"><span data-stu-id="d812e-273">PstnUsages : {}</span></span>

<span data-ttu-id="d812e-274">介绍</span><span class="sxs-lookup"><span data-stu-id="d812e-274">Description :</span></span>

<span data-ttu-id="d812e-275">AllowSimulRing: True</span><span class="sxs-lookup"><span data-stu-id="d812e-275">AllowSimulRing : True</span></span>

<span data-ttu-id="d812e-276">AllowCallForwarding: True</span><span class="sxs-lookup"><span data-stu-id="d812e-276">AllowCallForwarding : True</span></span>

<span data-ttu-id="d812e-277">AllowPSTNReRouting: True</span><span class="sxs-lookup"><span data-stu-id="d812e-277">AllowPSTNReRouting : True</span></span>

<span data-ttu-id="d812e-278">名称: DefaultPolicy</span><span class="sxs-lookup"><span data-stu-id="d812e-278">Name : DefaultPolicy</span></span>

<span data-ttu-id="d812e-279">EnableDelegation: True</span><span class="sxs-lookup"><span data-stu-id="d812e-279">EnableDelegation : True</span></span>

<span data-ttu-id="d812e-280">EnableTeamCall: True</span><span class="sxs-lookup"><span data-stu-id="d812e-280">EnableTeamCall : True</span></span>

<span data-ttu-id="d812e-281">EnableCallTransfer: True</span><span class="sxs-lookup"><span data-stu-id="d812e-281">EnableCallTransfer : True</span></span>

<span data-ttu-id="d812e-282">EnableCallPark: False</span><span class="sxs-lookup"><span data-stu-id="d812e-282">EnableCallPark : False</span></span>

<span data-ttu-id="d812e-283">EnableMaliciousCallTracing: False</span><span class="sxs-lookup"><span data-stu-id="d812e-283">EnableMaliciousCallTracing : False</span></span>

<span data-ttu-id="d812e-284">EnableBWPolicyOverride: False</span><span class="sxs-lookup"><span data-stu-id="d812e-284">EnableBWPolicyOverride : False</span></span>

<span data-ttu-id="d812e-285">PreventPSTNTollBypass: False</span><span class="sxs-lookup"><span data-stu-id="d812e-285">PreventPSTNTollBypass : False</span></span>

<span data-ttu-id="d812e-286">您还可以创建返回您的语音策略子集的查询。</span><span class="sxs-lookup"><span data-stu-id="d812e-286">You can also create queries that returned a subset of your voice policies.</span></span> <span data-ttu-id="d812e-287">例如, 此命令返回允许呼叫转接的所有语音策略:</span><span class="sxs-lookup"><span data-stu-id="d812e-287">For example, this command returns all the voice policies that allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

<span data-ttu-id="d812e-288">此命令将返回不允许呼叫转接的所有语音策略:</span><span class="sxs-lookup"><span data-stu-id="d812e-288">And this command returns all the voice policies that don’t allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

<span data-ttu-id="d812e-289">在 Windows PowerShell 中, 使用 CsVoiceRouting cmdlet 返回有关语音路由的信息:</span><span class="sxs-lookup"><span data-stu-id="d812e-289">In Windows PowerShell, use the Get-CsVoiceRouting cmdlet to return information about your voice routes:</span></span>

`Get-CsVoiceRoute`

<span data-ttu-id="d812e-290">该命令将为所有语音路线返回如下信息:</span><span class="sxs-lookup"><span data-stu-id="d812e-290">That command returns information such as this for all the voice routes:</span></span>

<span data-ttu-id="d812e-291">标识: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="d812e-291">Identity : LocalRoute</span></span>

<span data-ttu-id="d812e-292">优先级: 0</span><span class="sxs-lookup"><span data-stu-id="d812e-292">Priority : 0</span></span>

<span data-ttu-id="d812e-293">介绍</span><span class="sxs-lookup"><span data-stu-id="d812e-293">Description :</span></span>

<span data-ttu-id="d812e-294">NumberPattern: ^ (\\+ 1\[0-9\]{10}) $</span><span class="sxs-lookup"><span data-stu-id="d812e-294">NumberPattern : ^(\\+1\[0-9\]{10})$</span></span>

<span data-ttu-id="d812e-295">PstnUsages :{}</span><span class="sxs-lookup"><span data-stu-id="d812e-295">PstnUsages : {}</span></span>

<span data-ttu-id="d812e-296">PstnGatewayList :{}</span><span class="sxs-lookup"><span data-stu-id="d812e-296">PstnGatewayList : {}</span></span>

<span data-ttu-id="d812e-297">名称: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="d812e-297">Name : LocalRoute</span></span>

<span data-ttu-id="d812e-298">SuppressCallerId :</span><span class="sxs-lookup"><span data-stu-id="d812e-298">SuppressCallerId :</span></span>

<span data-ttu-id="d812e-299">AlternateCallerId :</span><span class="sxs-lookup"><span data-stu-id="d812e-299">AlternateCallerId :</span></span>

<span data-ttu-id="d812e-300">Lync Server 允许你创建没有 PSTN 使用的语音路由, 不指定 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="d812e-300">Lync Server allows you to create voice routes that do not have a PSTN usage and do not specify a PSTN gateway.</span></span> <span data-ttu-id="d812e-301">但是, 您实际上无法通过没有配置这两个属性值的语音路线路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="d812e-301">However, you can't actually route calls over a voice route that does not have these two property values configured.</span></span> <span data-ttu-id="d812e-302">出于此原因, 你可能会发现定期运行此命令非常有用, 该命令将返回没有 PSTN 使用的任何语音路由的标识:</span><span class="sxs-lookup"><span data-stu-id="d812e-302">Because of that, you might find it useful to periodically run this command, which returns the identity of any voice route that does not have a PSTN usage:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

<span data-ttu-id="d812e-303">同样, 此命令返回尚未配置为具有 PSTN 网关的任何语音路由的标识:</span><span class="sxs-lookup"><span data-stu-id="d812e-303">Similarly, this command returns the identity of any voice route that has not been configured to have a PSTN gateway:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a><span data-ttu-id="d812e-304">检查会议助理设置</span><span class="sxs-lookup"><span data-stu-id="d812e-304">Check Conferencing Attendant settings</span></span>

<span data-ttu-id="d812e-305">检查 PSTN 电话拨入式会议的会议助理设置。</span><span class="sxs-lookup"><span data-stu-id="d812e-305">Check conferencing Attendant settings for PSTN dial-in conferencing.</span></span> <span data-ttu-id="d812e-306">只能使用**CsDialInConferencingConfiguration** cmdlet 来检索会议助理设置。</span><span class="sxs-lookup"><span data-stu-id="d812e-306">Conferencing Attendant settings can only be retrieved by using the **Get-CsDialInConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="d812e-307">这些设置在 Lync Server "控制面板" 中不可用。</span><span class="sxs-lookup"><span data-stu-id="d812e-307">These settings are not available in the Lync Server Control Panel.</span></span> <span data-ttu-id="d812e-308">若要查看会议助理设置, 请使用与以下内容类似的 Windows PowerShell 命令, 它可返回全局会议助理设置的全局集合:</span><span class="sxs-lookup"><span data-stu-id="d812e-308">To view your Conferencing Attendant settings, use a Windows PowerShell command similar to the following, which returns the global collection of Conferencing Attendant settings:</span></span>

`Get-CsDialInConferencingConfiguration -Identity "Global"`

<span data-ttu-id="d812e-309">请注意, 还可以在网站范围内配置会议助理设置。</span><span class="sxs-lookup"><span data-stu-id="d812e-309">Note that Conferencing Attendant settings can also be configured at the site scope.</span></span> <span data-ttu-id="d812e-310">若要返回有关所有会议助理设置的信息, 请改用此命令:</span><span class="sxs-lookup"><span data-stu-id="d812e-310">To return information about all the Conferencing Attendant settings, use this command instead:</span></span>

`Get-CsDialInConferencingConfiguration`

<span data-ttu-id="d812e-311">CsDialInConferencingConfiguration cmdlet 返回与以下内容类似的数据:</span><span class="sxs-lookup"><span data-stu-id="d812e-311">The Get-CsDialInConferencingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="d812e-312">标识: 全局</span><span class="sxs-lookup"><span data-stu-id="d812e-312">Identity : Global</span></span>

<span data-ttu-id="d812e-313">EntryExitAnnouncementsType : UseNames</span><span class="sxs-lookup"><span data-stu-id="d812e-313">EntryExitAnnouncementsType : UseNames</span></span>

<span data-ttu-id="d812e-314">EnableNameRecording: True</span><span class="sxs-lookup"><span data-stu-id="d812e-314">EnableNameRecording : True</span></span>

<span data-ttu-id="d812e-315">EntryExitAnnouncementsEnabledByDefault: False</span><span class="sxs-lookup"><span data-stu-id="d812e-315">EntryExitAnnouncementsEnabledByDefault : False</span></span>

<span data-ttu-id="d812e-316">如果 EntryExitAnnouncementsEnabledByDefault 设置为 False, 则表示已禁用会议通知。</span><span class="sxs-lookup"><span data-stu-id="d812e-316">If EntryExitAnnouncementsEnabledByDefault is set to False, that means the conferencing announcements are disabled.</span></span> <span data-ttu-id="d812e-317">若要启用进入和退出通知, 请运行如下所示的 Windows PowerShell 命令:</span><span class="sxs-lookup"><span data-stu-id="d812e-317">To enable entry and exit announcements, run a Windows PowerShell command similar to this:</span></span>

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d812e-318">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d812e-318">See Also</span></span>


[<span data-ttu-id="d812e-319">Get-CsSipDomain</span><span class="sxs-lookup"><span data-stu-id="d812e-319">Get-CsSipDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[<span data-ttu-id="d812e-320">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="d812e-320">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[<span data-ttu-id="d812e-321">CsService</span><span class="sxs-lookup"><span data-stu-id="d812e-321">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="d812e-322">CsAccessEdgeConfiguration</span><span class="sxs-lookup"><span data-stu-id="d812e-322">Get-CsAccessEdgeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[<span data-ttu-id="d812e-323">CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="d812e-323">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="d812e-324">CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="d812e-324">Get-CsArchivingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[<span data-ttu-id="d812e-325">CsCdrConfiguration</span><span class="sxs-lookup"><span data-stu-id="d812e-325">Get-CsCdrConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[<span data-ttu-id="d812e-326">CsQoEConfiguration</span><span class="sxs-lookup"><span data-stu-id="d812e-326">Get-CsQoEConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[<span data-ttu-id="d812e-327">CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="d812e-327">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="d812e-328">CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="d812e-328">Get-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[<span data-ttu-id="d812e-329">Get-CsDialInConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="d812e-329">Get-CsDialInConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

