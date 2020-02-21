---
title: 删除前端池或 Standard Edition server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47aa2edebe202f6ed21d1b802d899faea563feba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="66218-102">删除前端池或 Standard Edition server</span><span class="sxs-lookup"><span data-stu-id="66218-102">Remove Front End pool or Standard Edition server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66218-103">_**上次修改的主题：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="66218-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="66218-104">本主题将指导您完成删除前端池或 Standard Edition 前端服务器的过程。</span><span class="sxs-lookup"><span data-stu-id="66218-104">This topic guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="66218-105">删除前端池时，会将属于池的每台前端服务器作为池删除过程的一部分删除。</span><span class="sxs-lookup"><span data-stu-id="66218-105">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="66218-106">删除 Standard Edition 前端服务器时，必须从拓扑生成器中删除 SQL 存储定义。</span><span class="sxs-lookup"><span data-stu-id="66218-106">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>

<div>

## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="66218-107">删除前端服务器池</span><span class="sxs-lookup"><span data-stu-id="66218-107">To remove a Front End Server pool</span></span>

1.  <span data-ttu-id="66218-108">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="66218-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="66218-109">导航到 "Lync Server 2010" 节点。</span><span class="sxs-lookup"><span data-stu-id="66218-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="66218-110">展开 " **Enterprise Edition 前端池**"，再展开 "前端池"，右键单击要删除的前端池，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="66218-110">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>

4.  <span data-ttu-id="66218-111">发布拓扑，检查复制状态，然后根据需要运行 Lync Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="66218-111">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="66218-112">删除 Standard Edition 前端服务器</span><span class="sxs-lookup"><span data-stu-id="66218-112">To remove a Standard Edition Front End server</span></span>

1.  <span data-ttu-id="66218-113">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="66218-113">Open Topology Builder.</span></span>

2.  <span data-ttu-id="66218-114">导航到 "Lync Server 2010" 节点。</span><span class="sxs-lookup"><span data-stu-id="66218-114">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="66218-115">展开**Standard Edition 前端服务器**，右键单击要删除的前端服务器，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="66218-115">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

4.  <span data-ttu-id="66218-116">展开 " **sql 存储**"，右键单击与 Standard Edition 前端服务器关联的 SQL Server 数据库，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="66218-116">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="66218-117">您必须从 Standard Edition 前端服务器中删除并置 SQL Server 数据库的定义。</span><span class="sxs-lookup"><span data-stu-id="66218-117">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="66218-118">发布拓扑，检查复制状态，然后根据需要运行 Lync Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="66218-118">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

