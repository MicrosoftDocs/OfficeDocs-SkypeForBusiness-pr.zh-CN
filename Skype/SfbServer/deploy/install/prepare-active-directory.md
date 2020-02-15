---
title: 为 Skype for business Server 准备 Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: 摘要：了解如何准备 Active Directory 域以安装 Skype for business Server。 从以下位置的 Microsoft 评估中心下载 Skype for Business Server 的免费试用版https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server：。
ms.openlocfilehash: 9a17ae327322b364935d0b965676d26fdce2cffb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018173"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a><span data-ttu-id="cfb91-104">为 Skype for business Server 准备 Active Directory</span><span class="sxs-lookup"><span data-stu-id="cfb91-104">Prepare Active Directory for Skype for Business Server</span></span>
 
<span data-ttu-id="cfb91-105">**摘要：** 了解如何准备 Active Directory 域以安装 Skype for business Server。</span><span class="sxs-lookup"><span data-stu-id="cfb91-105">**Summary:** Learn how to prepare your Active Directory domain for an installation of Skype for Business Server.</span></span> <span data-ttu-id="cfb91-106">从[Microsoft 评估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)下载 Skype For business Server 的免费试用版。</span><span class="sxs-lookup"><span data-stu-id="cfb91-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="cfb91-107">Skype for Business Server 与 Active Directory 紧密协作。</span><span class="sxs-lookup"><span data-stu-id="cfb91-107">Skype for Business Server works closely with Active Directory.</span></span> <span data-ttu-id="cfb91-108">您必须准备 Active Directory 域才能与 Skype for Business Server 配合使用。</span><span class="sxs-lookup"><span data-stu-id="cfb91-108">You must prepare the Active Directory domain to work with Skype for Business Server.</span></span> <span data-ttu-id="cfb91-109">此过程在部署向导中完成，仅对域执行一次。</span><span class="sxs-lookup"><span data-stu-id="cfb91-109">This process is accomplished in the Deployment Wizard and is only done once for the domain.</span></span> <span data-ttu-id="cfb91-110">这是因为该过程会创建组并修改域，您只需执行一次此操作。</span><span class="sxs-lookup"><span data-stu-id="cfb91-110">This is because the process creates groups and modifies the domain, and you need to do that only once.</span></span> <span data-ttu-id="cfb91-111">您可以按任意顺序执行步骤1至5。</span><span class="sxs-lookup"><span data-stu-id="cfb91-111">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="cfb91-112">但是，必须按顺序执行步骤6、7和8，并在第1步至第5步之后，如图中所述。</span><span class="sxs-lookup"><span data-stu-id="cfb91-112">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="cfb91-113">准备 Active Directory 是第4步（共8步）。</span><span class="sxs-lookup"><span data-stu-id="cfb91-113">Preparing Active Directory is step 4 of 8.</span></span> <span data-ttu-id="cfb91-114">有关规划 Active Directory 的详细信息，请参阅 skype [for Business server 的环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或[Skype for business Server 2019 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cfb91-114">For more information about planning for Active Directory, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![概述图表](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a><span data-ttu-id="cfb91-116">准备 Active Directory</span><span class="sxs-lookup"><span data-stu-id="cfb91-116">Prepare Active Directory</span></span>

<span data-ttu-id="cfb91-117">Skype for Business Server 与 Active Directory 域服务（AD DS）紧密集成。</span><span class="sxs-lookup"><span data-stu-id="cfb91-117">Skype for Business Server is tightly integrated with Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="cfb91-118">在第一次可以安装 Skype for Business Server 之前，必须准备 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="cfb91-118">Before Skype for Business Server can be installed for the first time, Active Directory must be prepared.</span></span> <span data-ttu-id="cfb91-119">部署向导中名为 "**准备 Active directory** " 的部分准备 active directory 环境以用于 Skype For business Server。</span><span class="sxs-lookup"><span data-stu-id="cfb91-119">The section of the Deployment Wizard titled **Prepare Active Directory** prepares the Active Directory environment for use with Skype for Business Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cfb91-120">Skype for Business Server 使用（AD DS）跟踪拓扑中的所有服务器并与之通信。</span><span class="sxs-lookup"><span data-stu-id="cfb91-120">Skype for Business Server uses (AD DS) to track and communicate with all of the servers in a topology.</span></span> <span data-ttu-id="cfb91-121">这些服务器中的大多数必须加入域，以便 Skype for Business Server 能够正常工作。</span><span class="sxs-lookup"><span data-stu-id="cfb91-121">The majority of these servers must be joined to the domain so that Skype for Business Server can work properly.</span></span> <span data-ttu-id="cfb91-122">请注意，边缘和反向代理等服务器不应加入域。</span><span class="sxs-lookup"><span data-stu-id="cfb91-122">Keep in mind that servers such as Edge and Reverse Proxy should not be domain joined.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="cfb91-123">对于部署中的每个域，应仅运行一次 "准备 Active Directory" 过程。</span><span class="sxs-lookup"><span data-stu-id="cfb91-123">The Prepare Active Directory procedure should be run only once for each domain in the deployment.</span></span> 
  
<span data-ttu-id="cfb91-124">观看**准备 Active Directory**的视频步骤：</span><span class="sxs-lookup"><span data-stu-id="cfb91-124">Watch the video steps for **Prepare Active Directory**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a><span data-ttu-id="cfb91-125">通过部署向导准备 Active Directory</span><span class="sxs-lookup"><span data-stu-id="cfb91-125">Prepare Active Directory from the Deployment Wizard</span></span>

1. <span data-ttu-id="cfb91-126">以具有 Active Directory 域的架构管理员凭据的用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="cfb91-126">Log on as a user with Schema Admins credentials for the Active Directory domain.</span></span>
    
2. <span data-ttu-id="cfb91-127">打开 Skype for Business Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="cfb91-127">Open Skype for Business Server Deployment Wizard.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="cfb91-128">如果要查看由 Skype for Business Server 部署向导创建的日志文件，可以在运行此步骤的 AD DS 用户的用户目录中的 "部署向导" 所在的计算机上找到这些文件。</span><span class="sxs-lookup"><span data-stu-id="cfb91-128">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the AD DS user who ran the step.</span></span> <span data-ttu-id="cfb91-129">例如，如果用户以域管理员的身份登录到本地域，则日志文件位于： C:\Users\Administrator.Contoso\AppData\Local\Temp。</span><span class="sxs-lookup"><span data-stu-id="cfb91-129">For example, if the user logged on as the domain administrator in the domain, contoso.local, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span> 
  
3. <span data-ttu-id="cfb91-130">单击 "**准备 Active Directory** " 链接。</span><span class="sxs-lookup"><span data-stu-id="cfb91-130">Click the **Prepare Active Directory** link.</span></span>
    
4. <span data-ttu-id="cfb91-131">**步骤1：准备架构**</span><span class="sxs-lookup"><span data-stu-id="cfb91-131">**Step 1: Prepare schema**</span></span>
    
    <span data-ttu-id="cfb91-132">a.</span><span class="sxs-lookup"><span data-stu-id="cfb91-132">a.</span></span> <span data-ttu-id="cfb91-133">查看步骤1的先决条件信息，可通过单击 "步骤 1" 标题下的下拉箭头来访问。</span><span class="sxs-lookup"><span data-stu-id="cfb91-133">Review the prerequisites information for Step 1 which can be accessed by clicking the drop-down under the Step 1 title.</span></span>
    
    <span data-ttu-id="cfb91-134">b.</span><span class="sxs-lookup"><span data-stu-id="cfb91-134">b.</span></span> <span data-ttu-id="cfb91-135">单击步骤1中的 "**运行**" 以启动 "准备架构" 向导。</span><span class="sxs-lookup"><span data-stu-id="cfb91-135">Click **Run** in Step 1 to launch the Prepare Schema wizard.</span></span>
    
    <span data-ttu-id="cfb91-136">c.</span><span class="sxs-lookup"><span data-stu-id="cfb91-136">c.</span></span> <span data-ttu-id="cfb91-137">请注意，每个部署应仅运行一次该过程，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="cfb91-137">Take note that the procedure should be run only once for each deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="cfb91-138">d.</span><span class="sxs-lookup"><span data-stu-id="cfb91-138">d.</span></span> <span data-ttu-id="cfb91-139">准备好架构后，可以通过单击 "**查看日志**" 来查看日志。</span><span class="sxs-lookup"><span data-stu-id="cfb91-139">Once the schema has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="cfb91-140">e.</span><span class="sxs-lookup"><span data-stu-id="cfb91-140">e.</span></span> <span data-ttu-id="cfb91-141">单击 "**完成**" 以关闭 "准备架构" 向导，然后返回到 "准备 Active Directory" 步骤。</span><span class="sxs-lookup"><span data-stu-id="cfb91-141">Click **Finish** to close the Prepare Schema wizard, and return to the Prepare Active Directory steps.</span></span>
    
5. <span data-ttu-id="cfb91-142">**步骤2：验证架构分区的复制**</span><span class="sxs-lookup"><span data-stu-id="cfb91-142">**Step 2: Verify replication of schema partition**</span></span>
    
    <span data-ttu-id="cfb91-143">a.</span><span class="sxs-lookup"><span data-stu-id="cfb91-143">a.</span></span> <span data-ttu-id="cfb91-144">登录到域的域控制器。</span><span class="sxs-lookup"><span data-stu-id="cfb91-144">Log on to the domain controller for the domain.</span></span>
    
    <span data-ttu-id="cfb91-145">b.</span><span class="sxs-lookup"><span data-stu-id="cfb91-145">b.</span></span> <span data-ttu-id="cfb91-146">从 "**服务器管理器**" 的 "**工具**" 下拉菜单中打开 " **ADSI 编辑**"。</span><span class="sxs-lookup"><span data-stu-id="cfb91-146">Open **ADSI Edit** from the **Tools** drop-down menu in **Server Manager**.</span></span>
    
    <span data-ttu-id="cfb91-147">c.</span><span class="sxs-lookup"><span data-stu-id="cfb91-147">c.</span></span> <span data-ttu-id="cfb91-148">在 **“操作”** 菜单上，单击 **“连接到”**。</span><span class="sxs-lookup"><span data-stu-id="cfb91-148">On the **Action** menu, click **Connect to**.</span></span>
    
    <span data-ttu-id="cfb91-149">d.</span><span class="sxs-lookup"><span data-stu-id="cfb91-149">d.</span></span> <span data-ttu-id="cfb91-150">在 **“连接设置”** 对话框中的 **“选择一个已知命名上下文”** 下，选择 **“架构”**，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="cfb91-150">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
    <span data-ttu-id="cfb91-151">e.</span><span class="sxs-lookup"><span data-stu-id="cfb91-151">e.</span></span> <span data-ttu-id="cfb91-152">在 "架构" 容器下，搜索 " **CN = ms-SIP-SchemaVersion**"。</span><span class="sxs-lookup"><span data-stu-id="cfb91-152">Under the schema container, search for **CN=ms-RTC-SIP-SchemaVersion**.</span></span> <span data-ttu-id="cfb91-153">如果该对象存在，并且**rangeUpper**属性的值为1150，并且**rangeLower**属性的值为3，则该架构已成功更新和复制。</span><span class="sxs-lookup"><span data-stu-id="cfb91-153">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, the schema was successfully updated and replicated.</span></span> <span data-ttu-id="cfb91-154">如果此对象不存在，或者**rangeUpper**和**rangeLower**属性的值不是指定的，则不会修改架构或未对其进行复制。</span><span class="sxs-lookup"><span data-stu-id="cfb91-154">If this object does not exist or the values of the **rangeUpper** and **rangeLower** attributes are not as specified, the schema was not modified or has not replicated.</span></span>
    
6. <span data-ttu-id="cfb91-155">**步骤3：准备当前林**</span><span class="sxs-lookup"><span data-stu-id="cfb91-155">**Step 3: Prepare current forest**</span></span>
    
    <span data-ttu-id="cfb91-156">a.</span><span class="sxs-lookup"><span data-stu-id="cfb91-156">a.</span></span> <span data-ttu-id="cfb91-157">查看步骤3的先决条件信息，可通过单击步骤3标题下的下拉菜单访问该信息。</span><span class="sxs-lookup"><span data-stu-id="cfb91-157">Review the prerequisites information for Step 3 which can be accessed by clicking the drop-down under the Step 3 title.</span></span>
    
    <span data-ttu-id="cfb91-158">b.</span><span class="sxs-lookup"><span data-stu-id="cfb91-158">b.</span></span> <span data-ttu-id="cfb91-159">单击步骤3中的 "**运行**" 以启动 "准备当前林" 向导。</span><span class="sxs-lookup"><span data-stu-id="cfb91-159">Click **Run** in Step 3 to launch the Prepare Current Forest wizard.</span></span>
    
    <span data-ttu-id="cfb91-160">c.</span><span class="sxs-lookup"><span data-stu-id="cfb91-160">c.</span></span> <span data-ttu-id="cfb91-161">请注意，每个部署的过程应仅运行一次，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="cfb91-161">Take note that the procedure should be only run once per deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="cfb91-162">d.</span><span class="sxs-lookup"><span data-stu-id="cfb91-162">d.</span></span> <span data-ttu-id="cfb91-163">指定将在其中创建通用组的域。</span><span class="sxs-lookup"><span data-stu-id="cfb91-163">Specify the domain where the universal groups will be created.</span></span> <span data-ttu-id="cfb91-164">如果服务器是域的一部分，则可以选择 "**本地域**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="cfb91-164">If the server is part of the domain, you can choose **Local domain**, and click **Next**.</span></span>
    
    <span data-ttu-id="cfb91-165">e.</span><span class="sxs-lookup"><span data-stu-id="cfb91-165">e.</span></span> <span data-ttu-id="cfb91-166">准备好林后，可以通过单击 "**查看日志**" 来查看日志。</span><span class="sxs-lookup"><span data-stu-id="cfb91-166">Once the forest has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="cfb91-167">f.</span><span class="sxs-lookup"><span data-stu-id="cfb91-167">f.</span></span> <span data-ttu-id="cfb91-168">单击 "**完成**" 以关闭 "准备当前林" 向导，然后返回到 "准备 Active Directory" 步骤。</span><span class="sxs-lookup"><span data-stu-id="cfb91-168">Click **Finish** to close the Prepare Current Forest wizard, and return to the Prepare Active Directory steps.</span></span>
    
    <span data-ttu-id="cfb91-169">g.</span><span class="sxs-lookup"><span data-stu-id="cfb91-169">g.</span></span> <span data-ttu-id="cfb91-170">从 "**应用程序**" 页上单击 " **Skype For Business Server Management Shell** " 以启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="cfb91-170">Click **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.</span></span>
    
    <span data-ttu-id="cfb91-171">水平.</span><span class="sxs-lookup"><span data-stu-id="cfb91-171">h.</span></span> <span data-ttu-id="cfb91-172">键入命令 CsAdForest，然后按**enter**。</span><span class="sxs-lookup"><span data-stu-id="cfb91-172">Type the command Get-CsAdForest, and press **Enter**.</span></span>
    
    <span data-ttu-id="cfb91-173">得到.</span><span class="sxs-lookup"><span data-stu-id="cfb91-173">i.</span></span> <span data-ttu-id="cfb91-174">如果结果是**LC_FORESTSETTINGS_STATE_READY**的，则表示已成功准备林，如图所示。</span><span class="sxs-lookup"><span data-stu-id="cfb91-174">If the result is **LC_FORESTSETTINGS_STATE_READY**, the forest has successfully been prepared, as shown in the figure.</span></span>
    
     ![验证林复制。](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. <span data-ttu-id="cfb91-176">**步骤4：验证全局编录的复制**</span><span class="sxs-lookup"><span data-stu-id="cfb91-176">**Step 4: Verify replication of the global catalog**</span></span>
    
    <span data-ttu-id="cfb91-177">a.</span><span class="sxs-lookup"><span data-stu-id="cfb91-177">a.</span></span> <span data-ttu-id="cfb91-178">在域控制器上（最好是在来自其他域控制器的远程站点中），在运行林准备的林中，打开 " **Active Directory 用户和计算机**"。</span><span class="sxs-lookup"><span data-stu-id="cfb91-178">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
    <span data-ttu-id="cfb91-179">b.</span><span class="sxs-lookup"><span data-stu-id="cfb91-179">b.</span></span> <span data-ttu-id="cfb91-180">在 **“Active Directory 用户和计算机”** 中，展开林或子域的域名。</span><span class="sxs-lookup"><span data-stu-id="cfb91-180">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
    <span data-ttu-id="cfb91-181">c.</span><span class="sxs-lookup"><span data-stu-id="cfb91-181">c.</span></span> <span data-ttu-id="cfb91-182">单击左侧窗格中的 "**用户**" 容器，然后在右侧窗格中查找通用组**CsAdministrator** 。</span><span class="sxs-lookup"><span data-stu-id="cfb91-182">Click the **Users** container on the left side pane, and look for the Universal group **CsAdministrator** in the right side pane.</span></span> <span data-ttu-id="cfb91-183">如果 CsAdministrator （与以 Cs 开头的其他新通用组）存在，则表明 Active Directory 已成功复制。</span><span class="sxs-lookup"><span data-stu-id="cfb91-183">If CsAdministrator (among other new Universal groups that begin with Cs) is present, Active Directory replication has been successful.</span></span>
    
    <span data-ttu-id="cfb91-184">d.</span><span class="sxs-lookup"><span data-stu-id="cfb91-184">d.</span></span> <span data-ttu-id="cfb91-185">如果这些组尚不存在，则可以强制进行复制，或等待15分钟并刷新右侧窗格。</span><span class="sxs-lookup"><span data-stu-id="cfb91-185">If the groups are not yet present, you can force the replication, or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="cfb91-186">显示组后，表明复制完成。</span><span class="sxs-lookup"><span data-stu-id="cfb91-186">When the groups are present, replication is complete.</span></span>
    
8. <span data-ttu-id="cfb91-187">**步骤5：准备当前域**</span><span class="sxs-lookup"><span data-stu-id="cfb91-187">**Step 5: Prepare the current domain**</span></span>
    
    <span data-ttu-id="cfb91-188">a.</span><span class="sxs-lookup"><span data-stu-id="cfb91-188">a.</span></span> <span data-ttu-id="cfb91-189">查看步骤5的先决条件信息。</span><span class="sxs-lookup"><span data-stu-id="cfb91-189">Review the prerequisites information for Step 5.</span></span>
    
    <span data-ttu-id="cfb91-190">b.</span><span class="sxs-lookup"><span data-stu-id="cfb91-190">b.</span></span> <span data-ttu-id="cfb91-191">单击步骤5中的 "**运行**" 以启动 "准备当前域" 向导。</span><span class="sxs-lookup"><span data-stu-id="cfb91-191">Click **Run** in Step 5 to launch the Prepare Current Domain wizard.</span></span>
    
    <span data-ttu-id="cfb91-192">c.</span><span class="sxs-lookup"><span data-stu-id="cfb91-192">c.</span></span> <span data-ttu-id="cfb91-193">请注意，应仅为部署中的每个域运行一次该过程，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="cfb91-193">Take note that the procedure should only be run once for each domain in the deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="cfb91-194">d.</span><span class="sxs-lookup"><span data-stu-id="cfb91-194">d.</span></span> <span data-ttu-id="cfb91-195">准备好域后，可以通过单击 "**查看日志**" 来查看日志。</span><span class="sxs-lookup"><span data-stu-id="cfb91-195">Once the domain has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="cfb91-196">e.</span><span class="sxs-lookup"><span data-stu-id="cfb91-196">e.</span></span> <span data-ttu-id="cfb91-197">单击 "**完成**" 关闭 "准备当前域" 向导，然后返回 "准备 Active Directory" 步骤。</span><span class="sxs-lookup"><span data-stu-id="cfb91-197">Click **Finish** to close the Prepare Current Domain wizard, and return to the Prepare Active Directory steps.</span></span>
    
    <span data-ttu-id="cfb91-198">必须在找到 Skype for Business Server 对象的每个域中完成这些步骤，否则服务可能无法启动。</span><span class="sxs-lookup"><span data-stu-id="cfb91-198">These steps must be completed in every domain where Skype for Business Server objects are found, otherwise services might not start.</span></span> <span data-ttu-id="cfb91-199">这包括任何类型的 Active Directory 对象，例如用户、联系人对象、管理组或任何其他类型的对象。</span><span class="sxs-lookup"><span data-stu-id="cfb91-199">This includes any type of Active Directory object, such as users, contact objects, administrative groups, or any other type of object.</span></span> <span data-ttu-id="cfb91-200">如果需要，可以使用 CsUserReplicatorConfiguration-ADDomainNamingContextList 仅添加具有 Skype for business Server 对象的域。</span><span class="sxs-lookup"><span data-stu-id="cfb91-200">You can use Set-CsUserReplicatorConfiguration -ADDomainNamingContextList to add only the domains with Skype for Business Server objects, if needed.</span></span>
    
9. <span data-ttu-id="cfb91-201">**步骤6：验证域中的复制**</span><span class="sxs-lookup"><span data-stu-id="cfb91-201">**Step 6: Verify replication in the domain**</span></span>
    
    <span data-ttu-id="cfb91-202">a.</span><span class="sxs-lookup"><span data-stu-id="cfb91-202">a.</span></span> <span data-ttu-id="cfb91-203">单击 "**应用程序**" 页上的 " **Skype For Business Server Management Shell** " 以启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="cfb91-203">Click the **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.</span></span>
    
    <span data-ttu-id="cfb91-204">b.</span><span class="sxs-lookup"><span data-stu-id="cfb91-204">b.</span></span> <span data-ttu-id="cfb91-205">使用命令 CsAdDomain 验证域中的复制。</span><span class="sxs-lookup"><span data-stu-id="cfb91-205">Use the command Get-CsAdDomain to verify replication within the domain.</span></span>
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > <span data-ttu-id="cfb91-206">如果不指定 Domain 参数，则将该值设置为本地域。</span><span class="sxs-lookup"><span data-stu-id="cfb91-206">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> 
  
    <span data-ttu-id="cfb91-207">为 contoso. 本地域运行命令的示例：</span><span class="sxs-lookup"><span data-stu-id="cfb91-207">Example of running the command for the contoso.local domain:</span></span>
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > <span data-ttu-id="cfb91-208">通过使用参数 GlobalSettingsDomainController，可以指示存储全局设置的位置。</span><span class="sxs-lookup"><span data-stu-id="cfb91-208">By using the parameter GlobalSettingsDomainController, you can indicate where global settings are stored.</span></span> <span data-ttu-id="cfb91-209">如果您的设置存储在系统容器中（这对于不将全局设置迁移到配置容器的升级部署来说很典型），则需要在 AD DS 林的根目录中定义域控制器。</span><span class="sxs-lookup"><span data-stu-id="cfb91-209">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your AD DS forest.</span></span> <span data-ttu-id="cfb91-210">如果全局设置存储在“配置”容器中（通常在新部署或设置已迁移到“配置”容器的升级部署中是这种情况），则定义林中的任何域控制器。</span><span class="sxs-lookup"><span data-stu-id="cfb91-210">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="cfb91-211">如果不指定此参数，则 cmdlet 假定设置存储在配置容器中，并引用 Active Directory 中的任何域控制器。</span><span class="sxs-lookup"><span data-stu-id="cfb91-211">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="cfb91-212">c.</span><span class="sxs-lookup"><span data-stu-id="cfb91-212">c.</span></span> <span data-ttu-id="cfb91-213">如果结果是**LC_DOMAINSETTINGS_STATE_READY**的，则域已成功复制。</span><span class="sxs-lookup"><span data-stu-id="cfb91-213">If the result is **LC_DOMAINSETTINGS_STATE_READY**, the domain has successfully replicated.</span></span>
    
10. <span data-ttu-id="cfb91-214">**步骤7：添加用户以提供对 Skype for business Server 控制面板的管理访问权限**</span><span class="sxs-lookup"><span data-stu-id="cfb91-214">**Step 7: Add users to provide administrative access to the Skype for Business Server Control Panel**</span></span>
    
    <span data-ttu-id="cfb91-215">a.</span><span class="sxs-lookup"><span data-stu-id="cfb91-215">a.</span></span> <span data-ttu-id="cfb91-216">以 Domain Admins 组或 RTCUniversalServerAdmins 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="cfb91-216">Log on as a member of the Domain Admins group or the RTCUniversalServerAdmins group.</span></span>
    
    <span data-ttu-id="cfb91-217">b.</span><span class="sxs-lookup"><span data-stu-id="cfb91-217">b.</span></span> <span data-ttu-id="cfb91-218">打开 " **Active Directory 用户和计算机**"，展开您的域，单击 "**用户**" 容器，右键单击 "CSAdministrator"，然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="cfb91-218">Open **Active Directory Users and Computers**, expand your domain, click the **Users** container, right-click CSAdministrator, and choose **Properties**.</span></span>
    
    <span data-ttu-id="cfb91-219">c.</span><span class="sxs-lookup"><span data-stu-id="cfb91-219">c.</span></span> <span data-ttu-id="cfb91-220">在“CSAdministrator 属性”\*\*\*\* 中，单击“成员”\*\*\*\* 选项卡。</span><span class="sxs-lookup"><span data-stu-id="cfb91-220">In **CSAdministrator Properties**, click the **Members** tab.</span></span>
    
    <span data-ttu-id="cfb91-221">d.</span><span class="sxs-lookup"><span data-stu-id="cfb91-221">d.</span></span> <span data-ttu-id="cfb91-222">在"成员"选项卡上，单击"添加"。</span><span class="sxs-lookup"><span data-stu-id="cfb91-222">On the **Members** tab, click **Add**.</span></span> <span data-ttu-id="cfb91-223">在“选择用户、联系人、计算机、服务帐户或组”\*\*\*\* 中，找到“输入要选择的对象名称”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cfb91-223">In **Select Users, Contacts, Computers, Service Accounts, or Groups**, locate the **Enter the object names to select**.</span></span> <span data-ttu-id="cfb91-224">键入要添加到 CSAdministrators 组的用户名或组名。</span><span class="sxs-lookup"><span data-stu-id="cfb91-224">Type the user name(s) or group name(s) to add to the group CSAdministrators.</span></span> <span data-ttu-id="cfb91-225">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cfb91-225">Click **OK**.</span></span>
    
    <span data-ttu-id="cfb91-226">e.</span><span class="sxs-lookup"><span data-stu-id="cfb91-226">e.</span></span> <span data-ttu-id="cfb91-227">在 "**成员**" 选项卡上，确认所选的用户或组存在。</span><span class="sxs-lookup"><span data-stu-id="cfb91-227">On the **Members** tab, confirm that the users or groups that you selected are present.</span></span> <span data-ttu-id="cfb91-228">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="cfb91-228">Click **OK**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="cfb91-229">Skype for Business Server 控制面板是基于角色的访问控制工具。</span><span class="sxs-lookup"><span data-stu-id="cfb91-229">The Skype for Business Server Control Panel is a role-based access control tool.</span></span> <span data-ttu-id="cfb91-230">CsAdministrator 组中的成员身份为所有可用的配置功能提供了使用 Skype for Business Server 控制面板的 "完全控制" 权限的用户。</span><span class="sxs-lookup"><span data-stu-id="cfb91-230">Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all configuration functions available.</span></span> <span data-ttu-id="cfb91-231">为特定功能提供了其他专门的角色。</span><span class="sxs-lookup"><span data-stu-id="cfb91-231">There are other roles available that are designed for specific functions.</span></span> <span data-ttu-id="cfb91-232">有关可用角色的详细信息，请参阅 skype for business [server 的环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或[Skype for business Server 2019 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cfb91-232">For details on the roles available, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="cfb91-233">请注意，无需为 Skype for business Server 启用用户即可成为管理组的成员。</span><span class="sxs-lookup"><span data-stu-id="cfb91-233">Note that users do not have to be enabled for Skype for Business Server in order to be made members of the management groups.</span></span> 
  
    > [!CAUTION]
    > <span data-ttu-id="cfb91-234">若要帮助保留安全性和基于角色的访问控制完整性，请将用户添加到定义了用户在管理 Skype for Business Server 部署时所执行的角色的组。</span><span class="sxs-lookup"><span data-stu-id="cfb91-234">To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment.</span></span> 
  
11. <span data-ttu-id="cfb91-235">注销，然后重新登录到 Windows，以便使用新的 Skype for Business Server 安全组更新您的安全令牌，然后重新打开部署向导。</span><span class="sxs-lookup"><span data-stu-id="cfb91-235">Log off, and then log back on to Windows so that your security token is updated with the new Skype for Business Server security group, and then reopen the Deployment Wizard.</span></span>
    
12. <span data-ttu-id="cfb91-236">验证您是否在**准备 Active Directory**以确认成功时看到一个绿色的标记，如图所示。</span><span class="sxs-lookup"><span data-stu-id="cfb91-236">Verify that you see a green checkmark next to **Prepare Active Directory** to confirm success, as shown in the figure.</span></span>
    
     ![准备 Active Directory 已完成。](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a><span data-ttu-id="cfb91-238">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cfb91-238">See also</span></span>
 
[<span data-ttu-id="cfb91-239">适用于 Skype for business Server 2015 的 Active Directory 域服务</span><span class="sxs-lookup"><span data-stu-id="cfb91-239">Active Directory Domain Services for Skype for Business Server 2015</span></span>](../../plan-your-deployment/security/active-directory-domain-services.md)
