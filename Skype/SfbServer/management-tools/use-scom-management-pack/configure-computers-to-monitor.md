---
title: 配置将受视的 Skype for Business Server 计算机
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b24ea184-4b3e-4277-a244-157afb4b368b
description: 摘要： 安装上业务服务器 2015年计算机要监视，Skype 的运营经理代理文件和配置作为系统中心代理的计算机。
ms.openlocfilehash: bbf2abfe2617b8bc03dd56d3ecdafc25643ba17e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a><span data-ttu-id="7d52d-103">配置将受视的 Skype for Business Server 计算机</span><span class="sxs-lookup"><span data-stu-id="7d52d-103">Configure the Skype for Business Server computers that will be monitored</span></span>
 
<span data-ttu-id="7d52d-104">**摘要：**安装业务服务器 2015年计算机要监视，Skype 的运营经理代理文件和配置作为系统中心代理的计算机。</span><span class="sxs-lookup"><span data-stu-id="7d52d-104">**Summary:** Install the Operations Manager agent files on the Skype for Business Server 2015 computer to be monitored, and configure the computer to act as a System Center proxy.</span></span>
  
<span data-ttu-id="7d52d-105">每个 Skype 为想要监视的业务服务器 2015年计算机必须能够自我报告其存在到管理服务器。</span><span class="sxs-lookup"><span data-stu-id="7d52d-105">Each Skype for Business Server 2015 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="7d52d-106">为了启用此过程，必须在每台要受监视的计算机上安装 Operations Manager 代理文件。</span><span class="sxs-lookup"><span data-stu-id="7d52d-106">To enable this process, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="7d52d-107">安装代理文件后，必须将计算机配置为作为 System Center 代理。</span><span class="sxs-lookup"><span data-stu-id="7d52d-107">After installing the agent files, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="7d52d-108">请确保您首次安装和 Skype 业务服务器上配置这些计算机在执行这些过程之前。</span><span class="sxs-lookup"><span data-stu-id="7d52d-108">Be sure that you have first installed and configured Skype for Business Server on these computers before carrying out these procedures.</span></span>
  
## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a><span data-ttu-id="7d52d-109">在位于外围网络外的观察程序节点上安装证书</span><span class="sxs-lookup"><span data-stu-id="7d52d-109">Installing a Certificate on a Watcher Node Located Outside the Perimeter Network</span></span>
<span data-ttu-id="7d52d-110"><a name="watcher_node_outside"> </a></span><span class="sxs-lookup"><span data-stu-id="7d52d-110"></span></span>

<span data-ttu-id="7d52d-111">系统中心操作管理器代理运行在外围网络 （如业务服务器边缘服务器 Skype) 外企业 （如外部综合事务观察程序节点中），或需要通过 Active Directory 信任边界，系统中心操作管理器网关服务器的配置。</span><span class="sxs-lookup"><span data-stu-id="7d52d-111">System Center Operations Manager agents running in a perimeter network (such as a Skype for Business Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory trust boundary, may require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="7d52d-112">此服务器角色可使与根管理服务器没有信任关系的代理发出警报。</span><span class="sxs-lookup"><span data-stu-id="7d52d-112">This server role enables agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="7d52d-113">有关详细信息，请参阅[管理运营经理 2012年中的网关服务器](https://technet.microsoft.com/en-us/library/hh212823.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7d52d-113">For details, see [Managing Gateway Servers in Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212823.aspx).</span></span>
  
<span data-ttu-id="7d52d-114">如果部署代理程序在两个位置之一时，将需要请求并配置证书，使观察者节点向系统中心操作管理器发送警报。</span><span class="sxs-lookup"><span data-stu-id="7d52d-114">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="7d52d-115">若要简化这一过程，运营经理团队已创建一组实用程序，您可以请求并观察程序节点计算机上安装正确的证书类型。</span><span class="sxs-lookup"><span data-stu-id="7d52d-115">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="7d52d-116">有关详细信息，以及要下载这些实用工具，请参阅[为非域加入代理进行简单与证书生成向导获取证书](http://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="7d52d-116">For details, and to download these utilities, see [Obtaining Certificates for Non-Domain Joined Agents Made Easy with Certificate Generation Wizard](http://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).</span></span>
  
### <a name="installing-the-operation-manager-agent-files"></a><span data-ttu-id="7d52d-117">安装 Operation Manager 代理文件</span><span class="sxs-lookup"><span data-stu-id="7d52d-117">Installing the Operation Manager Agent Files</span></span>

1. <span data-ttu-id="7d52d-118">在 System Center 安装介质上，双击“Setup.exe****”。</span><span class="sxs-lookup"><span data-stu-id="7d52d-118">On your System Center setup media, double-click **Setup.exe**.</span></span>
    
2. <span data-ttu-id="7d52d-119">在系统中心操作管理器安装向导中，单击**安装操作管理器代理**，请从安装在可选安装的代理</span><span class="sxs-lookup"><span data-stu-id="7d52d-119">In the System Center Operation Manager setup wizard, click **Install Operations Manager Agent**, from Install Agent under Optional Installations</span></span>
    
3. <span data-ttu-id="7d52d-120">在系统中心安装向导中，在欢迎系统中心操作管理器安装向导页中，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7d52d-120">In the System Center setup wizard, on the Welcome to the System Center Operations Manager Setup wizard page, click **Next**.</span></span>
    
4. <span data-ttu-id="7d52d-121">在目标文件夹页中，选择的文件夹的操作管理器代理文件将被安装，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7d52d-121">On the Destination Folder page, select the folder where the Operations Manager Agent files will be installed and click **Next**.</span></span>
    
5. <span data-ttu-id="7d52d-122">在“管理组配置”页面上选择“指定管理组信息”****。然后单击“下一步”****。</span><span class="sxs-lookup"><span data-stu-id="7d52d-122">On the Management Group Configuration page, select **Specify Management Group information** and click **Next**.</span></span>
    
6. <span data-ttu-id="7d52d-123">在管理组配置页上，请在**管理组名称**框中，键入操作管理器管理组的名称，然后键入您的操作管理器服务器的主机名 (例如，atl-scom-001) 在**管理服务器**框。</span><span class="sxs-lookup"><span data-stu-id="7d52d-123">On the Management Group Configuration page, type the name of your Operations Manager Management Group in the **Management Group Name** box, and then type the host name of your Operations Manager server (for example, atl-scom-001) in the **Management Server** box.</span></span> <span data-ttu-id="7d52d-124">如果更改操作管理器使用的端口号，请在**管理服务器端口**框中输入新的端口号。</span><span class="sxs-lookup"><span data-stu-id="7d52d-124">If you changed the port number used by Operations Manager, enter the new port number in the **Management Server Port** box.</span></span> <span data-ttu-id="7d52d-125">否则为保留 5723，默认值的端口，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7d52d-125">Otherwise, leave the port at the default value of 5723, and then click **Next**.</span></span>
    
7. <span data-ttu-id="7d52d-126">在“代理操作帐户”页面上，选择“本地系统”****，然后单击“下一步”****。</span><span class="sxs-lookup"><span data-stu-id="7d52d-126">On the Agent Action Account page, select **Local System** and click **Next**.</span></span>
    
8. <span data-ttu-id="7d52d-127">在“Microsoft Update”页面上，选择“我不想使用 Microsoft Update”****，然后单击“下一步”****。</span><span class="sxs-lookup"><span data-stu-id="7d52d-127">On the Microsoft Update page, select **I don't want to use Microsoft Update** and click **Next**.</span></span>
    
9. <span data-ttu-id="7d52d-128">在“安装准备就绪”页面上，单击“安装”****。</span><span class="sxs-lookup"><span data-stu-id="7d52d-128">On the Ready to Install page, click **Install**.</span></span>
    
10. <span data-ttu-id="7d52d-129">在完成系统中心操作管理器安装向导页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="7d52d-129">On the Completing the System Center Operations Manager Setup wizard page, click **Finish**.</span></span>
    
11. <span data-ttu-id="7d52d-130">单击“退出”****。</span><span class="sxs-lookup"><span data-stu-id="7d52d-130">Click **Exit**.</span></span>
    
<span data-ttu-id="7d52d-131">对于 System Center 2012，您可以验证已通过单击**「 开始 」**，然后单击**所有程序**、**系统中心操作管理器 2012**年，**操作管理器外壳 2012年**创建了代理。</span><span class="sxs-lookup"><span data-stu-id="7d52d-131">For System Center 2012, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking **System Center Operations Manager 2012**, and then clicking **Operations 2012 Manager Shell**.</span></span> <span data-ttu-id="7d52d-132">在操作管理器外壳中，键入下面的 Windows PowerShell 命令，然后按 enter 键：</span><span class="sxs-lookup"><span data-stu-id="7d52d-132">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>
```
Get-SCOMAgent
```

<span data-ttu-id="7d52d-133">所有 Operations Manager 代理的列表将出现在屏幕上。</span><span class="sxs-lookup"><span data-stu-id="7d52d-133">A list of all your Operations Manager agents will appear.</span></span>
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="7d52d-134">将 Skype for Business Server 计算机配置为参加 System Center Discovery</span><span class="sxs-lookup"><span data-stu-id="7d52d-134">Configuring the Skype for Business Server Computer to Participate in System Center Discovery</span></span>
<span data-ttu-id="7d52d-135"><a name="watcher_node_outside"> </a></span><span class="sxs-lookup"><span data-stu-id="7d52d-135"></span></span>

<span data-ttu-id="7d52d-136">若要确保该业务服务器代理为您新 Skype 参与发现过程系统中心操作管理器，您必须完成系统中心操作管理器控制台安装位置的每台计算机上的以下过程：</span><span class="sxs-lookup"><span data-stu-id="7d52d-136">To make sure that your new Skype for Business Server agent participates in the discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>
  
1. <span data-ttu-id="7d52d-137">在“管理”选项卡上，单击“代理托管”****。</span><span class="sxs-lookup"><span data-stu-id="7d52d-137">On the Administration tab, click **Agent Managed**.</span></span>
    
2. <span data-ttu-id="7d52d-138">单击“发现向导”****，然后完成向导，以使计算机能被发现。</span><span class="sxs-lookup"><span data-stu-id="7d52d-138">Click on **Discovery Wizard** and complete the wizard for the computer to be discovered.</span></span>
    
3. <span data-ttu-id="7d52d-139">重新启动健康代理服务。</span><span class="sxs-lookup"><span data-stu-id="7d52d-139">Reboot the Health Agent service.</span></span> <span data-ttu-id="7d52d-140">重新启动该服务将强制发现新计算机。</span><span class="sxs-lookup"><span data-stu-id="7d52d-140">Rebooting the service will force discovery of the new machine.</span></span> <span data-ttu-id="7d52d-141">如果不重新启动该服务，它可能需要最长为 4 个小时前发现新计算机系统中心操作管理器。</span><span class="sxs-lookup"><span data-stu-id="7d52d-141">If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.</span></span> 
    
4. <span data-ttu-id="7d52d-142">验证 Operations Manager 事件日志中是否未记录任何错误事件。</span><span class="sxs-lookup"><span data-stu-id="7d52d-142">Verify that no error events were recorded in the Operations Manager event log.</span></span>
    
5. <span data-ttu-id="7d52d-143">其中成功推送代理的计算机将显示在"代理托管"列表下，代理手动安装的计算机将显示在"挂起管理"下，单击计算机名称和批准。</span><span class="sxs-lookup"><span data-stu-id="7d52d-143">The computer where the agent is pushed successfully will be shown under "Agent Managed" list and the computer where agent was installed manually will be shown under "Pending Management", click on the computer name and approve.</span></span>
    
6. <span data-ttu-id="7d52d-p107">右键单击计算机的名称，然后单击“属性”****。在“属性”对话框中的“安全性”选项卡上，选择“允许此代理充当代理并发现其他计算机上的托管对象”****，然后单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="7d52d-p107">Right-click the name of the computer, and then click **Properties**. In the Properties dialog box, on the Security tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>
    

