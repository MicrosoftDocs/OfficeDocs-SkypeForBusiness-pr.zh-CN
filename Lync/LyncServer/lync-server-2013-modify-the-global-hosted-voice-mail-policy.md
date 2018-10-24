---
title: 在 Lync Server 2013 中修改全局承载语音邮件策略
TOCTitle: 在 Lync Server 2013 中修改全局承载语音邮件策略
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412994(v=OCS.15)
ms:contentKeyID: 49314688
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中修改全局承载语音邮件策略

 

_**上一次修改主题：** 2012-09-24_

全局托管的语音邮件策略随 Lync Server 2013 一同安装。可以根据需要修改该策略，但不能重命名或删除它。若要修改全局策略，您可以针对特定的部署使用 Set-CsHostedVoicemailPolicy cmdlet 将参数设置为相应的值。

有关 [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsHostedVoicemailPolicy) cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。

## 修改全局托管语音邮件策略

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  运行 Set-CsHostedVoicemailPolicy cmdlet，为您的环境设置全局策略参数。例如，运行：
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    由于该命令不指定策略的 Identity 参数，因此，Windows PowerShell 命令行接口会在全局托管的语音邮件策略中设置以下值：
    
      - **Destination** 指定托管 Exchange UM 服务的完全限定域名 (FQDN)。此参数为可选参数，但如果尝试为用户启用托管语音邮件，而用户的已分配策略没有 Destination 值，则无法启用。
    
      - **Organization** 指定托管 Lync Server 用户的 Exchange 租户列表（以逗号分隔）。必须将每个租户指定为托管 Exchange UM 服务上租户的 FQDN。
    
    > [!NOTE]  
    > 在前面的示例 cmdlet 中，“corp1.litwareinc.com”值替代可能已经显示在 Organization 参数中的任何值。例如，如果策略已包含以逗号分隔的组织列表，则会替换整个列表。如果要向列表中添加组织，而不是替换整个列表，可运行类似如下的命令。
    
    
        $a = Get-CsHostedVoicemailPolicy
        $a.Organization += ",corp3.litwareinc.com"
        Set-CsHostedVoicemailPolicy -Organization $a.Organization

