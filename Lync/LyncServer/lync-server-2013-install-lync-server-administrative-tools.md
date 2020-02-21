---
title: Lync Server 2013：安装 Lync Server 管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server administrative tools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48184695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8805c82c26eb97da8537b33cda8346f5942de1c2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204248"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-lync-server-2013-administrative-tools"></a><span data-ttu-id="a9195-102">安装 Lync Server 2013 管理工具</span><span class="sxs-lookup"><span data-stu-id="a9195-102">Install Lync Server 2013 administrative tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9195-103">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="a9195-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="a9195-104">本主题介绍如何安装您需要用于部署和管理 Lync Server 2013 的管理工具。</span><span class="sxs-lookup"><span data-stu-id="a9195-104">This topic describes how to install the administrative tools you need to use to deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="a9195-105">默认情况下，在运行 Lync Server 2013 的每台服务器上安装管理工具。</span><span class="sxs-lookup"><span data-stu-id="a9195-105">The administrative tools are installed by default on each server running Lync Server 2013.</span></span> <span data-ttu-id="a9195-106">此外，您可在其他计算机（如专用管理控制台）上安装这些管理工具。</span><span class="sxs-lookup"><span data-stu-id="a9195-106">Additionally, you can install the administrative tools on other computers, such as dedicated administrative consoles.</span></span> <span data-ttu-id="a9195-107">强烈建议您在要创建的 Lync Server 2013 部署所在的同一域或林中的计算机上安装管理工具，因为这样做可以确保已将 Active Directory 域服务准备步骤完成，这使您可以在以后使用该计算机上的管理工具发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="a9195-107">We strongly recommend that you install the administrative tools on a computer that is in the same domain or forest as the Lync Server 2013 deployment you are creating because by doing so you make sure that Active Directory Domain Services preparation steps are already complete, which enables you to use the administrative tools on that computer later to publish your topology.</span></span>

<span data-ttu-id="a9195-108">在安装或使用 Lync Server 2013 管理工具之前，请务必先查看基础结构、操作系统、软件和管理员权限要求。</span><span class="sxs-lookup"><span data-stu-id="a9195-108">Make sure that you review infrastructure, operating system, software, and administrator rights requirements before you install or use the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="a9195-109">有关基础结构要求的详细信息，请参阅[Lync Server 2013 中的管理工具基础结构要求](lync-server-2013-administrative-tools-infrastructure-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a9195-109">For details about infrastructure requirements, see [Administrative tools infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span></span> <span data-ttu-id="a9195-110">有关操作系统和软件要求的详细信息，以安装 Lync Server 2013 管理工具，请参阅 lync server [2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)、 [lync server 2013 的其他软件要求](lync-server-2013-additional-software-requirements.md)以及[Lync server 2013 中的其他服务器支持和要求](lync-server-2013-additional-server-support-and-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a9195-110">For details about operating system and software requirements to install the Lync Server 2013 administrative tools, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span> <span data-ttu-id="a9195-111">有关安装和使用这些工具所需的用户权利和权限的详细信息，请参阅[安装和管理 Lync Server 2013 所需的管理员权限和权限](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)。</span><span class="sxs-lookup"><span data-stu-id="a9195-111">For details about the user rights and permissions required to install and use the tools, see [Administrator rights and permissions required for setup and administration of Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a9195-112">如果组织要求您在系统驱动器之外的某个驱动器上定位 Internet Information Services (IIS) 和所有 Web Services，您可以在“安装”对话框中更改 Lync Server 文件的安装位置路径。</span><span class="sxs-lookup"><span data-stu-id="a9195-112">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="a9195-113">如果将安装文件安装到此路径（包括 OCSCore），则其余的 Lync Server 2013 文件也将部署到此驱动器。</span><span class="sxs-lookup"><span data-stu-id="a9195-113">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span>



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a><span data-ttu-id="a9195-114">安装 Lync Server 2013 管理工具</span><span class="sxs-lookup"><span data-stu-id="a9195-114">To install the Lync Server 2013 administrative tools</span></span>

1.  <span data-ttu-id="a9195-p104">以本地管理员身份登录（最低要求）要安装管理工具的计算机。如果您以标准用户身份登录 Windows Vista 或 Windows 7 操作系统，并且启用了用户帐户控制 (UAC)，则系统将提示您输入本地管理员或域等效用户的名称和密码。</span><span class="sxs-lookup"><span data-stu-id="a9195-p104">Log on as a local administrator (minimum requirement) to the computer where you want to install the administrative tools. If you are logged on as an a standard user on the Windows Vista or Windows 7 operating systems, and User Account Control (UAC) is enabled, you will be prompted for the local administrator or a domain equivalent user name and password.</span></span>

2.  <span data-ttu-id="a9195-117">在您的计算机上找到安装媒体，然后双击 " \\设置\\amd64\\setup.exe"。</span><span class="sxs-lookup"><span data-stu-id="a9195-117">Locate the installation media on your computer, and then double-click \\Setup\\amd64\\Setup.exe.</span></span>

3.  <span data-ttu-id="a9195-118">如果提示您安装 Microsoft Visual C++ 2008 可发行软件包，请单击 **“是”**。</span><span class="sxs-lookup"><span data-stu-id="a9195-118">If you are prompted to install the Microsoft Visual C++ 2008 distributable, click **Yes**.</span></span>

4.  <span data-ttu-id="a9195-119">在 " **Microsoft Lync Server 2013 安装位置**" 页上，单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="a9195-119">On the **Microsoft Lync Server 2013 Installation Location** page, click **OK**.</span></span> <span data-ttu-id="a9195-120">如果要将文件安装至其他位置，请将此路径更改为相应的位置或驱动器。</span><span class="sxs-lookup"><span data-stu-id="a9195-120">Change this path to another location or drive if you need to have the files installed to another location.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a9195-121">如果您的组织要求您在除系统驱动器之外的驱动器上查找 Internet 信息服务（IIS）和所有 Web 服务，则可以在 "安装程序" 对话框中更改 Lync Server 2013 文件的安装位置路径。</span><span class="sxs-lookup"><span data-stu-id="a9195-121">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box.</span></span> <span data-ttu-id="a9195-122">如果将安装文件安装到此路径（包括 OCSCore），则其余的 Lync Server 2013 文件也将部署到此驱动器。</span><span class="sxs-lookup"><span data-stu-id="a9195-122">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive too.</span></span>

    
    </div>

5.  <span data-ttu-id="a9195-p107">在 **“最终用户许可协议”** 页上，查看许可条款，单击 **“我接受”**，然后单击 **“确定”**。必须完成此步骤，才能继续安装。</span><span class="sxs-lookup"><span data-stu-id="a9195-p107">On the **End User License Agreement** page, review the license terms, click **I accept**, and then click **OK**. This step is required before you can continue.</span></span>

6.  <span data-ttu-id="a9195-125">在 " **Microsoft Lync Server 2013 –部署向导**" 页上，单击 "**安装管理员工具**"。</span><span class="sxs-lookup"><span data-stu-id="a9195-125">On the **Microsoft Lync Server 2013 – Deployment Wizard** page, click **Install Administrator Tools**.</span></span>

7.  <span data-ttu-id="a9195-126">安装成功完成后，单击 **“退出”**。</span><span class="sxs-lookup"><span data-stu-id="a9195-126">When the installation successfully completes, click **Exit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a9195-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9195-127">See Also</span></span>


[<span data-ttu-id="a9195-128">打开 Lync Server 2013 管理工具</span><span class="sxs-lookup"><span data-stu-id="a9195-128">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)  


[<span data-ttu-id="a9195-129">Lync Server 2013 管理工具</span><span class="sxs-lookup"><span data-stu-id="a9195-129">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

