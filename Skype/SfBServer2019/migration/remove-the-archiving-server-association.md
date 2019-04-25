---
title: 删除存档服务器关联
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 若要删除某个存档服务器，您需要更改或清除关联前端池，前端服务器、 Survivable Branch Appliance 和 Survivable Branch Server 上的相关性。 编辑前端服务器、 Survivable Branch Appliance 和 Survivable Branch Server 中删除依赖关系前端池的属性。 清除依赖项并删除拓扑生成器中的服务器后，将通知您在拓扑生成器中的关联的数据库存储对象也将被删除。
ms.openlocfilehash: 15e6b33decb11ce7ed4550b0d84cc346a0baf073
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231412"
---
# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="33fa5-105">删除存档服务器关联</span><span class="sxs-lookup"><span data-stu-id="33fa5-105">Remove the Archiving server association</span></span>

<span data-ttu-id="33fa5-106">若要删除某个存档服务器，您需要更改或清除关联前端池、 前端服务器、 Survivable Branch Appliance 和 Survivable Branch Server 上的相关性。</span><span class="sxs-lookup"><span data-stu-id="33fa5-106">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="33fa5-107">编辑前端池、 前端服务器、 Survivable Branch Appliance 和 Survivable Branch Server 中删除依赖关系的属性。</span><span class="sxs-lookup"><span data-stu-id="33fa5-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="33fa5-108">清除依赖关系和删除拓扑生成器中的服务器后，将通知您在拓扑生成器中的关联的数据库存储对象也将被删除。</span><span class="sxs-lookup"><span data-stu-id="33fa5-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="33fa5-109">删除存档服务器关联</span><span class="sxs-lookup"><span data-stu-id="33fa5-109">To remove the Archiving Server association</span></span>

1. <span data-ttu-id="33fa5-110">在业务 Server 2019 前端服务器的 Skype，打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="33fa5-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="33fa5-111">导航到旧的安装节点。</span><span class="sxs-lookup"><span data-stu-id="33fa5-111">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="33fa5-112">在拓扑生成器中，根据定义存档服务器的位置展开**Enterprise Edition 前端池**、 **Standard Edition 前端服务器**或**分支站点**。</span><span class="sxs-lookup"><span data-stu-id="33fa5-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Archiving Server is defined.</span></span>
    
4. <span data-ttu-id="33fa5-113">如果您有关联的 Survivable Branch Server，展开**分支站点**，展开分支站点名称，，然后展开**Survivable Branch Appliance**。</span><span class="sxs-lookup"><span data-stu-id="33fa5-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="33fa5-114">用户界面中的**survivable Branch Appliance**适用于 Survivable Branch Appliance 和 Survivable Branch Server。</span><span class="sxs-lookup"><span data-stu-id="33fa5-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="33fa5-115">右键单击池、 服务器或存档服务器，与相关联的设备，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="33fa5-115">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="33fa5-116">在**编辑属性**在**常规**下 > **关联**，清除**关联存档服务器**复选框，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="33fa5-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="33fa5-117">对任何其他池、 服务器或与您要删除存档服务器相关联的设备重复上一步。</span><span class="sxs-lookup"><span data-stu-id="33fa5-117">Repeat the previous step for any other pool, server, or device associated with the Archiving Server that you want to remove.</span></span>
    
8. <span data-ttu-id="33fa5-118">右键单击存档服务器，，，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="33fa5-118">Right-click the Archiving Server, and then click **Delete**.</span></span>
    
9. <span data-ttu-id="33fa5-119">在**删除相关存储**，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="33fa5-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="33fa5-120">发布拓扑，检查复制状态，并根据需要业务 Server 部署向导运行 Skype。</span><span class="sxs-lookup"><span data-stu-id="33fa5-120">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

