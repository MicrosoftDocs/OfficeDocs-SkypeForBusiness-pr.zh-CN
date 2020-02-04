---
title: Lync Server 2013：管理组织的外部访问策略
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
ms.openlocfilehash: e9ade02d1c7a3eae1d65cd62ba69684129105dce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a><span data-ttu-id="eccd3-102">在 Lync Server 2013 中管理组织的外部访问策略</span><span class="sxs-lookup"><span data-stu-id="eccd3-102">Manage external access policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eccd3-103">_**主题上次修改时间：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="eccd3-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="eccd3-104">部署一个或多个边缘服务器后，必须启用组织支持的外部访问类型。</span><span class="sxs-lookup"><span data-stu-id="eccd3-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="eccd3-105">默认情况下，没有配置任何可支持外部用户访问的策略，包括远程用户访问权限、联盟用户访问权限，即使你已启用组织的外部用户访问支持。</span><span class="sxs-lookup"><span data-stu-id="eccd3-105">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization.</span></span> <span data-ttu-id="eccd3-106">若要控制外部用户访问的使用，必须配置一个或多个策略，指定每个策略支持的外部用户访问类型。</span><span class="sxs-lookup"><span data-stu-id="eccd3-106">To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy.</span></span> <span data-ttu-id="eccd3-107">以下策略作用域可用于创建和配置。</span><span class="sxs-lookup"><span data-stu-id="eccd3-107">The following policy scopes are available for creation and configuration.</span></span> <span data-ttu-id="eccd3-108">默认情况下，创建全局策略，但不能删除。</span><span class="sxs-lookup"><span data-stu-id="eccd3-108">By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="eccd3-109">**全局策略**   当你部署 Edge 服务器时，将创建全局策略。</span><span class="sxs-lookup"><span data-stu-id="eccd3-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="eccd3-110">默认情况下，全局策略中未启用任何外部用户访问选项。</span><span class="sxs-lookup"><span data-stu-id="eccd3-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="eccd3-111">若要在全局级别支持外部用户访问，请将全局策略配置为支持一种或多种类型的外部用户访问选项。</span><span class="sxs-lookup"><span data-stu-id="eccd3-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="eccd3-112">全局策略适用于组织中的所有用户，但网站策略和用户策略替代全局策略。</span><span class="sxs-lookup"><span data-stu-id="eccd3-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="eccd3-113">如果您删除全局策略，则不会将其删除。</span><span class="sxs-lookup"><span data-stu-id="eccd3-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="eccd3-114">而是将其重置为默认设置。</span><span class="sxs-lookup"><span data-stu-id="eccd3-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="eccd3-115">**网站策略**   您可以创建和配置一个或多个网站策略，以限制对特定网站的外部用户访问的支持。</span><span class="sxs-lookup"><span data-stu-id="eccd3-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="eccd3-116">站点策略中的配置将覆盖全局策略，但是仅限于站点策略所涉及的特定站点。</span><span class="sxs-lookup"><span data-stu-id="eccd3-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="eccd3-117">例如，如果在全局策略中启用 "远程用户访问"，则可以指定一个网站策略，该策略可禁用特定网站的远程用户访问。</span><span class="sxs-lookup"><span data-stu-id="eccd3-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="eccd3-118">默认情况下，网站策略应用于该网站的所有用户，但你可以将用户策略分配给用户以替代网站策略设置。</span><span class="sxs-lookup"><span data-stu-id="eccd3-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="eccd3-119">**用户策略**   您可以创建和配置一个或多个用户策略，以限制对特定用户的远程用户访问的支持。</span><span class="sxs-lookup"><span data-stu-id="eccd3-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="eccd3-120">用户策略中的配置替代全局和网站策略，但仅适用于为其分配用户策略的特定用户。</span><span class="sxs-lookup"><span data-stu-id="eccd3-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="eccd3-121">例如，如果在全局策略和网站策略中启用远程用户访问，则可以指定禁用远程用户访问的用户策略，然后将该用户策略分配给特定用户。</span><span class="sxs-lookup"><span data-stu-id="eccd3-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="eccd3-122">如果创建用户策略，则必须将其应用于一个或多个用户，然后它才会生效。</span><span class="sxs-lookup"><span data-stu-id="eccd3-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="eccd3-123">在一个策略级别应用的 Lync Server 策略设置可以覆盖在其他策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="eccd3-123">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="eccd3-124">Lync 服务器策略优先级为：用户策略（最受影响）覆盖网站策略，然后网站策略覆盖全局策略（最不影响）。</span><span class="sxs-lookup"><span data-stu-id="eccd3-124">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="eccd3-125">这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。</span><span class="sxs-lookup"><span data-stu-id="eccd3-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>



</div>

<span data-ttu-id="eccd3-126">这些选项包括以下类型的外部访问：</span><span class="sxs-lookup"><span data-stu-id="eccd3-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="eccd3-127">\*\*\*\*   如果你希望支持用户对联盟伙伴域的访问权限，请启用与联盟用户的通信。</span><span class="sxs-lookup"><span data-stu-id="eccd3-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="eccd3-128">此设置将用户配置为与其他 SIP 联盟域以及托管提供商（如 Microsoft Office 365）进行通信的能力。</span><span class="sxs-lookup"><span data-stu-id="eccd3-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft Office 365.</span></span> <span data-ttu-id="eccd3-129">选择此设置允许你选择允许与 XMPP 联盟域通信的选项。</span><span class="sxs-lookup"><span data-stu-id="eccd3-129">Selecting this setting allows you to select the option to allow communication with XMPP federated domains.</span></span>
    
    <span data-ttu-id="eccd3-130">作为一个选项，如果你首先选择 "**启用与联盟用户的通信**"，则可以选择 "**启用与 XMPP 联盟合作伙伴的通信**"。</span><span class="sxs-lookup"><span data-stu-id="eccd3-130">As an option, you can select **Enable communications with XMPP federated partners** if you first select **Enable communications with federated users**.</span></span> <span data-ttu-id="eccd3-131">XMPP 联盟是使用可扩展消息和状态协议（XMPP）的组织的联盟。</span><span class="sxs-lookup"><span data-stu-id="eccd3-131">XMPP federation is a federation with organizations that use extensible messaging and presence protocol (XMPP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eccd3-132">如果启用 XMPP 联合身份验证，还必须在拓扑生成器的 "边缘池配置" 部分中选择 "部署<STRONG>XMPP 联盟</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="eccd3-132">If you enable XMPP federation, you must also select to deploy <STRONG>XMPP federation</STRONG> in the Edge pools configuration section of Topology Builder.</span></span> <span data-ttu-id="eccd3-133">为 XMPP 联合身份验证将在 Edge 服务器上部署 XMPP 代理，并在前端服务器上部署 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="eccd3-133">Configuring for XMPP federation deploys an XMPP Proxy on the Edge Server and an XMPP gateway on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="eccd3-134">**启用与远程用户**   的通信如果你希望你的组织中的用户（如出差的远程办公和用户）能够通过 Internet 连接到 Lync 服务器，请启用此选项。</span><span class="sxs-lookup"><span data-stu-id="eccd3-134">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

  - <span data-ttu-id="eccd3-135">**启用与公共用户**   的通信如果希望内部用户能够与公共 IM 提供商的联系人（如 Windows Live、Yahoo\!和北美网络（AOL））通信，请启用此选项。</span><span class="sxs-lookup"><span data-stu-id="eccd3-135">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts, such as those provided by Windows Live, Yahoo\!, and America Online (AOL).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="eccd3-136">从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或续订协议。</span><span class="sxs-lookup"><span data-stu-id="eccd3-136">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="eccd3-137">具有活动许可证的客户将能够继续与 Yahoo！进行联盟</span><span class="sxs-lookup"><span data-stu-id="eccd3-137">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="eccd3-138">Messenger，直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="eccd3-138">Messenger until the service shut down date.</span></span> <span data-ttu-id="eccd3-139">AOL 和 Yahoo！的有效期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="eccd3-139">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="eccd3-140">已宣布。</span><span class="sxs-lookup"><span data-stu-id="eccd3-140">has been announced.</span></span> <span data-ttu-id="eccd3-141">有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。</span><span class="sxs-lookup"><span data-stu-id="eccd3-141">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="eccd3-142">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个每个用户每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="eccd3-142">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="eccd3-143">Messenger.</span><span class="sxs-lookup"><span data-stu-id="eccd3-143">Messenger.</span></span> <span data-ttu-id="eccd3-144">Microsoft 提供此服务的能力已作为对 Yahoo！的支持，它的底层协议被向下缠绕。</span><span class="sxs-lookup"><span data-stu-id="eccd3-144">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="eccd3-145">Lync 比以往更多，是一种强大的工具，用于跨组织和全球各地的人员进行连接。</span><span class="sxs-lookup"><span data-stu-id="eccd3-145">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="eccd3-146">与 Windows Live Messenger 的联盟不需要除 Lync 标准 CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="eccd3-146">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="eccd3-147">Skype 联盟将添加到此列表，使 Lync 用户可以通过 IM 和语音与成百上千人联系。</span><span class="sxs-lookup"><span data-stu-id="eccd3-147">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="eccd3-148">除了启用外部用户访问支持外，你还必须配置策略，以控制在你的组织中使用外部用户访问，然后再向用户提供任何类型的外部用户访问权限。</span><span class="sxs-lookup"><span data-stu-id="eccd3-148">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="eccd3-149">有关创建、配置和应用外部用户访问策略的详细信息，请参阅<A href="lync-server-2013-enable-or-disable-remote-user-access.md">在 Lync Server 2013 中启用或禁用远程用户访问</A>。</span><span class="sxs-lookup"><span data-stu-id="eccd3-149">For details about creating, configuring, and applying policies for external user access see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="eccd3-150">**使用 Windows PowerShell cmdlet 查看外部访问策略**</span><span class="sxs-lookup"><span data-stu-id="eccd3-150">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="eccd3-151">你可以使用 Lync Server 命令行管理程序和**CsExternalAccessPolicy** cmdlet 查看外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="eccd3-151">You can view external access policies by using Lync Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="eccd3-152">你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="eccd3-152">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="eccd3-153">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="eccd3-153">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="eccd3-154">若要查看有关所有外部访问策略的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="eccd3-154">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsExternalAccessPolicy
    
    <span data-ttu-id="eccd3-155">此命令会返回类似下列信息：</span><span class="sxs-lookup"><span data-stu-id="eccd3-155">This command returns information similar to the following:</span></span>
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a><span data-ttu-id="eccd3-156">本节内容</span><span class="sxs-lookup"><span data-stu-id="eccd3-156">In This Section</span></span>

  - [<span data-ttu-id="eccd3-157">在 Lync Server 2013 中配置策略以控制联盟用户访问</span><span class="sxs-lookup"><span data-stu-id="eccd3-157">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [<span data-ttu-id="eccd3-158">在 Lync Server 2013 中配置策略以控制 XMPP 联盟用户访问</span><span class="sxs-lookup"><span data-stu-id="eccd3-158">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [<span data-ttu-id="eccd3-159">在 Lync Server 2013 中配置策略以控制远程用户访问</span><span class="sxs-lookup"><span data-stu-id="eccd3-159">Configure policies to control remote user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [<span data-ttu-id="eccd3-160">在 Lync Server 2013 中配置策略以控制公共用户访问</span><span class="sxs-lookup"><span data-stu-id="eccd3-160">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [<span data-ttu-id="eccd3-161">在 Lync Server 2013 中将外部用户访问策略分配到启用 Lync 的用户</span><span class="sxs-lookup"><span data-stu-id="eccd3-161">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="eccd3-162">在 Lync Server 2013 中重置或删除外部用户访问策略</span><span class="sxs-lookup"><span data-stu-id="eccd3-162">Resetting or deleting external user access policies in Lync Server 2013</span></span>](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

