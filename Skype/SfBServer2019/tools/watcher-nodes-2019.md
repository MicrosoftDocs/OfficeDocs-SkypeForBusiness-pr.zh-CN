---
title: 配置将受视的 Skype for Business Server 计算机
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/7/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：在要监视的 Skype for business Server 2019 计算机上安装 Operations Manager 代理文件，并将计算机配置为充当 System Center proxy。
ms.openlocfilehash: 3fbe75b50faa0896d2458525734239317d21e49e
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40988967"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a><span data-ttu-id="1e764-103">配置将受视的 Skype for Business Server 计算机</span><span class="sxs-lookup"><span data-stu-id="1e764-103">Configure the Skype for Business Server computers that will be monitored</span></span>

<span data-ttu-id="1e764-104">**摘要：** 在要监视的 Skype for business Server 2019 计算机上安装 Operations Manager 代理文件，并将计算机配置为充当 System Center proxy。</span><span class="sxs-lookup"><span data-stu-id="1e764-104">**Summary:** Install the Operations Manager agent files on the Skype for Business Server 2019 computer to be monitored, and configure the computer to act as a System Center proxy.</span></span>

<span data-ttu-id="1e764-105">要监视的每个 Skype for Business 服务器2019计算机必须能够自我报告它是否存在于管理服务器。</span><span class="sxs-lookup"><span data-stu-id="1e764-105">Each Skype for Business Server 2019 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="1e764-106">为了启用此过程，必须在每台要受监视的计算机上安装 Operations Manager 代理文件。</span><span class="sxs-lookup"><span data-stu-id="1e764-106">To enable this process, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="1e764-107">安装代理文件后，必须将计算机配置为作为 System Center 代理。</span><span class="sxs-lookup"><span data-stu-id="1e764-107">After installing the agent files, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="1e764-108">在执行这些过程之前，请确保首先在这些计算机上安装和配置 Skype for Business 服务器。</span><span class="sxs-lookup"><span data-stu-id="1e764-108">Be sure that you have first installed and configured Skype for Business Server on these computers before carrying out these procedures.</span></span>

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a><span data-ttu-id="1e764-109">在位于外围网络外的观察程序节点上安装证书</span><span class="sxs-lookup"><span data-stu-id="1e764-109">Installing a Certificate on a Watcher Node Located Outside the Perimeter Network</span></span>
<span data-ttu-id="1e764-110"><a name="watcher_node_outside"> </a></span><span class="sxs-lookup"><span data-stu-id="1e764-110"></span></span>

<span data-ttu-id="1e764-111">在外围网络（如 Skype for Business 服务器 Edge 服务器）之外、企业外部（如外部合成事务观察程序节点）或跨 Active Directory 信任边界运行的 System Center Operations Manager 代理可能需要System Center Operations Manager 网关服务器的配置。</span><span class="sxs-lookup"><span data-stu-id="1e764-111">System Center Operations Manager agents running in a perimeter network (such as a Skype for Business Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory trust boundary, may require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="1e764-112">此服务器角色可使与根管理服务器没有信任关系的代理发出警报。</span><span class="sxs-lookup"><span data-stu-id="1e764-112">This server role enables agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="1e764-113">有关详细信息，请参阅[管理 Operations Manager 中的网关服务器 2012](https://technet.microsoft.com/en-us/library/hh212823.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1e764-113">For details, see [Managing Gateway Servers in Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212823.aspx).</span></span>

<span data-ttu-id="1e764-114">如果在其中一个位置中部署代理，你还需要请求和配置一个允许观察程序节点向 System Center Operations Manager 发送警报的证书。</span><span class="sxs-lookup"><span data-stu-id="1e764-114">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="1e764-115">为简化此过程，Operations Manager 团队已创建一组实用工具，可让你在观察程序节点计算机上请求和安装正确的证书类型。</span><span class="sxs-lookup"><span data-stu-id="1e764-115">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="1e764-116">有关详细信息和下载这些实用程序的信息，请参阅[通过证书生成向导轻松获取用于非域加入代理的证书](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="1e764-116">For details, and to download these utilities, see [Obtaining Certificates for Non-Domain Joined Agents Made Easy with Certificate Generation Wizard](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).</span></span>

### <a name="installing-the-operation-manager-agent-files"></a><span data-ttu-id="1e764-117">安装 Operation Manager 代理文件</span><span class="sxs-lookup"><span data-stu-id="1e764-117">Installing the Operation Manager Agent Files</span></span>

1. <span data-ttu-id="1e764-118">在 System Center 安装介质上，双击“Setup.exe\*\*\*\*”。</span><span class="sxs-lookup"><span data-stu-id="1e764-118">On your System Center setup media, double-click **Setup.exe**.</span></span>

2. <span data-ttu-id="1e764-119">在 System Center Operation Manager 安装程序向导中，单击 "**安装 Operations Manager 代理**"，从 "可选安装" 下的 "安装代理"</span><span class="sxs-lookup"><span data-stu-id="1e764-119">In the System Center Operation Manager setup wizard, click **Install Operations Manager Agent**, from Install Agent under Optional Installations</span></span>

3. <span data-ttu-id="1e764-120">在 System Center 设置向导中的 "欢迎使用 System Center Operations Manager 安装程序向导" 页面上，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="1e764-120">In the System Center setup wizard, on the Welcome to the System Center Operations Manager Setup wizard page, click **Next**.</span></span>

4. <span data-ttu-id="1e764-121">在 "目标文件夹" 页面上，选择将安装 Operations Manager 代理文件的文件夹，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="1e764-121">On the Destination Folder page, select the folder where the Operations Manager Agent files will be installed and click **Next**.</span></span>

5. <span data-ttu-id="1e764-122">在“管理组配置”页面上选择“指定管理组信息”\*\*\*\*。然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1e764-122">On the Management Group Configuration page, select **Specify Management Group information** and click **Next**.</span></span>

6. <span data-ttu-id="1e764-123">在 "管理组配置" 页面上，在 "**管理组名称**" 框中键入 Operations Manager 管理组的名称，然后在 "**管理服务器**" 框中键入 operations manager 服务器的主机名（如 "atl-scom-001"）。</span><span class="sxs-lookup"><span data-stu-id="1e764-123">On the Management Group Configuration page, type the name of your Operations Manager Management Group in the **Management Group Name** box, and then type the host name of your Operations Manager server (for example, atl-scom-001) in the **Management Server** box.</span></span> <span data-ttu-id="1e764-124">如果更改了 Operations Manager 使用的端口号，请在 "**管理服务器端口**" 框中输入新的端口号。</span><span class="sxs-lookup"><span data-stu-id="1e764-124">If you changed the port number used by Operations Manager, enter the new port number in the **Management Server Port** box.</span></span> <span data-ttu-id="1e764-125">否则，将该端口保留为默认值5723，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="1e764-125">Otherwise, leave the port at the default value of 5723, and then click **Next**.</span></span>

7. <span data-ttu-id="1e764-126">在“代理操作帐户”页面上，选择“本地系统”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1e764-126">On the Agent Action Account page, select **Local System** and click **Next**.</span></span>

8. <span data-ttu-id="1e764-127">在“Microsoft Update”页面上，选择“我不想使用 Microsoft Update”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1e764-127">On the Microsoft Update page, select **I don't want to use Microsoft Update** and click **Next**.</span></span>

9. <span data-ttu-id="1e764-128">在“安装准备就绪”页面上，单击“安装”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1e764-128">On the Ready to Install page, click **Install**.</span></span>

10. <span data-ttu-id="1e764-129">在 "正在完成 System Center Operations Manager 安装向导" 页面上，单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="1e764-129">On the Completing the System Center Operations Manager Setup wizard page, click **Finish**.</span></span>

11. <span data-ttu-id="1e764-130">单击“退出”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1e764-130">Click **Exit**.</span></span>

<span data-ttu-id="1e764-131">对于 System Center 2012，你可以通过单击 "**开始**"，单击 "**所有程序**"，单击 " **System Center Operations manager 2012**"，然后单击 "**操作2012管理器**" 来验证是否已创建代理。</span><span class="sxs-lookup"><span data-stu-id="1e764-131">For System Center 2012, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking **System Center Operations Manager 2012**, and then clicking **Operations 2012 Manager Shell**.</span></span> <span data-ttu-id="1e764-132">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span><span class="sxs-lookup"><span data-stu-id="1e764-132">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>
```PowerShell
Get-SCOMAgent
```

<span data-ttu-id="1e764-133">所有 Operations Manager 代理的列表将出现在屏幕上。</span><span class="sxs-lookup"><span data-stu-id="1e764-133">A list of all your Operations Manager agents will appear.</span></span>
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="1e764-134">将 Skype for Business Server 计算机配置为参加 System Center Discovery</span><span class="sxs-lookup"><span data-stu-id="1e764-134">Configuring the Skype for Business Server Computer to Participate in System Center Discovery</span></span>
<span data-ttu-id="1e764-135"><a name="watcher_node_outside"> </a></span><span class="sxs-lookup"><span data-stu-id="1e764-135"></span></span>

<span data-ttu-id="1e764-136">若要确保新的 Skype for Business 服务器代理参与 System Center Operations Manager 的发现过程，必须在安装了 System Center Operations Manager 控制台的每台计算机上完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="1e764-136">To make sure that your new Skype for Business Server agent participates in the discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>

1. <span data-ttu-id="1e764-137">在“管理”选项卡上，单击“代理托管”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1e764-137">On the Administration tab, click **Agent Managed**.</span></span>

2. <span data-ttu-id="1e764-138">单击“发现向导”\*\*\*\*，然后完成向导，以使计算机能被发现。</span><span class="sxs-lookup"><span data-stu-id="1e764-138">Click on **Discovery Wizard** and complete the wizard for the computer to be discovered.</span></span>

3. <span data-ttu-id="1e764-139">重新启动健康代理服务。</span><span class="sxs-lookup"><span data-stu-id="1e764-139">Reboot the Health Agent service.</span></span> <span data-ttu-id="1e764-140">重新启动该服务将强制发现新计算机。</span><span class="sxs-lookup"><span data-stu-id="1e764-140">Rebooting the service will force discovery of the new machine.</span></span> <span data-ttu-id="1e764-141">如果您不重新启动该服务，则系统中心运营经理可能需要长达4小时才能发现新计算机。</span><span class="sxs-lookup"><span data-stu-id="1e764-141">If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.</span></span>

4. <span data-ttu-id="1e764-142">验证 Operations Manager 事件日志中是否未记录任何错误事件。</span><span class="sxs-lookup"><span data-stu-id="1e764-142">Verify that no error events were recorded in the Operations Manager event log.</span></span>

5. <span data-ttu-id="1e764-143">成功推送代理的计算机将显示在 "代理托管" 列表下，并且手动安装了代理的计算机将显示在 "挂起的管理" 下，单击计算机名称并批准。</span><span class="sxs-lookup"><span data-stu-id="1e764-143">The computer where the agent is pushed successfully will be shown under "Agent Managed" list and the computer where agent was installed manually will be shown under "Pending Management", click on the computer name and approve.</span></span>

6. <span data-ttu-id="1e764-p107">右键单击计算机的名称，然后单击“属性”\*\*\*\*。在“属性”对话框中的“安全性”选项卡上，选择“允许此代理充当代理并发现其他计算机上的托管对象”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1e764-p107">Right-click the name of the computer, and then click **Properties**. In the Properties dialog box, on the Security tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>


