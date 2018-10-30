---
title: 删除会议配置设置的现有集合
TOCTitle: 删除会议配置设置的现有集合
ms:assetid: 92ff8a91-05c5-4047-a533-5dff12f22299
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688136(v=OCS.15)
ms:contentKeyID: 49888515
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除会议配置设置的现有集合

 

_**上一次修改主题：** 2013-02-23_

可以删除站点或用户配置。无法删除全局配置。如果删除全局配置，该配置将自动重置为默认值。

## 删除站点或用户会议配置

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“会议”，然后单击“会议配置”。

4.  在会议配置的列表中，单击要删除的站点或池配置，单击“编辑”，然后单击“删除”。

## 使用 Lync Server PowerShell Cmdlet 删除会议配置设置

还可使用 Windows PowerShell 和 Remove-CsMeetingConfiguration cmdlet 删除会议设置。可从 Lync Server 2013 命令行管理程序或从Windows PowerShell 的远程会话运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 删除会议配置设置的指定集合

  - 此命令删除应用于 Redmond 站点的会议配置设置：
    
        Remove-CsMeetingConfiguration -Identity "site:Redmond"

## 删除应用于站点作用域的所有会议配置设置

  - 此命令删除应用于站点作用域的所有会议配置设置：
    
        Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration

## 删除默认允许匿名用户的所有会议配置设置

  - 添加此命令将删除所有默认允许匿名用户的设置：
    
        Get-CsMeetingConfiguration | Where-Object {$_.AdmitAnonymousUsersByDefault -eq $True} | Remove-CsMeetingConfiguration

有关详细信息，请参阅 [Remove-CsMeetingConfiguration](ttps://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsMeetingConfiguration) cmdlet 的帮助主题。

