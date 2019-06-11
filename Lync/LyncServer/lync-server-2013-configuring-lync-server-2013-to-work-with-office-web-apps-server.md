---
title: 将 Lync Server 2013 配置为使用 Office Web Apps 服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ba6926af243b15449c5b8baa4b29706a2ec8ade
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a><span data-ttu-id="2fc7f-102">将 Lync Server 2013 配置为使用 Office Web Apps 服务器</span><span class="sxs-lookup"><span data-stu-id="2fc7f-102">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2fc7f-103">_**主题上次修改时间:** 2013-04-22_</span><span class="sxs-lookup"><span data-stu-id="2fc7f-103">_**Topic Last Modified:** 2013-04-22_</span></span>

<span data-ttu-id="2fc7f-104">必须先部署和配置 Office Web Apps 服务器, 然后才能将 Lync Server 2013 配置为使用 Office Web Apps 服务器。</span><span class="sxs-lookup"><span data-stu-id="2fc7f-104">Before you can configure Lync Server 2013 to use Office Web Apps Server, Office Web Apps Server must be deployed and configured.</span></span> <span data-ttu-id="2fc7f-105">有关如何安装和配置单个 Office Web Apps 服务器的详细信息, 请参阅文档**指南**, 有关如何安装和配置 office Web Apps 服务器场的详细信息, 请参阅 office web apps可用性.</span><span class="sxs-lookup"><span data-stu-id="2fc7f-105">See the document **Guide to Deploying Office Web Apps Server and Office Web Apps** for detail information on how to install and configure a single Office Web Apps Server, or for information on how to install and configure an Office Web Apps Server Farm for high availability.</span></span>

<span data-ttu-id="2fc7f-106">成功安装 Office Web Apps 服务器并正确配置 Web 场后, 必须配置 Lync 服务器才能与新服务器通信;可通过将 Office Web Apps 服务器发现 URL 添加到 Lync Server 拓扑来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="2fc7f-106">After Office Web Apps Server has been successfully installed and your Web farm correctly configured, you must then configure Lync Server to communicate with the new server; this is done by adding the Office Web Apps Server discovery URL to your Lync Server topology.</span></span> <span data-ttu-id="2fc7f-107">若要向拓扑中添加 Office Web Apps 服务器，请完成下列步骤：</span><span class="sxs-lookup"><span data-stu-id="2fc7f-107">To add Office Web Apps Server to your topology, complete the following steps:</span></span>

1.  <span data-ttu-id="2fc7f-108">单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="2fc7f-108">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="2fc7f-109">在“**拓扑生成器**”对话框中，选择“**从现有部署下载拓扑**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="2fc7f-109">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>

3.  <span data-ttu-id="2fc7f-p103">在“**将拓扑另存为**”对话框的“**文件名**”框中为拓扑文档键入一个名称（例如“**PreWebAppsServerTopology**”），然后单击“**保存**”。如果之后你的新拓扑遇到问题，则可检索和重新发布此拓扑。</span><span class="sxs-lookup"><span data-stu-id="2fc7f-p103">In the **Save Topology As** dialog box, type a name for your topology document (for example, **PreWebAppsServerTopology**) in the **File name** box and then click **Save**. This topology can later be retrieved and republished if you encounter problems with your new topology.</span></span>

4.  <span data-ttu-id="2fc7f-112">在拓扑生成器中, 展开 " **Lync Server 2013**", 展开您的网站的名称, 展开 "**企业版前端池**", 右键单击其中一个池的名称, 然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="2fc7f-112">In Topology Builder, expand **Lync Server 2013**, expand the name of your site, expand **Enterprise Edition Front End pools**, right-click the name of one of your pools, and then click **Edit Properties**.</span></span>

5.  <span data-ttu-id="2fc7f-113">在“**编辑属性**”对话框的“**常规**”选项卡上，查找标题“**关联 Office Web Apps 服务器**”，然后单击“**新建**”（或从下拉列表中选择现有 Office Web Apps 服务器）。</span><span class="sxs-lookup"><span data-stu-id="2fc7f-113">In the **Edit Properties** dialog box, on the **General** tab, find the heading **Associate Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

6.  <span data-ttu-id="2fc7f-114">在“**定义新的 Office Web Apps 服务器**”对话框的“**Office Web Apps 服务器 FQDN**”框中，键入你的 Office Web Apps 服务器计算机的完全限定域名 (FQDN)；执行此操作时，你的 Office Web Apps 服务器搜索 URL 应自动输入到“**Office Web Apps 服务器搜索 URL**”框中。</span><span class="sxs-lookup"><span data-stu-id="2fc7f-114">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="2fc7f-115">如果 Office Web Apps 服务器在本地安装, 并且在与 Lync Server 2013 相同的网络区域中安装, 则不应选择 " **Office Web Apps 服务器" 部署在外部网络 (即周边/Internet) 中**。</span><span class="sxs-lookup"><span data-stu-id="2fc7f-115">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="2fc7f-116">如果 Office Web Apps 服务器部署在内部防火墙之外，则请选择选项“**在外部网络(即，外围/Internet)中部署 Office Web Apps 服务器**”。</span><span class="sxs-lookup"><span data-stu-id="2fc7f-116">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>

7.  <span data-ttu-id="2fc7f-117">在“**定义新的 Office Web Apps Server**”对话框中，单击“**确定**”，然后在“**编辑属性**”对话框中单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="2fc7f-117">In the **Define New Office Web Apps Server** dialog box, click **OK**, and then click **OK** in the **Edit Properties** dialog box.</span></span> <span data-ttu-id="2fc7f-118">Office Web Apps 发现 URL 随后将作为该池的关联之一列出。</span><span class="sxs-lookup"><span data-stu-id="2fc7f-118">The Office Web Apps discovery URL will then be listed as one of the pool's Associations.</span></span>

<span data-ttu-id="2fc7f-119">您必须对需要与您的 Office Web Apps 服务器关联的每个池重复此过程。</span><span class="sxs-lookup"><span data-stu-id="2fc7f-119">You will have to repeat this process for each pool that needs to be associated with your Office Web Apps Server.</span></span>

<span data-ttu-id="2fc7f-120">将发现 URL 添加到拓扑后, 必须随后发布此更新后的拓扑。</span><span class="sxs-lookup"><span data-stu-id="2fc7f-120">After you have added the discovery URL to the topology you must then publish this updated topology.</span></span> <span data-ttu-id="2fc7f-121">若要在拓扑生成器中执行此操作：</span><span class="sxs-lookup"><span data-stu-id="2fc7f-121">To do that in Topology Builder:</span></span>

1.  <span data-ttu-id="2fc7f-122">单击“**操作**”，然后单击“**发布拓扑**”。</span><span class="sxs-lookup"><span data-stu-id="2fc7f-122">Click **Action** and then click **Publish Topology**.</span></span>

2.  <span data-ttu-id="2fc7f-123">在发布拓扑向导的“**发布拓扑**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="2fc7f-123">In the Publish Topology wizard, on the **Publish the Topology** page, click **Next**.</span></span>

3.  <span data-ttu-id="2fc7f-124">在“**发布向导完成**”页上，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="2fc7f-124">On the **Publishing wizard complete** page, click **Finish**.</span></span>

4.  <span data-ttu-id="2fc7f-125">关闭拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="2fc7f-125">Close Topology Builder.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

