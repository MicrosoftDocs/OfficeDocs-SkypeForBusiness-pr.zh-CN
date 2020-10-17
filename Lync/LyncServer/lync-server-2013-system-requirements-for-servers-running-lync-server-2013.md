---
title: Lync Server 2013：运行 Lync Server 2013 的服务器的系统要求
description: Lync Server 2013：运行 Lync Server 2013 的服务器的系统要求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b85940294e35a953d4ffb9c07bfdaba79141485
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562648"
---
# <a name="system-requirements-for-servers-running-lync-server-2013"></a><span data-ttu-id="d43ce-103">运行 Lync Server 2013 的服务器的系统要求</span><span class="sxs-lookup"><span data-stu-id="d43ce-103">System requirements for servers running Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d43ce-104">_**上次修改的主题：** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="d43ce-104">_**Topic Last Modified:** 2014-07-24_</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="d43ce-105">有关硬件要求的详细信息，请参阅 <A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 的服务器硬件平台</A>。</span><span class="sxs-lookup"><span data-stu-id="d43ce-105">For details about hardware requirements, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="d43ce-106">Standard Edition 和 Enterprise Edition 服务器共用相同的软件要求。</span><span class="sxs-lookup"><span data-stu-id="d43ce-106">Standard Edition and Enterprise Edition servers share the same software requirements.</span></span>

<span data-ttu-id="d43ce-107">运行 Lync Server 2013 的服务器的企业版适用于大型组织作为组织的主要部署。</span><span class="sxs-lookup"><span data-stu-id="d43ce-107">Servers running Lync Server 2013, Enterprise Edition are intended for large organizations as the main organizational deployment.</span></span> <span data-ttu-id="d43ce-108">Enterprise Edition Server 的设计规模为每个池大约承载 80,000 个用户。</span><span class="sxs-lookup"><span data-stu-id="d43ce-108">Enterprise Edition server is designed to scale to approximately 80,000 homed users per pool.</span></span> <span data-ttu-id="d43ce-109">运行 Lync Server 2013 的服务器的 Standard Edition 适用于从组织的主部署中的小型组织和远程位置。</span><span class="sxs-lookup"><span data-stu-id="d43ce-109">Servers running Lync Server 2013, Standard Edition are intended for smaller organizations and remote locations from the main organization deployment.</span></span> <span data-ttu-id="d43ce-110">一对 Standard Edition 服务器最多可支持5000个用户。。</span><span class="sxs-lookup"><span data-stu-id="d43ce-110">One pair of Standard Edition servers can support up to 5,000 users..</span></span> <span data-ttu-id="d43ce-111">有关 Standard Edition server 和 Enterprise Edition server 之间的差异的详细信息，请参阅 [Lync Server 2013 的部署概述](lync-server-2013-deployment-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d43ce-111">For details on the differences between Standard Edition servers and Enterprise Edition servers, see [Deployment overview for Lync Server 2013](lync-server-2013-deployment-overview.md).</span></span>

<div>

## <a name="operating-system-installation"></a><span data-ttu-id="d43ce-112">操作系统安装</span><span class="sxs-lookup"><span data-stu-id="d43ce-112">Operating System Installation</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="d43ce-113">Lync Server 2013 仅适用于64位版本，它需要64位硬件和一种64版本的 Windows Server 操作系统。</span><span class="sxs-lookup"><span data-stu-id="d43ce-113">Lync Server 2013 is available only in a 64-bit edition, which requires 64-bit hardware and a 64-bit edition of the Windows Server operating system.</span></span> <span data-ttu-id="d43ce-114">在此版本中，Lync Server 2013 的32位版本不可用。</span><span class="sxs-lookup"><span data-stu-id="d43ce-114">A 32-bit edition of Lync Server 2013 is not available with this release.</span></span>



</div>

<span data-ttu-id="d43ce-115">Standard Edition 和 Enterprise Edition server 可以使用以下任一项：</span><span class="sxs-lookup"><span data-stu-id="d43ce-115">Standard Edition and Enterprise Edition server can use any of the following:</span></span>

  - <span data-ttu-id="d43ce-116">Windows Server 2008 R2 SP1 或最新 service pack</span><span class="sxs-lookup"><span data-stu-id="d43ce-116">Windows Server 2008 R2 SP1 or latest service pack</span></span>

  - <span data-ttu-id="d43ce-117">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="d43ce-117">Windows Server 2012</span></span>

  - <span data-ttu-id="d43ce-118">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d43ce-118">Windows Server 2012 R2</span></span>

<span data-ttu-id="d43ce-119">在 Standard Edition Server 或 Enterprise Edition 前端服务器上安装操作系统软件。</span><span class="sxs-lookup"><span data-stu-id="d43ce-119">Install the operating system software on the Standard Edition Server or Enterprise Edition Front End Server.</span></span> <span data-ttu-id="d43ce-120">应用所有更新以使操作系统达到最新更新以及与组织标准一致的必需更新级别。</span><span class="sxs-lookup"><span data-stu-id="d43ce-120">Apply all updates in order to bring the operating system up to the latest update and required update level consistent with your organization’s standards.</span></span> <span data-ttu-id="d43ce-121">有关操作要求的更多详细信息，请参阅可支持性文档中的 [Lync server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md) 。</span><span class="sxs-lookup"><span data-stu-id="d43ce-121">For more details about the operating requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

> [!NOTE] 
> <span data-ttu-id="d43ce-122">Lync Server 2013 不支持操作系统的就地升级。</span><span class="sxs-lookup"><span data-stu-id="d43ce-122">In-place upgrade of the operating system is not supported with Lync Server 2013.</span></span>  <span data-ttu-id="d43ce-123">您必须部署单独的池，并将用户迁移到具有不同操作系统的新池。</span><span class="sxs-lookup"><span data-stu-id="d43ce-123">You must deploy a separate pool and migrate users to the new pool with a different operating system.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="d43ce-124">若要在 Windows Server 2012 R2 上运行 Lync Server 2013，您可能需要在 Windows Server 中更改注册表项的值。</span><span class="sxs-lookup"><span data-stu-id="d43ce-124">For Lync Server 2013 to work on Windows Server 2012 R2, you may need to change the value of a registry key in Windows Server.</span></span> <span data-ttu-id="d43ce-125">若要使证书正常工作，并且要向 Survivable 分支机构注册的客户端，可能需要进行此更改。</span><span class="sxs-lookup"><span data-stu-id="d43ce-125">This change may be necessary for certificates to work correctly, and for clients to register with Survivable Branch Appliances.</span></span> <span data-ttu-id="d43ce-126">有关详细信息，请参阅 <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A> 。</span><span class="sxs-lookup"><span data-stu-id="d43ce-126">For more information, see <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A>.</span></span>



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a><span data-ttu-id="d43ce-127">Lync Server 2013 的其他软件</span><span class="sxs-lookup"><span data-stu-id="d43ce-127">Additional Software for Lync Server 2013</span></span>

<span data-ttu-id="d43ce-128">除了操作系统所需的更新外，Lync Server 2013 还需要操作系统角色、功能和软件才能运行。</span><span class="sxs-lookup"><span data-stu-id="d43ce-128">In addition to the updates required for the operating system, Lync Server 2013 requires operating system roles, features, and software to operate.</span></span> <span data-ttu-id="d43ce-129">有关在发布拓扑和安装 Lync Server 2013 之前必须安装的其他软件的详细信息，请参阅规划文档中的 [其他软件要求（Lync server 2013](lync-server-2013-additional-software-requirements.md) ）。</span><span class="sxs-lookup"><span data-stu-id="d43ce-129">For details about the additional software that must be installed prior to publishing your topology and installing Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a><span data-ttu-id="d43ce-130">所有服务器角色所需的其他软件</span><span class="sxs-lookup"><span data-stu-id="d43ce-130">Additional Software Necessary for All Server Roles</span></span>

<span data-ttu-id="d43ce-131">在所有服务器角色上，还必须确保安装了 Windows PowerShell 命令行接口3.0 和 Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="d43ce-131">On all server roles, you must also make sure that Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are installed.</span></span>

<span data-ttu-id="d43ce-132">此外，在任何将运行 Lync Server 管理工具的计算机上都需要 Windows PowerShell 命令行接口3.0 和 Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="d43ce-132">Additionally, Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are required on any computer where you will run the Lync Server administrative tools.</span></span>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="d43ce-133">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="d43ce-133">Windows PowerShell 3.0</span></span>

<span data-ttu-id="d43ce-134">Lync Server 2013 要求您在将参与 Lync Server 拓扑的每台计算机上安装 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="d43ce-134">Lync Server 2013 requires you to install Windows PowerShell 3.0 on each computer that will take part in your Lync Server topology.</span></span> <span data-ttu-id="d43ce-135">有关安装 Windows PowerShell 3.0 的详细信息，请参阅 [安装 Windows powershell 3.0 For Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)。</span><span class="sxs-lookup"><span data-stu-id="d43ce-135">For details about installing Windows PowerShell 3.0, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="d43ce-136">在 Windows Server &nbsp; 2008 &nbsp; R2 SP1 上，在安装 Microsoft .net Framework 4.5 之前，不能安装 windows PowerShell 命令行界面3.0。</span><span class="sxs-lookup"><span data-stu-id="d43ce-136">On Windows Server&nbsp;2008&nbsp;R2 with SP1, Windows PowerShell command-line interface 3.0 cannot be installed before installing Microsoft .NET Framework 4.5.</span></span>



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="d43ce-137">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="d43ce-137">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="d43ce-138">在将在 Windows Server 2012 或 Windows Server 2012 R2 上运行 Lync Server 2013 的服务器上安装 Microsoft .NET Framework 4.5 时，必须执行一个额外的步骤。</span><span class="sxs-lookup"><span data-stu-id="d43ce-138">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 on Windows Server 2012 or Windows Server 2012 R2, you must perform one additional step.</span></span> <span data-ttu-id="d43ce-139">安装 .NET Framework 4.5 后，请使用服务器管理器安装 HTTP 激活。</span><span class="sxs-lookup"><span data-stu-id="d43ce-139">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="d43ce-140">**在 Windows Server 2012 或 Windows Server 2012 R2 上安装 .NET 4.5 HTTP 激活**</span><span class="sxs-lookup"><span data-stu-id="d43ce-140">**To Install .NET 4.5 HTTP Activation on Windows Server 2012 or Windows Server 2012 R2**</span></span>

1.  <span data-ttu-id="d43ce-141">从 " **开始** " 菜单中，单击 " **程序**"，再单击 " **管理工具**"，然后单击 " **服务器管理器**"。</span><span class="sxs-lookup"><span data-stu-id="d43ce-141">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="d43ce-142">在服务器管理器中的 " **功能摘要**" 下，选择 " **添加功能**"。</span><span class="sxs-lookup"><span data-stu-id="d43ce-142">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="d43ce-143">展开 **.Net Framework 4.5**。</span><span class="sxs-lookup"><span data-stu-id="d43ce-143">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="d43ce-144">选择 " **WCF 激活** " （如果尚未选中）。</span><span class="sxs-lookup"><span data-stu-id="d43ce-144">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="d43ce-145">然后选择 " **HTTP 激活**"。</span><span class="sxs-lookup"><span data-stu-id="d43ce-145">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="d43ce-146">单击 " **下一步** " 并按照提示完成安装。</span><span class="sxs-lookup"><span data-stu-id="d43ce-146">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

