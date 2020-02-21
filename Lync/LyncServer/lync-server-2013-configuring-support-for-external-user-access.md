---
title: Lync Server 2013：配置对外部用户访问的支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for external user access
ms:assetid: f8424f8c-f965-4414-8485-30f07e10214a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413051(v=OCS.15)
ms:contentKeyID: 48185874
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94250ec0fbae3a7077e545eebdc848db3c370d19
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190895"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="0d4d0-102">在 Lync Server 2013 中配置对外部用户访问的支持</span><span class="sxs-lookup"><span data-stu-id="0d4d0-102">Configuring support for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d4d0-103">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="0d4d0-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="0d4d0-104">部署边缘服务器或边缘池是支持外部用户的第一步。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-104">Deploying an Edge Server or Edge pool is the first step to supporting external users.</span></span> <span data-ttu-id="0d4d0-105">有关部署边缘服务器的详细信息，请参阅部署文档中的在[Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-105">For details about deploying Edge Servers, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="0d4d0-106">对策略配置的重要注意事项是了解策略的优先级及如何应用策略。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-106">An important consideration for the configuration of policies is to understand the precedence of policies and how the policies are applied.</span></span> <span data-ttu-id="0d4d0-107">在一个策略级别应用的 Lync Server 策略设置可以覆盖在另一个策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-107">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="0d4d0-108">Lync Server 策略优先级为：用户策略（最具影响力）替代网站策略，然后网站策略将覆盖全局策略（最不影响）。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-108">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="0d4d0-109">这意味着，策略设置越接近策略所影响的对象，它对对象的影响越大。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="0d4d0-110">边缘服务器或边缘池设置完成后，必须启用要提供的外部用户访问类型并配置对外部访问的支持。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-110">After completing the setup of an Edge Server or Edge pool, you must enable the types of external user access that you want to provide, and configure the settings for the external access.</span></span> <span data-ttu-id="0d4d0-111">在 Lync Server 2013 中，你可以根据任务要求，使用 Lync Server 控制面板、Lync Server Management Shell 或两者来启用和配置外部用户访问和策略。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-111">In Lync Server 2013, you enable and configure external user access and policies using the Lync Server Control Panel, the Lync Server Management Shell or both, based on the task requirements.</span></span>

<span data-ttu-id="0d4d0-112">要支持外部用户访问，必须执行以下两项操作：</span><span class="sxs-lookup"><span data-stu-id="0d4d0-112">To support external user access, you must do both of the following:</span></span>

  - <span data-ttu-id="0d4d0-113">**启用对组织**   的支持若要在部署中启用对外部用户访问的支持，您可以启用要支持的每种类型的外部访问。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-113">**Enable support for your organization**   To enable support for external user access in your deployment, you enable each type of external access that you want to support.</span></span> <span data-ttu-id="0d4d0-114">通过在 Lync Server 控制面板的 "**联盟和外部访问**" 组中或通过使用 Lync Server 命令行管理程序和关联的 cmdlet，在 "**外部访问策略**" 页上编辑全局设置或创建和配置站点或用户策略，可启用和禁用对外部用户访问的支持。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-114">You enable and disable support for external user access by editing the global settings or creating and configuring a site or user policy on the **External Access Policy** page in the **Federation and External Access** group of the Lync Server Control Panel or by using the Lync Server Management Shell and associated cmdlets.</span></span> <span data-ttu-id="0d4d0-115">在[Lync Server 2013 中的主题联盟和外部访问 cmdlet](https://docs.microsoft.com/powershell/module/skype/)中，可以找到用于管理**外部访问策略**的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-115">Cmdlets for managing the **External Access Policy** are found in the topic [Federation and external access cmdlets in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/).</span></span> <span data-ttu-id="0d4d0-116">启用对外部访问的支持指定运行 Lync Server 访问边缘服务的服务器支持与外部用户和服务器的通信。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-116">Enabling support for external access specifies that your servers running the Lync Server Access Edge service support communications with external users and servers.</span></span> <span data-ttu-id="0d4d0-117">外部用户访问被禁用，或者策略尚未配置为支持策略时，内部和外部用户无法进行通信。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-117">Internal and external users cannot communicate while external user access is disabled or if policies have not yet been configured to support it.</span></span>

  - <span data-ttu-id="0d4d0-118">**配置和分配一个或多个策略**   以支持外部用户访问，请配置策略以满足包括以下各项的要求：</span><span class="sxs-lookup"><span data-stu-id="0d4d0-118">**Configure and assign one or more policies**   To support external user access, you configure policies to address requirements that include:</span></span>
    
      - <span data-ttu-id="0d4d0-119">\*\*\*\*   使用站点或用户作用域创建的外部访问策略（默认情况下存在全局策略，并且没有已启用的设置）。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-119">**External access policies**   Created with either a site or user scope (a global policy exists by default and has no enabled settings).</span></span> <span data-ttu-id="0d4d0-120">您可以创建和配置策略以控制使用一种或多种类型的外部用户访问，包括联合用户访问（包括（如果已选中，联合 XMPP 域）远程用户用户访问和受支持的公共 IM 服务提供商。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-120">You create and configure policies to control the use of one or more types of external user access, including, federated user access (including, if selected, federated XMPP domains)remote users user access, and supported public IM service providers.</span></span> <span data-ttu-id="0d4d0-121">在**联盟和外部访问**组中的 "**外部访问策略**" 页上，使用全局策略或一个或多个以管理方式创建的网站和用户策略，在 Lync Server 控制面板中配置外部策略。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-121">You configure external policies in Lync Server Control Panel using the global policy or one or more administratively created site and user policies, on the **External Access Policy** page in the **Federation and External Access** group.</span></span> <span data-ttu-id="0d4d0-122">无法删除全局策略。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-122">The global policy cannot be deleted.</span></span> <span data-ttu-id="0d4d0-123">您可以创建和配置任何要用于限制特定网站或用户的外部用户访问的网站和用户策略。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-123">You create and configure any site and user policies that you want to use to limit external user access for specific sites or users.</span></span> <span data-ttu-id="0d4d0-124">自动分配全局和站点策略。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-124">Global and site policies are automatically assigned.</span></span> <span data-ttu-id="0d4d0-125">如果创建并配置了用户策略，则必须使用 "**用户**" 页上的 "Lync Server 控制面板" 中的 "用户配置" 页将其分配给特定用户。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-125">If you create and configure a user policy, you must then assign it to the specific users by using the user configuration page in the Lync Server Control Panel on the **Users** page.</span></span> <span data-ttu-id="0d4d0-126">查找要应用此策略的一个或一用户，并分配该策略。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-126">Find the user or users that you want this policy to apply to and assign the policy.</span></span> <span data-ttu-id="0d4d0-127">要对其应用的用户。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-127">to whom you want it to apply.</span></span> <span data-ttu-id="0d4d0-128">若要将已配置的用户策略分配给用户，请参阅[在 Lync Server 2013 中向启用 Lync 的用户分配外部用户访问策略](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-128">To assign a configured user policy to a user, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span></span> <span data-ttu-id="0d4d0-129">每个外部用户访问策略都可以支持以下一个或多个操作：远程用户访问、SIP 联合用户访问、XMPP 联盟用户访问和公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-129">Each external user access policy can support one or more of the following: remote user access, SIP federated user access, XMPP federated user access and public IM connectivity.</span></span>
    
      - <span data-ttu-id="0d4d0-130">**会议策略**   您创建并配置策略以控制组织中的会议，包括组织中的哪些用户可以向匿名用户邀请他们托管的会议。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-130">**Conferencing policies**   You create and configure policies to control conferencing in your organization, including which users in your organization can invite anonymous users to conferences that they host.</span></span> <span data-ttu-id="0d4d0-131">在 Lync Server 控制面板 **会议**页面上，是全局、站点和用户作用域的策略设置，用于控制实际会议的设置。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-131">On the Lync Server Control Panel **Conferencing** page are policy settings at the global, site and user scope that control settings for the actual conferences.</span></span> <span data-ttu-id="0d4d0-132">有关详细信息，请参阅[在 Lync Server 2013 中管理会议和会议](lync-server-2013-managing-meetings-and-conferences.md)。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-132">For details, see [Managing meetings and conferences in Lync Server 2013](lync-server-2013-managing-meetings-and-conferences.md).</span></span> <span data-ttu-id="0d4d0-133">您可启用参加会议的匿名用户及“访问边缘配置”\*\*\*\* 页面上的远程用户和联盟用户。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-133">You enable anonymous users for conferencing, remote users and federated users on the **Access Edge Configuration** page.</span></span> <span data-ttu-id="0d4d0-134">“访问边缘配置\*\*\*\* 上的策略是作用域中的全局策略。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-134">The policy on the **Access Edge Configuration** is global in scope.</span></span> <span data-ttu-id="0d4d0-135">没有可用于定义站点或用户策略的选项。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-135">There are no options to define a site or user policy.</span></span> <span data-ttu-id="0d4d0-136">通过使用全局、站点或用户策略设置在“外部访问策略”\*\*\*\* 页面上控制作用域。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-136">The scope is controlled on the **External Access Policy** page through the use of global, site, or user policy settings.</span></span>
        
        <span data-ttu-id="0d4d0-p106">例如，如果您想允许用户借助远程用户创建、邀请和管理会议，则必须在“外部访问策略”\*\*\*\* 全局、站点或用户策略上设置“启用与远程用户的通信”\*\*\*\* 及在“访问边缘配置”\*\*\*\* 页面上设置“启用与远程用户的通信”\*\*\*\*。同样，要允许与有定义关系的匿名用户或联盟合作伙伴开展会议（如，配置的联盟 SIP 域和提供商 – XMPP 联盟不支持会议），则要在“外部访问策略”\*\*\*\* 全局、站点或用户策略中设置“启用与公共用户的通信”\*\*\*\* 和“启用与联盟用户的通信”\*\*\*\*。然后在“访问边缘配置”\*\*\*\* 页面上选择赠送全局策略设置“允许匿名用户访问会议”\*\*\*\* 和“启用联盟和公共 IM 连接”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-p106">For example, if you want to allow users to create, invite and manage conferencing with remote users, you must set **Enable communications with remote users** on the **External Access Policy** global, site or user policy, and **Enable Communications with remote users** on the **Access Edge Configuration** page. Similarly, to allow conferencing with anonymous users or federated partners that you have a defined relationship with (such as configured federated SIP domains and providers – XMPP federation does not support conferencing), you set **Enable communications with public users** and **Enable communications with federated users** in the **External Access Policy** global, site or user policy. You then select complimentary global policy settings **Enable anonymous user access to conferences** and **Enable federated and public IM connectivity** on the **Access Edge Configuration** page.</span></span>

<span data-ttu-id="0d4d0-p107">即使没有为组织启用外部用户访问，也可以配置外部用户访问设置，包括要用于控制外部用户访问的任何策略。但是，只有为组织启用外部用户访问之后，配置的策略和其他设置才会生效。如果禁用外部用户访问或没有配置支持此功能的外部用户访问策略，外部用户将无法与组织的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-p107">You can configure external user access settings, including any policies that you want to use to control external user access, even if you have not enabled external user access for your organization. However, the policies and other settings that you configure are in effect only when you have external user access enabled for your organization. External users cannot communicate with users of your organization when external user access is disabled or if no external user access policies are configured to support it.</span></span>

<span data-ttu-id="0d4d0-p108">边缘部署会根据边缘支持的配置方式来对外部用户（匿名用户除外，他们通过会议 ID 和密钥（当您创建会议和邀请参与者时发送给匿名参与者）进行身份验证）类型进行身份验证并控制访问。为了控制通信，可以配置一个或多个策略并配置设置以定义部署内外的用户如何相互通信。除了可以创建和配置为特定站点或用户启用一种或多种类型外部用户访问的站点和用户策略之外，这些策略和设置还包括默认的外部用户访问全局策略。</span><span class="sxs-lookup"><span data-stu-id="0d4d0-p108">Your edge deployment authenticates the types of external users (except for anonymous users, who are authenticated by the conference ID and a passkey that is sent to the anonymous participant when you create the conference and invite participants) and controls access based on how you configure your edge support. In order to control communications, you can configure one or more policies and configure settings that define how users inside and outside your deployment communicate with each other. The policies and settings include the default global policy for external user access, in addition to site and user policies that you can create and configure to enable one or more types of external user access for specific sites or users.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0d4d0-146">本部分内容</span><span class="sxs-lookup"><span data-stu-id="0d4d0-146">In This Section</span></span>

  - [<span data-ttu-id="0d4d0-147">在 Lync Server 2013 中配置策略以控制远程用户访问</span><span class="sxs-lookup"><span data-stu-id="0d4d0-147">Configure policies to control remote user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [<span data-ttu-id="0d4d0-148">在 Lync Server 2013 中启用或禁用远程用户访问</span><span class="sxs-lookup"><span data-stu-id="0d4d0-148">Enable or disable remote user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [<span data-ttu-id="0d4d0-149">在 Lync Server 2013 中启用或禁用匿名用户访问</span><span class="sxs-lookup"><span data-stu-id="0d4d0-149">Enable or disable anonymous user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [<span data-ttu-id="0d4d0-150">在 Lync Server 2013 中分配会议策略以支持匿名用户</span><span class="sxs-lookup"><span data-stu-id="0d4d0-150">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

