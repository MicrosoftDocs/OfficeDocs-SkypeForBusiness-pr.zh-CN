---
title: Lync Server 2013 文件存储支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File storage support
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48185743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c424693b71f516b1fcb27523fbcb27b3a514176
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507275"
---
# <a name="file-storage-support-in-lync-server-2013"></a><span data-ttu-id="f36f8-102">Lync Server 2013 中的文件存储支持</span><span class="sxs-lookup"><span data-stu-id="f36f8-102">File storage support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f36f8-103">_**上次修改的主题：** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="f36f8-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="f36f8-104">Lync Server 2013 对所有文件存储使用相同的文件存储。</span><span class="sxs-lookup"><span data-stu-id="f36f8-104">Lync Server 2013 uses the same file store for all file storage.</span></span> <span data-ttu-id="f36f8-105">文件存储支持包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="f36f8-105">File storage support includes the following:</span></span>

  - <span data-ttu-id="f36f8-106">直接附加存储上的文件共享 (DAS) 或存储区域网络 (SAN) ，包括分布式文件系统 (DFS) 以及独立磁盘冗余阵列 (RAID) 用于文件存储。</span><span class="sxs-lookup"><span data-stu-id="f36f8-106">A file share on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS), and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="f36f8-107">有关存储要求的详细信息，请参阅规划文档中的 lync server 2013 中的 [前端服务器、即时消息和2013状态的技术要求](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) 以及 lync [server 中的控制器的硬件和软件要求](lync-server-2013-hardware-and-software-requirements-for-the-director.md) 。</span><span class="sxs-lookup"><span data-stu-id="f36f8-107">For details about storage requirements, see [Technical requirements for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) and [Hardware and software requirements for the Director in Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) in the Planning documentation.</span></span> <span data-ttu-id="f36f8-108">有关适用于 Windows Server 2008 操作系统的 DFS 的详细信息，请参阅 Windows Server 2008 at 的 DFS 分步指南 [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835) 。</span><span class="sxs-lookup"><span data-stu-id="f36f8-108">For details about DFS for Windows Server 2008 operating system, see the DFS Step-by-Step Guide for Windows Server 2008 at [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835).</span></span>

  - <span data-ttu-id="f36f8-109">文件共享的共享群集。</span><span class="sxs-lookup"><span data-stu-id="f36f8-109">A shared cluster for the file share.</span></span> <span data-ttu-id="f36f8-110">如果使用共享群集，则应使用运行 Windows Server 2008 或 Windows Server 2008 R2 的群集服务器。</span><span class="sxs-lookup"><span data-stu-id="f36f8-110">If you use a shared cluster, you should use cluster servers running Windows Server 2008 or Windows Server 2008 R2.</span></span> <span data-ttu-id="f36f8-111">使用运行较旧版本的 Windows 的群集服务器可能会导致权限问题，从而阻止某些功能可用。</span><span class="sxs-lookup"><span data-stu-id="f36f8-111">Using cluster servers running an older version of Windows may result in permission issues that prevent some features from being available.</span></span> <span data-ttu-id="f36f8-112">使用群集管理器创建文件共享。</span><span class="sxs-lookup"><span data-stu-id="f36f8-112">Use the Cluster Administrator to create the file shares.</span></span> <span data-ttu-id="f36f8-113">有关使用群集管理器的详细信息，请参阅中的 Microsoft 知识库文章284838，"如何使用 Cluster.exe 创建服务器群集文件共享" [https://go.microsoft.com/fwlink/p/?linkId=140899](https://go.microsoft.com/fwlink/p/?linkid=140899) 。</span><span class="sxs-lookup"><span data-stu-id="f36f8-113">For details about using the Cluster Administrator, see Microsoft Knowledge Base article 284838, "How to Create a Server Cluster File Share with Cluster.exe" at [https://go.microsoft.com/fwlink/p/?linkId=140899](https://go.microsoft.com/fwlink/p/?linkid=140899).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

