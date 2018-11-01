---
title: 删除存档策略
TOCTitle: 删除存档策略
ms:assetid: 4739a691-41cc-4128-8bb8-6d5a4c02107a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg520989(v=OCS.15)
ms:contentKeyID: 49312719
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除存档策略

 

_**上一次修改主题：** 2013-02-23_

可以删除用户策略或站点策略。无法删除全局策略。如果尝试删除全局策略，Lync Server 2013 会自动将该策略重置为默认值。

> [!NOTE]  
> 如果为部署启用 Microsoft Exchange 集成，则 Exchange 策略可控制是否为驻留在 Exchange 2013 上且其邮箱处于就地保留状态的用户启用存档。有关详细信息，请参阅部署文档中的<a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange 服务器集成设置存档的策略</a>。



## 删除用户存档策略或站点存档策略

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“监控和存档”，然后单击“存档策略”。

4.  在存档策略列表中，单击要删除的用户策略或站点策略，再单击“编辑”，然后单击“删除”。

5.  单击“提交”。

## 使用 Lync Server 命令行管理程序 Cmdlet 删除存档策略

还可使用 Windows PowerShell 和 **Remove-CsArchivingPolicy** cmdlet 删除存档策略。此 cmdlet 可从 Lync Server 2013 命令行管理程序运行或从 Windows PowerShell 的远程会话运行。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 删除指定的存档策略

  - 作为示例，**Remove-CsArchivingPolicy** 删除了 Identity 为 site:Redmond 的策略。请注意，删除站点作用域的策略时，全局存档策略将自动控制网站策略之前管理的用户。以下命令删除适用于 Redmond 站点的策略：
    
        Remove-CsArchivingPolicy -Identity site:Redmond

## 删除所有适用于每用户范围的存档策略

  - 此命令将删除所有适用于每用户范围的存档策略：
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

## 删除禁用了内部存档的所有存档策略

  - 此命令将删除其中禁用了内部存档的所有存档策略：
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

有关详细信息，请参阅 [Remove-CsArchivingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsArchivingPolicy) cmdlet 的帮助主题。

## 另请参阅

#### 其他资源

[在 Lync Server 2013 中管理内部通信和外部通信的存档](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

