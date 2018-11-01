---
title: 创建测试更新功能的设备
TOCTitle: 创建测试更新功能的设备
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182587(v=OCS.15)
ms:contentKeyID: 49314287
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 创建测试更新功能的设备

 

_**上一次修改主题：** 2013-02-23_

可将测试设备添加到“测试设备”页，然后使用此设备验证新更新的功能，之后再将更新部署到生产设备。可以在全局范围（在整个 Lync Server 环境）或在单个站点中测试设备。可通过测试设备的媒体访问控制 (MAC) 地址或序列号标识测试设备。添加设备时，设备会显示在 Lync Server 控制面板的“测试设备”页上的列表中。

## 添加测试设备

1.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左侧导航栏中，单击“客户端”，然后单击“测试设备”。

3.  单击“新建”，然后单击“全局测试设备”或“站点测试设备”。

4.  执行下列操作之一：
    
      - 如果单击了“全局测试设备”，则跳到下一步。
    
      - 如果单击了“站点测试设备”，则从可用站点列表中选择一个站点，然后单击“确定”。

5.  在“新建测试设备”上的“设备名称”中，键入设备的名称。

6.  在“标识符类型”下，单击“MAC 地址”或“序列号”。

7.  在“唯一标识符”框中，键入设备的 MAC 地址或序列号。

8.  单击“提交”。

## 使用 Windows PowerShell Cmdlet 创建测试设备

可以使用 Windows PowerShell 和 New-CsTestDevice cmdlet 创建测试设备。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

使用此 cmdlet 创建测试设备时，必须执行以下两个操作：

  - 指定 MACAddress 或 SerialNumber 为 IdentifierType。

  - 指定设备标识时包括作用域。要在全局作用域创建新设备，请使用类似如下的语法：
    
        -Identity "global/WindowsPhone"
    
    要在站点作用域创建测试设备，请使用类似如下的语法：
    
        -Identity "site:Redmond/WindowsPhone"

## 使用 MAC 地址创建测试设备

  - 以下命令在全局作用域创建测试设备，并使用 MAC 地址作为 IdentifierType：
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

## 使用序列号创建测试设备

  - 以下命令在站点作用域（对于 Redmond 站点）创建测试设备，并使用序列号作为 IdentifierType：
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

有关详细信息，请参阅 [New-CsTestDevice](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTestDevice) cmdlet 的帮助主题。

