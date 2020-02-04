---
title: Lync Server 2013：管理对 Lync Server 2013 的联盟和外部访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing federation and external access to Lync Server 2013
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9dadc455389d95c91996b75928def8f03b06c64e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-federation-and-external-access-to-lync-server-2013"></a><span data-ttu-id="3afbd-102">管理对 Lync Server 2013 的联盟和外部访问</span><span class="sxs-lookup"><span data-stu-id="3afbd-102">Managing federation and external access to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3afbd-103">_**主题上次修改时间：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="3afbd-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="3afbd-104">部署边缘服务器或边缘池是支持外部用户的第一步。</span><span class="sxs-lookup"><span data-stu-id="3afbd-104">Deploying an Edge Server or Edge pool is the first step to supporting external users.</span></span> <span data-ttu-id="3afbd-105">有关部署边缘服务器的详细信息，请参阅部署文档中[Lync Server 2013 中的 "部署外部用户访问](lync-server-2013-deploying-external-user-access.md)"。</span><span class="sxs-lookup"><span data-stu-id="3afbd-105">For details about deploying Edge Servers, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

<span data-ttu-id="3afbd-106">在安装并配置 Lync Server 2013 的内部部署之后，你组织中的内部用户可以与在你的 Active Directory 域服务（AD DS）中具有 SIP 帐户的其他内部用户进行协作。</span><span class="sxs-lookup"><span data-stu-id="3afbd-106">After installing and configuring your internal deployment of Lync Server 2013, internal users in your organization can collaborate with other internal users who have SIP accounts in your Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="3afbd-107">协作可以包括发送和接收即时消息，以及更新状态和参与会议（也称为 "会议"）。</span><span class="sxs-lookup"><span data-stu-id="3afbd-107">Collaboration can include sending and receiving instant messages, and update of presence status and participating in conferences (also known as "meetings").</span></span> <span data-ttu-id="3afbd-108">启用和配置外部用户访问以控制受支持的外部用户是否可以与内部 Lync Server 用户进行协作。</span><span class="sxs-lookup"><span data-stu-id="3afbd-108">You enable and configure external user access to control whether supported external users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="3afbd-109">外部用户可以包括部署的远程用户、联盟用户（包括公共即时消息（IM）服务提供商的支持用户）、XMPP 联盟和会议中的匿名参与者。</span><span class="sxs-lookup"><span data-stu-id="3afbd-109">External users can include remote users of your deployment, federated users (including supported users of public instant messaging (IM) service providers), XMPP federation and anonymous participants in conferences.</span></span>

<span data-ttu-id="3afbd-110">如果你的部署包括 Lync Server 2013 Edge 服务器或边缘池的安装，则可能的通信类型的范围很大程度上与外部用户访问、与其他 SIP 联盟域的成员通信有关的选项很大扩展。SIP 联合提供商和 XMPP 联盟用户。</span><span class="sxs-lookup"><span data-stu-id="3afbd-110">If your deployment included the installation of a Lync Server 2013 Edge Server or an Edge pool, the scope of possible communication types is greatly expanded with a number of options for external user access, communication with members of other SIP federated domains, SIP federated providers, and XMPP federated users.</span></span> <span data-ttu-id="3afbd-111">在设置边缘服务器或边缘池后，启用要提供的外部用户访问类型，并配置策略以控制外部访问。</span><span class="sxs-lookup"><span data-stu-id="3afbd-111">After setting up the Edge Server or Edge pool, you enable the types of external user access that you want to provide, and configure the policies to control for the external access.</span></span> <span data-ttu-id="3afbd-112">在 Lync Server 2013 中，你可以使用 Lync Server 控制面板、Lync Server Management Shell 或两者（基于任务要求）启用和配置外部用户访问和策略。</span><span class="sxs-lookup"><span data-stu-id="3afbd-112">In Lync Server 2013, you enable and configure external user access and policies using the Lync Server Control Panel, the Lync Server Management Shell or both, based on the task requirements.</span></span> <span data-ttu-id="3afbd-113">有关这些管理工具的详细信息，请参阅 operations 文档中的[Lync server 2013 管理工具](lync-server-2013-lync-server-administrative-tools.md)、操作文档中的[Lync Server 2013 管理外壳](lync-server-2013-lync-server-management-shell.md)以及安装操作文档中的[lync server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="3afbd-113">For details about these management tools, see [Lync Server 2013 administrative tools](lync-server-2013-lync-server-administrative-tools.md) in the Operations documentation, [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) in the Operations documentation, and [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md) in the Operations documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3afbd-114">为外部用户访问设计配置和策略时，必须了解策略的优先级以及策略的应用方式。</span><span class="sxs-lookup"><span data-stu-id="3afbd-114">When you design your configuration and policies for external user access, you must understand the precedence of policies and how the policies are applied.</span></span> <span data-ttu-id="3afbd-115">在一个策略级别应用的 Lync Server 策略设置可以覆盖在其他策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="3afbd-115">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="3afbd-116">Lync 服务器策略优先级为：用户策略（最受影响）覆盖网站策略，然后网站策略覆盖全局策略（最不影响）。</span><span class="sxs-lookup"><span data-stu-id="3afbd-116">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="3afbd-117">这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。</span><span class="sxs-lookup"><span data-stu-id="3afbd-117">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>



</div>

<span data-ttu-id="3afbd-118">默认情况下，未将任何策略配置为支持外部用户访问，包括远程用户访问权限、联合用户访问，即使你已启用组织的外部用户访问支持。</span><span class="sxs-lookup"><span data-stu-id="3afbd-118">By default, no policies are configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization.</span></span> <span data-ttu-id="3afbd-119">若要控制外部用户访问的使用，必须配置一个或多个策略，指定每个策略支持的外部用户访问类型。</span><span class="sxs-lookup"><span data-stu-id="3afbd-119">To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy.</span></span> <span data-ttu-id="3afbd-120">这包括以下外部访问策略：</span><span class="sxs-lookup"><span data-stu-id="3afbd-120">This includes the following external access policies:</span></span>

  - <span data-ttu-id="3afbd-121">**全局策略**   当你部署 Edge 服务器时，将创建全局策略。</span><span class="sxs-lookup"><span data-stu-id="3afbd-121">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="3afbd-122">默认情况下，全局策略中未启用任何外部用户访问选项。</span><span class="sxs-lookup"><span data-stu-id="3afbd-122">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="3afbd-123">若要在全局级别支持外部用户访问，请将全局策略配置为支持一种或多种类型的外部用户访问选项。</span><span class="sxs-lookup"><span data-stu-id="3afbd-123">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="3afbd-124">全局策略适用于组织中的所有用户，但网站策略和用户策略替代全局策略。</span><span class="sxs-lookup"><span data-stu-id="3afbd-124">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="3afbd-125">如果您删除全局策略，则不会将其删除。</span><span class="sxs-lookup"><span data-stu-id="3afbd-125">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="3afbd-126">而是将其重置为默认设置。</span><span class="sxs-lookup"><span data-stu-id="3afbd-126">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="3afbd-127">**网站策略**   您可以创建和配置一个或多个网站策略，以限制对特定网站的外部用户访问的支持。</span><span class="sxs-lookup"><span data-stu-id="3afbd-127">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="3afbd-128">站点策略中的配置将覆盖全局策略，但是仅限于站点策略所涉及的特定站点。</span><span class="sxs-lookup"><span data-stu-id="3afbd-128">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="3afbd-129">例如，如果在全局策略中启用 "远程用户访问"，则可以指定一个网站策略，该策略可禁用特定网站的远程用户访问。</span><span class="sxs-lookup"><span data-stu-id="3afbd-129">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="3afbd-130">默认情况下，网站策略应用于该网站的所有用户，但你可以将用户策略分配给用户以替代网站策略设置。</span><span class="sxs-lookup"><span data-stu-id="3afbd-130">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="3afbd-131">**用户策略**   您可以创建和配置一个或多个用户策略，以限制对特定用户的远程用户访问的支持。</span><span class="sxs-lookup"><span data-stu-id="3afbd-131">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="3afbd-132">用户策略中的配置替代全局和网站策略，但仅适用于为其分配用户策略的特定用户。</span><span class="sxs-lookup"><span data-stu-id="3afbd-132">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="3afbd-133">例如，如果在全局策略和网站策略中启用远程用户访问，则可以指定禁用远程用户访问的用户策略，然后将该用户策略分配给特定用户。</span><span class="sxs-lookup"><span data-stu-id="3afbd-133">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="3afbd-134">如果创建用户策略，则必须将其应用于一个或多个用户，然后它才会生效。</span><span class="sxs-lookup"><span data-stu-id="3afbd-134">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>

<span data-ttu-id="3afbd-135">若要确定要创建或编辑哪些配置设置以及需要哪些策略，请参阅以下决策点：</span><span class="sxs-lookup"><span data-stu-id="3afbd-135">To determine which configuration settings and which policies you need to create or edit, refer to the following decision points:</span></span>

<span data-ttu-id="3afbd-136">**您是否希望允许您的域的内部和外部用户能够使用即时消息、Web 会议和音频/视频进行协作？**</span><span class="sxs-lookup"><span data-stu-id="3afbd-136">**Do you want to allow internal and external users of your domain to be able to collaborate using instant messaging, Web conferencing, and Audio/Video?**</span></span>

<span data-ttu-id="3afbd-137">按照主题[配置策略来控制 Lync server 2013 中的远程用户访问](lync-server-2013-configure-policies-to-control-remote-user-access.md)，以及[在 lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)，详细配置设置</span><span class="sxs-lookup"><span data-stu-id="3afbd-137">Configure the settings as detailed in the topics [Configure policies to control remote user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md), and [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)</span></span>

<span data-ttu-id="3afbd-138">**你是否希望允许匿名用户出席并邀请你的部署中的用户托管的会议？**</span><span class="sxs-lookup"><span data-stu-id="3afbd-138">**Do you want to allow anonymous users to attend and be invited to conferences hosted by users in your deployment?**</span></span>

<span data-ttu-id="3afbd-139">详细配置本主题中的详细设置在 lync server 2013 中的 "[分配会议策略" 以支持匿名用户](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)、在 lync server [2013 中创建或修改会议策略](lync-server-2013-create-or-modify-a-conferencing-policy.md)以及[lync server 2013 的会议策略设置参考](lync-server-2013-conferencing-policy-settings-reference.md)</span><span class="sxs-lookup"><span data-stu-id="3afbd-139">Configure the settings as detailed in the topic [Assign conferencing policies to support anonymous users in Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md), [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) and [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)</span></span>

<span data-ttu-id="3afbd-140">**是否希望允许用户与 SIP 联盟域联系人通信？**</span><span class="sxs-lookup"><span data-stu-id="3afbd-140">**Do you want to allow users to communicate with SIP Federated Domain contacts?**</span></span>

<span data-ttu-id="3afbd-141">配置有关在[Lync server 2013 中配置用于控制联盟用户访问的策略](lync-server-2013-configure-policies-to-control-federated-user-access.md)的设置，在 lync server [2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)，以及[在 lync SERVER 中管理组织的 SIP 联盟域 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="3afbd-141">Configure the settings as detailed in the topics [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md), and [Manage SIP federated domains for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)</span></span>

<span data-ttu-id="3afbd-142">**如果已启用与 SIP 联合域的通信，是否要启用与 XMPP 联盟合作伙伴联系人的通信？**</span><span class="sxs-lookup"><span data-stu-id="3afbd-142">**If you have enabled communication with SIP Federation Domains, do you want to enable communications with XMPP Federated Partner contacts?**</span></span>

<span data-ttu-id="3afbd-143">配置在 Lync Server 2013 中的 "[配置策略以控制 XMPP 联盟用户访问](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)" 和["在 lync Server 2013 中管理 XMPP 联盟合作伙伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)" 中详细介绍的设置。</span><span class="sxs-lookup"><span data-stu-id="3afbd-143">Configure the settings as detailed in the topic [Configure policies to control XMPP federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md) and [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md).</span></span>

<span data-ttu-id="3afbd-144">**如果已启用与 SIP 联盟域的通信，是否要启用 SIP 联合自动发现？**</span><span class="sxs-lookup"><span data-stu-id="3afbd-144">**If you have enabled communication with SIP Federated Domains, do you want to enable SIP Federation automatic discovery?**</span></span>

<span data-ttu-id="3afbd-145">配置在[Lync Server 2013 中启用或禁用联合身份验证合作伙伴的发现](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)中详细介绍的设置。</span><span class="sxs-lookup"><span data-stu-id="3afbd-145">Configure the settings as detailed in the topic [Enable or disable discovery of federation partners in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="3afbd-146">**如果你已启用与 SIP 联合域的通信，你是否希望允许将免责声明发送给联盟联系人，通知他们你使用存档，并且该通信可能已存档？**</span><span class="sxs-lookup"><span data-stu-id="3afbd-146">**If you have enabled communication with SIP Federation Domains, do you want to enable sending a disclaimer to Federated contacts notifying them that you use archiving and that communications may be archived?**</span></span>

<span data-ttu-id="3afbd-147">在[Lync Server 2013 中启用或禁用向联盟伙伴发送存档免责声明](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)的详细信息，配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="3afbd-147">Configure the settings as detailed in the topic [Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

<span data-ttu-id="3afbd-148">**是否希望允许用户与支持公共提供商（如 Windows Live Messenger、AOL 和 Yahoo\!）的通信的 SIP 联合提供商进行通信？**</span><span class="sxs-lookup"><span data-stu-id="3afbd-148">**Do you want to allow users to communicate with SIP Federated Providers that enable communication with public providers, such as Windows Live Messenger, AOL, and Yahoo\!?**</span></span>

<span data-ttu-id="3afbd-149">在 lync server [2013 中配置策略以控制公共用户访问的策略](lync-server-2013-configure-policies-to-control-public-user-access.md)，在 lync server[2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)，以及[在 lync server 2013 中创建或编辑公共 SIP 联合提供程序](lync-server-2013-create-or-edit-public-sip-federated-providers.md)，详细说明了这些设置。</span><span class="sxs-lookup"><span data-stu-id="3afbd-149">Configure the settings as detailed in the topics [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)[Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md), and [Create or edit public SIP federated providers in Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md).</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="3afbd-150">从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或续订协议。</span><span class="sxs-lookup"><span data-stu-id="3afbd-150">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="3afbd-151">具有活动许可证的客户将能够继续与 Yahoo！进行联盟</span><span class="sxs-lookup"><span data-stu-id="3afbd-151">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="3afbd-152">Messenger，直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="3afbd-152">Messenger until the service shut down date.</span></span> <span data-ttu-id="3afbd-153">AOL 和 Yahoo！的有效期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="3afbd-153">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="3afbd-154">已宣布。</span><span class="sxs-lookup"><span data-stu-id="3afbd-154">has been announced.</span></span> <span data-ttu-id="3afbd-155">有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。</span><span class="sxs-lookup"><span data-stu-id="3afbd-155">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="3afbd-156">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个每个用户每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="3afbd-156">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="3afbd-157">Messenger.</span><span class="sxs-lookup"><span data-stu-id="3afbd-157">Messenger.</span></span> <span data-ttu-id="3afbd-158">Microsoft 提供此服务的能力已作为对 Yahoo！的支持，它的底层协议被向下缠绕。</span><span class="sxs-lookup"><span data-stu-id="3afbd-158">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="3afbd-159">Lync 比以往更多，是一种强大的工具，用于跨组织和全球各地的人员进行连接。</span><span class="sxs-lookup"><span data-stu-id="3afbd-159">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="3afbd-160">与 Windows Live Messenger 的联盟不需要除 Lync 标准 CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="3afbd-160">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="3afbd-161">Skype 联盟将添加到此列表，使 Lync 用户可以通过 IM 和语音与成百上千人联系。</span><span class="sxs-lookup"><span data-stu-id="3afbd-161">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="3afbd-162">**是否希望允许用户与运行 Microsoft Office 365、Microsoft Lync Online 和 Microsoft Lync Online 2010 的托管提供商的 SIP 联合提供商通信？**</span><span class="sxs-lookup"><span data-stu-id="3afbd-162">**Do you want to allow users to communicate with SIP Federated Providers that are hosted providers running Microsoft Office 365, Microsoft Lync Online and Microsoft Lync Online 2010?**</span></span>

<span data-ttu-id="3afbd-163">按主题中的详细信息配置设置在[lync server 2013 中创建或编辑公共 SIP 联合提供程序](lync-server-2013-create-or-edit-public-sip-federated-providers.md)，在[lync server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)，以及[创建或编辑托管 SIP 联合提供商 Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)</span><span class="sxs-lookup"><span data-stu-id="3afbd-163">Configure the settings as detailed in the topics [Create or edit public SIP federated providers in Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md), [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) and [Create or edit hosted SIP federated providers Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)</span></span>

<span data-ttu-id="3afbd-164">**你的部署是在拆分（也称为混合）域中配置的，其中某些用户在内部部署中拥有主服务器，而其他用户在联机环境中配置了主服务器？**</span><span class="sxs-lookup"><span data-stu-id="3afbd-164">**Is your deployment configured in a split (also known as a hybrid) domain, where some users have their home server in an on-premise deployment, and other users are configured with a home server in an online environment?**</span></span>

<span data-ttu-id="3afbd-165">配置有关在[Lync server 2013 中配置用于控制联盟用户访问的策略](lync-server-2013-configure-policies-to-control-federated-user-access.md)的设置，在 lync server [2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)，以及[创建或编辑托管 SIP 联合提供商 Lync server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)</span><span class="sxs-lookup"><span data-stu-id="3afbd-165">Configure the settings as detailed in the topics [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) and [Create or edit hosted SIP federated providers Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)</span></span>

<span data-ttu-id="3afbd-166">如果您更喜欢列出要求的表格，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3afbd-166">If you prefer a table that lists the requirements:</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3afbd-167">联盟和外部访问（跨）联盟或外部访问类型（向下）中的选项卡</span><span class="sxs-lookup"><span data-stu-id="3afbd-167">Tab in Federation and External Access (Across) Federation or External Access Type (Down)</span></span></th>
<th><span data-ttu-id="3afbd-168">外部访问策略</span><span class="sxs-lookup"><span data-stu-id="3afbd-168">External Access Policy</span></span></th>
<th><span data-ttu-id="3afbd-169">Access Edge 配置</span><span class="sxs-lookup"><span data-stu-id="3afbd-169">Access Edge Config</span></span></th>
<th><span data-ttu-id="3afbd-170">SIP 联盟域</span><span class="sxs-lookup"><span data-stu-id="3afbd-170">SIP Federated Domains</span></span></th>
<th><span data-ttu-id="3afbd-171">SIP 联盟提供商</span><span class="sxs-lookup"><span data-stu-id="3afbd-171">SIP Federated Providers</span></span></th>
<th><span data-ttu-id="3afbd-172">XMPP 联盟合作伙伴</span><span class="sxs-lookup"><span data-stu-id="3afbd-172">XMPP Federated Partner</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3afbd-173">远程用户</span><span class="sxs-lookup"><span data-stu-id="3afbd-173">Remote Users</span></span></p></td>
<td><p><span data-ttu-id="3afbd-174"><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">在 Lync Server 2013 中配置策略以控制远程用户访问</a></span><span class="sxs-lookup"><span data-stu-id="3afbd-174"><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure policies to control remote user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3afbd-175"><a href="lync-server-2013-enable-or-disable-remote-user-access.md">在 Lync Server 2013 中启用或禁用远程用户访问</a></span><span class="sxs-lookup"><span data-stu-id="3afbd-175"><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</a></span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3afbd-176">SIP 联盟联系人</span><span class="sxs-lookup"><span data-stu-id="3afbd-176">SIP Federated Contacts</span></span></p></td>
<td><p><span data-ttu-id="3afbd-177"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中配置策略以控制联盟用户访问</a></span><span class="sxs-lookup"><span data-stu-id="3afbd-177"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3afbd-178"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></span><span class="sxs-lookup"><span data-stu-id="3afbd-178"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="3afbd-179"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">在 Lync Server 2013 中启用或禁用联盟伙伴发现</a></span><span class="sxs-lookup"><span data-stu-id="3afbd-179"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Enable or disable discovery of federation partners in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="3afbd-180"><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">在 Lync Server 2013 中启用或禁用向联盟伙伴发送存档免责声明</a></span><span class="sxs-lookup"><span data-stu-id="3afbd-180"><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3afbd-181"><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">在 Lync Server 2013 中管理组织的 SIP 联盟域</a></span><span class="sxs-lookup"><span data-stu-id="3afbd-181"><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Manage SIP federated domains for your organization in Lync Server 2013</a></span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3afbd-182">XMPP 联盟联系人</span><span class="sxs-lookup"><span data-stu-id="3afbd-182">XMPP Federated Contacts</span></span></p></td>
<td><p><span data-ttu-id="3afbd-183"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中配置策略以控制联盟用户访问</a></span><span class="sxs-lookup"><span data-stu-id="3afbd-183"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="3afbd-184"><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">在 Lync Server 2013 中配置策略以控制 XMPP 联盟用户访问</a></span><span class="sxs-lookup"><span data-stu-id="3afbd-184"><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Configure policies to control XMPP federated user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3afbd-185"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></span><span class="sxs-lookup"><span data-stu-id="3afbd-185"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="3afbd-186"><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">在 Lync Server 2013 中管理组织的 XMPP 联盟伙伴</a></span><span class="sxs-lookup"><span data-stu-id="3afbd-186"><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Manage XMPP federated partners in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3afbd-187">拆分域/混合用户</span><span class="sxs-lookup"><span data-stu-id="3afbd-187">Split Domain / Hybrid Users</span></span></p></td>
<td><p><span data-ttu-id="3afbd-188"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中配置策略以控制联盟用户访问</a></span><span class="sxs-lookup"><span data-stu-id="3afbd-188"><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3afbd-189"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></span><span class="sxs-lookup"><span data-stu-id="3afbd-189"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3afbd-190"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">在 Lync Server 2013 中创建或编辑托管的 SIP 联盟提供程序</a></span><span class="sxs-lookup"><span data-stu-id="3afbd-190"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Create or edit hosted SIP federated providers Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3afbd-191">公用 IM 服务联系人</span><span class="sxs-lookup"><span data-stu-id="3afbd-191">Public IM Service Contacts</span></span></p></td>
<td><p><span data-ttu-id="3afbd-192"><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">在 Lync Server 2013 中配置策略以控制公共用户访问</a></span><span class="sxs-lookup"><span data-stu-id="3afbd-192"><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure policies to control public user access in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3afbd-193"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></span><span class="sxs-lookup"><span data-stu-id="3afbd-193"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3afbd-194"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">在 Lync Server 2013 中创建或编辑公共 SIP 联盟提供程序</a></span><span class="sxs-lookup"><span data-stu-id="3afbd-194"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3afbd-195">对会议和会议的匿名用户访问</span><span class="sxs-lookup"><span data-stu-id="3afbd-195">Anonymous user access to meetings and conferences</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3afbd-196"><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">在 Lync Server 2013 中分配会议策略以支持匿名用户</a></span><span class="sxs-lookup"><span data-stu-id="3afbd-196"><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Assign conferencing policies to support anonymous users in Lync Server 2013</a></span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="3afbd-197">还必须考虑 "会议策略" 下的以下配置设置：<A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">在 lync server 2013 中创建或修改会议策略</A>和<A href="lync-server-2013-conferencing-policy-settings-reference.md">lync Server 2013 的会议策略设置参考</A></span><span class="sxs-lookup"><span data-stu-id="3afbd-197">You must also consider the following configuration settings under Conferencing policies: <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">Create or modify a conferencing policy in Lync Server 2013</A> and <A href="lync-server-2013-conferencing-policy-settings-reference.md">Conferencing policy settings reference for Lync Server 2013</A></span></span>


</div></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3afbd-198">你可以配置外部用户访问设置，包括你希望用于控制外部用户访问的任何策略，即使你未启用组织的外部用户访问权限也是如此。</span><span class="sxs-lookup"><span data-stu-id="3afbd-198">You can configure external user access settings, including any policies that you want to use to control external user access, even if you have not enabled external user access for your organization.</span></span> <span data-ttu-id="3afbd-199">但是，你配置的策略和其他设置仅在你为你的组织启用外部用户访问时才有效。</span><span class="sxs-lookup"><span data-stu-id="3afbd-199">However, the policies and other settings that you configure are in effect only when you have external user access enabled for your organization.</span></span> <span data-ttu-id="3afbd-200">当外部用户访问被禁用或者没有配置任何外部用户访问策略来支持它时，外部用户无法与组织用户通信。</span><span class="sxs-lookup"><span data-stu-id="3afbd-200">External users cannot communicate with users of your organization when external user access is disabled or if no external user access policies are configured to support it.</span></span>

<span data-ttu-id="3afbd-201">边缘部署对外部用户的类型进行身份验证（匿名用户除外，这些用户是通过会议 ID 进行身份验证的，而在创建会议和邀请参与者时发送给匿名参与者）和控件的密钥基于配置 edge 支持的方式进行访问。</span><span class="sxs-lookup"><span data-stu-id="3afbd-201">Your edge deployment authenticates the types of external users (except for anonymous users, who are authenticated by the conference ID and a passkey that is sent to the anonymous participant when you create the conference and invite participants) and controls access based on how you configure your edge support.</span></span> <span data-ttu-id="3afbd-202">为了控制通信，你可以配置一个或多个策略，并配置定义你的部署内部和外部的用户之间如何相互通信的设置。</span><span class="sxs-lookup"><span data-stu-id="3afbd-202">In order to control communications, you can configure one or more policies and configure settings that define how users inside and outside your deployment communicate with each other.</span></span> <span data-ttu-id="3afbd-203">除了可创建和配置以启用特定网站或用户的一种或多种类型的外部用户访问的网站和用户策略之外，策略和设置包括外部用户访问的默认全局策略。</span><span class="sxs-lookup"><span data-stu-id="3afbd-203">The policies and settings include the default global policy for external user access, in addition to site and user policies that you can create and configure to enable one or more types of external user access for specific sites or users.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3afbd-204">本节内容</span><span class="sxs-lookup"><span data-stu-id="3afbd-204">In This Section</span></span>

  - [<span data-ttu-id="3afbd-205">在 Lync Server 2013 中管理组织的外部访问策略</span><span class="sxs-lookup"><span data-stu-id="3afbd-205">Manage external access policy in Lync Server 2013</span></span>](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [<span data-ttu-id="3afbd-206">在 Lync Server 2013 中管理您的组织的访问边缘配置</span><span class="sxs-lookup"><span data-stu-id="3afbd-206">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [<span data-ttu-id="3afbd-207">在 Lync Server 2013 中管理组织的 SIP 联盟域</span><span class="sxs-lookup"><span data-stu-id="3afbd-207">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [<span data-ttu-id="3afbd-208">在 Lync Server 2013 中管理组织的 SIP 联盟提供程序</span><span class="sxs-lookup"><span data-stu-id="3afbd-208">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [<span data-ttu-id="3afbd-209">在 Lync Server 2013 中管理组织的 XMPP 联盟伙伴</span><span class="sxs-lookup"><span data-stu-id="3afbd-209">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [<span data-ttu-id="3afbd-210">在 Lync Server 2013 中为 Lync Online 客户配置联合身份验证支持</span><span class="sxs-lookup"><span data-stu-id="3afbd-210">Configuring federation support for a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

