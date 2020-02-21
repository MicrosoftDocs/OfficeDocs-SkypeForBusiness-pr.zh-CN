---
title: 删除 BackCompatSite
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d41d333e834dba34da2a1a04854571d721e94e38
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a><span data-ttu-id="d6f1f-102">删除 BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="d6f1f-102">Remove BackCompatSite</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6f1f-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d6f1f-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d6f1f-104">停用所有池并卸载所有边缘服务器之后，请运行拓扑生成器合并向导以删除 **BackCompatSite**。</span><span class="sxs-lookup"><span data-stu-id="d6f1f-104">After all pools are deactivated and all Edge Servers have been uninstalled, run the Topology Builder Merge wizard to remove the **BackCompatSite**.</span></span>

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a><span data-ttu-id="d6f1f-105">从拓扑生成器中删除 BackCompat 站点</span><span class="sxs-lookup"><span data-stu-id="d6f1f-105">To remove BackCompat site from Topology Builder</span></span>

1.  <span data-ttu-id="d6f1f-106">从拓扑生成器打开一个现有部署。</span><span class="sxs-lookup"><span data-stu-id="d6f1f-106">Open an existing deployment from Topology Builder.</span></span>

2.  <span data-ttu-id="d6f1f-107">在“操作”\*\*\*\* 菜单中，单击“合并 2007 R2 拓扑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d6f1f-107">In the **Action** menu, click **Merge 2007 R2 Topology**.</span></span>

3.  <span data-ttu-id="d6f1f-108">单击“下一步”\*\*\*\* 继续。</span><span class="sxs-lookup"><span data-stu-id="d6f1f-108">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="d6f1f-p101">在“指定旧边缘”\*\*\*\* 页上，确保边缘服务器列表为空。如果该列表不为空，请使用“删除”\*\*\*\* 按钮删除所有旧边缘服务器，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d6f1f-p101">On the **Specify Legacy Edge** page, ensure that list of Edge Servers is empty. If the list is not empty, use the **Remove** button to remove all the legacy Edge Servers, and then click **Next**.</span></span>
    
    <span data-ttu-id="d6f1f-111">![合并拓扑向导中，指定 "边缘设置" 页](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "合并拓扑向导中，指定 "边缘设置" 页")</span><span class="sxs-lookup"><span data-stu-id="d6f1f-111">![Merge Topology Wizard, Specify Edge Setup page](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="d6f1f-112">在“指定内部 SIP 端口”\*\*\*\* 设置页上，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d6f1f-112">On the **Specify Internal SIP port setting** page, click **Next**.</span></span>

6.  <span data-ttu-id="d6f1f-113">在 "**摘要**" 页上，单击 "**下一步**" 开始合并拓扑以删除旧版网站。</span><span class="sxs-lookup"><span data-stu-id="d6f1f-113">On the **Summary** page, click **Next** to begin merging the topologies to remove the legacy site.</span></span>

7.  <span data-ttu-id="d6f1f-114">在“状态”\*\*\*\* 列中，确认值为“成功”\*\*\*\*，然后单击“完成”\*\*\*\* 以关闭向导。</span><span class="sxs-lookup"><span data-stu-id="d6f1f-114">In the **Status** column, verify that the value is **Success** and then click **Finish** to close the wizard.</span></span>

8.  <span data-ttu-id="d6f1f-115">在拓扑生成器的左窗格中，展开 BackCompatSite，确保未列出任何服务器。</span><span class="sxs-lookup"><span data-stu-id="d6f1f-115">In the left pane of Topology Builder, expand the BackCompatSite and ensure no servers are listed.</span></span>

9.  <span data-ttu-id="d6f1f-116">右键单击“BackCompatSite”\*\*\*\*，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d6f1f-116">Right-click the **BackCompatSite**, and then click **Delete**.</span></span>

10. <span data-ttu-id="d6f1f-117">在“拓扑生成器”\*\*\*\* 中，选择最顶层节点“Lync Server”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d6f1f-117">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

11. <span data-ttu-id="d6f1f-118">从“操作”\*\*\*\* 菜单中，选择“发布拓扑”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d6f1f-118">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

12. <span data-ttu-id="d6f1f-119">“发布向导”\*\*\*\* 完成时，单击“完成”\*\*\*\* 关闭向导。</span><span class="sxs-lookup"><span data-stu-id="d6f1f-119">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

