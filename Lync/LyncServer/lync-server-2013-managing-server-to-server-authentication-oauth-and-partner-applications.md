---
title: 管理服务器到服务器的身份验证 (OAuth) 和合作伙伴应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing server-to-server authentication (OAuth) and partner applications
ms:assetid: 38848373-c8c6-4097-bf7f-699fe471348d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204817(v=OCS.15)
ms:contentKeyID: 48183894
ms.date: 05/15/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4cdfd80c368558ee034369eba0ca0cb9e89ecea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a><span data-ttu-id="9e3f0-102">在 Lync Server 2013 中管理服务器到服务器的身份验证 (OAuth) 和合作伙伴应用程序</span><span class="sxs-lookup"><span data-stu-id="9e3f0-102">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e3f0-103">_**主题上次修改时间:** 2015-05-14_</span><span class="sxs-lookup"><span data-stu-id="9e3f0-103">_**Topic Last Modified:** 2015-05-14_</span></span>

<span data-ttu-id="9e3f0-104">Microsoft Lync Server 2013 必须能够与其他应用程序和服务器产品进行安全、无缝地通信。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-104">Microsoft Lync Server 2013 must be able to securely, and seamlessly, communicate with other applications and server products.</span></span> <span data-ttu-id="9e3f0-105">例如, 你可以配置 Lync Server 2013, 以便将联系人数据和/或存档数据存储在 Microsoft Exchange Server 2013 中;但是, 只有当 Lync Server 和 Exchange 能够相互安全地相互通信时才能执行此操作。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-105">For example, you can configure Lync Server 2013 so that contact data and/or archiving data is stored in Microsoft Exchange Server 2013; however, this can only be done if Lync Server and Exchange are able to securely communicate with one another.</span></span> <span data-ttu-id="9e3f0-106">同样, 您可以从 Microsoft SharePoint Server 中安排 Lync 服务器会议;但是, 如果两个服务器 (SharePoint 和 Lync Server) 相互信任, 则只能执行此操作。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-106">Likewise, you can schedule a Lync Server conference from within Microsoft SharePoint Server; again, however, this can only be done if the two servers (SharePoint and Lync Server) trust one another.</span></span> <span data-ttu-id="9e3f0-107">尽管可以使用一种身份验证机制进行 Lync 到 Exchange 通信以及用于 Lync 到 SharePoint 通信的单独机制, 但更好且更高效的方法是对所有服务器到服务器使用标准化的方法身份验证和授权。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-107">Although it's possible to use one authentication mechanism for Lync-to-Exchange communication and a separate mechanism for Lync-to-SharePoint communication, a better and more efficient approach is to use a standardized method for all server-to-server authentication and authorization.</span></span>

<span data-ttu-id="9e3f0-108">使用单个标准化的服务器到服务器身份验证方法是 Lync Server 2013 采用的方法。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-108">Using a single, standardized method for server-to-server authentication is the approach taken by Lync Server 2013.</span></span> <span data-ttu-id="9e3f0-109">对于2013版本, Lync Server 2013 (以及其他 Microsoft Server 产品, 包括 Exchange 2013 和 Microsoft SharePoint Server) 支持用于服务器到服务器身份验证和授权的 OAuth (开放授权) 协议。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-109">For the 2013 release, Lync Server 2013 (as well as other Microsoft Server products, including Exchange 2013 and Microsoft SharePoint Server) support the OAuth (Open Authorization) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="9e3f0-110">使用 OAuth (由许多主要网站使用的标准授权协议), 用户凭据和密码不会从一台计算机传递到另一台计算机。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-110">With OAuth, a standard authorization protocol used by a number of major websites, user credentials and passwords are not passed from one computer to another.</span></span> <span data-ttu-id="9e3f0-111">但是，身份验证和授权是基于安全令牌的交换；这些令牌会将访问权限授予特定时间量的一组特定资源。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-111">Instead, authentication and authorization is based on the exchange of security tokens; these tokens grant access to a specific set of resources for a specific amount of time.</span></span>

<span data-ttu-id="9e3f0-112">OAuth 身份验证通常涉及到三方：一台授权服务器和两个需要相互通信的领域。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-112">OAuth authentication typically involves three parties: a single authorization server and the two realms that need to communicate with one another.</span></span> <span data-ttu-id="9e3f0-113">(您也可以不使用授权服务器执行服务器到服务器的身份验证, 此过程将在本文档后面部分讨论。)安全令牌由授权服务器 (也称为安全令牌服务器) 颁发给需要通信的两个领域;这些令牌验证来自一个领域的通信是否应由其他领域信任。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-113">(You can also do server-to-server authentication without using an authorization server, a process that will be discussed later in this document.) Security tokens are issued by the authorization server (also known as a security token server) to the two realms that need to communicate; these tokens verify that communications originating from one realm should be trusted by the other realm.</span></span> <span data-ttu-id="9e3f0-114">例如, 授权服务器可能会颁发令牌以验证特定 Lync Server 2013 领域中的用户是否能够访问指定的 Exchange 2013 领域, 反之亦然。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-114">For example, the authorization server might issue tokens that verify that users from a specific Lync Server 2013 realm are able to access a specified Exchange 2013 realm, and vice-versa.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="9e3f0-115">领域只是一个安全容器。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-115">A realm is simply a security container.</span></span> <span data-ttu-id="9e3f0-116">默认情况下, Lync Server 2013 使用默认 SIP 域作为其 OAuth 领域。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-116">By default, Lync Server 2013 uses your default SIP domain as its OAuth realm.</span></span> <span data-ttu-id="9e3f0-117">其他 SIP 命名空间添加到 OAuth 证书中的“使用者替代名称”列表。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-117">Additional SIP namespaces are added to the Subject Alternate Name list in the OAuth certificate.</span></span>



</div>

<span data-ttu-id="9e3f0-118">Lync Server 2013 支持三种服务器到服务器身份验证方案。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-118">Lync Server 2013 supports three server-to-server authentication scenarios.</span></span> <span data-ttu-id="9e3f0-119">有了 Lync Server 2013, 您可以:</span><span class="sxs-lookup"><span data-stu-id="9e3f0-119">With Lync Server 2013 you can:</span></span>

  - <span data-ttu-id="9e3f0-120">在 Lync Server 2013 的本地安装和 Exchange 2013 和/或 Microsoft SharePoint Server 的本地安装之间配置服务器到服务器的身份验证。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-120">Configure server-to-server authentication between an on-premise installation of Lync Server 2013 and an on-premises installation of Exchange 2013 and/or Microsoft SharePoint Server.</span></span>

  - <span data-ttu-id="9e3f0-121">在一对 Office 365 组件 (例如, 在 Microsoft Exchange 和 Microsoft Lync Server 之间或 Microsoft Lync Server 和 Microsoft SharePoint 之间) 配置服务器到服务器的身份验证。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-121">Configure server-to-server authentication between a pair of Office 365 components (for example, between Microsoft Exchange and Microsoft Lync Server, or between Microsoft Lync Server and Microsoft SharePoint).</span></span>

  - <span data-ttu-id="9e3f0-122">在跨平台环境中配置服务器到服务器身份验证 (即本地服务器与 Office 365 组件之间的服务器到服务器身份验证)。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-122">Configure server-to-server authentication in a cross-premises environment (that is, server-to-server authentication between an on-premises server and an Office 365 component).</span></span>

<span data-ttu-id="9e3f0-123">请注意, 在此时间点, 仅限 Exchange 2013、SharePoint Server 和 Lync Server 2013 支持服务器到服务器身份验证;如果您没有运行这些服务器之一, 则您将无法完全实现 OAuth 身份验证。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-123">Note that, at this point in time, only Exchange 2013, SharePoint Server, and Lync Server 2013 support server-to-server authentication; if you are not running one of these servers then you will not be able to fully implement OAuth authentication.</span></span>

<span data-ttu-id="9e3f0-124">还应指出不需要使用服务器到服务器身份验证: 不需要使用服务器到服务器身份验证, 即可部署 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-124">It should also be pointed out that you do not need to use server-to-server authentication: server-to-server authentication is not required in order to deploy Lync Server 2013.</span></span> <span data-ttu-id="9e3f0-125">如果 Lync Server 2013 不需要与其他服务器 (如 Exchange 2013) 通信, 则不需要服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-125">If Lync Server 2013 does not need to communicate with other servers (such as Exchange 2013) then server-to-server authentication is not needed.</span></span>

<span data-ttu-id="9e3f0-126">但是, 如果你希望使用 Lync 服务器的某些新功能 (如 "统一联系人存储"), 则需要服务器到服务器的身份验证。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-126">However, server-to-server authentication is required if you want to use some of Lync Server's new features, such as the "unified contact store."</span></span> <span data-ttu-id="9e3f0-127">通过 "统一联系人存储", Lync Server 2013 联系人信息存储在 Exchange 2013 中, 而不是在 Lync Server 中。这使用户可以在 Lync、Microsoft Outlook 或 Microsoft Outlook Web Access 中轻松访问单个联系人集。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-127">With unified contact store, Lync Server 2013 contact information is stored in Exchange 2013 instead of in Lync Server; this enables users to have a single set of contacts that is readily accessible from within Lync, Microsoft Outlook, or Microsoft Outlook Web Access.</span></span> <span data-ttu-id="9e3f0-128">由于 "统一联系人存储" 要求 Lync Server 2013 与 Exchange 2013 共享信息, 因此必须使用服务器到服务器身份验证才能部署该功能。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-128">Because the unified contact store requires Lync Server 2013 to share information with Exchange 2013, you must use server-to-server authentication in order to deploy the feature.</span></span> <span data-ttu-id="9e3f0-129">如果你选择使用 Exchange 存档 (在其中将即时消息会话的脚本另存为 Exchange 2013 电子邮件, 而不是单个数据库记录), 也需要服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-129">Server-to-server authentication is also required if you choose to use Exchange archiving, in which the transcripts of instant messaging sessions are saved as Exchange 2013 emails rather than as individual database records.</span></span>

<span data-ttu-id="9e3f0-130">为了使 Office 365 版本的 Lync Server 与 Exchange 对应的版本通信, Lync Server 2013 必须首先从授权服务器获取一个安全令牌。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-130">For the Office 365 version of Lync Server to communicate with its Exchange counterpart, Lync Server 2013 must first obtain a security token from the authorization server.</span></span> <span data-ttu-id="9e3f0-131">然后, Lync 服务器使用该安全令牌向 Exchange 标识自身。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-131">Lync Server then uses that security token to identify itself to Exchange.</span></span> <span data-ttu-id="9e3f0-132">Office 365 版本的 Exchange 必须经过同一进程才能与 Lync Server 2013 通信。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-132">The Office 365 version of Exchange must go through the same process in order to communicate with Lync Server 2013.</span></span>

<span data-ttu-id="9e3f0-133">但是，对于两台 Microsoft 服务器之间的本地服务器到服务器身份验证，不需要使用第三方令牌服务器。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-133">However, for on-premises server-to-server authentication between two Microsoft servers there is no need to use a third-party token server.</span></span> <span data-ttu-id="9e3f0-134">服务器产品 (如 Lync Server 2013 和 Exchange 2013) 具有内置的令牌服务器, 可用于支持服务器到服务器身份验证的其他 Microsoft 服务器 (如 SharePoint Server) 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-134">Server products such as Lync Server 2013 and Exchange 2013 have a built-in token server that can be used for authentication purposes with other Microsoft servers (such as SharePoint server) that support server-to-server authentication.</span></span> <span data-ttu-id="9e3f0-135">例如, Lync Server 2013 可以自行发出和签名安全令牌, 然后使用该令牌与 Exchange 2013 通信。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-135">For example, Lync Server 2013 can issue and sign a security token by itself, then use that token to communicate with Exchange 2013.</span></span> <span data-ttu-id="9e3f0-136">在此类情况下，不需要第三方令牌服务器。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-136">In a case like this, there is no need for a third-party token server.</span></span>

<span data-ttu-id="9e3f0-137">为了为 Lync Server 2013 的本地实现配置服务器到服务器身份验证, 您必须执行两项操作:</span><span class="sxs-lookup"><span data-stu-id="9e3f0-137">In order to configure server-to-server authentication for an on-premises implementation of Lync Server 2013 you must do two things:</span></span>

  - <span data-ttu-id="9e3f0-138">为 Lync Server 的内置令牌颁发者分配证书。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-138">Assign a certificate to Lync Server's built-in token issuer.</span></span>

  - <span data-ttu-id="9e3f0-139">将 Lync Server 2013 将与之通信的服务器配置为 "合作伙伴应用程序"。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-139">Configure the server that Lync Server 2013 will communicate with to be a "partner application."</span></span> <span data-ttu-id="9e3f0-140">例如, 如果 Lync Server 2013 需要与 Exchange 2013 通信, 则需要将 Exchange 配置为合作伙伴应用程序。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-140">For example, if Lync Server 2013 needs to communicate with Exchange 2013 then you will need to configure Exchange to be a partner application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="9e3f0-141">"合作伙伴应用程序" 是 Lync Server 2013 可以直接与之交换安全令牌的任何应用程序, 而无需使用第三方安全令牌服务器。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-141">A "partner application" is any application that Lync Server 2013 can directly exchange security tokens with, without having to go through a third-party security token server.</span></span>



</div>

<span data-ttu-id="9e3f0-142">请注意，OAuth 是产品的核心部分，不可禁用或删除。</span><span class="sxs-lookup"><span data-stu-id="9e3f0-142">Note that OAuth is a core part of the product and cannot be disabled or removed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="9e3f0-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e3f0-143">See Also</span></span>


[<span data-ttu-id="9e3f0-144">将服务器到服务器身份验证证书分配给 Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e3f0-144">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[<span data-ttu-id="9e3f0-145">在跨平台环境中配置 Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e3f0-145">Configuring Microsoft Lync Server 2013 in a cross-premises environment</span></span>](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

