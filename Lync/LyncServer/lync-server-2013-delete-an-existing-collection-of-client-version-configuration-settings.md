---
title: 删除现有客户端版本配置设置集合
TOCTitle: 删除现有客户端版本配置设置集合
ms:assetid: 70bf1216-d0d2-45ce-881f-b8edadf3cec7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ898480(v=OCS.15)
ms:contentKeyID: 52061045
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除现有客户端版本配置设置集合

 

_**上一次修改主题：** 2013-02-23_

如果想要删除之前为站点配置的客户端配置设置，可以从 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序中删除这些设置。

## 使用 Lync Server 控制面板删除客户端版本配置设置

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“客户端”，然后单击“客户端版本配置”导航按钮。

4.  选择站点，单击“编辑”，单击“删除”，然后单击“确定”。

## 使用 Windows PowerShell Cmdlet 删除客户端版本配置设置

还可以通过使用 **Remove-CsClientVersionConfiguration** cmdlet 删除客户端版本配置设置。可从 Lync Server 2013 命令行管理程序 或从 Windows PowerShell 的远程会话运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 删除指定的客户端版本配置设置集合

  - 以下命令删除应用于 Redmond 站点的客户端版本配置设置：
    
        Remove-CsClientVersionConfiguration -Identity "site:Redmond"

## 删除应用于站点范围的所有客户端版本配置设置

  - 此命令删除在站点范围配置的所有客户端版本配置设置：
    
        Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

## 删除所有基于 DefaultAction 属性值的客户端版本配置设置

  - 此命令删除其默认操作设置为“Block”的所有客户端版本配置设置：
    
        Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block" | Remove-CsClientVersionConfiguration

有关详细信息，请参阅 [Remove-CsClientVersionConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClientVersionConfiguration) cmdlet 的帮助主题。

