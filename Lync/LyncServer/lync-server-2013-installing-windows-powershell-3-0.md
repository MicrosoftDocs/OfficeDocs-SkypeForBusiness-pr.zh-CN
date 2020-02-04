---
title: Lync Server 2013：安装 Windows PowerShell 3.0
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
ms.openlocfilehash: 7cd8b4b48f2ff5a50ef7cafc1ec39671f672670f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-windows-powershell-30-for-lync-server-2013"></a>为 Lync Server 2013 安装 Windows PowerShell 3.0

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-06-27_

若要成功部署 Lync Server 2013，你需要在你的 Lync Server 拓扑中的每台计算机上都需要 Windows PowerShell 3.0。

现在，对于运行 Windows Server 2012 或 Windows Server 2012 R2 的系统，你无需在此处执行任何操作，并且可以继续执行部署的下一个阶段，因为这些操作系统附带了 PowerShell 3.0。

<div>


> [!IMPORTANT]  
> 但对于运行 Windows Server 2008 R2 SP1 的系统，你需要在安装 Lync Server 2013 之前安装 PowerShell 3.0 作为先决条件，否则你的操作将不起作用。 若要安装 PowerShell 3.0，请参阅<A href="http://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</A>。 这是指向 PowerShell 3.0 下载页面的直接链接，以及与成功安装相关的信息。



</div>

完成安装后，或者仅想要检查并确保在继续 Lync Server 部署之前，如果执行此操作，确认 PowerShell 3.0 位于服务器上非常简单：

1.  在要检查的服务器上，依次选择 "**开始**"、"**所有程序**"、"**附件**"、" **Windows PowerShell**"，然后单击 " **windows powershell**"。

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

