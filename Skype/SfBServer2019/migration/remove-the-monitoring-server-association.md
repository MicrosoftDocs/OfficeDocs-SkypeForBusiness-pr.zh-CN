---
title: 删除监控服务器关联
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 若要删除监视服务器，您需要更改或清除关联的前端池、前端服务器、Survivable 分支设备和 Survivable 分支服务器上的依赖项。 您可以编辑前端池、前端服务器、Survivable 分支设备和 Survivable 分支服务器的属性以删除依赖项。 清除依赖项并在拓扑生成器中删除服务器后，系统会通知拓扑生成器中关联的数据库存储对象也将被删除。
ms.openlocfilehash: dafbeb88773330164a5daf2144988d1afb2776a8
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753414"
---
# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="1ac00-105">删除监控服务器关联</span><span class="sxs-lookup"><span data-stu-id="1ac00-105">Remove the Monitoring server association</span></span>

<span data-ttu-id="1ac00-106">若要删除监视服务器，您需要更改或清除关联的前端池、前端服务器、Survivable 分支设备和 Survivable 分支服务器上的依赖项。</span><span class="sxs-lookup"><span data-stu-id="1ac00-106">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="1ac00-107">您可以编辑前端池、前端服务器、Survivable 分支设备和 Survivable 分支服务器的属性以删除依赖项。</span><span class="sxs-lookup"><span data-stu-id="1ac00-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="1ac00-108">清除依赖项并在拓扑生成器中删除服务器后，系统会通知拓扑生成器中关联的数据库存储对象也将被删除。</span><span class="sxs-lookup"><span data-stu-id="1ac00-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="1ac00-109">删除监控服务器关联</span><span class="sxs-lookup"><span data-stu-id="1ac00-109">To remove the Monitoring Server association</span></span>

1. <span data-ttu-id="1ac00-110">在 Skype for Business Server 2019 前端服务器上，打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="1ac00-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="1ac00-111">导航到 "旧版安装" 节点。</span><span class="sxs-lookup"><span data-stu-id="1ac00-111">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="1ac00-112">在拓扑生成器中，展开 " **Enterprise Edition 前端池**"、" **Standard edition 前端服务器**" 或 "**分支站点**"，具体取决于监视服务器的定义位置。</span><span class="sxs-lookup"><span data-stu-id="1ac00-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Monitoring Server is defined.</span></span>
    
4. <span data-ttu-id="1ac00-113">如果你有与 Survivable 分支服务器相关联的，请展开 "**分支站点**"，展开分支站点名称，然后展开 " **Survivable 分支设备**"。</span><span class="sxs-lookup"><span data-stu-id="1ac00-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1ac00-114">用户界面中的**Survivable 分支设备**适用于 Survivable 分支服务器和 Survivable 分支设备。</span><span class="sxs-lookup"><span data-stu-id="1ac00-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="1ac00-115">右键单击与监视服务器关联的池、服务器或设备，然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="1ac00-115">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="1ac00-116">在 "**编辑属性**" 中的 "**常规**  >  **关联**" 下，清除 "**关联监视服务器**" 复选框，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="1ac00-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="1ac00-117">对与监视服务器关联的任何其他池、服务器或设备重复上一步骤。</span><span class="sxs-lookup"><span data-stu-id="1ac00-117">Repeat the previous step for any other pool, server, or device associated with the Monitoring Server.</span></span>
    
8. <span data-ttu-id="1ac00-118">右键单击监视服务器，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="1ac00-118">Right-click the Monitoring Server, and then click **Delete**.</span></span> 
    
9. <span data-ttu-id="1ac00-119">在“删除相关存储”\*\*\*\* 上，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1ac00-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="1ac00-120">根据需要发布拓扑、检查复制状态并运行 Skype for Business Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="1ac00-120">Publish the topology, check replication status, and run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

