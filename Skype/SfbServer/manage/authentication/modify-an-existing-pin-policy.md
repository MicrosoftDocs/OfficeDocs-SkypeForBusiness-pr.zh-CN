---
title: 在 Skype for Business Server 2015 中修改现有 PIN 策略
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
description: 摘要： 修改现有的 PIN 策略在 Skype 业务服务器 2015年。
ms.openlocfilehash: bb9be5807da0e72dfbc59d2000af82b181bfc6d6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="modify-an-existing-pin-policy-in-skype-for-business-server-2015"></a><span data-ttu-id="1dfb3-103">在 Skype for Business Server 2015 中修改现有 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="1dfb3-103">Modify an existing PIN policy in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1dfb3-104">**摘要：**修改现有的 PIN 策略在 Skype 业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="1dfb3-104">**Summary:** Modify an existing PIN policy in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="1dfb3-105">**PIN 策略**选项卡可用于连接到与 IP 电话业务的 Skype 为用户提供个人身份验证号码 (PIN) 身份验证。</span><span class="sxs-lookup"><span data-stu-id="1dfb3-105">You can use the **PIN Policy** tab to provide personal identification number (PIN) authentication to users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="1dfb3-106">要使用 PIN 身份验证，请确保在 Web 服务设置中选中“启用 PIN 身份验证”****。</span><span class="sxs-lookup"><span data-stu-id="1dfb3-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="1dfb3-107">按照以下步骤修改用户级别或站点级别的 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="1dfb3-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-modify-an-existing-pin-policy"></a><span data-ttu-id="1dfb3-108">修改现有的 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="1dfb3-108">To modify an existing PIN policy</span></span>

1.  <span data-ttu-id="1dfb3-109">从一个用户帐户，是 RTCUniversalServerAdmins 组的成员 （或具有相当的用户的权限），或者是指派到 CsServerAdministrator 或 CsAdministrator 的角色，在其中您部署 Skype 业务服务器的网络中任何计算机的登录2015。</span><span class="sxs-lookup"><span data-stu-id="1dfb3-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="1dfb3-110">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="1dfb3-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="1dfb3-111">在左侧导航栏中，单击“安全性”****，然后单击“PIN 策略”****。</span><span class="sxs-lookup"><span data-stu-id="1dfb3-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="1dfb3-112">在“PIN 策略”****页上，单击某个策略，再单击“编辑”****，然后单击“显示详细信息”****。</span><span class="sxs-lookup"><span data-stu-id="1dfb3-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="1dfb3-p102">在“编辑 PIN 策略”****的“最小 PIN 长度”****中，键入或选择希望允许的最小 PIN 长度。默认的最小长度为 5 位数。</span><span class="sxs-lookup"><span data-stu-id="1dfb3-p102">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
6. <span data-ttu-id="1dfb3-p103">为了能够指定锁定用户前允许的最大登录尝试次数，请选中“指定最大登录尝试数”****复选框。如果未选择此选项，允许的最大尝试次数将根据 PIN 长度自动确定。默认情况下，最大尝试次数自动确定。</span><span class="sxs-lookup"><span data-stu-id="1dfb3-p103">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
7. <span data-ttu-id="1dfb3-118">如果选中了“指定最大登录尝试数”****复选框，请在“最大登录尝试次数”****中键入或选择希望允许的最大登录尝试次数。</span><span class="sxs-lookup"><span data-stu-id="1dfb3-118">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
8. <span data-ttu-id="1dfb3-p104">要使 PIN 过期，请选中“启用 PIN 有效期”****复选框。如果未选择此选项，PIN 将永不过期。默认情况下，PIN 永不过期。</span><span class="sxs-lookup"><span data-stu-id="1dfb3-p104">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
9. <span data-ttu-id="1dfb3-122">如果选中了“启用 PIN 有效期”****复选框，请在“PIN 有效期(天)”****中键入或选择 PIN 保持有效的天数。</span><span class="sxs-lookup"><span data-stu-id="1dfb3-122">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
10. <span data-ttu-id="1dfb3-p105">在“PIN 历史记录计数”****中，键入用户可以重复使用某个 PIN 之前，必须创建的 PIN 数目。默认情况下，用户可以重复使用其 PIN。</span><span class="sxs-lookup"><span data-stu-id="1dfb3-p105">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
11. <span data-ttu-id="1dfb3-p106">要允许在 PIN 中使用数字的通用模式，如连续数字和重复数字集，请选中“允许通用模式”****复选框。如果未选择此选项，则仅允许使用数字的复杂模式。默认情况下，仅允许使用数字的复杂模式。</span><span class="sxs-lookup"><span data-stu-id="1dfb3-p106">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1dfb3-128">我们建议您不要允许使用通用模式。</span><span class="sxs-lookup"><span data-stu-id="1dfb3-128">We recommend that you do not allow common patterns.</span></span> 
  
12. <span data-ttu-id="1dfb3-129">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="1dfb3-129">Click **Commit**.</span></span>
    

