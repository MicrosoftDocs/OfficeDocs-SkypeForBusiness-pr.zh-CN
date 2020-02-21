---
title: Lync Server 2013：与 Exchange Server 2013 集成的先决条件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49733853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3ea70be8c4d431b6231b1cf8e8dc252581643b6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="3c9aa-102">集成 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 的先决条件</span><span class="sxs-lookup"><span data-stu-id="3c9aa-102">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c9aa-103">_**上次修改的主题：** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="3c9aa-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="3c9aa-104">在集成 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 之前，必须确保所有先决条件步骤都已完成。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-104">Before you can integrate Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 you must ensure that all the prerequisite steps have been completed.</span></span> <span data-ttu-id="3c9aa-105">正如您所料，在 Exchange 2013 和 Lync Server 2013 完全安装并运行之前，不会发生集成。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-105">As you might expect, integration cannot take place until both Exchange 2013 and Lync Server 2013 are fully installed and up and running.</span></span> <span data-ttu-id="3c9aa-106">有关安装 Exchange 的详细信息，请参阅位于[https://go.microsoft.com/fwlink/p/?LinkId=268539](https://go.microsoft.com/fwlink/p/?linkid=268539)的 Exchange 2013 规划和部署文档。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-106">For details about installing Exchange, see the Exchange 2013 Planning and Deployment documentation at [https://go.microsoft.com/fwlink/p/?LinkId=268539](https://go.microsoft.com/fwlink/p/?linkid=268539).</span></span> <span data-ttu-id="3c9aa-107">有关安装 Lync Server 2013 的详细信息，请参阅中的规划和[https://go.microsoft.com/fwlink/p/?LinkId=254806](https://go.microsoft.com/fwlink/p/?linkid=254806)部署文档。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-107">For details about installing Lync Server 2013, see the planning and deployment documentation at [https://go.microsoft.com/fwlink/p/?LinkId=254806](https://go.microsoft.com/fwlink/p/?linkid=254806).</span></span>

<span data-ttu-id="3c9aa-108">在服务器启动并运行之后，您必须为 Lync Server 2013 和 Exchange 2013 分配服务器到服务器身份验证证书;这些证书允许 Lync Server 和 Exchange 交换信息，并与其他人通信。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-108">After the servers are up and running you must assign server-to-server authentication certificates to both Lync Server 2013 and Exchange 2013; these certificates allow Lync Server and Exchange to exchange information and to communicate with one another.</span></span> <span data-ttu-id="3c9aa-109">当您安装 Exchange 2013 时，将为您创建名称为 Microsoft Exchange Server 身份验证证书的自签名证书。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-109">When you install Exchange 2013, a self-signed certificate with the name Microsoft Exchange Server Auth Certificate is created for you.</span></span> <span data-ttu-id="3c9aa-110">此证书（可在本地计算机证书存储中找到）应用于 Exchange 2013 上的服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-110">This certificate, which can be found in the local computer certificate store, should be used for server-to-server authentication on Exchange 2013.</span></span> <span data-ttu-id="3c9aa-111">有关在 Exchange 2013 中分配证书的详细信息，请参阅处[https://go.microsoft.com/fwlink/p/?LinkId=268540](https://go.microsoft.com/fwlink/p/?linkid=268540)的 "配置邮件流和客户端访问"。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-111">For details about assigning certificates in Exchange 2013, see "Configure Mail Flow and Client Access" at [https://go.microsoft.com/fwlink/p/?LinkId=268540](https://go.microsoft.com/fwlink/p/?linkid=268540).</span></span>

<span data-ttu-id="3c9aa-112">对于 Lync Server 2013，您可以使用现有的 Lync Server 证书作为服务器到服务器身份验证证书;例如，您的默认证书也可以用作 OAuthTokenIssuer 证书。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-112">For Lync Server 2013 you can use an existing Lync Server certificate as your server-to-server authentication certificate; for example, your default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="3c9aa-113">Lync Server 2013 允许您将任何 Web 服务器证书用作服务器到服务器身份验证的证书，前提是：</span><span class="sxs-lookup"><span data-stu-id="3c9aa-113">Lync Server 2013 allows you to use any Web server certificate as the certificate for server-to-server authentication provided that:</span></span>

  - <span data-ttu-id="3c9aa-114">该证书包括主题字段中 SIP 域的名称。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-114">The certificate includes the name of your SIP domain in the Subject field.</span></span>

  - <span data-ttu-id="3c9aa-115">在所有前端服务器上配置与 OAuthTokenIssuer 证书相同的证书。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-115">The same certificate is configured as the OAuthTokenIssuer certificate on all of your Front End Servers.</span></span>

  - <span data-ttu-id="3c9aa-116">该证书长度至少为 2048 字节。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-116">The certificate has a length of at least 2048 bits.</span></span>

<span data-ttu-id="3c9aa-117">有关 Microsoft Lync Server 2013 的服务器到服务器身份验证证书的详细信息，请参阅[向 Microsoft Lync server 2013 分配服务器到服务器身份验证证书](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-117">For details about server-to-server authentication certificates for Microsoft Lync Server 2013, see [Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).</span></span>

<span data-ttu-id="3c9aa-118">在分配证书后，您必须在 Exchange 2013 上配置自动发现服务。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-118">After the certificates have been assigned you must then configure the autodiscover service on Exchange 2013.</span></span> <span data-ttu-id="3c9aa-119">在 Exchange 2013 中，自动发现服务配置用户配置文件，并在用户登录到系统时提供对 Exchange 服务的访问权限。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-119">In Exchange 2013, the autodiscover service configures user profiles and provides access to Exchange services when users log on to the system.</span></span> <span data-ttu-id="3c9aa-120">用户为自动发现服务提供其电子邮件地址，而这些服务为用户提供诸如以下信息：</span><span class="sxs-lookup"><span data-stu-id="3c9aa-120">Users present the autodiscover service with their email address and password; in turn, the services provide the user with information such as:</span></span>

  - <span data-ttu-id="3c9aa-121">Exchange 2013 的内部和外部连接的连接信息。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-121">Connection information for both internal and external connectivity to Exchange 2013.</span></span>

  - <span data-ttu-id="3c9aa-122">用户的邮箱服务器的位置。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-122">The location of the user’s Mailbox server.</span></span>

  - <span data-ttu-id="3c9aa-123">用于 Outlook 功能的 URL，例如忙/闲信息、统一消息和脱机通讯簿。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-123">URLs for Outlook features such as free/busy information, Unified Messaging, and the offline address book.</span></span>

  - <span data-ttu-id="3c9aa-124">Outlook 无处不在服务器设置。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-124">Outlook Anywhere server settings.</span></span>

<span data-ttu-id="3c9aa-125">必须先配置自动发现服务，然后才能集成 Lync Server 2013 和 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-125">The autodiscover service must be configured before you can integrate Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="3c9aa-126">您可以通过在 Exchange 命令行管理程序中运行以下命令并检查确认 autodiscoverserviceinternaluri 属性的值来验证是否已配置自动发现服务：</span><span class="sxs-lookup"><span data-stu-id="3c9aa-126">You can verify whether or not the autodiscover service has been configured by running the following command from the Exchange Management Shell and checking the value of the AutoDiscoverServiceInternalUri property:</span></span>

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

<span data-ttu-id="3c9aa-p106">如果此值为空，必须将 URI 分配到自动发现服务。通常此 URI 将看上去类似于：</span><span class="sxs-lookup"><span data-stu-id="3c9aa-p106">If this value is blank, you must assign a URI to the autodiscover service. Typically this URI will look similar to this:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

<span data-ttu-id="3c9aa-129">可通过运行类似以下命令分配自动发现 URI：</span><span class="sxs-lookup"><span data-stu-id="3c9aa-129">You can assign the autodiscover URI by running a command similar to this:</span></span>

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

<span data-ttu-id="3c9aa-130">有关自动发现服务的详细信息，请参阅处[https://go.microsoft.com/fwlink/p/?LinkId=268542](https://go.microsoft.com/fwlink/p/?linkid=268542)的 "了解自动发现服务"。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-130">For details about the autodiscover service, see "Understanding the Autodiscover Service" at [https://go.microsoft.com/fwlink/p/?LinkId=268542](https://go.microsoft.com/fwlink/p/?linkid=268542).</span></span>

<span data-ttu-id="3c9aa-131">配置自动发现服务后，必须修改 Lync Server OAuth 配置设置;这将确保 Lync Server 知道在哪里可以找到自动发现服务。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-131">After the autodiscover service has been configured you must then modify the Lync Server OAuth configuration settings; this ensures that Lync Server knows where to find the autodiscover service.</span></span> <span data-ttu-id="3c9aa-132">若要在 Lync Server 2013 中修改 OAuth 配置设置，请在 Lync Server 命令行管理程序中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-132">To modify the OAuth configuration settings in Lync Server 2013, run the following command from within the Lync Server Management Shell.</span></span> <span data-ttu-id="3c9aa-133">运行此命令时，请确保指定在 Exchange 服务器上运行的自动发现服务的 URI，并使用**自动发现**来指向服务位置，而不是**自动发现**（指向服务使用的 xml 文件）：</span><span class="sxs-lookup"><span data-stu-id="3c9aa-133">When running this command, be sure that you specify the URI to the autodiscover service running on your Exchange server, and that you use **autodiscover.svc** to point to the service location instead of **autodiscover.xml** (which points to the XML file used by the service):</span></span>

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> <span data-ttu-id="3c9aa-134">上述命令中的 Identity 参数是可选的;这是因为 Lync Server 仅允许您拥有一个单一的全局 OAuth 配置设置集合。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-134">The Identity parameter in the preceding command is optional; that's because Lync Server only allows you to have a single, global collection of OAuth configuration settings.</span></span> <span data-ttu-id="3c9aa-135">在其他情况下，这表示您可使用此稍简单的命令配置自动发现 URL：</span><span class="sxs-lookup"><span data-stu-id="3c9aa-135">Among other things, that means that you can configure the autodiscover URL by using this slightly-simpler command:</span></span><BR><span data-ttu-id="3c9aa-136">Set-csoauthconfiguration – ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"</span><span class="sxs-lookup"><span data-stu-id="3c9aa-136">Set-CsOAuthConfiguration–ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"</span></span><BR><span data-ttu-id="3c9aa-p109">如果您不熟悉该技术，OAuth 是由大量网站使用的标准身份验证协议。借助 OAuth，不会将用户凭据和密码从一台计算机传递到另一台计算机。但是，身份验证和授权是基于安全令牌的交换；这些令牌会将访问权限授予特定时间量的一组特定资源。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-p109">If you are unfamiliar with the technology, OAuth is a standard authorization protocol used by a number of major websites. With OAuth, user credentials and passwords are not passed from one computer to another. Instead, authentication and authorization is based on the exchange of security tokens; these tokens grant access to a specific set of resources for a specific amount of time.</span></span>



</div>

<span data-ttu-id="3c9aa-140">除了配置自动发现服务之外，还必须为指向您的 Exchange 服务器的服务创建 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-140">In addition to configuring the autodiscover service, you must also create a DNS record for the service that points to your Exchange server.</span></span> <span data-ttu-id="3c9aa-141">例如，如果您的自动发现服务位于 autodiscover.litwareinc.com，则需要为 autodiscover.litwareinc.com 创建一个 DNS 记录，该记录可解析为您的 Exchange 服务器的完全限定域名（例如，atl-exchange-001.litwareinc.com）。</span><span class="sxs-lookup"><span data-stu-id="3c9aa-141">For example, if your autodiscover service is located at autodiscover.litwareinc.com you will need to create a DNS record for autodiscover.litwareinc.com that resolves to the fully qualified domain name of your Exchange server (for example, atl-exchange-001.litwareinc.com).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

