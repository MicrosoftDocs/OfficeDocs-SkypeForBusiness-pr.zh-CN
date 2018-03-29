---
title: 在 Skype for Business Server 2015 中配置与 Office Web Apps Server 的集成
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: 摘要： 请阅读本主题，以了解如何配置以启用 web 会议的 PowerPoint 演示文稿的 Office Web 应用程序服务器和业务服务器 2015年的 Skype 之间的集成。
ms.openlocfilehash: da6b5765cf62fc97fcc20b72e2411db306b37f0e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server-2015"></a><span data-ttu-id="f370d-103">在 Skype for Business Server 2015 中配置与 Office Web Apps Server 的集成</span><span class="sxs-lookup"><span data-stu-id="f370d-103">Configure integration with Office Web Apps Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f370d-104">**摘要：**阅读本主题，以了解如何配置以启用 web 会议的 PowerPoint 演示文稿的 Office Web 应用程序服务器和业务服务器 2015年的 Skype 之间的集成。</span><span class="sxs-lookup"><span data-stu-id="f370d-104">**Summary:** Read this topic to learn how to configure integration between Office Web Apps Server and Skype for Business Server 2015 to enable PowerPoint presentations for web conferencing.</span></span>
  
<span data-ttu-id="f370d-105">Skype 业务服务器使用 Office Web 应用程序服务器，以处理 web 会议的 PowerPoint 演示文稿。</span><span class="sxs-lookup"><span data-stu-id="f370d-105">Skype for Business Server employs Office Web Apps Server to handle PowerPoint presentations for web conferencing.</span></span> <span data-ttu-id="f370d-106">有关此方法的优点的信息，请参阅[规划业务服务器 2015年的 Skype 在会议](../../plan-your-deployment/conferencing/conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="f370d-106">For information about the advantages to this approach, see [Plan for conferencing in Skype for Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md).</span></span>
  
<span data-ttu-id="f370d-107">可以配置 Skype 业务服务器使用 Office Web 应用程序服务器之前，必须确保已部署和配置 Office Web 应用程序服务器。</span><span class="sxs-lookup"><span data-stu-id="f370d-107">Before you can configure Skype for Business Server to use Office Web Apps Server, you must ensure that Office Web Apps Server is already deployed and configured.</span></span> <span data-ttu-id="f370d-108">Office Web 应用程序服务器的信息，请参阅文章[部署基础结构： Office 联机服务器](https://go.microsoft.com/fwlink/p/?linkid=257525)。</span><span class="sxs-lookup"><span data-stu-id="f370d-108">For information on Office Web Apps Server, see the article [Deploy the infrastructure: Office Online Server](https://go.microsoft.com/fwlink/p/?linkid=257525).</span></span> 
  
<span data-ttu-id="f370d-109">Office Web 应用程序服务器已成功安装并正确配置您的 Web 服务器场，必须再配置业务服务器与新服务器通信的将 Office Web 应用程序服务器搜索 URL 添加到您的业务的 Skype 的 Skype 后服务器拓扑结构。</span><span class="sxs-lookup"><span data-stu-id="f370d-109">After Office Web Apps Server has been successfully installed and your Web farm correctly configured, you must then configure Skype for Business Server to communicate with the new server by adding the Office Web Apps Server discovery URL to your Skype for Business Server topology.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f370d-110">Office Web 应用程序服务器的最新小版本名为 Office 联机服务器，它受业务服务器 2015 Skype。</span><span class="sxs-lookup"><span data-stu-id="f370d-110">The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Skype for Business Server 2015.</span></span> <span data-ttu-id="f370d-111">有关详细信息，请参阅[Office 联机服务器的文档](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f370d-111">For more detail, refer to the [Office Online Server documentation](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx).</span></span> 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a><span data-ttu-id="f370d-112">Skype 与 Office Web 应用程序服务器进行通信的业务服务器的配置</span><span class="sxs-lookup"><span data-stu-id="f370d-112">Configure Skype for Business Server to communicate with Office Web Apps Server</span></span>

<span data-ttu-id="f370d-113">若要向拓扑中添加 Office Web Apps 服务器，请完成下列步骤：</span><span class="sxs-lookup"><span data-stu-id="f370d-113">To add Office Web Apps Server to your topology, complete the following steps:</span></span>
  
1.  <span data-ttu-id="f370d-114">打开 Skype 业务服务器拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="f370d-114">Open Skype for Business Server Topology Builder.</span></span>
    
2. <span data-ttu-id="f370d-115">在“**拓扑生成器**”对话框中，选择“**从现有部署下载拓扑**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="f370d-115">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>
    
3. <span data-ttu-id="f370d-p104">在“**将拓扑另存为**”对话框的“**文件名**”框中为拓扑文档键入一个名称（例如“**PreWebAppsServerTopology**”），然后单击“**保存**”。如果之后你的新拓扑遇到问题，则可检索和重新发布此拓扑。</span><span class="sxs-lookup"><span data-stu-id="f370d-p104">In the **Save Topology As** dialog box, type a name for your topology document (for example, **PreWebAppsServerTopology**) in the **File name** box and then click **Save**. This topology can later be retrieved and republished if you encounter problems with your new topology.</span></span>
    
4. <span data-ttu-id="f370d-118">在拓扑生成器中，依次展开“**Skype for Business Server**”、站点的名称和“**Enterprise Edition 前端池**”，右键单击某个池的名称，然后单击“**编辑属性**”。</span><span class="sxs-lookup"><span data-stu-id="f370d-118">In Topology Builder, expand **Skype for Business Server**, expand the name of your site, expand **Enterprise Edition Front End pools**, right-click the name of one of your pools, and then click **Edit Properties**.</span></span>
    
5. <span data-ttu-id="f370d-119">在“**编辑属性**”对话框的“**常规**”选项卡上，查找标题“**关联 Office Web Apps 服务器**”，然后单击“**新建**”（或从下拉列表中选择现有 Office Web Apps 服务器）。</span><span class="sxs-lookup"><span data-stu-id="f370d-119">In the **Edit Properties** dialog box, on the **General** tab, find the heading **Associate Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>
    
6. <span data-ttu-id="f370d-120">在“**定义新的 Office Web Apps 服务器**”对话框的“**Office Web Apps 服务器 FQDN**”框中，键入你的 Office Web Apps 服务器计算机的完全限定域名 (FQDN)；执行此操作时，你的 Office Web Apps 服务器搜索 URL 应自动输入到“**Office Web Apps 服务器搜索 URL**”框中。</span><span class="sxs-lookup"><span data-stu-id="f370d-120">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
  - <span data-ttu-id="f370d-121">如果 Office Web 应用程序服务器是内部部署安装和 Skype 业务服务器然后选择相同的网络分区**Office Web 应用程序服务器被部署在外部网络 (也就是说，外围/Internet)**应该不会选择。</span><span class="sxs-lookup"><span data-stu-id="f370d-121">If the Office Web Apps Server is installed on-premises and in the same network zone as Skype for Business Server then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
  - <span data-ttu-id="f370d-122">如果 Office Web Apps 服务器部署在内部防火墙之外，则请选择选项“**在外部网络(即，外围/Internet)中部署 Office Web Apps 服务器**”。</span><span class="sxs-lookup"><span data-stu-id="f370d-122">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>
    
7. <span data-ttu-id="f370d-p105">在“**定义新的 Office Web Apps Server**”对话框中，单击“**确定**”，然后在“**编辑属性**”对话框中单击“**确定**”。Office Online 发现 URL 将作为池的关联之一列出。</span><span class="sxs-lookup"><span data-stu-id="f370d-p105">In the **Define New Office Web Apps Server** dialog box, click **OK**, and then click **OK** in the **Edit Properties** dialog box. The Office Online discovery URL will then be listed as one of the pool's Associations.</span></span>
    
<span data-ttu-id="f370d-125">您必须对需要与您的 Office Web Apps 服务器关联的每个池重复此过程。</span><span class="sxs-lookup"><span data-stu-id="f370d-125">You will have to repeat this process for each pool that needs to be associated with your Office Web Apps Server.</span></span>
  
<span data-ttu-id="f370d-p106">向拓扑添加搜索 URL 后，必须发布更新的拓扑。若要在拓扑生成器中执行此操作：</span><span class="sxs-lookup"><span data-stu-id="f370d-p106">After you have added the discovery URL to the topology, you must then publish the updated topology. To do that in Topology Builder:</span></span>
  
1. <span data-ttu-id="f370d-128">单击“**操作**”，然后单击“**发布拓扑**”。</span><span class="sxs-lookup"><span data-stu-id="f370d-128">Click **Action** and then click **Publish Topology**.</span></span>
    
2. <span data-ttu-id="f370d-129">在发布拓扑向导的“**发布拓扑**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="f370d-129">In the Publish Topology wizard, on the **Publish the Topology** page, click **Next**.</span></span>
    
3. <span data-ttu-id="f370d-130">在“**发布向导完成**”页上，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="f370d-130">On the **Publishing wizard complete** page, click **Finish**.</span></span>
    
4. <span data-ttu-id="f370d-131">关闭拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="f370d-131">Close Topology Builder.</span></span>
    
## <a name="configure-access-for-external-users"></a><span data-ttu-id="f370d-132">配置外部用户访问</span><span class="sxs-lookup"><span data-stu-id="f370d-132">Configure access for external users</span></span>

<span data-ttu-id="f370d-133">如果您希望为外部用户 （即，从登录您所在组织的防火墙之外） 有权访问 Office Web 应用程序服务器 PowerPoint 演示文稿，则需要使用 Office Web 应用程序服务器和反向代理服务器。</span><span class="sxs-lookup"><span data-stu-id="f370d-133">If you want external users (that is, users logging on from outside your organization's firewall) to have access to Office Web Apps Server PowerPoint presentations, then you will need to use Office Web Apps Server and a reverse proxy server.</span></span> <span data-ttu-id="f370d-134">你还需要创建和配置网站发布规则，这有助于确保用户能连接到服务器。</span><span class="sxs-lookup"><span data-stu-id="f370d-134">You will also need to create and configure a website publishing rule, which will help ensure that users are able to connect to the server.</span></span> 
  
## <a name="validate-the-configuration"></a><span data-ttu-id="f370d-135">验证配置</span><span class="sxs-lookup"><span data-stu-id="f370d-135">Validate the configuration</span></span>

<span data-ttu-id="f370d-136">Office Web 应用程序服务器添加到拓扑结构中之后和在发布该拓扑结构之后，您应该看到两个新 Skype 业务服务器事件日志中的事件日志事件。</span><span class="sxs-lookup"><span data-stu-id="f370d-136">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Skype for Business Server event log.</span></span> <span data-ttu-id="f370d-137">首先，应该添加 LS 数据 MCU 事件（事件 ID 41034）；此事件将报告已发现 Office Web Apps Server：</span><span class="sxs-lookup"><span data-stu-id="f370d-137">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>
  
 <span data-ttu-id="f370d-138">**已发现 Web 会议服务器 Office Web Apps Server，启用了 PowerPoint 内容。**</span><span class="sxs-lookup"><span data-stu-id="f370d-138">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>
  
<span data-ttu-id="f370d-p109">例如，除了应该查看报告回 Office Web Apps Server URL 的另一个 LS Data MCU 事件（事件 ID 41032），还应该查看类似以下内容：</span><span class="sxs-lookup"><span data-stu-id="f370d-p109">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs. For example, you should see something similar to this:</span></span>
  
 <span data-ttu-id="f370d-141">**已成功发现 Web 会议服务器 Office Web Apps Server。**</span><span class="sxs-lookup"><span data-stu-id="f370d-141">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>
  
 <span data-ttu-id="f370d-142">**Office 应用程序的 Web 服务器内部演示者网页： https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp;嵌入 =**</span><span class="sxs-lookup"><span data-stu-id="f370d-142">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp;embed=**</span></span>
  
 <span data-ttu-id="f370d-143">**Office 应用程序的 Web 服务器内部与会者网页： https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;嵌入 = true&amp;=**</span><span class="sxs-lookup"><span data-stu-id="f370d-143">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp;=**</span></span>
  
<span data-ttu-id="f370d-144">如果配置了外部用户访问，你还将看到类似下面的内容：</span><span class="sxs-lookup"><span data-stu-id="f370d-144">If you have configured access for external users, you will see also see something similar to:</span></span>
  
 <span data-ttu-id="f370d-145">**Office Web 应用程序服务器外部演示者网页： https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp;嵌入**</span><span class="sxs-lookup"><span data-stu-id="f370d-145">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp;embed**</span></span>
  
 <span data-ttu-id="f370d-146">**Office 应用程序的 Web 服务器内部与会者网页： https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;嵌入 = true&amp;**</span><span class="sxs-lookup"><span data-stu-id="f370d-146">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp;**</span></span>
  
<span data-ttu-id="f370d-147">如果出现事件 id 为 41033，则意味着该 Office Web 应用程序服务器发现 LS 数据 MCU 事件失败。</span><span class="sxs-lookup"><span data-stu-id="f370d-147">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="f370d-148">在这种情况下，Skype 业务服务器将尝试发现新配置 Office Web 应用程序服务器所需的次数。</span><span class="sxs-lookup"><span data-stu-id="f370d-148">In that case, Skype for Business Server will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="f370d-149">如果发现过程反复失败应从拓扑文档中删除 Office Web 应用程序服务器、 发布更新的拓扑，然后尝试连接问题都已解决之后返回到拓扑结构中添加 Office Web 应用程序服务器。</span><span class="sxs-lookup"><span data-stu-id="f370d-149">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>
  
<span data-ttu-id="f370d-150">如果 Office Web 应用程序服务器看起来正确配置并且已经识别了发现过程可以验证 Office Web 应用程序服务器工作所需的共享一对 Skype 业务客户端之间的 PowerPoint 演示文稿。</span><span class="sxs-lookup"><span data-stu-id="f370d-150">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Skype for Business clients.</span></span> <span data-ttu-id="f370d-151">如果用户 A 可以加载并显示 PowerPoint 演示文稿，并且用户 B 可以加入会议并观看该演示文稿时使用 Office Web 应用程序服务器。</span><span class="sxs-lookup"><span data-stu-id="f370d-151">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>
  
<span data-ttu-id="f370d-152">即使 Office Web 应用程序服务器看起来正确配置，您可能有可能收到错误消息"一些共享功能是由于服务器连接问题而不可用"当您尝试共享的 PowerPoint 演示文稿。</span><span class="sxs-lookup"><span data-stu-id="f370d-152">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message "Some sharing features are unavailable due to server connectivity issues" when you try sharing a PowerPoint presentation.</span></span> <span data-ttu-id="f370d-153">如果您收到此错误消息，您应该重新启动与新的 Office Web 应用程序服务器前端服务器 （或服务器）。</span><span class="sxs-lookup"><span data-stu-id="f370d-153">If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>
  

