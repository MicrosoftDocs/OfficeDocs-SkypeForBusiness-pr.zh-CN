---
title: 为 Microsoft Lync Server 2013 语音邮件配置 Microsoft Exchange Server 2013 统一消息
TOCTitle: 为 Microsoft Lync Server 2013 语音邮件配置 Microsoft Exchange Server 2013 统一消息
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49888321
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为 Microsoft Lync Server 2013 语音邮件配置 Microsoft Exchange Server 2013 统一消息

 

_**上一次修改主题：** 2013-02-04_

Microsoft Lync Server 2013 使您可在 Microsoft Exchange Server 2013 中存储语音邮件；然后，这些语音邮件将在用户的收件箱中显示为电子邮件。Lync Server 和 Exchange 的 2010 版中也提供了此功能；但是，由于引入了 UM 调用路由器组件，配置此“统一消息”的过程在 2013 版本中得到了简化。此组件安装在 Exchange 2013 客户端访问服务器上，对 Exchange 统一消息（如语音邮件）的所有调用都先通过呼叫路由器路由，然后重定向到适当的邮箱服务器。

如果已在 Lync Server 2013 和 Exchange 2013 之间配置服务器到服务器身份验证，则您已做好设置统一消息的准备。为此，必须先在 Exchange 服务器上创建和分配新的统一消息拨号计划。例如，这两个命令（从 Exchange 命令行管理程序中运行）将为 Exchange 配置一个新的 3 位拨号计划：

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

在该示例的第一个命令中，VoIPSecurity 参数和参数值“Secured”指示信号通道用传输层安全性 (TLS) 加密。URIType“SipName”指示将使用 SIP 协议发送和接收消息，CountryOrRegionCode 为 1 指示拨号计划适用于美国。

在第二个命令中，传递给 ConfiguredInCountryOrRegionGroups 参数的参数值指定可在此拨号计划中使用的国家/地区组。参数值“Anywhere,\*,\*,\*”设置以下内容：

  - 组名 ("Anywhere")

  - AllowedNumberString（\*，指示允许任意数字字符串的通配符）

  - DialNumberString（\*，指示允许任意已拨号码的通配符）

  - TextComment（\*，指示允许任意文本命令的通配符）

在创建和配置新拨号计划后，必须将新拨号计划添加至统一消息服务器中，然后修改该服务器的启动模式；特别需要指出的是，必须将启动模式设置为“双”。这两个任务均可在 Exchange 命令行管理程序中执行：

    Set-UmServer -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

在配置完统一消息服务器后，接下来应该运行 Enable-ExchangeCertificate cmdlet 来确保 Exchange 证书已应用于统一消息服务：

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

在正确分配证书后，接下来必须在统一消息服务器上停止并重新启动 MsExchangeUM 服务。只要更改启动模式，就必须停止并重新启动此服务。

配置完统一消息服务器后，接下来可以配置 UM 调用路由器：

    Set-CsUMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

由于启动模式已更改，因此您必须在承载 UM 调用路由器的计算机上停止并重新启动 MsExchangeUMCR 服务。

要完成统一消息设置，接下来需要创建 UM 邮箱策略，然后使用该策略为用户启用统一消息。可使用类似如下的命令创建邮箱策略：

    New-UMMailboxPolicy -ID "RedmondMailboxPolicy" -AllowedCountryOrRegionGroups "Anywhere"

您可以使用类似如下的命令为用户启用统一消息：

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

在前一个命令中，Extensions 参数表示用户的电话分机号。在该示例中，用户的分机号为 100。

在启用其邮箱后，用户 kenmyer@litwareinc.com 应该能够使用 Exchange 统一消息。可以通过在 Lync Server 命令行管理程序中运行 [Test-CsExUMConnectivity](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsExUMConnectivity) cmdlet 来验证该用户是否可以连接到 Exchange UM：

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

如果已为第二个用户启用了统一消息，则可使用 [Test-CsExUMVoiceMail](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsExUMVoiceMail) cmdlet 验证第二个用户是否可为第一个用户留下语音邮件。

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

