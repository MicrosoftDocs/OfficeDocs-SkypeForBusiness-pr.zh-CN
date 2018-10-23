---
title: Lync Server 2013：导出拓扑并将其复制到外部媒体以用于边缘安装
TOCTitle: 导出拓扑并将其复制到外部媒体以用于边缘安装
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398983(v=OCS.15)
ms:contentKeyID: 49314472
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 导出 Lync Server 2013 拓扑并将其复制到外部媒体以用于边缘安装

 

_**上一次修改主题：** 2012-09-08_

发布拓扑后，为了在服务器上启动部署过程， Lync Server 部署向导需要访问 中央管理存储数据。在内部网络中，可直接从服务器访问数据，但不在内部域中的边缘服务器不能访问数据。若要使拓扑配置数据可用于边缘服务器部署，必须先将拓扑数据导出到文件并复制到外部介质（例如，可从边缘服务器访问的 USB 驱动器或网络共享），然后才能在边缘服务器上运行 Lync Server 部署向导。使用以下过程使拓扑配置数据在正在部署的边缘服务器上可用。

> [!NOTE]  
> 在一台边缘服务器上安装 Lync Server 2013 后，可使用内部网络中的管理工具来管理边缘服务器，这些管理工具可自动将配置复制到部署中的任何边缘服务器。仅有的例外是分配和安装证书以及停止和启动服务，这些操作必须在边缘服务器上执行。



## 使用 Lync Server 命令行管理程序使拓扑数据在边缘服务器上可用

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  在 Lync Server 命令行管理程序中，运行以下 cmdlet：
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  将导出的文件复制到外部介质（例如，在部署过程中可从边缘服务器访问的 USB 驱动器或网络共享）。

