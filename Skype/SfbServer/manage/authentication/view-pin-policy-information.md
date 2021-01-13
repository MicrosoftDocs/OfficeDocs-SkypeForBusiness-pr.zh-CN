---
title: 在 Skype for Business Server 中查看 PIN 策略信息
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 摘要：查看 Skype for Business Server 的用户 PIN 策略信息。
ms.openlocfilehash: 4c223d5736df7f5f8ee1dbee11401a9fef2237cb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806522"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a><span data-ttu-id="1cddb-103">在 Skype for Business Server 中查看 PIN 策略信息</span><span class="sxs-lookup"><span data-stu-id="1cddb-103">View PIN policy information in Skype for Business Server</span></span>
 
<span data-ttu-id="1cddb-104">**摘要：** 查看 Skype for Business Server 的用户 PIN 策略信息。</span><span class="sxs-lookup"><span data-stu-id="1cddb-104">**Summary:** View a user's PIN policy information for Skype for Business Server.</span></span>
  
<span data-ttu-id="1cddb-105">可以使用 **"PIN** 策略"选项卡查看个人标识号 (PIN) IP 电话连接到 Skype for Business 的用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="1cddb-105">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="1cddb-106">要使用 PIN 身份验证，请确保在 Web 服务设置中选中“启用 PIN 身份验证”。</span><span class="sxs-lookup"><span data-stu-id="1cddb-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="1cddb-107">按照以下步骤修改用户级别或站点级别的 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="1cddb-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="1cddb-108">在 Skype for Business Server 控制面板中查看有关 PIN 策略的信息</span><span class="sxs-lookup"><span data-stu-id="1cddb-108">To view information about a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="1cddb-109">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="1cddb-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="1cddb-110">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="1cddb-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="1cddb-111">在左侧导航栏中，单击“安全性”，然后单击“PIN 策略”。</span><span class="sxs-lookup"><span data-stu-id="1cddb-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="1cddb-112">在 **"PIN 策略"** 页上，单击某个策略，再单击 **"** 编辑"，然后单击"**显示详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="1cddb-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1cddb-113">使用 cmdlet Windows PowerShell PIN 策略</span><span class="sxs-lookup"><span data-stu-id="1cddb-113">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1cddb-114">您还可以使用 Windows PowerShell 和 Get-CsPinPolicy cmdlet 查看 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="1cddb-114">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="1cddb-115">此 cmdlet 可以从 Skype for Business Server 命令行管理程序运行，也可以从远程会话Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1cddb-115">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1cddb-116">有关使用远程部署Windows PowerShell Skype for Business Server 的详细信息，请参阅博客文章"[快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="1cddb-116">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="1cddb-117">此过程在 Skype for Business Server 中相同。</span><span class="sxs-lookup"><span data-stu-id="1cddb-117">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-pin-policies"></a><span data-ttu-id="1cddb-118">查看 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="1cddb-118">To view PIN policies</span></span>

<span data-ttu-id="1cddb-119">若要查看有关所有 PIN 策略的信息，请在 Skype for Business Server 命令行管理程序 中键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="1cddb-119">To view information about all your PIN policies, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsPinPolicy
  ```

<span data-ttu-id="1cddb-120">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="1cddb-120">That will return information similar to this:</span></span>

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

<span data-ttu-id="1cddb-121">有关详细信息，请参阅 [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="1cddb-121">For more information, see the help topic for the [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1cddb-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1cddb-122">See also</span></span>

[<span data-ttu-id="1cddb-123">在 Skype for Business Server 中创建新的 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="1cddb-123">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)
