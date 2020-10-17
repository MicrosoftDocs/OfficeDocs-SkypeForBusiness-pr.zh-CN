---
title: 从现有部署下载拓扑
description: 从现有部署下载拓扑。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c22d746f8faf3fdf14a44e751eeb3c88bf3eef4c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551178"
---
# <a name="download-topology-from-existing-deployment"></a><span data-ttu-id="d51aa-103">从现有部署下载拓扑</span><span class="sxs-lookup"><span data-stu-id="d51aa-103">Download topology from existing deployment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d51aa-104">_**上次修改的主题：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="d51aa-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="d51aa-105">创建 Lync Server 2013 池时，将使用与 Lync Server 2010 关联的中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="d51aa-105">When creating a Lync Server 2013 pool, you will use the Central Management Store that is associated with Lync Server 2010.</span></span> <span data-ttu-id="d51aa-106">因第一次使用而启动拓扑生成器并随后编辑会话时，系统会提示您要使拓扑生成器加载当前配置文档的位置。</span><span class="sxs-lookup"><span data-stu-id="d51aa-106">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="d51aa-107">由于已定义了 Lync Server 2010 拓扑，并且已建立了中央管理存储，因此应选择从现有部署下载拓扑。</span><span class="sxs-lookup"><span data-stu-id="d51aa-107">Because you already have a Lync Server 2010 topology defined and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="d51aa-108">拓扑生成器将读取数据库并检索当前的定义。</span><span class="sxs-lookup"><span data-stu-id="d51aa-108">Topology Builder will read the database and retrieve the current definition.</span></span>

<span data-ttu-id="d51aa-109">**从现有部署下载拓扑**</span><span class="sxs-lookup"><span data-stu-id="d51aa-109">**To download a topology from an existing deployment**</span></span>

1.  <span data-ttu-id="d51aa-110">打开“Lync Server 部署向导”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d51aa-110">Open the **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="d51aa-111">从“Lync Server 2013 – 部署向导”\*\*\*\* 页面，单击“安装管理工具”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d51aa-111">From the **Lync Server 2013 – Deployment Wizard** page, click **Install Administrative Tools**.</span></span>

3.  <span data-ttu-id="d51aa-112">启动拓扑生成器：依次单击 " **开始**"、" **所有程序**"、" **Microsoft Lync server 2013** "，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="d51aa-112">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013** , and then click **Lync Server Topology Builder**.</span></span>

4.  <span data-ttu-id="d51aa-113">选择“从现有部署下载拓扑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d51aa-113">Select **Download Topology from existing deployment**.</span></span>
    
    <span data-ttu-id="d51aa-114">![部署向导拓扑生成器设置](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "部署向导拓扑生成器设置")</span><span class="sxs-lookup"><span data-stu-id="d51aa-114">![Deployment Wizard Topology Builder settings](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Deployment Wizard Topology Builder settings")</span></span>

5.  <span data-ttu-id="d51aa-115">使用默认的 .tbxml 文件类型选择文件名并保存该拓扑。</span><span class="sxs-lookup"><span data-stu-id="d51aa-115">Choose a file name and save the topology with the default .tbxml file type.</span></span>

6.  <span data-ttu-id="d51aa-116">展开 Lync Server 节点（如图所示），在部署中查看各种服务器角色。</span><span class="sxs-lookup"><span data-stu-id="d51aa-116">Expand the Lync Server node, as shown, to reveal the various server roles in the deployment.</span></span>
    
    <span data-ttu-id="d51aa-117">![拓扑生成器服务器角色常规属性](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "拓扑生成器服务器角色常规属性")</span><span class="sxs-lookup"><span data-stu-id="d51aa-117">![Topology Builder server role general properties](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Topology Builder server role general properties")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

