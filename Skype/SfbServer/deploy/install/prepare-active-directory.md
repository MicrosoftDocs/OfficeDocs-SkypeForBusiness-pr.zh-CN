---
title: 为 Skype for business 服务器准备 Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: 摘要：了解如何为安装 Skype for Business 服务器准备 Active Directory 域。 从 Microsoft 评估中心的以下位置下载 Skype for Business Server 的免费试用版：https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。
ms.openlocfilehash: a7b9a22042cecae76a5a5390b0778119363043b5
ms.sourcegitcommit: a6e051c5c5c100dbf2ff3ca8fc7babc4415babf3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2020
ms.locfileid: "41554049"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a><span data-ttu-id="625f8-104">为 Skype for business 服务器准备 Active Directory</span><span class="sxs-lookup"><span data-stu-id="625f8-104">Prepare Active Directory for Skype for Business Server</span></span>
 
<span data-ttu-id="625f8-105">**摘要：** 了解如何为 Skype for business 服务器的安装准备 Active Directory 域。</span><span class="sxs-lookup"><span data-stu-id="625f8-105">**Summary:** Learn how to prepare your Active Directory domain for an installation of Skype for Business Server.</span></span> <span data-ttu-id="625f8-106">从[Microsoft 评估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)下载 Skype For business 服务器的免费试用版。</span><span class="sxs-lookup"><span data-stu-id="625f8-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="625f8-107">Skype for business 服务器与 Active Directory 密切协作。</span><span class="sxs-lookup"><span data-stu-id="625f8-107">Skype for Business Server works closely with Active Directory.</span></span> <span data-ttu-id="625f8-108">必须准备 Active Directory 域以与 Skype for Business Server 进行协作。</span><span class="sxs-lookup"><span data-stu-id="625f8-108">You must prepare the Active Directory domain to work with Skype for Business Server.</span></span> <span data-ttu-id="625f8-109">将在部署向导中完成此流程，且仅对该域执行一次该流程。</span><span class="sxs-lookup"><span data-stu-id="625f8-109">This process is accomplished in the Deployment Wizard and is only done once for the domain.</span></span> <span data-ttu-id="625f8-110">这是因为，该流程会创建组和修改域，您仅需完成一次此项操作。</span><span class="sxs-lookup"><span data-stu-id="625f8-110">This is because the process creates groups and modifies the domain, and you need to do that only once.</span></span> <span data-ttu-id="625f8-111">第 1 步至第 5 步可以按任意顺序执行。</span><span class="sxs-lookup"><span data-stu-id="625f8-111">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="625f8-112">但是，第 6、7、8 步必须在第 1 步至第 5 步之后按图表所示顺序执行。</span><span class="sxs-lookup"><span data-stu-id="625f8-112">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="625f8-113">准备 Active Directory 是 8 个步骤中的第 4 步。</span><span class="sxs-lookup"><span data-stu-id="625f8-113">Preparing Active Directory is step 4 of 8.</span></span> <span data-ttu-id="625f8-114">有关规划 Active Directory 的详细信息，请参阅适用于 Skype for business Server 2019 的 Skype for business 服务器或[服务器要求](../../../SfBServer2019/plan/system-requirements.md)[的环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="625f8-114">For more information about planning for Active Directory, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![概述图表](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a><span data-ttu-id="625f8-116">准备 Active Directory</span><span class="sxs-lookup"><span data-stu-id="625f8-116">Prepare Active Directory</span></span>

<span data-ttu-id="625f8-117">Skype for business 服务器与 Active Directory 域服务（AD DS）紧密集成。</span><span class="sxs-lookup"><span data-stu-id="625f8-117">Skype for Business Server is tightly integrated with Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="625f8-118">第一次安装 Skype for Business 服务器之前，必须准备 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="625f8-118">Before Skype for Business Server can be installed for the first time, Active Directory must be prepared.</span></span> <span data-ttu-id="625f8-119">名为 "**准备 Active directory** " 的部署向导部分准备了用于 Skype For business 服务器的 Active directory 环境。</span><span class="sxs-lookup"><span data-stu-id="625f8-119">The section of the Deployment Wizard titled **Prepare Active Directory** prepares the Active Directory environment for use with Skype for Business Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="625f8-120">Skype for Business 服务器使用（AD DS）跟踪拓扑中的所有服务器并与之通信。</span><span class="sxs-lookup"><span data-stu-id="625f8-120">Skype for Business Server uses (AD DS) to track and communicate with all of the servers in a topology.</span></span> <span data-ttu-id="625f8-121">这些服务器中的大部分必须加入域，以便 Skype for Business 服务器可以正常工作。</span><span class="sxs-lookup"><span data-stu-id="625f8-121">The majority of these servers must be joined to the domain so that Skype for Business Server can work properly.</span></span> <span data-ttu-id="625f8-122">请记住，"边缘" 和 "反向代理" 等服务器不应加入域。</span><span class="sxs-lookup"><span data-stu-id="625f8-122">Keep in mind that servers such as Edge and Reverse Proxy should not be domain joined.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="625f8-123">应仅为部署中的每个域运行一次“准备 Active Directory”过程。</span><span class="sxs-lookup"><span data-stu-id="625f8-123">The Prepare Active Directory procedure should be run only once for each domain in the deployment.</span></span> 
  
<span data-ttu-id="625f8-124">观看“**准备 Active Directory**”视频了解相关步骤。</span><span class="sxs-lookup"><span data-stu-id="625f8-124">Watch the video steps for **Prepare Active Directory**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a><span data-ttu-id="625f8-125">通过部署向导准备 Active Directory</span><span class="sxs-lookup"><span data-stu-id="625f8-125">Prepare Active Directory from the Deployment Wizard</span></span>

1. <span data-ttu-id="625f8-126">以具备 Active Directory 域的 Schema Admins 凭证的用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="625f8-126">Log on as a user with Schema Admins credentials for the Active Directory domain.</span></span>
    
2. <span data-ttu-id="625f8-127">打开 Skype for Business 服务器部署向导。</span><span class="sxs-lookup"><span data-stu-id="625f8-127">Open Skype for Business Server Deployment Wizard.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="625f8-128">如果你想要查看由 Skype for Business Server 部署向导创建的日志文件，可以在运行该步骤的 AD DS 用户的用户目录中找到这些文件，这些文件位于运行部署向导的计算机上。</span><span class="sxs-lookup"><span data-stu-id="625f8-128">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the AD DS user who ran the step.</span></span> <span data-ttu-id="625f8-129">例如，如果用户在域中以域管理员的身份登录到本地登录，则日志文件位于： C:\Users\Administrator.Contoso\AppData\Local\Temp。</span><span class="sxs-lookup"><span data-stu-id="625f8-129">For example, if the user logged on as the domain administrator in the domain, contoso.local, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span> 
  
3. <span data-ttu-id="625f8-130">单击“**准备 Active Directory**”链接。</span><span class="sxs-lookup"><span data-stu-id="625f8-130">Click the **Prepare Active Directory** link.</span></span>
    
4. <span data-ttu-id="625f8-131">**第 1 步：准备架构**</span><span class="sxs-lookup"><span data-stu-id="625f8-131">**Step 1: Prepare schema**</span></span>
    
    <span data-ttu-id="625f8-132">a.</span><span class="sxs-lookup"><span data-stu-id="625f8-132">a.</span></span> <span data-ttu-id="625f8-133">检查第 1 步的先决条件信息，可单击第 1 步标题下的下拉菜单访问该信息。</span><span class="sxs-lookup"><span data-stu-id="625f8-133">Review the prerequisites information for Step 1 which can be accessed by clicking the drop-down under the Step 1 title.</span></span>
    
    <span data-ttu-id="625f8-134">b.</span><span class="sxs-lookup"><span data-stu-id="625f8-134">b.</span></span> <span data-ttu-id="625f8-135">单击第 1 步中的“**运行**”以启动“准备架构”向导。</span><span class="sxs-lookup"><span data-stu-id="625f8-135">Click **Run** in Step 1 to launch the Prepare Schema wizard.</span></span>
    
    <span data-ttu-id="625f8-136">c.</span><span class="sxs-lookup"><span data-stu-id="625f8-136">c.</span></span> <span data-ttu-id="625f8-137">请注意，应仅为每个部署执行一次该过程，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="625f8-137">Take note that the procedure should be run only once for each deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="625f8-138">d.</span><span class="sxs-lookup"><span data-stu-id="625f8-138">d.</span></span> <span data-ttu-id="625f8-139">准备好架构后，您可以单击“**查看日志**”以查看日志。</span><span class="sxs-lookup"><span data-stu-id="625f8-139">Once the schema has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="625f8-140">e.i.</span><span class="sxs-lookup"><span data-stu-id="625f8-140">e.</span></span> <span data-ttu-id="625f8-141">单击“**完成**”以关闭“准备架构”向导，然后返回“准备 Active Directory”步骤。</span><span class="sxs-lookup"><span data-stu-id="625f8-141">Click **Finish** to close the Prepare Schema wizard, and return to the Prepare Active Directory steps.</span></span>
    
5. <span data-ttu-id="625f8-142">**第 2 步：验证架构分区的复制**</span><span class="sxs-lookup"><span data-stu-id="625f8-142">**Step 2: Verify replication of schema partition**</span></span>
    
    <span data-ttu-id="625f8-143">a.</span><span class="sxs-lookup"><span data-stu-id="625f8-143">a.</span></span> <span data-ttu-id="625f8-144">登录到域的域控制器。</span><span class="sxs-lookup"><span data-stu-id="625f8-144">Log on to the domain controller for the domain.</span></span>
    
    <span data-ttu-id="625f8-145">b.</span><span class="sxs-lookup"><span data-stu-id="625f8-145">b.</span></span> <span data-ttu-id="625f8-146">从“**服务器管理器**”中的“**工具**”下拉菜单打开“**ADSI Edit**”。</span><span class="sxs-lookup"><span data-stu-id="625f8-146">Open **ADSI Edit** from the **Tools** drop-down menu in **Server Manager**.</span></span>
    
    <span data-ttu-id="625f8-147">c.</span><span class="sxs-lookup"><span data-stu-id="625f8-147">c.</span></span> <span data-ttu-id="625f8-148">在“**操作**”菜单上，单击“**连接到**”。</span><span class="sxs-lookup"><span data-stu-id="625f8-148">On the **Action** menu, click **Connect to**.</span></span>
    
    <span data-ttu-id="625f8-149">d.</span><span class="sxs-lookup"><span data-stu-id="625f8-149">d.</span></span> <span data-ttu-id="625f8-150">在“**连接设置**”对话框中的“**选择一个已知命名上下文**”下，选择“**架构**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="625f8-150">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
    <span data-ttu-id="625f8-151">e.i.</span><span class="sxs-lookup"><span data-stu-id="625f8-151">e.</span></span> <span data-ttu-id="625f8-152">在架构容器下，搜索“**CN=ms-RTC-SIP-SchemaVersion**”。</span><span class="sxs-lookup"><span data-stu-id="625f8-152">Under the schema container, search for **CN=ms-RTC-SIP-SchemaVersion**.</span></span> <span data-ttu-id="625f8-153">如果此对象存在，并且 **rangeUpper** 属性的值为 1150，**rangeLower** 属性的值为 3，则说明架构更新和复制成功。</span><span class="sxs-lookup"><span data-stu-id="625f8-153">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, the schema was successfully updated and replicated.</span></span> <span data-ttu-id="625f8-154">如果此对象不存在，或 **rangeUpper** 和 **rangeLower** 属性的值不是指定的值，则说明架构未经过修改或尚未复制。</span><span class="sxs-lookup"><span data-stu-id="625f8-154">If this object does not exist or the values of the **rangeUpper** and **rangeLower** attributes are not as specified, the schema was not modified or has not replicated.</span></span>
    
6. <span data-ttu-id="625f8-155">**第 3 步：准备当前林**</span><span class="sxs-lookup"><span data-stu-id="625f8-155">**Step 3: Prepare current forest**</span></span>
    
    <span data-ttu-id="625f8-156">a.</span><span class="sxs-lookup"><span data-stu-id="625f8-156">a.</span></span> <span data-ttu-id="625f8-157">检查第 3 步的先决条件信息，可单击第 3 步标题下的下拉菜单访问该信息。</span><span class="sxs-lookup"><span data-stu-id="625f8-157">Review the prerequisites information for Step 3 which can be accessed by clicking the drop-down under the Step 3 title.</span></span>
    
    <span data-ttu-id="625f8-158">b.</span><span class="sxs-lookup"><span data-stu-id="625f8-158">b.</span></span> <span data-ttu-id="625f8-159">单击第 3 步中的“**运行**”以启动“准备当前林”向导。</span><span class="sxs-lookup"><span data-stu-id="625f8-159">Click **Run** in Step 3 to launch the Prepare Current Forest wizard.</span></span>
    
    <span data-ttu-id="625f8-160">c.</span><span class="sxs-lookup"><span data-stu-id="625f8-160">c.</span></span> <span data-ttu-id="625f8-161">请注意，应仅为每个部署执行一次该过程，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="625f8-161">Take note that the procedure should be only run once per deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="625f8-162">d.</span><span class="sxs-lookup"><span data-stu-id="625f8-162">d.</span></span> <span data-ttu-id="625f8-163">指定将创建通用组的域。</span><span class="sxs-lookup"><span data-stu-id="625f8-163">Specify the domain where the universal groups will be created.</span></span> <span data-ttu-id="625f8-164">如果服务器是组的一部分，您可以选择“**本地域**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="625f8-164">If the server is part of the domain, you can choose **Local domain**, and click **Next**.</span></span>
    
    <span data-ttu-id="625f8-165">e.i.</span><span class="sxs-lookup"><span data-stu-id="625f8-165">e.</span></span> <span data-ttu-id="625f8-166">准备好林后，您可以单击“**查看日志**”以查看日志。</span><span class="sxs-lookup"><span data-stu-id="625f8-166">Once the forest has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="625f8-167">f.</span><span class="sxs-lookup"><span data-stu-id="625f8-167">f.</span></span> <span data-ttu-id="625f8-168">单击“**完成**”以关闭“准备当前林”向导，然后返回“准备 Active Directory”步骤。</span><span class="sxs-lookup"><span data-stu-id="625f8-168">Click **Finish** to close the Prepare Current Forest wizard, and return to the Prepare Active Directory steps.</span></span>
    
    <span data-ttu-id="625f8-169">7.</span><span class="sxs-lookup"><span data-stu-id="625f8-169">g.</span></span> <span data-ttu-id="625f8-170">单击 "**应用**" 页面上的 " **Skype For Business 服务器管理外壳**" 以启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="625f8-170">Click **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.</span></span>
    
    <span data-ttu-id="625f8-171">硬件.</span><span class="sxs-lookup"><span data-stu-id="625f8-171">h.</span></span> <span data-ttu-id="625f8-172">键入命令 CsAdForest，然后按**enter**。</span><span class="sxs-lookup"><span data-stu-id="625f8-172">Type the command Get-CsAdForest, and press **Enter**.</span></span>
    
    <span data-ttu-id="625f8-173">怎样.</span><span class="sxs-lookup"><span data-stu-id="625f8-173">i.</span></span> <span data-ttu-id="625f8-174">如果结果为**LC_FORESTSETTINGS_STATE_READY**，则林已成功准备，如图所示。</span><span class="sxs-lookup"><span data-stu-id="625f8-174">If the result is **LC_FORESTSETTINGS_STATE_READY**, the forest has successfully been prepared, as shown in the figure.</span></span>
    
     ![验证林复制。](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. <span data-ttu-id="625f8-176">**第 4 步：验证全局目录的复制**</span><span class="sxs-lookup"><span data-stu-id="625f8-176">**Step 4: Verify replication of the global catalog**</span></span>
    
    <span data-ttu-id="625f8-177">a.</span><span class="sxs-lookup"><span data-stu-id="625f8-177">a.</span></span> <span data-ttu-id="625f8-178">在运行林准备的林中的域控制器上（最好在其他域控制器的远程站点中），打开“**Active Directory 用户和计算机**”。</span><span class="sxs-lookup"><span data-stu-id="625f8-178">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
    <span data-ttu-id="625f8-179">b.</span><span class="sxs-lookup"><span data-stu-id="625f8-179">b.</span></span> <span data-ttu-id="625f8-180">在“**Active Directory 用户和计算机**”中，展开林或子域的域名。</span><span class="sxs-lookup"><span data-stu-id="625f8-180">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
    <span data-ttu-id="625f8-181">c.</span><span class="sxs-lookup"><span data-stu-id="625f8-181">c.</span></span> <span data-ttu-id="625f8-182">在左侧窗格中单击“**用户**”容器，在右侧窗格中查找通用组 **CsAdministrator**。</span><span class="sxs-lookup"><span data-stu-id="625f8-182">Click the **Users** container on the left side pane, and look for the Universal group **CsAdministrator** in the right side pane.</span></span> <span data-ttu-id="625f8-183">如果除其他以 Cs 开头的新通用组外还显示 CsAdministrator，则表明 Active Directory 的复制成功。</span><span class="sxs-lookup"><span data-stu-id="625f8-183">If CsAdministrator (among other new Universal groups that begin with Cs) is present, Active Directory replication has been successful.</span></span>
    
    <span data-ttu-id="625f8-184">d.</span><span class="sxs-lookup"><span data-stu-id="625f8-184">d.</span></span> <span data-ttu-id="625f8-185">如果未显示这些组，可以强制复制或等待 15 分钟后再刷新右侧窗格。</span><span class="sxs-lookup"><span data-stu-id="625f8-185">If the groups are not yet present, you can force the replication, or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="625f8-186">显示组后，表明复制完成。</span><span class="sxs-lookup"><span data-stu-id="625f8-186">When the groups are present, replication is complete.</span></span>
    
8. <span data-ttu-id="625f8-187">**第 5 步：准备当前域**</span><span class="sxs-lookup"><span data-stu-id="625f8-187">**Step 5: Prepare the current domain**</span></span>
    
    <span data-ttu-id="625f8-188">a.</span><span class="sxs-lookup"><span data-stu-id="625f8-188">a.</span></span> <span data-ttu-id="625f8-189">查看第 5 步的先决条件信息</span><span class="sxs-lookup"><span data-stu-id="625f8-189">Review the prerequisites information for Step 5.</span></span>
    
    <span data-ttu-id="625f8-190">b.</span><span class="sxs-lookup"><span data-stu-id="625f8-190">b.</span></span> <span data-ttu-id="625f8-191">单击第 5 步中的“**运行**”以启动“准备当前域”向导。</span><span class="sxs-lookup"><span data-stu-id="625f8-191">Click **Run** in Step 5 to launch the Prepare Current Domain wizard.</span></span>
    
    <span data-ttu-id="625f8-192">c.</span><span class="sxs-lookup"><span data-stu-id="625f8-192">c.</span></span> <span data-ttu-id="625f8-193">请注意，应仅为部署中的每个域执行一次该过程，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="625f8-193">Take note that the procedure should only be run once for each domain in the deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="625f8-194">d.</span><span class="sxs-lookup"><span data-stu-id="625f8-194">d.</span></span> <span data-ttu-id="625f8-195">准备好域后，您可以单击“**查看日志**”以查看日志。</span><span class="sxs-lookup"><span data-stu-id="625f8-195">Once the domain has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="625f8-196">e.i.</span><span class="sxs-lookup"><span data-stu-id="625f8-196">e.</span></span> <span data-ttu-id="625f8-197">单击“**完成**”以关闭“准备当前域”向导，然后返回“准备 Active Directory”步骤。</span><span class="sxs-lookup"><span data-stu-id="625f8-197">Click **Finish** to close the Prepare Current Domain wizard, and return to the Prepare Active Directory steps.</span></span>
    
    <span data-ttu-id="625f8-198">必须在每个找到 Skype for Business 服务器对象的域中完成这些步骤，否则服务可能无法启动。</span><span class="sxs-lookup"><span data-stu-id="625f8-198">These steps must be completed in every domain where Skype for Business Server objects are found, otherwise services might not start.</span></span> <span data-ttu-id="625f8-199">这包括任意类型的 Active Directory 对象，比如用户、联系人对象、管理组或其他任何类型的对象。</span><span class="sxs-lookup"><span data-stu-id="625f8-199">This includes any type of Active Directory object, such as users, contact objects, administrative groups, or any other type of object.</span></span> <span data-ttu-id="625f8-200">如果需要，你可以使用 CsUserReplicatorConfiguration-ADDomainNamingContextList 仅添加具有 Skype for business 服务器对象的域。</span><span class="sxs-lookup"><span data-stu-id="625f8-200">You can use Set-CsUserReplicatorConfiguration -ADDomainNamingContextList to add only the domains with Skype for Business Server objects, if needed.</span></span>
    
9. <span data-ttu-id="625f8-201">**第 6 步：验证域中的复制**</span><span class="sxs-lookup"><span data-stu-id="625f8-201">**Step 6: Verify replication in the domain**</span></span>
    
    <span data-ttu-id="625f8-202">a.</span><span class="sxs-lookup"><span data-stu-id="625f8-202">a.</span></span> <span data-ttu-id="625f8-203">从 "**应用**" 页面中单击 " **Skype For Business 服务器管理外壳**" 以启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="625f8-203">Click the **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.</span></span>
    
    <span data-ttu-id="625f8-204">b.</span><span class="sxs-lookup"><span data-stu-id="625f8-204">b.</span></span> <span data-ttu-id="625f8-205">使用命令 CsAdDomain 验证域内的复制。</span><span class="sxs-lookup"><span data-stu-id="625f8-205">Use the command Get-CsAdDomain to verify replication within the domain.</span></span>
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > <span data-ttu-id="625f8-206">如果不指定 Domain 参数，则将该值设置为本地域。</span><span class="sxs-lookup"><span data-stu-id="625f8-206">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> 
  
    <span data-ttu-id="625f8-207">为 contoso.local 域运行命令的示例：</span><span class="sxs-lookup"><span data-stu-id="625f8-207">Example of running the command for the contoso.local domain:</span></span>
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > <span data-ttu-id="625f8-p138">通过使用参数 GlobalSettingsDomainController，您可以指出存储全局设置的位置。如果设置存储在“系统”容器中（在全局设置尚未迁移到“配置”容器的升级部署中时通常是这种情况），则定义 AD DS 林的根中的某个域控制器。如果全局设置存储在“配置”容器中（在新部署或设置已迁移到“配置”容器的升级部署中时通常是这种情况），则定义林中的任何域控制器。如果未指定此参数，则 cmdlet 会假定设置存储在“配置”容器中，并引用 Active Directory 中的任何域控制器。</span><span class="sxs-lookup"><span data-stu-id="625f8-p138">By using the parameter GlobalSettingsDomainController, you can indicate where global settings are stored. If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your AD DS forest. If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest. If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="625f8-212">c.</span><span class="sxs-lookup"><span data-stu-id="625f8-212">c.</span></span> <span data-ttu-id="625f8-213">如果结果为**LC_DOMAINSETTINGS_STATE_READY**，则域已成功复制。</span><span class="sxs-lookup"><span data-stu-id="625f8-213">If the result is **LC_DOMAINSETTINGS_STATE_READY**, the domain has successfully replicated.</span></span>
    
10. <span data-ttu-id="625f8-214">**第 7 步：添加用户以提供 Skype for Business Server 控制面板的管理访问权限**</span><span class="sxs-lookup"><span data-stu-id="625f8-214">**Step 7: Add users to provide administrative access to the Skype for Business Server Control Panel**</span></span>
    
    <span data-ttu-id="625f8-215">a.</span><span class="sxs-lookup"><span data-stu-id="625f8-215">a.</span></span> <span data-ttu-id="625f8-216">以 Domain Admins 组或 RTCUniversalServerAdmins 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="625f8-216">Log on as a member of the Domain Admins group or the RTCUniversalServerAdmins group.</span></span>
    
    <span data-ttu-id="625f8-217">b.</span><span class="sxs-lookup"><span data-stu-id="625f8-217">b.</span></span> <span data-ttu-id="625f8-218">打开“**Active Directory 用户和计算机**”，展开域，单击“**用户**”容器，右键单击 CSAdministrator，然后选择“**属性**”。</span><span class="sxs-lookup"><span data-stu-id="625f8-218">Open **Active Directory Users and Computers**, expand your domain, click the **Users** container, right-click CSAdministrator, and choose **Properties**.</span></span>
    
    <span data-ttu-id="625f8-219">c.</span><span class="sxs-lookup"><span data-stu-id="625f8-219">c.</span></span> <span data-ttu-id="625f8-220">在“**CSAdministrator 属性**”中，单击“**成员**”选项卡。</span><span class="sxs-lookup"><span data-stu-id="625f8-220">In **CSAdministrator Properties**, click the **Members** tab.</span></span>
    
    <span data-ttu-id="625f8-221">d.</span><span class="sxs-lookup"><span data-stu-id="625f8-221">d.</span></span> <span data-ttu-id="625f8-222">在“**成员**”选项卡上，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="625f8-222">On the **Members** tab, click **Add**.</span></span> <span data-ttu-id="625f8-223">在“**选择用户、联系人、计算机、服务帐户或组**”中，找到“**输入要选择的对象名称**”。</span><span class="sxs-lookup"><span data-stu-id="625f8-223">In **Select Users, Contacts, Computers, Service Accounts, or Groups**, locate the **Enter the object names to select**.</span></span> <span data-ttu-id="625f8-224">键入要添加到 CSAdministrators 组的用户名或组名。</span><span class="sxs-lookup"><span data-stu-id="625f8-224">Type the user name(s) or group name(s) to add to the group CSAdministrators.</span></span> <span data-ttu-id="625f8-225">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="625f8-225">Click **OK**.</span></span>
    
    <span data-ttu-id="625f8-226">e.i.</span><span class="sxs-lookup"><span data-stu-id="625f8-226">e.</span></span> <span data-ttu-id="625f8-227">在“**成员**”选项卡上，确认所选的用户或组存在。</span><span class="sxs-lookup"><span data-stu-id="625f8-227">On the **Members** tab, confirm that the users or groups that you selected are present.</span></span> <span data-ttu-id="625f8-228">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="625f8-228">Click **OK**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="625f8-229">Skype for Business Server "控制面板" 是基于角色的访问控制工具。</span><span class="sxs-lookup"><span data-stu-id="625f8-229">The Skype for Business Server Control Panel is a role-based access control tool.</span></span> <span data-ttu-id="625f8-230">CsAdministrator 组中的成员身份为所有可用的配置功能提供了使用 Skype for Business 服务器控制面板的 "完全控制"。</span><span class="sxs-lookup"><span data-stu-id="625f8-230">Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all configuration functions available.</span></span> <span data-ttu-id="625f8-231">还有其他为特定功能设计的专门角色可用。</span><span class="sxs-lookup"><span data-stu-id="625f8-231">There are other roles available that are designed for specific functions.</span></span> <span data-ttu-id="625f8-232">有关可用角色的详细信息，请参阅 skype for business server 2019 的[环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或 skype For business [Server 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="625f8-232">For details on the roles available, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="625f8-233">请注意，用户不必启用 Skype for Business 服务器，即可成为管理组的成员。</span><span class="sxs-lookup"><span data-stu-id="625f8-233">Note that users do not have to be enabled for Skype for Business Server in order to be made members of the management groups.</span></span> 
  
    > [!CAUTION]
    > <span data-ttu-id="625f8-234">若要帮助保留安全和基于角色的访问控制完整性，请将用户添加到定义用户在管理 Skype for Business 服务器部署时所执行的角色的组。</span><span class="sxs-lookup"><span data-stu-id="625f8-234">To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment.</span></span> 
  
11. <span data-ttu-id="625f8-235">注销，然后重新登录到 Windows，以便你的安全令牌通过新的 Skype for Business Server 安全组进行更新，然后重新打开部署向导。</span><span class="sxs-lookup"><span data-stu-id="625f8-235">Log off, and then log back on to Windows so that your security token is updated with the new Skype for Business Server security group, and then reopen the Deployment Wizard.</span></span>
    
12. <span data-ttu-id="625f8-236">验证是否在 "**准备 Active Directory** " 旁边看到绿色的复选标记以确认成功，如图所示。</span><span class="sxs-lookup"><span data-stu-id="625f8-236">Verify that you see a green checkmark next to **Prepare Active Directory** to confirm success, as shown in the figure.</span></span>
    
     ![Active Directory 准备工作已完成。](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a><span data-ttu-id="625f8-238">另请参阅</span><span class="sxs-lookup"><span data-stu-id="625f8-238">See also</span></span>
 
[<span data-ttu-id="625f8-239">Active Directory Domain Services for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="625f8-239">Active Directory Domain Services for Skype for Business Server 2015</span></span>](../../plan-your-deployment/security/active-directory-domain-services.md)
