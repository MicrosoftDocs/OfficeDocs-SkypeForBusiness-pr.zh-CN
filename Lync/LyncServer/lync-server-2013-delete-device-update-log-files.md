---
title: 删除设备更新日志文件
TOCTitle: 删除设备更新日志文件
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994039(v=OCS.15)
ms:contentKeyID: 52061035
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除设备更新日志文件

 

_**上一次修改主题：** 2013-02-23_

设备更新 Web 服务可保留大量日志文件的集合。此集合包括由服务自身执行的审核日志和从客户端设备上载的日志文件。若要防止服务器填满设备更新 Web 服务服务日志，您可能会希望从已经存在特定天数的日志文件中将其清除。根据更新活动和组织中的客户端设备数量，使用 Lync Server 控制面板或 Lync Server 命令行管理程序设置此天数。

## 使用 Lync Server 控制面板清除设备更新日志

1.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左侧导航栏中，单击“客户端”，然后单击“设备日志配置”。

3.  在“设备日志配置”页上，双击要更改的配置。

4.  在“编辑日志设置”对话框中的“日志文件的保留天数(1-365)”中，指定天数。

5.  单击“提交”。将删除服务器上超过指定天数的所有文件。此设置将应用于此配置，直到您更改它。

## 使用 Windows PowerShell Cmdlet 清除设备更新日志

可以使用 Windows PowerShell 和 **Clear-CsDeviceUpdateLog** cmdlet 清除设备更新日志。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。

> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>。



## 清除一台服务器上的设备更新日志

  - 以下命令清除 Web 服务器 atl-cs-001.litwareinc.com 上的设备更新日志。将从日志中移除超过 10 天（DaysBack 参数指定的值）的所有日志条目。
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

## 清除所有设备更新日志

  - 此命令从组织中当前使用的所有设备更新日志中移除过时条目（在此示例中，为超过 10 天的条目）。
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

有关详细信息，请参阅 [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/en-us/powershell/module/skype/Clear-CsDeviceUpdateLog) cmdlet 的帮助主题。

