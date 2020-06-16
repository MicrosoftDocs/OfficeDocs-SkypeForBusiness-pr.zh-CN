---
title: 使用拓扑生成器合并向导进行合并
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4760dcd8810d12b112c3bb042e0f28a039683a08
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a><span data-ttu-id="5d724-102">使用拓扑生成器合并向导进行合并</span><span class="sxs-lookup"><span data-stu-id="5d724-102">Merge using Topology Builder Merge wizard</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d724-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5d724-103">_**Topic Last Modified:** 2012-10-02_</span></span>

1.  <span data-ttu-id="5d724-104">使用拓扑生成器下载现有部署。</span><span class="sxs-lookup"><span data-stu-id="5d724-104">Download the existing deployment using Topology Builder.</span></span>

2.  <span data-ttu-id="5d724-105">在“操作”\*\*\*\* 菜单中，选择“合并 Office Communications Server 2007 R2”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5d724-105">From the **Action** menu, select **Merge Office Communications Server 2007 R2**.</span></span>

3.  <span data-ttu-id="5d724-106">单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5d724-106">Click **Next**.</span></span>

4.  <span data-ttu-id="5d724-107">在“指定边缘设置”\*\*\*\* 中，单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5d724-107">In **Specify Edge Setup**, click **Add**.</span></span>
    
    <span data-ttu-id="5d724-108">![合并拓扑向导中，指定 "边缘设置" 页](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "合并拓扑向导中，指定 "边缘设置" 页")</span><span class="sxs-lookup"><span data-stu-id="5d724-108">![Merge Topology Wizard, Specify Edge Setup page](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="5d724-109">In **Specify Edge Type**, enter the type of Edge Server configuration, and then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="5d724-109">In **Specify Edge Type**, enter the type of Edge Server configuration, and then click **Next**.</span></span> <span data-ttu-id="5d724-110">This example uses the **Single Edge Server** option.</span><span class="sxs-lookup"><span data-stu-id="5d724-110">This example uses the **Single Edge Server** option.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5d724-111"><STRONG>Expanded Edge deployment</STRONG> is not a supported configuration.</span><span class="sxs-lookup"><span data-stu-id="5d724-111"><STRONG>Expanded Edge deployment</STRONG> is not a supported configuration.</span></span> <span data-ttu-id="5d724-112">An <STRONG>Expanded Edge Server</STRONG> must first be converted to a <STRONG>Single Edge Server</STRONG> or a <STRONG>Load-balanced consolidated Edge</STRONG> Server.</span><span class="sxs-lookup"><span data-stu-id="5d724-112">An <STRONG>Expanded Edge Server</STRONG> must first be converted to a <STRONG>Single Edge Server</STRONG> or a <STRONG>Load-balanced consolidated Edge</STRONG> Server.</span></span>

    
    </div>

6.  <span data-ttu-id="5d724-113">在 "**指定内部边缘设置**" 中，根据需要为边缘池的内部 FQDN 和端口输入相关信息，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5d724-113">In **Specify Internal Edge Settings** , enter the relevant information for your Edge pool’s internal FQDN and ports as needed, and then click **Next**.</span></span>
    
    <span data-ttu-id="5d724-114">!["指定内部边缘设置" 对话框](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg ""指定内部边缘设置" 对话框")</span><span class="sxs-lookup"><span data-stu-id="5d724-114">![Specify Internal Edge Settings dialog](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Specify Internal Edge Settings dialog")</span></span>  

7.  <span data-ttu-id="5d724-115">在“指定外部边缘”\*\*\*\* 中，输入边缘服务器的 Web 会议 FQDN 信息。</span><span class="sxs-lookup"><span data-stu-id="5d724-115">In **Specify External Edge**, enter the web conferencing FQDN information for your Edge Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5d724-116">Before you click <STRONG>Next</STRONG>, do the next step in this procedure.</span><span class="sxs-lookup"><span data-stu-id="5d724-116">Before you click <STRONG>Next</STRONG>, do the next step in this procedure.</span></span> <span data-ttu-id="5d724-117">It is very important that you do not miss this step.</span><span class="sxs-lookup"><span data-stu-id="5d724-117">It is very important that you do not miss this step.</span></span>

    
    </div>

8.  <span data-ttu-id="5d724-118">如果计划将旧版 Office 通信服务器 2007 R2 边缘服务器用于联盟，请选中 "**此边缘池用于联盟和公用 IM 连接**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="5d724-118">Check the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use the legacy Office Communications Server 2007 R2 Edge Server for federation.</span></span> <span data-ttu-id="5d724-119">如果已部署多台边缘服务器，则将只为其中一台边缘服务器启用联盟。</span><span class="sxs-lookup"><span data-stu-id="5d724-119">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="5d724-120">如果未选中此复选框，但之后决定要启用联盟，则必须运行拓扑生成器合并向导，并再次发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="5d724-120">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard and publish your topology again.</span></span>
    
    <span data-ttu-id="5d724-121">!["边缘服务器" 对话框中，指定外部边缘页面](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg ""边缘服务器" 对话框中，指定外部边缘页面")</span><span class="sxs-lookup"><span data-stu-id="5d724-121">![Edge Server dialog, Specify External Edge page](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Edge Server dialog, Specify External Edge page")</span></span>  

9.  <span data-ttu-id="5d724-122">在“指定下一跃点”\*\*\*\* 中，输入所在环境中下一跃点位置的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="5d724-122">In **Specify Next Hop**, enter the fully qualified domain name (FQDN) of the next hop location in your environment.</span></span> <span data-ttu-id="5d724-123">单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5d724-123">Click **Finish**.</span></span>
    
    <span data-ttu-id="5d724-124">!["边缘服务器" 对话框，"指定下一跃点" 页](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg ""边缘服务器" 对话框，"指定下一跃点" 页")</span><span class="sxs-lookup"><span data-stu-id="5d724-124">![Edge Server dialog, Specify Next Hop page](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Edge Server dialog, Specify Next Hop page")</span></span>  

10. <span data-ttu-id="5d724-125">在 "**指定边缘设置**" 中，如果已添加所有 Office 通信服务器 2007 R2 边缘服务器，请单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5d724-125">In **Specify Edge Setup**, if all your Office Communications Server 2007 R2 Edge Servers have been added, click **Next**.</span></span> <span data-ttu-id="5d724-126">如果要添加更多的 Office 通信服务器 2007 R2 边缘服务器，请从步骤4开始，重复此过程。</span><span class="sxs-lookup"><span data-stu-id="5d724-126">If you have more Office Communications Server 2007 R2 Edge Servers to add, repeat this procedure starting at step 4.</span></span>

11. <span data-ttu-id="5d724-127">在 "**指定内部 SIP 端口**" 中，选择默认设置（即，如果您未修改默认 SIP 端口）。</span><span class="sxs-lookup"><span data-stu-id="5d724-127">In **Specify Internal SIP port** , select the default setting (that is, if you did not modify the default SIP port).</span></span> <span data-ttu-id="5d724-128">如果不使用默认端口 5061，则根据需要进行更改，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5d724-128">Change as appropriate if you are not using a default port of 5061, and then click **Next**.</span></span>

12. <span data-ttu-id="5d724-129">在“摘要”\*\*\*\* 中，单击“下一步”\*\*\*\* 开始合并拓扑。</span><span class="sxs-lookup"><span data-stu-id="5d724-129">In **Summary**, click **Next** to begin merging the topologies.</span></span>

13. <span data-ttu-id="5d724-130">向导页用于验证拓扑合并是否成功。</span><span class="sxs-lookup"><span data-stu-id="5d724-130">The wizard page verifies that the merging of the topologies was successful.</span></span>

14. <span data-ttu-id="5d724-131">在“状态”\*\*\*\* 列中，确认值为“成功”\*\*\*\*，然后单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5d724-131">In the **Status** column, verify that the value is **Success**, and then click **Finish**.</span></span>

15. <span data-ttu-id="5d724-132">在拓扑生成器的左窗格中，您现在应该会看到**BackCompatSite**，这表示您的 Office 通信服务器 2007 R2 环境已与 Lync Server 2013 合并。</span><span class="sxs-lookup"><span data-stu-id="5d724-132">In the left pane of Topology Builder, you should now see the **BackCompatSite**, which indicates that your Office Communications Server 2007 R2 environment has been merged with Lync Server 2013.</span></span>
    
    <span data-ttu-id="5d724-133">![显示合并拓扑的拓扑生成器](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "显示合并拓扑的拓扑生成器")</span><span class="sxs-lookup"><span data-stu-id="5d724-133">![Topology Builder showing a merged topology](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder showing a merged topology")</span></span>  

16. <span data-ttu-id="5d724-134">从“操作”\*\*\*\* 菜单中，单击“发布拓扑”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5d724-134">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

17. <span data-ttu-id="5d724-135">“发布向导”\*\*\*\* 完成时，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5d724-135">When the **Publishing wizard** completes, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5d724-136">请务必填写下一个主题 "<A href="import-policies-and-settings.md">导入策略和设置</A>"，以确保将旧策略设置导入到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="5d724-136">It’s important that you complete the next topic, <A href="import-policies-and-settings.md">Import policies and settings</A>, to ensure that the legacy policy settings are imported into Lync Server 2013.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

