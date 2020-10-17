---
title: 将试点池连接到旧 Edge Server
description: 将试点池连接到旧版边缘服务器。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ede2256efabf561be6b3f99543437087cb5c3890
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550268"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="07227-103">将试点池连接到旧 Edge Server</span><span class="sxs-lookup"><span data-stu-id="07227-103">Connect pilot pool to legacy Edge Servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07227-104">_**上次修改的主题：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="07227-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="07227-105">部署 Lync Server 2013 后，需要为您的网站配置联盟路由。</span><span class="sxs-lookup"><span data-stu-id="07227-105">After deploying Lync Server 2013, you need to configure a federation route for your site.</span></span> <span data-ttu-id="07227-106">为了使用 Lync Server 2010 正在使用的联盟路由，必须将 Lync Server 2013 配置为使用此路由。</span><span class="sxs-lookup"><span data-stu-id="07227-106">In order to use the federated route that is being used by Lync Server 2010, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="07227-107">若要使 Lync Server 2013 网站能够使用 Lync Server 2010 部署的控制器和边缘服务器，请使用拓扑生成器来关联旧版边缘池。</span><span class="sxs-lookup"><span data-stu-id="07227-107">To enable the Lync Server 2013 site to use the Director and Edge Server of the Lync Server 2010 deployment, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="07227-108">使用拓扑生成器关联旧的边缘池</span><span class="sxs-lookup"><span data-stu-id="07227-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="07227-109">打开**拓扑生成器**。</span><span class="sxs-lookup"><span data-stu-id="07227-109">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="07227-110">选择位于 **Lync Server** 节点正下方的站点。</span><span class="sxs-lookup"><span data-stu-id="07227-110">Select your site, which is directly below the **Lync Server** node.</span></span>

3.  <span data-ttu-id="07227-111">在“操作”\*\*\*\* 菜单上，单击“编辑属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="07227-111">On the **Actions** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="07227-112">在左侧窗格中，选择“联盟路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="07227-112">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="07227-113">在 " **站点联合路由分配**" 下，选择 " **启用 SIP 联盟**"，然后选择 lync server 2010 控制器，如果未列出控制器，则选择 Lync server 2010 边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="07227-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Lync Server 2010 Director, or the Lync Server 2010 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="07227-114">!["编辑属性"、"联盟路由" 页面](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg ""编辑属性"、"联盟路由" 页面")</span><span class="sxs-lookup"><span data-stu-id="07227-114">![Edit Properties, Federation route page](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Edit Properties, Federation route page")</span></span>  

6.  <span data-ttu-id="07227-115">单击“确定”\*\*\*\* 关闭“编辑属性”\*\*\*\* 页。</span><span class="sxs-lookup"><span data-stu-id="07227-115">Click **OK** to close the **Edit Properties** page.</span></span>

7.  <span data-ttu-id="07227-116">在拓扑生成器中，在 "Lync Server 2013" 节点下，导航到 **Standard edition server** 或 **Enterprise Edition 前端池**，右键单击该池，然后单击 " **编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="07227-116">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

8.  <span data-ttu-id="07227-117">在“关联”\*\*\*\* 下，选中“关联边缘池(用于媒体组件)”\*\*\*\* 旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="07227-117">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

9.  <span data-ttu-id="07227-118">从列表中选择旧的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="07227-118">From the list, select the legacy Edge Server.</span></span>
    
    <span data-ttu-id="07227-119">!["编辑属性" 对话框，选择旧版边缘](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg ""编辑属性" 对话框，选择旧版边缘")</span><span class="sxs-lookup"><span data-stu-id="07227-119">![Edit Properties dialog, selecting the legacy Edge](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Edit Properties dialog, selecting the legacy Edge")</span></span>  

10. <span data-ttu-id="07227-120">单击“确定”\*\*\*\* 关闭“编辑属性”\*\*\*\* 页。</span><span class="sxs-lookup"><span data-stu-id="07227-120">Click **OK** to close the **Edit Properties** page.</span></span>

11. <span data-ttu-id="07227-121">在“拓扑生成器”\*\*\*\* 中，选择最顶层节点 **Lync Server**。</span><span class="sxs-lookup"><span data-stu-id="07227-121">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

12. <span data-ttu-id="07227-122">从“操作”\*\*\*\* 菜单中，单击“发布拓扑”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="07227-122">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

13. <span data-ttu-id="07227-123">“发布向导”\*\*\*\* 完成时，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="07227-123">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

