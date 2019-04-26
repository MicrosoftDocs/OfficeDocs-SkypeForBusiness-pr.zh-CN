---
title: 将试点池连接到旧 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 部署业务服务器 2019 Skype 之后，您需要配置联盟路由，为您的网站。 若要使用正在使用旧安装的联盟的路由，必须配置的业务服务器 2019 Skype 要使用该路由。
ms.openlocfilehash: 5a3498041b4af762d184cd56e3883a90612b13e0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238666"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="6304f-104">将试点池连接到旧 Edge Server</span><span class="sxs-lookup"><span data-stu-id="6304f-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="6304f-105">部署业务服务器 2019 Skype 之后，您需要配置联盟路由，为您的网站。</span><span class="sxs-lookup"><span data-stu-id="6304f-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="6304f-106">若要使用正在使用旧安装的联盟的路由，必须配置的业务服务器 2019 Skype 要使用该路由。</span><span class="sxs-lookup"><span data-stu-id="6304f-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="6304f-107">若要启用业务服务器 2019年网站 Skype，以使用控制器和边缘服务器的旧部署，请使用拓扑生成器来关联旧式边缘池。</span><span class="sxs-lookup"><span data-stu-id="6304f-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="6304f-108">使用拓扑生成器关联旧式边缘池</span><span class="sxs-lookup"><span data-stu-id="6304f-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="6304f-109">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="6304f-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="6304f-110">选择您的网站，即**Skype 业务 server**节点正下方。</span><span class="sxs-lookup"><span data-stu-id="6304f-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="6304f-111">在**操作**菜单中，单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="6304f-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="6304f-112">在左窗格中，选择**联盟路由**。</span><span class="sxs-lookup"><span data-stu-id="6304f-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="6304f-113">在**站点联盟路由分配**下选择**启用 SIP 联盟**，，然后选择上旧控制器或旧的边缘服务器，如果未不列出任何控制器。</span><span class="sxs-lookup"><span data-stu-id="6304f-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="6304f-114">单击**确定**以关闭**编辑属性**页。</span><span class="sxs-lookup"><span data-stu-id="6304f-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="6304f-115">在拓扑生成器，业务服务器 2019年节点 Skype 导航到**Standard Edition server**或**Enterprise Edition 前端池**，右键单击池，，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="6304f-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="6304f-116">在**关联**下选择**关联边缘池 （用于媒体组件）** 旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="6304f-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="6304f-117">从列表中，选择旧边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="6304f-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="6304f-118">单击**确定**以关闭**编辑属性**页。</span><span class="sxs-lookup"><span data-stu-id="6304f-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="6304f-119">在**拓扑生成器**中，选择顶层节点， **Skype 业务服务器**。</span><span class="sxs-lookup"><span data-stu-id="6304f-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="6304f-120">从**操作**菜单中，单击**发布拓扑**，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6304f-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="6304f-121">**发布向导**完成后，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="6304f-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

