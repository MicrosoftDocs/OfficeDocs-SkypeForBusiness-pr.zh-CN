---
title: 在 Skype for Business 服务器中删除 PIN 策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: '摘要: 删除用户的 Skype for business 服务器的电话拨入式会议 PIN。'
ms.openlocfilehash: 2f42531480ac4099d574a21a96f1954abc70d1d3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283778"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="104a9-103">在 Skype for Business 服务器中删除 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="104a9-103">Delete a PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="104a9-104">**摘要:** 删除用户的 Skype for business 服务器的电话拨入式会议 PIN。</span><span class="sxs-lookup"><span data-stu-id="104a9-104">**Summary:** Delete a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="104a9-105">按照以下步骤删除个人标识号 (PIN) 策略。</span><span class="sxs-lookup"><span data-stu-id="104a9-105">Follow these steps to delete a personal identification number (PIN) policy.</span></span>
  
> [!NOTE]
> <span data-ttu-id="104a9-106">无法删除全局 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="104a9-106">You cannot delete the global PIN policy.</span></span> 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="104a9-107">在 "Skype for Business 服务器控制面板" 中删除 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="104a9-107">To delete a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="104a9-108">从 RTCUniversalServerAdmins 组的成员 (或具有等效用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户, 登录到你部署了 Skype for Business 服务器的网络中的任何计算机.</span><span class="sxs-lookup"><span data-stu-id="104a9-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="104a9-109">打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="104a9-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="104a9-110">在左侧导航栏中，单击“安全性”\*\*\*\*，然后单击“PIN 策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="104a9-110">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="104a9-111">在“PIN 策略”\*\*\*\* 页上的搜索字段中，键入要删除的策略的全部或部分名称。</span><span class="sxs-lookup"><span data-stu-id="104a9-111">On the **PIN Policy** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="104a9-112">在策略列表中，单击所需的策略，再单击“编辑”\*\*\*\*，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="104a9-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="104a9-113">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="104a9-113">Click **OK**.</span></span>
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="104a9-114">使用 Windows PowerShell Cmdlet 删除 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="104a9-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="104a9-115">你可以使用 Windows PowerShell 和 CsPinPolicy cmdlet 删除 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="104a9-115">You can delete PIN policies by using Windows PowerShell and the Remove-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="104a9-116">你可以从 Skype for Business Server Management Shell 或 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="104a9-116">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="104a9-117">有关使用远程 Windows PowerShell 连接到 Skype for Business 服务器的详细信息, 请参阅博客文章["快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="104a9-117">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="104a9-118">在 Skype for Business 服务器中, 此过程是相同的。</span><span class="sxs-lookup"><span data-stu-id="104a9-118">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-pin-policy"></a><span data-ttu-id="104a9-119">删除特定 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="104a9-119">To remove a specific PIN policy</span></span>

- <span data-ttu-id="104a9-120">以下命令使用 Identity RedmondPinPolicy 删除 PIN 策略：</span><span class="sxs-lookup"><span data-stu-id="104a9-120">This command removes the PIN policy with the Identity RedmondPinPolicy:</span></span>
    
  ```
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a><span data-ttu-id="104a9-121">删除适用于站点范围的所有 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="104a9-121">To remove all the PIN policies applied to the site scope</span></span>

- <span data-ttu-id="104a9-122">以下命令删除在站点作用域配置的所有 PIN 策略：</span><span class="sxs-lookup"><span data-stu-id="104a9-122">This command removes all the PIN policies configured at the site scope:</span></span>
    
  ```
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a><span data-ttu-id="104a9-123">删除允许使用通用模式的所有 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="104a9-123">To remove all the PIN policies that allow the use of common patterns</span></span>

- <span data-ttu-id="104a9-124">以下命令删除允许使用通用模式的所有 PIN 策略：G</span><span class="sxs-lookup"><span data-stu-id="104a9-124">And this one removes all the PIN policies that allow the use of common patterns:G</span></span>
    
  ```
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

<span data-ttu-id="104a9-125">有关详细信息, 请参阅[CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="104a9-125">For more information, see the help topic for the [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  

