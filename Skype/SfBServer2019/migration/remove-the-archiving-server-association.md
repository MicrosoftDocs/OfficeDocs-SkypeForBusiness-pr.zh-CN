---
title: 删除存档服务器关联
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 若要删除存档服务器, 你需要更改或清除关联的前端池、前端服务器、Survivable 分支设备和 Survivable 分支服务器上的依赖关系。 编辑前端池、前端服务器、Survivable 分支装置和 Survivable 分支服务器的属性以删除相关性。 清除相关性并在拓扑生成器中删除服务器后, 系统会通知你拓扑生成器中的相关数据库存储对象也将被删除。
ms.openlocfilehash: 52bba22f678bb4aee1ce406613ce19bb686a78c4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301109"
---
# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="d053e-105">删除存档服务器关联</span><span class="sxs-lookup"><span data-stu-id="d053e-105">Remove the Archiving server association</span></span>

<span data-ttu-id="d053e-106">若要删除存档服务器, 你需要更改或清除关联的前端池、前端服务器、Survivable 分支装置和 Survivable 分支服务器上的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="d053e-106">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="d053e-107">编辑 "前端池"、"前端服务器"、"Survivable 分支" 装置和 "Survivable 分支服务器" 的属性以删除相关性。</span><span class="sxs-lookup"><span data-stu-id="d053e-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="d053e-108">清除相关性并在拓扑生成器中删除服务器后, 系统会通知你拓扑生成器中关联的数据库存储对象也将被删除。</span><span class="sxs-lookup"><span data-stu-id="d053e-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="d053e-109">删除存档服务器关联</span><span class="sxs-lookup"><span data-stu-id="d053e-109">To remove the Archiving Server association</span></span>

1. <span data-ttu-id="d053e-110">在 Skype for Business 服务器2019前端服务器上, 打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="d053e-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="d053e-111">导航到 "旧版安装" 节点。</span><span class="sxs-lookup"><span data-stu-id="d053e-111">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="d053e-112">在拓扑生成器中, 展开 "**企业版前端池**"、"**标准版前端服务器**" 或 "**分支站点**", 具体取决于定义存档服务器的位置。</span><span class="sxs-lookup"><span data-stu-id="d053e-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Archiving Server is defined.</span></span>
    
4. <span data-ttu-id="d053e-113">如果您有关联的 Survivable 分支服务器, 请展开 "**分支站点**", 展开 "分支站点名称", 然后展开 "**分支机构" Survivable**。</span><span class="sxs-lookup"><span data-stu-id="d053e-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d053e-114">用户界面中的**Survivable 分支装置**适用于 Survivable 分支服务器和 Survivable 分支装置。</span><span class="sxs-lookup"><span data-stu-id="d053e-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="d053e-115">右键单击与存档服务器相关联的池、服务器或设备, 然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="d053e-115">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="d053e-116">在 "**编辑属性**" 下的 "**常规** > **关联**" 下, 清除 "**关联存档服务器**" 复选框, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="d053e-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="d053e-117">对与要删除的存档服务器关联的任何其他池、服务器或设备重复上一步骤。</span><span class="sxs-lookup"><span data-stu-id="d053e-117">Repeat the previous step for any other pool, server, or device associated with the Archiving Server that you want to remove.</span></span>
    
8. <span data-ttu-id="d053e-118">右键单击存档服务器, 然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="d053e-118">Right-click the Archiving Server, and then click **Delete**.</span></span>
    
9. <span data-ttu-id="d053e-119">在 "**删除从属存储**" 中, 单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="d053e-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="d053e-120">发布拓扑, 检查复制状态, 然后根据需要运行 Skype for Business 服务器部署向导。</span><span class="sxs-lookup"><span data-stu-id="d053e-120">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

