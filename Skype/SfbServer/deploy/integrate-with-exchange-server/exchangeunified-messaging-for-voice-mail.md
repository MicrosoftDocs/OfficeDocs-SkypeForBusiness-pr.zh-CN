---
title: 为 Skype for Business Server 2015 语音邮件配置 Exchange Server 统一消息
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/19/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 摘要： 配置统一消息 Exchange Server 的 Skype 业务服务器的语音邮件。
ms.openlocfilehash: 9f4cb3dcd43d8f6300a5fbe38bd37c40d48e8273
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-2015-voice-mail"></a><span data-ttu-id="8ce0a-103">为 Skype for Business Server 2015 语音邮件配置 Exchange Server 统一消息</span><span class="sxs-lookup"><span data-stu-id="8ce0a-103">Configure Exchange Server Unified Messaging for Skype for Business Server 2015 voice mail</span></span>
 
<span data-ttu-id="8ce0a-104">**摘要：**配置统一邮件的 Exchange Server 的 Skype 业务服务器的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="8ce0a-104">**Summary:** Configure Exchange Server Unified Messaging for Skype for Business Server voice mail.</span></span>
  
<span data-ttu-id="8ce0a-105">业务服务器 2015年的 Skype，您可以存储在 Exchange Server 2016年或 Exchange Server 2013; 语音邮件消息然后，这些语音邮件消息将显示为用户的收件箱中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8ce0a-105">Skype for Business Server 2015 enables you to have voicemail messages stored in Exchange Server 2016 or Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> 
  
<span data-ttu-id="8ce0a-106">如果您已经配置了业务服务器 2015年和 Exchange Server 2016年或 Exchange Server 2013 Skype 之间的服务器到服务器进行身份验证，您已准备好安装统一邮件。</span><span class="sxs-lookup"><span data-stu-id="8ce0a-106">If you have already configured server-to-server authentication between Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you are ready to setup unified messaging.</span></span> <span data-ttu-id="8ce0a-107">若要执行此操作，必须首先创建并分配一个新的统一邮件拨号计划上 Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="8ce0a-107">To do so, you must first create and assign a new unified messaging dial plan on your Exchange Server.</span></span> <span data-ttu-id="8ce0a-108">例如，（从内运行 Exchange 管理外壳） 这两个命令 exchange 配置新的 3 位数字拨号计划：</span><span class="sxs-lookup"><span data-stu-id="8ce0a-108">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="8ce0a-p102">在该示例的第一个命令中，VoIPSecurity 参数和参数值“Secured”指示信号通道用传输层安全性 (TLS) 加密。URIType“SipName”指示将使用 SIP 协议发送和接收消息，CountryOrRegionCode 为 1 指示拨号计划适用于美国。</span><span class="sxs-lookup"><span data-stu-id="8ce0a-p102">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicate that the signaling channel is encrypted by using Transport Layer Security (TLS). The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>
  
<span data-ttu-id="8ce0a-111">在第二个命令中，传递给 ConfiguredInCountryOrRegionGroups 参数的参数值指定可在此拨号计划中使用的国家/地区组。</span><span class="sxs-lookup"><span data-stu-id="8ce0a-111">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="8ce0a-112">参数值"，\*，\*，\*"设置如下：</span><span class="sxs-lookup"><span data-stu-id="8ce0a-112">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>
  
- <span data-ttu-id="8ce0a-113">组名 ("Anywhere")</span><span class="sxs-lookup"><span data-stu-id="8ce0a-113">Group name ("Anywhere")</span></span>
    
- <span data-ttu-id="8ce0a-114">AllowedNumberString (\*，通配符字符，指示允许任何数字字符串)</span><span class="sxs-lookup"><span data-stu-id="8ce0a-114">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>
    
- <span data-ttu-id="8ce0a-115">DialNumberString (\*，表明任何拨叫的号码允许通配符)</span><span class="sxs-lookup"><span data-stu-id="8ce0a-115">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>
    
- <span data-ttu-id="8ce0a-116">TextComment (\*，通配符字符，指示允许任何文本命令)</span><span class="sxs-lookup"><span data-stu-id="8ce0a-116">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>
    
> [!NOTE]
> <span data-ttu-id="8ce0a-117">创建新的拨号计划也会创建一条默认邮箱策略。</span><span class="sxs-lookup"><span data-stu-id="8ce0a-117">Creating a new dial plan will also create a Default Mailbox Policy.</span></span> 
  
<span data-ttu-id="8ce0a-118">在创建和配置新拨号计划后，必须将新拨号计划添加至统一消息服务器中，然后修改该服务器的启动模式；特别需要指出的是，必须将启动模式设置为“双”。</span><span class="sxs-lookup"><span data-stu-id="8ce0a-118">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="8ce0a-119">您可以执行两项任务从 Exchange 管理外壳程序中：</span><span class="sxs-lookup"><span data-stu-id="8ce0a-119">You can perform both of these tasks from within the Exchange Management Shell:</span></span>
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

<span data-ttu-id="8ce0a-120">配置统一消息服务器后下一步应该运行启用 ExchangeCertificate cmdlet 以确保交换证书用于统一邮件服务：</span><span class="sxs-lookup"><span data-stu-id="8ce0a-120">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>
  
```
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

<span data-ttu-id="8ce0a-p105">在正确分配证书后，接下来必须在统一消息服务器上停止并重新启动 MsExchangeUM 服务。只要更改启动模式，就必须停止并重新启动此服务。</span><span class="sxs-lookup"><span data-stu-id="8ce0a-p105">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server. This service must be stopped and restarted any time you change the startup mode.</span></span>
  
<span data-ttu-id="8ce0a-123">配置完统一消息服务器后，接下来可以配置 UM 调用路由器：</span><span class="sxs-lookup"><span data-stu-id="8ce0a-123">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>
  
```
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

<span data-ttu-id="8ce0a-124">由于启动模式已更改，因此您必须在承载 UM 调用路由器的计算机上停止并重新启动 MsExchangeUMCR 服务。</span><span class="sxs-lookup"><span data-stu-id="8ce0a-124">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>
  
<span data-ttu-id="8ce0a-p106">要完成统一消息设置，接下来需要创建 UM 邮箱策略，然后使用该策略为用户启用统一消息。可使用类似如下的命令创建邮箱策略：</span><span class="sxs-lookup"><span data-stu-id="8ce0a-p106">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging. You can create a mailbox policy by using a command similar to this:</span></span>
  
```
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="8ce0a-127">您可以使用类似如下的命令为用户启用统一消息：</span><span class="sxs-lookup"><span data-stu-id="8ce0a-127">And you can enable a user for unified messaging by using a command similar to this:</span></span>
  
```
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

<span data-ttu-id="8ce0a-p107">在前一个命令中，Extensions 参数表示用户的电话分机号。在该示例中，用户的分机号为 100。</span><span class="sxs-lookup"><span data-stu-id="8ce0a-p107">In the preceding command, the Extensions parameter represents the telephone extension number for the user. In this example, the user has the extension number 100.</span></span>
  
<span data-ttu-id="8ce0a-130">在启用其邮箱后，用户 kenmyer@litwareinc.com 应该能够使用 Exchange 统一消息。</span><span class="sxs-lookup"><span data-stu-id="8ce0a-130">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="8ce0a-131">您可以验证用户可以连接到 UM 交换通过为业务服务器管理外壳程序运行[测试 CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet 从 Skype 内：</span><span class="sxs-lookup"><span data-stu-id="8ce0a-131">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet from within the Skype for Business Server Management Shell:</span></span>
  
```
$credential = Get-Credential "litwareinc\kenmyer"

Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

<span data-ttu-id="8ce0a-132">如果您已启用统一消息的第二个用户可以使用[测试 CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) cmdlet 以验证此第二个用户可以留下语音邮件消息的第一个用户。</span><span class="sxs-lookup"><span data-stu-id="8ce0a-132">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>
  
```
$credential = Get-Credential "litwareinc\pilar"

Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```


