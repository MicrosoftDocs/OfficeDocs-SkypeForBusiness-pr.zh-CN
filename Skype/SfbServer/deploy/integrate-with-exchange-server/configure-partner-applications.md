---
title: 在 Skype for Business Server 2015 和 Exchange Server 中配置合作伙伴应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: 摘要：将服务器配置为 Exchange Server 2016 或 Exchange Server 2013 和 Skype for business 服务器的服务器身份验证。
ms.openlocfilehash: 9512d271b23f26afcb1ef6385a1a6dd5d513c948
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797073"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a><span data-ttu-id="21f8c-103">在 Skype for Business Server 和 Exchange Server 中配置合作伙伴应用程序</span><span class="sxs-lookup"><span data-stu-id="21f8c-103">Configure partner applications in Skype for Business Server and Exchange Server</span></span>
 
<span data-ttu-id="21f8c-104">**摘要：** 将服务器配置为 Exchange Server 2016 或 Exchange Server 2013 和 Skype for business 服务器的服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="21f8c-104">**Summary:** Configure server to server authentication for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="21f8c-105">服务器到服务器身份验证通常要有两台需要相互通信的服务器以及一台第三方安全令牌服务器。</span><span class="sxs-lookup"><span data-stu-id="21f8c-105">Server-to-server authentication usually requires two servers that need to communicate with one another and a third-party security token server.</span></span> <span data-ttu-id="21f8c-106">如果服务器 A 和服务器 B 需要进行通信，则这两个服务器通常都通过联系令牌服务器并获取相互信任的安全令牌开始。</span><span class="sxs-lookup"><span data-stu-id="21f8c-106">If Server A and Server B need to communicate, then both of those servers typically start by contacting a token server and obtaining a mutually-trusted security token.</span></span> <span data-ttu-id="21f8c-107">之后服务器 A 会向服务器 B 提供安全令牌（反之亦然）作为保证真实性和可信度的方式。</span><span class="sxs-lookup"><span data-stu-id="21f8c-107">Server A then presents that security token to Server B (and vice-versa) as a way to guarantee its authenticity and trustworthiness.</span></span>
  
<span data-ttu-id="21f8c-108">但是，这是一个一般规则。</span><span class="sxs-lookup"><span data-stu-id="21f8c-108">However, that's a general rule.</span></span> <span data-ttu-id="21f8c-109">Skype for business 服务器、Exchange Server 2016、Exchange Server 2013 和 SharePoint Server 2013 在彼此通信时不需要使用第三方令牌服务器;这是因为这些服务器产品可以创建彼此不需要单独的令牌服务器即可接受的安全令牌。</span><span class="sxs-lookup"><span data-stu-id="21f8c-109">Skype for Business Server, Exchange Server 2016, Exchange Server 2013, and SharePoint Server 2013 do not need to use a third-party token server when communicating with one another; that's because these server products can create security tokens that can be accepted by one another without the need for a separate token server.</span></span> <span data-ttu-id="21f8c-110">（此功能仅在 Skype for Business Server、Exchange Server 2016、Exchange Server 2013 和 SharePoint Server 2013 中可用。</span><span class="sxs-lookup"><span data-stu-id="21f8c-110">(This capability is only available in Skype for Business Server, Exchange Server 2016, Exchange Server 2013, and SharePoint Server 2013.</span></span> <span data-ttu-id="21f8c-111">如果需要与其他服务器（包括其他 Microsoft 服务器产品）设置服务器到服务器的身份验证，则需要使用第三方令牌服务器执行此操作。</span><span class="sxs-lookup"><span data-stu-id="21f8c-111">If you need to set up server-to-server authentication with other servers, including other Microsoft server products, then you will need to do so by using a third-party token server.)</span></span>
  
<span data-ttu-id="21f8c-112">若要在 Skype for Business 服务器和 Exchange Server 之间设置服务器到服务器身份验证，你必须执行两项操作：1）必须为每台服务器分配相应的证书;和2），您必须将每台服务器配置为另一台服务器的合作伙伴应用程序：这意味着您必须将 Skype for business 服务器配置为 Exchange Server 的合作伙伴应用程序，并且您必须将 Exchange Server 配置为适用于 Skype 的合作伙伴应用程序适用于企业服务器。</span><span class="sxs-lookup"><span data-stu-id="21f8c-112">In order to set up server-to-server authentication between Skype for Business Server and Exchange Server you must do two things: 1) you must assign the appropriate certificates to each server; and, 2) you must configure each server to be a partner application of the other server: that means you must configure Skype for Business Server to be a partner application for Exchange Server, and you must configure Exchange Server to be a partner application for Skype for Business Server.</span></span>
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a><span data-ttu-id="21f8c-113">将 Skype for business 服务器配置为 Exchange Server 的合作伙伴应用程序</span><span class="sxs-lookup"><span data-stu-id="21f8c-113">Configuring Skype for Business Server to be a Partner Application for Exchange Server</span></span>

<span data-ttu-id="21f8c-114">将 Skype for business 服务器配置为具有 Exchange Server 2016 或 Exchange Server 2013 的合作伙伴应用程序的最简单方法是运行 Configure-EnterprisePartnerApplication 脚本，该脚本是随 Exchange Server 一起提供的 Windows PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="21f8c-114">The easiest way to configure Skype for Business Server to be a partner application with Exchange Server 2016 or Exchange Server 2013 is to run the Configure-EnterprisePartnerApplication.ps1 script, a Windows PowerShell script that ships with Exchange Server.</span></span> <span data-ttu-id="21f8c-115">若要运行此脚本，必须提供 Skype for Business Server 身份验证元数据文档的 URL;这通常是 Skype for Business 服务器池的完全限定的域名，后跟后缀/metadata/json/1。</span><span class="sxs-lookup"><span data-stu-id="21f8c-115">To run this script, you must provide the URL for the Skype for Business Server authentication metadata document; this will typically be the fully qualified domain name of the Skype for Business Server pool followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="21f8c-116">例如：</span><span class="sxs-lookup"><span data-stu-id="21f8c-116">For example:</span></span>
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

<span data-ttu-id="21f8c-117">若要将 Skype for Business 服务器配置为合作伙伴应用程序，请打开 Exchange 命令行管理程序并运行与此类似的命令（假设 Exchange 已安装在驱动器 C：上，并且它使用默认文件夹路径）：</span><span class="sxs-lookup"><span data-stu-id="21f8c-117">To configure Skype for Business Server as a partner application, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

<span data-ttu-id="21f8c-118">配置合作伙伴应用程序后，建议您在 Exchange 邮箱和客户端访问服务器上停止并重新启动 Internet 信息服务（IIS）。</span><span class="sxs-lookup"><span data-stu-id="21f8c-118">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="21f8c-119">您可使用类似于以下命令的命令重新启动 IIS，以下命令将重新启动计算机 atl-exchange-001 上的此服务：</span><span class="sxs-lookup"><span data-stu-id="21f8c-119">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>
  
```powershell
iisreset atl-exchange-001
```

<span data-ttu-id="21f8c-120">此命令可以从 Exchange 命令行管理程序中运行，也可以从任何其他命令窗口中通过管理员权限运行。</span><span class="sxs-lookup"><span data-stu-id="21f8c-120">This command can be run from within the Exchange Management Shell or from any other command window run under administrator privileges.</span></span>
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a><span data-ttu-id="21f8c-121">将 Exchange Server 配置为 Skype for Business 服务器的合作伙伴应用程序</span><span class="sxs-lookup"><span data-stu-id="21f8c-121">Configuring Exchange Server to be a Partner Application for Skype for Business Server</span></span>

<span data-ttu-id="21f8c-122">将 Skype for business 服务器配置为 Exchange Server 2016 或 Exchange Server 2013 的合作伙伴应用程序后，必须随后将 Exchange Server 配置为适用于 Skype for business 服务器的合作伙伴应用程序。</span><span class="sxs-lookup"><span data-stu-id="21f8c-122">After you have configured Skype for Business Server to be a partner application for Exchange Server 2016 or Exchange Server 2013, you must then configure Exchange Server to be a partner application for Skype for Business Server.</span></span> <span data-ttu-id="21f8c-123">这可以通过使用 Skype for Business 服务器管理外壳程序和指定 Exchange 的身份验证元数据文档来完成;这通常是 Exchange 自动发现服务的 URI，后跟后缀/metadata/json/1。</span><span class="sxs-lookup"><span data-stu-id="21f8c-123">This can be done by using the Skype for Business Server Management Shell and specifying the authentication metadata document for Exchange; this will typically be the URI of the Exchange autodiscover service followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="21f8c-124">例如：</span><span class="sxs-lookup"><span data-stu-id="21f8c-124">For example:</span></span>
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

<span data-ttu-id="21f8c-125">在 Skype for Business 服务器中，通过使用[CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) cmdlet 配置合作伙伴应用程序。</span><span class="sxs-lookup"><span data-stu-id="21f8c-125">In Skype for Business Server, partner applications are configured by using the [New-CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="21f8c-126">除了指定元数据 URI 之外，还应将应用程序信任级别设置为 "完全";这将允许 Exchange 同时代表领域中的自身和任何授权用户。</span><span class="sxs-lookup"><span data-stu-id="21f8c-126">In addition to specifying the metadata URI you should also set the application trust level to Full; this will allow Exchange to represent both itself and any authorized user in the realm.</span></span> <span data-ttu-id="21f8c-127">例如：</span><span class="sxs-lookup"><span data-stu-id="21f8c-127">For example:</span></span>
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

<span data-ttu-id="21f8c-128">或者，你可以通过复制和修改 Skype for Business Server 服务器到服务器身份验证文档中找到的脚本代码来创建合作伙伴应用程序。</span><span class="sxs-lookup"><span data-stu-id="21f8c-128">Alternatively, you can create a partner application by copying and modifying the script code found in the Skype for Business Server server-to-server authentication documentation.</span></span> <span data-ttu-id="21f8c-129">有关详细信息，请参阅[Skype For Business server 文章中的 "管理服务器到服务器的身份验证（OAuth）和合作伙伴应用程序](../../manage/authentication/server-to-server-and-partner-applications.md)"。</span><span class="sxs-lookup"><span data-stu-id="21f8c-129">See the [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) article for more information.</span></span>
  
<span data-ttu-id="21f8c-130">如果你已成功配置 Skype for business Server 和 Exchange Server 的合作伙伴应用程序，则你还成功配置了这两个产品之间的服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="21f8c-130">If you have successfully configured partner applications for both Skype for Business Server and Exchange Server, you have also successfully configured server-to-server authentication between the two products.</span></span> <span data-ttu-id="21f8c-131">Skype for Business 服务器包括 Windows PowerShell cmdlet、 [CsExStorageConnectivity 测试](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps)版，可用于验证服务器到服务器身份验证是否已正确配置以及 Skype For Business Server 存储服务是否可以连接到 Exchange 服务器。</span><span class="sxs-lookup"><span data-stu-id="21f8c-131">Skype for Business Server includes a Windows PowerShell cmdlet, [Test-CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) which enables you to verify that server-to-server authentication has been correctly configured and that the Skype for Business Server Storage Service can connect to Exchange Server.</span></span> <span data-ttu-id="21f8c-132">该 cmdlet 通过以下方式执行此操作：连接到 Exchange Server 用户的邮箱，向该用户的 "对话历史记录" 文件夹中写入项目，然后（可选）删除该项目。</span><span class="sxs-lookup"><span data-stu-id="21f8c-132">The cmdlet does this by connecting to the mailbox of an Exchange Server user, writing an item into the Conversation History folder for that user, and then (optionally) deleting that item.</span></span>
  
<span data-ttu-id="21f8c-133">若要测试 Skype for business 服务器和 Exchange Server 的集成，请从 Skype for business 服务器管理外壳程序运行类似以下内容的命令：</span><span class="sxs-lookup"><span data-stu-id="21f8c-133">To test the integration of Skype for Business Server and Exchange Server, run a command similar to the following from the Skype for Business Server Management Shell:</span></span>
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="21f8c-134">在前面的命令中，SipUri 表示具有 Exchange Server 帐户的用户的 SIP 地址;您的命令将失败，这不是有效的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="21f8c-134">In the preceding command, the SipUri represents the SIP address of a user with an account on Exchange Server; your command will fail in this is not a valid user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="21f8c-135">如果你收到来自此 cmdlet 的401响应，这可能是因为 Exchange 的默认配置不包括对接受 Oauth 令牌的支持。</span><span class="sxs-lookup"><span data-stu-id="21f8c-135">If you receive a 401 response from this cmdlet, it is probably because the default configuration for Exchange does not include support for accepting Oauth tokens.</span></span> <span data-ttu-id="21f8c-136">有关在 Exchange 中使用 Oauth 的详细信息，请参阅[使用 SharePoint 2013 和 Skype For Business 服务器配置 oauth 身份验证](https://go.microsoft.com/fwlink/p/?LinkId=513103)。</span><span class="sxs-lookup"><span data-stu-id="21f8c-136">For more information about using Oauth in Exchange, see [Configure OAuth authentication with SharePoint 2013 and Skype for Business Server](https://go.microsoft.com/fwlink/p/?LinkId=513103).</span></span> 
  
<span data-ttu-id="21f8c-137">如果测试成功并且建立了连接，则您可继续配置存档集成和统一的联系人存储等可选功能。</span><span class="sxs-lookup"><span data-stu-id="21f8c-137">If the test succeeds and connectivity has been established, you can then proceed to configure optional features such as archiving integration and the unified contact store.</span></span>
