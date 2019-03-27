---
title: 删除前端池或 Standard Edition Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本主题将指导您完成删除前端池或 Standard Edition 前端服务器的过程。 删除前端池时，您删除每个前端服务器池删除过程一部分属于池。 删除 Standard Edition 前端服务器时，您必须从拓扑生成器删除 SQL 存储定义。
ms.openlocfilehash: 394edcd6f5c89478ed98abebe0be29720d009107
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30872715"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="87e02-105">删除前端池或 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="87e02-105">Remove Front End pool or Standard Edition server</span></span>

<span data-ttu-id="87e02-106">本文将指导您完成删除前端池或 Standard Edition 前端服务器的过程。</span><span class="sxs-lookup"><span data-stu-id="87e02-106">This article guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="87e02-107">删除前端池时，您删除每个前端服务器池删除过程一部分属于池。</span><span class="sxs-lookup"><span data-stu-id="87e02-107">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="87e02-108">删除 Standard Edition 前端服务器时，您必须从拓扑生成器删除 SQL 存储定义。</span><span class="sxs-lookup"><span data-stu-id="87e02-108">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>
  
## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="87e02-109">删除前端服务器池</span><span class="sxs-lookup"><span data-stu-id="87e02-109">To remove a Front End Server pool</span></span>

1. <span data-ttu-id="87e02-110">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="87e02-110">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="87e02-111">导航到旧节点。</span><span class="sxs-lookup"><span data-stu-id="87e02-111">Navigate to the legacy node.</span></span>
    
3. <span data-ttu-id="87e02-112">展开**Enterprise Edition 前端池**，展开前端池，右键单击您想要删除的前端池，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="87e02-112">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="87e02-113">发布拓扑，检查复制状态，并根据需要运行旧部署向导。</span><span class="sxs-lookup"><span data-stu-id="87e02-113">Publish the topology, check replication status, and then run the legacy Deployment Wizard as needed.</span></span> 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="87e02-114">删除 Standard Edition 前端服务器</span><span class="sxs-lookup"><span data-stu-id="87e02-114">To remove a Standard Edition Front End server</span></span>

1. <span data-ttu-id="87e02-115">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="87e02-115">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="87e02-116">导航到旧的安装节点。</span><span class="sxs-lookup"><span data-stu-id="87e02-116">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="87e02-117">展开**Standard Edition 前端服务器**，右键单击您想要删除的前端最终服务器，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="87e02-117">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="87e02-118">展开**SQL 存储**，右键单击与 Standard Edition 前端服务器关联的 SQL Server 数据库，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="87e02-118">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="87e02-119">必须从 Standard Edition 前端服务器中删除的并置的 SQL Server 数据库的定义。</span><span class="sxs-lookup"><span data-stu-id="87e02-119">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span> 
  
5. <span data-ttu-id="87e02-120">发布拓扑，检查复制状态，并根据需要然后运行部署向导。</span><span class="sxs-lookup"><span data-stu-id="87e02-120">Publish the topology, check replication status, and then run the Deployment Wizard as needed.</span></span> 
    

