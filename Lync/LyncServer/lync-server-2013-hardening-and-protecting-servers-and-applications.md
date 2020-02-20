---
title: Lync Server 2013：强化和保护服务器和应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50bd8d3fb538a7450d2129691ec523dbcb6dd208
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a><span data-ttu-id="f938a-102">强化和保护 Lync Server 2013 的服务器和应用程序</span><span class="sxs-lookup"><span data-stu-id="f938a-102">Hardening and protecting servers and applications for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f938a-103">_**上次修改的主题：** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="f938a-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="f938a-104">您应根据特定组件的最佳做法强化和保护操作系统及应用程序。</span><span class="sxs-lookup"><span data-stu-id="f938a-104">You should harden and protect your operating system and applications according to best practices for that specific component.</span></span> <span data-ttu-id="f938a-105">本节介绍如何强化应用程序服务器和使用组策略来实现安全锁定。</span><span class="sxs-lookup"><span data-stu-id="f938a-105">This section describes how to harden application servers and use Group Policy to implement security lockdowns.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f938a-106">您还可以加强和保护用于 Microsoft Lync Server 2013 部署的数据库。</span><span class="sxs-lookup"><span data-stu-id="f938a-106">You can also harden and protect the databases used for you Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="f938a-107">有关详细信息，请参阅<A href="lync-server-2013-hardening-and-protecting-databases.md">强化和保护 Lync Server 2013 的数据库</A>。</span><span class="sxs-lookup"><span data-stu-id="f938a-107">For details, see <A href="lync-server-2013-hardening-and-protecting-databases.md">Hardening and protecting the databases of Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="securing-application-servers"></a><span data-ttu-id="f938a-108">保护应用程序服务器</span><span class="sxs-lookup"><span data-stu-id="f938a-108">Securing Application Servers</span></span>

<span data-ttu-id="f938a-p103">对于应用程序服务器，应强化操作系统和应用程序。例如，对于专门用来运行 Microsoft Internet Security and Acceleration (ISA) Server 2006 的 Windows Server 2008 计算机，应从操作系统和应用程序方面进行强化。应将尽量减少服务器提供的正在运行的服务数作为主要目标。</span><span class="sxs-lookup"><span data-stu-id="f938a-p103">For applications servers, the operating system and the application should be hardened. For example, a Windows Server 2008 computer dedicated to running Microsoft Internet Security and Acceleration (ISA) Server 2006 should be hardened from the operating system and from the application perspective. Minimizing the number of services running and provided by the server should be a primary goal.</span></span>

</div>

<div>

## <a name="securing-virtual-servers"></a><span data-ttu-id="f938a-112">保护虚拟服务器</span><span class="sxs-lookup"><span data-stu-id="f938a-112">Securing Virtual Servers</span></span>

<span data-ttu-id="f938a-113">虚拟服务器快照包含服务器的数据磁盘的副本，还包含内存中的数据的转储，这两种都可能包含可能导致攻击的敏感加密数据。</span><span class="sxs-lookup"><span data-stu-id="f938a-113">Virtual server snapshots contain copies of the server’s data disks and also contain dumps of in-memory data, both of which can contain sensitive cryptographic data that might lead to attacks.</span></span> <span data-ttu-id="f938a-114">对于使用虚拟化实现的生产服务器，应禁用所有服务器快照或以受严格控制的方式管理它们。</span><span class="sxs-lookup"><span data-stu-id="f938a-114">For production servers implemented using virtualization, you should disable all server snapshots or manage them in a very controlled manner.</span></span> <span data-ttu-id="f938a-115">有关保护 Hyper-v 虚拟服务器的详细信息，请参阅以下位置的 Hyper-v 安全指南： [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176)。</span><span class="sxs-lookup"><span data-stu-id="f938a-115">For details about securing Hyper-V virtual servers, see the Hyper-V Security Guide at: [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176).</span></span>

</div>

<div>

## <a name="group-policy"></a><span data-ttu-id="f938a-116">组策略</span><span class="sxs-lookup"><span data-stu-id="f938a-116">Group Policy</span></span>

<span data-ttu-id="f938a-p105">在 Windows Server 2008 和 Windows Server 2008 R2 中，组策略提供基于目录的桌面配置管理。通过在组策略对象 (GPO) 中定义以下各项的“计算机和用户”设置，可以使用组策略来实现安全锁定：</span><span class="sxs-lookup"><span data-stu-id="f938a-p105">In Windows Server 2008 and Windows Server 2008 R2, Group Policy provides directory-based desktop configuration management. You can use Group Policy to implement security lockdowns by defining Computer and User settings within a Group Policy object (GPO) for the following:</span></span>

  - <span data-ttu-id="f938a-119">基于注册表的策略</span><span class="sxs-lookup"><span data-stu-id="f938a-119">Registry-based policies</span></span>

  - <span data-ttu-id="f938a-120">安全性</span><span class="sxs-lookup"><span data-stu-id="f938a-120">Security</span></span>

  - <span data-ttu-id="f938a-121">软件安装</span><span class="sxs-lookup"><span data-stu-id="f938a-121">Software installation</span></span>

  - <span data-ttu-id="f938a-122">脚本</span><span class="sxs-lookup"><span data-stu-id="f938a-122">Scripts</span></span>

  - <span data-ttu-id="f938a-123">文件夹重定向</span><span class="sxs-lookup"><span data-stu-id="f938a-123">Folder redirection</span></span>

  - <span data-ttu-id="f938a-124">远程安装服务</span><span class="sxs-lookup"><span data-stu-id="f938a-124">Remote installation services</span></span>

<span data-ttu-id="f938a-125">为了向管理员提供用于配置这些设置的用户界面，管理模板随操作系统版本、service pack 版本和一些应用程序（包括 Lync Server 2013）一起提供。</span><span class="sxs-lookup"><span data-stu-id="f938a-125">To provide a user interface for the administrator to configure these settings, administrative templates are shipped with operating system releases, service pack releases, and some applications, including Lync Server 2013.</span></span>

<span data-ttu-id="f938a-126">Communicator .adm 文件是一个随 Lync Server 2013 提供的管理模板，安装在% windir%\\inf\\目录中，并提供组策略设置的接口。</span><span class="sxs-lookup"><span data-stu-id="f938a-126">The Communicator.adm file is an administrative template that ships with Lync Server 2013, is installed to the %windir%\\inf\\ directory, and provides an interface to the Group Policy settings.</span></span> <span data-ttu-id="f938a-127">Communicator.adm 中的每项设置均与注册表中影响应用程序行为的设置对应。</span><span class="sxs-lookup"><span data-stu-id="f938a-127">Each setting in Communicator.adm corresponds to a setting in the registry that affects application behavior.</span></span>

<span data-ttu-id="f938a-128">利用 Active Directory 用户和计算机控制台以及组策略管理控制台 (GPMC) 中提供的 GPedit.dll，可以访问这些设置。</span><span class="sxs-lookup"><span data-stu-id="f938a-128">The settings can be accessed from GPedit.dll, which is available from the Active Directory Users and Computers console and the Group Policy Management Console (GPMC).</span></span>

</div>

<div>

## <a name="group-policy-security-settings"></a><span data-ttu-id="f938a-129">组策略安全设置</span><span class="sxs-lookup"><span data-stu-id="f938a-129">Group Policy Security Settings</span></span>

<span data-ttu-id="f938a-130">组策略包含 GPO 的安全设置，当通过 GPedit.dll 访问这些安全设置时，它们位于“计算机配置”/“Windows 设置”/“安全设置”下。</span><span class="sxs-lookup"><span data-stu-id="f938a-130">Group Policy contains security settings for a GPO under Computer Configuration/Windows Settings/Security Settings when accessed from GPedit.dll.</span></span> <span data-ttu-id="f938a-131">可以导入安全模板以配置 GPO 的安全设置。</span><span class="sxs-lookup"><span data-stu-id="f938a-131">You can import security templates to configure security settings for the GPO.</span></span> <span data-ttu-id="f938a-132">Windows Server 2008 安全指南（网址[https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186)为）和 windows Server 2008 R2 安全合规性管理[https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882)工具包包含多个示例模板，可以对它们进行修改以满足您的需求。</span><span class="sxs-lookup"><span data-stu-id="f938a-132">The Windows Server 2008 Security Guide at [https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186) and the Windows Server 2008 R2 Security Compliance Management Toolkit at [https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882) contain a number of sample templates that you can modify to meet your needs.</span></span>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="f938a-133">最佳做法</span><span class="sxs-lookup"><span data-stu-id="f938a-133">Best Practices</span></span>

  - <span data-ttu-id="f938a-134">强化所有服务器操作系统和应用程序。</span><span class="sxs-lookup"><span data-stu-id="f938a-134">Harden all server operating systems and applications.</span></span>

  - <span data-ttu-id="f938a-135">保护服务器快照和增强所有虚拟服务器的安全性。</span><span class="sxs-lookup"><span data-stu-id="f938a-135">Protect server snapshots and enhance the security of all virtual servers.</span></span>

  - <span data-ttu-id="f938a-136">使用组策略实现安全锁定。</span><span class="sxs-lookup"><span data-stu-id="f938a-136">Use Group Policy to implement security lockdowns.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

