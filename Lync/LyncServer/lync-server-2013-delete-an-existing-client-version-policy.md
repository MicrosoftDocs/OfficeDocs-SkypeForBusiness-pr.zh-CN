---
title: 删除现有客户端版本策略
TOCTitle: 删除现有客户端版本策略
ms:assetid: b88aaa25-97ff-4eb6-bd34-b97332cd6890
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ923064(v=OCS.15)
ms:contentKeyID: 52061102
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除现有客户端版本策略

 

_**上一次修改主题：** 2013-02-23_

如果您要删除以前配置的客户端版本策略，可从 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序删除它。

## 使用 Lync Server 控制面板删除客户端版本策略

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“客户端”，然后单击“客户端版本策略”导航按钮。

4.  在“客户端版本策略”页上，选择要删除的客户端版本策略，单击“编辑”，然后单击“删除”。

## 使用 Windows PowerShell Cmdlet 删除客户端版本策略

可使用 **Remove-CsClientVersionPolicy** cmdlet 删除客户端版本策略。可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 删除特定客户端版本策略

  - 以下命令可删除应用于 Redmond 站点的客户端版本策略：
    
        Remove-CsClientVersionPolicy -Identity site:Redmond

## 删除应用于网站范围的所有客户端版本策略

  - 以下命令可删除在网站范围内配置的所有客户端版本策略：
    
        Get-CsClientVersionPolicy -Fiter "site:*" | Remove-CsClientVersionPolicy

## 删除不包括特定用户代理的客户端版本策略

  - 以下命令可删除不包括 Windows Phone Lync (WPLync) 用户代理规则的任何客户端版本策略：
    
        Get-CsClientVersionPolicy | Where-Object {$_.Rules -notmatch "UserAgent=WPLync" | Remove-CsClientVersionPolicy

有关详细信息，请参阅 [Remove-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClientVersionPolicy) cmdlet 的帮助主题。

