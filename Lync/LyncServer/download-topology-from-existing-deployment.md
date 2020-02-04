---
title: 从现有部署下载拓扑
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29a8bd95af99b6b79b91f84231120c6981eeedb7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="download-topology-from-existing-deployment"></a><span data-ttu-id="368cb-102">从现有部署下载拓扑</span><span class="sxs-lookup"><span data-stu-id="368cb-102">Download topology from existing deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="368cb-103">_**主题上次修改时间：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="368cb-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="368cb-104">创建 Lync Server 2013 池时，将使用与 Lync Server 2010 相关联的中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="368cb-104">When creating a Lync Server 2013 pool, you will use the Central Management Store that is associated with Lync Server 2010.</span></span> <span data-ttu-id="368cb-105">在首次使用时启动拓扑生成器和后续编辑会话时，系统会提示你输入希望拓扑生成器加载当前配置文档的位置。</span><span class="sxs-lookup"><span data-stu-id="368cb-105">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="368cb-106">因为你已定义了 Lync Server 2010 拓扑，并且已建立中央管理存储，因此你应该选择从现有部署下载拓扑。</span><span class="sxs-lookup"><span data-stu-id="368cb-106">Because you already have a Lync Server 2010 topology defined and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="368cb-107">拓扑生成器将读取数据库并检索当前定义。</span><span class="sxs-lookup"><span data-stu-id="368cb-107">Topology Builder will read the database and retrieve the current definition.</span></span>

<span data-ttu-id="368cb-108">**从现有部署下载拓扑**</span><span class="sxs-lookup"><span data-stu-id="368cb-108">**To download a topology from an existing deployment**</span></span>

1.  <span data-ttu-id="368cb-109">打开**Lync Server 部署向导**。</span><span class="sxs-lookup"><span data-stu-id="368cb-109">Open the **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="368cb-110">在 " **Lync Server 2013-部署向导**" 页面上，单击 "**安装管理工具**"。</span><span class="sxs-lookup"><span data-stu-id="368cb-110">From the **Lync Server 2013 – Deployment Wizard** page, click **Install Administrative Tools**.</span></span>

3.  <span data-ttu-id="368cb-111">启动拓扑生成器：单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft Lync server 2013** "，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="368cb-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013** , and then click **Lync Server Topology Builder**.</span></span>

4.  <span data-ttu-id="368cb-112">**从现有部署中选择 "下载拓扑**"。</span><span class="sxs-lookup"><span data-stu-id="368cb-112">Select **Download Topology from existing deployment**.</span></span>
    
    <span data-ttu-id="368cb-113">![部署向导拓扑生成器设置](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "部署向导拓扑生成器设置")</span><span class="sxs-lookup"><span data-stu-id="368cb-113">![Deployment Wizard Topology Builder settings](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Deployment Wizard Topology Builder settings")</span></span>

5.  <span data-ttu-id="368cb-114">选择文件名，并使用默认的 tbxml 文件类型保存拓扑。</span><span class="sxs-lookup"><span data-stu-id="368cb-114">Choose a file name and save the topology with the default .tbxml file type.</span></span>

6.  <span data-ttu-id="368cb-115">如图所示展开 Lync 服务器节点，以显示部署中的各种服务器角色。</span><span class="sxs-lookup"><span data-stu-id="368cb-115">Expand the Lync Server node, as shown, to reveal the various server roles in the deployment.</span></span>
    
    <span data-ttu-id="368cb-116">![拓扑生成器服务器角色常规属性](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "拓扑生成器服务器角色常规属性")</span><span class="sxs-lookup"><span data-stu-id="368cb-116">![Topology Builder server role general properties](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Topology Builder server role general properties")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

