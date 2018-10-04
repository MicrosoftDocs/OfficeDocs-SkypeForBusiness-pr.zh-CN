---
title: 将单个用户移动到试点池
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 您可以将用户从旧池移动到您 Skype 的 Skype 业务 Server 2019 控制面板或 Skype 用于业务服务器 2019年命令行管理程序的业务服务器 2019年试点池。 下面的示例中，在注册器池列中，在 pool01.contoso.net 旧池中，且所有六个这些用户连接到该池。 使用以下过程将用户移至您 Skype 业务服务器 2019年池 Skype 业务 Server 2019 Control Panel 和 Skype 用于业务 Server Management Shell。
ms.openlocfilehash: 6742c5fc00c9d53030ac32ee698686bb8b11fa07
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372743"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="3b0bf-105">将单个用户移动到试点池</span><span class="sxs-lookup"><span data-stu-id="3b0bf-105">Move a single user to the pilot pool</span></span>

<span data-ttu-id="3b0bf-106">您可以将用户从旧池移动到您 Skype 的 Skype 业务 Server 2019 控制面板或 Skype 用于业务服务器 2019年命令行管理程序的业务服务器 2019年试点池。</span><span class="sxs-lookup"><span data-stu-id="3b0bf-106">You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span> <span data-ttu-id="3b0bf-107">下面的示例中，在**注册器池**列中，在**pool01.contoso.net**旧池中，且所有六个这些用户连接到该池。</span><span class="sxs-lookup"><span data-stu-id="3b0bf-107">In the example below, in the **Registrar pool** column, **pool01.contoso.net** is the legacy pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="3b0bf-108">使用以下过程将用户移至您 Skype 业务服务器 2019年池 Skype 业务 Server 2019 Control Panel 和 Skype 用于业务 Server Management Shell。</span><span class="sxs-lookup"><span data-stu-id="3b0bf-108">Use the following procedures to move a user to your Skype for Business Server 2019 pool using Skype for Business Server 2019 Control Panel and Skype for Business Server Management Shell.</span></span> 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="3b0bf-109">使用 Skype 业务 Server 2019 控制面板移动用户</span><span class="sxs-lookup"><span data-stu-id="3b0bf-109">To move a user by using the Skype for Business Server 2019 Control Panel</span></span>
  
1. <span data-ttu-id="3b0bf-110">使用具有 RTCUniversalServerAdmins 组成员身份或 CsAdministrator 或 CsUserAdministrator 管理角色成员身份的帐户登录到前端服务器。</span><span class="sxs-lookup"><span data-stu-id="3b0bf-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="3b0bf-111">打开**Skype 的业务 Server Control Panel**。</span><span class="sxs-lookup"><span data-stu-id="3b0bf-111">Open **Skype for Business Server Control Panel**.</span></span>
    
3. <span data-ttu-id="3b0bf-112">单击**用户**，单击**搜索**，然后单击**查找**。</span><span class="sxs-lookup"><span data-stu-id="3b0bf-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
4. <span data-ttu-id="3b0bf-113">选择您想要将移动到 Skype 业务服务器 2019年池的用户。</span><span class="sxs-lookup"><span data-stu-id="3b0bf-113">Select a user that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="3b0bf-114">本示例中，我们将移动用户 Sara Davis。</span><span class="sxs-lookup"><span data-stu-id="3b0bf-114">In this example, we will move user Sara Davis.</span></span>
    
5. <span data-ttu-id="3b0bf-115">在“**操作**”菜单中，选择“**将所选用户移动到池**”。</span><span class="sxs-lookup"><span data-stu-id="3b0bf-115">On the **Action** menu, select **Move selected users to pool**.</span></span>
    
6. <span data-ttu-id="3b0bf-116">从下拉列表中，选择业务服务器 2019年池 Skype。</span><span class="sxs-lookup"><span data-stu-id="3b0bf-116">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
7. <span data-ttu-id="3b0bf-117">单击**操作**，然后单击**移动所选的用户移动到池**。</span><span class="sxs-lookup"><span data-stu-id="3b0bf-117">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="3b0bf-118">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="3b0bf-118">Click **OK**.</span></span>
  
8. <span data-ttu-id="3b0bf-119">确认该用户的**注册器池**列现在包含业务服务器 2019年池，这表明已成功移动该用户的 Skype。</span><span class="sxs-lookup"><span data-stu-id="3b0bf-119">Verify that the **Registrar pool** column for the user now contains the Skype for Business Server 2019 pool, which indicates that the user has been successfully moved.</span></span> 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="3b0bf-120">使用 Skype 业务服务器 2019年命令行管理程序移动用户</span><span class="sxs-lookup"><span data-stu-id="3b0bf-120">To move a user by using the Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="3b0bf-121">打开 Skype 业务 Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="3b0bf-121">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="3b0bf-122">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="3b0bf-122">At the command line, type the following:</span></span> 
    
   ```
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. <span data-ttu-id="3b0bf-123">接下来，在命令行中，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="3b0bf-123">Next, at the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -Identity "David Pelton"
   ```

4. <span data-ttu-id="3b0bf-124">**RegistrarPool**标识现在指向业务服务器 2019年池 Skype。</span><span class="sxs-lookup"><span data-stu-id="3b0bf-124">The **RegistrarPool** identity now points to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="3b0bf-125">该标识的状态，确认已成功移动该用户。</span><span class="sxs-lookup"><span data-stu-id="3b0bf-125">The presence of this identity confirms that the user has been successfully moved.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="3b0bf-126">有关**Get-csuser** cmdlet 的详细信息，请运行： **Get-help Get-csuser-详细**</span><span class="sxs-lookup"><span data-stu-id="3b0bf-126">For details about the **Get-CsUser** cmdlet, run: **Get-Help Get-CsUser -Detailed**</span></span>
  

