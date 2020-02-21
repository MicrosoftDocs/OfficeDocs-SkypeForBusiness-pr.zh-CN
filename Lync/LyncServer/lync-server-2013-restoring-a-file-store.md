---
title: Lync Server 2013：还原文件存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a file store
ms:assetid: 89916fc6-31d3-4c7f-9eaf-c02584761ef4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202180(v=OCS.15)
ms:contentKeyID: 51541491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b73ba97ccadcc5cb34a5dbc3963d80620da8e516
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-file-store-in-lync-server-2013"></a><span data-ttu-id="a8d20-102">在 Lync Server 2013 中还原文件存储</span><span class="sxs-lookup"><span data-stu-id="a8d20-102">Restoring a file store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8d20-103">_**上次修改的主题：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="a8d20-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="a8d20-104">Standard Edition 的文件存储通常位于 Standard Edition server 上。</span><span class="sxs-lookup"><span data-stu-id="a8d20-104">File Stores for Standard Edition are typically located on the Standard Edition server.</span></span> <span data-ttu-id="a8d20-105">Enterprise Edition 的文件存储通常位于文件服务器或群集上。</span><span class="sxs-lookup"><span data-stu-id="a8d20-105">File Stores for Enterprise Edition are typically located on a file server or cluster.</span></span> <span data-ttu-id="a8d20-106">以下过程介绍了如何还原文件存储。</span><span class="sxs-lookup"><span data-stu-id="a8d20-106">The following procedure describes how to restore a File Store.</span></span>

<div>

## <a name="to-restore-a-file-store"></a><span data-ttu-id="a8d20-107">还原文件存储</span><span class="sxs-lookup"><span data-stu-id="a8d20-107">To restore a File Store</span></span>

1.  <span data-ttu-id="a8d20-108">如果文件存储失败，请将相应的文件存储从 $Backup\\复制到文件服务器或 Standard Edition 服务器上的文件存储位置，然后共享该文件夹。</span><span class="sxs-lookup"><span data-stu-id="a8d20-108">If a File Store fails, copy the appropriate File Store from $Backup\\ to the File Store location on the file server or Standard Edition server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a8d20-109">已还原文件存储的路径和文件名应与备份的文件存储完全相同，以便使用这些文件的组件可以访问它们。</span><span class="sxs-lookup"><span data-stu-id="a8d20-109">The path and file name for the restored File Store should be exactly the same as the backed up File Store, so that components that use the files can access them.</span></span>

    
    </div>

2.  <span data-ttu-id="a8d20-110">如有必要，为文件存储设置访问控制列表（Acl）。</span><span class="sxs-lookup"><span data-stu-id="a8d20-110">If necessary, set the access control lists (ACLs) for the File Store.</span></span> <span data-ttu-id="a8d20-111">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="a8d20-111">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a8d20-112">只有在还原过程中未运行拓扑生成器时，才需要执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="a8d20-112">You need to perform this step only if you have not otherwise run Topology Builder during your restoration process.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

