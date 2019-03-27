---
title: 将多个用户移至试点池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 可以将多个用户从旧池移动到您 Skype 业务服务器 2019年试点池 Skype 业务 Server 2019 控制面板或 Skype 用于业务服务器 2019年命令行管理程序中。
ms.openlocfilehash: c77598d531fa4640d64a61e22ace17e39d87b005
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888299"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="7a19c-103">将多个用户移至试点池</span><span class="sxs-lookup"><span data-stu-id="7a19c-103">Move multiple users to the pilot pool</span></span>

<span data-ttu-id="7a19c-104">可以将多个用户从旧池移动到您 Skype 业务服务器 2019年试点池 Skype 业务 Server 2019 控制面板或 Skype 用于业务服务器 2019年命令行管理程序中。</span><span class="sxs-lookup"><span data-stu-id="7a19c-104">You can move multiple users from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span>

 <span data-ttu-id="7a19c-105">**本文中**</span><span class="sxs-lookup"><span data-stu-id="7a19c-105">**In this article**</span></span>
  
[<span data-ttu-id="7a19c-106">使用 Skype 业务 Server 2019 控制面板移动多个用户</span><span class="sxs-lookup"><span data-stu-id="7a19c-106">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection0)
  
[<span data-ttu-id="7a19c-107">使用 Skype 业务服务器 2019年命令行管理程序移动多个用户</span><span class="sxs-lookup"><span data-stu-id="7a19c-107">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection1)
  
[<span data-ttu-id="7a19c-108">要使用 Skype 业务服务器 2019年命令行管理程序同时移动所有用户</span><span class="sxs-lookup"><span data-stu-id="7a19c-108">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="7a19c-109">使用 Skype 业务 Server 2019 控制面板移动多个用户</span><span class="sxs-lookup"><span data-stu-id="7a19c-109">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="7a19c-110"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="7a19c-110"></span></span>

1. <span data-ttu-id="7a19c-111">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="7a19c-111">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="7a19c-112">单击**用户**，单击**搜索**，然后单击**查找**。</span><span class="sxs-lookup"><span data-stu-id="7a19c-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="7a19c-113">选择您想要业务服务器 2019年池移动到 Skype 的两个用户。</span><span class="sxs-lookup"><span data-stu-id="7a19c-113">Select two users that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="7a19c-114">本示例中，我们将移动用户 Chen Yang 和来了 Hansen。</span><span class="sxs-lookup"><span data-stu-id="7a19c-114">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
     ![将用户移至特定的注册池](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. <span data-ttu-id="7a19c-116">从**操作**菜单中，选择**移动所选的用户移动到池**。</span><span class="sxs-lookup"><span data-stu-id="7a19c-116">From the **Action** menu, select **Move selected users to pool**.</span></span>
    
5. <span data-ttu-id="7a19c-117">从下拉列表中，选择业务服务器 2019年池 Skype。</span><span class="sxs-lookup"><span data-stu-id="7a19c-117">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
6. <span data-ttu-id="7a19c-118">单击**操作**，然后单击**移动所选的用户移动到池**。</span><span class="sxs-lookup"><span data-stu-id="7a19c-118">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="7a19c-119">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="7a19c-119">Click **OK**.</span></span>
    
     ![移动用户，目标注册器池对话框](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. <span data-ttu-id="7a19c-121">确认用户的**注册器池**列现在包含业务服务器 2019年池，这表明已成功移动用户的 Skype。</span><span class="sxs-lookup"><span data-stu-id="7a19c-121">Verify that the **Registrar pool** column for the users now contains the Skype for Business Server 2019 pool, which indicates that the users have been successfully moved.</span></span> 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="7a19c-122">使用 Skype 业务服务器 2019年命令行管理程序移动多个用户</span><span class="sxs-lookup"><span data-stu-id="7a19c-122">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="7a19c-123"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="7a19c-123"></span></span>

1. <span data-ttu-id="7a19c-124">打开 Skype 业务服务器 2019年命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="7a19c-124">Open the Skype for Business Server 2019 Management Shell.</span></span> 
    
2. <span data-ttu-id="7a19c-125">在命令行中，键入以下命令并**User1**和**User2**替换为您想要移动的具体用户名**pool_FQDN**替换为目标池的名称。</span><span class="sxs-lookup"><span data-stu-id="7a19c-125">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move, and replace **pool_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="7a19c-126">在此示例中，我们将移动用户 Hao Chen 和 Katie 约旦。</span><span class="sxs-lookup"><span data-stu-id="7a19c-126">In this example we will move users Hao Chen and Katie Jordan.</span></span> 
    
   ```
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![PowerShell Get-csuser cmdlet 的示例](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. <span data-ttu-id="7a19c-128">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="7a19c-128">At the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -Identity "User1"
   ```

4. <span data-ttu-id="7a19c-129">**注册器池**标识现在应指向为**pool_FQDN**上一步骤中指定的池。</span><span class="sxs-lookup"><span data-stu-id="7a19c-129">The **Registrar Pool** identity should now point to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="7a19c-130">该标识的状态，确认已成功移动该用户。</span><span class="sxs-lookup"><span data-stu-id="7a19c-130">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="7a19c-131">重复步骤以验证已移动**User2** 。</span><span class="sxs-lookup"><span data-stu-id="7a19c-131">Repeat step to verify that **User2** has been moved.</span></span> 
    
     ![输出的 PowerShell Get-UsUser-Identity cmdlet](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="7a19c-133">要使用 Skype 业务服务器 2019年命令行管理程序同时移动所有用户</span><span class="sxs-lookup"><span data-stu-id="7a19c-133">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="7a19c-134"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="7a19c-134"></span></span>

<span data-ttu-id="7a19c-135">本示例中，所有用户已都返回到旧池 (pool01.contoso.net)。</span><span class="sxs-lookup"><span data-stu-id="7a19c-135">In this example, all users have been returned to the legacy pool (pool01.contoso.net).</span></span> <span data-ttu-id="7a19c-136">使用 Skype 业务服务器 2019年命令行管理程序，我们将移动所有用户在同一时间到业务服务器 2019年池 (pool02.contoso.net) Skype。</span><span class="sxs-lookup"><span data-stu-id="7a19c-136">Using the Skype for Business Server 2019 Management Shell, we will move all users at the same time to the Skype for Business Server 2019 pool (pool02.contoso.net).</span></span>
  
1. <span data-ttu-id="7a19c-137">打开 Skype 业务服务器 2019年命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="7a19c-137">Open the Skype for Business Server 2019 Management Shell.</span></span>
    
2. <span data-ttu-id="7a19c-138">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="7a19c-138">At the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![PowerShell cmdlet 和命令行管理程序中的结果](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. <span data-ttu-id="7a19c-140">运行**Get-csuser**为试点用户之一。</span><span class="sxs-lookup"><span data-stu-id="7a19c-140">Run **Get-CsUser** for one of the pilot users.</span></span> 
    
   ```
   Get-CsUser -Identity "Hao Chen"
   ```

4. <span data-ttu-id="7a19c-141">为每个用户的**注册器池**标识现在指向为**pool_FQDN**上一步骤中指定的池。</span><span class="sxs-lookup"><span data-stu-id="7a19c-141">The **Registrar Pool** identity for each user now points to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="7a19c-142">该标识的状态，确认已成功移动该用户。</span><span class="sxs-lookup"><span data-stu-id="7a19c-142">The presence of this identity confirms that the user has been successfully moved.</span></span> 
    
5. <span data-ttu-id="7a19c-143">此外，我们可以业务 Server 2019 控制面板的 Skype 中查看用户列表，并验证 Registrar Pool 值现在指向业务服务器 2019年池 Skype。</span><span class="sxs-lookup"><span data-stu-id="7a19c-143">Additionally, we can view the list of users in the Skype for Business Server 2019 Control Panel and verify that the Registrar Pool value now points to the Skype for Business Server 2019 pool.</span></span>
    
     ![Skype 业务 Server 2019 Control Panel 用户列表](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

