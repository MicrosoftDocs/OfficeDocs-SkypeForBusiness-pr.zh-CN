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

# <a name="installing-windows-powershell-30-for-lync-server-2013"></a><span data-ttu-id="54f0f-102">为 Lync Server 2013 安装 Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="54f0f-102">Installing Windows PowerShell 3.0 for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54f0f-103">_**主题上次修改时间：** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="54f0f-103">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="54f0f-104">若要成功部署 Lync Server 2013，你需要在你的 Lync Server 拓扑中的每台计算机上都需要 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="54f0f-104">To deploy Lync Server 2013 successfully, you’ll need Windows PowerShell 3.0 on each computer that’s part of your Lync Server topology.</span></span>

<span data-ttu-id="54f0f-105">现在，对于运行 Windows Server 2012 或 Windows Server 2012 R2 的系统，你无需在此处执行任何操作，并且可以继续执行部署的下一个阶段，因为这些操作系统附带了 PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="54f0f-105">Now, for systems running Windows Server 2012 or Windows Server 2012 R2, you don’t need to do anything here, and can go ahead to the next stage of deployment, because PowerShell 3.0 is included with those operating systems.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="54f0f-106">但对于运行 Windows Server 2008 R2 SP1 的系统，你需要在安装 Lync Server 2013 之前安装 PowerShell 3.0 作为先决条件，否则你的操作将不起作用。</span><span class="sxs-lookup"><span data-stu-id="54f0f-106">But for systems running Windows Server 2008 R2 SP1, you’ll need to install PowerShell 3.0 as a prerequisite before you install Lync Server 2013, or things won’t work.</span></span> <span data-ttu-id="54f0f-107">若要安装 PowerShell 3.0，请参阅<A href="http://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</A>。</span><span class="sxs-lookup"><span data-stu-id="54f0f-107">To install PowerShell 3.0, see <A href="http://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</A>.</span></span> <span data-ttu-id="54f0f-108">这是指向 PowerShell 3.0 下载页面的直接链接，以及与成功安装相关的信息。</span><span class="sxs-lookup"><span data-stu-id="54f0f-108">This is a direct link to the PowerShell 3.0 download page, along with information relating to installing it successfully.</span></span>



</div>

<span data-ttu-id="54f0f-109">完成安装后，或者仅想要检查并确保在继续 Lync Server 部署之前，如果执行此操作，确认 PowerShell 3.0 位于服务器上非常简单：</span><span class="sxs-lookup"><span data-stu-id="54f0f-109">Once you’ve done the install, or if you just want to check and be sure before continuing with the Lync Server deployment, confirming that PowerShell 3.0 is on a server is pretty straightforward if you do this:</span></span>

1.  <span data-ttu-id="54f0f-110">在要检查的服务器上，依次选择 "**开始**"、"**所有程序**"、"**附件**"、" **Windows PowerShell**"，然后单击 " **windows powershell**"。</span><span class="sxs-lookup"><span data-stu-id="54f0f-110">On the server you want to check, choose **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>

2.  <span data-ttu-id="54f0f-111">在 Windows PowerShell 控制台中，在命令提示符处键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="54f0f-111">In the Windows PowerShell console, type the following command at the command prompt, and then press ENTER:</span></span>
    
        Get-Host | Select-Object Version

3.  <span data-ttu-id="54f0f-112">如果安装了 Windows PowerShell 3.0，你将看到如下所示的输出：</span><span class="sxs-lookup"><span data-stu-id="54f0f-112">If Windows PowerShell 3.0 is installed you’ll see output that looks like this:</span></span>
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

