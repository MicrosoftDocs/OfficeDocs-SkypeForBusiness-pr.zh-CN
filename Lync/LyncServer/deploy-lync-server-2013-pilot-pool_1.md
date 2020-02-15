---
title: 部署 Lync Server 2013 试点池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204718(v=OCS.15)
ms:contentKeyID: 48183539
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c97ea5304309aaf635ac284e792a73634c5ae19
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="59d5a-102">部署 Lync Server 2013 试点池</span><span class="sxs-lookup"><span data-stu-id="59d5a-102">Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59d5a-103">_**上次修改的主题：** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="59d5a-103">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="59d5a-104">迁移到 Lync Server 2013 所需的第一步是部署试点池。</span><span class="sxs-lookup"><span data-stu-id="59d5a-104">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="59d5a-105">试点池是您在 Office 通信服务器 2007 R2 部署中测试 Lync Server 2013 共存的地方。</span><span class="sxs-lookup"><span data-stu-id="59d5a-105">The pilot pool is where you test coexistence of Lync Server 2013 with your Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="59d5a-106">共存是在将所有用户和池移到 Lync Server 2013 之前一直持续的临时状态。</span><span class="sxs-lookup"><span data-stu-id="59d5a-106">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="59d5a-107">部署试点池时，应使用“定义新前端池”向导。</span><span class="sxs-lookup"><span data-stu-id="59d5a-107">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="59d5a-108">您应在您的 Office 通信服务器 2007 R2 池中的 Lync Server 2013 试验池中部署相同的功能和工作负载。</span><span class="sxs-lookup"><span data-stu-id="59d5a-108">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="59d5a-109">如果您部署了存档服务器、监视服务器或 System Center Operations Manager 以存档或监视 Office 通信服务器 2007 R2 环境，并且您希望在整个迁移过程中继续存档或监视，您需要此外，还可以在您的试点环境中部署这些功能。</span><span class="sxs-lookup"><span data-stu-id="59d5a-109">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Office Communications Server 2007 R2 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="59d5a-110">您部署用于存档或监视 Office 通信服务器 2007 R2 环境的版本将不会在 Lync Server 2013 环境中捕获数据。</span><span class="sxs-lookup"><span data-stu-id="59d5a-110">The version you deployed to archive or monitor your Office Communications Server 2007 R2 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="59d5a-111">随后的过程讨论应被视为试点池总体部署过程一部分的功能和设置。</span><span class="sxs-lookup"><span data-stu-id="59d5a-111">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="59d5a-112">本节只着重介绍在部署试点池的过程中应考虑的关键点。</span><span class="sxs-lookup"><span data-stu-id="59d5a-112">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="59d5a-113">有关详细步骤，请参阅<A href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</A>部署指南。</span><span class="sxs-lookup"><span data-stu-id="59d5a-113">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="59d5a-114">**部署 Lync Server 2013 引导池**</span><span class="sxs-lookup"><span data-stu-id="59d5a-114">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="59d5a-115">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="59d5a-115">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="59d5a-116">打开拓扑生成器并选择创建新拓扑。</span><span class="sxs-lookup"><span data-stu-id="59d5a-116">Open Topology Builder and choose to create a new topology.</span></span>

3.  <span data-ttu-id="59d5a-117">输入主 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="59d5a-117">Enter the primary SIP domain.</span></span>
    
    <span data-ttu-id="59d5a-118">![新建拓扑，定义主域页面](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "新建拓扑，定义主域页面")</span><span class="sxs-lookup"><span data-stu-id="59d5a-118">![Create New Topology, Define primary domain page](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Create New Topology, Define primary domain page")</span></span>

4.  <span data-ttu-id="59d5a-119">继续完成向导，直到出现“定义新前端池”\*\*\*\* 向导。</span><span class="sxs-lookup"><span data-stu-id="59d5a-119">Continue completing the wizard until you reach the **Define the New Front End pool** wizard.</span></span> <span data-ttu-id="59d5a-120">单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="59d5a-120">Click Next.</span></span>

5.  <span data-ttu-id="59d5a-121">输入池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="59d5a-121">Enter the pool FQDN.</span></span> <span data-ttu-id="59d5a-122">在定义试点池时，可以选择部署企业版前端池或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="59d5a-122">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="59d5a-123">Lync Server 2013 不要求您的引导池功能与您的旧版池中部署的功能相匹配。</span><span class="sxs-lookup"><span data-stu-id="59d5a-123">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="59d5a-124">您为试点定义的池或服务器的完全限定域名 (FQDN) 必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="59d5a-124">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="59d5a-125">它无法与当前部署的 Office 通信服务器 2007 R2 池或当前部署的任何其他服务器的名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="59d5a-125">It cannot match the name of the currently deployed Office Communications Server 2007 R2 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="59d5a-126">![定义前端池 FQDN 页](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "定义前端池 FQDN 页")</span><span class="sxs-lookup"><span data-stu-id="59d5a-126">![Define the Front End pool FQDN page](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Define the Front End pool FQDN page")</span></span>

6.  <span data-ttu-id="59d5a-127">定义将添加到池中的计算机。</span><span class="sxs-lookup"><span data-stu-id="59d5a-127">Define the computer that will be added to the pool.</span></span>
    
    <span data-ttu-id="59d5a-128">!["定义新的前端池" 对话框](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg ""定义新的前端池" 对话框")</span><span class="sxs-lookup"><span data-stu-id="59d5a-128">![Define New Front End Pool dialog](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Define New Front End Pool dialog")</span></span>

7.  <span data-ttu-id="59d5a-129">在“选择功能”\*\*\*\* 页上，选中希望此前端池具有的功能的复选框。</span><span class="sxs-lookup"><span data-stu-id="59d5a-129">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="59d5a-130">例如，如果您仅部署即时消息 (IM) 和状态功能，可以选中“会议”复选框以允许多方 IM，但不能选中“电话拨入式(PSTN)会议”、“企业语音”或“呼叫允许控制”复选框，因为它们代表语音、视频和协作会议功能。</span><span class="sxs-lookup"><span data-stu-id="59d5a-130">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="59d5a-131">有关选择功能的其他信息，请参阅部署文档中的在[Lync server 2013 中定义和配置前端池或 Standard Edition server](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="59d5a-131">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="59d5a-132">![前端池选择功能页](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "前端池选择功能页")</span><span class="sxs-lookup"><span data-stu-id="59d5a-132">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

8.  <span data-ttu-id="59d5a-133">在 "**选择并置服务器角色**" 页上，我们建议您在 Lync server 2013 中并置中介服务器。</span><span class="sxs-lookup"><span data-stu-id="59d5a-133">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="59d5a-134">将旧版拓扑与 Lync Server 2013 合并时，我们需要您首先并置 Office 通信服务器 2007 R2 中介服务器。</span><span class="sxs-lookup"><span data-stu-id="59d5a-134">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Office Communications Server 2007 R2 Mediation Server.</span></span> <span data-ttu-id="59d5a-135">在合并拓扑并配置 Lync Server 2013 中介服务器之后，您可以决定是否保留并置中介服务器，或在部署中将中介服务器角色移到 Lync Server 2013 时将其更改为独立服务器过程.</span><span class="sxs-lookup"><span data-stu-id="59d5a-135">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="59d5a-136">![前端池选择 "并置服务器角色" 页](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "前端池选择 "并置服务器角色" 页")</span><span class="sxs-lookup"><span data-stu-id="59d5a-136">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

9.  <span data-ttu-id="59d5a-p109">在部署试点池过程中，不要选择“将服务器角色与此前端池关联”\*\*\*\* 页上的“启用此前端池的媒体组件要使用的边缘池”\*\*\*\* 选项。这是您将启用并使其在后面的迁移阶段进入联机状态的功能。目前请清除此设置。</span><span class="sxs-lookup"><span data-stu-id="59d5a-p109">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option. This is a feature you will enable and bring online in a later phase of migration. Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="59d5a-140">![将服务器角色与前端池页面关联](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "将服务器角色与前端池页面关联")</span><span class="sxs-lookup"><span data-stu-id="59d5a-140">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

10. <span data-ttu-id="59d5a-141">在“选择 Office Web Apps 服务器”\*\*\*\* 页上，单击“新建”\*\*\*\* 并指定应用程序服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="59d5a-141">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="59d5a-142">![定义新的 Office Web Apps Server FQDN 属性](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "定义新的 Office Web Apps Server FQDN 属性")</span><span class="sxs-lookup"><span data-stu-id="59d5a-142">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

11. <span data-ttu-id="59d5a-143">在 "**定义存档 SQL Server 存储**" 页上，选择之前为 Lync Server 2013 创建的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="59d5a-143">On the **Define the Archiving SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="59d5a-144">![定义 "存档 SQL Server 存储" 页](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "定义 "存档 SQL Server 存储" 页")</span><span class="sxs-lookup"><span data-stu-id="59d5a-144">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

12. <span data-ttu-id="59d5a-145">在 "**定义监视 SQL Server 存储**" 页上，选择之前为 Lync Server 2013 创建的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="59d5a-145">On the **Define the Monitoring SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span> <span data-ttu-id="59d5a-146">单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59d5a-146">Click **Finish**.</span></span>

13. <span data-ttu-id="59d5a-p111">从拓扑生成器的顶部节点中，右键单击“Lync Server”\*\*\*\* 并单击“编辑属性”\*\*\*\*。单击“简单 URL”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59d5a-p111">From the top node of Topology Builder, right click **Lync Server** and click **Edit Properties.** Click **Simple URLs**.</span></span>

14. <span data-ttu-id="59d5a-149">更新“管理访问 URL”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59d5a-149">Update the **Administrative access URL**.</span></span>
    
    <span data-ttu-id="59d5a-150">!["编辑属性"、"简单 Url" 页](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg ""编辑属性"、"简单 Url" 页")</span><span class="sxs-lookup"><span data-stu-id="59d5a-150">![Edit Properties, Simple URLs page](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Edit Properties, Simple URLs page")</span></span>
    
    <span data-ttu-id="59d5a-151">有关简单 Url 的其他信息，请参阅部署文档中的主题 "[在 Lync Server 2013 中编辑或配置简单 url](lync-server-2013-edit-or-configure-simple-urls.md) "。</span><span class="sxs-lookup"><span data-stu-id="59d5a-151">For additional information on Simple URLs, see the topic [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

15. <span data-ttu-id="59d5a-152">从“编辑属性”\*\*\*\* 中，单击“中央管理服务器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59d5a-152">From the **Edit Properties**, click **Central Management Server**.</span></span>

16. <span data-ttu-id="59d5a-153">从下拉列表中，选择 "Lync Server 2013" 池。</span><span class="sxs-lookup"><span data-stu-id="59d5a-153">From the drop-down list, select the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="59d5a-154">![编辑属性（中央管理服务器页面）](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "编辑属性（中央管理服务器页面）")</span><span class="sxs-lookup"><span data-stu-id="59d5a-154">![Edit Properties, Central Management Server page](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Edit Properties, Central Management Server page")</span></span>

17. <span data-ttu-id="59d5a-155">单击“确定”\*\*\*\* 关闭“编辑属性”页。</span><span class="sxs-lookup"><span data-stu-id="59d5a-155">Click OK to close **the Edit Properties** page.</span></span>

18. <span data-ttu-id="59d5a-156">从“操作”\*\*\*\* 菜单上选择“发布拓扑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59d5a-156">From the **Action** menu, select **Publish Topology**.</span></span>

19. <span data-ttu-id="59d5a-157">发布过程完成后，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59d5a-157">When the publish process has completed, click **Finish**.</span></span>

20. <span data-ttu-id="59d5a-158">返回到 Lync Server 2013 部署向导，请单击 "**安装或更新 Lync Server 系统**"。</span><span class="sxs-lookup"><span data-stu-id="59d5a-158">Returning to the Lync Server 2013 Deployment Wizard, click **Install or Update Lync Server System**.</span></span>
    
    <span data-ttu-id="59d5a-159">![Lync Server 2013 部署向导](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 部署向导")</span><span class="sxs-lookup"><span data-stu-id="59d5a-159">![Lync Server 2013 Deployment Wizard](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 Deployment Wizard")</span></span>

<span data-ttu-id="59d5a-160">若要安装配置存储的本地副本并启动所需的服务，请参阅部署文档中的为[Lync Server 2013 设置前端服务器和前端池](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)。</span><span class="sxs-lookup"><span data-stu-id="59d5a-160">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>

