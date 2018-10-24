---
title: Lync Server 2013：安装 Windows PowerShell 3.0
TOCTitle: 安装 Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205328(v=OCS.15)
ms:contentKeyID: 49314428
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为 Lync Server 2013 安装 Windows PowerShell 3.0

 

_**上一次修改主题：** 2016-12-08_

要成功部署 Lync Server 2013，您需要在属于您的 Lync Server 拓扑的一部分的每台计算机上安装 Windows PowerShell 3.0。

现在，对于运行 Windows Server 2012 或 Windows Server 2012 R2 的系统，您不需要在这里执行任何操作，可以继续部署的下一阶段，因为这些操作系统中包括 PowerShell 3.0。

> [!IMPORTANT]
> 但是对于运行 Windows Server 2008 R2 SP1 的系统，在安装 Lync Server 2013 之前，您需要安装 PowerShell 3.0 作为先决条件，否则无法正常工作。要安装 PowerShell 3.0，请参阅 <a href="http://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</a>。这是 PowerShell 3.0 下载页面以及有关成功安装它的信息的直接连接。


完成安装后或者如果您只希望在继续 Lync Server 部署之前检查并确认，那么通过执行以下操作确认服务器上存在 PowerShell 3.0 非常简单：

1.  在要检查的服务器上，依次选择“开始”、“所有程序”、“附件”和“Windows PowerShell”，然后单击“Windows PowerShell”。

2.  在 Windows PowerShell 控制台中的命令提示符下键入以下命令，然后按 ENTER：
    
        Get-Host | Select-Object Version

3.  如果 Windows PowerShell 3.0 已安装，您将看到如下所示输出：
    
        Version
        -------
        3.0

