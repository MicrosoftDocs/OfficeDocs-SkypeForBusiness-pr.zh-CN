---
title: Lync Server 2013：管理工具软件要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administrative tools software requirements
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195653(v=OCS.15)
ms:contentKeyID: 48183740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d1532acc21bc788adc8e52bfd1d562509e105ea
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administrative-tools-software-requirements-in-lync-server-2013"></a><span data-ttu-id="0405e-102">Lync Server 2013 中的管理工具软件要求</span><span class="sxs-lookup"><span data-stu-id="0405e-102">Administrative tools software requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0405e-103">_**上次修改的主题：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="0405e-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="0405e-104">本主题介绍除了操作系统要求之外，安装和使用 Lync Server 2013 管理工具所需的软件。</span><span class="sxs-lookup"><span data-stu-id="0405e-104">This topic describes the software required to install and use Lync Server 2013 administrative tools in addition to the operating system requirements.</span></span>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="0405e-105">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="0405e-105">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="0405e-106">Lync Server 2013 需要64位版本的 Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="0405e-106">The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="0405e-107">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="0405e-107">Windows PowerShell 3.0</span></span>

<span data-ttu-id="0405e-108">运行 Microsoft Lync Server 2013 的任何组件需要 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="0405e-108">Windows PowerShell 3.0 is required for running any component of Microsoft Lync Server 2013.</span></span> <span data-ttu-id="0405e-109">有关详细信息，请参阅[安装适用于 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。</span><span class="sxs-lookup"><span data-stu-id="0405e-109">For more information, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="windows-installer-version-45"></a><span data-ttu-id="0405e-110">Windows Installer 版本 4.5</span><span class="sxs-lookup"><span data-stu-id="0405e-110">Windows Installer Version 4.5</span></span>

<span data-ttu-id="0405e-111">Lync Server 2013 使用 Windows Installer 技术安装、卸载和维护各种服务器角色。</span><span class="sxs-lookup"><span data-stu-id="0405e-111">Lync Server 2013 uses Windows Installer technology to install, uninstall, and maintain various server roles.</span></span> <span data-ttu-id="0405e-112">Windows Installer 4.5 可用作 Windows Server 操作系统的可再发行组件。</span><span class="sxs-lookup"><span data-stu-id="0405e-112">Windows Installer version 4.5 is available as a redistributable component for the Windows Server operating system.</span></span> <span data-ttu-id="0405e-113">Windows Installer 4.5 附带 Windows Server 2012 R2、Windows Server 2012 和 Windows Server 2008 R2，这意味着您无需为任何运行 Lync Server 2013 的计算机下载该实用工具。</span><span class="sxs-lookup"><span data-stu-id="0405e-113">Windows Installer 4.5 ships with Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 meaning that you do not need to download the utility for any computer that is running Lync Server 2013.</span></span> <span data-ttu-id="0405e-114">（Lync Server 2013 仅可安装在运行 Windows Server 2012 R2、Windows Server 2012 或 Windows Server 2008 R2 的计算机上。）</span><span class="sxs-lookup"><span data-stu-id="0405e-114">(Lync Server 2013 can only be installed on computers running Windows Server 2012 R2, Windows Server 2012 or Windows Server 2008 R2.)</span></span>

<span data-ttu-id="0405e-115">但是，如果要在管理员工作站上安装 Lync Server 命令行管理程序或 Lync Server 拓扑生成器，可能需要下载 Windows Installer 4.5。</span><span class="sxs-lookup"><span data-stu-id="0405e-115">However, if you want to install Lync Server Management Shell or Lync Server Topology Builder on an administrator workstation you might need to download Windows Installer 4.5.</span></span> <span data-ttu-id="0405e-116">该实用工具附带 Windows 7 和 Windows 2008 R2，但不是在任何以前版本的 Windows 操作系统上提供。</span><span class="sxs-lookup"><span data-stu-id="0405e-116">That utility ships with Windows 7 and Windows 2008 R2 but not with any previous versions of the Windows operating system.</span></span> <span data-ttu-id="0405e-117">您可以从 Microsoft 下载中心下载 Windows Installer 4.5 <https://go.microsoft.com/fwlink/p/?linkid=197395>。</span><span class="sxs-lookup"><span data-stu-id="0405e-117">You can download Windows Installer 4.5 from the Microsoft Download Center at <https://go.microsoft.com/fwlink/p/?linkid=197395>.</span></span>

</div>

<div>

## <a name="microsoft-silverlight-5-browser-plug-in"></a><span data-ttu-id="0405e-118">Microsoft Silverlight 5 浏览器插件</span><span class="sxs-lookup"><span data-stu-id="0405e-118">Microsoft Silverlight 5 browser plug-in</span></span>

<span data-ttu-id="0405e-119">Lync Server 2013 控制面板是一种基于 web 的工具，需要安装最新版本的 Microsoft Silverlight 5 浏览器插件。</span><span class="sxs-lookup"><span data-stu-id="0405e-119">Lync Server 2013 Control Panel is a web-based tool and requires that you install the latest version of Microsoft Silverlight 5 browser plug-in.</span></span> <span data-ttu-id="0405e-120">当您启动 Lync Server 2013 控制面板时，如果未安装此软件或安装了早期版本，Lync Server 2013 控制面板将提示您安装所需的版本。</span><span class="sxs-lookup"><span data-stu-id="0405e-120">When you start Lync Server 2013 Control Panel, if this software is not installed or if an earlier version is installed, Lync Server 2013 Control Panel prompts you to install the required version.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0405e-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0405e-121">See Also</span></span>


[<span data-ttu-id="0405e-122">Lync Server 2013 中的服务器和工具操作系统支持</span><span class="sxs-lookup"><span data-stu-id="0405e-122">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="0405e-123">Lync Server 2013 中的管理工具基础结构要求</span><span class="sxs-lookup"><span data-stu-id="0405e-123">Administrative tools infrastructure requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[<span data-ttu-id="0405e-124">安装和管理 Lync Server 2013 所需的管理员权利和权限</span><span class="sxs-lookup"><span data-stu-id="0405e-124">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

