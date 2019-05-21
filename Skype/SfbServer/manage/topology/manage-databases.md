---
title: 在 Skype for Business Server 中使用 "AlwaysOn 可用性" 组管理数据库
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: '摘要: 了解如何将更多 Skype for business 服务器数据库添加到现有 AlwaysOn 可用性组, 并了解在修补或升级作为 Skype for AlwaysOn 可用性组一部分的后端服务器后所需的附加步骤企业服务器。'
ms.openlocfilehash: c6d8877448a68aa2331f3c290170418f6dca08ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275183"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="f4495-103">在 Skype for Business Server 中使用 "AlwaysOn 可用性" 组管理数据库</span><span class="sxs-lookup"><span data-stu-id="f4495-103">Manage databases with an AlwaysOn Availability Group in Skype for Business Server</span></span>

<span data-ttu-id="f4495-104">使用本文中的步骤将更多 Skype for business 服务器数据库添加到 Skype for Business Server 中的现有 AlwaysOn 可用性组, 并在修补或升级属于 AlwaysOn 的后端服务器后了解必要的附加步骤Skype for Business 服务器中的 "可用性" 组。</span><span class="sxs-lookup"><span data-stu-id="f4495-104">Use the steps in this article to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server, and find out about the necessary additional steps after you patch or upgrade a Back End Server that is part of a AlwaysOn Availability Group in Skype for Business Server.</span></span>

## <a name="add-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="f4495-105">将数据库添加到 AlwaysOn 可用性组</span><span class="sxs-lookup"><span data-stu-id="f4495-105">Add databases to an AlwaysOn Availability Group</span></span> 

1. <span data-ttu-id="f4495-106">打开 SQL Server Management Studio, 然后导航到 "AlwaysOn 可用性" 组。</span><span class="sxs-lookup"><span data-stu-id="f4495-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="f4495-107">将其故障转移到主副本。</span><span class="sxs-lookup"><span data-stu-id="f4495-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="f4495-108">在拓扑生成器中, 将 "AlwaysOn 可用性" 组的 SQL Server FQDN 设置为该组的主节点的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="f4495-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
   - <span data-ttu-id="f4495-109">打开拓扑生成器,**从现有部署**中选择 "下载拓扑", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="f4495-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="f4495-110">依次展开 Skype for Business Server、你的拓扑，以及“**SQL Server 存储**”。</span><span class="sxs-lookup"><span data-stu-id="f4495-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="f4495-111">右键单击新的 "AlwaysOn 可用性" 组的 SQL 应用商店, 然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="f4495-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="f4495-112">在页面底部的 " **SQL SERVER FQDN** " 框中, 键入 AlwaysOn 可用性组的主节点的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="f4495-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="f4495-113">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="f4495-113">Publish the topology.</span></span> <span data-ttu-id="f4495-114">从“**操作**”菜单中，单击“**拓扑**”，然后单击“**发布**”。</span><span class="sxs-lookup"><span data-stu-id="f4495-114">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="f4495-115">在确认页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="f4495-115">Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="f4495-116">使用 SQL Server Management Studio 将新数据库添加到 "AlwaysOn 可用性" 组。</span><span class="sxs-lookup"><span data-stu-id="f4495-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a><span data-ttu-id="f4495-117">修补或更新 AlwaysOn 可用性组中的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="f4495-117">Patch or update a SQL Server in an AlwaysOn Availability Group</span></span>

<span data-ttu-id="f4495-118">在修补属于 AlwaysOn 可用性组的后端服务器之后, 必须重新发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="f4495-118">After patching a Back End Server that is part of an AlwaysOn Availability Group, you must republish the topology.</span></span>

1. <span data-ttu-id="f4495-119">在你的一台或多台 Skype for Business 服务器上安装更新。</span><span class="sxs-lookup"><span data-stu-id="f4495-119">Install the update on your Skype for Business server or servers.</span></span>
    
2. <span data-ttu-id="f4495-120">在 Skype for Business 命令行管理程序中运行以下 PowerShell 命令（用被授予适当权限可向 SQL AlwaysOn 数据库应用更改的帐户登录），如下所述：</span><span class="sxs-lookup"><span data-stu-id="f4495-120">Run the following PowerShell command in your Skype for Business Management Shell (logged in with an account that's appropriately permissioned to apply changes to the SQL AlwaysOn databases) as follows:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    <span data-ttu-id="f4495-121">其中，[sqlpool.contoso.com] 被替换为 AlwaysOn 可用性组的完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="f4495-121">Where [sqlpool.contoso.com] is replaced with the fully qualified domain name (FQDN) of your AlwaysOn availability group.</span></span>
