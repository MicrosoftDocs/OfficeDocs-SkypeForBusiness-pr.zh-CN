---
title: Lync Server 2013：管理组织的外部访问策略
description: Lync Server 2013：管理组织的外部访问策略。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f0bb0e6764f67403065187c62debef13c77fcc3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558408"
---
# <a name="manage-external-access-policy-in-lync-server-2013"></a><span data-ttu-id="6ee49-103">在 Lync Server 2013 中管理外部访问策略</span><span class="sxs-lookup"><span data-stu-id="6ee49-103">Manage external access policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ee49-104">_**上次修改的主题：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="6ee49-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="6ee49-105">部署一台或多台 Edge 服务器后，必须启用组织支持的外部访问类型。</span><span class="sxs-lookup"><span data-stu-id="6ee49-105">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="6ee49-p101">默认情况下，即使已为组织启用对外部用户访问的支持，也不会将任何策略配置为支持外部用户访问（包括远程用户访问、联盟用户访问）。要控制外部用户访问的使用，必须配置一个或多个策略，并指定每个策略支持的外部用户访问类型。可创建和配置以下策略范围。默认情况下，将创建全局策略且无法被删除。</span><span class="sxs-lookup"><span data-stu-id="6ee49-p101">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization. To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy. The following policy scopes are available for creation and configuration. By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="6ee49-110">**全局策略**   在部署 Edge 服务器时创建全局策略。</span><span class="sxs-lookup"><span data-stu-id="6ee49-110">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="6ee49-111">默认情况下，全局策略中未启用任何外部用户访问选项。</span><span class="sxs-lookup"><span data-stu-id="6ee49-111">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="6ee49-112">要支持全局级别的外部用户访问，请将全局策略配置为支持一种或多种外部用户访问选项。</span><span class="sxs-lookup"><span data-stu-id="6ee49-112">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="6ee49-113">全局策略适用于组织中的所有用户，但站点策略和用户策略将覆盖全局策略。</span><span class="sxs-lookup"><span data-stu-id="6ee49-113">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="6ee49-114">如果删除全局策略，则不要将其移除。</span><span class="sxs-lookup"><span data-stu-id="6ee49-114">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="6ee49-115">相反，将其重置为默认设置。</span><span class="sxs-lookup"><span data-stu-id="6ee49-115">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="6ee49-116">**站点策略**   可创建和配置一个或多个站点策略，以将外部用户访问限制到指定站点。</span><span class="sxs-lookup"><span data-stu-id="6ee49-116">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="6ee49-117">站点策略中的配置将覆盖全局策略，但仅适用于站点策略覆盖的指定站点。</span><span class="sxs-lookup"><span data-stu-id="6ee49-117">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="6ee49-118">例如，如果在全局策略中启用远程用户访问，则可以指定禁用特定站点的远程用户访问的站点策略。</span><span class="sxs-lookup"><span data-stu-id="6ee49-118">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="6ee49-119">默认情况下，站点策略应用于该站点的所有用户，但可以将用户策略分配给用户以覆盖站点策略设置。</span><span class="sxs-lookup"><span data-stu-id="6ee49-119">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="6ee49-120">**用户策略**   可以创建和配置一个或多个用户策略，以将远程用户访问支持限制到指定用户。</span><span class="sxs-lookup"><span data-stu-id="6ee49-120">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="6ee49-121">用户策略中的配置将覆盖全局和站点策略，但仅适用于为其分配策略的特定用户。</span><span class="sxs-lookup"><span data-stu-id="6ee49-121">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="6ee49-122">例如，如果在全局策略和站点策略中启用远程用户访问，则可以指定禁用远程用户访问的用户策略，然后将该用户策略分配给特定用户。</span><span class="sxs-lookup"><span data-stu-id="6ee49-122">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="6ee49-123">如果创建用户策略，必须将其应用于一个或多个用户，然后才能生效。</span><span class="sxs-lookup"><span data-stu-id="6ee49-123">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6ee49-124">在一个策略级别应用的 Lync Server 策略设置可以覆盖在另一个策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="6ee49-124">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="6ee49-125">Lync Server 策略优先级为：用户策略 (影响最大的) 替代网站策略，然后网站策略将覆盖全局策略 (最小影响) 。</span><span class="sxs-lookup"><span data-stu-id="6ee49-125">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="6ee49-126">这意味着，策略设置越接近策略影响的对象，它对对象的影响就越大。</span><span class="sxs-lookup"><span data-stu-id="6ee49-126">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>



</div>

<span data-ttu-id="6ee49-127">这些选项包括以下类型的外部访问：</span><span class="sxs-lookup"><span data-stu-id="6ee49-127">These options include the following types of external access:</span></span>

  - <span data-ttu-id="6ee49-128">**启用与联盟用户的通信**   如果要支持用户对联合伙伴域的访问，则启用此选项。</span><span class="sxs-lookup"><span data-stu-id="6ee49-128">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="6ee49-129">此设置配置用户与其他 SIP 联盟域进行通信的能力，以及 Microsoft 365 等托管提供程序。</span><span class="sxs-lookup"><span data-stu-id="6ee49-129">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft 365.</span></span> <span data-ttu-id="6ee49-130">通过选择此设置，可以选择允许与 XMPP 联盟域进行通信的选项。</span><span class="sxs-lookup"><span data-stu-id="6ee49-130">Selecting this setting allows you to select the option to allow communication with XMPP federated domains.</span></span>
    
    <span data-ttu-id="6ee49-p107">作为一种选择，如果您先选择“启用与联盟用户的通信”\*\*\*\*，则可以选择“启用与 XMPP 联盟伙伴的通信”\*\*\*\*。XMPP 联盟是与使用可扩展消息传递和状态协议 (XMPP) 的组织的联盟。</span><span class="sxs-lookup"><span data-stu-id="6ee49-p107">As an option, you can select **Enable communications with XMPP federated partners** if you first select **Enable communications with federated users**. XMPP federation is a federation with organizations that use extensible messaging and presence protocol (XMPP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6ee49-133">如果启用 XMPP 联合身份验证，则还必须在拓扑生成器的 "边缘池" 配置部分中选择 "部署 <STRONG>XMPP 联合</STRONG> "。</span><span class="sxs-lookup"><span data-stu-id="6ee49-133">If you enable XMPP federation, you must also select to deploy <STRONG>XMPP federation</STRONG> in the Edge pools configuration section of Topology Builder.</span></span> <span data-ttu-id="6ee49-134">为 XMPP 联合身份验证将在边缘服务器上部署 XMPP 代理，并在前端服务器上部署一个 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="6ee49-134">Configuring for XMPP federation deploys an XMPP Proxy on the Edge Server and an XMPP gateway on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="6ee49-135">**启用与远程用户**     的通信如果您希望组织中的用户（如正在旅行的远程办公和用户）能够通过 Internet 连接到 Lync Server，请启用此选项。</span><span class="sxs-lookup"><span data-stu-id="6ee49-135">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

  - <span data-ttu-id="6ee49-136">**启用与公共用户**     的通信如果希望内部用户能够与公共 IM 提供商联系人（如 Windows Live、Yahoo \! 和北美在线 (AOL) 提供）进行通信，请启用此选项。</span><span class="sxs-lookup"><span data-stu-id="6ee49-136">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts, such as those provided by Windows Live, Yahoo\!, and America Online (AOL).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="6ee49-137">从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证 ( "PIC USL" ) 不再可用于购买新的或更新的协议。</span><span class="sxs-lookup"><span data-stu-id="6ee49-137">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="6ee49-138">拥有主动许可证的客户将能够继续与 Yahoo！联合联合</span><span class="sxs-lookup"><span data-stu-id="6ee49-138">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="6ee49-139">信使，直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="6ee49-139">Messenger until the service shut down date.</span></span> <span data-ttu-id="6ee49-140">AOL 和 Yahoo！的生命周期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="6ee49-140">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="6ee49-141">已宣布。</span><span class="sxs-lookup"><span data-stu-id="6ee49-141">has been announced.</span></span> <span data-ttu-id="6ee49-142">有关详细信息，请参阅 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</span><span class="sxs-lookup"><span data-stu-id="6ee49-142">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="6ee49-143">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个用户每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="6ee49-143">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="6ee49-144">Messenger.</span><span class="sxs-lookup"><span data-stu-id="6ee49-144">Messenger.</span></span> <span data-ttu-id="6ee49-145">Microsoft 提供此服务的能力因 Yahoo！中的支持而受到了支持，其下凸的底层协议。</span><span class="sxs-lookup"><span data-stu-id="6ee49-145">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="6ee49-146">Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。</span><span class="sxs-lookup"><span data-stu-id="6ee49-146">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="6ee49-147">与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="6ee49-147">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="6ee49-148">Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。</span><span class="sxs-lookup"><span data-stu-id="6ee49-148">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="6ee49-149">除了启用外部用户访问支持外，还必须在用户可以使用任何类型的外部用户访问之前，配置策略以控制组织中外部用户访问的使用。</span><span class="sxs-lookup"><span data-stu-id="6ee49-149">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="6ee49-150">有关创建、配置和应用外部用户访问策略的详细信息，请参阅 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">在 Lync Server 2013 中启用或禁用远程用户访问</A>。</span><span class="sxs-lookup"><span data-stu-id="6ee49-150">For details about creating, configuring, and applying policies for external user access see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="6ee49-151">**使用 Windows PowerShell cmdlet 查看外部访问策略**</span><span class="sxs-lookup"><span data-stu-id="6ee49-151">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="6ee49-152">您可以通过使用 Lync Server 命令行管理程序和 **set-csexternalaccesspolicy** cmdlet 来查看外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="6ee49-152">You can view external access policies by using Lync Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="6ee49-153">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6ee49-153">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6ee49-154">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="6ee49-154">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="6ee49-155">若要查看有关所有外部访问策略的信息，请在 Lync Server Management Shell 中键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="6ee49-155">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsExternalAccessPolicy
    
    <span data-ttu-id="6ee49-156">此命令会返回类似下列信息：</span><span class="sxs-lookup"><span data-stu-id="6ee49-156">This command returns information similar to the following:</span></span>
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a><span data-ttu-id="6ee49-157">本部分内容</span><span class="sxs-lookup"><span data-stu-id="6ee49-157">In This Section</span></span>

  - [<span data-ttu-id="6ee49-158">在 Lync Server 2013 中配置用于控制联合用户访问的策略</span><span class="sxs-lookup"><span data-stu-id="6ee49-158">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [<span data-ttu-id="6ee49-159">在 Lync Server 2013 中配置策略以控制 XMPP 联盟用户访问</span><span class="sxs-lookup"><span data-stu-id="6ee49-159">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [<span data-ttu-id="6ee49-160">在 Lync Server 2013 中配置策略以控制远程用户访问</span><span class="sxs-lookup"><span data-stu-id="6ee49-160">Configure policies to control remote user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [<span data-ttu-id="6ee49-161">配置策略以控制 Lync Server 2013 中的公共用户访问</span><span class="sxs-lookup"><span data-stu-id="6ee49-161">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [<span data-ttu-id="6ee49-162">在 Lync Server 2013 中将外部用户访问策略分配给启用 Lync 的用户</span><span class="sxs-lookup"><span data-stu-id="6ee49-162">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="6ee49-163">在 Lync Server 2013 中重置或删除外部用户访问策略</span><span class="sxs-lookup"><span data-stu-id="6ee49-163">Resetting or deleting external user access policies in Lync Server 2013</span></span>](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

