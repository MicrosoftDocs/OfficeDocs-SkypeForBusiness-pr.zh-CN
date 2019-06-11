---
title: 将试点池连接到旧 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fc42c645548ea9bad072da5f18643271a9eceeb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="7d420-102">将试点池连接到旧 Edge Server</span><span class="sxs-lookup"><span data-stu-id="7d420-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d420-103">_**主题上次修改时间:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="7d420-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="7d420-104">部署 Lync Server 2013 后, 您需要为您的网站配置联盟路由。</span><span class="sxs-lookup"><span data-stu-id="7d420-104">After deploying Lync Server 2013, you need to configure a federation route for your site.</span></span> <span data-ttu-id="7d420-105">为了使用 Lync Server 2010 正在使用的联盟路由, Lync Server 2013 必须配置为使用此路由。</span><span class="sxs-lookup"><span data-stu-id="7d420-105">In order to use the federated route that is being used by Lync Server 2010, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="7d420-106">若要使 Lync Server 2013 网站使用 Lync Server 2010 部署的 Director 和 Edge 服务器, 请使用拓扑生成器关联旧版 Edge 池。</span><span class="sxs-lookup"><span data-stu-id="7d420-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the Lync Server 2010 deployment, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="7d420-107">使用拓扑生成器关联旧式边缘池</span><span class="sxs-lookup"><span data-stu-id="7d420-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="7d420-108">打开**拓扑生成器**。</span><span class="sxs-lookup"><span data-stu-id="7d420-108">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="7d420-109">选择您的网站, 它位于**Lync Server**节点正下方。</span><span class="sxs-lookup"><span data-stu-id="7d420-109">Select your site, which is directly below the **Lync Server** node.</span></span>

3.  <span data-ttu-id="7d420-110">在 "**操作**" 菜单上, 单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="7d420-110">On the **Actions** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="7d420-111">在左窗格中, 选择 "**联盟路由**"。</span><span class="sxs-lookup"><span data-stu-id="7d420-111">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="7d420-112">在 "**站点联合路由分配**" 下, 选择 "**启用 SIP 联盟**", 然后选择 lync Server 2010 控制器或 Lync server 2010 Edge 服务器 (如果未列出 Director)。</span><span class="sxs-lookup"><span data-stu-id="7d420-112">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Lync Server 2010 Director, or the Lync Server 2010 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="7d420-113">!["编辑属性"、"联盟路由" 页面](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "\"编辑属性\"、\"联盟路由\" 页面")</span><span class="sxs-lookup"><span data-stu-id="7d420-113">![Edit Properties, Federation route page](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Edit Properties, Federation route page")</span></span>  

6.  <span data-ttu-id="7d420-114">单击 **"确定"** 以关闭 "**编辑属性**" 页面。</span><span class="sxs-lookup"><span data-stu-id="7d420-114">Click **OK** to close the **Edit Properties** page.</span></span>

7.  <span data-ttu-id="7d420-115">在拓扑生成器中, 在 Lync Server 2013 节点下, 导航到**标准版服务器**或**企业版前端池**, 右键单击该池, 然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="7d420-115">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

8.  <span data-ttu-id="7d420-116">在 "**关联**" 下, 选中 "**关联边缘池" (对于媒体组件)** 旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="7d420-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

9.  <span data-ttu-id="7d420-117">从列表中, 选择旧式边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="7d420-117">From the list, select the legacy Edge Server.</span></span>
    
    <span data-ttu-id="7d420-118">!["编辑属性" 对话框, 选择旧版边缘](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "\"编辑属性\" 对话框, 选择旧版边缘")</span><span class="sxs-lookup"><span data-stu-id="7d420-118">![Edit Properties dialog, selecting the legacy Edge](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Edit Properties dialog, selecting the legacy Edge")</span></span>  

10. <span data-ttu-id="7d420-119">单击 **"确定"** 以关闭 "**编辑属性**" 页面。</span><span class="sxs-lookup"><span data-stu-id="7d420-119">Click **OK** to close the **Edit Properties** page.</span></span>

11. <span data-ttu-id="7d420-120">在**拓扑生成器**中, 选择最上面的节点 " **Lync 服务器**"。</span><span class="sxs-lookup"><span data-stu-id="7d420-120">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

12. <span data-ttu-id="7d420-121">从 "**操作**" 菜单中, 单击 "**发布拓扑**", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="7d420-121">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

13. <span data-ttu-id="7d420-122">**发布向导**完成后, 单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="7d420-122">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

