---
title: 在服务器上安装操作系统和必备软件
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
ms.openlocfilehash: 69ad97d578073e2b0f9ed08d929007c33e59b8fd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a><span data-ttu-id="611cd-102">在服务器上安装适用于 Lync Server 2013 的操作系统和必备软件</span><span class="sxs-lookup"><span data-stu-id="611cd-102">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="611cd-103">_**上次修改的主题：** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="611cd-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="611cd-104">设置硬件和系统基础结构后，需要在要部署的每台服务器上安装相应的 Windows 操作系统及更新，以及其他所有必备软件。</span><span class="sxs-lookup"><span data-stu-id="611cd-104">After you have set up the hardware and system infrastructure, you need to install the appropriate Windows operating systems and updates, in addition to all other prerequisite software on each server that you are deploying.</span></span> <span data-ttu-id="611cd-105">这包括每个 Lync Server 2013 服务器角色以及您的部署所需的任何其他运行 SQL Server 的基础结构服务器或服务器。</span><span class="sxs-lookup"><span data-stu-id="611cd-105">This includes each Lync Server 2013 server role and any additional infrastructure servers or servers running SQL Server that are required for your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="611cd-106">本节介绍操作系统和内部服务器必备软件的安装。</span><span class="sxs-lookup"><span data-stu-id="611cd-106">This section describes installation of operating systems and prerequisite software for internal servers.</span></span> <span data-ttu-id="611cd-107">如果要部署边缘服务器以支持外部用户访问，则还需要为这些服务器（包括边缘服务器和反向代理服务器）安装操作系统和必备软件。</span><span class="sxs-lookup"><span data-stu-id="611cd-107">If you are deploying Edge Servers to support external user access, you also need to install operating systems and prerequisite software for those servers, including Edge Servers and reverse proxy servers.</span></span> <span data-ttu-id="611cd-108">有关准备服务器以支持外部用户访问的详细信息，请参阅部署文档中的在<A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">外围网络中为 Lync Server 2013 安装服务器的准备</A>工作。</span><span class="sxs-lookup"><span data-stu-id="611cd-108">For details about preparing servers to support external user access, see <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a><span data-ttu-id="611cd-109">在服务器上安装 Windows 操作系统</span><span class="sxs-lookup"><span data-stu-id="611cd-109">Install Windows Operating Systems on Servers</span></span>

<span data-ttu-id="611cd-110">在要部署的每台服务器上，安装相应的 Windows 操作系统，如下所示：</span><span class="sxs-lookup"><span data-stu-id="611cd-110">On each server that you are deploying, install the appropriate Windows operating system as follows:</span></span>

  - <span data-ttu-id="611cd-111">**运行 lync server 2013**   的服务器有关运行 lync server 2013 的服务器的操作系统要求的详细信息，请参阅可支持性文档中的[Lync server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)。</span><span class="sxs-lookup"><span data-stu-id="611cd-111">**Servers running Lync Server 2013**   For details about the operating system requirements for servers running Lync Server 2013, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="611cd-112">**数据库服务器**   有关数据库服务器的操作系统要求的详细信息（包括后端数据库、存档数据库和监视数据库），请参阅 SQL Server 文档。</span><span class="sxs-lookup"><span data-stu-id="611cd-112">**Database servers**   For details about operating system requirements for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server documentation.</span></span> <span data-ttu-id="611cd-113">有关 SQL Server 2012，请参阅上[https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015)的 sql Server 2012 联机丛书。</span><span class="sxs-lookup"><span data-stu-id="611cd-113">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="611cd-114">如果要在 Windows Server&nbsp;2008&nbsp;R2 SP1 上安装 Lync Server 2013，则必须先安装 Microsoft 知识库文章 2646886 "修复：当模块在 IIS 7.5 中调用 InsertEntityBody 方法时出现堆损坏"，时间<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp为; http://go.microsoft.com/fwlink/?linkid=3052&kbid=823018 = 2646886</A>。</span><span class="sxs-lookup"><span data-stu-id="611cd-114">If you are installing Lync Server 2013 on Windows Server&nbsp;2008&nbsp;R2 with SP1, you must first install the update described in the Microsoft Knowledge Based article 2646886, “FIX: Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5”, at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2646886</A>.</span></span><BR><span data-ttu-id="611cd-115">您还必须修改注册表，如知识库文章中所述，在<A href="https://go.microsoft.com/fwlink/p/?linkid=506893">Windows Server 2012 R2 中安装的 Lync Server 2013 前端服务器中记录了事件 id 32402，61045</A>。</span><span class="sxs-lookup"><span data-stu-id="611cd-115">You must also modify the registry as described in the KB article, <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">Event IDs 32402, 61045 are logged in Lync Server 2013 Front End servers that are installed in Windows Server 2012 R2</A>.</span></span>



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a><span data-ttu-id="611cd-116">在服务器上安装 Windows Update</span><span class="sxs-lookup"><span data-stu-id="611cd-116">Install Windows Update on Servers</span></span>

<span data-ttu-id="611cd-117">在每台服务器上安装 Windows 更新中的以下更新：</span><span class="sxs-lookup"><span data-stu-id="611cd-117">Install the following updates from Windows Update on each server:</span></span>

  - <span data-ttu-id="611cd-118">**运行 lync server 2013**   的服务器的 Windows update 有关运行 lync server 2013 的服务器所需的来自 Windows Update 的更新的详细信息，请参阅规划文档中[Lync Server 2013 的其他软件要求](lync-server-2013-additional-software-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="611cd-118">**Windows Update for servers running Lync Server 2013**   For details about the updates from Windows Update that are required for servers running Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="611cd-119">**数据库服务器**   有关数据库服务器（包括后端数据库、存档数据库和监视数据库）所需的 Windows 更新中的更新的详细信息，请参阅 SQL Server 2012 文档。</span><span class="sxs-lookup"><span data-stu-id="611cd-119">**Database servers**   For details about the updates from Windows Update that are required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation.</span></span> <span data-ttu-id="611cd-120">有关 SQL Server 2012，请参阅上[https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015)的 sql Server 2012 联机丛书。</span><span class="sxs-lookup"><span data-stu-id="611cd-120">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a><span data-ttu-id="611cd-121">在服务器上安装其他必备软件</span><span class="sxs-lookup"><span data-stu-id="611cd-121">Install Other Prerequisite Software on Servers</span></span>

<span data-ttu-id="611cd-122">Lync Server 2013 要求在服务器上安装以下附加软件：</span><span class="sxs-lookup"><span data-stu-id="611cd-122">Lync Server 2013 requires the installation of the following additional software on servers:</span></span>

  - <span data-ttu-id="611cd-123">**运行 lync server 2013**   的服务器的必备软件。运行 lync server 2013 的服务器的其他必备软件取决于要部署的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="611cd-123">**Prerequisite software for servers running Lync Server 2013**   The additional software prerequisites for servers running Lync Server 2013 depend on the server role being deployed.</span></span> <span data-ttu-id="611cd-124">有关每台服务器的特定软件要求的详细信息，请参阅规划文档中的[Lync server 2013 的其他软件要求](lync-server-2013-additional-software-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="611cd-124">For details about the specific software requirements for each server, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="611cd-125">**Windows identity foundation**   Lync Server 2013 要求安装 Windows Identity Foundation，以便支持服务器到服务器身份验证方案。</span><span class="sxs-lookup"><span data-stu-id="611cd-125">**Windows Identity Foundation**   Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server-to-server authentication scenarios.</span></span> <span data-ttu-id="611cd-126">若要验证是否已将其安装在你的计算机上，请转到 "控制面板"，单击 "**程序和功能**"，**查看已安装的更新**，然后查看 " **Microsoft Windows**"。</span><span class="sxs-lookup"><span data-stu-id="611cd-126">To verify that it has already been installed on your computer, go to Control Panel, click **Programs and Features**, **View installed updates**, and look under **Microsoft Windows**.</span></span> <span data-ttu-id="611cd-127">有关安装 Windows Identity Foundation 的详细信息， [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)请参阅。</span><span class="sxs-lookup"><span data-stu-id="611cd-127">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="611cd-128">**Microsoft .net framework 4.5**   Lync Server 2013 需要64位版本的 microsoft .net framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="611cd-128">**Microsoft .NET Framework 4.5**   The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

  - <span data-ttu-id="611cd-129">**数据库服务器**   的必备软件有关数据库服务器（包括后端数据库、存档数据库和监视数据库）所需的 Windows 更新的详细信息，请参阅 SQL Server 2012 文档（网址[https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015)为）。</span><span class="sxs-lookup"><span data-stu-id="611cd-129">**Prerequisite software for database servers**   For details about the Windows Update required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="611cd-130">Lync Server 2013 会在每个 Standard Edition 服务器和运行本地配置存储所在的 Lync Server 2013 的每台服务器上自动安装 Microsoft SQL Server 2012 Express。</span><span class="sxs-lookup"><span data-stu-id="611cd-130">Lync Server 2013 automatically installs Microsoft SQL Server 2012 Express on each Standard Edition server and each server running Lync Server 2013 on which the local configuration store is located.</span></span>

    
    </div>

  - <span data-ttu-id="611cd-131">**Windows media 格式运行时**   要部署会议的所有前端服务器和 Standard Edition 服务器必须安装 Windows Media Format runtime。</span><span class="sxs-lookup"><span data-stu-id="611cd-131">**Windows Media Format Runtime**   All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed.</span></span> <span data-ttu-id="611cd-132">Windows Media Format Runtime 是运行呼叫寄存、通知和响应组应用程序播放通知和音乐时使用的 Windows Media 音频 (.wma) 文件所必需的软件。</span><span class="sxs-lookup"><span data-stu-id="611cd-132">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="611cd-133">对于 Windows Server 2012 和 Windows Server 2012 R2，Windows Media Format Runtime 在 Microsoft Media Foundation 中安装。</span><span class="sxs-lookup"><span data-stu-id="611cd-133">For Windows Server 2012 and Windows Server 2012 R2 the Windows Media Format Runtime installs with Microsoft Media Foundation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="611cd-134">对于 Windows Server&nbsp;2008 和 windows server&nbsp;2008&nbsp;R2，Windows Media Format Runtime 将作为 windows 桌面体验的一部分进行安装。</span><span class="sxs-lookup"><span data-stu-id="611cd-134">For Windows Server&nbsp;2008 and Windows Server&nbsp;2008&nbsp;R2 the Windows Media Format Runtime installs as part of the Windows Desktop Experience.</span></span> <span data-ttu-id="611cd-135">建议您在安装 Lync Server 2013 之前安装 Windows 桌面体验。</span><span class="sxs-lookup"><span data-stu-id="611cd-135">It is recommended that you install Windows Desktop Experience before you install Lync Server 2013.</span></span> <span data-ttu-id="611cd-136">如果 Lync Server 2013 在服务器上找不到此软件，它将提示您安装它，然后您必须重新启动服务器才能完成安装。</span><span class="sxs-lookup"><span data-stu-id="611cd-136">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

