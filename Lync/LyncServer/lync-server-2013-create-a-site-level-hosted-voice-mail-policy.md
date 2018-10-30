---
title: 在 Lync Server 2013 中创建站点级承载语音邮件策略
TOCTitle: 在 Lync Server 2013 中创建站点级承载语音邮件策略
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398216(v=OCS.15)
ms:contentKeyID: 49312081
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中创建站点级承载语音邮件策略

 

_**上一次修改主题：** 2012-09-24_

*站点* 策略可以影响在为其定义策略的站点上承载的所有用户。如果已为用户配置托管 Exchange UM 访问且未向用户分配每用户策略，则将应用站点策略。如果尚未部署站点策略，则将应用全局策略。

有关配置站点策略的详细信息，请参阅 Lync Server 命令行管理程序文档中以下 cmdlet 的相关内容：

  - [New-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsHostedVoicemailPolicy)

## 创建站点托管语音邮件策略

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  运行 New-CsHostedVoicemailPolicy cmdlet 创建策略。例如，运行：
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    本示例创建 site 作用域的托管语音邮件策略，并设置以下参数：
    
      - **Identity** 为策略指定唯一标识符，其中包含作用域。对于 site 作用域的策略，Identity 参数值必须指定为 `site:`*\<名称\>* 格式，例如，`site:Redmond`。
    
      - **Destination** 指定托管 Exchange UM 服务的完全限定域名 (FQDN)。此参数为可选参数，但如果尝试为用户启用托管语音邮件，而用户的已分配策略没有 Destination 值，则无法启用。
    
      - **Description** 提供有关策略的可选描述性信息。
    
      - **Organization** 指定承载 Lync Server 2013 用户的 Exchange 租户列表（以逗号分隔）。必须将每个租户指定为托管 Exchange UM 服务上租户的 FQDN。

