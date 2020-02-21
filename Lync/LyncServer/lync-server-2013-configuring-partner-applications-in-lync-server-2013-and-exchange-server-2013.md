---
title: 在 Lync Server 2013 和 Exchange Server 2013 中配置合作伙伴应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db2f0df542cb85956ae3efa7321083b99ed561a8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="da024-102">在 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 中配置合作伙伴应用程序</span><span class="sxs-lookup"><span data-stu-id="da024-102">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da024-103">_**上次修改的主题：** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="da024-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="da024-p101">服务器到服务器身份验证通常涉及三个实体：两台需要相互通信的服务器以及一台第三方安全令牌服务器。如果两台服务器（例如，服务器 A 和服务器 B）需要通信，则这两台服务器一般通过联系令牌服务器并获取相互信任的安全令牌来启动。之后服务器 A 会向服务器 B 提供安全令牌（反之亦然）作为保证真实性和可信度的方式。</span><span class="sxs-lookup"><span data-stu-id="da024-p101">Server-to-server authentication typically involves three entities: the two servers that need to communicate with one another, and a third-party security token server. If two servers (for example, Server A and Server B) need to communicate, then both of those servers typically start by contacting a token server and obtain a mutually-trusted security token. Server A then present that security token to Server B (and vice-versa) as a way to guarantee both its authenticity and its trustworthiness.</span></span>

<span data-ttu-id="da024-107">但是，这是一般规则。</span><span class="sxs-lookup"><span data-stu-id="da024-107">However, that's a general rule.</span></span> <span data-ttu-id="da024-108">Lync Server 2013、Microsoft Exchange Server 2013 和 Microsoft SharePoint Server 2013 在彼此通信时不需要使用第三方令牌服务器;这是因为这些服务器产品可以创建可以接受的安全令牌，而无需单独的令牌服务器。</span><span class="sxs-lookup"><span data-stu-id="da024-108">Lync Server 2013, Microsoft Exchange Server 2013, and Microsoft SharePoint Server 2013 do not need to use a third-party token server when communicating with one another; that's because these server products can create security tokens that can be accepted by one another without the need for a separate token server.</span></span> <span data-ttu-id="da024-109">（此功能仅在 Lync Server 2013、Exchange 2013 和 SharePoint Server 2013 中可用。</span><span class="sxs-lookup"><span data-stu-id="da024-109">(This capability is only available in Lync Server 2013, Exchange 2013, and SharePoint Server 2013.</span></span> <span data-ttu-id="da024-110">如果需要设置与其他服务器（包括其他 Microsoft 服务器产品）的服务器到服务器身份验证，则需要使用第三方令牌服务器执行此操作。</span><span class="sxs-lookup"><span data-stu-id="da024-110">If you need to set up server-to-server authentication with other servers, including other Microsoft server products, then you will need to do so by using a third-party token server.)</span></span>

<span data-ttu-id="da024-111">若要在 Lync Server 和 Exchange 之间设置服务器到服务器身份验证，您必须执行以下两项操作：1）您必须为每台服务器分配适当的证书;和2），您必须将每台服务器配置为另一台服务器的合作伙伴应用程序：这意味着，您必须将 Lync Server 2013 配置为 Exchange 2013 的合作伙伴应用程序，并且必须将 Exchange 2013 配置为 Lync Server 2013 的合作伙伴应用程序。</span><span class="sxs-lookup"><span data-stu-id="da024-111">In order to set up server-to-server authentication between Lync Server and Exchange you must do two things: 1) you must assign the appropriate certificates to each server; and, 2) you must configure each server to be a partner application of the other server: that means you must configure Lync Server 2013 to be a partner application for Exchange 2013, and you must configure Exchange 2013 to be a partner application for Lync Server 2013.</span></span>

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a><span data-ttu-id="da024-112">将 Lync Server 2013 配置为 Exchange 2013 的合作伙伴应用程序</span><span class="sxs-lookup"><span data-stu-id="da024-112">Configuring Lync Server 2013 to be a Partner Application for Exchange 2013</span></span>

<span data-ttu-id="da024-113">将 Lync Server 2013 配置为具有 Exchange 2013 的合作伙伴应用程序的最简单方法是运行 Configure-enterprisepartnerapplication.ps1 脚本，该脚本是 Exchange 2013 附带的 Windows PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="da024-113">The easiest way to configure Lync Server 2013 to be a partner application with Exchange 2013 is to run the Configure-EnterprisePartnerApplication.ps1 script, a Windows PowerShell script that ships with Exchange 2013.</span></span> <span data-ttu-id="da024-114">若要运行此脚本，您必须提供 Lync Server 身份验证元数据文档的 URL;这通常是 Lync Server 2013 池的完全限定的域名，后跟后缀/metadata/json/1。</span><span class="sxs-lookup"><span data-stu-id="da024-114">To run this script, you must provide the URL for the Lync Server authentication metadata document; this will typically be the fully qualified domain name of the Lync Server 2013 pool followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="da024-115">例如：</span><span class="sxs-lookup"><span data-stu-id="da024-115">For example:</span></span>

    https://atl-cs-001.litwareinc.com/metadata/json/1

<span data-ttu-id="da024-116">若要将 Lync Server 配置为合作伙伴应用程序，请打开 Exchange 命令行管理程序，并运行与此类似的命令（假设 Exchange 已安装在驱动器 C：上，并且它使用默认文件夹路径）：</span><span class="sxs-lookup"><span data-stu-id="da024-116">To configure Lync Server as a partner application, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

<span data-ttu-id="da024-117">配置合作伙伴应用程序后，建议您在 Exchange 邮箱和客户端访问服务器上停止并重新启动 Internet Information Services （IIS）。</span><span class="sxs-lookup"><span data-stu-id="da024-117">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="da024-118">您可使用类似于以下命令的命令重新启动 IIS，以下命令将重新启动计算机 atl-exchange-001 上的此服务：</span><span class="sxs-lookup"><span data-stu-id="da024-118">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="da024-119">可以在 Exchange 命令行管理程序或任何其他命令窗口中从管理员权限下运行此命令。</span><span class="sxs-lookup"><span data-stu-id="da024-119">This command can be run from within the Exchange Management Shell or from any other command window run under administrator privileges.</span></span>

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a><span data-ttu-id="da024-120">将 Exchange 2013 配置为 Lync Server 2013 的合作伙伴应用程序</span><span class="sxs-lookup"><span data-stu-id="da024-120">Configuring Exchange 2013 to be a Partner Application for Lync Server 2013</span></span>

<span data-ttu-id="da024-121">将 Lync Server 2013 配置为 Exchange 2013 的合作伙伴应用程序后，必须将 Exchange 配置为 Lync Server 的合作伙伴应用程序。</span><span class="sxs-lookup"><span data-stu-id="da024-121">After you have configured Lync Server 2013 to be a partner application for Exchange 2013, you must then configure Exchange to be a partner application for Lync Server.</span></span> <span data-ttu-id="da024-122">这可以通过使用 Lync Server 命令行管理程序并为 Exchange 指定身份验证元数据文档来实现;这通常是 Exchange 自动发现服务的 URI，后跟后缀/metadata/json/1。</span><span class="sxs-lookup"><span data-stu-id="da024-122">This can be done by using the Lync Server Management Shell and specifying the authentication metadata document for Exchange; this will typically be the URI of the Exchange autodiscover service followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="da024-123">例如：</span><span class="sxs-lookup"><span data-stu-id="da024-123">For example:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

<span data-ttu-id="da024-124">在 Lync Server 中，通过使用[CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) cmdlet 配置合作伙伴应用程序。</span><span class="sxs-lookup"><span data-stu-id="da024-124">In Lync Server, partner applications are configured by using the [New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="da024-125">除了指定元数据 URI 之外，还应将应用程序信任级别设置为 "完全";这将允许 Exchange 代表其自身和领域中的任何授权用户。</span><span class="sxs-lookup"><span data-stu-id="da024-125">In addition to specifying the metadata URI you should also set the application trust level to Full; this will allow Exchange to represent both itself and any authorized user in the realm.</span></span> <span data-ttu-id="da024-126">例如：</span><span class="sxs-lookup"><span data-stu-id="da024-126">For example:</span></span>

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

<span data-ttu-id="da024-127">或者，您可以通过复制和修改在 Lync Server 2013 服务器到服务器身份验证文档中找到的脚本代码来创建合作伙伴应用程序。</span><span class="sxs-lookup"><span data-stu-id="da024-127">Alternatively, you can create a partner application by copying and modifying the script code found in the Lync Server 2013 server-to-server authentication documentation.</span></span> <span data-ttu-id="da024-128">有关详细信息，请参阅[管理 Lync server 2013 中的服务器到服务器身份验证（OAuth）和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)一文。</span><span class="sxs-lookup"><span data-stu-id="da024-128">See the article [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) for more information.</span></span>

<span data-ttu-id="da024-129">如果你已为 Lync Server 和 Exchange 成功配置了合作伙伴应用程序，这意味着你还在两个产品之间成功配置了服务器到服务器的身份验证。</span><span class="sxs-lookup"><span data-stu-id="da024-129">If you have successfully configured partner applications for both Lync Server and Exchange that means that you have also successfully configured server-to-server authentication between the two products.</span></span> <span data-ttu-id="da024-130">Lync Server 2013 包括一个 Windows PowerShell cmdlet [CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15))，可让你验证是否已正确配置服务器到服务器身份验证，以及 Lync Server Storage Service 是否可以连接到 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="da024-130">Lync Server 2013 includes a Windows PowerShell cmdlet, [Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15)), that enables you to verify that server-to-server authentication has been correctly configured and that the Lync Server Storage Service can connect to Exchange 2013.</span></span> <span data-ttu-id="da024-131">通过连接到 Exchange 2013 用户的邮箱，向该用户的对话历史记录文件夹中写入一个项目，然后删除该项目（可选），cmdlet 可执行此项。</span><span class="sxs-lookup"><span data-stu-id="da024-131">The cmdlet does this by connecting to the mailbox of an Exchange 2013 user, writing an item into the Conversation History folder for that user, and then, optionally, deleting that item.</span></span>

<span data-ttu-id="da024-132">若要测试 Lync Server 2013 和 Exchange 2013 的集成，请在 Lync Server 命令行管理程序中运行与以下内容类似的命令：</span><span class="sxs-lookup"><span data-stu-id="da024-132">To test the integration of Lync Server 2013 and Exchange 2013, run a command similar to this from within the Lync Server Management Shell:</span></span>

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="da024-133">在上面的命令中，SipUri 表示在 Exchange 2013 上具有帐户的用户的 SIP 地址;在这不是一个有效的用户帐户时，您的命令将失败。</span><span class="sxs-lookup"><span data-stu-id="da024-133">In the preceding command, the SipUri represents the SIP address of a user with an account on Exchange 2013; your command will fail in this is not a valid user account.</span></span>

<span data-ttu-id="da024-134">如果测试成功并且建立了连接，则您可继续配置存档集成和统一的联系人存储等可选功能。</span><span class="sxs-lookup"><span data-stu-id="da024-134">If the test succeeds and connectivity has been established, you can then proceed to configure optional features such as archiving integration and the unified contact store.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

