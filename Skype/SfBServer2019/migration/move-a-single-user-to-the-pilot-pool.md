---
title: 将单个用户移动到引导池
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
description: 您可以使用 Skype for Business Server 2019 控制面板或 Skype for Business Server 2019 命令行管理程序，将用户从旧版池移动到 Skype for business Server 2019 试点池。 在下面的示例中，在 "注册器池" 列中，pool01.contoso.net 是旧池，所有这六个用户均连接到此池。 使用以下过程可使用 Skype for Business Server 2019 控制面板和 Skype for Business Server 命令行管理程序将用户移动到 Skype for business Server 2019 池。
ms.openlocfilehash: 6be30f37987cc31835a12178d32a8337d9fc5cae
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752504"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="0d234-105">将单个用户移动到引导池</span><span class="sxs-lookup"><span data-stu-id="0d234-105">Move a single user to the pilot pool</span></span>

<span data-ttu-id="0d234-106">您可以使用 Skype for Business Server 2019 控制面板或 Skype for Business Server 2019 命令行管理程序，将用户从旧版池移动到 Skype for business Server 2019 试点池。</span><span class="sxs-lookup"><span data-stu-id="0d234-106">You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span> <span data-ttu-id="0d234-107">在下面的示例中，在 "**注册器池**" 列中， **pool01.contoso.net**是旧池，所有这六个用户均连接到此池。</span><span class="sxs-lookup"><span data-stu-id="0d234-107">In the example below, in the **Registrar pool** column, **pool01.contoso.net** is the legacy pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="0d234-108">使用以下过程可使用 Skype for Business Server 2019 控制面板和 Skype for Business Server 命令行管理程序将用户移动到 Skype for business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="0d234-108">Use the following procedures to move a user to your Skype for Business Server 2019 pool using Skype for Business Server 2019 Control Panel and Skype for Business Server Management Shell.</span></span> 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="0d234-109">使用 Skype for Business Server 2019 控制面板移动用户</span><span class="sxs-lookup"><span data-stu-id="0d234-109">To move a user by using the Skype for Business Server 2019 Control Panel</span></span>
  
1. <span data-ttu-id="0d234-110">使用具有 RTCUniversalServerAdmins 组成员身份或者 CsAdministrator 或 CsUserAdministrator 管理角色成员身份的帐户登录到前端服务器。</span><span class="sxs-lookup"><span data-stu-id="0d234-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="0d234-111">打开 **"Skype For Business Server 控制面板"**。</span><span class="sxs-lookup"><span data-stu-id="0d234-111">Open **Skype for Business Server Control Panel**.</span></span>
    
3. <span data-ttu-id="0d234-112">依次单击“用户”\*\*\*\*、“搜索”\*\*\*\* 和“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d234-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
4. <span data-ttu-id="0d234-113">选择要移到 Skype for Business Server 2019 池的用户。</span><span class="sxs-lookup"><span data-stu-id="0d234-113">Select a user that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="0d234-114">在本示例中，我们将移动用户 Sara Davis。</span><span class="sxs-lookup"><span data-stu-id="0d234-114">In this example, we will move user Sara Davis.</span></span>
    
5. <span data-ttu-id="0d234-115">在“操作”\*\*\*\* 菜单中，选择“将所选用户移动到池”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d234-115">On the **Action** menu, select **Move selected users to pool**.</span></span>
    
6. <span data-ttu-id="0d234-116">从下拉列表中，选择 "Skype for Business Server 2019" 池。</span><span class="sxs-lookup"><span data-stu-id="0d234-116">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
7. <span data-ttu-id="0d234-117">单击“操作”\*\*\*\*，然后单击“将所选用户移动到池”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d234-117">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="0d234-118">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d234-118">Click **OK**.</span></span>
  
8. <span data-ttu-id="0d234-119">确认用户的 "**注册器池**" 列现在包含 Skype For business Server 2019 池，这表明已成功移动该用户。</span><span class="sxs-lookup"><span data-stu-id="0d234-119">Verify that the **Registrar pool** column for the user now contains the Skype for Business Server 2019 pool, which indicates that the user has been successfully moved.</span></span> 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="0d234-120">使用 Skype for Business Server 2019 命令行管理程序移动用户</span><span class="sxs-lookup"><span data-stu-id="0d234-120">To move a user by using the Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="0d234-121">打开 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="0d234-121">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="0d234-122">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="0d234-122">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. <span data-ttu-id="0d234-123">接下来，在命令行处键入：</span><span class="sxs-lookup"><span data-stu-id="0d234-123">Next, at the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. <span data-ttu-id="0d234-124">**RegistrarPool**标识现在指向 Skype For business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="0d234-124">The **RegistrarPool** identity now points to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="0d234-125">存在该标识即可确认已成功移动用户。</span><span class="sxs-lookup"><span data-stu-id="0d234-125">The presence of this identity confirms that the user has been successfully moved.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="0d234-126">有关**get-csuser** cmdlet 的详细信息，请运行： **Get-help get-csuser-详细**信息</span><span class="sxs-lookup"><span data-stu-id="0d234-126">For details about the **Get-CsUser** cmdlet, run: **Get-Help Get-CsUser -Detailed**</span></span>
  

