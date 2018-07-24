---
title: 将数据库添加到 AlwaysOn 可用性组中 Skype，业务服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 摘要： 了解如何将多个 Skype 业务服务器数据库添加到 Skype 中现有的 AlwaysOn 可用性组，业务服务器。
ms.openlocfilehash: f055466788494f10575b7bd3710705a138c456b2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20976322"
---
# <a name="add-databases-to-an-alwayson-availability-group-in-skype-for-business-server"></a><span data-ttu-id="40164-103">将数据库添加到 AlwaysOn 可用性组中 Skype，业务服务器</span><span class="sxs-lookup"><span data-stu-id="40164-103">Add databases to an AlwaysOn Availability Group in Skype for Business Server</span></span>
 
<span data-ttu-id="40164-104">**摘要：** 了解如何为业务服务器到 Skype 中现有的 AlwaysOn 可用性组添加业务服务器数据库的详细 Skype。</span><span class="sxs-lookup"><span data-stu-id="40164-104">**Summary:** Learn how to add more Skype for Business Server databases to an existing AlwaysOn Availability Group in Skype for Business Server.</span></span>
  
### <a name="adding-databases-to-an-alwayson-availability-group"></a><span data-ttu-id="40164-105">将数据库添加到 AlwaysOn 可用性组</span><span class="sxs-lookup"><span data-stu-id="40164-105">Adding databases to an AlwaysOn Availability Group</span></span>

1. <span data-ttu-id="40164-106">打开 SQL Server Management Studio，并导航到 AlwaysOn 可用性组。</span><span class="sxs-lookup"><span data-stu-id="40164-106">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="40164-107">其进行故障转移到主副本。</span><span class="sxs-lookup"><span data-stu-id="40164-107">Fail it over to the primary replica.</span></span>
    
2. <span data-ttu-id="40164-108">在拓扑生成器中，AlwaysOn 可用性组的 SQL Server FQDN 设置到该组的主节点的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="40164-108">In Topology Builder, set the SQL Server FQDN of the AlwaysOn Availability Group to the FQDN of the primary node of that group.</span></span>
    
  - <span data-ttu-id="40164-109">打开拓扑生成器，选择**下载从现有部署的拓扑**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="40164-109">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
  - <span data-ttu-id="40164-110">依次展开 Skype for Business Server、你的拓扑，以及“**SQL Server 存储**”。</span><span class="sxs-lookup"><span data-stu-id="40164-110">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="40164-111">右键单击新 AlwaysOn 可用性组的 SQL 存储，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="40164-111">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
  - <span data-ttu-id="40164-112">底部的页上，在**SQL Server FQDN**框中，键入 AlwaysOn 可用性组的主节点的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="40164-112">At the bottom of the page, in the **SQL Server FQDN** box, type in the FQDN of the primary node of the AlwaysOn Availability Group.</span></span>
    
3. <span data-ttu-id="40164-p103">发布拓扑。从“**操作**”菜单中，单击“**拓扑**”，然后单击“**发布**”。然后在确认页中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="40164-p103">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
4. <span data-ttu-id="40164-116">使用 SQL Server Management Studio 将新数据库添加到 AlwaysOn 可用性组。</span><span class="sxs-lookup"><span data-stu-id="40164-116">Use SQL Server Management Studio to add the new database to the AlwaysOn Availability Group.</span></span>
    

