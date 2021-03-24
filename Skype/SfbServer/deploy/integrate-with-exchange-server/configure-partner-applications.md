---
title: 在 Skype for Business Server 2015 和 Exchange Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 摘要：为 Exchange Server 2016 或 Exchange Server 2013 和 Skype for Business Server 配置服务器到服务器身份验证。
ms.openlocfilehash: 47f192ce11a48ab4c256ac6a1f499aa24563a725
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110108"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a><span data-ttu-id="6ad22-103">在 Skype for Business Server 和 Exchange Server</span><span class="sxs-lookup"><span data-stu-id="6ad22-103">Configure partner applications in Skype for Business Server and Exchange Server</span></span>
 
<span data-ttu-id="6ad22-104">**摘要：** 为 Exchange Server 2016 或 Exchange Server 2013 和 Skype for Business Server 配置服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="6ad22-104">**Summary:** Configure server to server authentication for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="6ad22-105">服务器到服务器身份验证通常需要两台需要相互通信的服务器和第三方安全令牌服务器。</span><span class="sxs-lookup"><span data-stu-id="6ad22-105">Server-to-server authentication usually requires two servers that need to communicate with one another and a third-party security token server.</span></span> <span data-ttu-id="6ad22-106">如果服务器 A 和服务器 B 需要通信，则这两台服务器通常首先联系令牌服务器并获取相互信任的安全令牌。</span><span class="sxs-lookup"><span data-stu-id="6ad22-106">If Server A and Server B need to communicate, then both of those servers typically start by contacting a token server and obtaining a mutually-trusted security token.</span></span> <span data-ttu-id="6ad22-107">然后，服务器 A 向服务器 B (安全令牌) ，以确保其真实性和可信度。</span><span class="sxs-lookup"><span data-stu-id="6ad22-107">Server A then presents that security token to Server B (and vice-versa) as a way to guarantee its authenticity and trustworthiness.</span></span>
  
<span data-ttu-id="6ad22-108">但是，这是一般规则。</span><span class="sxs-lookup"><span data-stu-id="6ad22-108">However, that's a general rule.</span></span> <span data-ttu-id="6ad22-109">Skype for Business Server、Exchange Server 2016、Exchange Server 2013 和 SharePoint Server 2013 在相互通信时不需要使用第三方令牌服务器;这是因为这些服务器产品可以创建彼此都可以接受的安全令牌，而无需使用单独的令牌服务器。</span><span class="sxs-lookup"><span data-stu-id="6ad22-109">Skype for Business Server, Exchange Server 2016, Exchange Server 2013, and SharePoint Server 2013 do not need to use a third-party token server when communicating with one another; that's because these server products can create security tokens that can be accepted by one another without the need for a separate token server.</span></span> <span data-ttu-id="6ad22-110"> (此功能仅适用于 Skype for Business Server、Exchange Server 2016、Exchange Server 2013 和 SharePoint Server 2013。</span><span class="sxs-lookup"><span data-stu-id="6ad22-110">(This capability is only available in Skype for Business Server, Exchange Server 2016, Exchange Server 2013, and SharePoint Server 2013.</span></span> <span data-ttu-id="6ad22-111">如果需要设置与其他服务器（包括其他 Microsoft 服务器产品）的服务器到服务器身份验证，则需要使用第三方令牌服务器) </span><span class="sxs-lookup"><span data-stu-id="6ad22-111">If you need to set up server-to-server authentication with other servers, including other Microsoft server products, then you will need to do so by using a third-party token server.)</span></span>
  
<span data-ttu-id="6ad22-112">为了在 Skype for Business Server 和 skype for Business Server 之间设置服务器到服务器身份验证Exchange Server必须执行两项操作：1) 必须为每个服务器分配相应的证书;此外，) 必须将每台服务器配置为另一台服务器的合作伙伴应用程序：这意味着必须将 Skype for Business Server 配置为 Exchange Server 的合作伙伴应用程序，并且必须将 Exchange Server 配置为 Skype for Business Server 的合作伙伴应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ad22-112">In order to set up server-to-server authentication between Skype for Business Server and Exchange Server you must do two things: 1) you must assign the appropriate certificates to each server; and, 2) you must configure each server to be a partner application of the other server: that means you must configure Skype for Business Server to be a partner application for Exchange Server, and you must configure Exchange Server to be a partner application for Skype for Business Server.</span></span>
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a><span data-ttu-id="6ad22-113">将 Skype for Business Server 配置为 skype for Business Server 合作伙伴Exchange Server</span><span class="sxs-lookup"><span data-stu-id="6ad22-113">Configuring Skype for Business Server to be a Partner Application for Exchange Server</span></span>

<span data-ttu-id="6ad22-114">将 Skype for Business Server 配置为 Exchange Server 2016 或 Exchange Server 2013 的合作伙伴应用程序的最简单方法是运行 Configure-EnterprisePartnerApplication.ps1 脚本，这是 Exchange Server 附带一个 Windows PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="6ad22-114">The easiest way to configure Skype for Business Server to be a partner application with Exchange Server 2016 or Exchange Server 2013 is to run the Configure-EnterprisePartnerApplication.ps1 script, a Windows PowerShell script that ships with Exchange Server.</span></span> <span data-ttu-id="6ad22-115">若要运行此脚本，你必须提供 Skype for Business Server 身份验证元数据文档的 URL;这通常是 Skype for Business Server 池的完全限定域名，后跟后缀 /metadata/json/1。</span><span class="sxs-lookup"><span data-stu-id="6ad22-115">To run this script, you must provide the URL for the Skype for Business Server authentication metadata document; this will typically be the fully qualified domain name of the Skype for Business Server pool followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="6ad22-116">例如：</span><span class="sxs-lookup"><span data-stu-id="6ad22-116">For example:</span></span>
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

<span data-ttu-id="6ad22-117">若要将 Skype for Business Server 配置为合作伙伴应用程序，请打开 Exchange 命令行管理程序并运行与以下命令类似的命令 (假定 Exchange 已安装在驱动器 C： 上，并使用默认文件夹路径) ：</span><span class="sxs-lookup"><span data-stu-id="6ad22-117">To configure Skype for Business Server as a partner application, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

<span data-ttu-id="6ad22-118">配置合作伙伴应用程序后，建议您在 Exchange 邮箱和客户端访问Internet Information Services (IIS) 停止并重新启动。</span><span class="sxs-lookup"><span data-stu-id="6ad22-118">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="6ad22-119">您可使用类似于以下命令的命令重新启动 IIS，以下命令将重新启动计算机 atl-exchange-001 上的此服务：</span><span class="sxs-lookup"><span data-stu-id="6ad22-119">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>
  
```powershell
iisreset atl-exchange-001
```

<span data-ttu-id="6ad22-120">此命令可以从 Exchange 命令行管理程序 内运行，也可以从以管理员权限运行的其他命令窗口运行。</span><span class="sxs-lookup"><span data-stu-id="6ad22-120">This command can be run from within the Exchange Management Shell or from any other command window run under administrator privileges.</span></span>
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a><span data-ttu-id="6ad22-121">将Exchange Server Skype for Business Server 合作伙伴应用程序</span><span class="sxs-lookup"><span data-stu-id="6ad22-121">Configuring Exchange Server to be a Partner Application for Skype for Business Server</span></span>

<span data-ttu-id="6ad22-122">将 Skype for Business Server 配置为 Exchange Server 2016 或 Exchange Server 2013 的合作伙伴应用程序后，必须将 Exchange Server 配置为 Skype for Business Server 的合作伙伴应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ad22-122">After you have configured Skype for Business Server to be a partner application for Exchange Server 2016 or Exchange Server 2013, you must then configure Exchange Server to be a partner application for Skype for Business Server.</span></span> <span data-ttu-id="6ad22-123">为此，可以使用 Skype for Business Server 命令行管理程序并指定 Exchange 的身份验证元数据文档;这通常是 Exchange 自动发现服务的 URI，后跟后缀 /metadata/json/1。</span><span class="sxs-lookup"><span data-stu-id="6ad22-123">This can be done by using the Skype for Business Server Management Shell and specifying the authentication metadata document for Exchange; this will typically be the URI of the Exchange autodiscover service followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="6ad22-124">例如：</span><span class="sxs-lookup"><span data-stu-id="6ad22-124">For example:</span></span>
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

<span data-ttu-id="6ad22-125">在 Skype for Business Server 中，合作伙伴应用程序是使用 [New-CsPartnerApplication](/powershell/module/skype/new-cspartnerapplication?view=skype-ps) cmdlet 配置的。</span><span class="sxs-lookup"><span data-stu-id="6ad22-125">In Skype for Business Server, partner applications are configured by using the [New-CsPartnerApplication](/powershell/module/skype/new-cspartnerapplication?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="6ad22-126">除了指定元数据 URI 之外，还应将应用程序信任级别设置为"完全";这将允许 Exchange 代表自身和领域中任何授权的用户。</span><span class="sxs-lookup"><span data-stu-id="6ad22-126">In addition to specifying the metadata URI you should also set the application trust level to Full; this will allow Exchange to represent both itself and any authorized user in the realm.</span></span> <span data-ttu-id="6ad22-127">例如：</span><span class="sxs-lookup"><span data-stu-id="6ad22-127">For example:</span></span>
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

<span data-ttu-id="6ad22-128">或者，您可以通过复制和修改 Skype for Business Server 服务器到服务器身份验证文档中的脚本代码来创建合作伙伴应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ad22-128">Alternatively, you can create a partner application by copying and modifying the script code found in the Skype for Business Server server-to-server authentication documentation.</span></span> <span data-ttu-id="6ad22-129">有关详细信息， [请参阅 Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) 一文。</span><span class="sxs-lookup"><span data-stu-id="6ad22-129">See the [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) article for more information.</span></span>
  
<span data-ttu-id="6ad22-130">如果已成功为 Skype for Business Server 和 Exchange Server 配置合作伙伴应用程序，则还可以在两个产品之间成功配置服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="6ad22-130">If you have successfully configured partner applications for both Skype for Business Server and Exchange Server, you have also successfully configured server-to-server authentication between the two products.</span></span> <span data-ttu-id="6ad22-131">Skype for Business Server 包括一个 Windows PowerShell cmdlet [Test-CsExStorageConnectivity，](/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) 它使您能够验证服务器到服务器身份验证是否正确配置，以及 Skype for Business Server 存储服务能否连接到 Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="6ad22-131">Skype for Business Server includes a Windows PowerShell cmdlet, [Test-CsExStorageConnectivity](/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) which enables you to verify that server-to-server authentication has been correctly configured and that the Skype for Business Server Storage Service can connect to Exchange Server.</span></span> <span data-ttu-id="6ad22-132">此 cmdlet 通过连接到 Exchange Server 用户的邮箱、将项目写入该用户的对话历史记录文件夹中，然后选择 (删除) 来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="6ad22-132">The cmdlet does this by connecting to the mailbox of an Exchange Server user, writing an item into the Conversation History folder for that user, and then (optionally) deleting that item.</span></span>
  
<span data-ttu-id="6ad22-133">若要测试 Skype for Business Server 与 Exchange Server 集成，请从 Skype for Business Server 命令行管理程序 运行类似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="6ad22-133">To test the integration of Skype for Business Server and Exchange Server, run a command similar to the following from the Skype for Business Server Management Shell:</span></span>
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="6ad22-134">在上一个命令中，SipUri 表示拥有用户帐户的用户的 SIP Exchange Server;你的命令将失败，因为这不是一个有效的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="6ad22-134">In the preceding command, the SipUri represents the SIP address of a user with an account on Exchange Server; your command will fail in this is not a valid user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6ad22-135">如果从此 cmdlet 收到 401 响应，可能是因为 Exchange 的默认配置不包括对接受 Oauth 令牌的支持。</span><span class="sxs-lookup"><span data-stu-id="6ad22-135">If you receive a 401 response from this cmdlet, it is probably because the default configuration for Exchange does not include support for accepting Oauth tokens.</span></span> <span data-ttu-id="6ad22-136">有关在 Exchange 中使用 Oauth 的信息，请参阅 Configure [OAuth authentication with SharePoint 2013 and Skype for Business Server。](/exchange/configure-oauth-authentication-with-sharepoint-2013-and-lync-2013-exchange-2013-help)</span><span class="sxs-lookup"><span data-stu-id="6ad22-136">For more information about using Oauth in Exchange, see [Configure OAuth authentication with SharePoint 2013 and Skype for Business Server](/exchange/configure-oauth-authentication-with-sharepoint-2013-and-lync-2013-exchange-2013-help).</span></span> 
  
<span data-ttu-id="6ad22-137">如果测试成功并且建立了连接，则您可继续配置存档集成和统一的联系人存储等可选功能。</span><span class="sxs-lookup"><span data-stu-id="6ad22-137">If the test succeeds and connectivity has been established, you can then proceed to configure optional features such as archiving integration and the unified contact store.</span></span>