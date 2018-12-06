---
title: "Lync Server 2013：在 Survivable Branch Appliance 或 Survivable Branch Server 上承载用户"
TOCTitle: 在 Survivable Branch Appliance 或 Survivable Branch Server 上承载用户
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413066(v=OCS.15)
ms:contentKeyID: 49314821
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中在 Survivable Branch Appliance 或 Survivable Branch Server 上承载用户

 

_**上一次修改主题：** 2014-12-10_

在 Survivable Branch Appliance 或 Survivable Branch Server 上承载用户的过程类似于在 前端池中承载用户的过程。请在中央站点上执行 Survivable Branch Appliance 或 Survivable Branch Server 过程。

## 在 Survivable Branch Appliance 或 Survivable Branch Server 上承载用户

1.  将用户移动到 Survivable Branch Server 或 Survivable Branch Server 之前，打开 Lync Server 命令行管理程序，然后执行以下所有操作：
    
      - 运行 cmdlet **Test-CsPstnOutboundCall** 来验证 Survivable Branch Server 是否正在运行，以及是否已配置公用电话交换网 (PSTN) 连接。如果需要修改 PSTN 网关属性，请使用 cmdlet **Set-CsPstnGateway**。
    
      - 运行 cmdlet **Get-CsVoicePolicy** 来验证将承载在 Survivable Branch Server 上的用户是否具有相应的 VoIP 路由策略。如果需要修改 VoIP 策略，请使用 cmdlet **Set-CsVoicePolicy**。
    
      - 运行 cmdlet **Get-CsVoicemailReroutingConfiguration** 来验证是否已配置语音邮件重新路由设置。如果需要修改语音邮件重新路由设置，请使用 cmdlet **Set-CsVoicemailReroutingConfiguration**。

2.  在 Lync Server 命令行管理程序中，运行 cmdlet **Move-CsUser** 以承载用户。

> [!NOTE]  
> 还可以使用 Lync Server 控制面板验证先决条件并承载用户。



## 另请参阅

#### 其他资源

[Test-CsPstnOutboundCall](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsPstnOutboundCall)  
[Get-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsVoicePolicy)  
[Get-CsVoicemailReroutingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsUser)

