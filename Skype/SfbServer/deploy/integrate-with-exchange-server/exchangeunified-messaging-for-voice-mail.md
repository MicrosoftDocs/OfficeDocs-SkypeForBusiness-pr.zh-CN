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
description: 摘要： 配置 Exchange Server 统一消息的 Skype Business Server 语音邮件。
ms.openlocfilehash: 5cc8825e04e348004f4105d483eb7a92dd0e5c60
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569220"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-2015-voice-mail"></a>为 Skype for Business Server 2015 语音邮件配置 Exchange Server 统一消息
 
**摘要：** 配置 Exchange Server 统一消息的 Skype Business Server 语音邮件。
  
业务服务器 2015年的 Skype，您可以在 Exchange Server 2016 或 Exchange Server 2013; 中存储的语音邮件然后，这些语音邮件消息将显示为用户的收件箱中的电子邮件。 
  
如果您已配置 Skype 业务服务器 2015年和 Exchange Server 2016 或 Exchange Server 2013 之间的服务器到服务器身份验证，则表明已准备好安装统一消息。 为此，必须首先创建，并将新的统一消息拨号计划分配 Exchange 服务器上。 例如，（在 Exchange 命令行管理程序从运行） 这两个命令为 Exchange 配置新 3 位数字拨号计划：
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

在该示例的第一个命令中，VoIPSecurity 参数和参数值“Secured”指示信号通道用传输层安全性 (TLS) 加密。URIType“SipName”指示将使用 SIP 协议发送和接收消息，CountryOrRegionCode 为 1 指示拨号计划适用于美国。
  
在第二个命令中，传递给 ConfiguredInCountryOrRegionGroups 参数的参数值指定可在此拨号计划中使用的国家/地区组。 参数值"Anywhere，\*，\*，\*"设置以下：
  
- 组名 ("Anywhere")
    
- AllowedNumberString (\*，指示允许任意数字字符串的通配符)
    
- DialNumberString (\*，指示允许任意已拨的号码的通配符)
    
- TextComment (\*，指示允许任意文本命令的通配符)
    
> [!NOTE]
> 创建新的拨号计划也会创建一条默认邮箱策略。 
  
在创建和配置新拨号计划后，必须将新拨号计划添加至统一消息服务器中，然后修改该服务器的启动模式；特别需要指出的是，必须将启动模式设置为“双”。 您可以执行两项任务从 Exchange 命令行管理程序中：
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

配置统一消息服务器后，接下来应该运行 Enable-exchangecertificate cmdlet，以确保您的 Exchange 证书于统一消息服务：
  
```
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

在正确分配证书后，接下来必须在统一消息服务器上停止并重新启动 MsExchangeUM 服务。只要更改启动模式，就必须停止并重新启动此服务。
  
配置完统一消息服务器后，接下来可以配置 UM 调用路由器：
  
```
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

由于启动模式已更改，因此您必须在承载 UM 调用路由器的计算机上停止并重新启动 MsExchangeUMCR 服务。
  
要完成统一消息设置，接下来需要创建 UM 邮箱策略，然后使用该策略为用户启用统一消息。可使用类似如下的命令创建邮箱策略：
  
```
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

您可以使用类似如下的命令为用户启用统一消息：
  
```
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

在前一个命令中，Extensions 参数表示用户的电话分机号。在该示例中，用户的分机号为 100。
  
在启用其邮箱后，用户 kenmyer@litwareinc.com 应该能够使用 Exchange 统一消息。 您可以验证用户可以连接到 Exchange UM 由运行 Business Server 命令行管理程序中 Skype [Test-csexumconnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet:
  
```
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

如果您有第二个已启用统一消息的用户可以使用[Test-csexumvoicemail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) cmdlet 以确认此第二个用户都可以离开的第一个用户的语音邮件消息。
  
```
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```