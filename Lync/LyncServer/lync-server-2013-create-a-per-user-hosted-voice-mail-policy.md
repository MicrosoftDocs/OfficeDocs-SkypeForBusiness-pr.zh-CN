---
title: 在 Lync Server 2013 中创建每用户承载语音邮件策略
TOCTitle: 在 Lync Server 2013 中创建每用户承载语音邮件策略
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425867(v=OCS.15)
ms:contentKeyID: 49312541
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中创建每用户承载语音邮件策略

 

_**上一次修改主题：** 2012-09-24_

每用户策略只能影响单个用户、组和联系对象。要部署每用户策略，必须将策略显式分配给一个或多个用户、组或联系对象。有关详细信息，请参阅[在 Lync Server 2013 中分配每用户承载的语音邮件策略](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)。

有关使用每用户托管语音邮件策略的详细信息，请参阅 Lync Server 命令行管理程序文档中以下 cmdlet 的相关内容：

  - [New-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsHostedVoicemailPolicy)

## 创建每用户托管语音邮件策略

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  运行 New-CsHostedVoicemailPolicy cmdlet 创建策略。例如，运行：
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    以上示例创建了一个具有每用户作用域的托管语音邮件策略，并设置了以下参数：
    
      - **Identity** 为策略指定唯一标识符，其中包含作用域。对于具有每用户作用域的策略，此参数值会指定为简单字符串，如 ExRedmond。
    
      - **Destination** 指定托管 Exchange UM 服务的完全限定域名 (FQDN)。此参数为可选参数，但如果尝试为用户启用托管语音邮件，而用户的已分配策略没有 Destination 值，则无法启用。
    
      - **Description** 提供有关策略的可选描述性信息。
    
      - **Organization** 指定承载 Lync Server 2013 用户的 Exchange 租户列表（以逗号分隔）。必须将每个租户指定为托管 Exchange UM 服务上租户的 FQDN。

## 另请参阅

#### 任务

[在 Lync Server 2013 中分配每用户承载的语音邮件策略](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)

