---
title: 业务服务器 Skype 中查看 PIN 策略信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 摘要： 查看用户 PIN 策略信息的 Skype 业务服务器。
ms.openlocfilehash: 37bb66dfb3d899057d1679c2438fd7e695349629
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919673"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a><span data-ttu-id="0a7cc-103">业务服务器 Skype 中查看 PIN 策略信息</span><span class="sxs-lookup"><span data-stu-id="0a7cc-103">View PIN policy information in Skype for Business Server</span></span>
 
<span data-ttu-id="0a7cc-104">**摘要：** 查看用户 PIN 策略信息的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="0a7cc-104">**Summary:** View a user's PIN policy information for Skype for Business Server.</span></span>
  
<span data-ttu-id="0a7cc-105">您可以使用视图个人识别号 (PIN) 身份验证的用户连接到业务与 IP 电话的 Skype **PIN 策略**选项卡。</span><span class="sxs-lookup"><span data-stu-id="0a7cc-105">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="0a7cc-106">要使用 PIN 身份验证，请确保在 Web 服务设置中选中“启用 PIN 身份验证”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0a7cc-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="0a7cc-107">按照以下步骤修改用户级别或站点级别的 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="0a7cc-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="0a7cc-108">以查看 PIN 策略的信息中 Skype 业务 Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="0a7cc-108">To view information about a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="0a7cc-109">从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="0a7cc-110">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="0a7cc-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="0a7cc-111">在左侧导航栏中，单击“安全性”\*\*\*\*，然后单击“PIN 策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0a7cc-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="0a7cc-112">在“PIN 策略”\*\*\*\* 页上，单击某个策略，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0a7cc-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0a7cc-113">使用 Windows PowerShell Cmdlet 查看 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="0a7cc-113">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0a7cc-114">您还可以使用 Windows PowerShell 和 Get-cspinpolicy cmdlet 查看 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="0a7cc-114">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="0a7cc-115">从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0a7cc-115">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0a7cc-116">有关使用远程 Windows PowerShell 连接到 Skype 业务服务器的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="0a7cc-116">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="0a7cc-117">过程是相同的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="0a7cc-117">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-pin-policies"></a><span data-ttu-id="0a7cc-118">查看 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="0a7cc-118">To view PIN policies</span></span>

<span data-ttu-id="0a7cc-119">若要查看有关所有 PIN 策略的信息，业务 Server 命令行管理程序 Skype 中键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="0a7cc-119">To view information about all your PIN policies, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```
  Get-CsPinPolicy
  ```

<span data-ttu-id="0a7cc-120">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="0a7cc-120">That will return information similar to this:</span></span>

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

<span data-ttu-id="0a7cc-121">有关详细信息，请参阅[Get-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="0a7cc-121">For more information, see the help topic for the [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0a7cc-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a7cc-122">See also</span></span>

[<span data-ttu-id="0a7cc-123">为 Business Server Skype 创建新的 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="0a7cc-123">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)
