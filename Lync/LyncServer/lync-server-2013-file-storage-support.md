---
title: Lync Server 2013 文件存储支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: File storage support
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48185743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3025534aecb45f230e986016e839af07fe1406cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a><span data-ttu-id="af7c9-102">Lync Server 2013 中的文件存储支持</span><span class="sxs-lookup"><span data-stu-id="af7c9-102">File storage support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af7c9-103">_**主题上次修改时间:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="af7c9-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="af7c9-104">Lync Server 2013 对所有文件存储使用相同的文件存储。</span><span class="sxs-lookup"><span data-stu-id="af7c9-104">Lync Server 2013 uses the same file store for all file storage.</span></span> <span data-ttu-id="af7c9-105">文件存储支持包括以下内容:</span><span class="sxs-lookup"><span data-stu-id="af7c9-105">File storage support includes the following:</span></span>

  - <span data-ttu-id="af7c9-106">直接连接存储 (DAS) 或存储区域网络 (SAN) 上的文件共享, 包括分布式文件系统 (DFS) 和文件存储的独立磁盘冗余阵列 (RAID)。</span><span class="sxs-lookup"><span data-stu-id="af7c9-106">A file share on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS), and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="af7c9-107">有关存储要求的详细信息, 请参阅[Lync server 2013 中的技术要求、即时消息和状态显示在 lync server 的技术要求](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md)和计划中的[lync server 2013 中的控制器的硬件和软件要求](lync-server-2013-hardware-and-software-requirements-for-the-director.md)文档.</span><span class="sxs-lookup"><span data-stu-id="af7c9-107">For details about storage requirements, see [Technical requirements for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) and [Hardware and software requirements for the Director in Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) in the Planning documentation.</span></span> <span data-ttu-id="af7c9-108">有关 DFS for Windows Server 2008 操作系统的详细信息, 请参阅 Windows Server 2008 的 DFS 分步指南[http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)。</span><span class="sxs-lookup"><span data-stu-id="af7c9-108">For details about DFS for Windows Server 2008 operating system, see the DFS Step-by-Step Guide for Windows Server 2008 at [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835).</span></span>

  - <span data-ttu-id="af7c9-109">文件共享的共享群集。</span><span class="sxs-lookup"><span data-stu-id="af7c9-109">A shared cluster for the file share.</span></span> <span data-ttu-id="af7c9-110">如果使用共享群集, 则应使用运行 Windows Server 2008 或 Windows Server 2008 R2 的群集服务器。</span><span class="sxs-lookup"><span data-stu-id="af7c9-110">If you use a shared cluster, you should use cluster servers running Windows Server 2008 or Windows Server 2008 R2.</span></span> <span data-ttu-id="af7c9-111">使用运行旧版本 Windows 的群集服务器可能会导致权限问题, 防止某些功能可用。</span><span class="sxs-lookup"><span data-stu-id="af7c9-111">Using cluster servers running an older version of Windows may result in permission issues that prevent some features from being available.</span></span> <span data-ttu-id="af7c9-112">使用群集管理器创建文件共享。</span><span class="sxs-lookup"><span data-stu-id="af7c9-112">Use the Cluster Administrator to create the file shares.</span></span> <span data-ttu-id="af7c9-113">有关使用群集管理器的详细信息, 请参阅 Microsoft 知识库文章 284838, "如何在上[http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899)创建服务器群集文件共享"。</span><span class="sxs-lookup"><span data-stu-id="af7c9-113">For details about using the Cluster Administrator, see Microsoft Knowledge Base article 284838, "How to Create a Server Cluster File Share with Cluster.exe" at [http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

