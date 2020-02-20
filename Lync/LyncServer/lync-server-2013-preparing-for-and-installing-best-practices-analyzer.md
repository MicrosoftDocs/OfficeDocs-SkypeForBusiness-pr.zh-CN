---
title: Lync Server 2013：准备和安装最佳实践分析工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for and installing Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48184149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 303df28b307a2d23bdc468d1c53977030d0cf8df
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="992f4-102">在 Lync Server 2013 中准备和安装最佳实践分析程序</span><span class="sxs-lookup"><span data-stu-id="992f4-102">Preparing for and installing Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="992f4-103">_**上次修改的主题：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="992f4-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="992f4-104">您必须以 Administrators 组的成员身份登录以执行本主题中介绍的任务。</span><span class="sxs-lookup"><span data-stu-id="992f4-104">You must be logged on as a member of the Administrators group to perform the tasks that are described in this topic.</span></span>

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a><span data-ttu-id="992f4-105">最佳做法分析器安装的系统要求</span><span class="sxs-lookup"><span data-stu-id="992f4-105">System Requirements for Best Practices Analyzer Installation</span></span>

<span data-ttu-id="992f4-106">若要运行 Lync Server 2013 （最佳实践分析工具来扫描环境），计算机必须运行以下操作系统之一的64位版本：</span><span class="sxs-lookup"><span data-stu-id="992f4-106">To run Lync Server 2013, Best Practices Analyzer to scan your environment, the computer must be running a 64-bit edition of one of the following operating systems:</span></span>

  - <span data-ttu-id="992f4-107">Windows Server 2008 R2 Service Pack 1 （SP1）标准操作系统</span><span class="sxs-lookup"><span data-stu-id="992f4-107">Windows Server 2008 R2 with Service Pack 1 (SP1) Standard operating system</span></span>

  - <span data-ttu-id="992f4-108">Windows Server 2008 R2 SP1 Enterprise 操作系统</span><span class="sxs-lookup"><span data-stu-id="992f4-108">Windows Server 2008 R2 with SP1 Enterprise operating system</span></span>

  - <span data-ttu-id="992f4-109">Windows Server 2008 R2 （包含 SP1 Datacenter 操作系统）</span><span class="sxs-lookup"><span data-stu-id="992f4-109">Windows Server 2008 R2 with SP1 Datacenter operating system</span></span>

  - <span data-ttu-id="992f4-110">Windows Server 2012 Datacenter 操作系统</span><span class="sxs-lookup"><span data-stu-id="992f4-110">Windows Server 2012 Datacenter operating system</span></span>

  - <span data-ttu-id="992f4-111">Windows Server 2012 标准操作系统</span><span class="sxs-lookup"><span data-stu-id="992f4-111">Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="992f4-112">Windows Server 2012 企业版操作系统</span><span class="sxs-lookup"><span data-stu-id="992f4-112">Windows Server 2012 Enterprise operating system</span></span>

  - <span data-ttu-id="992f4-113">Windows Server 2012 R2 Datacenter 操作系统</span><span class="sxs-lookup"><span data-stu-id="992f4-113">Windows Server 2012 R2 Datacenter operating system</span></span>

  - <span data-ttu-id="992f4-114">Windows Server 2012 R2 Standard 操作系统</span><span class="sxs-lookup"><span data-stu-id="992f4-114">Windows Server 2012 R2 Standard operating system</span></span>

  - <span data-ttu-id="992f4-115">Windows Server 2012 R2 Enterprise 操作系统</span><span class="sxs-lookup"><span data-stu-id="992f4-115">Windows Server 2012 R2 Enterprise operating system</span></span>

  - <span data-ttu-id="992f4-116">Windows 8 操作系统</span><span class="sxs-lookup"><span data-stu-id="992f4-116">Windows 8 operating system</span></span>

  - <span data-ttu-id="992f4-117">Windows 7 操作系统</span><span class="sxs-lookup"><span data-stu-id="992f4-117">Windows 7 operating system</span></span>

<span data-ttu-id="992f4-118">计算机还必须运行：</span><span class="sxs-lookup"><span data-stu-id="992f4-118">The computer must also be running the following:</span></span>

  - <span data-ttu-id="992f4-119">Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="992f4-119">Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="992f4-120">对于 Lync Server 2013，在安装 Lync Server 2013 之前，必须在服务器上手动安装64位版本的 Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="992f4-120">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span>

  - <span data-ttu-id="992f4-121">Lync Server 2013 核心组件。</span><span class="sxs-lookup"><span data-stu-id="992f4-121">Lync Server 2013, Core Components.</span></span>

  - <span data-ttu-id="992f4-122">WMI 向后兼容包。</span><span class="sxs-lookup"><span data-stu-id="992f4-122">WMI Backward Compatibility Package.</span></span> <span data-ttu-id="992f4-123">有关详细信息，请参阅迁移文档中的[安装 WMI 后向兼容性程序包](install-wmi-backward-compatibility-package.md)。</span><span class="sxs-lookup"><span data-stu-id="992f4-123">For details, see [Install WMI Backward Compatibility package](install-wmi-backward-compatibility-package.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="992f4-124">Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="992f4-124">Windows PowerShell 3.0.</span></span> <span data-ttu-id="992f4-125">有关详细信息，请参阅部署文档中的[安装 Windows PowerShell 3.0 For Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) 。</span><span class="sxs-lookup"><span data-stu-id="992f4-125">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) in the Deployment documentation.</span></span>

<span data-ttu-id="992f4-126">您可以在具有不运行 Lync Server 2013、核心组件或 WMI 向后兼容性程序包的受支持操作系统的计算机上安装最佳实践分析工具，但只能在这些计算机上使用最佳实践分析工具来查看报告，而不是运行扫描。</span><span class="sxs-lookup"><span data-stu-id="992f4-126">You can install Best Practices Analyzer on computers with a supported operating system that are not running Lync Server 2013, Core Components or WMI Backward Compatibility Package, but you can use Best Practices Analyzer on those computers only to view reports, not to run scans.</span></span>

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a><span data-ttu-id="992f4-127">选择计算机以进行安装</span><span class="sxs-lookup"><span data-stu-id="992f4-127">Choosing a Computer for Installation</span></span>

<span data-ttu-id="992f4-128">我们建议您在专用于 Lync Server 2013 管理的计算机上安装 Lync Server 2013 和最佳实践分析工具。</span><span class="sxs-lookup"><span data-stu-id="992f4-128">We recommend that you install Lync Server 2013, Best Practices Analyzer on a computer that is dedicated to Lync Server 2013 management.</span></span> <span data-ttu-id="992f4-129">可以在运行 Lync Server 2013 的服务器或运行 Lync Server 2013 管理工具的管理计算机上安装该工具。</span><span class="sxs-lookup"><span data-stu-id="992f4-129">You can install the tool on a server running Lync Server 2013 or an administrative computer running Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="992f4-130">如果您在运行 Lync Server 的服务器上安装该工具，我们建议您使用该工具仅扫描该服务器。</span><span class="sxs-lookup"><span data-stu-id="992f4-130">If you install the tool on a server that is running Lync Server, we recommend that you use the tool to scan only that server.</span></span>

</div>

<div>

## <a name="installing-best-practices-analyzer"></a><span data-ttu-id="992f4-131">安装最佳做法分析器</span><span class="sxs-lookup"><span data-stu-id="992f4-131">Installing Best Practices Analyzer</span></span>

<span data-ttu-id="992f4-132">你可以在上[https://go.microsoft.com/fwlink/p/?linkId=266539](https://go.microsoft.com/fwlink/p/?linkid=266539)下载适用于 Lync Server 2013 的最佳实践分析工具。</span><span class="sxs-lookup"><span data-stu-id="992f4-132">You can download the Best Practices Analyzer for Lync Server 2013 at [https://go.microsoft.com/fwlink/p/?linkId=266539](https://go.microsoft.com/fwlink/p/?linkid=266539).</span></span>

<span data-ttu-id="992f4-133">若要安装最佳做法分析器，请在要安装此工具的计算机上启动 Microsoft Installer 文件 RtcBPA.msi，然后按照屏幕上显示的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="992f4-133">To install Best Practices Analyzer, start the Microsoft Installer file RtcBPA.msi on the computer where you want to install the tool, and then follow the instructions on the screen.</span></span> <span data-ttu-id="992f4-134">安装程序文件的默认\<位置是系统驱动器\>\\程序文件\\Lync Server 2013\\BPA。</span><span class="sxs-lookup"><span data-stu-id="992f4-134">The default location for installing the program files is \<system drive\>\\Program Files\\Lync Server 2013\\BPA.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

