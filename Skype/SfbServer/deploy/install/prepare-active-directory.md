---
title: 为 Skype for Business Server 准备 Active Directory
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 摘要：了解如何为安装 Skype for Business Server 准备 Active Directory 域。 从 Microsoft 评估中心下载 Skype for Business Server 的免费试用版， https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 位置为：
ms.openlocfilehash: 6196855ffeaf33fbea11c47d56c620e3df9195ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801672"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a><span data-ttu-id="38778-104">为 Skype for Business Server 准备 Active Directory</span><span class="sxs-lookup"><span data-stu-id="38778-104">Prepare Active Directory for Skype for Business Server</span></span>
 
<span data-ttu-id="38778-105">**摘要：** 了解如何为安装 Skype for Business Server 准备 Active Directory 域。</span><span class="sxs-lookup"><span data-stu-id="38778-105">**Summary:** Learn how to prepare your Active Directory domain for an installation of Skype for Business Server.</span></span> <span data-ttu-id="38778-106">从 Microsoft 评估中心下载 Skype for Business Server [的免费试用版](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="38778-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="38778-107">Skype for Business Server 与 Active Directory 紧密配合。</span><span class="sxs-lookup"><span data-stu-id="38778-107">Skype for Business Server works closely with Active Directory.</span></span> <span data-ttu-id="38778-108">必须准备 Active Directory 域以使用 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="38778-108">You must prepare the Active Directory domain to work with Skype for Business Server.</span></span> <span data-ttu-id="38778-109">此过程在部署向导中完成，并且仅对域执行一次。</span><span class="sxs-lookup"><span data-stu-id="38778-109">This process is accomplished in the Deployment Wizard and is only done once for the domain.</span></span> <span data-ttu-id="38778-110">这是因为该过程将创建组并修改域，并且只需执行一次此操作。</span><span class="sxs-lookup"><span data-stu-id="38778-110">This is because the process creates groups and modifies the domain, and you need to do that only once.</span></span> <span data-ttu-id="38778-111">可以按任意顺序执行步骤 1 到步骤 5。</span><span class="sxs-lookup"><span data-stu-id="38778-111">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="38778-112">但是，您必须按顺序执行步骤 6、7 和 8，在步骤 1 到 5 之后，如图中所述。</span><span class="sxs-lookup"><span data-stu-id="38778-112">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="38778-113">准备 Active Directory 是步骤 4/8。</span><span class="sxs-lookup"><span data-stu-id="38778-113">Preparing Active Directory is step 4 of 8.</span></span> <span data-ttu-id="38778-114">有关规划 Active Directory 的信息，请参阅 [Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 的环境要求或 Skype for Business Server [2019 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="38778-114">For more information about planning for Active Directory, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![概述图表](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a><span data-ttu-id="38778-116">准备 Active Directory</span><span class="sxs-lookup"><span data-stu-id="38778-116">Prepare Active Directory</span></span>

<span data-ttu-id="38778-117">Skype for Business Server 与 Active Directory 域服务 (AD DS) 。</span><span class="sxs-lookup"><span data-stu-id="38778-117">Skype for Business Server is tightly integrated with Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="38778-118">必须先准备 Active Directory，然后才能首次安装 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="38778-118">Before Skype for Business Server can be installed for the first time, Active Directory must be prepared.</span></span> <span data-ttu-id="38778-119">部署向导中标题为 **"准备 Active Directory"** 的部分准备 Active Directory 环境以用于 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="38778-119">The section of the Deployment Wizard titled **Prepare Active Directory** prepares the Active Directory environment for use with Skype for Business Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="38778-120">Skype for Business Server (AD DS) 跟踪拓扑中所有服务器并进行通信。</span><span class="sxs-lookup"><span data-stu-id="38778-120">Skype for Business Server uses (AD DS) to track and communicate with all of the servers in a topology.</span></span> <span data-ttu-id="38778-121">这些服务器中的大多数必须加入域，Skype for Business Server 才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="38778-121">The majority of these servers must be joined to the domain so that Skype for Business Server can work properly.</span></span> <span data-ttu-id="38778-122">请记住，边缘和反向代理等服务器不应加入域。</span><span class="sxs-lookup"><span data-stu-id="38778-122">Keep in mind that servers such as Edge and Reverse Proxy should not be domain joined.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="38778-123">应仅为部署中的每个域运行一次"准备 Active Directory"过程。</span><span class="sxs-lookup"><span data-stu-id="38778-123">The Prepare Active Directory procedure should be run only once for each domain in the deployment.</span></span> 
  
<span data-ttu-id="38778-124">观看准备 Active **Directory 的视频步骤**：</span><span class="sxs-lookup"><span data-stu-id="38778-124">Watch the video steps for **Prepare Active Directory**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a><span data-ttu-id="38778-125">从部署向导准备 Active Directory</span><span class="sxs-lookup"><span data-stu-id="38778-125">Prepare Active Directory from the Deployment Wizard</span></span>

1. <span data-ttu-id="38778-126">以具有 Active Directory 域的架构管理员凭据的用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="38778-126">Log on as a user with Schema Admins credentials for the Active Directory domain.</span></span>
    
2. <span data-ttu-id="38778-127">打开 Skype for Business Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="38778-127">Open Skype for Business Server Deployment Wizard.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="38778-128">如果要查看由 Skype for Business Server 部署向导创建的日志文件，可以在运行部署向导的计算机上找到这些文件，位于运行该步骤的 AD DS 用户的 Users 目录中。</span><span class="sxs-lookup"><span data-stu-id="38778-128">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the AD DS user who ran the step.</span></span> <span data-ttu-id="38778-129">例如，如果用户以域 contoso.local 的域管理员身份登录，日志文件位于：C：\Users\Administrator.Contoso\AppData\Local\Temp。</span><span class="sxs-lookup"><span data-stu-id="38778-129">For example, if the user logged on as the domain administrator in the domain, contoso.local, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span> 
  
3. <span data-ttu-id="38778-130">单击 **"准备 Active Directory"** 链接。</span><span class="sxs-lookup"><span data-stu-id="38778-130">Click the **Prepare Active Directory** link.</span></span>
    
4. <span data-ttu-id="38778-131">**步骤 1：准备架构**</span><span class="sxs-lookup"><span data-stu-id="38778-131">**Step 1: Prepare schema**</span></span>
    
    <span data-ttu-id="38778-132">a.</span><span class="sxs-lookup"><span data-stu-id="38778-132">a.</span></span> <span data-ttu-id="38778-133">查看步骤 1 的先决条件信息，可通过单击步骤 1 标题下的下拉列表来访问该信息。</span><span class="sxs-lookup"><span data-stu-id="38778-133">Review the prerequisites information for Step 1 which can be accessed by clicking the drop-down under the Step 1 title.</span></span>
    
    <span data-ttu-id="38778-134">b.</span><span class="sxs-lookup"><span data-stu-id="38778-134">b.</span></span> <span data-ttu-id="38778-135">单击 **步骤** 1 中的"运行"以启动"准备架构"向导。</span><span class="sxs-lookup"><span data-stu-id="38778-135">Click **Run** in Step 1 to launch the Prepare Schema wizard.</span></span>
    
    <span data-ttu-id="38778-136">c.</span><span class="sxs-lookup"><span data-stu-id="38778-136">c.</span></span> <span data-ttu-id="38778-137">请注意，对于每个部署，该过程应只运行一次，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="38778-137">Take note that the procedure should be run only once for each deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="38778-138">d.</span><span class="sxs-lookup"><span data-stu-id="38778-138">d.</span></span> <span data-ttu-id="38778-139">准备好架构后，可以通过单击"查看日志" **来查看日志**。</span><span class="sxs-lookup"><span data-stu-id="38778-139">Once the schema has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="38778-140">e.</span><span class="sxs-lookup"><span data-stu-id="38778-140">e.</span></span> <span data-ttu-id="38778-141">单击 **"** 完成"关闭"准备架构"向导，然后返回到"准备 Active Directory"步骤。</span><span class="sxs-lookup"><span data-stu-id="38778-141">Click **Finish** to close the Prepare Schema wizard, and return to the Prepare Active Directory steps.</span></span>
    
5. <span data-ttu-id="38778-142">**步骤 2：验证架构分区的复制**</span><span class="sxs-lookup"><span data-stu-id="38778-142">**Step 2: Verify replication of schema partition**</span></span>
    
    <span data-ttu-id="38778-143">a.</span><span class="sxs-lookup"><span data-stu-id="38778-143">a.</span></span> <span data-ttu-id="38778-144">登录到域的域控制器。</span><span class="sxs-lookup"><span data-stu-id="38778-144">Log on to the domain controller for the domain.</span></span>
    
    <span data-ttu-id="38778-145">b.</span><span class="sxs-lookup"><span data-stu-id="38778-145">b.</span></span> <span data-ttu-id="38778-146">从 **服务器管理器** 中的"工具"下拉菜单中打开 ADSI **编辑**。</span><span class="sxs-lookup"><span data-stu-id="38778-146">Open **ADSI Edit** from the **Tools** drop-down menu in **Server Manager**.</span></span>
    
    <span data-ttu-id="38778-147">c.</span><span class="sxs-lookup"><span data-stu-id="38778-147">c.</span></span> <span data-ttu-id="38778-148">在 **“操作”** 菜单上，单击 **“连接到”**。</span><span class="sxs-lookup"><span data-stu-id="38778-148">On the **Action** menu, click **Connect to**.</span></span>
    
    <span data-ttu-id="38778-149">d.</span><span class="sxs-lookup"><span data-stu-id="38778-149">d.</span></span> <span data-ttu-id="38778-150">在 **“连接设置”** 对话框中的 **“选择一个已知命名上下文”** 下，选择 **“架构”**，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="38778-150">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
    <span data-ttu-id="38778-151">e.</span><span class="sxs-lookup"><span data-stu-id="38778-151">e.</span></span> <span data-ttu-id="38778-152">在架构容器下，搜索 **CN=ms-RTC-SIP-SchemaVersion。**</span><span class="sxs-lookup"><span data-stu-id="38778-152">Under the schema container, search for **CN=ms-RTC-SIP-SchemaVersion**.</span></span> <span data-ttu-id="38778-153">如果此对象存在，**并且 rangeUpper** 属性的值为 1150，rangeLower 属性的值为 3，则架构已成功更新和复制。</span><span class="sxs-lookup"><span data-stu-id="38778-153">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, the schema was successfully updated and replicated.</span></span> <span data-ttu-id="38778-154">如果此对象不存在，或者 **rangeUpper 和** **rangeLower** 属性的值未指定，则说明架构未修改或尚未复制。</span><span class="sxs-lookup"><span data-stu-id="38778-154">If this object does not exist or the values of the **rangeUpper** and **rangeLower** attributes are not as specified, the schema was not modified or has not replicated.</span></span>
    
6. <span data-ttu-id="38778-155">**步骤 3：准备当前林**</span><span class="sxs-lookup"><span data-stu-id="38778-155">**Step 3: Prepare current forest**</span></span>
    
    <span data-ttu-id="38778-156">a.</span><span class="sxs-lookup"><span data-stu-id="38778-156">a.</span></span> <span data-ttu-id="38778-157">查看步骤 3 的先决条件信息，可通过单击步骤 3 标题下的下拉列表来访问该信息。</span><span class="sxs-lookup"><span data-stu-id="38778-157">Review the prerequisites information for Step 3 which can be accessed by clicking the drop-down under the Step 3 title.</span></span>
    
    <span data-ttu-id="38778-158">b.</span><span class="sxs-lookup"><span data-stu-id="38778-158">b.</span></span> <span data-ttu-id="38778-159">单击 **步骤** 3 中的"运行"以启动"准备当前林"向导。</span><span class="sxs-lookup"><span data-stu-id="38778-159">Click **Run** in Step 3 to launch the Prepare Current Forest wizard.</span></span>
    
    <span data-ttu-id="38778-160">c.</span><span class="sxs-lookup"><span data-stu-id="38778-160">c.</span></span> <span data-ttu-id="38778-161">请注意，每个部署只能运行一次该过程，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="38778-161">Take note that the procedure should be only run once per deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="38778-162">d.</span><span class="sxs-lookup"><span data-stu-id="38778-162">d.</span></span> <span data-ttu-id="38778-163">指定将在其中创建通用组的域。</span><span class="sxs-lookup"><span data-stu-id="38778-163">Specify the domain where the universal groups will be created.</span></span> <span data-ttu-id="38778-164">如果服务器是域的一部分，可以选择"本地 **域**"，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="38778-164">If the server is part of the domain, you can choose **Local domain**, and click **Next**.</span></span>
    
    <span data-ttu-id="38778-165">e.</span><span class="sxs-lookup"><span data-stu-id="38778-165">e.</span></span> <span data-ttu-id="38778-166">准备好林后，可以通过单击"查看日志" **来查看日志**。</span><span class="sxs-lookup"><span data-stu-id="38778-166">Once the forest has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="38778-167">f.</span><span class="sxs-lookup"><span data-stu-id="38778-167">f.</span></span> <span data-ttu-id="38778-168">单击 **"** 完成"以关闭"准备当前林"向导，然后返回到"准备 Active Directory"步骤。</span><span class="sxs-lookup"><span data-stu-id="38778-168">Click **Finish** to close the Prepare Current Forest wizard, and return to the Prepare Active Directory steps.</span></span>
    
    <span data-ttu-id="38778-169">g.</span><span class="sxs-lookup"><span data-stu-id="38778-169">g.</span></span> <span data-ttu-id="38778-170">从 **"应用"页单击 Skype for Business Server** 命令行管理程序 以启动 PowerShell。 </span><span class="sxs-lookup"><span data-stu-id="38778-170">Click **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.</span></span>
    
    <span data-ttu-id="38778-171">h.</span><span class="sxs-lookup"><span data-stu-id="38778-171">h.</span></span> <span data-ttu-id="38778-172">键入命令 Get-CsAdForest，然后按 **Enter。**</span><span class="sxs-lookup"><span data-stu-id="38778-172">Type the command Get-CsAdForest, and press **Enter**.</span></span>
    
    <span data-ttu-id="38778-173">i.</span><span class="sxs-lookup"><span data-stu-id="38778-173">i.</span></span> <span data-ttu-id="38778-174">如果 **结果为** LC_FORESTSETTINGS_STATE_READY，则林已成功准备，如图所示。</span><span class="sxs-lookup"><span data-stu-id="38778-174">If the result is **LC_FORESTSETTINGS_STATE_READY**, the forest has successfully been prepared, as shown in the figure.</span></span>
    
     ![验证林复制。](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. <span data-ttu-id="38778-176">**步骤 4：验证全局编录的复制**</span><span class="sxs-lookup"><span data-stu-id="38778-176">**Step 4: Verify replication of the global catalog**</span></span>
    
    <span data-ttu-id="38778-177">a.</span><span class="sxs-lookup"><span data-stu-id="38778-177">a.</span></span> <span data-ttu-id="38778-178">在域控制器 (最好在其他域控制器) 的远程站点中，在运行林准备的林中，打开 **Active Directory 用户和计算机**。</span><span class="sxs-lookup"><span data-stu-id="38778-178">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
    <span data-ttu-id="38778-179">b.</span><span class="sxs-lookup"><span data-stu-id="38778-179">b.</span></span> <span data-ttu-id="38778-180">在 **“Active Directory 用户和计算机”** 中，展开林或子域的域名。</span><span class="sxs-lookup"><span data-stu-id="38778-180">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
    <span data-ttu-id="38778-181">c.</span><span class="sxs-lookup"><span data-stu-id="38778-181">c.</span></span> <span data-ttu-id="38778-182">单击 **左侧窗格** 上的"用户"容器，在右侧窗格中查找通用组 **CsAdministrator。**</span><span class="sxs-lookup"><span data-stu-id="38778-182">Click the **Users** container on the left side pane, and look for the Universal group **CsAdministrator** in the right side pane.</span></span> <span data-ttu-id="38778-183">如果 CsAdministrator (以 Cs 对象开头的其他新通用组) ，则 Active Directory 复制已成功。</span><span class="sxs-lookup"><span data-stu-id="38778-183">If CsAdministrator (among other new Universal groups that begin with Cs) is present, Active Directory replication has been successful.</span></span>
    
    <span data-ttu-id="38778-184">d.</span><span class="sxs-lookup"><span data-stu-id="38778-184">d.</span></span> <span data-ttu-id="38778-185">如果组尚不存在，可以强制复制，或等待 15 分钟并刷新右侧窗格。</span><span class="sxs-lookup"><span data-stu-id="38778-185">If the groups are not yet present, you can force the replication, or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="38778-186">显示组后，表明复制完成。</span><span class="sxs-lookup"><span data-stu-id="38778-186">When the groups are present, replication is complete.</span></span>
    
8. <span data-ttu-id="38778-187">**步骤 5：准备当前域**</span><span class="sxs-lookup"><span data-stu-id="38778-187">**Step 5: Prepare the current domain**</span></span>
    
    <span data-ttu-id="38778-188">a.</span><span class="sxs-lookup"><span data-stu-id="38778-188">a.</span></span> <span data-ttu-id="38778-189">查看步骤 5 的先决条件信息。</span><span class="sxs-lookup"><span data-stu-id="38778-189">Review the prerequisites information for Step 5.</span></span>
    
    <span data-ttu-id="38778-190">b.</span><span class="sxs-lookup"><span data-stu-id="38778-190">b.</span></span> <span data-ttu-id="38778-191">单击 **步骤** 5 中的"运行"以启动"准备当前域"向导。</span><span class="sxs-lookup"><span data-stu-id="38778-191">Click **Run** in Step 5 to launch the Prepare Current Domain wizard.</span></span>
    
    <span data-ttu-id="38778-192">c.</span><span class="sxs-lookup"><span data-stu-id="38778-192">c.</span></span> <span data-ttu-id="38778-193">请注意，该过程只应为部署中每个域运行一次，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="38778-193">Take note that the procedure should only be run once for each domain in the deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="38778-194">d.</span><span class="sxs-lookup"><span data-stu-id="38778-194">d.</span></span> <span data-ttu-id="38778-195">准备好域后，可以通过单击"查看日志" **来查看日志**。</span><span class="sxs-lookup"><span data-stu-id="38778-195">Once the domain has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="38778-196">e.</span><span class="sxs-lookup"><span data-stu-id="38778-196">e.</span></span> <span data-ttu-id="38778-197">单击 **"** 完成"以关闭"准备当前域"向导，并返回到"准备 Active Directory"步骤。</span><span class="sxs-lookup"><span data-stu-id="38778-197">Click **Finish** to close the Prepare Current Domain wizard, and return to the Prepare Active Directory steps.</span></span>
    
    <span data-ttu-id="38778-198">必须在找到 Skype for Business Server 对象的每个域中完成这些步骤，否则服务可能无法启动。</span><span class="sxs-lookup"><span data-stu-id="38778-198">These steps must be completed in every domain where Skype for Business Server objects are found, otherwise services might not start.</span></span> <span data-ttu-id="38778-199">这包括任何类型的 Active Directory 对象，如用户、联系对象、管理组或任何类型的对象。</span><span class="sxs-lookup"><span data-stu-id="38778-199">This includes any type of Active Directory object, such as users, contact objects, administrative groups, or any other type of object.</span></span> <span data-ttu-id="38778-200">如果需要，Set-CsUserReplicatorConfiguration -ADDomainNamingContextList 仅添加包含 Skype for Business Server 对象的域。</span><span class="sxs-lookup"><span data-stu-id="38778-200">You can use Set-CsUserReplicatorConfiguration -ADDomainNamingContextList to add only the domains with Skype for Business Server objects, if needed.</span></span>
    
9. <span data-ttu-id="38778-201">**步骤 6：验证域中的复制**</span><span class="sxs-lookup"><span data-stu-id="38778-201">**Step 6: Verify replication in the domain**</span></span>
    
    <span data-ttu-id="38778-202">a.</span><span class="sxs-lookup"><span data-stu-id="38778-202">a.</span></span> <span data-ttu-id="38778-203">从" **应用"页** 单击 Skype for Business Server 命令行 **管理程序** 以启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="38778-203">Click the **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.</span></span>
    
    <span data-ttu-id="38778-204">b.</span><span class="sxs-lookup"><span data-stu-id="38778-204">b.</span></span> <span data-ttu-id="38778-205">使用命令Get-CsAdDomain验证域中的复制。</span><span class="sxs-lookup"><span data-stu-id="38778-205">Use the command Get-CsAdDomain to verify replication within the domain.</span></span>
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > <span data-ttu-id="38778-206">如果不指定 Domain 参数，则将该值设置为本地域。</span><span class="sxs-lookup"><span data-stu-id="38778-206">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> 
  
    <span data-ttu-id="38778-207">为 contoso.local 域运行命令的示例：</span><span class="sxs-lookup"><span data-stu-id="38778-207">Example of running the command for the contoso.local domain:</span></span>
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > <span data-ttu-id="38778-208">通过使用参数 GlobalSettingsDomainController，您可以指示存储全局设置的位置。</span><span class="sxs-lookup"><span data-stu-id="38778-208">By using the parameter GlobalSettingsDomainController, you can indicate where global settings are stored.</span></span> <span data-ttu-id="38778-209">如果你的设置存储在系统容器 (这通常与尚未将全局设置迁移到配置容器) 的升级部署一样，则定义 AD DS 林根目录的域控制器。</span><span class="sxs-lookup"><span data-stu-id="38778-209">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your AD DS forest.</span></span> <span data-ttu-id="38778-210">如果全局设置存储在“配置”容器中（通常在新部署或设置已迁移到“配置”容器的升级部署中是这种情况），则定义林中的任何域控制器。</span><span class="sxs-lookup"><span data-stu-id="38778-210">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="38778-211">如果不指定此参数，此 cmdlet 将假定设置存储在"配置"容器中，并引用 Active Directory 中的任意域控制器。</span><span class="sxs-lookup"><span data-stu-id="38778-211">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="38778-212">c.</span><span class="sxs-lookup"><span data-stu-id="38778-212">c.</span></span> <span data-ttu-id="38778-213">如果 **结果为** LC_DOMAINSETTINGS_STATE_READY，则已成功复制域。</span><span class="sxs-lookup"><span data-stu-id="38778-213">If the result is **LC_DOMAINSETTINGS_STATE_READY**, the domain has successfully replicated.</span></span>
    
10. <span data-ttu-id="38778-214">**步骤 7：添加用户以提供对 Skype for Business Server 控制面板的管理访问权限**</span><span class="sxs-lookup"><span data-stu-id="38778-214">**Step 7: Add users to provide administrative access to the Skype for Business Server Control Panel**</span></span>
    
    <span data-ttu-id="38778-215">a.</span><span class="sxs-lookup"><span data-stu-id="38778-215">a.</span></span> <span data-ttu-id="38778-216">以 Domain Admins 组或 RTCUniversalServerAdmins 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="38778-216">Log on as a member of the Domain Admins group or the RTCUniversalServerAdmins group.</span></span>
    
    <span data-ttu-id="38778-217">b.</span><span class="sxs-lookup"><span data-stu-id="38778-217">b.</span></span> <span data-ttu-id="38778-218">打开 **Active Directory 用户和计算机**，展开域，单击"用户"容器，右键单击 CSAdministrator，然后选择 **"属性"。**</span><span class="sxs-lookup"><span data-stu-id="38778-218">Open **Active Directory Users and Computers**, expand your domain, click the **Users** container, right-click CSAdministrator, and choose **Properties**.</span></span>
    
    <span data-ttu-id="38778-219">c.</span><span class="sxs-lookup"><span data-stu-id="38778-219">c.</span></span> <span data-ttu-id="38778-220">在“CSAdministrator 属性”中，单击“成员”选项卡。</span><span class="sxs-lookup"><span data-stu-id="38778-220">In **CSAdministrator Properties**, click the **Members** tab.</span></span>
    
    <span data-ttu-id="38778-221">d.</span><span class="sxs-lookup"><span data-stu-id="38778-221">d.</span></span> <span data-ttu-id="38778-222">在"成员"选项卡上，单击"添加"。</span><span class="sxs-lookup"><span data-stu-id="38778-222">On the **Members** tab, click **Add**.</span></span> <span data-ttu-id="38778-223">在“选择用户、联系人、计算机、服务帐户或组”中，找到“输入要选择的对象名称”。</span><span class="sxs-lookup"><span data-stu-id="38778-223">In **Select Users, Contacts, Computers, Service Accounts, or Groups**, locate the **Enter the object names to select**.</span></span> <span data-ttu-id="38778-224">键入要添加到 CSAdministrators 组的用户名或组名。</span><span class="sxs-lookup"><span data-stu-id="38778-224">Type the user name(s) or group name(s) to add to the group CSAdministrators.</span></span> <span data-ttu-id="38778-225">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="38778-225">Click **OK**.</span></span>
    
    <span data-ttu-id="38778-226">e.</span><span class="sxs-lookup"><span data-stu-id="38778-226">e.</span></span> <span data-ttu-id="38778-227">在 **"成员** "选项卡上，确认所选的用户或组存在。</span><span class="sxs-lookup"><span data-stu-id="38778-227">On the **Members** tab, confirm that the users or groups that you selected are present.</span></span> <span data-ttu-id="38778-228">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="38778-228">Click **OK**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="38778-229">Skype for Business Server 控制面板是基于角色的访问控制工具。</span><span class="sxs-lookup"><span data-stu-id="38778-229">The Skype for Business Server Control Panel is a role-based access control tool.</span></span> <span data-ttu-id="38778-230">CsAdministrator 组的成员身份使使用 Skype for Business Server 控制面板的用户可以完全控制所有可用的配置功能。</span><span class="sxs-lookup"><span data-stu-id="38778-230">Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all configuration functions available.</span></span> <span data-ttu-id="38778-231">为特定功能提供了其他专门的角色。</span><span class="sxs-lookup"><span data-stu-id="38778-231">There are other roles available that are designed for specific functions.</span></span> <span data-ttu-id="38778-232">有关可用角色的详细信息，请参阅 [Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 的环境要求或 Skype for Business Server [2019 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="38778-232">For details on the roles available, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="38778-233">请注意，用户不需要启用 Skype for Business Server，就成为管理组的成员。</span><span class="sxs-lookup"><span data-stu-id="38778-233">Note that users do not have to be enabled for Skype for Business Server in order to be made members of the management groups.</span></span> 
  
    > [!CAUTION]
    > <span data-ttu-id="38778-234">若要帮助保留安全性和基于角色的访问控制完整性，请向组添加用户，这些组定义了用户在 Skype for Business Server 部署管理中执行的角色。</span><span class="sxs-lookup"><span data-stu-id="38778-234">To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment.</span></span> 
  
11. <span data-ttu-id="38778-235">注销，然后重新登录到 Windows，以便使用新的 Skype for Business Server 安全组更新你的安全令牌，然后重新打开部署向导。</span><span class="sxs-lookup"><span data-stu-id="38778-235">Log off, and then log back on to Windows so that your security token is updated with the new Skype for Business Server security group, and then reopen the Deployment Wizard.</span></span>
    
12. <span data-ttu-id="38778-236">确认在"准备 **Active Directory"** 旁边看到绿色选中标记以确认成功，如图所示。</span><span class="sxs-lookup"><span data-stu-id="38778-236">Verify that you see a green checkmark next to **Prepare Active Directory** to confirm success, as shown in the figure.</span></span>
    
     ![准备 Active Directory 已完成。](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a><span data-ttu-id="38778-238">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38778-238">See also</span></span>
 
[<span data-ttu-id="38778-239">适用于 Skype for Business Server 2015 的 Active Directory 域服务</span><span class="sxs-lookup"><span data-stu-id="38778-239">Active Directory Domain Services for Skype for Business Server 2015</span></span>](../../plan-your-deployment/security/active-directory-domain-services.md)
