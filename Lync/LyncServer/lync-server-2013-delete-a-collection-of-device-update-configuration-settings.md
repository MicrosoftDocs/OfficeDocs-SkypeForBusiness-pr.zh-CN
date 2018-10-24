---
title: 删除设备更新配置设置的集合
TOCTitle: 删除设备更新配置设置的集合
ms:assetid: 1a649136-34a9-42a7-a5b3-a78bbfe93f36
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994019(v=OCS.15)
ms:contentKeyID: 52060971
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除设备更新配置设置的集合

 

_**上一次修改主题：** 2013-02-20_

还可以使用 Windows PowerShell 和 **Remove-CsdeviceUpdateConfiguration** cmdlet 删除设备更新配置设置。可从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。


## 删除特定的设备更新配置设置集合

  - 此命令可删除应用于 Redmond 站点的设备更新配置设置：
    
        Remove-CsDeviceUpdateConfiguration -Identity "site:Redmond"

## 删除应用于站点作用域的所有设备更新配置设置

  - 此命令可删除应用于站点作用域的所有设备更新配置设置：
    
        Get-CsDeviceUpdateConfiguration -Filter "site:*" | Remove-CsDeviceUpdateConfiguration

## 基于 LogCleanUpInterval 属性值删除设备更新配置设置

  - 以下命令可删除日志清除间隔大于 10 天 (10.00:00:00) 的所有设备更新配置设置：
    
        Get-CsDeviceUpdateConfiguration | Where-Object {$_.LogCleanUpInterval -gt "10.00:00:00" | Remove-CsDeviceUpdateConfiguration

有关详细信息，请参阅 [Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) cmdlet 的帮助主题。

