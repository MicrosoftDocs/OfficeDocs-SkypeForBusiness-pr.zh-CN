---
title: Lync Server 2013：配置 Microsoft Exchange Server 2013 适用于 Lync Server 的统一消息2013语音邮件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Exchange Server 2013 Unified Messaging for Lync Server 2013 voice mail
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49733573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 367f4cc517771f51d7a1452293ad9803075d285f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755926"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a>为 Microsoft Lync Server 2013 语音邮件配置 Microsoft Exchange Server 2013 统一消息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-04_

Microsoft Lync Server 2013 允许你在 Microsoft Exchange Server 2013 中存储语音邮件消息;这些语音邮件将以电子邮件形式显示在用户的收件箱中。 在 Lync Server 和 Exchange 的2010版本中也可以找到此功能;但是，由于 UM 呼叫路由器组件的推出，配置此 "统一消息" 的过程在2013版本中已得到简化。 此组件安装在 Exchange 2013 客户端访问服务器上，并且所有对 Exchange 统一消息（如语音邮件）的呼叫首先通过呼叫路由器路由，然后被重定向到相应的邮箱服务器。

如果您已在 Lync Server 2013 和 Exchange 2013 之间配置了服务器到服务器的身份验证，则已准备好设置统一消息。 若要执行此操作，必须首先在 Exchange 服务器上创建并分配新的统一邮件拨号计划。 例如，这两个命令（从 Exchange 命令行管理程序中运行）为 Exchange 配置新的3位数拨号计划：

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

在该示例的第一个命令中，VoIPSecurity 参数和参数值“Secured”指示信号通道用传输层安全性 (TLS) 加密。URIType“SipName”指示将使用 SIP 协议发送和接收消息，CountryOrRegionCode 为 1 指示拨号计划适用于美国。

在第二个命令中，传递给 ConfiguredInCountryOrRegionGroups 参数的参数值指定可在此拨号计划中使用的国家/地区组。 参数值 "Anywhere，\*，"\*，\*"设置以下各项：

  - 组名 ("Anywhere")

  - AllowedNumberString （\*，通配符表示允许使用任何数字字符串）

  - DialNumberString （\*，表示允许任何拨出号码的通配符）

  - TextComment （\*，表示允许使用任何文本命令的通配符）

<div>


> [!NOTE]  
> 创建新的拨号计划也会创建一条默认邮箱策略。



</div>

在创建和配置新拨号计划后，必须将新拨号计划添加至统一消息服务器中，然后修改该服务器的启动模式；特别需要指出的是，必须将启动模式设置为“双”。 你可以从 Exchange 管理外壳程序中执行这两个任务：

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

配置统一消息服务器之后，您应该下一步运行 ExchangeCertificate cmdlet 以确保 Exchange 证书应用于统一消息服务：

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

在正确分配证书后，接下来必须在统一消息服务器上停止并重新启动 MsExchangeUM 服务。只要更改启动模式，就必须停止并重新启动此服务。

配置完统一消息服务器后，接下来可以配置 UM 调用路由器：

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

由于启动模式已更改，因此您必须在承载 UM 调用路由器的计算机上停止并重新启动 MsExchangeUMCR 服务。

要完成统一消息设置，接下来需要创建 UM 邮箱策略，然后使用该策略为用户启用统一消息。可使用类似如下的命令创建邮箱策略：

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

您可以使用类似如下的命令为用户启用统一消息：

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

在前一个命令中，Extensions 参数表示用户的电话分机号。在该示例中，用户的分机号为 100。

在启用其邮箱后，用户 kenmyer@litwareinc.com 应该能够使用 Exchange 统一消息。 你可以通过在 Lync Server Management Shell 中运行[CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) cmdlet 来验证用户是否可以连接到 Exchange UM：

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

如果已为第二个用户启用了统一消息，则可使用 [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) cmdlet 验证第二个用户是否可为第一个用户留下语音邮件。

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>

