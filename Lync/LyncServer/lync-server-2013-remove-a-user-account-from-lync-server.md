---
title: 从 Lync Server 删除用户帐户
TOCTitle: 从 Lync Server 删除用户帐户
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49888359
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 从 Lync Server 删除用户帐户

 

_**上一次修改主题：** 2013-02-22_

您可以使用以下过程来移除 Lync Server 2013 中以前添加的用户帐户。

> [!NOTE]  
> 移除用户将导致您丢失为用户帐户配置的所有设置。如果您要临时禁用用户帐户，请参阅主题<a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">禁用或重新启用 Lync Server 的用户帐户</a>。



## 移除 Lync Server 中的 Lync Server 用户帐户

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“用户”。

4.  在“搜索用户”框中，键入要禁用或重新启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”。

5.  在表中，单击要移除的用户帐户。

6.  在“操作”菜单上，选择“从 Lync Server 中删除”，然后将出现一个对话框。

7.  从该对话框中，选择“确定”来移除该用户。

## 使用 Lync Server PowerShell Cmdlet 移除用户帐户

您还可以使用 Disable-CsUser cmdlet 移除用户帐户。此 cmdlet 可从 Lync Server 2013 命令行管理程序或从远程会话 Windows PowerShell 运行。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 移除用户帐户

  - 若要移除用户帐户，请使用 Disable-CsUser cmdlet。例如：
    
        Disable-CsUser -Identity "Ken Myer"
    
    在此命令运行后，没有办法重新启用该帐户及其以前的设置。您将需要使用 Enable-CsUser cmdlet 为 Ken Myer 创建全新的帐户。

有关详细信息，请参阅 [Disable-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Disable-CsUser) cmdlet 的帮助主题。

## 另请参阅

#### 任务

[禁用或重新启用 Lync Server 的用户帐户](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  

#### 其他资源

[启用和禁用 Lync Server 2013 的用户](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

