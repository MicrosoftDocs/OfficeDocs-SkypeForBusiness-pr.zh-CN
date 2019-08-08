---
title: 将试点池连接到旧 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 部署 Skype for Business Server 2019 后, 您需要为您的站点配置联盟路由。 为了使用旧版安装使用的联盟路由, 必须将 Skype for Business Server 2019 配置为使用此路由。
ms.openlocfilehash: 7a5a65e1488d5a119e3d11affbbaa9995a06626e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239222"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="00353-104">将试点池连接到旧 Edge Server</span><span class="sxs-lookup"><span data-stu-id="00353-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="00353-105">部署 Skype for Business Server 2019 后, 您需要为您的站点配置联盟路由。</span><span class="sxs-lookup"><span data-stu-id="00353-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="00353-106">为了使用旧版安装使用的联盟路由, 必须将 Skype for Business Server 2019 配置为使用此路由。</span><span class="sxs-lookup"><span data-stu-id="00353-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="00353-107">若要启用 Skype for Business Server 2019 网站使用旧版部署的 Director 和 Edge 服务器, 请使用拓扑生成器关联旧版 Edge 池。</span><span class="sxs-lookup"><span data-stu-id="00353-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="00353-108">使用拓扑生成器关联旧式边缘池</span><span class="sxs-lookup"><span data-stu-id="00353-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="00353-109">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="00353-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="00353-110">选择您的网站, 它位于**Skype For Business 服务器**节点正下方。</span><span class="sxs-lookup"><span data-stu-id="00353-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="00353-111">在 "**操作**" 菜单上, 单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="00353-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="00353-112">在左窗格中, 选择 "**联盟路由**"。</span><span class="sxs-lookup"><span data-stu-id="00353-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="00353-113">在 "**站点联合路由分配**" 下, 选择 "**启用 SIP 联盟**", 然后选择旧式控制器, 如果未列出 Director, 则选择旧版边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="00353-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="00353-114">单击 **"确定"** 以关闭 "**编辑属性**" 页面。</span><span class="sxs-lookup"><span data-stu-id="00353-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="00353-115">在拓扑生成器中, 在 Skype for Business Server 2019 节点下, 导航到**标准版服务器**或**企业版前端池**, 右键单击该池, 然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="00353-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="00353-116">在 "**关联**" 下, 选中 "**关联边缘池" (对于媒体组件)** 旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="00353-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="00353-117">从列表中, 选择旧式边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="00353-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="00353-118">单击 **"确定"** 以关闭 "**编辑属性**" 页面。</span><span class="sxs-lookup"><span data-stu-id="00353-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="00353-119">在**拓扑生成器**中, 选择最上面的节点 " **Skype For**business" 服务器。</span><span class="sxs-lookup"><span data-stu-id="00353-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="00353-120">从 "**操作**" 菜单中, 单击 "**发布拓扑**", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="00353-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="00353-121">**发布向导**完成后, 单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="00353-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

