---
title: 常见问题：设置适用于 Skype 连接的 Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Frequently Asked Questions: Provisioning Lync Server for Skype connectivity'
ms:assetid: 4d1b2bfc-780b-4b8c-afd5-11c2e59203b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440172(v=OCS.15)
ms:contentKeyID: 57793362
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0315104e4bbbd2d8741d5bc011455be2d28191dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500809"
---
# <a name="frequently-asked-questions-provisioning-lync-server-2013-for-skype-connectivity"></a><span data-ttu-id="28002-102">常见问题：设置适用于 Skype 连接的 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28002-102">Frequently Asked Questions: Provisioning Lync Server 2013 for Skype connectivity</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28002-103">_**上次修改的主题：** 2019-03-22_</span><span class="sxs-lookup"><span data-stu-id="28002-103">_**Topic Last Modified:** 2019-03-22_</span></span>

<span data-ttu-id="28002-104">从2019年4月起，我们将停止通过 pic.lync.com 网站为 Skype 联盟预配的客户的联系信息的收集和保留。</span><span class="sxs-lookup"><span data-stu-id="28002-104">Beginning in April 2019, we will stop the collection and retention of contact information for customers who are provisioned for Skype Federation via the pic.lync.com website.</span></span> <span data-ttu-id="28002-105">进行此更改是为了确保 pic.lync.com 预配系统符合 Microsoft 隐私策略。</span><span class="sxs-lookup"><span data-stu-id="28002-105">This change is being made to ensure that the pic.lync.com provisioning system adheres to Microsoft privacy policies.</span></span> 
 
<span data-ttu-id="28002-106">此更改生效后，我们将不再能够在挂起的设置更改时提供电子邮件更新。</span><span class="sxs-lookup"><span data-stu-id="28002-106">Once this change goes live, we will no longer be able to provide email updates on pending provisioning changes.</span></span> <span data-ttu-id="28002-107">PIC 设置更改通常在输入后的24-48 小时内完成。</span><span class="sxs-lookup"><span data-stu-id="28002-107">PIC provisioning changes typically complete within 24-48 hours after being entered.</span></span> <span data-ttu-id="28002-108">如果在提交设置请求后仍遇到 Skype 联合身份问题48小时，请与 Microsoft 技术支持人员联系，以进一步调查。</span><span class="sxs-lookup"><span data-stu-id="28002-108">If you are still experiencing Skype Federation issues 48 hours after submitting a provisioning request, please engage Microsoft Technical Support to investigate further.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="28002-109">作为此更改的一部分，所有以前输入的联系信息将在2019年4月结束时从系统中清除。</span><span class="sxs-lookup"><span data-stu-id="28002-109">As part of this change, all previously entered contact information will be purged from our system by the end of April, 2019.</span></span>


<span data-ttu-id="28002-110">**问： Microsoft Lync 和 Skype 之间支持哪些功能？**</span><span class="sxs-lookup"><span data-stu-id="28002-110">**Q: What features are supported between Microsoft Lync and Skype?**</span></span>

<span data-ttu-id="28002-111">**A：** 通过 Microsoft 系列的现已准备好，新可能会将统一通信方案扩展到数百个使用 Skype 的用户。</span><span class="sxs-lookup"><span data-stu-id="28002-111">**A:** With Skype now part of the Microsoft family, new possibilities open up for extending unified communications scenarios to the hundreds of millions of people who use Skype.</span></span> <span data-ttu-id="28002-112">此组合将使 Lync 客户能够与供应商、客户和合作伙伴进行连接和协作，依赖 Lync 的丰富程度和 Skype 的覆盖范围。</span><span class="sxs-lookup"><span data-stu-id="28002-112">This combination will enable Lync customers to connect and collaborate with suppliers, customers, and partners, relying on the richness of Lync and the reach of Skype.</span></span>

  - <span data-ttu-id="28002-113">即时消息和音频和视频呼叫— Lync 和 Skype 用户之间的联合音频和视频呼叫和即时消息</span><span class="sxs-lookup"><span data-stu-id="28002-113">Instant Message and Audio and Video Calls—Federated audio and video calling and instant messaging between Lync and Skype users</span></span>

  - <span data-ttu-id="28002-114">状态共享—联盟联系人之间的交换状态信息</span><span class="sxs-lookup"><span data-stu-id="28002-114">Presence Sharing— Exchange presence information between federated contacts</span></span>

  - <span data-ttu-id="28002-115">简单管理—根据组织策略和标准配置联合通信的设置和控件</span><span class="sxs-lookup"><span data-stu-id="28002-115">Simple Administration—Settings and controls to configure federated communications in accordance with your organization’s policies and standards</span></span>

<span data-ttu-id="28002-116">**问：如何有资格将我的 Lync 部署与 Skype 连接？**</span><span class="sxs-lookup"><span data-stu-id="28002-116">**Q: How do I qualify to connect my Lync deployment with Skype?**</span></span>

<span data-ttu-id="28002-117">**A：** 如果你有以下任一种，则可以使用 Skype 连接许可：</span><span class="sxs-lookup"><span data-stu-id="28002-117">**A:** You are licensed for Skype connectivity if you have either:</span></span>

  - <span data-ttu-id="28002-118">Lync Server (2010 或 2013) 加上 Lync Server Standard Client Access 许可证 ( "Cal";对于组织中将连接到 Skype 的用户和/或设备，为2010或 2013) 。</span><span class="sxs-lookup"><span data-stu-id="28002-118">Lync Server (2010 or 2013) plus Lync Server Standard Client Access Licenses (“CALs”; 2010 or 2013) for the users and/or devices in your organization that will connect to Skype.</span></span> 

  - <span data-ttu-id="28002-119">Lync Online (作为独立许可证，也可作为 Office 365 套件) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="28002-119">Lync Online (as standalone licenses or as part of an Office 365 suite).</span></span><span data-ttu-id="28002-120">但是，此服务 (pic.lync.com) 仅用于设置 Lync Server 和混合 Lync Server 和 Lync Online 部署。</span><span class="sxs-lookup"><span data-stu-id="28002-120">  However, this service (pic.lync.com) is only for provisioning Lync Server and hybrid Lync Server and Lync Online deployments.</span></span><span data-ttu-id="28002-121">Lync Online PIC 预配在 Lync Online 控制面板中执行 (LOCP) 。</span><span class="sxs-lookup"><span data-stu-id="28002-121">  Lync Online PIC provisioning is done in Lync Online Control Panel (LOCP).</span></span>

<span data-ttu-id="28002-122">**问： Lync 最终用户必须要连接到 Skype 联系人？**</span><span class="sxs-lookup"><span data-stu-id="28002-122">**Q: What must Lync end users do to connect to Skype contacts?**</span></span>

<span data-ttu-id="28002-123">**A：** 在域被激活且组织的 Lync 管理员启用了这些功能之后，Lync 用户可以将 Skype 联系人添加到 Lync 客户端中的联系人列表中。</span><span class="sxs-lookup"><span data-stu-id="28002-123">**A:** After a domain is activated and the features are enabled by an organization’s Lync administrator, Lync users can add Skype contacts to their contact lists within the Lync client.</span></span>

<span data-ttu-id="28002-124">**问： Skype 最终用户必须要连接到 Lync 联系人？**</span><span class="sxs-lookup"><span data-stu-id="28002-124">**Q: What must Skype end users do to connect to Lync contacts?**</span></span>

<span data-ttu-id="28002-125">**A：** 希望连接到 Lync 用户的所有 Skype 用户必须具有与其 Skype Id 关联的 Microsoft 帐户，并使用 Microsoft 帐户登录。</span><span class="sxs-lookup"><span data-stu-id="28002-125">**A:** All Skype users wishing to connect to a Lync user must have a Microsoft Account associated with their Skype IDs and sign in using the Microsoft Account.</span></span><span data-ttu-id="28002-126">可以在 Skype 客户端中启用此功能。</span><span class="sxs-lookup"><span data-stu-id="28002-126">  This can be enabled within the Skype client.</span></span>

<span data-ttu-id="28002-127">**问：与 Windows Live 的联盟是否仍然可用？**</span><span class="sxs-lookup"><span data-stu-id="28002-127">**Q: Is federation with Windows Live still available?**</span></span>

<span data-ttu-id="28002-128">**A：** 从2012年10月起，Microsoft 开始帮助 Windows Live Messenger (WLM) 用户迁移到 Skype，通过途中路由最终注销 WLM。</span><span class="sxs-lookup"><span data-stu-id="28002-128">**A:** Beginning in October, 2012, Microsoft started helping Windows Live Messenger (WLM) users move to Skype, en route to eventually retiring WLM.</span></span><span data-ttu-id="28002-129">只要 WLM 在市场中，Lync 将继续支持与 WLM 联合身份验证，但不允许其他任何 Windows Live 域激活。</span><span class="sxs-lookup"><span data-stu-id="28002-129"> Lync will continue to support federation with WLM as long as WLM is in market, but no additional Windows Live domain activations will be allowed.</span></span><span data-ttu-id="28002-130">WLM 用户的移动由 Skype 6.0 for Mac 和 Windows (启用。在10月25日发布的 2012) 这将允许使用 Microsoft 帐户登录 (即与 WLM) 相同的凭据。</span><span class="sxs-lookup"><span data-stu-id="28002-130"> The movement of WLM users is enabled by the Skype 6.0 for Mac and Windows (released October 25, 2012) which allows signing in with a Microsoft Account (i.e., the same credentials as WLM).</span></span> <span data-ttu-id="28002-131">简单地登录到 Skype 后，WLM 好友列表将自动填充到 Skype，用户可以利用 Skype 的扩展通信功能，如呼叫座机和 mobiles、屏幕共享、分组视频呼叫，以及对各种设备的支持。</span><span class="sxs-lookup"><span data-stu-id="28002-131">After simply signing in to Skype, WLM buddy lists automatically populate into Skype, and users can take advantage of Skype’s expanded communication capabilities such as calling landlines and mobiles, screen sharing, group video calling, and support for a wide variety of devices.</span></span><span data-ttu-id="28002-132">此外，WLM 用户的联合 Lync 联系人将转到 Skype 并将其好友列表的其余部分转换为 Skype，并且这些联系人的 Skype 和 Lync 之间的 IM 将立即可用。</span><span class="sxs-lookup"><span data-stu-id="28002-132"> Moreover, WLM users’ federated Lync contacts follow the transition into Skype with the rest of their buddy lists, and IM between Skype and Lync for these contacts will be available immediately.</span></span> <span data-ttu-id="28002-133">Lync 客户无需执行任何操作即可启用此服务的连续性。</span><span class="sxs-lookup"><span data-stu-id="28002-133">Lync customers do not need to do anything to enable this continuity of service.</span></span>

<span data-ttu-id="28002-134">**问：与 Yahoo 或 AOL 的联盟是否 \! 仍然可用？**</span><span class="sxs-lookup"><span data-stu-id="28002-134">**Q: Is federation with Yahoo\! or AOL still available?**</span></span>

<span data-ttu-id="28002-135">**A：** 不。</span><span class="sxs-lookup"><span data-stu-id="28002-135">**A:** No.</span></span> <span data-ttu-id="28002-136">与 Yahoo 的联盟\!</span><span class="sxs-lookup"><span data-stu-id="28002-136">Federation with Yahoo\!</span></span> <span data-ttu-id="28002-137">而且 AOL 因 Yahoo 提供了支持\!</span><span class="sxs-lookup"><span data-stu-id="28002-137">and AOL were contingent upon support from Yahoo\!</span></span> <span data-ttu-id="28002-138">和 AOL。</span><span class="sxs-lookup"><span data-stu-id="28002-138">and AOL.</span></span><span data-ttu-id="28002-139">对于这两个 Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="28002-139"> For both Yahoo\!</span></span> <span data-ttu-id="28002-140">和 AOL，服务在2014年6月30日结束。</span><span class="sxs-lookup"><span data-stu-id="28002-140">and AOL, the service ended on June 30, 2014.</span></span> 

<span data-ttu-id="28002-141">**问：在购买 Lync 之前，可以试用 Skype 连接吗？**</span><span class="sxs-lookup"><span data-stu-id="28002-141">**Q: Can I trial Skype connectivity before purchasing Lync?**</span></span>

<span data-ttu-id="28002-142">**A：** 在试用版中不提供 Skype 连接。</span><span class="sxs-lookup"><span data-stu-id="28002-142">**A:** Skype connectivity is not offered on a trial basis.</span></span> <span data-ttu-id="28002-143">在试用版中，鼓励具有符合条件的许可证的 Lync 客户只需注册服务即可进行测试。</span><span class="sxs-lookup"><span data-stu-id="28002-143">In place of a trial, Lync customers with eligible licenses are encouraged to simply sign up for the service to test.</span></span>

<span data-ttu-id="28002-144">**问：设置需要什么信息？**</span><span class="sxs-lookup"><span data-stu-id="28002-144">**Q: What information is required for provisioning?**</span></span>

<span data-ttu-id="28002-145">**A：** 若要在合格的许可证下提交设置请求，您需要具备以下条件：</span><span class="sxs-lookup"><span data-stu-id="28002-145">**A:** To submit a provisioning request under a qualified license, you need the following:</span></span>

  - <span data-ttu-id="28002-146">Microsoft 协议编号：</span><span class="sxs-lookup"><span data-stu-id="28002-146">Microsoft agreement number:</span></span>
    
      - <span data-ttu-id="28002-147">Microsoft 批量许可支持： Microsoft 批量许可协议编号</span><span class="sxs-lookup"><span data-stu-id="28002-147">Microsoft Volume Licensing Support: Microsoft Volume Licensing Agreement number</span></span>
    
      - <span data-ttu-id="28002-148">Microsoft 合作伙伴网络： Headquarter 合作伙伴 ID</span><span class="sxs-lookup"><span data-stu-id="28002-148">Microsoft Partner Network: Headquarter partner ID</span></span>
    
      - <span data-ttu-id="28002-149">服务提供商许可协议：初始注册号码</span><span class="sxs-lookup"><span data-stu-id="28002-149">Service Provider Licensing Agreement: Initial enrollment number</span></span>
    
      - <span data-ttu-id="28002-150">高容量服务：产品注册号</span><span class="sxs-lookup"><span data-stu-id="28002-150">High Volume Services: Product enrollment number</span></span>

  - <span data-ttu-id="28002-151">访问边缘服务的 (Fqdn) 完全限定的域名称。</span><span class="sxs-lookup"><span data-stu-id="28002-151">Fully qualified domain names (FQDNs) for the Access Edge service.</span></span>
    
      - <span data-ttu-id="28002-152">至少需要一个访问边缘服务的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="28002-152">FQDN for at least one Access Edge service is required.</span></span>
    
      - <span data-ttu-id="28002-153">如果您的组织有多台服务器运行访问边缘服务，请为每个额外的访问边缘服务指定 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="28002-153">If your organization has more than one server running the Access Edge service, specify the FQDNs for each additional Access Edge service.</span></span> <span data-ttu-id="28002-154">重要说明：如果您先前已为访问边缘服务指定了 FQDN，并且想要更改它，则为更改设置可能需要几天才能完成，并可能导致服务中断。</span><span class="sxs-lookup"><span data-stu-id="28002-154">Important: If you previously specified an FQDN for the Access Edge service and want to change it, provisioning for the change can take several days to complete and can result in a disruption in service.</span></span> <span data-ttu-id="28002-155">为了防止服务中断，我们建议您保留以前指定的访问边缘服务的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="28002-155">To prevent service disruption, we recommend that you maintain the previously specified FQDN of the Access Edge service.</span></span>

  - <span data-ttu-id="28002-156">会话初始协议 (SIP) 域 (s) 。</span><span class="sxs-lookup"><span data-stu-id="28002-156">Session Initiation Protocol (SIP) domain(s).</span></span> <span data-ttu-id="28002-157">这是用户当前用于即时消息的 SIP URI 的域后缀。</span><span class="sxs-lookup"><span data-stu-id="28002-157">This is the domain suffix of the SIP URI that users currently use for instant messaging.</span></span> <span data-ttu-id="28002-158">如果您的组织具有多个 SIP 域，请为用于即时消息的每个域指定域后缀。</span><span class="sxs-lookup"><span data-stu-id="28002-158">If your organization has more than one SIP domain, specify the domain suffix for each domain used for instant messaging.</span></span> <span data-ttu-id="28002-159">例如，对于 user1@contoso.com，请指定 SIP 域的 contoso.com;对于 user1@example.fabrikam.com，将 example.fabrikam.com 指定为 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="28002-159">For example, for user1@contoso.com, specify contoso.com for the SIP domain; for user1@example.fabrikam.com, specify example.fabrikam.com as the SIP domain.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="28002-160">仅指定 SIP 域的域后缀。</span><span class="sxs-lookup"><span data-stu-id="28002-160">Specify only the domain suffix for the SIP domain.</span></span> <span data-ttu-id="28002-161">请勿为 SIP 域指定任何 Fqdn，包括访问边缘服务的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="28002-161">Do not specify any FQDNs, including the FQDN for the Access Edge service, for the SIP domain.</span></span>

    
    </div>

  - <span data-ttu-id="28002-162">联系人信息。</span><span class="sxs-lookup"><span data-stu-id="28002-162">Contact information.</span></span> <span data-ttu-id="28002-163">为您指定的每个 SIP 域的管理员指定一个电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="28002-163">Specify an e-mail address for the administrator of each SIP domain that you specify.</span></span>

<span data-ttu-id="28002-164">**问：如何在拆分域方案中启用 Lync-Skype 连接？**</span><span class="sxs-lookup"><span data-stu-id="28002-164">**Q: How do I enable Lync-Skype Connectivity in a split-domain scenario?**</span></span>

<span data-ttu-id="28002-165">**A：** 如果您具有 Lync Online 2013 和 Lync Server 本地拆分域方案 (与使用相同 SIP 域的联机和本地用户) ，请通过以下两个步骤按以下顺序启用 Lync-Skype 连接</span><span class="sxs-lookup"><span data-stu-id="28002-165">**A:** If you have a Lync Online 2013 and Lync Server on-premise split-domain scenario (with users on both online and on-premise using the same SIP domain), enable Lync-Skype Connectivity by doing these two steps in the following order</span></span>

1.  <span data-ttu-id="28002-166">按照 PIC 设置指南中的说明，设置本地 Lync-Skype 连接。</span><span class="sxs-lookup"><span data-stu-id="28002-166">Set up on-premise Lync-Skype Connectivity as explained in the PIC Provisioning Guide.</span></span>

2.  <span data-ttu-id="28002-167">等待您看到您的域已由 Microsoft 设置的确认。</span><span class="sxs-lookup"><span data-stu-id="28002-167">Wait until you see confirmation that your domain has been provisioned by Microsoft.</span></span>

3.  <span data-ttu-id="28002-168">在您看到确认后，请使用 Lync 管理中心打开 "外部通信"。</span><span class="sxs-lookup"><span data-stu-id="28002-168">After you see the confirmation, use the Lync admin center to turn on “external communications”.</span></span> <span data-ttu-id="28002-169">有关详细信息，请参阅 [https://office.microsoft.com/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](https://office.microsoft.com/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356)</span><span class="sxs-lookup"><span data-stu-id="28002-169">For more information, see [https://office.microsoft.com/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](https://office.microsoft.com/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356)</span></span>

<span data-ttu-id="28002-170">此顺序非常重要。</span><span class="sxs-lookup"><span data-stu-id="28002-170">This order is important.</span></span><span data-ttu-id="28002-171">您必须先设置本地连接，然后才能在 Lync Online 中启用通信。</span><span class="sxs-lookup"><span data-stu-id="28002-171">  You must set up the on-premise connectivity before you enable the communications in Lync Online.</span></span> <span data-ttu-id="28002-172">如果订单已冲销，则在内部部署中输入的信息 <https://pic.lync.com> 将不会经过。</span><span class="sxs-lookup"><span data-stu-id="28002-172">If the order is reversed, the information entered for on-premise in <https://pic.lync.com> will not go through.</span></span> <span data-ttu-id="28002-173">如果已经为与此域的外部通信设置了 Lync Online，则必须将其关闭，等待24小时，然后重新开始，首先在中输入本地信息， <https://pic.lync.com> 然后再打开 Lync Online 的外部通信。</span><span class="sxs-lookup"><span data-stu-id="28002-173">If you have already set up Lync Online for external communications with this domain, you must turn it off, wait for 24 hours, and start again, first by entering your on-premise information at <https://pic.lync.com> and then turning on external communications for Lync Online.</span></span>

<span data-ttu-id="28002-174">**问：是否可以为 Skype 连接设置多个访问边缘服务 Fqdn？**</span><span class="sxs-lookup"><span data-stu-id="28002-174">**Q: Can I provision multiple Access Edge service FQDNs for Skype connectivity?**</span></span>

<span data-ttu-id="28002-175">**A：** 可以为一个或多个域仅设置一个访问边缘 FQDN。</span><span class="sxs-lookup"><span data-stu-id="28002-175">**A:** You can provision only one access edge FQDN for one or more domains.</span></span> <span data-ttu-id="28002-176">您可以设置多个访问边缘 Fqdn （每个请求最多10个）（如果它们具有不同的域）。</span><span class="sxs-lookup"><span data-stu-id="28002-176">You can provision multiple access edge FQDNs, up to 10 per request, if they have distinct domains.</span></span>

<span data-ttu-id="28002-177">**问：是否可以获取为组织请求预配而找到的 Microsoft 帐户电子邮件地址列表？**</span><span class="sxs-lookup"><span data-stu-id="28002-177">**Q: Can I obtain the list of Microsoft Account e-mail addresses that you find for the organization requesting provisioning?**</span></span>

<span data-ttu-id="28002-178">**A：** 不。</span><span class="sxs-lookup"><span data-stu-id="28002-178">**A:** No.</span></span> <span data-ttu-id="28002-179">这些地址被视为个人身份信息且不共享。</span><span class="sxs-lookup"><span data-stu-id="28002-179">These addresses are considered personally identifiable information and are not shared.</span></span>

<span data-ttu-id="28002-180">**问：我如何添加 ID 包含 Windows Live 不支持的域的 Windows Live Messenger 联系人？**</span><span class="sxs-lookup"><span data-stu-id="28002-180">**Q: How do I add a Windows Live Messenger contact that has an ID containing a domain other than those supported by Windows Live?**</span></span>

<span data-ttu-id="28002-181">**A：** 如果要使用包含非 Windows Live 域的帐户或 ID 添加 Windows Live Messenger 用户，请按以下格式输入该地址： \<user name\> (\<domain name\>) @msn .com，其中 \<domain name\> 是用户的电子邮件地址中的域名。</span><span class="sxs-lookup"><span data-stu-id="28002-181">**A:** If you are adding a Windows Live Messenger user with an account or ID with a non-Windows Live domain, enter the address in the following format: \<user name\>(\<domain name\>)@msn.com, where \<domain name\> is the domain name in the e-mail address of the user.</span></span> <span data-ttu-id="28002-182">例如，如果您想要添加 ted@contoso.com，则可以使用以下格式：李小明 (contoso.com) @msn .com。</span><span class="sxs-lookup"><span data-stu-id="28002-182">For example, if you wanted to add ted@contoso.com, you would use the following format: ted(contoso.com)@msn.com.</span></span> <span data-ttu-id="28002-183">有关 Windows Live 管理的域的列表，请参阅中的 "在安装 Live 通信服务器 Service Pack 1 后，公共即时消息中出现的已知问题" 部分中的 "支持的域" 部分 https://support.microsoft.com/?kbid=897567 。</span><span class="sxs-lookup"><span data-stu-id="28002-183">For a list of domains that are administered by Windows Live, see the Supported Domains section in “Known Issues That Occur with Public Instant Messaging After You Install Live Communications Server Service Pack 1” at https://support.microsoft.com/?kbid=897567.</span></span>

<span data-ttu-id="28002-184">**问：预配过程需要多长时间？**</span><span class="sxs-lookup"><span data-stu-id="28002-184">**Q: How long does the provisioning process take?**</span></span>

<span data-ttu-id="28002-185">**A：** 设置可能需要30天。</span><span class="sxs-lookup"><span data-stu-id="28002-185">**A:** Provisioning can take up to 30 days.</span></span>

<span data-ttu-id="28002-186">**问：如何知道设置已完成？**</span><span class="sxs-lookup"><span data-stu-id="28002-186">**Q: How will I know when provisioning is complete?**</span></span>

<span data-ttu-id="28002-187">**A：** Microsoft 将在设置完成时发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="28002-187">**A:** Microsoft will send e-mail notification when provisioning is complete.</span></span>

<span data-ttu-id="28002-188">**问：怎样才能更新我提交的配置或联系人详细信息？**</span><span class="sxs-lookup"><span data-stu-id="28002-188">**Q: How can I update the configuration or contact details that I submit?**</span></span>

<span data-ttu-id="28002-189">**A：** 完成设置后，您可以在用于请求设置的相同网站上更新您的信息。</span><span class="sxs-lookup"><span data-stu-id="28002-189">**A:** You can update your information at the same web site that you used to request provisioning, after provisioning is complete.</span></span> <span data-ttu-id="28002-190">输入您的协议号码，然后单击 "更新服务"。</span><span class="sxs-lookup"><span data-stu-id="28002-190">Enter your agreement number, and then click Update service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>
