---
title: Lync Server 2013：运行 Lync Server 2013 的服务器的系统要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ad30b9687c9566adb7936612e71ae9f41e69095
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-requirements-for-servers-running-lync-server-2013"></a><span data-ttu-id="48820-102">运行 Lync Server 2013 的服务器的系统要求</span><span class="sxs-lookup"><span data-stu-id="48820-102">System requirements for servers running Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48820-103">_**主题上次修改时间:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="48820-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="48820-104">有关硬件要求的详细信息, 请参阅<A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 的服务器硬件平台</A>。</span><span class="sxs-lookup"><span data-stu-id="48820-104">For details about hardware requirements, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="48820-105">标准版和企业版服务器共享相同的软件要求。</span><span class="sxs-lookup"><span data-stu-id="48820-105">Standard Edition and Enterprise Edition servers share the same software requirements.</span></span>

<span data-ttu-id="48820-106">对于运行 Lync Server 2013 的服务器, 企业版适用于作为主要组织部署的大型组织。</span><span class="sxs-lookup"><span data-stu-id="48820-106">Servers running Lync Server 2013, Enterprise Edition are intended for large organizations as the main organizational deployment.</span></span> <span data-ttu-id="48820-107">企业版服务器设计为每个池中大约80000穴用户。</span><span class="sxs-lookup"><span data-stu-id="48820-107">Enterprise Edition server is designed to scale to approximately 80,000 homed users per pool.</span></span> <span data-ttu-id="48820-108">运行 Lync Server 2013 的服务器的标准版适用于较小组织和组织内部部署中的远程位置。</span><span class="sxs-lookup"><span data-stu-id="48820-108">Servers running Lync Server 2013, Standard Edition are intended for smaller organizations and remote locations from the main organization deployment.</span></span> <span data-ttu-id="48820-109">一对标准版服务器最多可支持5000个用户。。</span><span class="sxs-lookup"><span data-stu-id="48820-109">One pair of Standard Edition servers can support up to 5,000 users..</span></span> <span data-ttu-id="48820-110">有关标准版服务器和企业版服务器之间的差异的详细信息, 请参阅[Lync Server 2013 的部署概述](lync-server-2013-deployment-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="48820-110">For details on the differences between Standard Edition servers and Enterprise Edition servers, see [Deployment overview for Lync Server 2013](lync-server-2013-deployment-overview.md).</span></span>

<div>

## <a name="operating-system-installation"></a><span data-ttu-id="48820-111">操作系统安装</span><span class="sxs-lookup"><span data-stu-id="48820-111">Operating System Installation</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="48820-112">Lync Server 2013 仅在64位版本中可用, 它需要64位硬件和 Windows Server 操作系统的一个64版本。</span><span class="sxs-lookup"><span data-stu-id="48820-112">Lync Server 2013 is available only in a 64-bit edition, which requires 64-bit hardware and a 64-bit edition of the Windows Server operating system.</span></span> <span data-ttu-id="48820-113">此版本不支持 Lync Server 2013 的32位版本。</span><span class="sxs-lookup"><span data-stu-id="48820-113">A 32-bit edition of Lync Server 2013 is not available with this release.</span></span>



</div>

<span data-ttu-id="48820-114">标准版和企业版服务器可以使用以下任何一种:</span><span class="sxs-lookup"><span data-stu-id="48820-114">Standard Edition and Enterprise Edition server can use any of the following:</span></span>

  - <span data-ttu-id="48820-115">Windows Server 2008 R2 SP1 或最新 service pack</span><span class="sxs-lookup"><span data-stu-id="48820-115">Windows Server 2008 R2 SP1 or latest service pack</span></span>

  - <span data-ttu-id="48820-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="48820-116">Windows Server 2012</span></span>

  - <span data-ttu-id="48820-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="48820-117">Windows Server 2012 R2</span></span>

<span data-ttu-id="48820-118">在标准版服务器或企业版前端服务器上安装操作系统软件。</span><span class="sxs-lookup"><span data-stu-id="48820-118">Install the operating system software on the Standard Edition Server or Enterprise Edition Front End Server.</span></span> <span data-ttu-id="48820-119">应用所有更新, 以使操作系统的最新更新和所需更新级别与组织的标准一致。</span><span class="sxs-lookup"><span data-stu-id="48820-119">Apply all updates in order to bring the operating system up to the latest update and required update level consistent with your organization’s standards.</span></span> <span data-ttu-id="48820-120">有关操作要求的更多详细信息, 请参阅支持文档中的[Lync server 2013 中的 "服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)"。</span><span class="sxs-lookup"><span data-stu-id="48820-120">For more details about the operating requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="48820-121">要使 Lync Server 2013 在 Windows Server 2012 R2 上工作, 你可能需要在 Windows Server 中更改注册表项的值。</span><span class="sxs-lookup"><span data-stu-id="48820-121">For Lync Server 2013 to work on Windows Server 2012 R2, you may need to change the value of a registry key in Windows Server.</span></span> <span data-ttu-id="48820-122">若要使证书正常工作, 并且客户端向 Survivable 分支机构注册, 则可能需要此更改。</span><span class="sxs-lookup"><span data-stu-id="48820-122">This change may be necessary for certificates to work correctly, and for clients to register with Survivable Branch Appliances.</span></span> <span data-ttu-id="48820-123">有关详细信息, 请<A class=uri href="http://support.microsoft.com/kb/2901554">http://support.microsoft.com/kb/2901554</A>参阅。</span><span class="sxs-lookup"><span data-stu-id="48820-123">For more information, see <A class=uri href="http://support.microsoft.com/kb/2901554">http://support.microsoft.com/kb/2901554</A>.</span></span>



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a><span data-ttu-id="48820-124">Lync Server 2013 的其他软件</span><span class="sxs-lookup"><span data-stu-id="48820-124">Additional Software for Lync Server 2013</span></span>

<span data-ttu-id="48820-125">除了操作系统需要的更新外, Lync Server 2013 还需要操作系统角色、功能和软件才能运行。</span><span class="sxs-lookup"><span data-stu-id="48820-125">In addition to the updates required for the operating system, Lync Server 2013 requires operating system roles, features, and software to operate.</span></span> <span data-ttu-id="48820-126">有关在发布拓扑和安装 Lync Server 2013 之前必须安装的其他软件的详细信息, 请参阅规划文档中[Lync Server 2013 的其他软件要求](lync-server-2013-additional-software-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="48820-126">For details about the additional software that must be installed prior to publishing your topology and installing Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a><span data-ttu-id="48820-127">所有服务器角色所需的其他软件</span><span class="sxs-lookup"><span data-stu-id="48820-127">Additional Software Necessary for All Server Roles</span></span>

<span data-ttu-id="48820-128">在所有服务器角色上, 还必须确保安装了 Windows PowerShell 命令行界面3.0 和 Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="48820-128">On all server roles, you must also make sure that Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are installed.</span></span>

<span data-ttu-id="48820-129">此外, 在运行 Lync Server 管理工具的任何计算机上都需要 Windows PowerShell 命令行界面3.0 和 Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="48820-129">Additionally, Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are required on any computer where you will run the Lync Server administrative tools.</span></span>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="48820-130">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="48820-130">Windows PowerShell 3.0</span></span>

<span data-ttu-id="48820-131">Lync Server 2013 要求你在将参与 Lync Server 拓扑的每台计算机上安装 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="48820-131">Lync Server 2013 requires you to install Windows PowerShell 3.0 on each computer that will take part in your Lync Server topology.</span></span> <span data-ttu-id="48820-132">有关安装 Windows PowerShell 3.0 的详细信息, 请参阅[安装 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。</span><span class="sxs-lookup"><span data-stu-id="48820-132">For details about installing Windows PowerShell 3.0, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="48820-133">在 Windows Server&nbsp;2008&nbsp;R2 SP1 上安装 Microsoft .net Framework 4.5 之前, 无法安装 windows PowerShell 命令行界面3.0。</span><span class="sxs-lookup"><span data-stu-id="48820-133">On Windows Server&nbsp;2008&nbsp;R2 with SP1, Windows PowerShell command-line interface 3.0 cannot be installed before installing Microsoft .NET Framework 4.5.</span></span>



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="48820-134">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="48820-134">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="48820-135">在将在 Windows Server 2012 或 Windows Server 2012 R2 上运行 Lync Server 2013 的服务器上安装 Microsoft .NET Framework 4.5 时, 必须执行一个附加步骤。</span><span class="sxs-lookup"><span data-stu-id="48820-135">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 on Windows Server 2012 or Windows Server 2012 R2, you must perform one additional step.</span></span> <span data-ttu-id="48820-136">安装 .NET Framework 4.5 后, 请使用服务器管理器安装 HTTP 激活。</span><span class="sxs-lookup"><span data-stu-id="48820-136">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="48820-137">**在 Windows Server 2012 或 Windows Server 2012 R2 上安装 .NET 4.5 HTTP 激活**</span><span class="sxs-lookup"><span data-stu-id="48820-137">**To Install .NET 4.5 HTTP Activation on Windows Server 2012 or Windows Server 2012 R2**</span></span>

1.  <span data-ttu-id="48820-138">从 "**开始**" 菜单中, 单击 "**程序**", 然后单击 "**管理工具**", 然后单击 "**服务器管理器**"。</span><span class="sxs-lookup"><span data-stu-id="48820-138">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="48820-139">在服务器管理器中的 "**功能摘要**" 下, 选择 "**添加功能**"。</span><span class="sxs-lookup"><span data-stu-id="48820-139">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="48820-140">展开 **.Net Framework 4.5**。</span><span class="sxs-lookup"><span data-stu-id="48820-140">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="48820-141">选择 " **WCF 激活**" (如果尚未选中)。</span><span class="sxs-lookup"><span data-stu-id="48820-141">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="48820-142">然后选择 " **HTTP 激活**"。</span><span class="sxs-lookup"><span data-stu-id="48820-142">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="48820-143">单击 "**下一步**" 并按照提示完成安装。</span><span class="sxs-lookup"><span data-stu-id="48820-143">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

