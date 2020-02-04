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
ms.openlocfilehash: c013159de83d258273e381dd54556bcceec056f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-file-store-in-lync-server-2013"></a><span data-ttu-id="034b7-102">在 Lync Server 2013 中还原文件存储</span><span class="sxs-lookup"><span data-stu-id="034b7-102">Restoring a file store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="034b7-103">_**主题上次修改时间：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="034b7-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="034b7-104">标准版的文件存储通常位于标准版服务器上。</span><span class="sxs-lookup"><span data-stu-id="034b7-104">File Stores for Standard Edition are typically located on the Standard Edition server.</span></span> <span data-ttu-id="034b7-105">企业版的文件存储通常位于文件服务器或群集上。</span><span class="sxs-lookup"><span data-stu-id="034b7-105">File Stores for Enterprise Edition are typically located on a file server or cluster.</span></span> <span data-ttu-id="034b7-106">以下过程介绍了如何还原文件存储。</span><span class="sxs-lookup"><span data-stu-id="034b7-106">The following procedure describes how to restore a File Store.</span></span>

<div>

## <a name="to-restore-a-file-store"></a><span data-ttu-id="034b7-107">还原文件存储</span><span class="sxs-lookup"><span data-stu-id="034b7-107">To restore a File Store</span></span>

1.  <span data-ttu-id="034b7-108">如果文件存储失败，请将相应的文件存储区从\\ $Backup 复制到文件服务器或标准版服务器上的文件存储位置，然后共享该文件夹。</span><span class="sxs-lookup"><span data-stu-id="034b7-108">If a File Store fails, copy the appropriate File Store from $Backup\\ to the File Store location on the file server or Standard Edition server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="034b7-109">已还原文件存储的路径和文件名应与备份的文件存储完全相同，以便使用这些文件的组件可以访问它们。</span><span class="sxs-lookup"><span data-stu-id="034b7-109">The path and file name for the restored File Store should be exactly the same as the backed up File Store, so that components that use the files can access them.</span></span>

    
    </div>

2.  <span data-ttu-id="034b7-110">如有必要，请设置文件存储的访问控制列表（Acl）。</span><span class="sxs-lookup"><span data-stu-id="034b7-110">If necessary, set the access control lists (ACLs) for the File Store.</span></span> <span data-ttu-id="034b7-111">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="034b7-111">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="034b7-112">只有在还原过程中没有其他方法运行拓扑生成器时，才需要执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="034b7-112">You need to perform this step only if you have not otherwise run Topology Builder during your restoration process.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

