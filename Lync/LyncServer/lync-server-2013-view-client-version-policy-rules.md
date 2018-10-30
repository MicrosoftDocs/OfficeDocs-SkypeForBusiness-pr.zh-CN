---
title: 查看客户端版本策略规则
TOCTitle: 查看客户端版本策略规则
ms:assetid: f3a0215f-f72f-4e9b-a07b-25858dc4203a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ923060(v=OCS.15)
ms:contentKeyID: 52061155
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 查看客户端版本策略规则

 

_**上一次修改主题：** 2013-02-23_

客户端版本策略由一组客户端版本策略规则组成。这些规则定义在用户尝试使用特定客户端和客户端版本登录时应采取的操作。您可以从 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序中查看客户端版本策略规则。

## 使用 Lync Server 控制面板查看客户端版本策略规则

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“客户端”，然后单击“客户端版本策略”导航按钮。

4.  在“客户端版本策略”页上，双击您要查看的客户端版本策略。

5.  这些规则将显示在“编辑客户端版本策略”页上。若要查看某个规则的详细信息，请选择该规则，然后单击“显示详细信息”。

## 使用 Windows PowerShell Cmdlet 查看客户端版本策略规则

可以使用 Lync Server 命令行管理程序和 **Get-CsClientVersionPolicyRule** cmdlet 查看客户端版本策略规则。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 查看客户端版本策略规则

  - 若要查看客户端版本策略规则，请在 Lync Server 命令行管理程序中键入以下命令，然后按 Enter：
    
        Get-CsClientVersionPolicyRule
    
    这将为已配置的每个规则返回如下信息：
    
        Identity          : Global/2336c611-a243-4c5d-994b-eea8a524d0e4
        Priority          : 0
        RuleId            : 2336c611-a243-4c5d-994b-eea8a524d0e4
        Description       :
        Action            : Block
        ActionUrl         :
        MajorVersion      : 1
        MinorVersion      : 3
        BuildNumber       :
        QfeNumber         :
        UserAgent         : RTC
        UserAgentFullName :
        Enabled           : True
        CompareOp         : LEQ

有关详细信息，请参阅 [Get-CsClientVersionPolicyRule](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClientVersionPolicyRule) cmdlet 的帮助主题。

