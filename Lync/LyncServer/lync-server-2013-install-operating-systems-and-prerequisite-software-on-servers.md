---
title: Lync Server 2013：在服务器上安装操作系统和必备软件
TOCTitle: 在服务器上安装操作系统和必备软件
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398103(v=OCS.15)
ms:contentKeyID: 49311866
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在服务器上安装适用于 Lync Server 2013 的操作系统和必备软件

 

_**上一次修改主题：** 2016-12-08_

设置硬件和系统基础结构后，需要在要部署的每台服务器上安装相应的 Windows 操作系统及更新，以及其他所有必备软件。这包括部署所需的每个 Lync Server 2013 服务器角色和其他任何基础结构服务器以及运行 SQL Server 的服务器。

> [!NOTE]  
> 本节介绍操作系统和内部服务器必备软件的安装。如果要部署 边缘服务器以支持外部用户访问，则还需要为包括 边缘服务器和反向代理服务器在内的服务器安装操作系统和必备软件。有关准备服务器以支持外部用户访问的详细信息，请参阅部署边缘服务器文档中的 <a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">准备针对 Lync Server 2013 在外围网络中安装服务器</a>。



## 在服务器上安装 Windows 操作系统

在要部署的每台服务器上，安装相应的 Windows 操作系统：

  - **运行 Lync Server 2013 的服务器**   有关运行 Lync Server 2013 的服务器的操作系统要求的详细信息，请参阅可支持性文档中的[Lync Server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)。

  - **数据库服务器**   有关数据库服务器（包括后端数据库、 存档数据库和 监控数据库）的操作系统要求的详细信息，请参阅 SQL Server 文档。对于 SQL Server 2012，请参阅 SQL Server 2012 联机丛书，网址为 [http://go.microsoft.com/fwlink/?linkid=218015\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=218015%26clcid=0x804)。

> [!NOTE]  
> 如果要在 Windows Server 2008 R2 SP1 上安装 Lync Server 2013，必须首先安装 Microsoft 知识库文章 2646886“修复：在 IIS 7.5 中，当模块调用 InsertEntityBody 方法时，出现堆损坏”中描述的更新，网址为 <a href="http://go.microsoft.com/fwlink/?linkid=3052%26clcid=0x804" class="uri">http://go.microsoft.com/fwlink/?linkid=3052&amp;clcid=0x804</a>。<br />
您也必须按知识库文章<a href="http://go.microsoft.com/fwlink/p/?linkid=506893">事件 ID 32402 和 61045 被记录到安装在运行 Windows Server 2012 R2 系统的电脑中的 Lync Server 2013 前端服务器中</a>中所述修改注册表。



## 在服务器上安装 Windows 更新

在每台服务器上安装 Windows 更新中的以下更新：

  - **适用于运行 Lync Server 2013 的服务器的 Windows 更新**   有关运行 Lync Server 2013 的服务器所需的 Windows 更新 中的更新的详细信息，请参阅规划文档中的[Lync Server 2013 的其他软件要求](lync-server-2013-additional-software-requirements.md)。

  - **数据库服务器**   有关数据库服务器（包括后端数据库、 存档数据库和 监控数据库）所需的 Windows 更新中的更新的详细信息，请参阅 SQL Server 2012 文档。对于 SQL Server 2012，请参阅 SQL Server 2012 联机丛书，网址为 [http://go.microsoft.com/fwlink/?linkid=218015\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=218015%26clcid=0x804)。

## 在服务器上安装其他必备软件

Lync Server 2013 需要在服务器上安装以下其他软件：

  - **运行 Lync Server 2013 的服务器的必备软件**   运行 Lync Server 2013 的服务器的其他必备软件取决于要部署的服务器角色。有关每台服务器的特定软件要求的详细信息，请参阅规划文档中的[Lync Server 2013 的其他软件要求](lync-server-2013-additional-software-requirements.md)。

  - **Windows Identity Foundation**   Lync Server 2013 需要安装 Windows Identity Foundation 才能支持服务器到服务器身份验证方案。要确认您的计算机上是否已安装该软件，请转至控制面板，依次单击“程序和功能”、“查看已安装的更新”，并在“Microsoft Windows”下查找。有关安装 Windows Identity Foundation 的详细信息，请参阅 [http://go.microsoft.com/fwlink/?linkid=204657\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=204657%26clcid=0x804)。

  - **Microsoft .NET Framework 4.5**    Lync Server 2013 需要 Microsoft .NET Framework 4.5 64 位版本。

  - **数据库服务器的必备软件**   有关数据库服务器（包括后端数据库、 存档数据库和 监控数据库）所需的 Windows 更新的详细信息，请参阅 SQL Server 2012 文档，网址为 [http://go.microsoft.com/fwlink/?linkid=218015\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=218015%26clcid=0x804)。
    
    > [!NOTE]  
    > Lync Server 2013 会在每台 Standard Edition Server和每台运行包含本地配置存储的 Lync Server 2013 的服务器上自动安装 Microsoft SQL Server 2012 Express。
    


  - **Windows Media Format Runtime**    将要部署会议的所有 前端服务器 和 Standard Edition 服务器 都必须已安装 Windows Media Format Runtime。运行呼叫寄存、公告和响应组应用程序播放通知和音乐所需的 Windows Media 音频 (.wma) 文件时，必须使用 Windows Media Format Runtime。
    
    > [!NOTE]  
    > 对于 Windows Server 2012 和 Windows Server 2012 R2，请使用 Microsoft 媒体基础安装 Windows Media Format Runtime。
    
    
    > [!NOTE]  
    > 对于 Windows Server 2008 和 Windows Server 2008 R2，Windows Media Format Runtime 将作为 Windows 桌面体验的一部分安装。建议在安装 Lync Server 2013 之前安装 Windows 桌面体验。如果 Lync Server 2013 在服务器上找不到此软件，则它会提示您安装此软件，然后，必须重新启动服务器来完成安装。
    

