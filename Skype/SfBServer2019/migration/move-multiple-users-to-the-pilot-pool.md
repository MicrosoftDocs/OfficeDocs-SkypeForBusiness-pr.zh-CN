---
title: 将多个用户移动到引导池
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 您可以使用 Skype for Business Server 2019 控制面板或 Skype for Business Server 2019 命令行管理程序，将多个用户从旧版池移动到 Skype for business Server 2019 试点池。
ms.openlocfilehash: d1b003c5630a0917fbecbd9b04196675657fef83
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753424"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="9ef62-103">将多个用户移动到引导池</span><span class="sxs-lookup"><span data-stu-id="9ef62-103">Move multiple users to the pilot pool</span></span>

<span data-ttu-id="9ef62-104">您可以使用 Skype for Business Server 2019 控制面板或 Skype for Business Server 2019 命令行管理程序，将多个用户从旧版池移动到 Skype for business Server 2019 试点池。</span><span class="sxs-lookup"><span data-stu-id="9ef62-104">You can move multiple users from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span>

 <span data-ttu-id="9ef62-105">**本文内容：**</span><span class="sxs-lookup"><span data-stu-id="9ef62-105">**In this article**</span></span>
  
[<span data-ttu-id="9ef62-106">使用 Skype for Business Server 2019 控制面板移动多个用户</span><span class="sxs-lookup"><span data-stu-id="9ef62-106">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection0)
  
[<span data-ttu-id="9ef62-107">使用 Skype for Business Server 2019 命令行管理程序移动多个用户</span><span class="sxs-lookup"><span data-stu-id="9ef62-107">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection1)
  
[<span data-ttu-id="9ef62-108">使用 Skype for Business Server 2019 命令行管理程序同时移动所有用户</span><span class="sxs-lookup"><span data-stu-id="9ef62-108">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="9ef62-109">使用 Skype for Business Server 2019 控制面板移动多个用户</span><span class="sxs-lookup"><span data-stu-id="9ef62-109">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="9ef62-110"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="9ef62-110"><a name="sectionSection0"> </a></span></span>

1. <span data-ttu-id="9ef62-111">打开 "Skype for Business Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="9ef62-111">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="9ef62-112">依次单击“用户”\*\*\*\*、“搜索”\*\*\*\* 和“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9ef62-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="9ef62-113">选择要移到 Skype for Business Server 2019 池的两个用户。</span><span class="sxs-lookup"><span data-stu-id="9ef62-113">Select two users that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="9ef62-114">在本例中，我们将移动用户 Chen Yang 和 Claus Hansen。</span><span class="sxs-lookup"><span data-stu-id="9ef62-114">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
     ![将用户移动到特定的注册池](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. <span data-ttu-id="9ef62-116">在“操作”\*\*\*\* 菜单中，选择“将所选用户移动到池”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9ef62-116">From the **Action** menu, select **Move selected users to pool**.</span></span>
    
5. <span data-ttu-id="9ef62-117">从下拉列表中，选择 "Skype for Business Server 2019" 池。</span><span class="sxs-lookup"><span data-stu-id="9ef62-117">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
6. <span data-ttu-id="9ef62-118">单击“操作”\*\*\*\*，然后单击“将所选用户移动到池”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9ef62-118">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="9ef62-119">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9ef62-119">Click **OK**.</span></span>
    
     !["移动用户，目标注册器池" 对话框](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. <span data-ttu-id="9ef62-121">确认用户的 "**注册器池**" 列现在包含 Skype For business Server 2019 池，这表明已成功移动了用户。</span><span class="sxs-lookup"><span data-stu-id="9ef62-121">Verify that the **Registrar pool** column for the users now contains the Skype for Business Server 2019 pool, which indicates that the users have been successfully moved.</span></span> 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="9ef62-122">使用 Skype for Business Server 2019 命令行管理程序移动多个用户</span><span class="sxs-lookup"><span data-stu-id="9ef62-122">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="9ef62-123"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="9ef62-123"><a name="sectionSection1"> </a></span></span>

1. <span data-ttu-id="9ef62-124">打开 Skype for Business Server 2019 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="9ef62-124">Open the Skype for Business Server 2019 Management Shell.</span></span> 
    
2. <span data-ttu-id="9ef62-125">在命令行中，键入以下内容，并**User1**将 User1**和用户2替换为要**移动的特定用户名，并将**pool_FQDN**替换为目标池的名称。</span><span class="sxs-lookup"><span data-stu-id="9ef62-125">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move, and replace **pool_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="9ef62-126">在本例中，我们将移动用户 Hao Chen 和 Katie Jordan。</span><span class="sxs-lookup"><span data-stu-id="9ef62-126">In this example we will move users Hao Chen and Katie Jordan.</span></span> 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![PowerShell Get-csuser cmdlet 示例](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. <span data-ttu-id="9ef62-128">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="9ef62-128">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. <span data-ttu-id="9ef62-129">**Registrar Pool** 标识现在应该指向在上一步中指定为 **pool_FQDN** 的池。</span><span class="sxs-lookup"><span data-stu-id="9ef62-129">The **Registrar Pool** identity should now point to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="9ef62-130">存在该标识即可确认已成功移动用户。</span><span class="sxs-lookup"><span data-stu-id="9ef62-130">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="9ef62-131">重复步骤以验证是否**已移动**到 "2"。</span><span class="sxs-lookup"><span data-stu-id="9ef62-131">Repeat step to verify that **User2** has been moved.</span></span> 
    
     ![PowerShell UsUser cmdlet 的输出](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="9ef62-133">使用 Skype for Business Server 2019 命令行管理程序同时移动所有用户</span><span class="sxs-lookup"><span data-stu-id="9ef62-133">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="9ef62-134"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="9ef62-134"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="9ef62-135">在此示例中，所有用户都已返回到旧版池（pool01.contoso.net）。</span><span class="sxs-lookup"><span data-stu-id="9ef62-135">In this example, all users have been returned to the legacy pool (pool01.contoso.net).</span></span> <span data-ttu-id="9ef62-136">使用 Skype for Business Server 2019 命令行管理程序，我们将同时将所有用户移动到 Skype for Business Server 2019 池（pool02.contoso.net）。</span><span class="sxs-lookup"><span data-stu-id="9ef62-136">Using the Skype for Business Server 2019 Management Shell, we will move all users at the same time to the Skype for Business Server 2019 pool (pool02.contoso.net).</span></span>
  
1. <span data-ttu-id="9ef62-137">打开 Skype for Business Server 2019 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="9ef62-137">Open the Skype for Business Server 2019 Management Shell.</span></span>
    
2. <span data-ttu-id="9ef62-138">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="9ef62-138">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![PowerShell cmdlet 和命令行管理程序中的结果](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. <span data-ttu-id="9ef62-140">为试用用户之一运行**get-csuser** 。</span><span class="sxs-lookup"><span data-stu-id="9ef62-140">Run **Get-CsUser** for one of the pilot users.</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. <span data-ttu-id="9ef62-141">每个用户的**注册器池**标识现在指向您在上一步中指定为**pool_FQDN**的池。</span><span class="sxs-lookup"><span data-stu-id="9ef62-141">The **Registrar Pool** identity for each user now points to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="9ef62-142">存在该标识即可确认已成功移动用户。</span><span class="sxs-lookup"><span data-stu-id="9ef62-142">The presence of this identity confirms that the user has been successfully moved.</span></span> 
    
5. <span data-ttu-id="9ef62-143">此外，我们还可以查看 Skype for business Server 2019 控制面板中的用户列表，并验证注册器池值是否现在指向 Skype for Business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="9ef62-143">Additionally, we can view the list of users in the Skype for Business Server 2019 Control Panel and verify that the Registrar Pool value now points to the Skype for Business Server 2019 pool.</span></span>
    
     ![Skype for Business Server 2019 控制面板用户列表](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

