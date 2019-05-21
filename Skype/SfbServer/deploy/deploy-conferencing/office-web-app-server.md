---
title: 在 Skype for Business Server 中配置与 Office Web Apps 服务器的集成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: '摘要: 阅读本主题, 了解如何配置 Office Web Apps 服务器与 Skype for business 服务器之间的集成, 以启用适用于 Web 会议的 PowerPoint 演示文稿。'
ms.openlocfilehash: e657820a7a44197a344f23a67fdcd42ce0e593a8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289109"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a><span data-ttu-id="4f608-103">在 Skype for Business Server 中配置与 Office Web Apps 服务器的集成</span><span class="sxs-lookup"><span data-stu-id="4f608-103">Configure integration with Office Web Apps Server in Skype for Business Server</span></span>
 
<span data-ttu-id="4f608-104">**摘要:** 阅读本主题, 了解如何配置 Office Web Apps 服务器与 Skype for business 服务器之间的集成, 以启用适用于 Web 会议的 PowerPoint 演示文稿。</span><span class="sxs-lookup"><span data-stu-id="4f608-104">**Summary:** Read this topic to learn how to configure integration between Office Web Apps Server and Skype for Business Server to enable PowerPoint presentations for web conferencing.</span></span>
  
<span data-ttu-id="4f608-105">Skype for business 服务器使用 Office Web Apps 服务器处理适用于 Web 会议的 PowerPoint 演示文稿。</span><span class="sxs-lookup"><span data-stu-id="4f608-105">Skype for Business Server employs Office Web Apps Server to handle PowerPoint presentations for web conferencing.</span></span> <span data-ttu-id="4f608-106">有关此方法的优势的信息, 请参阅[在 Skype For Business 服务器中规划会议](../../plan-your-deployment/conferencing/conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="4f608-106">For information about the advantages to this approach, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md).</span></span>
  
<span data-ttu-id="4f608-107">在将 Skype for business 服务器配置为使用 Office Web Apps 服务器之前, 必须确保已部署和配置 Office Web Apps 服务器。</span><span class="sxs-lookup"><span data-stu-id="4f608-107">Before you can configure Skype for Business Server to use Office Web Apps Server, you must ensure that Office Web Apps Server is already deployed and configured.</span></span> <span data-ttu-id="4f608-108">有关 Office Web Apps 服务器的信息, 请参阅[部署基础结构的文章: Office Online server](https://go.microsoft.com/fwlink/p/?linkid=257525)。</span><span class="sxs-lookup"><span data-stu-id="4f608-108">For information on Office Web Apps Server, see the article [Deploy the infrastructure: Office Online Server](https://go.microsoft.com/fwlink/p/?linkid=257525).</span></span> 
  
<span data-ttu-id="4f608-109">在成功安装 Office Web Apps 服务器并正确配置 Web 场后, 必须随后将 Office Web Apps 服务器发现 URL 添加到 Skype for business, 将 Skype for Business 服务器配置为与新服务器通信服务器拓扑。</span><span class="sxs-lookup"><span data-stu-id="4f608-109">After Office Web Apps Server has been successfully installed and your Web farm correctly configured, you must then configure Skype for Business Server to communicate with the new server by adding the Office Web Apps Server discovery URL to your Skype for Business Server topology.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="4f608-110">Office Web Apps 服务器的最新小版本称为 "Office Online Server", 该服务器受 Skype for Business 服务器支持。</span><span class="sxs-lookup"><span data-stu-id="4f608-110">The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Skype for Business Server.</span></span> <span data-ttu-id="4f608-111">有关更多详细信息, 请参阅[Office Online Server 文档](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4f608-111">For more detail, refer to the [Office Online Server documentation](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx).</span></span> 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a><span data-ttu-id="4f608-112">配置 Skype for Business 服务器以与 Office Web Apps 服务器通信</span><span class="sxs-lookup"><span data-stu-id="4f608-112">Configure Skype for Business Server to communicate with Office Web Apps Server</span></span>

<span data-ttu-id="4f608-113">若要向拓扑中添加 Office Web Apps 服务器，请完成下列步骤：</span><span class="sxs-lookup"><span data-stu-id="4f608-113">To add Office Web Apps Server to your topology, complete the following steps:</span></span>
  
1. <span data-ttu-id="4f608-114">打开 Skype for Business 服务器拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="4f608-114">Open Skype for Business Server Topology Builder.</span></span>
    
2. <span data-ttu-id="4f608-115">在“**拓扑生成器**”对话框中，选择“**从现有部署下载拓扑**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="4f608-115">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>
    
3. <span data-ttu-id="4f608-p104">在“**将拓扑另存为**”对话框的“**文件名**”框中为拓扑文档键入一个名称（例如“**PreWebAppsServerTopology**”），然后单击“**保存**”。如果之后你的新拓扑遇到问题，则可检索和重新发布此拓扑。</span><span class="sxs-lookup"><span data-stu-id="4f608-p104">In the **Save Topology As** dialog box, type a name for your topology document (for example, **PreWebAppsServerTopology**) in the **File name** box and then click **Save**. This topology can later be retrieved and republished if you encounter problems with your new topology.</span></span>
    
4. <span data-ttu-id="4f608-118">在拓扑生成器中，依次展开“**Skype for Business Server**”、站点的名称和“**Enterprise Edition 前端池**”，右键单击某个池的名称，然后单击“**编辑属性**”。</span><span class="sxs-lookup"><span data-stu-id="4f608-118">In Topology Builder, expand **Skype for Business Server**, expand the name of your site, expand **Enterprise Edition Front End pools**, right-click the name of one of your pools, and then click **Edit Properties**.</span></span>
    
5. <span data-ttu-id="4f608-119">在“**编辑属性**”对话框的“**常规**”选项卡上，查找标题“**关联 Office Web Apps 服务器**”，然后单击“**新建**”（或从下拉列表中选择现有 Office Web Apps 服务器）。</span><span class="sxs-lookup"><span data-stu-id="4f608-119">In the **Edit Properties** dialog box, on the **General** tab, find the heading **Associate Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>
    
6. <span data-ttu-id="4f608-120">在“**定义新的 Office Web Apps 服务器**”对话框的“**Office Web Apps 服务器 FQDN**”框中，键入你的 Office Web Apps 服务器计算机的完全限定域名 (FQDN)；执行此操作时，你的 Office Web Apps 服务器搜索 URL 应自动输入到“**Office Web Apps 服务器搜索 URL**”框中。</span><span class="sxs-lookup"><span data-stu-id="4f608-120">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
   - <span data-ttu-id="4f608-121">如果 Office Web Apps 服务器在本地安装, 并且在与 Skype for Business 服务器相同的网络区域中安装, 则不应选择 " **Office Web apps" 服务器在外部网络 (即, 周边/Internet) 中部署**。</span><span class="sxs-lookup"><span data-stu-id="4f608-121">If the Office Web Apps Server is installed on-premises and in the same network zone as Skype for Business Server then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
   - <span data-ttu-id="4f608-122">如果 Office Web Apps 服务器部署在内部防火墙之外，则请选择选项“**在外部网络(即，外围/Internet)中部署 Office Web Apps 服务器**”。</span><span class="sxs-lookup"><span data-stu-id="4f608-122">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>
    
7. <span data-ttu-id="4f608-p105">在“**定义新的 Office Web Apps Server**”对话框中，单击“**确定**”，然后在“**编辑属性**”对话框中单击“**确定**”。Office Online 发现 URL 将作为池的关联之一列出。</span><span class="sxs-lookup"><span data-stu-id="4f608-p105">In the **Define New Office Web Apps Server** dialog box, click **OK**, and then click **OK** in the **Edit Properties** dialog box. The Office Online discovery URL will then be listed as one of the pool's Associations.</span></span>
    
<span data-ttu-id="4f608-125">您必须对需要与您的 Office Web Apps 服务器关联的每个池重复此过程。</span><span class="sxs-lookup"><span data-stu-id="4f608-125">You will have to repeat this process for each pool that needs to be associated with your Office Web Apps Server.</span></span>
  
<span data-ttu-id="4f608-p106">向拓扑添加搜索 URL 后，必须发布更新的拓扑。若要在拓扑生成器中执行此操作：</span><span class="sxs-lookup"><span data-stu-id="4f608-p106">After you have added the discovery URL to the topology, you must then publish the updated topology. To do that in Topology Builder:</span></span>
  
1. <span data-ttu-id="4f608-128">单击“**操作**”，然后单击“**发布拓扑**”。</span><span class="sxs-lookup"><span data-stu-id="4f608-128">Click **Action** and then click **Publish Topology**.</span></span>
    
2. <span data-ttu-id="4f608-129">在发布拓扑向导的“**发布拓扑**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="4f608-129">In the Publish Topology wizard, on the **Publish the Topology** page, click **Next**.</span></span>
    
3. <span data-ttu-id="4f608-130">在“**发布向导完成**”页上，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="4f608-130">On the **Publishing wizard complete** page, click **Finish**.</span></span>
    
4. <span data-ttu-id="4f608-131">关闭拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="4f608-131">Close Topology Builder.</span></span>
    
## <a name="configure-access-for-external-users"></a><span data-ttu-id="4f608-132">配置外部用户访问</span><span class="sxs-lookup"><span data-stu-id="4f608-132">Configure access for external users</span></span>

<span data-ttu-id="4f608-133">如果你希望外部用户 (即从组织防火墙外部登录的用户) 有权访问 Office Web Apps Server PowerPoint 演示文稿, 则需要使用 Office Web Apps 服务器和反向代理服务器。</span><span class="sxs-lookup"><span data-stu-id="4f608-133">If you want external users (that is, users logging on from outside your organization's firewall) to have access to Office Web Apps Server PowerPoint presentations, then you will need to use Office Web Apps Server and a reverse proxy server.</span></span> <span data-ttu-id="4f608-134">你还需要创建和配置网站发布规则，这有助于确保用户能连接到服务器。</span><span class="sxs-lookup"><span data-stu-id="4f608-134">You will also need to create and configure a website publishing rule, which will help ensure that users are able to connect to the server.</span></span> 
  
## <a name="validate-the-configuration"></a><span data-ttu-id="4f608-135">验证配置</span><span class="sxs-lookup"><span data-stu-id="4f608-135">Validate the configuration</span></span>

<span data-ttu-id="4f608-136">在将 Office Web Apps 服务器添加到拓扑后, 在该拓扑发布后, 你应该会在 Skype for Business 服务器事件日志中看到两个新的事件日志事件。</span><span class="sxs-lookup"><span data-stu-id="4f608-136">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Skype for Business Server event log.</span></span> <span data-ttu-id="4f608-137">首先，应该添加 LS 数据 MCU 事件（事件 ID 41034）；此事件将报告已发现 Office Web Apps Server：</span><span class="sxs-lookup"><span data-stu-id="4f608-137">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>
  
 <span data-ttu-id="4f608-138">**已发现 Web 会议服务器 Office Web Apps Server，启用了 PowerPoint 内容。**</span><span class="sxs-lookup"><span data-stu-id="4f608-138">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>
  
<span data-ttu-id="4f608-p109">例如，除了应该查看报告回 Office Web Apps Server URL 的另一个 LS Data MCU 事件（事件 ID 41032），还应该查看类似以下内容：</span><span class="sxs-lookup"><span data-stu-id="4f608-p109">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs. For example, you should see something similar to this:</span></span>
  
 <span data-ttu-id="4f608-141">**已成功发现 Web 会议服务器 Office Web Apps Server。**</span><span class="sxs-lookup"><span data-stu-id="4f608-141">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>
  
 <span data-ttu-id="4f608-142">**Office Web Apps 服务器内部演示者页面https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp:; 嵌入 =**</span><span class="sxs-lookup"><span data-stu-id="4f608-142">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp;embed=**</span></span>
  
 <span data-ttu-id="4f608-143">**Office Web Apps 服务器内部与会者页面: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp; 嵌入 = true&amp;=**</span><span class="sxs-lookup"><span data-stu-id="4f608-143">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp;=**</span></span>
  
<span data-ttu-id="4f608-144">如果你已为外部用户配置访问权限, 你还会看到类似于以下内容的内容:</span><span class="sxs-lookup"><span data-stu-id="4f608-144">If you have configured access for external users, you will also see something similar to:</span></span>
  
 <span data-ttu-id="4f608-145">**Office Web Apps 服务器外部演示者页面https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp:; 嵌入**</span><span class="sxs-lookup"><span data-stu-id="4f608-145">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp;embed**</span></span>
  
 <span data-ttu-id="4f608-146">**Office Web Apps 服务器内部与会者页面: <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>;**</span><span class="sxs-lookup"><span data-stu-id="4f608-146">**Office Web Apps Server internal attendee page: <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>;**</span></span>
  
<span data-ttu-id="4f608-147">如果看到的 LS 数据 MCU 事件的事件 ID 为 41033, 表示 Office Web Apps 服务器发现失败。</span><span class="sxs-lookup"><span data-stu-id="4f608-147">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="4f608-148">在这种情况下, Skype for Business 服务器将根据需要尝试多次, 以发现新配置的 Office Web Apps 服务器。</span><span class="sxs-lookup"><span data-stu-id="4f608-148">In that case, Skype for Business Server will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="4f608-149">如果发现过程重复失败, 则应从拓扑文档中删除 Office Web Apps 服务器, 发布更新后的拓扑, 然后尝试在连接问题解决后将 Office Web App 服务器重新添加到拓扑。</span><span class="sxs-lookup"><span data-stu-id="4f608-149">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>
  
<span data-ttu-id="4f608-150">如果 Office Web Apps 服务器似乎配置正确且已被发现过程识别, 则可以通过在一对 Skype for Business 客户端之间共享 PowerPoint 演示文稿来验证 Office Web Apps 服务器是否按预期工作。</span><span class="sxs-lookup"><span data-stu-id="4f608-150">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Skype for Business clients.</span></span> <span data-ttu-id="4f608-151">如果用户 A 可以加载和显示 PowerPoint 演示文稿, 并且如果用户 B 可以加入会议并查看该演示文稿, 则 Office Web Apps 服务器正在工作。</span><span class="sxs-lookup"><span data-stu-id="4f608-151">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>
  
<span data-ttu-id="4f608-152">即使 Office Web Apps 服务器显示正确配置, 您也可能会收到错误消息 "当你尝试共享 PowerPoint 演示文稿时, 由于服务器连接问题, 某些共享功能不可用"。</span><span class="sxs-lookup"><span data-stu-id="4f608-152">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message "Some sharing features are unavailable due to server connectivity issues" when you try sharing a PowerPoint presentation.</span></span> <span data-ttu-id="4f608-153">如果您收到该错误消息, 则应重新启动与新的 Office Web Apps 服务器相关联的前端服务器 (或服务器)。</span><span class="sxs-lookup"><span data-stu-id="4f608-153">If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>
  

