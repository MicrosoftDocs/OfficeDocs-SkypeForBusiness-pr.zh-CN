---
title: 将单个用户移动到 "引导" 池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 你可以使用 Skype for Business Server 2019 控制面板或 Skype for business Server 2019 命令行管理程序将用户从旧版池中移动到 Skype for business Server 2019 试验池。 在下面的示例中，在 "注册机构池" 列中，pool01.contoso.net 是旧版池，并且所有六个用户都连接到该池。 使用以下过程，使用 Skype for business Server 2019 控制面板和 Skype for business Server Management Shell 将用户移动到 Skype for business Server 2019 池。
ms.openlocfilehash: cc8c657b5e8d9cea760472c80da28bad4cf21f2e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813300"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="8143c-105">将单个用户移动到 "引导" 池</span><span class="sxs-lookup"><span data-stu-id="8143c-105">Move a single user to the pilot pool</span></span>

<span data-ttu-id="8143c-106">你可以使用 Skype for Business Server 2019 控制面板或 Skype for business Server 2019 命令行管理程序将用户从旧版池中移动到 Skype for business Server 2019 试验池。</span><span class="sxs-lookup"><span data-stu-id="8143c-106">You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span> <span data-ttu-id="8143c-107">在下面的示例中，在 "**注册机构池**" 列中， **pool01.contoso.net**是旧版池，并且所有六个用户都连接到该池。</span><span class="sxs-lookup"><span data-stu-id="8143c-107">In the example below, in the **Registrar pool** column, **pool01.contoso.net** is the legacy pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="8143c-108">使用以下过程，使用 Skype for business Server 2019 控制面板和 Skype for business Server Management Shell 将用户移动到 Skype for business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="8143c-108">Use the following procedures to move a user to your Skype for Business Server 2019 pool using Skype for Business Server 2019 Control Panel and Skype for Business Server Management Shell.</span></span> 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="8143c-109">使用 Skype for Business Server 2019 控制面板移动用户</span><span class="sxs-lookup"><span data-stu-id="8143c-109">To move a user by using the Skype for Business Server 2019 Control Panel</span></span>
  
1. <span data-ttu-id="8143c-110">使用具有 RTCUniversalServerAdmins 组成员身份或 CsAdministrator 或 CsUserAdministrator 管理角色成员身份的帐户登录到前端服务器。</span><span class="sxs-lookup"><span data-stu-id="8143c-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="8143c-111">打开 **"Skype For Business 服务器" 控制面板**。</span><span class="sxs-lookup"><span data-stu-id="8143c-111">Open **Skype for Business Server Control Panel**.</span></span>
    
3. <span data-ttu-id="8143c-112">单击 "**用户**"，单击 "**搜索**"，然后单击 "**查找**"。</span><span class="sxs-lookup"><span data-stu-id="8143c-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
4. <span data-ttu-id="8143c-113">选择要移动到 Skype for business Server 2019 池的用户。</span><span class="sxs-lookup"><span data-stu-id="8143c-113">Select a user that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="8143c-114">在此示例中，将移动用户 Sara Davis。</span><span class="sxs-lookup"><span data-stu-id="8143c-114">In this example, we will move user Sara Davis.</span></span>
    
5. <span data-ttu-id="8143c-115">在“操作”\*\*\*\* 菜单中，选择“将所选用户移动到池”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8143c-115">On the **Action** menu, select **Move selected users to pool**.</span></span>
    
6. <span data-ttu-id="8143c-116">从下拉列表中，选择 Skype for business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="8143c-116">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
7. <span data-ttu-id="8143c-117">单击 "**操作**"，然后单击 "**将所选用户移至池**"。</span><span class="sxs-lookup"><span data-stu-id="8143c-117">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="8143c-118">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="8143c-118">Click **OK**.</span></span>
  
8. <span data-ttu-id="8143c-119">验证用户的**注册池**列现在是否包含 Skype For business Server 2019 池，这表示用户已成功移动。</span><span class="sxs-lookup"><span data-stu-id="8143c-119">Verify that the **Registrar pool** column for the user now contains the Skype for Business Server 2019 pool, which indicates that the user has been successfully moved.</span></span> 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="8143c-120">使用 Skype for Business Server 2019 命令行管理程序移动用户</span><span class="sxs-lookup"><span data-stu-id="8143c-120">To move a user by using the Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="8143c-121">打开 Skype for Business 服务器命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="8143c-121">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="8143c-122">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="8143c-122">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. <span data-ttu-id="8143c-123">接下来，在命令行键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="8143c-123">Next, at the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. <span data-ttu-id="8143c-124">**RegistrarPool**标识现在指向 Skype For business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="8143c-124">The **RegistrarPool** identity now points to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="8143c-125">此标识的存在可确认用户已成功移动。</span><span class="sxs-lookup"><span data-stu-id="8143c-125">The presence of this identity confirms that the user has been successfully moved.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="8143c-126">有关**move-csuser** cmdlet 的详细信息，请运行： **Get-help move-csuser-详细**信息</span><span class="sxs-lookup"><span data-stu-id="8143c-126">For details about the **Get-CsUser** cmdlet, run: **Get-Help Get-CsUser -Detailed**</span></span>
  

