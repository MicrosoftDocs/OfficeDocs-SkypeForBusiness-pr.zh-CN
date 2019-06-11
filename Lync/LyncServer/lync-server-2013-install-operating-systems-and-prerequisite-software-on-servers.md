---
title: 在服务器上安装操作系统和必备软件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26a4eed86f12386b10b49d4290a4596b40c1fcc9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a>在服务器上安装适用于 Lync Server 2013 的操作系统和必备软件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-07-24_

设置硬件和系统基础结构后, 除了要部署的每台服务器上的所有其他必备软件外, 还需要安装相应的 Windows 操作系统和更新。 这包括每个 Lync Server 2013 服务器角色以及运行你的部署所需的任何其他基础结构服务器或运行 SQL Server 的服务器。

<div>


> [!NOTE]
> 本部分介绍安装内部服务器的操作系统和必备软件。 如果要部署边缘服务器以支持外部用户访问, 还需要为这些服务器安装操作系统和必备软件, 包括边缘服务器和反向代理服务器。 有关准备服务器以支持外部用户访问的详细信息, 请参阅部署文档中<A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Lync Server 2013 的外围网络中的服务器安装准备</A>。



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a>在服务器上安装 Windows 操作系统

在要部署的每台服务器上, 安装相应的 Windows 操作系统, 如下所示:

  - **运行 lync server 2013**   的服务器有关运行 lync server 2013 的服务器的操作系统要求的详细信息, 请参阅支持文档中[Lync server 2013 中的 "服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)"。

  - **数据库服务器**   有关数据库服务器的操作系统要求 (包括后端数据库、存档数据库和监视数据库) 的详细信息, 请参阅 SQL Server 文档。 有关 SQL Server 2012, 请参阅中[http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)的 sql Server 2012 联机丛书。

<div>


> [!NOTE]
> 如果在 Windows Server&nbsp;2008&nbsp;R2 上使用 SP1 安装 Lync Server 2013, 则必须首先安装 Microsoft 知识库文章 2646886 "修复: 当模块调用 InsertEntityBody 方法时发生堆损坏在 IIS 7.5 ", at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 2646886</A>。<BR>你还必须修改注册表, 如知识库文章中所述, 在<A href="http://go.microsoft.com/fwlink/p/?linkid=506893">Windows server 2012 R2 中安装的 Lync Server 2013 前端服务器中记录事件 id 32402、61045</A>。



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a>在服务器上安装 Windows 更新

在每台服务器上安装 Windows 更新中的以下更新:

  - ****   有关运行 lync server 2013 的服务器的 Windows 更新有关运行 lync server 2013 的服务器的更新的详细信息, 请参阅规划中[Lync Server 2013 的其他软件要求](lync-server-2013-additional-software-requirements.md)文档.

  - **数据库服务器**   有关数据库服务器 (包括后端数据库、存档数据库和监视数据库) 所需的 Windows 更新更新的详细信息, 请参阅 SQL Server 2012 文档。 有关 SQL Server 2012, 请参阅中[http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)的 sql Server 2012 联机丛书。

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a>在服务器上安装其他必备软件

Lync Server 2013 要求在服务器上安装以下其他软件:

  - **运行 lync server 2013**   的服务器必备软件对于运行 lync server 2013 的服务器, 其他软件必备条件取决于正在部署的服务器角色。 有关每台服务器的特定软件要求的详细信息, 请参阅规划文档中[Lync server 2013 的其他软件要求](lync-server-2013-additional-software-requirements.md)。

  - **Windows identity foundation**   Lync Server 2013 需要安装 Windows identity Foundation 才能支持服务器到服务器的身份验证方案。 若要验证是否已在计算机上安装, 请转到 "控制面板", 单击 "**程序和功能**",**查看已安装的更新**, 然后查看 " **Microsoft Windows**"。 有关安装 Windows Identity Foundation 的详细信息, [http://go.microsoft.com/fwlink/p/?linkId=204657](http://go.microsoft.com/fwlink/p/?linkid=204657)请参阅。

  - **Microsoft .net framework 4.5**   Lync Server 2013 需要64位版本的 microsoft .net framework 4.5。

  - **数据库服务器**   必备软件有关数据库服务器 (包括后端数据库、存档数据库和监视数据库) 所需的 Windows 更新的详细信息, 请参阅 SQL Server 2012 文档[http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)。
    
    <div>
    

    > [!NOTE]
    > Lync Server 2013 会在每个标准版服务器以及运行本地配置存储所在的 Lync Server 2013 的每台服务器上自动安装 Microsoft SQL Server 2012 Express。

    
    </div>

  - **Windows media 格式运行时**   要部署会议的所有前端服务器和标准版服务器必须安装 Windows Media Format runtime。 若要运行 windows Media 音频 (.wma) 文件, 需要 Windows Media Format Runtime 才能运行通知和音乐的 "呼叫寄存"、"通知" 和 "响应" 组应用程序。
    
    <div>
    

    > [!NOTE]
    > 对于 Windows Server 2012 和 Windows Server 2012 R2 Windows Media 格式运行时与 Microsoft Media Foundation 一起安装。

    
    </div>
    
    <div>
    

    > [!NOTE]
    > 对于 Windows Server&nbsp;2008 和 windows server&nbsp;2008&nbsp;R2 Windows Media 格式运行时作为 windows 桌面体验的一部分进行安装。 建议在安装 Lync Server 2013 之前安装 Windows 桌面体验。 如果 Lync Server 2013 在服务器上找不到此软件, 它将提示您安装它, 然后必须重新启动服务器才能完成安装。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

