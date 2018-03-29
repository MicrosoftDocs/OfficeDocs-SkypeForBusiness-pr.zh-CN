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
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-2015-voice-mail"></a>为 Skype for Business Server 2015 语音邮件配置 Exchange Server 统一消息
 
**摘要：**配置统一邮件的 Exchange Server 的 Skype 业务服务器的语音邮件。
  
业务服务器 2015年的 Skype，您可以存储在 Exchange Server 2016年或 Exchange Server 2013; 语音邮件消息然后，这些语音邮件消息将显示为用户的收件箱中的电子邮件。 
  
如果您已经配置了业务服务器 2015年和 Exchange Server 2016年或 Exchange Server 2013 Skype 之间的服务器到服务器进行身份验证，您已准备好安装统一邮件。 若要执行此操作，必须首先创建并分配一个新的统一邮件拨号计划上 Exchange Server。 例如，（从内运行 Exchange 管理外壳） 这两个命令 exchange 配置新的 3 位数字拨号计划：
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

在该示例的第一个命令中，VoIPSecurity 参数和参数值“Secured”指示信号通道用传输层安全性 (TLS) 加密。URIType“SipName”指示将使用 SIP 协议发送和接收消息，CountryOrRegionCode 为 1 指示拨号计划适用于美国。
  
在第二个命令中，传递给 ConfiguredInCountryOrRegionGroups 参数的参数值指定可在此拨号计划中使用的国家/地区组。 参数值"，\*，\*，\*"设置如下：
  
- 组名 ("Anywhere")
    
- AllowedNumberString (\*，通配符字符，指示允许任何数字字符串)
    
- DialNumberString (\*，表明任何拨叫的号码允许通配符)
    
- TextComment (\*，通配符字符，指示允许任何文本命令)
    
> [!NOTE]
> 创建新的拨号计划也会创建一条默认邮箱策略。 
  
在创建和配置新拨号计划后，必须将新拨号计划添加至统一消息服务器中，然后修改该服务器的启动模式；特别需要指出的是，必须将启动模式设置为“双”。 您可以执行两项任务从 Exchange 管理外壳程序中：
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

配置统一消息服务器后下一步应该运行启用 ExchangeCertificate cmdlet 以确保交换证书用于统一邮件服务：
  
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
  
在启用其邮箱后，用户 kenmyer@litwareinc.com 应该能够使用 Exchange 统一消息。 您可以验证用户可以连接到 UM 交换通过为业务服务器管理外壳程序运行[测试 CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet 从 Skype 内：
  
```
$credential = Get-Credential "litwareinc\kenmyer"

Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

如果您已启用统一消息的第二个用户可以使用[测试 CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) cmdlet 以验证此第二个用户可以留下语音邮件消息的第一个用户。
  
```
$credential = Get-Credential "litwareinc\pilar"

Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```


