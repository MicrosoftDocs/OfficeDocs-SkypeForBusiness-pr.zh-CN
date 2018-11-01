---
title: Lync Server 2013：为用户启用托管语音邮件
TOCTitle: 为用户启用托管语音邮件
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413062(v=OCS.15)
ms:contentKeyID: 49314811
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中为用户启用托管语音邮件

 

_**上一次修改主题：** 2012-09-24_

按照本过程，在托管的 Exchange 统一消息 (UM) 服务中为 Lync Server 2013 用户启用语音邮件。

有关详细信息，请参阅规划文档中的 [Lync Server 2013 中的托管 Exchange 用户管理](lync-server-2013-hosted-exchange-user-management.md)。

有关 [Set-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUser) cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。

> [!IMPORTANT]
> 在可以为 Lync Server 2013 用户启用托管语音邮件之前，必须已部署应用于其用户帐户的托管语音邮件策略。有关详细信息，请参阅 <a href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中的托管语音邮件策略</a>。


## 为用户启用托管语音邮件

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  运行 Set-CsUser cmdlet 以为用户帐户配置托管语音邮件。例如，运行：
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    上述示例设置了以下参数：
    
      - 通过 **HostedVoiceMail**，可以将用户的语音邮件呼叫路由至托管 Exchange UM。它还会向 Microsoft Lync 2013 发信号，以点亮“呼叫语音邮件”指示器。
    
      - **Identity** 指定要修改的用户帐户。可以使用以下任意格式指定 Identity 值：
        
          - 用户的 SIP 地址
        
          - 用户的 Active Directory 用户主体名称
        
          - 用户的域\\登录名（例如，contoso\\kenmyer）
        
          - 用户的 Active Directory 域服务显示名称（例如，Ken Myer）。如果将显示名称用作 Identity 值，可以使用星号 (\*) 通配符。例如，Identity "\* Smith" 将返回显示名称以字符串值“Smith”结尾的所有用户。
        
        > [!NOTE]  
		> 用户的 Active Directory SAM 帐户名不能用作 Identity 值，因为 SAM 帐户名在林中不一定是唯一的。
        

