---
title: 'Lync Server 2013: 配置 Microsoft Exchange Server 2013 适用于 Lync Server 的统一消息2013语音邮件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Exchange Server 2013 Unified Messaging for Lync Server 2013 voice mail
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49733573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e1d2bac84183e6cc274d6bb297c17401b3ff7f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a><span data-ttu-id="f7144-102">为 Microsoft Lync Server 2013 语音邮件配置 Microsoft Exchange Server 2013 统一消息</span><span class="sxs-lookup"><span data-stu-id="f7144-102">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7144-103">_**主题上次修改时间:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="f7144-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="f7144-104">Microsoft Lync Server 2013 允许你在 Microsoft Exchange Server 2013 中存储语音邮件消息;这些语音邮件将以电子邮件形式显示在用户的收件箱中。</span><span class="sxs-lookup"><span data-stu-id="f7144-104">Microsoft Lync Server 2013 enables you to have voicemail messages stored in Microsoft Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> <span data-ttu-id="f7144-105">在 Lync Server 和 Exchange 的2010版本中也可以找到此功能;但是, 由于 UM 呼叫路由器组件的推出, 配置此 "统一消息" 的过程在2013版本中已得到简化。</span><span class="sxs-lookup"><span data-stu-id="f7144-105">This capability was also found in the 2010 editions of Lync Server and Exchange; however, the process of configuring this "unified messaging" has been simplified in the 2013 editions thanks to the introduction of the UM Call Router component.</span></span> <span data-ttu-id="f7144-106">此组件安装在 Exchange 2013 客户端访问服务器上, 并且所有对 Exchange 统一消息 (如语音邮件) 的呼叫首先通过呼叫路由器路由, 然后被重定向到相应的邮箱服务器。</span><span class="sxs-lookup"><span data-stu-id="f7144-106">This component is installed on the Exchange 2013 Client Access server, and all calls to Exchange unified messaging (such as a voicemail) are first routed through the Call Router and then are redirected to the appropriate Mailbox server.</span></span>

<span data-ttu-id="f7144-107">如果您已在 Lync Server 2013 和 Exchange 2013 之间配置了服务器到服务器的身份验证, 则已准备好设置统一消息。</span><span class="sxs-lookup"><span data-stu-id="f7144-107">If you have already configured server-to-server authentication between Lync Server 2013 and Exchange 2013 then you are ready to setup unified messaging.</span></span> <span data-ttu-id="f7144-108">若要执行此操作, 必须首先在 Exchange 服务器上创建并分配新的统一邮件拨号计划。</span><span class="sxs-lookup"><span data-stu-id="f7144-108">To do so, you must first create and assign a new unified messaging dial plan on your Exchange server.</span></span> <span data-ttu-id="f7144-109">例如, 这两个命令 (从 Exchange 命令行管理程序中运行) 为 Exchange 配置新的3位数拨号计划:</span><span class="sxs-lookup"><span data-stu-id="f7144-109">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="f7144-p103">在该示例的第一个命令中，VoIPSecurity 参数和参数值“Secured”指示信号通道用传输层安全性 (TLS) 加密。URIType“SipName”指示将使用 SIP 协议发送和接收消息，CountryOrRegionCode 为 1 指示拨号计划适用于美国。</span><span class="sxs-lookup"><span data-stu-id="f7144-p103">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicate that the signaling channel is encrypted by using Transport Layer Security (TLS). The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>

<span data-ttu-id="f7144-112">在第二个命令中，传递给 ConfiguredInCountryOrRegionGroups 参数的参数值指定可在此拨号计划中使用的国家/地区组。</span><span class="sxs-lookup"><span data-stu-id="f7144-112">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="f7144-113">参数值 "Anywhere,\*,"\*,\*"设置以下各项:</span><span class="sxs-lookup"><span data-stu-id="f7144-113">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>

  - <span data-ttu-id="f7144-114">组名 ("Anywhere")</span><span class="sxs-lookup"><span data-stu-id="f7144-114">Group name ("Anywhere")</span></span>

  - <span data-ttu-id="f7144-115">AllowedNumberString (\*, 通配符表示允许使用任何数字字符串)</span><span class="sxs-lookup"><span data-stu-id="f7144-115">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>

  - <span data-ttu-id="f7144-116">DialNumberString (\*, 表示允许任何拨出号码的通配符)</span><span class="sxs-lookup"><span data-stu-id="f7144-116">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>

  - <span data-ttu-id="f7144-117">TextComment (\*, 表示允许使用任何文本命令的通配符)</span><span class="sxs-lookup"><span data-stu-id="f7144-117">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f7144-118">创建新的拨号计划也会创建一条默认邮箱策略。</span><span class="sxs-lookup"><span data-stu-id="f7144-118">Creating a new dial plan will also create a Default Mailbox Policy.</span></span>



</div>

<span data-ttu-id="f7144-119">在创建和配置新拨号计划后，必须将新拨号计划添加至统一消息服务器中，然后修改该服务器的启动模式；特别需要指出的是，必须将启动模式设置为“双”。</span><span class="sxs-lookup"><span data-stu-id="f7144-119">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="f7144-120">你可以从 Exchange 管理外壳程序中执行这两个任务:</span><span class="sxs-lookup"><span data-stu-id="f7144-120">You can perform both of these tasks from within the Exchange Management Shell:</span></span>

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

<span data-ttu-id="f7144-121">配置统一消息服务器之后, 您应该下一步运行 ExchangeCertificate cmdlet 以确保 Exchange 证书应用于统一消息服务:</span><span class="sxs-lookup"><span data-stu-id="f7144-121">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

<span data-ttu-id="f7144-p106">在正确分配证书后，接下来必须在统一消息服务器上停止并重新启动 MsExchangeUM 服务。只要更改启动模式，就必须停止并重新启动此服务。</span><span class="sxs-lookup"><span data-stu-id="f7144-p106">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server. This service must be stopped and restarted any time you change the startup mode.</span></span>

<span data-ttu-id="f7144-124">配置完统一消息服务器后，接下来可以配置 UM 调用路由器：</span><span class="sxs-lookup"><span data-stu-id="f7144-124">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

<span data-ttu-id="f7144-125">由于启动模式已更改，因此您必须在承载 UM 调用路由器的计算机上停止并重新启动 MsExchangeUMCR 服务。</span><span class="sxs-lookup"><span data-stu-id="f7144-125">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>

<span data-ttu-id="f7144-p107">要完成统一消息设置，接下来需要创建 UM 邮箱策略，然后使用该策略为用户启用统一消息。可使用类似如下的命令创建邮箱策略：</span><span class="sxs-lookup"><span data-stu-id="f7144-p107">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging. You can create a mailbox policy by using a command similar to this:</span></span>

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="f7144-128">您可以使用类似如下的命令为用户启用统一消息：</span><span class="sxs-lookup"><span data-stu-id="f7144-128">And you can enable a user for unified messaging by using a command similar to this:</span></span>

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

<span data-ttu-id="f7144-p108">在前一个命令中，Extensions 参数表示用户的电话分机号。在该示例中，用户的分机号为 100。</span><span class="sxs-lookup"><span data-stu-id="f7144-p108">In the preceding command, the Extensions parameter represents the telephone extension number for the user. In this example, the user has the extension number 100.</span></span>

<span data-ttu-id="f7144-131">在启用其邮箱后，用户 kenmyer@litwareinc.com 应该能够使用 Exchange 统一消息。</span><span class="sxs-lookup"><span data-stu-id="f7144-131">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="f7144-132">你可以通过在 Lync Server Management Shell 中运行[CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) cmdlet 来验证用户是否可以连接到 Exchange UM:</span><span class="sxs-lookup"><span data-stu-id="f7144-132">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) cmdlet from within the Lync Server Management Shell:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="f7144-133">如果已为第二个用户启用了统一消息，则可使用 [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) cmdlet 验证第二个用户是否可为第一个用户留下语音邮件。</span><span class="sxs-lookup"><span data-stu-id="f7144-133">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>

