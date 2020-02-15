---
title: Lync Server 2013： Lync VDI 插件先决条件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync VDI plug-in prerequisites
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205304(v=OCS.15)
ms:contentKeyID: 48185552
ms.date: 03/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1e5434ed445bf19d2aaeea146ba0edb7dcac04c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a><span data-ttu-id="0bf9e-102">Lync Server 2013 中的 lync VDI 插件先决条件</span><span class="sxs-lookup"><span data-stu-id="0bf9e-102">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0bf9e-103">_**上次修改的主题：** 2017-03-07_</span><span class="sxs-lookup"><span data-stu-id="0bf9e-103">_**Topic Last Modified:** 2017-03-07_</span></span>

<span data-ttu-id="0bf9e-104">在虚拟桌面基础结构（VDI）环境中，虚拟机和用户的本地计算机必须满足本节中概述的要求。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-104">In a virtual desktop infrastructure (VDI) environment, the virtual machines and the user’s local computer must meet the requirements outlined in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0bf9e-105">有关如何安装和部署虚拟化环境的详细信息，请参阅您的虚拟化解决方案提供商。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-105">Refer to your virtualization solution provider for details about how to install and deploy the virtualized environment.</span></span> <span data-ttu-id="0bf9e-106">有关基于 Hyper-v 和远程桌面服务部署虚拟化环境的信息，请参阅 Microsoft TechNet 库中的以下文章：</span><span class="sxs-lookup"><span data-stu-id="0bf9e-106">For information about deploying a virtualized environment based on Hyper-V and Remote Desktop Services, see the following articles in the Microsoft TechNet Library:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="0bf9e-107">Hyper-v 位置<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span><span class="sxs-lookup"><span data-stu-id="0bf9e-107">Hyper-V at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span></span></P>
> <LI>
> <P><span data-ttu-id="0bf9e-108">Windows Server&nbsp;2008&nbsp;R2 中的远程桌面服务<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span><span class="sxs-lookup"><span data-stu-id="0bf9e-108">Remote Desktop Services in Windows Server&nbsp;2008&nbsp;R2 at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="0bf9e-109">以下是在数据中心计算机上运行的虚拟机的要求：</span><span class="sxs-lookup"><span data-stu-id="0bf9e-109">The following are requirements for the virtual machines running on the data center computer:</span></span>

  - <span data-ttu-id="0bf9e-110">虚拟机必须使用 Windows 10、windows 8.1、windows 8、Windows 7 或 Windows Server 2008 R2 以及最新的 service pack 进行配置。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-110">Virtual machines must be configured with Windows 10, Windows 8.1, Windows 8, Windows 7, or Windows Server 2008 R2 with the latest service packs.</span></span>

<span data-ttu-id="0bf9e-111">以下是用户和用户的本地计算机的要求：</span><span class="sxs-lookup"><span data-stu-id="0bf9e-111">The following are requirements for the user and the user’s local computer:</span></span>

  - <span data-ttu-id="0bf9e-112">用户必须驻留在 Lync Server 2013 上。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-112">The user must be homed on Lync Server 2013.</span></span>

  - <span data-ttu-id="0bf9e-113">本地计算机必须运行 Windows Embedded Standard 7 with SP1、Windows 7 SP1、windows 8、Windows 8.1 Embedded 或 Windows 8.1 （未嵌入）。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-113">The local computer must be running Windows Embedded Standard 7 with SP1, Windows 7 with SP1, Windows 8, Windows 8.1 Embedded, or Windows 8.1 (not embedded).</span></span>

  - <span data-ttu-id="0bf9e-114">如果使用远程桌面服务，则 Lync VDI 插件位数（即应用程序是否为32位或64位）必须与本地计算机的操作系统位数匹配。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-114">If you are using Remote Desktop Services, the Lync VDI plug-in bitness (that is, whether the application is 32-bit or 64-bit) must match the local computer’s operating system bitness.</span></span> <span data-ttu-id="0bf9e-115">本地计算机上的操作系统和虚拟机上的操作系统的位数不需要匹配。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-115">The bitness of the operating system on the local computer and the operating system on the virtual machine do not need to match.</span></span> <span data-ttu-id="0bf9e-116">如果使用的是其他虚拟化解决方案或平台，请参阅虚拟化解决方案提供商关于位数要求的指南。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-116">If you are using another virtualization solution or platform, refer to guidance from your virtualization solution provider about bitness requirements.</span></span>

  - <span data-ttu-id="0bf9e-117">本地计算机必须运行最新版本的远程桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-117">The local computer must be running the latest version of the remote desktop client.</span></span> <span data-ttu-id="0bf9e-118">从虚拟化解决方案提供商处安装来自 Microsoft 或最新远程桌面客户端软件的远程桌面服务客户端的最新更新。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-118">Install the latest updates of Remote Desktop Services client from Microsoft or the latest remote desktop client software from your virtualization solution provider.</span></span> <span data-ttu-id="0bf9e-119">有关最新的远程桌面服务更新， [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)请参阅。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-119">For the latest Remote Desktop Services updates, see [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

  - <span data-ttu-id="0bf9e-120">在本地计算机上，必须配置远程桌面客户端设置，以便在本地计算机上播放音频，并禁用远程录制。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-120">On the local computer, the remote desktop client settings must be configured so that audio plays on the local computer and remote recording is disabled.</span></span> <span data-ttu-id="0bf9e-121">若要在 Windows 中为远程桌面连接配置这些设置，请参阅下一节 "配置远程桌面连接设置"。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-121">To configure these settings for Remote Desktop Connection in Windows, see the next section, "To configure Remote Desktop Connection settings."</span></span>

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a><span data-ttu-id="0bf9e-122">配置远程桌面连接设置</span><span class="sxs-lookup"><span data-stu-id="0bf9e-122">To configure Remote Desktop Connection settings</span></span>

<span data-ttu-id="0bf9e-123">若要为 Lync VDI 插件准备 Windows 中的远程桌面连接，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-123">To prepare Remote Desktop Connection in Windows for the Lync VDI plug-in, follow these steps.</span></span>

1.  <span data-ttu-id="0bf9e-124">如果本地计算机运行的是 Windows 8，请跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-124">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="0bf9e-125">如果本地计算机运行的是 Windows 7 SP1，请安装最新的 Windows 8 版本的远程桌面服务客户端，网址[https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)为。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-125">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the Remote Desktop Services client, available at [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

2.  <span data-ttu-id="0bf9e-126">通过单击 "**开始**"，然后单击 "**远程桌面连接**" 来启动远程桌面服务客户端。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-126">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>

3.  <span data-ttu-id="0bf9e-127">单击 **"选项"**。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-127">Click **Options**.</span></span>

4.  <span data-ttu-id="0bf9e-128">单击 "**本地资源**" 选项卡。在 "**远程音频**" 下，单击 "**设置**"，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0bf9e-128">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
      - <span data-ttu-id="0bf9e-129">在 "**远程音频播放**" 下，选择 "**在此计算机上播放**"。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-129">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
      - <span data-ttu-id="0bf9e-130">在 "**远程音频录制**" 下，选择 "**不录制**"。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-130">Under **Remote audio recording**, select **Do not record**.</span></span>
    
      - <span data-ttu-id="0bf9e-131">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-131">Click **OK**.</span></span>

5.  <span data-ttu-id="0bf9e-132">单击 "**体验**" 选项卡。在 "**性能**" 下，清除 "**永久位图缓存**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-132">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>

6.  <span data-ttu-id="0bf9e-133">单击 "**常规**" 选项卡。在 "**计算机**" 中，键入虚拟机的名称，然后单击 "**连接**"。</span><span class="sxs-lookup"><span data-stu-id="0bf9e-133">Click the **General** tab. In **Computer**, type the name of the virtual machine, and then click **Connect**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

