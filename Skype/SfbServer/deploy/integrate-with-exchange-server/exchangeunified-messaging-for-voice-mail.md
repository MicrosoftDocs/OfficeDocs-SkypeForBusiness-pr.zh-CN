---
title: 为 Skype for Business Server 语音邮件配置 Exchange Server 统一消息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/11/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 摘要： 配置 Exchange Server 统一消息的 Skype Business Server 语音邮件。
ms.openlocfilehash: 76a73c396657d98871a0238fe840e08016bccf13
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894342"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a><span data-ttu-id="98783-103">为 Skype for Business Server 语音邮件配置 Exchange Server 统一消息</span><span class="sxs-lookup"><span data-stu-id="98783-103">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>
 
<span data-ttu-id="98783-104">**摘要：** 配置 Exchange Server 统一消息的 Skype Business Server 语音邮件。</span><span class="sxs-lookup"><span data-stu-id="98783-104">**Summary:** Configure Exchange Server Unified Messaging for Skype for Business Server voice mail.</span></span>
  
<span data-ttu-id="98783-105">Skype 业务服务器，您可以在 Exchange Server 2016 或 Exchange Server 2013; 中存储的语音邮件然后，这些语音邮件消息将显示为用户的收件箱中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="98783-105">Skype for Business Server enables you to have voicemail messages stored in Exchange Server 2016 or Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> 

> [!NOTE]
> <span data-ttu-id="98783-106">Exchange 统一消息为以前已知不再可用在 Exchange 2019，但您可以仍使用电话系统中的记录的语音邮件，然后用户的 Exchange 邮箱中保留录制。</span><span class="sxs-lookup"><span data-stu-id="98783-106">Exchange Unified Messaging as previously known is no longer available in Exchange 2019, but you can still use Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="98783-107">有关详细信息，请参阅[规划语音邮件云服务](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="98783-107">See [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) for more information.</span></span>
  
<span data-ttu-id="98783-108">如果您已配置的业务服务器和 Exchange Server 2016 或 Exchange Server 2013 的 Skype 之间的服务器到服务器身份验证，则表明已准备好安装统一消息。</span><span class="sxs-lookup"><span data-stu-id="98783-108">If you have already configured server-to-server authentication between Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, then you are ready to setup unified messaging.</span></span> <span data-ttu-id="98783-109">为此，必须首先创建，并将新的统一消息拨号计划分配 Exchange 服务器上。</span><span class="sxs-lookup"><span data-stu-id="98783-109">To do so, you must first create and assign a new unified messaging dial plan on your Exchange Server.</span></span> <span data-ttu-id="98783-110">例如，（在 Exchange 命令行管理程序从运行） 这两个命令为 Exchange 配置新 3 位数字拨号计划：</span><span class="sxs-lookup"><span data-stu-id="98783-110">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="98783-111">在第一个命令，该示例的 VoIPSecurity 参数，并参数值"Secured"指示通过使用传输层安全性 (TLS) 进行加密的信号通道。</span><span class="sxs-lookup"><span data-stu-id="98783-111">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicates that the signaling channel is encrypted by using Transport Layer Security (TLS).</span></span> <span data-ttu-id="98783-112">URIType“SipName”指示将使用 SIP 协议发送和接收消息，CountryOrRegionCode 为 1 指示拨号计划适用于美国。</span><span class="sxs-lookup"><span data-stu-id="98783-112">The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>
  
<span data-ttu-id="98783-113">在第二个命令中，传递给 ConfiguredInCountryOrRegionGroups 参数的参数值指定可在此拨号计划中使用的国家/地区组。</span><span class="sxs-lookup"><span data-stu-id="98783-113">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="98783-114">参数值"Anywhere，\*，\*，\*"设置以下：</span><span class="sxs-lookup"><span data-stu-id="98783-114">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>
  
- <span data-ttu-id="98783-115">组名 ("Anywhere")</span><span class="sxs-lookup"><span data-stu-id="98783-115">Group name ("Anywhere")</span></span>
    
- <span data-ttu-id="98783-116">AllowedNumberString (\*，指示允许任意数字字符串的通配符)</span><span class="sxs-lookup"><span data-stu-id="98783-116">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>
    
- <span data-ttu-id="98783-117">DialNumberString (\*，指示允许任意已拨的号码的通配符)</span><span class="sxs-lookup"><span data-stu-id="98783-117">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>
    
- <span data-ttu-id="98783-118">TextComment (\*，指示允许任意文本命令的通配符)</span><span class="sxs-lookup"><span data-stu-id="98783-118">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>
    
> [!NOTE]
> <span data-ttu-id="98783-119">创建新的拨号计划也会创建一条默认邮箱策略。</span><span class="sxs-lookup"><span data-stu-id="98783-119">Creating a new dial plan will also create a Default Mailbox Policy.</span></span> 
  
<span data-ttu-id="98783-120">在创建和配置新拨号计划后，必须将新拨号计划添加至统一消息服务器中，然后修改该服务器的启动模式；特别需要指出的是，必须将启动模式设置为“双”。</span><span class="sxs-lookup"><span data-stu-id="98783-120">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="98783-121">您可以执行两项任务从 Exchange 命令行管理程序中：</span><span class="sxs-lookup"><span data-stu-id="98783-121">You can perform both of these tasks from within the Exchange Management Shell:</span></span>
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

<span data-ttu-id="98783-122">配置统一消息服务器后，接下来应该运行 Enable-exchangecertificate cmdlet，以确保您的 Exchange 证书于统一消息服务：</span><span class="sxs-lookup"><span data-stu-id="98783-122">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>
  
```
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

<span data-ttu-id="98783-p106">在正确分配证书后，接下来必须在统一消息服务器上停止并重新启动 MsExchangeUM 服务。只要更改启动模式，就必须停止并重新启动此服务。</span><span class="sxs-lookup"><span data-stu-id="98783-p106">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server. This service must be stopped and restarted any time you change the startup mode.</span></span>
  
<span data-ttu-id="98783-125">配置完统一消息服务器后，接下来可以配置 UM 调用路由器：</span><span class="sxs-lookup"><span data-stu-id="98783-125">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>
  
```
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

<span data-ttu-id="98783-126">由于启动模式已更改，因此您必须在承载 UM 调用路由器的计算机上停止并重新启动 MsExchangeUMCR 服务。</span><span class="sxs-lookup"><span data-stu-id="98783-126">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>
  
<span data-ttu-id="98783-p107">要完成统一消息设置，接下来需要创建 UM 邮箱策略，然后使用该策略为用户启用统一消息。可使用类似如下的命令创建邮箱策略：</span><span class="sxs-lookup"><span data-stu-id="98783-p107">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging. You can create a mailbox policy by using a command similar to this:</span></span>
  
```
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="98783-129">您可以使用类似如下的命令为用户启用统一消息：</span><span class="sxs-lookup"><span data-stu-id="98783-129">And you can enable a user for unified messaging by using a command similar to this:</span></span>
  
```
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

<span data-ttu-id="98783-p108">在前一个命令中，Extensions 参数表示用户的电话分机号。在该示例中，用户的分机号为 100。</span><span class="sxs-lookup"><span data-stu-id="98783-p108">In the preceding command, the Extensions parameter represents the telephone extension number for the user. In this example, the user has the extension number 100.</span></span>
  
<span data-ttu-id="98783-132">在启用其邮箱后，用户 kenmyer@litwareinc.com 应该能够使用 Exchange 统一消息。</span><span class="sxs-lookup"><span data-stu-id="98783-132">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="98783-133">您可以验证用户可以连接到 Exchange UM 由运行 Business Server 命令行管理程序中 Skype [Test-csexumconnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet:</span><span class="sxs-lookup"><span data-stu-id="98783-133">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet from within the Skype for Business Server Management Shell:</span></span>
  
```
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

<span data-ttu-id="98783-134">如果已为第二个用户启用了统一消息，则可使用 [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) cmdlet 验证第二个用户是否可为第一个用户留下语音邮件。</span><span class="sxs-lookup"><span data-stu-id="98783-134">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>
  
```
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a><span data-ttu-id="98783-135">配置 Microsoft Exchange Server 统一消息</span><span class="sxs-lookup"><span data-stu-id="98783-135">Configuring Unified Messaging on Microsoft Exchange Server</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="98783-136">如果您想要使用 Exchange 统一消息 (UM) 来提供呼叫应答、 Outlook Voice Access 或自动助理服务为企业语音用户，阅读[Plan for Business 的 Skype 中的 Exchange 统一消息集成](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)，并按本部分中的说明。</span><span class="sxs-lookup"><span data-stu-id="98783-136">If you want to use Exchange Unified Messaging (UM) to provide call answering, Outlook Voice Access, or auto-attendant services for Enterprise Voice users, read [Plan for Exchange Unified Messaging integration in Skype for Business](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md), and then follow the instructions in this section.</span></span> 

<span data-ttu-id="98783-137">若要配置 Exchange 统一消息 (UM) 与企业语音一起工作，您需要执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="98783-137">To configure Exchange Unified Messaging (UM) to work with Enterprise Voice, you’ll need to perform the following tasks:</span></span>

- <span data-ttu-id="98783-138">在运行 Exchange 统一消息 (UM) 服务的服务器上配置证书</span><span class="sxs-lookup"><span data-stu-id="98783-138">Configure certificates on the server running Exchange Unified Messaging (UM) services</span></span>
  > [!NOTE]
  > <span data-ttu-id="98783-139">将所有客户端访问和邮箱服务器添加到所有 UM SIP URI 拨号计划。</span><span class="sxs-lookup"><span data-stu-id="98783-139">Add all Client Access and Mailbox servers to all UM SIP URI dial plans.</span></span> <span data-ttu-id="98783-140">如果没有，出站呼叫路由不能作为预期。</span><span class="sxs-lookup"><span data-stu-id="98783-140">If not, outbound call routing won’t work as expected.</span></span> 
- <span data-ttu-id="98783-141">创建一个或多个 UM SIP URI 拨号计划，订阅者访问电话号码，以及根据需要，然后创建相应 L 拨号计划。</span><span class="sxs-lookup"><span data-stu-id="98783-141">Create one or more UM SIP URI dial plans, along with the subscriber access phone numbers, as needed, and then create corresponding L dial plans.</span></span>

- <span data-ttu-id="98783-142">使用 exchucutil.ps1 脚本执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="98783-142">Use the exchucutil.ps1 script to:</span></span>
    - <span data-ttu-id="98783-143">创建 UM IP 网关。</span><span class="sxs-lookup"><span data-stu-id="98783-143">Create UM IP gateways.</span></span>
    - <span data-ttu-id="98783-144">创建 UM 智能寻线。</span><span class="sxs-lookup"><span data-stu-id="98783-144">Create UM hunt groups.</span></span>
    - <span data-ttu-id="98783-145">授予 Skype Business Server 权限读取 UM Active Directory 域服务对象。</span><span class="sxs-lookup"><span data-stu-id="98783-145">Grant Skype for Business Server permission to read UM Active Directory Domain Services objects.</span></span>
- <span data-ttu-id="98783-146">创建 UM 自动助理对象。</span><span class="sxs-lookup"><span data-stu-id="98783-146">Create a UM auto-attendant object.</span></span>
- <span data-ttu-id="98783-147">创建订阅者访问对象。</span><span class="sxs-lookup"><span data-stu-id="98783-147">Create a subscriber access object.</span></span>
- <span data-ttu-id="98783-148">为创建一个 SIP URI 每个用户和将用户与 UM SIP URI 拨号计划。</span><span class="sxs-lookup"><span data-stu-id="98783-148">Create a SIP URI for each user and associating users with a UM SIP URI dial plan.</span></span>

### <a name="requirements-and-recommendations"></a><span data-ttu-id="98783-149">要求与建议</span><span class="sxs-lookup"><span data-stu-id="98783-149">Requirements and Recommendations</span></span>

<span data-ttu-id="98783-150">在开始之前，本节中的文档假定您已部署以下 Exchange 角色： 客户端访问和邮箱。</span><span class="sxs-lookup"><span data-stu-id="98783-150">Before you begin, the documentation in this section assumes that you have deployed the following Exchange roles: Client Access and Mailbox.</span></span> <span data-ttu-id="98783-151">在 Microsoft Exchange Server Exchange UM 作为服务运行在这些服务器上。</span><span class="sxs-lookup"><span data-stu-id="98783-151">In Microsoft Exchange Server, Exchange UM runs as a service on these servers.</span></span>

<span data-ttu-id="98783-152">此外请注意以下情况：</span><span class="sxs-lookup"><span data-stu-id="98783-152">Also note the following:</span></span>
- <span data-ttu-id="98783-153">如果 Exchange UM 安装在多个林中，则必须在每个 UM 林执行 Exchange Server 集成步骤。</span><span class="sxs-lookup"><span data-stu-id="98783-153">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest.</span></span> <span data-ttu-id="98783-154">此外，每个 UM 林必须配置为信任的林在其中部署了 Skype 业务服务器，则和 whichSkype 中的为林的部署业务服务器必须配置为信任每个 UM 林。</span><span class="sxs-lookup"><span data-stu-id="98783-154">In addition, each UM forest must be configured to trust the forest in which Skype for Business Server is deployed, and the forest in whichSkype for Business Server is deployed must be configured to trust each UM forest.</span></span>
- <span data-ttu-id="98783-155">在其中运行的统一消息服务，这两个 Exchange 服务器角色和业务服务器运行 Skype 的服务器上执行集成步骤。</span><span class="sxs-lookup"><span data-stu-id="98783-155">Integration steps are performed on both the Exchange Server roles where Unified Messaging services are running, and on the server running Skype for Business Server.</span></span> <span data-ttu-id="98783-156">执行的 Lync Server 2013 集成步骤之前，应执行的 Exchange Server 统一消息集成步骤。</span><span class="sxs-lookup"><span data-stu-id="98783-156">You should perform the Exchange Server Unified Messaging integration steps before you perform the Lync Server 2013 integration steps.</span></span>
  > [!NOTE]
  > <span data-ttu-id="98783-157">若要查看在哪些服务器上并且由哪些管理员角色执行哪些集成步骤，请参阅[集成的部署过程概述在本地统一消息和 Skype for Business](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="98783-157">To see which integration steps are performed on which servers and by which administrator roles, see  [Deployment process overview for integrating on-premises Unified Messaging and Skype for Business](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md).</span></span> 

<span data-ttu-id="98783-158">必须在每台服务器运行 Exchange UM 上提供以下工具：</span><span class="sxs-lookup"><span data-stu-id="98783-158">The following tools must be available on each server running Exchange UM:</span></span>
- <span data-ttu-id="98783-159">Exchange 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="98783-159">Exchange Management Shell</span></span>
- <span data-ttu-id="98783-160">脚本 exchucutil.ps1，它将执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="98783-160">The script exchucutil.ps1, which performs the following tasks:</span></span>
    - <span data-ttu-id="98783-161">业务服务器，请为每个 Skype 上创建一个 UM IP 网关。</span><span class="sxs-lookup"><span data-stu-id="98783-161">Creates a UM IP gateway for each Skype for Business Server.</span></span>
    - <span data-ttu-id="98783-162">创建每个网关的智能寻线组。</span><span class="sxs-lookup"><span data-stu-id="98783-162">Creates a hunt group for each gateway.</span></span> <span data-ttu-id="98783-163">每个智能寻线的引导标识符指定由前端池或 Standard Edition 服务器与网关相关联的 UM SIP URI 拨号计划。</span><span class="sxs-lookup"><span data-stu-id="98783-163">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Front End pool or Standard Edition server that is associated with the gateway.</span></span>
    - <span data-ttu-id="98783-164">授予 Skype 的业务 Server 读取 Active Directory 域服务中的 Exchange UM 对象的权限。</span><span class="sxs-lookup"><span data-stu-id="98783-164">Grants Skype for Business Server permission to read Exchange UM objects in Active Directory Domain Services.</span></span>



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a><span data-ttu-id="98783-165">Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1</span><span class="sxs-lookup"><span data-stu-id="98783-165">Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1</span></span> 

<span data-ttu-id="98783-166">当您正在为业务 Server 与 Exchange 统一消息 (UM) 集成 Microsoft Skype 时，您必须在命令行管理程序中运行 ExchUcUtil.ps1 脚本。</span><span class="sxs-lookup"><span data-stu-id="98783-166">When you’re integrating Microsoft Skype for Business Server with Exchange Unified Messaging (UM), you have to run the ExchUcUtil.ps1 script in the Shell.</span></span> <span data-ttu-id="98783-167">ExchUcUtil.ps1 脚本执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="98783-167">The ExchUcUtil.ps1 script does the following:</span></span>

- <span data-ttu-id="98783-168">为每个 Skype 业务服务器池创建一个 UM IP 网关。</span><span class="sxs-lookup"><span data-stu-id="98783-168">Creates a UM IP gateway for each Skype for Business Server pool.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="98783-169">ExchUcUtil.ps1 脚本将创建一个或多个 UM IP 网关。</span><span class="sxs-lookup"><span data-stu-id="98783-169">The ExchUcUtil.ps1 script creates one or more UM IP gateways.</span></span> <span data-ttu-id="98783-170">您必须禁用上创建脚本的一个网关除外的所有 UM IP 网关的传出呼叫。</span><span class="sxs-lookup"><span data-stu-id="98783-170">You must disable outgoing calls on all UM IP gateways except one gateway that the script created.</span></span> <span data-ttu-id="98783-171">这包括禁用上运行脚本之前创建的 UM IP 网关的传出呼叫。</span><span class="sxs-lookup"><span data-stu-id="98783-171">This includes disabling outgoing calls on UM IP gateways that were created before you ran the script.</span></span> 

- <span data-ttu-id="98783-172">创建 UM 智能寻每个 UM IP 网关。</span><span class="sxs-lookup"><span data-stu-id="98783-172">Creates a UM hunt group for each UM IP gateway.</span></span> <span data-ttu-id="98783-173">每个智能寻线的引导标识符指定 Skype 用于业务 Server 前端池或 Standard Edition server 的与 UM IP 网关相关联的 UM SIP URI 拨号计划。</span><span class="sxs-lookup"><span data-stu-id="98783-173">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Skype for Business Server Front End pool or Standard Edition server that’s associated with the UM IP gateway.</span></span>
- <span data-ttu-id="98783-174">业务 Server 读取 Active Directory UM 容器对象，例如 UM 拨号计划、 自动助理、 UM IP 网关和 UM 智能寻权限的授予 Skype。</span><span class="sxs-lookup"><span data-stu-id="98783-174">Grants Skype for Business Server permission to read Active Directory UM container objects such as UM dial plans, auto attendants, UM IP gateways, and UM hunt groups.</span></span>
  > [!IMPORTANT]
  > <span data-ttu-id="98783-175">必须将每个 UM 林配置为信任的林顺序 Skype 业务服务器部署，并在其中部署业务 Server 2013 的 Skype 林必须配置为信任每个 UM 林。</span><span class="sxs-lookup"><span data-stu-id="98783-175">Each UM forest must be configured to trust the forest in which Skype for Business Server is deployed, and the forest in which Skype for Business Server 2013 is deployed must be configured to trust each UM forest.</span></span> <span data-ttu-id="98783-176">如果 Exchange UM 安装在多个林中，则必须为每个 UM 林执行 Exchange Server 集成步骤或您必须指定 Skype Business Server 域。</span><span class="sxs-lookup"><span data-stu-id="98783-176">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest or you’ll have to specify the Skype for Business Server domain.</span></span> <span data-ttu-id="98783-177">例如，ExchUcUtil.ps1 – 林： <lync-域-控制器-fqdn>。</span><span class="sxs-lookup"><span data-stu-id="98783-177">For example, ExchUcUtil.ps1 –Forest:<lync-domain-controller-fqdn>.</span></span> 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a><span data-ttu-id="98783-178">使用命令行管理程序运行 ExchUcUtil.ps1 脚本</span><span class="sxs-lookup"><span data-stu-id="98783-178">Use the Shell to run the ExchUcUtil.ps1 script</span></span>

<span data-ttu-id="98783-179">在组织中的同一作为 Skype 的企业服务器拓扑中任何 Exchange 服务器上运行 ExchUcUtil.ps1 脚本。</span><span class="sxs-lookup"><span data-stu-id="98783-179">Run the ExchUcUtil.ps1 script on any Exchange server in your organization that’s in the same topology as Skype for Business Server.</span></span> <span data-ttu-id="98783-180">您可以从邮箱服务器使用命令行管理程序中运行该脚本，也可以运行的客户端访问服务器上使用远程 Windows PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="98783-180">You can run the script from a Mailbox server using the Shell or you can run the script using Remote Windows PowerShell on a Client Access server.</span></span> <span data-ttu-id="98783-181">如果您在组织中的客户端访问服务器上运行该脚本，客户端访问服务器将代理到组织中的邮箱服务器的远程 Windows PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="98783-181">If you run the script on a Client Access server in your organization, the Client Access server will proxy the Remote Windows PowerShell session to a Mailbox server in the organization.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="98783-182">ExchUcUtil.ps1 脚本将创建一个或多个 UM IP 网关。</span><span class="sxs-lookup"><span data-stu-id="98783-182">The ExchUcUtil.ps1 script creates one or more UM IP gateways.</span></span> <span data-ttu-id="98783-183">您必须禁用上创建脚本的一个网关除外的所有 UM IP 网关的传出呼叫。</span><span class="sxs-lookup"><span data-stu-id="98783-183">You must disable outgoing calls on all UM IP gateways except one gateway that the script created.</span></span> <span data-ttu-id="98783-184">这包括禁用上运行脚本之前创建的 UM IP 网关的传出呼叫。</span><span class="sxs-lookup"><span data-stu-id="98783-184">This includes disabling outgoing calls on UM IP gateways that were created before you ran the script.</span></span> <span data-ttu-id="98783-185">若要禁用 UM IP 网关的传出呼叫，请参阅禁用传出呼叫的 UM IP 网关。</span><span class="sxs-lookup"><span data-stu-id="98783-185">To disable outgoing calls on a UM IP gateway, see Disable outgoing calls on UM IP gateways.</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="98783-186">您必须具有 Exchange Organization Management 角色的权限或者是要运行脚本的 Exchange Organization Administrators 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="98783-186">You must have the permissions of the Exchange Organization Management role or be a member of the Exchange Organization Administrators security group to run the script.</span></span> 

1. <span data-ttu-id="98783-187">打开 Exchange Management Shell。</span><span class="sxs-lookup"><span data-stu-id="98783-187">Open the Exchange Management Shell.</span></span>
2. <span data-ttu-id="98783-188">在 C:\Windows\System32 提示符处，键入**cd\<驱动器 letter>:\Program Files\Microsoft\Exchange Server\V15\Scripts>。ExchUcUtil.ps1**，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="98783-188">At the C:\Windows\System32 prompt, type **cd \<drive letter>:\Program Files\Microsoft\Exchange Server\V15\Scripts>.ExchUcUtil.ps1**, and then press Enter.</span></span>

#### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="98783-189">您如何知道这样可行？</span><span class="sxs-lookup"><span data-stu-id="98783-189">How do you know this worked?</span></span>

<span data-ttu-id="98783-190">若要验证成功完成 ExchUcUtul.ps1 脚本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="98783-190">To verify that the ExchUcUtul.ps1 script completed successfully, do the following:</span></span>
- <span data-ttu-id="98783-191">使用 Get-umipgateway cmdlet 或 EAC 查看新 UM IP 网关或已创建的网关。</span><span class="sxs-lookup"><span data-stu-id="98783-191">Use the Get-UMIPGateway cmdlet or the EAC to view the new UM IP gateway or gateways that were created.</span></span>
- <span data-ttu-id="98783-192">使用 Get-umhuntgroup cmdlet 或 EAC 查看新 UM 智能寻线组或已创建的组。</span><span class="sxs-lookup"><span data-stu-id="98783-192">Use the Get-UMHuntGroup cmdlet or the EAC to view the new UM hunt group or groups that were created.</span></span>

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a><span data-ttu-id="98783-193">在运行 Exchange Server 统一消息的服务器上配置证书</span><span class="sxs-lookup"><span data-stu-id="98783-193">Configure certificates on the server running Exchange Server Unified Messaging</span></span>
 
<span data-ttu-id="98783-194">如果您已规划中的业务服务器规划文档中的 Skype 的 Exchange 统一消息集成中所述部署 Exchange 统一消息 (UM)，并且想要提供 Exchange UM 中的企业语音用户的功能您组织可以使用以下过程在运行 Exchange UM 服务器上配置证书。</span><span class="sxs-lookup"><span data-stu-id="98783-194">If you have deployed Exchange Unified Messaging (UM), as described in Planning for Exchange Unified Messaging integration in Skype for Business Server in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="98783-195">对于内部证书，运行 Skype 业务服务器的服务器和运行 Microsoft Exchange 的服务器必须拥有受信任相互受信任的根证书颁发机构证书。</span><span class="sxs-lookup"><span data-stu-id="98783-195">For internal certificates, both the servers running Skype for Business Server and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="98783-196">证书颁发机构 (CA) 可以是相同，或不同的证书颁发机构，只要服务器具有其受信任的根证书颁发机构证书存储中注册的证书颁发机构的根证书。</span><span class="sxs-lookup"><span data-stu-id="98783-196">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span> 

<span data-ttu-id="98783-197">Exchange Server 必须配置了服务器证书，才能连接到 Skype 业务服务器：</span><span class="sxs-lookup"><span data-stu-id="98783-197">The Exchange Server must be configured with a server certificate in order to connect to Skype for Business Server:</span></span>
1. <span data-ttu-id="98783-198">为 Exchange Server 下载 CA 证书。</span><span class="sxs-lookup"><span data-stu-id="98783-198">Download the CA certificate for the Exchange Server.</span></span>
2. <span data-ttu-id="98783-199">为 Exchange Server 安装 CA 证书。</span><span class="sxs-lookup"><span data-stu-id="98783-199">Install the CA certificate for the Exchange Server.</span></span>
3. <span data-ttu-id="98783-200">确认该 CA 的 Exchange 服务器的受信任的根 Ca 列表中。</span><span class="sxs-lookup"><span data-stu-id="98783-200">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>
4. <span data-ttu-id="98783-201">为 Exchange Server 创建证书请求并安装证书。</span><span class="sxs-lookup"><span data-stu-id="98783-201">Create a certificate request for the Exchange Server and install the certificate.</span></span> 
5. <span data-ttu-id="98783-202">为 Exchange Server 分配证书。</span><span class="sxs-lookup"><span data-stu-id="98783-202">Assign the certificate for the Exchange Server.</span></span>


<span data-ttu-id="98783-203">**若要下载 CA 证书：**</span><span class="sxs-lookup"><span data-stu-id="98783-203">**To download the CA certificate:**</span></span>

1. <span data-ttu-id="98783-204">在运行 Exchange UM 服务器上，单击**开始**，单击**运行**类型**http://\<颁发 CA Server>/certsrv 名称**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="98783-204">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server>/certsrv**, and then click **OK**.</span></span>
2. <span data-ttu-id="98783-205">在选择任务下，单击**下载 CA 证书、 证书链或 CRL**。</span><span class="sxs-lookup"><span data-stu-id="98783-205">Under Select a task, click **Download a CA certificate, certificate chain, or CRL**.</span></span>
3. <span data-ttu-id="98783-206">在**下载 CA 证书、 证书链或 CRL**下选择**Base 64 编码方式**，，然后单击**下载 CA 证书**。</span><span class="sxs-lookup"><span data-stu-id="98783-206">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click**Download CA certificate**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="98783-207">您还可以指定在此步骤的可分辨编码规则 (DER) 编码。</span><span class="sxs-lookup"><span data-stu-id="98783-207">You can also specify Distinguished Encoding Rules (DER) encoding at this step.</span></span> <span data-ttu-id="98783-208">如果选择 DER 编码，此过程的下一步的文件类型和在步骤 10 个**到安装 CA 证书**是.p7b 而不是非.cer。</span><span class="sxs-lookup"><span data-stu-id="98783-208">If you select DER encoding, the file type in the next step of this procedure and in step 10 of **To Install the CA certificate** is .p7b rather than .cer.</span></span> 
4. <span data-ttu-id="98783-209">在**文件下载**对话框中，单击**保存**，然后将文件保存到硬盘上，在服务器上。</span><span class="sxs-lookup"><span data-stu-id="98783-209">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server.</span></span> <span data-ttu-id="98783-210">（文件会为.cer 或.p7b 文件扩展名，具体取决于您在上一步中选择的编码。）</span><span class="sxs-lookup"><span data-stu-id="98783-210">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

<span data-ttu-id="98783-211">**安装 CA 证书：**</span><span class="sxs-lookup"><span data-stu-id="98783-211">**To install the CA certificate:**</span></span>

1. <span data-ttu-id="98783-212">在运行 Exchange UM 服务器上，通过单击**启动**、**运行**，在打开框中键入**mmc** ，然后单击**确定**打开 Microsoft 管理控制台 (MMC)。</span><span class="sxs-lookup"><span data-stu-id="98783-212">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the Open box, and then clicking **OK**.</span></span>
2. <span data-ttu-id="98783-213">在**文件**菜单中，单击**添加/删除管理单元**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="98783-213">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>
3. <span data-ttu-id="98783-214">在**添加独立管理单元**框中，单击**证书**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="98783-214">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>
4. <span data-ttu-id="98783-215">在“**证书管理单元**”对话框中，单击“**计算机帐户**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="98783-215">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>
5. <span data-ttu-id="98783-216">在**选择计算机**对话框中，确认**本地计算机: （运行这个控制台的计算机）** 复选框处于选中状态，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="98783-216">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>
6. <span data-ttu-id="98783-217">单击**关闭**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="98783-217">Click **Close**, and then click **OK**.</span></span> 
7. <span data-ttu-id="98783-218">在控制台树中，展开**证书 （本地计算机）**，展开**受信任的根证书颁发机构**，，然后单击**证书**。</span><span class="sxs-lookup"><span data-stu-id="98783-218">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>
8. <span data-ttu-id="98783-219">右键单击**证书**，单击**所有任务**，然后单击**导入**。</span><span class="sxs-lookup"><span data-stu-id="98783-219">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>
9. <span data-ttu-id="98783-220">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="98783-220">Click **Next**.</span></span> 
10. <span data-ttu-id="98783-221">单击**浏览**找到文件，，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="98783-221">Click **Browse** to locate the file, and then click **Next**.</span></span> <span data-ttu-id="98783-222">（该文件将具有为.cer 或.p7b 文件扩展名，具体取决于您的**下载 CA 证书**的步骤 3 中选择的编码。</span><span class="sxs-lookup"><span data-stu-id="98783-222">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>
11. <span data-ttu-id="98783-223">单击**将所有证书放**入下列存储。</span><span class="sxs-lookup"><span data-stu-id="98783-223">Click **Place All Certificates** in the following store.</span></span>
12. <span data-ttu-id="98783-224">单击**浏览**，然后选择**受信任的根证书颁发机构**。</span><span class="sxs-lookup"><span data-stu-id="98783-224">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span> 
13. <span data-ttu-id="98783-225">单击**下一步**来验证设置，，，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="98783-225">Click **Next** to verify the settings, and then click **Finish**.</span></span> 


<span data-ttu-id="98783-226">**验证 CA 位于受信任根 Ca 的列表：**</span><span class="sxs-lookup"><span data-stu-id="98783-226">**To verify that the CA is in the list of trusted root CAs:**</span></span>

1. <span data-ttu-id="98783-227">在运行 Exchange UM 服务器上，在 MMC 展开证书 （本地计算机）、 受信任根证书颁发机构，然后单击证书。</span><span class="sxs-lookup"><span data-stu-id="98783-227">On the server running Exchange UM, in MMC expand Certificates (Local Computer), expand Trusted Root Certification Authorities, and then click Certificates.</span></span>
2. <span data-ttu-id="98783-228">在细节窗格中，确认您的 CA 位于受信任的 Ca 列表。</span><span class="sxs-lookup"><span data-stu-id="98783-228">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>


