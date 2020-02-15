---
title: Lync Server 2013：安装 Windows PowerShell 3。0
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35ab12cc2e00bf81bc17552253eb56417dde2c6e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-windows-powershell-30-for-lync-server-2013"></a>为 Lync Server 2013 安装 Windows PowerShell 3。0

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-06-27_

若要成功部署 Lync Server 2013，你需要在你的 Lync Server 拓扑中包含的每台计算机上都有 Windows PowerShell 3.0。

现在，对于运行 Windows Server 2012 或 Windows Server 2012 R2 的系统，不需要在此处执行任何操作，并且可以继续进行部署的下一个阶段，因为这些操作系统附带了 PowerShell 3.0。

<div>


> [!IMPORTANT]  
> 但对于运行 Windows Server 2008 R2 SP1 的系统，您需要在安装 Lync Server 2013 之前安装 PowerShell 3.0 作为先决条件，否则无法正常运行。 若要安装 PowerShell 3.0，请参阅<A href="http://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</A>。 这是指向 PowerShell 3.0 下载页面的直接链接，以及与成功安装相关的信息。



</div>

完成安装后，或者只想在继续 Lync Server 部署之前进行检查并确保，确认 PowerShell 3.0 在服务器上是非常简单的，如果执行此操作：

1.  在要检查的服务器上，依次选择 "**开始**"、"**所有程序**"、"**附件**" 和 **"Windows PowerShell"，** 然后单击 " **windows powershell**"。

2.  在 Windows PowerShell 控制台中，在命令提示符处键入以下命令，然后按 ENTER：
    
        Get-Host | Select-Object Version

3.  如果安装了 Windows PowerShell 3.0，你将看到如下所示的输出：
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

