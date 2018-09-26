---
title: 删除监控服务器关联
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 若要删除监控服务器，您需要更改或清除关联前端池，前端服务器、 Survivable Branch Appliance 和 Survivable Branch Server 上的相关性。 编辑前端服务器、 Survivable Branch Appliance 和 Survivable Branch Server 中删除依赖关系前端池的属性。 清除依赖关系和删除拓扑生成器中的服务器后，将通知您在拓扑生成器中的关联的数据库存储对象也将被删除。
ms.openlocfilehash: 01fb53a054da8f9e39dbbfbdd1ddfc08f345a1c2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030383"
---
# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="f682a-105">删除监控服务器关联</span><span class="sxs-lookup"><span data-stu-id="f682a-105">Remove the Monitoring server association</span></span>

<span data-ttu-id="f682a-106">若要删除监控服务器，您需要更改或清除关联前端池、 前端服务器、 Survivable Branch Appliance 和 Survivable Branch Server 上的相关性。</span><span class="sxs-lookup"><span data-stu-id="f682a-106">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="f682a-107">编辑前端池、 前端服务器、 Survivable Branch Appliance 和 Survivable Branch Server 中删除依赖关系的属性。</span><span class="sxs-lookup"><span data-stu-id="f682a-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="f682a-108">清除依赖关系和删除拓扑生成器中的服务器后，将通知您在拓扑生成器中的关联的数据库存储对象也将被删除。</span><span class="sxs-lookup"><span data-stu-id="f682a-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="f682a-109">删除监控服务器关联</span><span class="sxs-lookup"><span data-stu-id="f682a-109">To remove the Monitoring Server association</span></span>

1. <span data-ttu-id="f682a-110">在业务 Server 2019 前端服务器的 Skype，打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="f682a-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="f682a-111">导航到旧的安装节点。</span><span class="sxs-lookup"><span data-stu-id="f682a-111">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="f682a-112">在拓扑生成器中，根据定义监控服务器的位置展开**Enterprise Edition 前端池**、 **Standard Edition 前端服务器**或**分支站点**。</span><span class="sxs-lookup"><span data-stu-id="f682a-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Monitoring Server is defined.</span></span>
    
4. <span data-ttu-id="f682a-113">如果您有关联的 Survivable Branch Server，展开**分支站点**，展开分支站点名称，，然后展开**Survivable Branch Appliance**。</span><span class="sxs-lookup"><span data-stu-id="f682a-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f682a-114">用户界面中的**survivable Branch Appliance**适用于 Survivable Branch Appliance 和 Survivable Branch Server。</span><span class="sxs-lookup"><span data-stu-id="f682a-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="f682a-115">右键单击池、 服务器或与监控服务器相关联的设备，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="f682a-115">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="f682a-116">在**编辑属性**在**常规**下 > **关联**，清除**关联监控服务器**复选框，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f682a-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="f682a-117">对任何其他池、 服务器或监控服务器相关联的设备重复上一步。</span><span class="sxs-lookup"><span data-stu-id="f682a-117">Repeat the previous step for any other pool, server, or device associated with the Monitoring Server.</span></span>
    
8. <span data-ttu-id="f682a-118">右键单击监控服务器，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="f682a-118">Right-click the Monitoring Server, and then click **Delete**.</span></span> 
    
9. <span data-ttu-id="f682a-119">在**删除相关存储**，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f682a-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="f682a-120">发布拓扑，检查复制状态，并根据需要运行 Skype 业务 Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="f682a-120">Publish the topology, check replication status, and run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

