---
title: 还原设备更新规则
TOCTitle: 还原设备更新规则
ms:assetid: ac490baf-c7a0-48d9-8fd0-ba5729489341
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994061(v=OCS.15)
ms:contentKeyID: 52061108
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 还原设备更新规则

 

_**上一次修改主题：** 2013-02-23_

若要从您的部署中的设备上卸载设备更新规则，请还原它。还原设备更新规则不仅卸载更新还将重新安装该规则的以前版本。

可以使用 Lync Server 控制面板或 Windows PowerShell 还原设备更新规则。

## 使用 Lync Server 控制面板还原设备更新规则

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“客户端”，然后单击“设备更新”导航按钮。

4.  在“设备更新”页上，执行下列操作之一：
    
      - 若要还原一个规则，请选择该规则。
    
      - 若要还原所有规则，请单击“编辑”，然后单击“全选”。

5.  单击“操作”菜单，然后单击“还原”。

## 使用 Windows PowerShell Cmdlet 还原设备更新规则

也可以使用 Windows PowerShell 和 **Restore-CsDeviceUpdateRule** cmdlet 还原设备更新规则。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话运行此 cmdlet。

> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>。



## 还原一台服务器上的单个设备更新规则

  - 以下命令还原 Web 服务器 atl-cs-001.litwareinc.com 上的设备更新规则 d5ce3c10-2588-420a-82ac-dc2d9b1222ff9：
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

## 还原一台服务器上的所有设备更新规则

  - 此命令还原 Web 服务器 atl-cs-001.litwareinc.com 上的所有设备更新规则：
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

有关详细信息，请参阅 [Restore-CsDeviceUpdateRule](https://docs.microsoft.com/en-us/powershell/module/skype/Restore-CsDeviceUpdateRule) cmdlet 的帮助主题。

