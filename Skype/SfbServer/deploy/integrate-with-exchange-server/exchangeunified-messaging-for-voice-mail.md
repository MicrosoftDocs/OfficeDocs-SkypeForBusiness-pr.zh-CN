---
title: 为 Skype for Business Server 语音邮件配置 Exchange Server 统一消息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: '摘要: 为 Skype for business 服务器语音邮件配置 Exchange Server 统一消息。'
ms.openlocfilehash: a1c83b4ec92e6e3b3d678d2d7e0a65f58fc9d6ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278183"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a><span data-ttu-id="349c9-103">为 Skype for Business Server 语音邮件配置 Exchange Server 统一消息</span><span class="sxs-lookup"><span data-stu-id="349c9-103">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>
 
<span data-ttu-id="349c9-104">**摘要:** 为 Skype for business 服务器语音邮件配置 Exchange Server 统一消息。</span><span class="sxs-lookup"><span data-stu-id="349c9-104">**Summary:** Configure Exchange Server Unified Messaging for Skype for Business Server voice mail.</span></span>
  
<span data-ttu-id="349c9-105">Skype for Business 服务器使你能够将语音邮件消息存储在 Exchange Server 2016 或 Exchange Server 2013 中;这些语音邮件将以电子邮件形式显示在用户的收件箱中。</span><span class="sxs-lookup"><span data-stu-id="349c9-105">Skype for Business Server enables you to have voicemail messages stored in Exchange Server 2016 or Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> 

> [!NOTE]
> <span data-ttu-id="349c9-106">Exchange 2019 中不再提供 exchange 统一消息, 但您仍然可以使用 "电话系统" 录制语音邮件, 然后将录制内容保留在用户的 Exchange 邮箱中。</span><span class="sxs-lookup"><span data-stu-id="349c9-106">Exchange Unified Messaging as previously known is no longer available in Exchange 2019, but you can still use Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="349c9-107">有关详细信息, 请参阅[规划云语音邮件服务](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="349c9-107">See [Plan Cloud Voicemail service](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) for more information.</span></span>
  
<span data-ttu-id="349c9-108">如果您已在 Skype for Business 服务器与 Exchange Server 2016 或 Exchange Server 2013 之间配置了服务器到服务器的身份验证, 则可以设置统一消息。</span><span class="sxs-lookup"><span data-stu-id="349c9-108">If you have already configured server-to-server authentication between Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, then you are ready to setup unified messaging.</span></span> <span data-ttu-id="349c9-109">若要执行此操作, 必须首先在 Exchange 服务器上创建并分配新的统一邮件拨号计划。</span><span class="sxs-lookup"><span data-stu-id="349c9-109">To do so, you must first create and assign a new unified messaging dial plan on your Exchange Server.</span></span> <span data-ttu-id="349c9-110">例如, 这两个命令 (从 Exchange 命令行管理程序中运行) 为 Exchange 配置新的3位数拨号计划:</span><span class="sxs-lookup"><span data-stu-id="349c9-110">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="349c9-111">在示例中的第一个命令中, VoIPSecurity 参数和参数值 "受保护" 表示使用传输层安全 (TLS) 加密信号信道。</span><span class="sxs-lookup"><span data-stu-id="349c9-111">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicates that the signaling channel is encrypted by using Transport Layer Security (TLS).</span></span> <span data-ttu-id="349c9-112">URIType“SipName”指示将使用 SIP 协议发送和接收消息，CountryOrRegionCode 为 1 指示拨号计划适用于美国。</span><span class="sxs-lookup"><span data-stu-id="349c9-112">The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>
  
<span data-ttu-id="349c9-113">在第二个命令中，传递给 ConfiguredInCountryOrRegionGroups 参数的参数值指定可在此拨号计划中使用的国家/地区组。</span><span class="sxs-lookup"><span data-stu-id="349c9-113">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="349c9-114">参数值 "Anywhere,\*,"\*,\*"设置以下各项:</span><span class="sxs-lookup"><span data-stu-id="349c9-114">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>
  
- <span data-ttu-id="349c9-115">组名 ("Anywhere")</span><span class="sxs-lookup"><span data-stu-id="349c9-115">Group name ("Anywhere")</span></span>
    
- <span data-ttu-id="349c9-116">AllowedNumberString (\*, 通配符表示允许使用任何数字字符串)</span><span class="sxs-lookup"><span data-stu-id="349c9-116">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>
    
- <span data-ttu-id="349c9-117">DialNumberString (\*, 表示允许任何拨出号码的通配符)</span><span class="sxs-lookup"><span data-stu-id="349c9-117">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>
    
- <span data-ttu-id="349c9-118">TextComment (\*, 表示允许使用任何文本命令的通配符)</span><span class="sxs-lookup"><span data-stu-id="349c9-118">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>
    
> [!NOTE]
> <span data-ttu-id="349c9-119">创建新的拨号计划也会创建一条默认邮箱策略。</span><span class="sxs-lookup"><span data-stu-id="349c9-119">Creating a new dial plan will also create a Default Mailbox Policy.</span></span> 
  
<span data-ttu-id="349c9-120">在创建和配置新拨号计划后，必须将新拨号计划添加至统一消息服务器中，然后修改该服务器的启动模式；特别需要指出的是，必须将启动模式设置为“双”。</span><span class="sxs-lookup"><span data-stu-id="349c9-120">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="349c9-121">你可以从 Exchange 管理外壳程序中执行这两个任务:</span><span class="sxs-lookup"><span data-stu-id="349c9-121">You can perform both of these tasks from within the Exchange Management Shell:</span></span>
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

<span data-ttu-id="349c9-122">配置统一消息服务器之后, 您应该下一步运行 ExchangeCertificate cmdlet 以确保 Exchange 证书应用于统一消息服务:</span><span class="sxs-lookup"><span data-stu-id="349c9-122">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>
  
```
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

<span data-ttu-id="349c9-p106">在正确分配证书后，接下来必须在统一消息服务器上停止并重新启动 MsExchangeUM 服务。只要更改启动模式，就必须停止并重新启动此服务。</span><span class="sxs-lookup"><span data-stu-id="349c9-p106">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server. This service must be stopped and restarted any time you change the startup mode.</span></span>
  
<span data-ttu-id="349c9-125">配置完统一消息服务器后，接下来可以配置 UM 调用路由器：</span><span class="sxs-lookup"><span data-stu-id="349c9-125">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>
  
```
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

<span data-ttu-id="349c9-126">由于启动模式已更改，因此您必须在承载 UM 调用路由器的计算机上停止并重新启动 MsExchangeUMCR 服务。</span><span class="sxs-lookup"><span data-stu-id="349c9-126">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>
  
<span data-ttu-id="349c9-p107">要完成统一消息设置，接下来需要创建 UM 邮箱策略，然后使用该策略为用户启用统一消息。可使用类似如下的命令创建邮箱策略：</span><span class="sxs-lookup"><span data-stu-id="349c9-p107">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging. You can create a mailbox policy by using a command similar to this:</span></span>
  
```
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="349c9-129">您可以使用类似如下的命令为用户启用统一消息：</span><span class="sxs-lookup"><span data-stu-id="349c9-129">And you can enable a user for unified messaging by using a command similar to this:</span></span>
  
```
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

<span data-ttu-id="349c9-p108">在前一个命令中，Extensions 参数表示用户的电话分机号。在该示例中，用户的分机号为 100。</span><span class="sxs-lookup"><span data-stu-id="349c9-p108">In the preceding command, the Extensions parameter represents the telephone extension number for the user. In this example, the user has the extension number 100.</span></span>
  
<span data-ttu-id="349c9-132">在启用其邮箱后，用户 kenmyer@litwareinc.com 应该能够使用 Exchange 统一消息。</span><span class="sxs-lookup"><span data-stu-id="349c9-132">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="349c9-133">你可以通过在 Skype for Business Server Management Shell 中运行[CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet 来验证用户是否可以连接到 Exchange UM:</span><span class="sxs-lookup"><span data-stu-id="349c9-133">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet from within the Skype for Business Server Management Shell:</span></span>
  
```
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

<span data-ttu-id="349c9-134">如果已为第二个用户启用了统一消息，则可使用 [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) cmdlet 验证第二个用户是否可为第一个用户留下语音邮件。</span><span class="sxs-lookup"><span data-stu-id="349c9-134">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>
  
```
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a><span data-ttu-id="349c9-135">在 Microsoft Exchange Server 上配置统一消息</span><span class="sxs-lookup"><span data-stu-id="349c9-135">Configuring Unified Messaging on Microsoft Exchange Server</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="349c9-136">如果要使用 Exchange 统一消息 (UM) 为企业语音用户提供呼叫应答、Outlook Voice Access 或自动助理服务, 请阅读[Skype For business 中 Exchange 统一消息集成的计划](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md), 然后按照本部分中的说明。</span><span class="sxs-lookup"><span data-stu-id="349c9-136">If you want to use Exchange Unified Messaging (UM) to provide call answering, Outlook Voice Access, or auto-attendant services for Enterprise Voice users, read [Plan for Exchange Unified Messaging integration in Skype for Business](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md), and then follow the instructions in this section.</span></span> 

<span data-ttu-id="349c9-137">要将 Exchange 统一消息 (UM) 配置为使用企业语音, 你需要执行以下任务:</span><span class="sxs-lookup"><span data-stu-id="349c9-137">To configure Exchange Unified Messaging (UM) to work with Enterprise Voice, you’ll need to perform the following tasks:</span></span>

- <span data-ttu-id="349c9-138">在运行 Exchange 统一消息 (UM) 服务的服务器上配置证书</span><span class="sxs-lookup"><span data-stu-id="349c9-138">Configure certificates on the server running Exchange Unified Messaging (UM) services</span></span>
  > [!NOTE]
  > <span data-ttu-id="349c9-139">将所有客户端访问和邮箱服务器添加到所有 UM SIP URI 拨号计划。</span><span class="sxs-lookup"><span data-stu-id="349c9-139">Add all Client Access and Mailbox servers to all UM SIP URI dial plans.</span></span> <span data-ttu-id="349c9-140">如果不是, 则出站呼叫路由不会按预期工作。</span><span class="sxs-lookup"><span data-stu-id="349c9-140">If not, outbound call routing won’t work as expected.</span></span> 
- <span data-ttu-id="349c9-141">创建一个或多个 UM SIP URI 拨号计划, 以及订阅者按需访问电话号码, 然后创建相应的 L 拨号计划。</span><span class="sxs-lookup"><span data-stu-id="349c9-141">Create one or more UM SIP URI dial plans, along with the subscriber access phone numbers, as needed, and then create corresponding L dial plans.</span></span>

- <span data-ttu-id="349c9-142">使用 exchucutil 脚本执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="349c9-142">Use the exchucutil.ps1 script to:</span></span>
    - <span data-ttu-id="349c9-143">创建 UM IP 网关。</span><span class="sxs-lookup"><span data-stu-id="349c9-143">Create UM IP gateways.</span></span>
    - <span data-ttu-id="349c9-144">创建 UM 查寻组。</span><span class="sxs-lookup"><span data-stu-id="349c9-144">Create UM hunt groups.</span></span>
    - <span data-ttu-id="349c9-145">授予 Skype for Business 服务器读取 UM Active Directory 域服务对象的权限。</span><span class="sxs-lookup"><span data-stu-id="349c9-145">Grant Skype for Business Server permission to read UM Active Directory Domain Services objects.</span></span>
- <span data-ttu-id="349c9-146">创建 UM 自动助理对象。</span><span class="sxs-lookup"><span data-stu-id="349c9-146">Create a UM auto-attendant object.</span></span>
- <span data-ttu-id="349c9-147">创建订阅者访问对象。</span><span class="sxs-lookup"><span data-stu-id="349c9-147">Create a subscriber access object.</span></span>
- <span data-ttu-id="349c9-148">为每个用户创建 SIP URI 并将用户与 UM SIP URI 拨号计划相关联。</span><span class="sxs-lookup"><span data-stu-id="349c9-148">Create a SIP URI for each user and associating users with a UM SIP URI dial plan.</span></span>

### <a name="requirements-and-recommendations"></a><span data-ttu-id="349c9-149">要求与建议</span><span class="sxs-lookup"><span data-stu-id="349c9-149">Requirements and Recommendations</span></span>

<span data-ttu-id="349c9-150">开始之前, 本部分中的文档假定你已部署以下 Exchange 角色: 客户端访问和邮箱。</span><span class="sxs-lookup"><span data-stu-id="349c9-150">Before you begin, the documentation in this section assumes that you have deployed the following Exchange roles: Client Access and Mailbox.</span></span> <span data-ttu-id="349c9-151">在 Microsoft Exchange Server 中, Exchange UM 在这些服务器上作为一项服务运行。</span><span class="sxs-lookup"><span data-stu-id="349c9-151">In Microsoft Exchange Server, Exchange UM runs as a service on these servers.</span></span>

<span data-ttu-id="349c9-152">另请注意以下事项:</span><span class="sxs-lookup"><span data-stu-id="349c9-152">Also note the following:</span></span>
- <span data-ttu-id="349c9-153">如果 Exchange UM 安装在多个林中, 则必须为每个 UM 林执行 Exchange Server 集成步骤。</span><span class="sxs-lookup"><span data-stu-id="349c9-153">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest.</span></span> <span data-ttu-id="349c9-154">此外, 必须将每个 UM 林配置为信任在其中部署 Skype for Business 服务器的林, 并且部署 whichSkype for Business Server 中的林必须配置为信任每个 UM 林。</span><span class="sxs-lookup"><span data-stu-id="349c9-154">In addition, each UM forest must be configured to trust the forest in which Skype for Business Server is deployed, and the forest in whichSkype for Business Server is deployed must be configured to trust each UM forest.</span></span>
- <span data-ttu-id="349c9-155">在运行统一消息服务的 Exchange 服务器角色上以及运行 Skype for business 服务器的服务器上执行集成步骤。</span><span class="sxs-lookup"><span data-stu-id="349c9-155">Integration steps are performed on both the Exchange Server roles where Unified Messaging services are running, and on the server running Skype for Business Server.</span></span> <span data-ttu-id="349c9-156">在执行 Lync Server 2013 集成步骤之前, 应执行 Exchange Server 统一消息集成步骤。</span><span class="sxs-lookup"><span data-stu-id="349c9-156">You should perform the Exchange Server Unified Messaging integration steps before you perform the Lync Server 2013 integration steps.</span></span>
  > [!NOTE]
  > <span data-ttu-id="349c9-157">若要查看在哪些服务器及其管理员角色上执行哪些集成步骤, 请参阅[集成本地统一消息和 Skype for business 的部署过程概述](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="349c9-157">To see which integration steps are performed on which servers and by which administrator roles, see  [Deployment process overview for integrating on-premises Unified Messaging and Skype for Business](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md).</span></span> 

<span data-ttu-id="349c9-158">以下工具必须在运行 Exchange UM 的每台服务器上可用:</span><span class="sxs-lookup"><span data-stu-id="349c9-158">The following tools must be available on each server running Exchange UM:</span></span>
- <span data-ttu-id="349c9-159">Exchange 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="349c9-159">Exchange Management Shell</span></span>
- <span data-ttu-id="349c9-160">脚本 exchucutil, 它执行以下任务:</span><span class="sxs-lookup"><span data-stu-id="349c9-160">The script exchucutil.ps1, which performs the following tasks:</span></span>
    - <span data-ttu-id="349c9-161">为每个 Skype for Business 服务器创建 UM IP 网关。</span><span class="sxs-lookup"><span data-stu-id="349c9-161">Creates a UM IP gateway for each Skype for Business Server.</span></span>
    - <span data-ttu-id="349c9-162">为每个网关创建一个查寻组。</span><span class="sxs-lookup"><span data-stu-id="349c9-162">Creates a hunt group for each gateway.</span></span> <span data-ttu-id="349c9-163">每个查寻组的引导标识符指定与网关相关联的前端池或标准版服务器使用的 UM SIP URI 拨号计划。</span><span class="sxs-lookup"><span data-stu-id="349c9-163">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Front End pool or Standard Edition server that is associated with the gateway.</span></span>
    - <span data-ttu-id="349c9-164">授予 Skype for Business 服务器在 Active Directory 域服务中读取 Exchange UM 对象的权限。</span><span class="sxs-lookup"><span data-stu-id="349c9-164">Grants Skype for Business Server permission to read Exchange UM objects in Active Directory Domain Services.</span></span>



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a><span data-ttu-id="349c9-165">Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1</span><span class="sxs-lookup"><span data-stu-id="349c9-165">Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1</span></span> 

<span data-ttu-id="349c9-166">将 Microsoft Skype for Business 服务器与 Exchange 统一消息 (UM) 集成时, 必须在 Shell 中运行 ExchUcUtil 脚本。</span><span class="sxs-lookup"><span data-stu-id="349c9-166">When you’re integrating Microsoft Skype for Business Server with Exchange Unified Messaging (UM), you have to run the ExchUcUtil.ps1 script in the Shell.</span></span> <span data-ttu-id="349c9-167">ExchUcUtil 脚本将执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="349c9-167">The ExchUcUtil.ps1 script does the following:</span></span>

- <span data-ttu-id="349c9-168">为每个 Skype for business 服务器池创建 UM IP 网关。</span><span class="sxs-lookup"><span data-stu-id="349c9-168">Creates a UM IP gateway for each Skype for Business Server pool.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="349c9-169">ExchUcUtil 脚本将创建一个或多个 UM IP 网关。</span><span class="sxs-lookup"><span data-stu-id="349c9-169">The ExchUcUtil.ps1 script creates one or more UM IP gateways.</span></span> <span data-ttu-id="349c9-170">您必须在所有 UM IP 网关 (该脚本创建的一个网关除外) 上禁用传出呼叫。</span><span class="sxs-lookup"><span data-stu-id="349c9-170">You must disable outgoing calls on all UM IP gateways except one gateway that the script created.</span></span> <span data-ttu-id="349c9-171">这包括在运行脚本之前创建的 UM IP 网关上禁用传出呼叫。</span><span class="sxs-lookup"><span data-stu-id="349c9-171">This includes disabling outgoing calls on UM IP gateways that were created before you ran the script.</span></span> 

- <span data-ttu-id="349c9-172">为每个 UM IP 网关创建一个 UM 查寻组。</span><span class="sxs-lookup"><span data-stu-id="349c9-172">Creates a UM hunt group for each UM IP gateway.</span></span> <span data-ttu-id="349c9-173">每个查寻组的引导标识符指定与 UM IP 网关相关联的 Skype for Business Server 前端池或标准版服务器使用的 UM SIP URI 拨号计划。</span><span class="sxs-lookup"><span data-stu-id="349c9-173">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Skype for Business Server Front End pool or Standard Edition server that’s associated with the UM IP gateway.</span></span>
- <span data-ttu-id="349c9-174">授予 Skype for Business 服务器读取 Active Directory UM 容器对象 (如 UM 拨号计划、自动助理、UM IP 网关和 UM 查寻组) 的权限。</span><span class="sxs-lookup"><span data-stu-id="349c9-174">Grants Skype for Business Server permission to read Active Directory UM container objects such as UM dial plans, auto attendants, UM IP gateways, and UM hunt groups.</span></span>
  > [!IMPORTANT]
  > <span data-ttu-id="349c9-175">必须将每个 UM 林配置为信任在其中部署 Skype for Business 服务器的林, 并且必须将部署 Skype for business Server 2013 的林配置为信任每个 UM 林。</span><span class="sxs-lookup"><span data-stu-id="349c9-175">Each UM forest must be configured to trust the forest in which Skype for Business Server is deployed, and the forest in which Skype for Business Server 2013 is deployed must be configured to trust each UM forest.</span></span> <span data-ttu-id="349c9-176">如果 Exchange UM 安装在多个林中, 则必须为每个 UM 林执行 Exchange Server 集成步骤, 否则你将必须指定 Skype for business 服务器域。</span><span class="sxs-lookup"><span data-stu-id="349c9-176">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest or you’ll have to specify the Skype for Business Server domain.</span></span> <span data-ttu-id="349c9-177">例如, ExchUcUtil-林: <lync-fqdn>。</span><span class="sxs-lookup"><span data-stu-id="349c9-177">For example, ExchUcUtil.ps1 –Forest:<lync-domain-controller-fqdn>.</span></span> 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a><span data-ttu-id="349c9-178">使用外壳运行 ExchUcUtil 脚本</span><span class="sxs-lookup"><span data-stu-id="349c9-178">Use the Shell to run the ExchUcUtil.ps1 script</span></span>

<span data-ttu-id="349c9-179">在组织中与 Skype for business 服务器处于同一拓扑的任何 Exchange 服务器上运行 ExchUcUtil 脚本。</span><span class="sxs-lookup"><span data-stu-id="349c9-179">Run the ExchUcUtil.ps1 script on any Exchange server in your organization that’s in the same topology as Skype for Business Server.</span></span> <span data-ttu-id="349c9-180">你可以使用 Shell 从邮箱服务器运行脚本, 也可以使用客户端访问服务器上的远程 Windows PowerShell 运行脚本。</span><span class="sxs-lookup"><span data-stu-id="349c9-180">You can run the script from a Mailbox server using the Shell or you can run the script using Remote Windows PowerShell on a Client Access server.</span></span> <span data-ttu-id="349c9-181">如果你在组织中的客户端访问服务器上运行脚本, 客户端访问服务器会将远程 Windows PowerShell 会话代理到组织中的邮箱服务器。</span><span class="sxs-lookup"><span data-stu-id="349c9-181">If you run the script on a Client Access server in your organization, the Client Access server will proxy the Remote Windows PowerShell session to a Mailbox server in the organization.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="349c9-182">ExchUcUtil 脚本将创建一个或多个 UM IP 网关。</span><span class="sxs-lookup"><span data-stu-id="349c9-182">The ExchUcUtil.ps1 script creates one or more UM IP gateways.</span></span> <span data-ttu-id="349c9-183">您必须在所有 UM IP 网关 (该脚本创建的一个网关除外) 上禁用传出呼叫。</span><span class="sxs-lookup"><span data-stu-id="349c9-183">You must disable outgoing calls on all UM IP gateways except one gateway that the script created.</span></span> <span data-ttu-id="349c9-184">这包括在运行脚本之前创建的 UM IP 网关上禁用传出呼叫。</span><span class="sxs-lookup"><span data-stu-id="349c9-184">This includes disabling outgoing calls on UM IP gateways that were created before you ran the script.</span></span> <span data-ttu-id="349c9-185">若要禁用 UM IP 网关的传出呼叫, 请参阅禁用 UM IP 网关上的传出呼叫。</span><span class="sxs-lookup"><span data-stu-id="349c9-185">To disable outgoing calls on a UM IP gateway, see Disable outgoing calls on UM IP gateways.</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="349c9-186">您必须具有 Exchange 组织管理角色的权限, 或者是 Exchange 组织管理员安全组的成员才能运行脚本。</span><span class="sxs-lookup"><span data-stu-id="349c9-186">You must have the permissions of the Exchange Organization Management role or be a member of the Exchange Organization Administrators security group to run the script.</span></span> 

1. <span data-ttu-id="349c9-187">打开 Exchange 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="349c9-187">Open the Exchange Management Shell.</span></span>
2. <span data-ttu-id="349c9-188">在 C:\Windows\System32 提示符处, 键入**cd \<drive letter>: \Program Files\Microsoft\Exchange Server\V15\Scripts>。ExchUcUtil**, 然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="349c9-188">At the C:\Windows\System32 prompt, type **cd \<drive letter>:\Program Files\Microsoft\Exchange Server\V15\Scripts>.ExchUcUtil.ps1**, and then press Enter.</span></span>

#### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="349c9-189">如何知道这是正常工作的？</span><span class="sxs-lookup"><span data-stu-id="349c9-189">How do you know this worked?</span></span>

<span data-ttu-id="349c9-190">若要验证 ExchUcUtul 脚本是否已成功完成, 请执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="349c9-190">To verify that the ExchUcUtul.ps1 script completed successfully, do the following:</span></span>
- <span data-ttu-id="349c9-191">使用 UMIPGateway cmdlet 或 EAC 查看已创建的新 UM IP 网关或网关。</span><span class="sxs-lookup"><span data-stu-id="349c9-191">Use the Get-UMIPGateway cmdlet or the EAC to view the new UM IP gateway or gateways that were created.</span></span>
- <span data-ttu-id="349c9-192">使用 UMHuntGroup cmdlet 或 EAC 查看已创建的新 UM 查寻组或组。</span><span class="sxs-lookup"><span data-stu-id="349c9-192">Use the Get-UMHuntGroup cmdlet or the EAC to view the new UM hunt group or groups that were created.</span></span>

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a><span data-ttu-id="349c9-193">在运行 Exchange Server 统一消息的服务器上配置证书</span><span class="sxs-lookup"><span data-stu-id="349c9-193">Configure certificates on the server running Exchange Server Unified Messaging</span></span>
 
<span data-ttu-id="349c9-194">如果已部署 Exchange 统一消息 (UM), 请参阅规划文档中的 Skype for Business 服务器中的 Exchange 统一消息集成规划中所述, 并希望向企业语音用户提供 Exchange UM 功能组织中, 你可以使用以下过程在运行 Exchange UM 的服务器上配置证书。</span><span class="sxs-lookup"><span data-stu-id="349c9-194">If you have deployed Exchange Unified Messaging (UM), as described in Planning for Exchange Unified Messaging integration in Skype for Business Server in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="349c9-195">对于内部证书, 运行 Skype for Business 服务器的服务器和运行 Microsoft Exchange 的服务器都必须具有相互信任的受信任根颁发机构证书。</span><span class="sxs-lookup"><span data-stu-id="349c9-195">For internal certificates, both the servers running Skype for Business Server and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="349c9-196">证书颁发机构 (CA) 既可以是相同的, 也可以是不同的证书颁发机构, 前提是服务器在其受信任的根颁发机构证书存储中注册了证书颁发机构的根证书。</span><span class="sxs-lookup"><span data-stu-id="349c9-196">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span> 

<span data-ttu-id="349c9-197">必须使用服务器证书配置 Exchange 服务器才能连接到 Skype for Business 服务器:</span><span class="sxs-lookup"><span data-stu-id="349c9-197">The Exchange Server must be configured with a server certificate in order to connect to Skype for Business Server:</span></span>
1. <span data-ttu-id="349c9-198">下载 Exchange 服务器的 CA 证书。</span><span class="sxs-lookup"><span data-stu-id="349c9-198">Download the CA certificate for the Exchange Server.</span></span>
2. <span data-ttu-id="349c9-199">为 Exchange 服务器安装 CA 证书。</span><span class="sxs-lookup"><span data-stu-id="349c9-199">Install the CA certificate for the Exchange Server.</span></span>
3. <span data-ttu-id="349c9-200">验证 CA 是否位于 Exchange 服务器的受信任根 Ca 列表中。</span><span class="sxs-lookup"><span data-stu-id="349c9-200">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>
4. <span data-ttu-id="349c9-201">为 Exchange 服务器创建证书请求并安装证书。</span><span class="sxs-lookup"><span data-stu-id="349c9-201">Create a certificate request for the Exchange Server and install the certificate.</span></span> 
5. <span data-ttu-id="349c9-202">为 Exchange Server 分配证书。</span><span class="sxs-lookup"><span data-stu-id="349c9-202">Assign the certificate for the Exchange Server.</span></span>


<span data-ttu-id="349c9-203">**要下载 CA 证书, 请执行以下操作:**</span><span class="sxs-lookup"><span data-stu-id="349c9-203">**To download the CA certificate:**</span></span>

1. <span data-ttu-id="349c9-204">在运行 Exchange UM 的服务器上, 单击 "**开始**", 单击 "**运行**", 键入**发证 CA Server>/certsrv 的 Http://\<名称**, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="349c9-204">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server>/certsrv**, and then click **OK**.</span></span>
2. <span data-ttu-id="349c9-205">在 "选择任务" 下, 单击 "**下载 CA 证书、证书链或 CRL**"。</span><span class="sxs-lookup"><span data-stu-id="349c9-205">Under Select a task, click **Download a CA certificate, certificate chain, or CRL**.</span></span>
3. <span data-ttu-id="349c9-206">在 "**下载 Ca 证书、证书链或 CRL**" 下, 选择 "**编码方法以基本 64**", 然后单击 "**下载 CA 证书**"。</span><span class="sxs-lookup"><span data-stu-id="349c9-206">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click**Download CA certificate**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="349c9-207">您还可以在此步骤中指定可分辨编码规则 (DER) 编码。</span><span class="sxs-lookup"><span data-stu-id="349c9-207">You can also specify Distinguished Encoding Rules (DER) encoding at this step.</span></span> <span data-ttu-id="349c9-208">如果选择 "DER 编码", 此过程的下一步中和**安装 CA 证书**的步骤10中的文件类型是. p7b 而不是 .cer。</span><span class="sxs-lookup"><span data-stu-id="349c9-208">If you select DER encoding, the file type in the next step of this procedure and in step 10 of **To Install the CA certificate** is .p7b rather than .cer.</span></span> 
4. <span data-ttu-id="349c9-209">在 "**文件下载**" 对话框中, 单击 "**保存**", 然后将文件保存到服务器上的硬盘。</span><span class="sxs-lookup"><span data-stu-id="349c9-209">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server.</span></span> <span data-ttu-id="349c9-210">(该文件将具有 .cer 或. p7b 文件扩展名, 具体取决于您在上一步中选择的编码。)</span><span class="sxs-lookup"><span data-stu-id="349c9-210">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

<span data-ttu-id="349c9-211">**要安装 CA 证书, 请执行以下操作:**</span><span class="sxs-lookup"><span data-stu-id="349c9-211">**To install the CA certificate:**</span></span>

1. <span data-ttu-id="349c9-212">在运行 Exchange UM 的服务器上, 依次单击 "**开始**" 和 "**运行**", 在 "打开" 框中键入**MMC** , 然后单击 **"确定"**, 打开 Microsoft 管理控制台 (MMC)。</span><span class="sxs-lookup"><span data-stu-id="349c9-212">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the Open box, and then clicking **OK**.</span></span>
2. <span data-ttu-id="349c9-213">在 "**文件**" 菜单上, 单击 "**添加/删除管理单元**", 然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="349c9-213">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>
3. <span data-ttu-id="349c9-214">在 "**添加独立的管理单元**" 框中, 单击 "**证书**", 然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="349c9-214">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>
4. <span data-ttu-id="349c9-215">在“**证书管理单元**”对话框中，单击“**计算机帐户**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="349c9-215">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>
5. <span data-ttu-id="349c9-216">在 "**选择计算机**" 对话框中, 验证 "**本地计算机: (运行此控制台的计算机)** " 复选框是否已选中, 然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="349c9-216">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>
6. <span data-ttu-id="349c9-217">单击 "**关闭**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="349c9-217">Click **Close**, and then click **OK**.</span></span> 
7. <span data-ttu-id="349c9-218">在控制台树中, 展开 "**证书 (本地计算机)**", 展开 "**受信任的根证书颁发机构**", 然后单击 "**证书**"。</span><span class="sxs-lookup"><span data-stu-id="349c9-218">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>
8. <span data-ttu-id="349c9-219">右键单击 "**证书**", 单击 "**所有任务**", 然后单击 "**导入**"。</span><span class="sxs-lookup"><span data-stu-id="349c9-219">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>
9. <span data-ttu-id="349c9-220">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="349c9-220">Click **Next**.</span></span> 
10. <span data-ttu-id="349c9-221">单击 "**浏览**" 找到文件, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="349c9-221">Click **Browse** to locate the file, and then click **Next**.</span></span> <span data-ttu-id="349c9-222">(该文件将具有 .cer 或. p7b 文件扩展名, 具体取决于**下载 CA 证书**的步骤3中所选的编码。</span><span class="sxs-lookup"><span data-stu-id="349c9-222">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>
11. <span data-ttu-id="349c9-223">单击 "**将所有证书放**入下列存储"。</span><span class="sxs-lookup"><span data-stu-id="349c9-223">Click **Place All Certificates** in the following store.</span></span>
12. <span data-ttu-id="349c9-224">单击 "**浏览**", 然后选择 "**受信任的根证书颁发机构**"。</span><span class="sxs-lookup"><span data-stu-id="349c9-224">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span> 
13. <span data-ttu-id="349c9-225">单击 "**下一步**" 以验证设置, 然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="349c9-225">Click **Next** to verify the settings, and then click **Finish**.</span></span> 


<span data-ttu-id="349c9-226">**若要验证 CA 是否位于受信任根 Ca 列表中, 请执行以下操作:**</span><span class="sxs-lookup"><span data-stu-id="349c9-226">**To verify that the CA is in the list of trusted root CAs:**</span></span>

1. <span data-ttu-id="349c9-227">在运行 Exchange UM 的服务器上, 在 MMC 中展开 "证书 (本地计算机)", 展开 "受信任的根证书颁发机构", 然后单击 "证书"。</span><span class="sxs-lookup"><span data-stu-id="349c9-227">On the server running Exchange UM, in MMC expand Certificates (Local Computer), expand Trusted Root Certification Authorities, and then click Certificates.</span></span>
2. <span data-ttu-id="349c9-228">在 "详细信息" 窗格中, 验证您的 CA 是否在受信任的 Ca 列表中。</span><span class="sxs-lookup"><span data-stu-id="349c9-228">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>


