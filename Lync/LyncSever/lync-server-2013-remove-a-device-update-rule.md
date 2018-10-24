---
title: 删除设备更新规则
TOCTitle: 删除设备更新规则
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994066(v=OCS.15)
ms:contentKeyID: 52061097
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除设备更新规则

 

_**上一次修改主题：** 2013-02-23_

删除一条设备更新规则会将其永久地从设备更新队列中删除。

删除规则和从部署中的设备上或测试设备上卸载更新不同。要从部署中卸载已批准的更新，需要*还原* 该设备更新规则。有关详细信息，请参阅[还原设备更新规则](lync-server-2013-restore-a-device-update-rule.md)。要从测试设备卸载您还未批准的更新，需要*重置* 它。有关详细信息，请参阅[重置设备更新规则](lync-server-2013-reset-a-device-update-rule.md)。

可以使用 Lync Server 控制面板或 Windows PowerShell 删除设备更新规则。

## 使用 Lync Server 控制面板删除设备更新规则

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“客户端”，然后单击“设备更新”导航按钮。

4.  在“设备更新”页上，执行下列操作之一：
    
      - 若要删除一个规则，请选择要删除的规则。
    
      - 若要删除所有规则，请单击“编辑”菜单，然后单击“全选”。

5.  单击“编辑”，然后单击“删除”。

## 使用 Windows PowerShell Cmdlet 删除设备更新规则

还可以使用 Windows PowerShell 和 **Remove-CsDeviceUpdateRule** cmdlet 删除设备更新规则。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 从一台服务器删除单个设备更新规则

  - 以下命令从 atl-cs-001.litwareinc.com 上的 Web 服务器删除设备更新规则 d5ce3c10-2588-420a-82ac-dc2d9b1222ff9。
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

## 从一台服务器删除所有设备更新规则

  - 此命令从 atl-cs-001.litwareinc.com 上的 Web 服务器删除所有设备更新规则。
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

有关详细信息，请参阅 [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsDeviceUpdateRule) cmdlet 的帮助主题。

## 另请参阅

#### 任务

[批准设备更新规则](lync-server-2013-approve-a-device-update-rule.md)

