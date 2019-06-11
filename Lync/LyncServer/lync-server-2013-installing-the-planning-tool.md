---
title: Lync Server 2013：安装规划工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing the Planning Tool
ms:assetid: ebdc9e26-4b22-4b02-85b9-7462bcfe7c93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615046(v=OCS.15)
ms:contentKeyID: 51541525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e528062d5fd04e1a11df934cbc01b2dc8c92aa4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-planning-tool-in-lync-server-2013"></a><span data-ttu-id="8c207-102">在 Lync Server 2013 中安装规划工具</span><span class="sxs-lookup"><span data-stu-id="8c207-102">Installing the Planning Tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c207-103">_**主题上次修改时间:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="8c207-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="8c207-104">在使用 Microsoft Lync Server 2013 (计划工具) 开始设计和规划 Lync Server 2013 基础结构之前, 必须首先安装规划工具。</span><span class="sxs-lookup"><span data-stu-id="8c207-104">Before you begin designing and planning your Lync Server 2013 infrastructure by using the Microsoft Lync Server 2013, Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="8c207-105">规划工具不需要部署到属于你计划安装 Lync Server 2013 的域或基础结构的一部分的工作站或服务器。</span><span class="sxs-lookup"><span data-stu-id="8c207-105">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Lync Server 2013.</span></span> <span data-ttu-id="8c207-106">规划工具附带的自述文件详细介绍了有关安装和使用该工具的重要信息。</span><span class="sxs-lookup"><span data-stu-id="8c207-106">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="8c207-107">Some of the information in the Readme file is duplicated here for clarity.</span><span class="sxs-lookup"><span data-stu-id="8c207-107">Some of the information in the Readme file is duplicated here for clarity.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8c207-108">规划工具要求在安装该工具的计算机上具有管理员权限和权限的用户进行安装。</span><span class="sxs-lookup"><span data-stu-id="8c207-108">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>



</div>

<span data-ttu-id="8c207-109">规划工具的安装和操作支持的操作系统包括:</span><span class="sxs-lookup"><span data-stu-id="8c207-109">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

  - <span data-ttu-id="8c207-110">Windows 8</span><span class="sxs-lookup"><span data-stu-id="8c207-110">Windows 8</span></span>

  - <span data-ttu-id="8c207-111">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="8c207-111">Windows 8.1</span></span>

  - <span data-ttu-id="8c207-112">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="8c207-112">Windows Server 2012</span></span>

  - <span data-ttu-id="8c207-113">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="8c207-113">Windows Server 2012 R2</span></span>

  - <span data-ttu-id="8c207-114">Windows 7 32 位版本</span><span class="sxs-lookup"><span data-stu-id="8c207-114">Windows 7, 32-bit edition</span></span>

  - <span data-ttu-id="8c207-115">Windows 7，使用 Windows on Win32 (WOW) 的 64 位版本</span><span class="sxs-lookup"><span data-stu-id="8c207-115">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

  - <span data-ttu-id="8c207-116">Windows Server 2008 R2，使用 WOW</span><span class="sxs-lookup"><span data-stu-id="8c207-116">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="8c207-117">此外, 规划工具需要 Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="8c207-117">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="8c207-118">满足预安装要求后, 即可安装规划工具。</span><span class="sxs-lookup"><span data-stu-id="8c207-118">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>

<div>

## <a name="to-install-the-planning-tool"></a><span data-ttu-id="8c207-119">安装规划工具</span><span class="sxs-lookup"><span data-stu-id="8c207-119">To install the Planning Tool</span></span>

1.  <span data-ttu-id="8c207-120">以 Administrators 组成员的身份登录本地计算机。</span><span class="sxs-lookup"><span data-stu-id="8c207-120">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="8c207-121">使用 Windows 资源管理器或命令窗口, 找到您下载规划工具安装文件的目录。</span><span class="sxs-lookup"><span data-stu-id="8c207-121">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3.  <span data-ttu-id="8c207-122">找到 LyncPlanningTool。</span><span class="sxs-lookup"><span data-stu-id="8c207-122">Locate the LyncPlanningTool.msi.</span></span> <span data-ttu-id="8c207-123">在 Windows 资源管理器中双击该文件。</span><span class="sxs-lookup"><span data-stu-id="8c207-123">In Windows Explorer, double-click the file.</span></span> <span data-ttu-id="8c207-124">在命令窗口中，键入文件的名称，然后按 **Enter** 运行该文件。</span><span class="sxs-lookup"><span data-stu-id="8c207-124">In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4.  <span data-ttu-id="8c207-125">在**Microsoft Lync Server 2013**的 "欢迎" 页面上, 选择 "规划工具设置向导", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="8c207-125">On the Welcome page of the **Microsoft Lync Server 2013, Planning Tool Setup Wizard**, click **Next**.</span></span>

5.  <span data-ttu-id="8c207-126">查看“**最终用户许可协议**”，如果选择接受许可协议中的使用条款，则选择“**我接受许可协议中的条款**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="8c207-126">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6.  <span data-ttu-id="8c207-127">选择安装规划工具文件的位置。</span><span class="sxs-lookup"><span data-stu-id="8c207-127">Choose where to install the Planning Tool files.</span></span> <span data-ttu-id="8c207-128">默认位置是 C:\\Program Files (x86)\\Microsoft Lync Server 2013\\计划工具。</span><span class="sxs-lookup"><span data-stu-id="8c207-128">The default location is C:\\Program Files (x86)\\Microsoft Lync Server 2013\\Planning Tool.</span></span> <span data-ttu-id="8c207-129">如果要更改安装位置，请单击“**更改**”。</span><span class="sxs-lookup"><span data-stu-id="8c207-129">If you want to change the installation location, click **Change**.</span></span> <span data-ttu-id="8c207-130">在“**更改目标文件夹**”上，浏览或键入要安装这些文件的位置，单击“**确定**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="8c207-130">On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="8c207-131">安装程序现在已准备好安装规划工具。</span><span class="sxs-lookup"><span data-stu-id="8c207-131">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="8c207-132">单击“安装”\*\*\*\* 开始安装过程。</span><span class="sxs-lookup"><span data-stu-id="8c207-132">Click **Install** to begin the installation process.</span></span>

8.  <span data-ttu-id="8c207-133">将开始安装，并将显示进度。</span><span class="sxs-lookup"><span data-stu-id="8c207-133">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="8c207-134">成功完成安装后，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="8c207-134">After the installation is successfully completed, click **Finish**.</span></span>

9.  <span data-ttu-id="8c207-135">规划工具可供使用。</span><span class="sxs-lookup"><span data-stu-id="8c207-135">The Planning Tool is ready for use.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8c207-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c207-136">See Also</span></span>


[<span data-ttu-id="8c207-137">在 Lync Server 2013 中安装可选软件</span><span class="sxs-lookup"><span data-stu-id="8c207-137">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

