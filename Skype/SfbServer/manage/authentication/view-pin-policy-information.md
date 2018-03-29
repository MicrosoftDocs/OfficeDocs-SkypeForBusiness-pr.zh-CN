---
title: 在 Skype for Business Server 2015 中查看 PIN 策略信息
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 摘要： 查看用户的 PIN 策略信息的 Skype 业务服务器 2015年。
ms.openlocfilehash: 3b62dae5cbd29c4622e30c6369a498eb48e126c7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="view-pin-policy-information-in-skype-for-business-server-2015"></a><span data-ttu-id="5f433-103">在 Skype for Business Server 2015 中查看 PIN 策略信息</span><span class="sxs-lookup"><span data-stu-id="5f433-103">View PIN policy information in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5f433-104">**摘要：**查看用户的 PIN 策略信息的 Skype 业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="5f433-104">**Summary:** View a user's PIN policy information for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5f433-105">您可以使用视图个人标识号码 (PIN) 身份验证的用户连接到与 IP 电话业务的 Skype **PIN 策略**选项卡。</span><span class="sxs-lookup"><span data-stu-id="5f433-105">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="5f433-106">要使用 PIN 身份验证，请确保在 Web 服务设置中选中“启用 PIN 身份验证”****。</span><span class="sxs-lookup"><span data-stu-id="5f433-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="5f433-107">按照以下步骤修改用户级别或站点级别的 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="5f433-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="5f433-108">在 Skype 业务服务器控件面板查看 PIN 策略信息</span><span class="sxs-lookup"><span data-stu-id="5f433-108">To view information about a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="5f433-109">从一个用户帐户，是 RTCUniversalServerAdmins 组的成员 （或具有相当的用户的权限），或者是指派到 CsServerAdministrator 或 CsAdministrator 的角色，在其中您部署 Skype 业务服务器的网络中任何计算机的登录2015。</span><span class="sxs-lookup"><span data-stu-id="5f433-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="5f433-110">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="5f433-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="5f433-111">在左侧导航栏中，单击“安全性”****，然后单击“PIN 策略”****。</span><span class="sxs-lookup"><span data-stu-id="5f433-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="5f433-112">在“PIN 策略”****页上，单击某个策略，再单击“编辑”****，然后单击“显示详细信息”****。</span><span class="sxs-lookup"><span data-stu-id="5f433-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5f433-113">查看通过使用 Windows PowerShell Cmdlet 的 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="5f433-113">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5f433-114">您还可以查看通过使用 Windows PowerShell 和 Get CsPinPolicy cmdlet 的 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="5f433-114">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="5f433-115">从业务服务器管理外壳的 Skype 或 Windows PowerShell 的远程会话，则可以运行该 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5f433-115">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5f433-116">有关使用远程 Windows PowerShell Skype 业务服务器的连接的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync 服务器 2010年使用远程 PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="5f433-116">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="5f433-117">该过程是相同的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="5f433-117">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-pin-policies"></a><span data-ttu-id="5f433-118">查看 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="5f433-118">To view PIN policies</span></span>

<span data-ttu-id="5f433-119">要查看所有 PIN 策略有关的信息，请键入下面的命令在 Skype 的业务服务器管理外壳程序，然后按 enter 键：</span><span class="sxs-lookup"><span data-stu-id="5f433-119">To view information about all your PIN policies, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```
  Get-CsPinPolicy
  ```

<span data-ttu-id="5f433-120">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="5f433-120">That will return information similar to this:</span></span>

  ```
  Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
  ```

<span data-ttu-id="5f433-121">有关详细信息，请参阅有关[获取 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="5f433-121">For more information, see the help topic for the [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5f433-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f433-122">See also</span></span>

#### 

[<span data-ttu-id="5f433-123">在 Skype 为业务服务器 2015年中创建的新 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="5f433-123">Create a new PIN policy in Skype for Business Server 2015</span></span>](create-a-new-pin-policy.md)

