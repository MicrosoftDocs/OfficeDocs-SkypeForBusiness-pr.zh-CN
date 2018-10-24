---
title: 重置设备更新规则
TOCTitle: 重置设备更新规则
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994069(v=OCS.15)
ms:contentKeyID: 52061135
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 重置设备更新规则

 

_**上一次修改主题：** 2013-02-23_

如果您不喜欢测试设备上某更新的运行方式，则可以重置设备更新规则，以便从测试设备中删除规则的挂起状态并卸载该更新。

您可以使用 Lync Server 控制面板或 Windows PowerShell 删除设备更新规则。

> [!NOTE]  
> 要卸载您已批准（即，已推出）的规则，请还原它。有关详细信息，请参阅<a href="lync-server-2013-restore-a-device-update-rule.md">还原设备更新规则</a>。



## 使用 Lync Server 控制面板重置设备更新规则

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“客户端”，然后单击“设备更新”导航按钮。

4.  在“设备更新”页上，执行下列操作之一：
    
      - 要重置某规则，请选择该规则。
    
      - 要重置所有规则，请在“编辑”菜单中，单击“全选”。
    
      - 要重置针对某品牌的所有规则，请使用“品牌”列菜单。

5.  单击“操作”，然后单击“取消挂起更新”。
    
    > [!TIP]
    > 如果您确信不再希望推出已取消的设备更新规则，可能需要删除它们。有关详细信息，请参阅<a href="lync-server-2013-remove-a-device-update-rule.md">删除设备更新规则</a>。


## 使用 Windows PowerShell Cmdlet 重置设备更新规则

还可使用 Windows PowerShell 和 **Reset-CsDeviceUpdateRule** cmdlet 重置设备更新规则。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。

> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>。



## 重置服务器上的特定设备更新规则

  - 以下命令可重置 Web 服务器 atl-cs-001.litwareinc.com 上的设备更新规则 d5ce3c10-2588-420a-82ac-dc2d9b1222ff9：
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

## 重置服务器上的所有设备更新规则

  - 此命令可重置 Web 服务器 atl-cs-001.litwareinc.com 上的所有设备更新规则：
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

## 重置某特定品牌的所有设备更新规则

  - 在此示例中，将重置组织中其 Brand（品牌）等于 Microsoft 的所有设备更新：
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

有关详细信息，请参阅 [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/en-us/powershell/module/skype/Reset-CsDeviceUpdateRule) cmdlet 的帮助主题。

## 另请参阅

#### 任务

[批准设备更新规则](lync-server-2013-approve-a-device-update-rule.md)

