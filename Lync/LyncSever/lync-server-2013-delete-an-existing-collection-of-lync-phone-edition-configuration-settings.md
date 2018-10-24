---
title: 删除 Lync Phone Edition 配置设置的现有集合
TOCTitle: 删除 Lync Phone Edition 配置设置的现有集合
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49888322
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除 Lync Phone Edition 配置设置的现有集合

 

_**上一次修改主题：** 2013-02-23_

如果您不再想将某一设置集合用于运行 Lync Phone Edition 的设备，可删除该集合。如果删除某一站点的集合，则全局设置将应用于该站点中的电话。不能删除全局集合。

> [!NOTE]  
> 您可能不想删除集合，只是想更改其中的一些设置。有关如何执行此操作的详细信息，请参阅<a href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">创建或修改 Lync Phone Edition 配置设置的集合</a>。



## 删除 Lync Phone Edition 配置设置的集合

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“客户端”，然后单击“设备配置”导航按钮。

4.  在“设备配置”页上，单击要删除的集合，单击“编辑”菜单，然后单击“删除”。
    
    > [!NOTE]  
    > 如果删除全局集合，设置将只恢复为默认设置。集合不会消失。
    


5.  在确认框中，单击“确定”。

## 使用 Lync Server 命令行管理程序 cmdlet 删除 Lync Phone Edition 配置设置

可以使用 Windows PowerShell 和 **Remove-CsUCConfiguration** cmdlet 删除 Lync Phone Edition 配置设置。可从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 删除指定的 Lync Phone Edition 配置设置集合

  - 此命令可删除应用于 Redmond 站点的 UC 电话配置设置：
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

## 删除应用于站点范围的所有 Lync Phone Edition 配置设置

  - 此命令可删除应用于服务范围的所有 UC 电话配置设置：
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

## 删除禁用电话锁定的所有 Lync Phone Edition 配置设置

  - 此命令可删除已禁用电话锁定的所有 UC 电话配置设置集合：
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

有关详细信息，请参阅 [Remove-CsUCPhoneConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsUCPhoneConfiguration)。

