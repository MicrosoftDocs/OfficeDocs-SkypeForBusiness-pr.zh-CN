---
title: 禁用或重新启用 Lync Server 的用户帐户
TOCTitle: 禁用或重新启用 Lync Server 的用户帐户
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg429696(v=OCS.15)
ms:contentKeyID: 49312057
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 禁用或重新启用 Lync Server 的用户帐户

 

_**上一次修改主题：** 2016-04-04_

使用以下过程可以禁用在 Lync Server 2013 中以前启用的用户帐户，而不会丢失为该用户帐户配置的 Lync Server 设置。由于没有丢失 Lync Server 用户帐户设置，因此，可以再次重新启用以前启用的用户帐户而无需重新配置该用户帐户。

## 为 Lync Server 禁用或重新启用以前启用的用户帐户

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“用户”。

4.  在“搜索用户”框中，键入要禁用或重新启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”。

5.  在表中，单击要禁用或重新启用的用户帐户。

6.  在“操作”菜单上，执行下列操作之一：
    
      - 若要为 Lync Server 2013 暂时禁用用户帐户，请单击“为 Lync Server 临时禁用”。
    
      - 若要为用户帐户启用 Lync Server 2013，请单击“为 Lync Server 重新启用”。

## 使用 Windows PowerShell Cmdlet 禁用和重新启用用户帐户

使用 **Set-CsUser** cmdlet 还可以暂时禁用、然后稍后再重新启用用户帐户。可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 禁用用户帐户

  - 若要暂时禁用某一用户帐户，请将 Enabled 属性的值设置为 False ($False)。例如：
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

## 重新启用用户帐户

  - 若要重新启用已禁用的用户帐户，请将 Enabled 属性的值设置为 True ($True)。例如：
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

有关详细信息，请参阅 [Set-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUser) cmdlet 的帮助主题。

## 另请参阅

#### 任务

[向 Lync Server 2010 添加和启用用户帐户](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  

#### 其他资源

[启用和禁用 Lync Server 2013 的用户](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

