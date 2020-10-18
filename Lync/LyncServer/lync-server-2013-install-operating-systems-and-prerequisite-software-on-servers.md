---
title: 在服务器上安装操作系统和必备软件
description: 在服务器上安装操作系统和必备软件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bae9e57db9c2f1d3f3bde7ce9cc7071b73aa01d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574128"
---
# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a>在服务器上安装适用于 Lync Server 2013 的操作系统和必备软件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-07-24_

设置硬件和系统基础结构后，需要在要部署的每台服务器上安装相应的 Windows 操作系统及更新，以及其他所有必备软件。 这包括每个 Lync Server 2013 服务器角色以及您的部署所需的任何其他运行 SQL Server 的基础结构服务器或服务器。

<div>


> [!NOTE]
> 本节介绍操作系统和内部服务器必备软件的安装。 如果要部署边缘服务器以支持外部用户访问，则还需要为这些服务器（包括边缘服务器和反向代理服务器）安装操作系统和必备软件。 有关准备服务器以支持外部用户访问的详细信息，请参阅部署文档中的在 <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">外围网络中为 Lync Server 2013 安装服务器的准备</A> 工作。



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a>在服务器上安装 Windows 操作系统

在要部署的每台服务器上，安装相应的 Windows 操作系统，如下所示：

  - **运行 Lync Server 2013**     的服务器有关运行 Lync Server 2013 的服务器的操作系统要求的详细信息，请参阅可支持性文档中的[Lync server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)。

  - **数据库服务器**    有关数据库服务器的操作系统要求的详细信息（包括后端数据库、存档数据库和监视数据库），请参阅 SQL Server 文档。 有关 SQL Server 2012，请参阅上的 SQL Server 2012 联机丛书 [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) 。

<div>


> [!NOTE]
> 如果要在 Windows Server 2008 R2 SP1 上安装 Lync Server 2013 &nbsp; &nbsp; ，则必须先安装 Microsoft 知识库文章 2646886 "修复：当模块在 IIS 7.5 中调用 InsertEntityBody 方法时出现堆损坏"，时间<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp 为; http://go.microsoft.com/fwlink/?linkid=3052&kbid=823018 = 2646886</A>。<BR>您还必须修改注册表，如知识库文章中所述，在 <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">Windows Server 2012 R2 中安装的 Lync Server 2013 前端服务器中记录了事件 id 32402，61045</A>。



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a>在服务器上安装 Windows Update

在每台服务器上安装 Windows 更新中的以下更新：

  - **运行 Lync Server 2013 的服务器的 Windows Update**    有关运行 Lync Server 2013 的服务器所需的 Windows Update 更新的详细信息，请参阅规划文档中[Lync Server 2013 的其他软件要求](lync-server-2013-additional-software-requirements.md)。

  - **数据库服务器**    有关数据库服务器（包括后端数据库、存档数据库和监视数据库）所需的 Windows 更新中的更新的详细信息，请参阅 SQL Server 2012 文档。 有关 SQL Server 2012，请参阅上的 SQL Server 2012 联机丛书 [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) 。

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a>在服务器上安装其他必备软件

Lync Server 2013 要求在服务器上安装以下附加软件：

  - **运行 Lync Server 2013 的服务器的必备软件**    运行 Lync Server 2013 的服务器的其他必备软件取决于要部署的服务器角色。 有关每台服务器的特定软件要求的详细信息，请参阅规划文档中的 [Lync server 2013 的其他软件要求](lync-server-2013-additional-software-requirements.md) 。

  - **Windows Identity Foundation**    Lync Server 2013 要求安装 Windows Identity Foundation，以便支持服务器到服务器身份验证方案。 若要验证是否已将其安装在你的计算机上，请转到 "控制面板"，单击 " **程序和功能**"， **查看已安装的更新**，然后查看 " **Microsoft Windows**"。 有关安装 Windows Identity Foundation 的详细信息，请参阅 [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) 。

  - **Microsoft .Net Framework 4.5**    Lync Server 2013 需要64位版本的 Microsoft .NET Framework 4.5。

  - **数据库服务器**     的必备软件有关数据库服务器（包括后端数据库、存档数据库和监视数据库）所需的 Windows 更新的详细信息，请参阅 SQL Server 2012 文档（网址为） [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) 。
    
    <div>
    

    > [!NOTE]
    > Lync Server 2013 会在每个 Standard Edition 服务器和运行本地配置存储所在的 Lync Server 2013 的每台服务器上自动安装 Microsoft SQL Server 2012 Express。

    
    </div>

  - **Windows Media Format Runtime**    将部署会议的所有前端服务器和 Standard Edition 服务器必须安装 Windows Media Format Runtime。 Windows Media Format Runtime 是运行呼叫寄存、通知和响应组应用程序播放通知和音乐时使用的 Windows Media 音频 (.wma) 文件所必需的软件。
    
    <div>
    

    > [!NOTE]
    > 对于 Windows Server 2012 和 Windows Server 2012 R2，Windows Media Format Runtime 在 Microsoft Media Foundation 中安装。

    
    </div>
    
    <div>
    

    > [!NOTE]
    > 对于 Windows Server &nbsp; 2008 和 Windows server &nbsp; 2008 &nbsp; R2，Windows Media Format Runtime 将作为 windows 桌面体验的一部分进行安装。 建议您在安装 Lync Server 2013 之前安装 Windows 桌面体验。 如果 Lync Server 2013 在服务器上找不到此软件，它将提示您安装它，然后您必须重新启动服务器才能完成安装。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

