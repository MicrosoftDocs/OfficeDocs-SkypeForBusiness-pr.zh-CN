---
title: 删除前端池或 Standard Edition Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本主题将指导你完成删除前端池或标准版前端服务器的过程。 删除前端池时, 将在池删除过程中删除属于该池的每个前端服务器。 删除标准版前端服务器时, 必须从拓扑生成器中删除 SQL 应用商店定义。
ms.openlocfilehash: 57679fb248c9281b79c12be98b7fd5246c9afd38
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244265"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="e14bf-105">删除前端池或 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="e14bf-105">Remove Front End pool or Standard Edition server</span></span>

<span data-ttu-id="e14bf-106">本文将引导你完成删除前端池或标准版前端服务器的过程。</span><span class="sxs-lookup"><span data-stu-id="e14bf-106">This article guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="e14bf-107">删除前端池时, 将在池删除过程中删除属于该池的每个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="e14bf-107">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="e14bf-108">删除标准版前端服务器时, 必须从拓扑生成器中删除 SQL 应用商店定义。</span><span class="sxs-lookup"><span data-stu-id="e14bf-108">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>
  
## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="e14bf-109">删除前端服务器池</span><span class="sxs-lookup"><span data-stu-id="e14bf-109">To remove a Front End Server pool</span></span>

1. <span data-ttu-id="e14bf-110">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="e14bf-110">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="e14bf-111">导航到 "旧版" 节点。</span><span class="sxs-lookup"><span data-stu-id="e14bf-111">Navigate to the legacy node.</span></span>
    
3. <span data-ttu-id="e14bf-112">展开 "**企业版前端池**", 展开 "前端池", 右键单击要删除的前端池, 然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="e14bf-112">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="e14bf-113">发布拓扑, 检查复制状态, 然后根据需要运行旧版部署向导。</span><span class="sxs-lookup"><span data-stu-id="e14bf-113">Publish the topology, check replication status, and then run the legacy Deployment Wizard as needed.</span></span> 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="e14bf-114">删除标准版前端服务器</span><span class="sxs-lookup"><span data-stu-id="e14bf-114">To remove a Standard Edition Front End server</span></span>

1. <span data-ttu-id="e14bf-115">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="e14bf-115">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="e14bf-116">导航到 "旧版安装" 节点。</span><span class="sxs-lookup"><span data-stu-id="e14bf-116">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="e14bf-117">展开**标准版前端服务器**, 右键单击要删除的前端服务器, 然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="e14bf-117">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="e14bf-118">展开 " **sql 存储**", 右键单击与标准版前端服务器关联的 SQL Server 数据库, 然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="e14bf-118">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e14bf-119">必须从标准版前端服务器中删除 collocated SQL Server 数据库的定义。</span><span class="sxs-lookup"><span data-stu-id="e14bf-119">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span> 
  
5. <span data-ttu-id="e14bf-120">发布拓扑, 检查复制状态, 然后根据需要运行部署向导。</span><span class="sxs-lookup"><span data-stu-id="e14bf-120">Publish the topology, check replication status, and then run the Deployment Wizard as needed.</span></span> 
    

