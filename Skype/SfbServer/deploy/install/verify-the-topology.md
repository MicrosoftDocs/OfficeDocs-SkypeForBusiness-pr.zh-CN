---
title: 在 Skype for Business Server 2015 中验证拓扑
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: '摘要： 了解如何验证业务服务器拓扑 Skype 和 Active Directory 服务器按预期的方式工作。 有关从 Microsoft 评估中心的业务服务器 2015年下载免费试用版的 Skype: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: 983ecf8b78a12898d18f04f7ec5c26c5271cf79a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="verify-the-topology-in-skype-for-business-server-2015"></a><span data-ttu-id="4aa6c-104">在 Skype for Business Server 2015 中验证拓扑</span><span class="sxs-lookup"><span data-stu-id="4aa6c-104">Verify the topology in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4aa6c-105">**摘要：**了解如何确定业务服务器拓扑 Skype 和 Active Directory 服务器按预期的方式工作。</span><span class="sxs-lookup"><span data-stu-id="4aa6c-105">**Summary:** Learn how to verify the Skype for Business Server topology and Active Directory servers are working as expected.</span></span> <span data-ttu-id="4aa6c-106">有关从[Microsoft 评估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)业务服务器 2015年下载 Skype 的免费试用版。</span><span class="sxs-lookup"><span data-stu-id="4aa6c-106">Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="4aa6c-107">已发布的拓扑和 Skype 业务服务器系统组件安装在每个拓扑中的服务器后，您就可以验证拓扑按预期的方式工作。</span><span class="sxs-lookup"><span data-stu-id="4aa6c-107">After you have the topology published and the Skype for Business Server system components installed on each of the servers in the topology, you are ready to verify that the topology is working as expected.</span></span> <span data-ttu-id="4aa6c-108">这包括验证配置传播到所有 Active Directory 的服务器，以便整个域知道 Skype 业务可在域中。</span><span class="sxs-lookup"><span data-stu-id="4aa6c-108">This includes verifying that the configuration has propagated out to all of the Active Directory servers so that the entire domain knows Skype for Business is available in the domain.</span></span> <span data-ttu-id="4aa6c-109">您可以按照任意顺序完成第 1 步至第 5 步。</span><span class="sxs-lookup"><span data-stu-id="4aa6c-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="4aa6c-110">但是，第 6、7、8 步必须在第 1 步至第 5 步之后按图表所示顺序执行。</span><span class="sxs-lookup"><span data-stu-id="4aa6c-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="4aa6c-111">验证拓扑是 8 个步骤中的第 8 步。</span><span class="sxs-lookup"><span data-stu-id="4aa6c-111">Verifying the topology is step 8 of 8.</span></span>
  
![概述图表。](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a><span data-ttu-id="4aa6c-113">测试前端池部署</span><span class="sxs-lookup"><span data-stu-id="4aa6c-113">Test the Front End pool deployment</span></span>

<span data-ttu-id="4aa6c-114">最后一步是测试前端池并确认 Skype 业务客户端可以相互通信。</span><span class="sxs-lookup"><span data-stu-id="4aa6c-114">The final step is to test the Front End pool and confirm that Skype for Business clients can communicate with each other.</span></span> 
  
### <a name="add-users-and-verify-client-connectivity"></a><span data-ttu-id="4aa6c-115">添加用户并验证客户端连接</span><span class="sxs-lookup"><span data-stu-id="4aa6c-115">Add users and verify client connectivity</span></span>

1. <span data-ttu-id="4aa6c-116">使用活动目录计算机和用户添加到**CSAdministrator**组的管理员角色的 Active Directory 用户对象 （在其上安装了业务服务器控件面板的 Skype） 的业务服务器部署 Skype。</span><span class="sxs-lookup"><span data-stu-id="4aa6c-116">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Skype for Business Server deployment (on which Skype for Business Server Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="4aa6c-117">如果没有在 CsAdministors 组中添加适当的用户和组，您会收到错误，当您打开 Skype 业务服务器控制面板中读取，它"未经授权： 访问由于基于角色的访问控制 (RBAC) 授权失败被拒绝."</span><span class="sxs-lookup"><span data-stu-id="4aa6c-117">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when you open Skype for Business Server Control Panel which reads, "Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure."</span></span> 
  
2. <span data-ttu-id="4aa6c-118">如果用户对象当前已登录，则注销后重新登录，以注册新的组分配。</span><span class="sxs-lookup"><span data-stu-id="4aa6c-118">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4aa6c-119">用户帐户不能为任何业务服务器运行 Skype 的服务器的本地管理员。</span><span class="sxs-lookup"><span data-stu-id="4aa6c-119">The user account cannot be the local administrator of any server running Skype for Business Server.</span></span> 
  
3. <span data-ttu-id="4aa6c-120">使用管理帐户登录到计算机上装有 Skype 业务服务器的控制面板。</span><span class="sxs-lookup"><span data-stu-id="4aa6c-120">Use the administrative account to log on to the computer where Skype for Business Server Control Panel is installed.</span></span>
    
4. <span data-ttu-id="4aa6c-121">为业务服务器控制面板启动 Skype，然后如果系统提示您提供凭据。</span><span class="sxs-lookup"><span data-stu-id="4aa6c-121">Start Skype for Business Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="4aa6c-122">Skype 业务服务器控件面板显示部署的信息。</span><span class="sxs-lookup"><span data-stu-id="4aa6c-122">Skype for Business Server Control Panel displays deployment information.</span></span>
    
5. <span data-ttu-id="4aa6c-123">在左侧的导航栏中，单击**拓扑结构**，并确认服务状态显示带有一个绿色箭头的计算机和一个绿色的复选标记为复制状态是每个已部署和联机业务服务器角色的 Skype 旁边。</span><span class="sxs-lookup"><span data-stu-id="4aa6c-123">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Skype for Business Server role that has been deployed and brought online.</span></span> 
    
6. <span data-ttu-id="4aa6c-124">在左侧导航栏中，单击**用户**，然后单击**启用用户**。</span><span class="sxs-lookup"><span data-stu-id="4aa6c-124">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span> 
    
7. <span data-ttu-id="4aa6c-125">在**新的 Skype 业务服务器用户的**页面上，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="4aa6c-125">On the **New Skype for Business Server User** page, click **Add**.</span></span>
    
8. <span data-ttu-id="4aa6c-p105">要为希望查找的对象定义搜索参数，可以在**从 Active Directory 中选择**页上选择**搜索**，然后选择单击**添加筛选器**。还可以选择**LDAP 搜索**，然后输入 LDAP 表达式以筛选或限制将返回的对象。确定“搜索”选项后，单击**查找**。</span><span class="sxs-lookup"><span data-stu-id="4aa6c-p105">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**. You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned. After you have decided on your Search options, click **Find**.</span></span>
    
9. <span data-ttu-id="4aa6c-129">在搜索结果窗格中，选择要添加的用户，然后单击 **确定**。</span><span class="sxs-lookup"><span data-stu-id="4aa6c-129">In the Search results pane, select the users you want to add, and then click **OK**.</span></span>
    
10. <span data-ttu-id="4aa6c-130">在**新 Skype 业务服务器用户的**页面上，您所选的用户是在**用户**显示。</span><span class="sxs-lookup"><span data-stu-id="4aa6c-130">On the **New Skype for Business Server User** page, the users you selected are in the **Users** display.</span></span> <span data-ttu-id="4aa6c-131">在**将用户分配给池**列表中，选择应驻留用户的服务器。</span><span class="sxs-lookup"><span data-stu-id="4aa6c-131">In the **Assign users to a pool** list, select the server where the users should reside.</span></span>
    
    <span data-ttu-id="4aa6c-132">您可以使用以下列表中的选项来配置对象。</span><span class="sxs-lookup"><span data-stu-id="4aa6c-132">The following is a list of options you can use to configure the objects.</span></span>
    
    - <span data-ttu-id="4aa6c-133">**生成用户的 SIP URI**</span><span class="sxs-lookup"><span data-stu-id="4aa6c-133">**Generate user's SIP URI**</span></span>
    
    - <span data-ttu-id="4aa6c-134">**电话**</span><span class="sxs-lookup"><span data-stu-id="4aa6c-134">**Telephony**</span></span>
    
    - <span data-ttu-id="4aa6c-135">**线路 URI**</span><span class="sxs-lookup"><span data-stu-id="4aa6c-135">**Line URI**</span></span>
    
    - <span data-ttu-id="4aa6c-136">**会议策略**</span><span class="sxs-lookup"><span data-stu-id="4aa6c-136">**Conferencing policy**</span></span>
    
    - <span data-ttu-id="4aa6c-137">**客户端版本策略**</span><span class="sxs-lookup"><span data-stu-id="4aa6c-137">**Client version policy**</span></span>
    
    - <span data-ttu-id="4aa6c-138">**PIN 策略**</span><span class="sxs-lookup"><span data-stu-id="4aa6c-138">**PIN policy**</span></span>
    
    - <span data-ttu-id="4aa6c-139">**外部访问策略**</span><span class="sxs-lookup"><span data-stu-id="4aa6c-139">**External access policy**</span></span>
    
    - <span data-ttu-id="4aa6c-140">**存档策略**</span><span class="sxs-lookup"><span data-stu-id="4aa6c-140">**Archiving policy**</span></span>
    
    - <span data-ttu-id="4aa6c-141">**位置策略**</span><span class="sxs-lookup"><span data-stu-id="4aa6c-141">**Location policy**</span></span>
    
    - <span data-ttu-id="4aa6c-142">**客户端策略**</span><span class="sxs-lookup"><span data-stu-id="4aa6c-142">**Client policy**</span></span>
    
    <span data-ttu-id="4aa6c-143">要测试的基本功能，请选择您想用于**生成用户的 SIP URI**设置 （其他选项中配置使用默认设置），选项然后单击**启用**，如图中所示。</span><span class="sxs-lookup"><span data-stu-id="4aa6c-143">To test the basic functionality, select the option you prefer for the **Generate user's SIP URI** setting (the other options in the configuration use default settings), and then click **Enable**, as shown in the figure.</span></span>
    
     ![在控制面板中启用用户。](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. <span data-ttu-id="4aa6c-p107">此时将显示摘要页面，其中**已启用**列将显示复选标记，指示用户现已完成设置。**SIP 地址**列将显示用户登录配置所需的地址。</span><span class="sxs-lookup"><span data-stu-id="4aa6c-p107">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the users are setup. The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>
    
     ![已添加到 Skype for Business Server 控制面板的用户。](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. <span data-ttu-id="4aa6c-148">使一个用户登录到加入域的计算机，另一个用户登录到域中的另一台计算机。</span><span class="sxs-lookup"><span data-stu-id="4aa6c-148">Log one user on to a computer that is joined to the domain and another user on to another computer in the domain.</span></span>
    
13. <span data-ttu-id="4aa6c-149">为在每两个客户端计算机上业务客户端安装 Skype，并验证两个用户可以登录到 Skype 业务服务器并可以相互发送即时消息。</span><span class="sxs-lookup"><span data-stu-id="4aa6c-149">Install Skype for Business client on each of the two client computers, and then verify that both users can sign in to Skype for Business Server and can send instant messages to each other.</span></span>
    

