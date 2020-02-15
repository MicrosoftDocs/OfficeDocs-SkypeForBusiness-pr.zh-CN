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
ms.openlocfilehash: 60c4a3e1563890d64394f3a99141523cb95add38
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006128"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-file-store-in-lync-server-2013"></a><span data-ttu-id="35d2e-102">在 Lync Server 2013 中还原文件存储</span><span class="sxs-lookup"><span data-stu-id="35d2e-102">Restoring a file store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35d2e-103">_**上次修改的主题：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="35d2e-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="35d2e-104">Standard Edition 的文件存储通常位于 Standard Edition server 上。</span><span class="sxs-lookup"><span data-stu-id="35d2e-104">File Stores for Standard Edition are typically located on the Standard Edition server.</span></span> <span data-ttu-id="35d2e-105">Enterprise Edition 的文件存储通常位于文件服务器或群集上。</span><span class="sxs-lookup"><span data-stu-id="35d2e-105">File Stores for Enterprise Edition are typically located on a file server or cluster.</span></span> <span data-ttu-id="35d2e-106">以下过程介绍了如何还原文件存储。</span><span class="sxs-lookup"><span data-stu-id="35d2e-106">The following procedure describes how to restore a File Store.</span></span>

<div>

## <a name="to-restore-a-file-store"></a><span data-ttu-id="35d2e-107">还原文件存储</span><span class="sxs-lookup"><span data-stu-id="35d2e-107">To restore a File Store</span></span>

1.  <span data-ttu-id="35d2e-108">如果文件存储失败，请将相应的文件存储从 $Backup\\复制到文件服务器或 Standard Edition 服务器上的文件存储位置，然后共享该文件夹。</span><span class="sxs-lookup"><span data-stu-id="35d2e-108">If a File Store fails, copy the appropriate File Store from $Backup\\ to the File Store location on the file server or Standard Edition server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="35d2e-109">已还原文件存储的路径和文件名应与备份的文件存储完全相同，以便使用这些文件的组件可以访问它们。</span><span class="sxs-lookup"><span data-stu-id="35d2e-109">The path and file name for the restored File Store should be exactly the same as the backed up File Store, so that components that use the files can access them.</span></span>

    
    </div>

2.  <span data-ttu-id="35d2e-110">如有必要，为文件存储设置访问控制列表（Acl）。</span><span class="sxs-lookup"><span data-stu-id="35d2e-110">If necessary, set the access control lists (ACLs) for the File Store.</span></span> <span data-ttu-id="35d2e-111">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="35d2e-111">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="35d2e-112">只有在还原过程中未运行拓扑生成器时，才需要执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="35d2e-112">You need to perform this step only if you have not otherwise run Topology Builder during your restoration process.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

