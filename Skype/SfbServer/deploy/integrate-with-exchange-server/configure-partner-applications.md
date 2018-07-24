---
title: 在 Skype for Business Server 2015 和 Exchange Server 中配置合作伙伴应用程序
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: 摘要： 配置 Exchange Server 2016 或 Exchange Server 2013 和 Skype 的业务服务器的服务器到服务器身份验证。
ms.openlocfilehash: f437b081466f837c012e0d2ddba8bea79d3ad445
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20973078"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a><span data-ttu-id="4b744-103">在 Skype for Business Server 和 Exchange Server 中配置合作伙伴应用程序</span><span class="sxs-lookup"><span data-stu-id="4b744-103">Configure partner applications in Skype for Business Server and Exchange Server</span></span>
 
<span data-ttu-id="4b744-104">**摘要：** 配置 Exchange Server 2016 或 Exchange Server 2013 和 Skype 业务服务器的服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="4b744-104">**Summary:** Configure server to server authentication for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="4b744-105">服务器到服务器身份验证通常要有两台需要相互通信的服务器以及一台第三方安全令牌服务器。</span><span class="sxs-lookup"><span data-stu-id="4b744-105">Server-to-server authentication usually requires two servers that need to communicate with one another and a third-party security token server.</span></span> <span data-ttu-id="4b744-106">如果服务器 A 和服务器 B 需要进行通信，然后两台这些服务器通常首先联系令牌的服务器和获取相互受信任安全令牌。</span><span class="sxs-lookup"><span data-stu-id="4b744-106">If Server A and Server B need to communicate, then both of those servers typically start by contacting a token server and obtaining a mutually-trusted security token.</span></span> <span data-ttu-id="4b744-107">之后服务器 A 会向服务器 B 提供安全令牌（反之亦然）作为保证真实性和可信度的方式。</span><span class="sxs-lookup"><span data-stu-id="4b744-107">Server A then presents that security token to Server B (and vice-versa) as a way to guarantee its authenticity and trustworthiness.</span></span>
  
<span data-ttu-id="4b744-108">但是，这是一个常规的规则。</span><span class="sxs-lookup"><span data-stu-id="4b744-108">However, that's a general rule.</span></span> <span data-ttu-id="4b744-109">为 Business Server、 Exchange Server 2016、 Exchange Server 2013 和 SharePoint Server 2013 的 Skype 不需要时相互; 通信使用第三方令牌服务器这是因为这些服务器产品可以创建可由另一接受无需单独的令牌服务器的安全令牌。</span><span class="sxs-lookup"><span data-stu-id="4b744-109">Skype for Business Server, Exchange Server 2016, Exchange Server 2013, and SharePoint Server 2013 do not need to use a third-party token server when communicating with one another; that's because these server products can create security tokens that can be accepted by one another without the need for a separate token server.</span></span> <span data-ttu-id="4b744-110">（此功能才 Skype Business Server、 Exchange Server 2016、 Exchange Server 2013 和 SharePoint Server 2013 中可用。</span><span class="sxs-lookup"><span data-stu-id="4b744-110">(This capability is only available in Skype for Business Server, Exchange Server 2016, Exchange Server 2013, and SharePoint Server 2013.</span></span> <span data-ttu-id="4b744-111">如果您需要设置与其他服务器的服务器到服务器身份验证，包括其他 Microsoft 服务器产品，则您将需要使用第三方令牌服务器完成此操作。）</span><span class="sxs-lookup"><span data-stu-id="4b744-111">If you need to set up server-to-server authentication with other servers, including other Microsoft server products, then you will need to do so by using a third-party token server.)</span></span>
  
<span data-ttu-id="4b744-112">若要设置 Skype 业务 server 和 Exchange 服务器之间的服务器到服务器身份验证，您必须执行两个操作： 1) 必须将适当的证书分配给每个服务器;以及 2） 必须配置每台服务器的其他服务器合作伙伴应用程序： 这意味着您必须配置 Skype 业务服务器进行 Exchange server 合作伙伴应用程序，您必须配置 Exchange Server 的 Skype 合作伙伴应用程序对于业务服务器。</span><span class="sxs-lookup"><span data-stu-id="4b744-112">In order to set up server-to-server authentication between Skype for Business Server and Exchange Server you must do two things: 1) you must assign the appropriate certificates to each server; and, 2) you must configure each server to be a partner application of the other server: that means you must configure Skype for Business Server to be a partner application for Exchange Server, and you must configure Exchange Server to be a partner application for Skype for Business Server.</span></span>
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a><span data-ttu-id="4b744-113">配置 Exchange server 合作伙伴应用程序的业务服务器的 Skype</span><span class="sxs-lookup"><span data-stu-id="4b744-113">Configuring Skype for Business Server to be a Partner Application for Exchange Server</span></span>

<span data-ttu-id="4b744-114">配置业务合作伙伴应用程序与 Exchange Server 2016 或 Exchange Server 2013 服务器的 Skype 的最简单方式是运行 Configure-EnterprisePartnerApplication.ps1 脚本随 Exchange Server 的 Windows PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="4b744-114">The easiest way to configure Skype for Business Server to be a partner application with Exchange Server 2016 or Exchange Server 2013 is to run the Configure-EnterprisePartnerApplication.ps1 script, a Windows PowerShell script that ships with Exchange Server.</span></span> <span data-ttu-id="4b744-115">若要运行此脚本，必须提供的 URL 的业务服务器身份验证元数据文档; Skype通常，这将业务服务器池跟后缀 /metadata/json/1 Skype 的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="4b744-115">To run this script, you must provide the URL for the Skype for Business Server authentication metadata document; this will typically be the fully qualified domain name of the Skype for Business Server pool followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="4b744-116">例如：</span><span class="sxs-lookup"><span data-stu-id="4b744-116">For example:</span></span>
  
```
https://atl-cs-001.litwareinc.com/metadata/json/1
```

<span data-ttu-id="4b744-117">若要配置 Skype 业务合作伙伴应用程序的服务器，打开 Exchange Management Shell 并运行类似如下的命令 （假定 c： 驱动器上安装了 Exchange，并使其使用的默认文件夹路径）：</span><span class="sxs-lookup"><span data-stu-id="4b744-117">To configure Skype for Business Server as a partner application, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

<span data-ttu-id="4b744-118">配置合作伙伴应用程序后建议您停止并在您的 Exchange 邮箱和客户端访问服务器上重新启动 Internet 信息服务 (IIS)。</span><span class="sxs-lookup"><span data-stu-id="4b744-118">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="4b744-119">您可使用类似于以下命令的命令重新启动 IIS，以下命令将重新启动计算机 atl-exchange-001 上的此服务：</span><span class="sxs-lookup"><span data-stu-id="4b744-119">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>
  
```
iisreset atl-exchange-001
```

<span data-ttu-id="4b744-120">在 Exchange 命令行管理程序中或从管理员权限下运行的任何其他命令窗口，可以从运行此命令。</span><span class="sxs-lookup"><span data-stu-id="4b744-120">This command can be run from within the Exchange Management Shell or from any other command window run under administrator privileges.</span></span>
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a><span data-ttu-id="4b744-121">配置 Exchange Server 的企业服务器的 Skype 合作伙伴应用程序</span><span class="sxs-lookup"><span data-stu-id="4b744-121">Configuring Exchange Server to be a Partner Application for Skype for Business Server</span></span>

<span data-ttu-id="4b744-122">配置 Skype 业务服务器进行 Exchange Server 2016 或 Exchange Server 2013 的合作伙伴应用程序后，您必须然后配置 Exchange Server 的企业服务器的 Skype 合作伙伴应用程序。</span><span class="sxs-lookup"><span data-stu-id="4b744-122">After you have configured Skype for Business Server to be a partner application for Exchange Server 2016 or Exchange Server 2013, you must then configure Exchange Server to be a partner application for Skype for Business Server.</span></span> <span data-ttu-id="4b744-123">这可以通过使用 Skype 业务 Server 命令行管理程序和 exchange; 指定身份验证元数据文档这通常是跟后缀 /metadata/json/1 Exchange 自动发现服务的 URI。</span><span class="sxs-lookup"><span data-stu-id="4b744-123">This can be done by using the Skype for Business Server Management Shell and specifying the authentication metadata document for Exchange; this will typically be the URI of the Exchange autodiscover service followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="4b744-124">例如：</span><span class="sxs-lookup"><span data-stu-id="4b744-124">For example:</span></span>
  
```
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

<span data-ttu-id="4b744-125">在业务服务器 Skype，通过[New-cspartnerapplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) cmdlet 配置合作伙伴应用程序。</span><span class="sxs-lookup"><span data-stu-id="4b744-125">In Skype for Business Server, partner applications are configured by using the [New-CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="4b744-126">除了指定 URI 的元数据应当还应用程序信任级别设置为 Full;这将使 Exchange 以表示本身和领域中的任何授权的用户。</span><span class="sxs-lookup"><span data-stu-id="4b744-126">In addition to specifying the metadata URI you should also set the application trust level to Full; this will allow Exchange to represent both itself and any authorized user in the realm.</span></span> <span data-ttu-id="4b744-127">例如：</span><span class="sxs-lookup"><span data-stu-id="4b744-127">For example:</span></span>
  
```
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

<span data-ttu-id="4b744-128">或者，您可以通过复制并修改脚本代码中的业务服务器到服务器身份验证文档 Skype 找到创建合作伙伴应用程序。</span><span class="sxs-lookup"><span data-stu-id="4b744-128">Alternatively, you can create a partner application by copying and modifying the script code found in the Skype for Business Server server-to-server authentication documentation.</span></span> <span data-ttu-id="4b744-129">请参阅[管理服务器到服务器身份验证 (OAuth) 和合作伙伴应用程序中的业务服务器 Skype](../../manage/authentication/server-to-server-and-partner-applications.md)文章的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4b744-129">See the [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) article for more information.</span></span>
  
<span data-ttu-id="4b744-130">如果您已成功配置这两个 Skype 的业务 Server 和 Exchange Server 合作伙伴应用程序，您还成功已配置的两个产品之间的服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="4b744-130">If you have successfully configured partner applications for both Skype for Business Server and Exchange Server, you have also successfully configured server-to-server authentication between the two products.</span></span> <span data-ttu-id="4b744-131">Skype 业务服务器包括 Windows PowerShell cmdlet、 [Test-csexstorageconnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps)可以验证已正确配置服务器到服务器身份验证和业务 Server 存储服务 Skype 可以连接到 Exchange 服务器。</span><span class="sxs-lookup"><span data-stu-id="4b744-131">Skype for Business Server includes a Windows PowerShell cmdlet, [Test-CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) which enables you to verify that server-to-server authentication has been correctly configured and that the Skype for Business Server Storage Service can connect to Exchange Server.</span></span> <span data-ttu-id="4b744-132">此 cmdlet 来连接到 Exchange Server 用户的邮箱，为该用户，写入到对话历史记录文件夹的项目，然后 （可选） 删除该项目达到此目的。</span><span class="sxs-lookup"><span data-stu-id="4b744-132">The cmdlet does this by connecting to the mailbox of an Exchange Server user, writing an item into the Conversation History folder for that user, and then (optionally) deleting that item.</span></span>
  
<span data-ttu-id="4b744-133">若要测试业务 Server 和 Exchange Server 的集成的 Skype，运行 Business Server 命令行管理程序从 Skype 类似于以下命令：</span><span class="sxs-lookup"><span data-stu-id="4b744-133">To test the integration of Skype for Business Server and Exchange Server, run a command similar to the following from the Skype for Business Server Management Shell:</span></span>
  
```
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="4b744-134">在上述命令中，SipUri 表示的用户的 Exchange 服务器; 上的帐户的 SIP 地址您的命令将失败这不是有效的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="4b744-134">In the preceding command, the SipUri represents the SIP address of a user with an account on Exchange Server; your command will fail in this is not a valid user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4b744-135">如果您收到 401 响应来自此 cmdlet 时，可能是因为 Exchange 的默认配置不包括对接受 Oauth 令牌的支持。</span><span class="sxs-lookup"><span data-stu-id="4b744-135">If you receive a 401 response from this cmdlet, it is probably because the default configuration for Exchange does not include support for accepting Oauth tokens.</span></span> <span data-ttu-id="4b744-136">有关在 Exchange 中使用 Oauth 的详细信息，请参阅[使用 SharePoint 2013 和 Skype 业务服务器配置 OAuth 身份验证](https://go.microsoft.com/fwlink/p/?LinkId=513103)。</span><span class="sxs-lookup"><span data-stu-id="4b744-136">For more information about using Oauth in Exchange, see [Configure OAuth authentication with SharePoint 2013 and Skype for Business Server](https://go.microsoft.com/fwlink/p/?LinkId=513103).</span></span> 
  
<span data-ttu-id="4b744-137">如果测试成功并且建立了连接，则您可继续配置存档集成和统一的联系人存储等可选功能。</span><span class="sxs-lookup"><span data-stu-id="4b744-137">If the test succeeds and connectivity has been established, you can then proceed to configure optional features such as archiving integration and the unified contact store.</span></span>