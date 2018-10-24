---
title: 删除现有会议策略
TOCTitle: 删除现有会议策略
ms:assetid: 709ed771-790f-4bf1-a4de-b37ca5168688
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688089(v=OCS.15)
ms:contentKeyID: 49888460
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除现有会议策略

 

_**上一次修改主题：** 2013-02-23_

按照以下步骤删除用户级别或站点级别的会议策略。

> [!NOTE]  
> 无法删除全局会议策略。



## 删除站点或用户会议策略

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“会议”，然后单击“会议策略”。

4.  在会议策略列表中，单击要删除的站点策略或用户策略，再单击“编辑”，然后单击“删除”。

## 使用 Lync Server 命令行管理程序 cmdlet 删除会议策略

您还可以使用 Lync Server 命令行管理程序和 **Remove-CsConferencingPolicy** cmdlet 删除中继配置设置。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 删除指定会议策略

  - 以下命令删除 Identity 为 RedmondConferencingPolicy 的会议策略：
    
        Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"

## 删除适用于每用户范围的所有会议策略

  - 以下命令删除在每用户范围配置的所有会议策略：
    
        Get-CsConferencingPolicy -Filter "tag:*" | Remove-CsConferencingPolicy

## 删除允许外部用户记录的所有会议策略

  - 以下命令删除允许外部用户记录会议的所有会议策略：
    
        Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy

有关详细信息，请参阅 [Remove-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsConferencingPolicy)。

