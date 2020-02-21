---
title: 将试点池连接到旧版边缘服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e48d2450d468ae6a28faef4c1fcacf577262c42f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="01824-102">将试点池连接到旧版边缘服务器</span><span class="sxs-lookup"><span data-stu-id="01824-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01824-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="01824-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="01824-104">部署 Lync Server 2013 后，未配置此网站的联合身份验证路由。</span><span class="sxs-lookup"><span data-stu-id="01824-104">After deploying Lync Server 2013, a federation route for this site is not configured.</span></span> <span data-ttu-id="01824-105">为了使用 Office 通信服务器 2007 R2 使用的联盟路由，Lync Server 2013 必须配置为使用此路由。</span><span class="sxs-lookup"><span data-stu-id="01824-105">In order to use the federated route that is being used by Office Communications Server 2007 R2, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="01824-106">若要使 Lync Server 2013 网站能够使用 BackCompatSite 的控制器和边缘服务器，请使用拓扑生成器来关联旧版边缘池。</span><span class="sxs-lookup"><span data-stu-id="01824-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the BackCompatSite, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="01824-107">使用拓扑生成器关联旧式边缘池</span><span class="sxs-lookup"><span data-stu-id="01824-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="01824-108">在拓扑生成器中打开试点池拓扑。</span><span class="sxs-lookup"><span data-stu-id="01824-108">Open the pilot pool topology in Topology Builder.</span></span>

2.  <span data-ttu-id="01824-109">选择你的 Lync Server 2013 网站。</span><span class="sxs-lookup"><span data-stu-id="01824-109">Select your Lync Server 2013 site.</span></span>

3.  <span data-ttu-id="01824-110">在“操作”\*\*\*\* 菜单上，单击“编辑属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="01824-110">On the **Action** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="01824-111">在 "**站点联合路由分配**" 下，选择 "**启用 SIP 联盟**"，然后选择 Office 通信服务器 2007 R2 控制器或 Office 通信服务器 2007 r2 边缘服务器（如果未列出控制器）。</span><span class="sxs-lookup"><span data-stu-id="01824-111">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Office Communications Server 2007 R2 Director, or the Office Communications Server 2007 R2 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="01824-112">!["编辑属性" 对话框（"联合路由" 页）](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg ""编辑属性" 对话框（"联合路由" 页）")</span><span class="sxs-lookup"><span data-stu-id="01824-112">![Edit Properties dialog, Federation route page](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>  

5.  <span data-ttu-id="01824-113">单击“确定”\*\*\*\* 关闭“编辑属性”\*\*\*\* 页。</span><span class="sxs-lookup"><span data-stu-id="01824-113">Click **OK** to close the **Edit Properties** page.</span></span>

6.  <span data-ttu-id="01824-114">在拓扑生成器中，在 "Lync Server 2013" 节点下，导航到**Standard edition server**或**Enterprise Edition 前端池**，右键单击该池，然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="01824-114">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="01824-115">在“关联”\*\*\*\* 下，选中“关联边缘池(用于媒体组件)”\*\*\*\* 旁的复选框。</span><span class="sxs-lookup"><span data-stu-id="01824-115">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

8.  <span data-ttu-id="01824-116">从列表中选择用于 BackCompatSite 的边缘服务器接口。</span><span class="sxs-lookup"><span data-stu-id="01824-116">From the list, select the Edge Server interface for the BackCompatSite.</span></span>
    
    <span data-ttu-id="01824-117">!["编辑属性" 对话框（"常规" 页）](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg ""编辑属性" 对话框（"常规" 页）")</span><span class="sxs-lookup"><span data-stu-id="01824-117">![Edit Properties dialog, General page](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Edit Properties dialog, General page")</span></span>  

9.  <span data-ttu-id="01824-118">单击“确定”\*\*\*\* 关闭“编辑属性”\*\*\*\* 页。</span><span class="sxs-lookup"><span data-stu-id="01824-118">Click **OK** to close the **Edit Properties** page.</span></span>

10. <span data-ttu-id="01824-119">在“拓扑生成器”\*\*\*\* 中，选择最顶层节点 **Lync Server**。</span><span class="sxs-lookup"><span data-stu-id="01824-119">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

11. <span data-ttu-id="01824-120">从“操作”\*\*\*\* 菜单中，单击“发布拓扑”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="01824-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

12. <span data-ttu-id="01824-121">“发布向导”\*\*\*\* 完成时，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="01824-121">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

