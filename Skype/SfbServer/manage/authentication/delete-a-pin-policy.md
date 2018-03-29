---
title: 在 Skype for Business Server 2015 中删除 PIN 策略
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 摘要： 删除业务服务器 2015年的 Skype 用户的拨入会议针。
ms.openlocfilehash: b64a4509105214358549f320cf8885d6386986f7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="delete-a-pin-policy-in-skype-for-business-server-2015"></a><span data-ttu-id="5b5d3-103">在 Skype for Business Server 2015 中删除 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="5b5d3-103">Delete a PIN policy in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5b5d3-104">**摘要：**删除业务服务器 2015年的 Skype 用户的拨入会议针。</span><span class="sxs-lookup"><span data-stu-id="5b5d3-104">**Summary:** Delete a user's dial-in conferencing PIN for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5b5d3-105">按照以下步骤删除个人标识号 (PIN) 策略。</span><span class="sxs-lookup"><span data-stu-id="5b5d3-105">Follow these steps to delete a personal identification number (PIN) policy.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5b5d3-106">无法删除全局 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="5b5d3-106">You cannot delete the global PIN policy.</span></span> 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="5b5d3-107">删除业务服务器控件面板中 Skype 的 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="5b5d3-107">To delete a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="5b5d3-108">从一个用户帐户，是 RTCUniversalServerAdmins 组的成员 （或具有相当的用户的权限），或者是指派到 CsServerAdministrator 或 CsAdministrator 的角色，在其中您部署 Skype 业务服务器的网络中任何计算机的登录2015。</span><span class="sxs-lookup"><span data-stu-id="5b5d3-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="5b5d3-109">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="5b5d3-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="5b5d3-110">在左侧导航栏中，单击“安全性”****，然后单击“PIN 策略”****。</span><span class="sxs-lookup"><span data-stu-id="5b5d3-110">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="5b5d3-111">在“PIN 策略”****页上的搜索字段中，键入要删除的策略的全部或部分名称。</span><span class="sxs-lookup"><span data-stu-id="5b5d3-111">On the **PIN Policy** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="5b5d3-112">在策略列表中，单击所需的策略，再单击“编辑”****，然后单击“删除”****。</span><span class="sxs-lookup"><span data-stu-id="5b5d3-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="5b5d3-113">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="5b5d3-113">Click **OK**.</span></span>
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5b5d3-114">使用 Windows PowerShell Cmdlet 移除 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="5b5d3-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5b5d3-115">您可以通过使用 Windows PowerShell 和删除 CsPinPolicy cmdlet 删除 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="5b5d3-115">You can delete PIN policies by using Windows PowerShell and the Remove-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="5b5d3-116">可以从 Skype 业务服务器管理外壳程序或从 Windows PowerShell 的远程会话来运行该 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5b5d3-116">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5b5d3-117">有关使用远程 Windows PowerShell Skype 业务服务器的连接的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync 服务器 2010年使用远程 PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="5b5d3-117">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="5b5d3-118">该过程是相同的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="5b5d3-118">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-pin-policy"></a><span data-ttu-id="5b5d3-119">删除特定 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="5b5d3-119">To remove a specific PIN policy</span></span>

- <span data-ttu-id="5b5d3-120">以下命令使用 Identity RedmondPinPolicy 删除 PIN 策略：</span><span class="sxs-lookup"><span data-stu-id="5b5d3-120">This command removes the PIN policy with the Identity RedmondPinPolicy:</span></span>
    
  ```
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a><span data-ttu-id="5b5d3-121">删除适用于站点范围的所有 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="5b5d3-121">To remove all the PIN policies applied to the site scope</span></span>

- <span data-ttu-id="5b5d3-122">以下命令删除在站点作用域配置的所有 PIN 策略：</span><span class="sxs-lookup"><span data-stu-id="5b5d3-122">This command removes all the PIN policies configured at the site scope:</span></span>
    
  ```
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a><span data-ttu-id="5b5d3-123">删除允许使用通用模式的所有 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="5b5d3-123">To remove all the PIN policies that allow the use of common patterns</span></span>

- <span data-ttu-id="5b5d3-124">以下命令删除允许使用通用模式的所有 PIN 策略：G</span><span class="sxs-lookup"><span data-stu-id="5b5d3-124">And this one removes all the PIN policies that allow the use of common patterns:G</span></span>
    
  ```
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

<span data-ttu-id="5b5d3-125">有关详细信息，请参阅[删除 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="5b5d3-125">For more information, see the help topic for the [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  

