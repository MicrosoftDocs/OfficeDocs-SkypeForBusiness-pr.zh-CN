---
title: Lync Server 2013：将 Lync Server 2013 Standard Edition 部署到现有 Lync Server 2013 Enterprise 中
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48183297
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c505a692590662adf03e48d695b3c1ff089d8d7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a><span data-ttu-id="7a974-102">将 Lync Server 2013 Standard Edition 部署到现有 Lync Server 2013 Enterprise 中</span><span class="sxs-lookup"><span data-stu-id="7a974-102">Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a974-103">_**主题上次修改时间:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7a974-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7a974-104">将标准版服务器部署到现有企业版部署类似于部署其他服务器角色。</span><span class="sxs-lookup"><span data-stu-id="7a974-104">Deploying a Standard Edition server into an existing Enterprise Edition deployment is similar to deploying additional server roles.</span></span> <span data-ttu-id="7a974-105">标准版服务器可能会部署到另一个网站, 允许该网站中的用户驻留在标准版服务器上, 而不是在广域网 (WAN) 上的前端池。</span><span class="sxs-lookup"><span data-stu-id="7a974-105">A Standard Edition server might be deployed to another site, allowing for users in that site to be homed on the Standard Edition server rather than the Front End pool across a wide area network (WAN).</span></span> <span data-ttu-id="7a974-106">在[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)文档的其他部分中已定义了在该网站中安装新网站和服务器的过程。</span><span class="sxs-lookup"><span data-stu-id="7a974-106">The procedures for installing the new site and servers in that site are already defined in other sections of the [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) documentation.</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="7a974-107">**定义新网站**</span><span class="sxs-lookup"><span data-stu-id="7a974-107">**To define a new site**</span></span>

1.  <span data-ttu-id="7a974-108">启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="7a974-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="7a974-109">在控制台树中, 右键单击 " **Lync Server 2013**", 然后单击 "**新建中心网站**"。</span><span class="sxs-lookup"><span data-stu-id="7a974-109">In the console tree, right-click **Lync Server 2013**, and then click **New Central Site**.</span></span>

3.  <span data-ttu-id="7a974-110">在 "**标识网站**" 页面上, 为网站提供一个名称, 并选择 "输入说明"。</span><span class="sxs-lookup"><span data-stu-id="7a974-110">On the **Identify the site** page, give a name to the site and optionally enter a description.</span></span>

4.  <span data-ttu-id="7a974-111">按照定义网站拓扑的其余部分中的过程操作。</span><span class="sxs-lookup"><span data-stu-id="7a974-111">Follow the procedures for defining the rest of the site topology.</span></span> <span data-ttu-id="7a974-112">有关详细信息, 请参阅[在 Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="7a974-112">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

5.  <span data-ttu-id="7a974-113">发布更新后的拓扑。</span><span class="sxs-lookup"><span data-stu-id="7a974-113">Publish the updated topology.</span></span> <span data-ttu-id="7a974-114">有关详细信息, 请参阅[在 Lync Server 2013 中发布拓扑](lync-server-2013-publish-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="7a974-114">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

6.  <span data-ttu-id="7a974-115">设置和安装标准版服务器。</span><span class="sxs-lookup"><span data-stu-id="7a974-115">Set up and install a Standard Edition server.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="7a974-116">如果你已使用标准版服务器部署了环境, 则你将通过使用 "<STRONG>准备第一个标准版服务器</STRONG>" 链接从 Lync Server 部署向导开始安装过程, 方法是将初始数据库文件安装到新标准版服务器。</span><span class="sxs-lookup"><span data-stu-id="7a974-116">If you have deployed an environment with only a Standard Edition server, you would have begun the setup process from the Lync Server Deployment Wizard by using the <STRONG>Prepare first Standard Edition server</STRONG> link to install the initial database files to the new Standard Edition server.</span></span> <span data-ttu-id="7a974-117"><STRONG></STRONG>在将标准版服务器安装到现有 Lync server 2013 部署中时, 请不要执行此过程。</span><span class="sxs-lookup"><span data-stu-id="7a974-117"><STRONG>Do not</STRONG> follow that process when installing a Standard Edition server into an existing Lync Server 2013 deployment.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

