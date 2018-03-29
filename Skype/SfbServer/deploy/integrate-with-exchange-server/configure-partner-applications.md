---
title: 在 Skype 为业务服务器 2015年和 Exchange Server 配置合作伙伴应用程序
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: 摘要： 配置服务器到服务器的身份验证的 Exchange Server 2016年或 Exchange Server 2013年和 Skype 业务服务器 2015年。
ms.openlocfilehash: d7b3d93126c5b2db06e5f7343f5636b3c305d7c8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-partner-applications-in-skype-for-business-server-2015-and-exchange-server"></a><span data-ttu-id="56122-103">在 Skype 为业务服务器 2015年和 Exchange Server 配置合作伙伴应用程序</span><span class="sxs-lookup"><span data-stu-id="56122-103">Configure partner applications in Skype for Business Server 2015 and Exchange Server</span></span>
 
<span data-ttu-id="56122-104">**摘要：**配置服务器到服务器的身份验证的 Exchange Server 2016年或 Exchange Server 2013年和 Skype 业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="56122-104">**Summary:** Configure server to server authentication for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="56122-105">服务器到服务器身份验证通常要有两台需要相互通信的服务器以及一台第三方安全令牌服务器。</span><span class="sxs-lookup"><span data-stu-id="56122-105">Server-to-server authentication usually requires two servers that need to communicate with one another and a third-party security token server.</span></span> <span data-ttu-id="56122-106">如果服务器 A 和服务器 B 需要进行通信，然后这些服务器的两个通常首先与令牌服务器联系并获得相互信任安全令牌。</span><span class="sxs-lookup"><span data-stu-id="56122-106">If Server A and Server B need to communicate, then both of those servers typically start by contacting a token server and obtaining a mutually-trusted security token.</span></span> <span data-ttu-id="56122-107">之后服务器 A 会向服务器 B 提供安全令牌（反之亦然）作为保证真实性和可信度的方式。</span><span class="sxs-lookup"><span data-stu-id="56122-107">Server A then presents that security token to Server B (and vice-versa) as a way to guarantee its authenticity and trustworthiness.</span></span>
  
<span data-ttu-id="56122-108">但是，这是一般规则。</span><span class="sxs-lookup"><span data-stu-id="56122-108">However, that's a general rule.</span></span> <span data-ttu-id="56122-109">Skype 业务服务器 2015年、 Exchange Server 2016年、 Exchange Server 2013，和 SharePoint Server 2013 不需要与另一个; 通信时使用第三方的令牌服务器这是因为这些服务器产品可以创建无需单独的令牌服务器通过另一个被接受的安全令牌。</span><span class="sxs-lookup"><span data-stu-id="56122-109">Skype for Business Server 2015, Exchange Server 2016, Exchange Server 2013, and SharePoint Server 2013 do not need to use a third-party token server when communicating with one another; that's because these server products can create security tokens that can be accepted by one another without the need for a separate token server.</span></span> <span data-ttu-id="56122-110">（此功能才可用在 Skype 业务服务器 2015年、 Exchange Server 2016年、 Exchange Server 2013，和 SharePoint Server 2013。</span><span class="sxs-lookup"><span data-stu-id="56122-110">(This capability is only available in Skype for Business Server 2015, Exchange Server 2016, Exchange Server 2013, and SharePoint Server 2013.</span></span> <span data-ttu-id="56122-111">如果您需要设置服务器到服务器与其他服务器的身份验证，包括其他的 Microsoft 服务器产品，则您将需要使用第三方的令牌服务器进行操作。）</span><span class="sxs-lookup"><span data-stu-id="56122-111">If you need to set up server-to-server authentication with other servers, including other Microsoft server products, then you will need to do so by using a third-party token server.)</span></span>
  
<span data-ttu-id="56122-112">Skype 业务服务器和 Exchange Server 之间的服务器到服务器身份验证设置，您必须做两件事： 1) 必须将适当的证书分配给每个服务器;并且，2） 您必须配置为其他服务器的合作伙伴应用程序的每台服务器： 这意味着您必须配置为 Exchange Server 的合作伙伴应用程序的业务服务器 2015年的 Skype，您必须配置 Exchange Server 是一个合作伙伴应用程序业务服务器 2015 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="56122-112">In order to set up server-to-server authentication between Skype for Business Server and Exchange Server you must do two things: 1) you must assign the appropriate certificates to each server; and, 2) you must configure each server to be a partner application of the other server: that means you must configure Skype for Business Server 2015 to be a partner application for Exchange Server, and you must configure Exchange Server to be a partner application for Skype for Business Server 2015.</span></span>
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a><span data-ttu-id="56122-113">Skype 将 Exchange Server 的合作伙伴应用程序的业务服务器的配置</span><span class="sxs-lookup"><span data-stu-id="56122-113">Configuring Skype for Business Server to be a Partner Application for Exchange Server</span></span>

<span data-ttu-id="56122-114">配置为与 Exchange Server 2016年或 Exchange Server 2013年的合作伙伴应用程序的业务服务器 2015年的 Skype 的最简单方法就是运行配置 EnterprisePartnerApplication.ps1 脚本，随 Exchange Server 的 Windows PowerShell 脚本.</span><span class="sxs-lookup"><span data-stu-id="56122-114">The easiest way to configure Skype for Business Server 2015 to be a partner application with Exchange Server 2016 or Exchange Server 2013 is to run the Configure-EnterprisePartnerApplication.ps1 script, a Windows PowerShell script that ships with Exchange Server.</span></span> <span data-ttu-id="56122-115">若要运行此脚本，您必须提供的 URL Skype 业务服务器身份验证元数据文档;通常，这将完全限定的域名的 Skype 跟后缀 /metadata/json/1 业务服务器 2015年池。</span><span class="sxs-lookup"><span data-stu-id="56122-115">To run this script, you must provide the URL for the Skype for Business Server authentication metadata document; this will typically be the fully qualified domain name of the Skype for Business Server 2015 pool followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="56122-116">例如：</span><span class="sxs-lookup"><span data-stu-id="56122-116">For example:</span></span>
  
```
https://atl-cs-001.litwareinc.com/metadata/json/1
```

<span data-ttu-id="56122-117">要配置 Skype 业务合作伙伴应用程序的服务器，打开 Exchange 管理外壳程序并运行与以下类似的命令 （假定驱动器 c： 上安装了 Exchange 和它使用默认的文件夹路径）：</span><span class="sxs-lookup"><span data-stu-id="56122-117">To configure Skype for Business Server as a partner application, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

<span data-ttu-id="56122-118">合作伙伴应用程序配置后建议您停止并重新启动 Exchange 邮箱存储和客户端访问服务器上的 Internet Information Services (IIS)。</span><span class="sxs-lookup"><span data-stu-id="56122-118">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="56122-119">您可使用类似于以下命令的命令重新启动 IIS，以下命令将重新启动计算机 atl-exchange-001 上的此服务：</span><span class="sxs-lookup"><span data-stu-id="56122-119">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>
  
```
iisreset atl-exchange-001
```

<span data-ttu-id="56122-120">在 Exchange 管理外壳程序中或从管理员权限下运行的任何其他命令窗口，可以从运行此命令。</span><span class="sxs-lookup"><span data-stu-id="56122-120">This command can be run from within the Exchange Management Shell or from any other command window run under administrator privileges.</span></span>
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a><span data-ttu-id="56122-121">配置 Exchange Server 将 Skype 业务服务器合作伙伴应用程序</span><span class="sxs-lookup"><span data-stu-id="56122-121">Configuring Exchange Server to be a Partner Application for Skype for Business Server</span></span>

<span data-ttu-id="56122-122">在配置 Exchange Server 2016年或 Exchange Server 2013年合作伙伴应用程序的业务服务器 2015年的 Skype 之后，然后必须配置 Exchange Server 将 Skype 业务服务器的合作伙伴应用程序。</span><span class="sxs-lookup"><span data-stu-id="56122-122">After you have configured Skype for Business Server 2015 to be a partner application for Exchange Server 2016 or Exchange Server 2013, you must then configure Exchange Server to be a partner application for Skype for Business Server.</span></span> <span data-ttu-id="56122-123">这可以通过使用 Skype 业务服务器管理外壳和指定身份验证元数据文档交换;这通常是跟后缀 /metadata/json/1 Exchange 自动发现服务的 URI。</span><span class="sxs-lookup"><span data-stu-id="56122-123">This can be done by using the Skype for Business Server Management Shell and specifying the authentication metadata document for Exchange; this will typically be the URI of the Exchange autodiscover service followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="56122-124">例如：</span><span class="sxs-lookup"><span data-stu-id="56122-124">For example:</span></span>
  
```
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

<span data-ttu-id="56122-125">在 Skype 业务服务器，通过使用[New CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) cmdlet 配置合作伙伴应用程序。</span><span class="sxs-lookup"><span data-stu-id="56122-125">In Skype for Business Server, partner applications are configured by using the [New-CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="56122-126">除了指定元数据 URI 应当还应用程序信任级别设置为完全;这将允许 Exchange 表示本身和任何领域中的授权的用户。</span><span class="sxs-lookup"><span data-stu-id="56122-126">In addition to specifying the metadata URI you should also set the application trust level to Full; this will allow Exchange to represent both itself and any authorized user in the realm.</span></span> <span data-ttu-id="56122-127">例如：</span><span class="sxs-lookup"><span data-stu-id="56122-127">For example:</span></span>
  
```
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

<span data-ttu-id="56122-128">或者，您可以创建合作伙伴应用程序复制并修改 Skype 业务服务器 2015年服务器到服务器的身份验证文档中的脚本代码。</span><span class="sxs-lookup"><span data-stu-id="56122-128">Alternatively, you can create a partner application by copying and modifying the script code found in the Skype for Business Server 2015 server-to-server authentication documentation.</span></span> <span data-ttu-id="56122-129">请参阅[管理服务器的身份验证 (OAuth) 和合作伙伴应用程序中的业务服务器 2015 Skype](../../manage/authentication/server-to-server-and-partner-applications.md)文章的详细信息。</span><span class="sxs-lookup"><span data-stu-id="56122-129">See the [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server 2015](../../manage/authentication/server-to-server-and-partner-applications.md) article for more information.</span></span>
  
<span data-ttu-id="56122-130">如果您已成功配置为两种 Skype 业务服务器和 Exchange Server 的合作伙伴应用程序，还成功配置了两个产品之间的服务器到服务器进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="56122-130">If you have successfully configured partner applications for both Skype for Business Server and Exchange Server, you have also successfully configured server-to-server authentication between the two products.</span></span> <span data-ttu-id="56122-131">Skype 的业务服务器 2015年包括 Windows PowerShell cmdlet，使您可以验证是否已正确配置该服务器的身份验证和[测试 CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) Skype 业务服务器存储服务可以连接到 Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="56122-131">Skype for Business Server 2015 includes a Windows PowerShell cmdlet, [Test-CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) which enables you to verify that server-to-server authentication has been correctly configured and that the Skype for Business Server Storage Service can connect to Exchange Server.</span></span> <span data-ttu-id="56122-132">该 cmdlet 会通过连接到邮箱的 Exchange Server 用户、 为用户编写到对话历史记录文件夹中的项，然后 （可选） 删除该项目。</span><span class="sxs-lookup"><span data-stu-id="56122-132">The cmdlet does this by connecting to the mailbox of an Exchange Server user, writing an item into the Conversation History folder for that user, and then (optionally) deleting that item.</span></span>
  
<span data-ttu-id="56122-133">若要测试的 Skype 业务服务器 2015年和 Exchange Server 的集成，业务服务器管理外壳程序运行从 Skype 与以下类似的命令：</span><span class="sxs-lookup"><span data-stu-id="56122-133">To test the integration of Skype for Business Server 2015 and Exchange Server, run a command similar to the following from the Skype for Business Server Management Shell:</span></span>
  
```
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="56122-134">在上述命令中，SipUri 表示 SIP 地址的用户的帐户在 Exchange Server;您的命令将在失败这不是一个有效的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="56122-134">In the preceding command, the SipUri represents the SIP address of a user with an account on Exchange Server; your command will fail in this is not a valid user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="56122-135">如果您收到来自此 cmdlet 的 401 响应，可能是因为 Exchange 的默认配置不包括对接受 Oauth 标记的支持。</span><span class="sxs-lookup"><span data-stu-id="56122-135">If you receive a 401 response from this cmdlet, it is probably because the default configuration for Exchange does not include support for accepting Oauth tokens.</span></span> <span data-ttu-id="56122-136">有关在 Exchange 使用 Oauth 的详细信息，请参阅[使用 SharePoint 2013 和 Skype 的业务服务器 2015年配置 OAuth 进行身份验证](https://go.microsoft.com/fwlink/p/?LinkId=513103)。</span><span class="sxs-lookup"><span data-stu-id="56122-136">For more information about using Oauth in Exchange, see [Configure OAuth authentication with SharePoint 2013 and Skype for Business Server 2015](https://go.microsoft.com/fwlink/p/?LinkId=513103).</span></span> 
  
<span data-ttu-id="56122-137">如果测试成功并且建立了连接，则您可继续配置存档集成和统一的联系人存储等可选功能。</span><span class="sxs-lookup"><span data-stu-id="56122-137">If the test succeeds and connectivity has been established, you can then proceed to configure optional features such as archiving integration and the unified contact store.</span></span>
  

