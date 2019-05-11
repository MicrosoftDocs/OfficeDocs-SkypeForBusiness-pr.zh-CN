---
title: Skype 业务 Online 和 Exchange 服务器之间的集成
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: 配置 OAuth 业务 online 本地 Exchange 和 Skype 之间的身份验证使 Skype 功能支持中所述的业务和 Exchange 集成功能。
ms.openlocfilehash: c6a3819c9ec6ae0c207307a23f67bf04e4f07ac0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894237"
---
# <a name="configure-integration-between-skype-for-business-online-or-microsoft-teams-and-exchange-server"></a><span data-ttu-id="af1e4-103">配置 Skype for Business 联机或 Microsoft 团队和 Exchange 服务器之间的集成</span><span class="sxs-lookup"><span data-stu-id="af1e4-103">Configure Integration between Skype for Business Online or Microsoft Teams and Exchange Server</span></span> 

<span data-ttu-id="af1e4-104">配置 Exchange server 和 Skype 之间业务 online 的集成允许 Skype[功能支持](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)中所述的业务和 Exchange 集成功能。</span><span class="sxs-lookup"><span data-stu-id="af1e4-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="af1e4-105">本主题适用于通过 2019年与 Exchange Server 2013 的集成。</span><span class="sxs-lookup"><span data-stu-id="af1e4-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="af1e4-106">开始之前你需要了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="af1e4-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="af1e4-107">完成此任务的估计时间：15 分钟</span><span class="sxs-lookup"><span data-stu-id="af1e4-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="af1e4-108">在可以执行此过程或其他过程之前，你需要被分配适当的权限。</span><span class="sxs-lookup"><span data-stu-id="af1e4-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="af1e4-109">若要查看所需的权限，请参阅[and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511)主题。</span><span class="sxs-lookup"><span data-stu-id="af1e4-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="af1e4-110">有关可能适用于此主题中的过程的键盘快捷方式的信息，请参阅[Exchange 管理中心中的键盘快捷方式]( https://go.microsoft.com/fwlink/p/?LinkId=746512)。</span><span class="sxs-lookup"><span data-stu-id="af1e4-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="af1e4-111">配置 Exchange Server 和 O365 之间的集成</span><span class="sxs-lookup"><span data-stu-id="af1e4-111">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="af1e4-112">步骤 1： 配置 Exchange Server 和 O365 之间的 OAuth 身份验证</span><span class="sxs-lookup"><span data-stu-id="af1e4-112">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="af1e4-113">执行以下文章中的步骤：</span><span class="sxs-lookup"><span data-stu-id="af1e4-113">Perform the steps in the following article:</span></span>

[<span data-ttu-id="af1e4-114">配置 Exchange 和 Exchange Online 组织之间的 OAuth 身份验证</span><span class="sxs-lookup"><span data-stu-id="af1e4-114">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-or-teams-partner-application"></a><span data-ttu-id="af1e4-115">步骤 2： 业务联机或团队合作伙伴应用程序为 Skype 创建新邮件用户帐户</span><span class="sxs-lookup"><span data-stu-id="af1e4-115">Step 2: Create a new Mail User account for the Skype for Business Online or Teams Partner Application</span></span>

<span data-ttu-id="af1e4-116">Exchange 服务器上完成此步骤。</span><span class="sxs-lookup"><span data-stu-id="af1e4-116">This step is done on the Exchange server.</span></span> <span data-ttu-id="af1e4-117">它将创建一个邮件用户并为其分配合适的管理角色权限。</span><span class="sxs-lookup"><span data-stu-id="af1e4-117">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="af1e4-118">随后此用户将用于下一步骤。</span><span class="sxs-lookup"><span data-stu-id="af1e4-118">This account will then be used in the next step.</span></span>

<span data-ttu-id="af1e4-119">指定为 Exchange 组织已验证的域。</span><span class="sxs-lookup"><span data-stu-id="af1e4-119">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="af1e4-120">此域应为同一个域用作用于内部部署 Exchange 帐户的主 SMTP 域。</span><span class="sxs-lookup"><span data-stu-id="af1e4-120">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="af1e4-121">此域称作\<验证域\>在下面的过程。</span><span class="sxs-lookup"><span data-stu-id="af1e4-121">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="af1e4-122">此外， \<DomainControllerFQDN\>应域控制器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="af1e4-122">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

``` Powershell
$user = New-MailUser -Name O365-ApplicationAccount -ExternalEmailAddress O365-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="af1e4-123">此命令将在地址列表中隐藏新的邮件用户。</span><span class="sxs-lookup"><span data-stu-id="af1e4-123">This command will hide the new mail user from address lists.</span></span>

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="af1e4-124">接下来的两个命令将为这个新帐户分配 UserApplication 和 ArchiveApplication 管理角色。</span><span class="sxs-lookup"><span data-stu-id="af1e4-124">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online-or-teams"></a><span data-ttu-id="af1e4-125">步骤 3： 创建和启用合作伙伴应用程序的 Skype 业务联机或团队</span><span class="sxs-lookup"><span data-stu-id="af1e4-125">Step 3: Create and enable a Partner Application for Skype for Business Online or Teams</span></span>

<span data-ttu-id="af1e4-126">创建新的合作伙伴应用程序，并且将使用你刚刚创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="af1e4-126">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="af1e4-127">运行以下命令在 Exchange PowerShell 中，在您的内部部署 Exchange 组织。</span><span class="sxs-lookup"><span data-stu-id="af1e4-127">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="verify-your-success"></a><span data-ttu-id="af1e4-128">验证是否成功</span><span class="sxs-lookup"><span data-stu-id="af1e4-128">Verify your success</span></span>

<span data-ttu-id="af1e4-129">验证配置通过验证成功工作的一些功能正确。</span><span class="sxs-lookup"><span data-stu-id="af1e4-129">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="af1e4-130">确认 Outlook 日历委派的工作方式与 Exchange Server 2016 或 2019年邮箱介于这两个两个团队用户。</span><span class="sxs-lookup"><span data-stu-id="af1e4-130">Confirm Outlook Calendar delegation works betweeen two Teams users with Exchange Server 2016 or 2019 mailboxes.</span></span>

2. <span data-ttu-id="af1e4-131">确认在 Outlook 对话历史记录文件夹中的移动客户端的对话历史记录可见。</span><span class="sxs-lookup"><span data-stu-id="af1e4-131">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

<span data-ttu-id="af1e4-132">另外，查看您的通信。</span><span class="sxs-lookup"><span data-stu-id="af1e4-132">Alternately, look at your traffic.</span></span> <span data-ttu-id="af1e4-133">OAuth 握手流量是真正独特 （和看起来像基本身份验证），尤其是在领域，开始将看到如下所示的颁发者流量: 00000004-0000-0ff1-ce00-000000000000 @ (有时与 / 之前@ 符号)，正在传递令牌中。</span><span class="sxs-lookup"><span data-stu-id="af1e4-133">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="af1e4-134">您将看用户名和密码，即点的 OAuth。</span><span class="sxs-lookup"><span data-stu-id="af1e4-134">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="af1e4-135">但您将看到 Office 颁发者 –"4"在这种情况下是 Skype 商业 – 和您的订阅的领域。</span><span class="sxs-lookup"><span data-stu-id="af1e4-135">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="af1e4-136">如果希望以确保您成功使用 OAuth，请确保您知道要预期并知道流量应如下所示。</span><span class="sxs-lookup"><span data-stu-id="af1e4-136">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="af1e4-137">[下面是收获](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)是这样，下面是一个非常标准[的 Microsoft 应用程序中的 OAuth 流量示例](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)（真正有用读取，但它不使用刷新令牌），并且有可以让您看到到您 OAuth JWT (JSON 的 Fiddler 扩展Web 令牌）。</span><span class="sxs-lookup"><span data-stu-id="af1e4-137">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="af1e4-138">下面是[一个设置的示例](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/)中，但您可以使用任何要执行此过程的网络跟踪工具。</span><span class="sxs-lookup"><span data-stu-id="af1e4-138">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="af1e4-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="af1e4-139">Related topics</span></span>

[<span data-ttu-id="af1e4-140">配置 Exchange 和 Exchange Online 组织之间的 OAuth 身份验证</span><span class="sxs-lookup"><span data-stu-id="af1e4-140">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
