---
title: 为 Business Server Skype 创建新的 PIN 策略
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
description: 摘要： 为 Business Server Skype 创建新的 PIN 策略。
ms.openlocfilehash: 080b6efabc168d1d099c0f14abc394e8cd2d267a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20977555"
---
# <a name="create-a-new-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="6c9eb-103">为 Business Server Skype 创建新的 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="6c9eb-103">Create a new PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="6c9eb-104">**摘要：** 为 Business Server Skype 创建新的 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="6c9eb-104">**Summary:** Create a new PIN policy in Skype for Business Server.</span></span>
  
<span data-ttu-id="6c9eb-105">**PIN 策略**页可用于连接到业务与 IP 电话的 Skype 为用户提供个人识别号 (PIN) 身份验证。</span><span class="sxs-lookup"><span data-stu-id="6c9eb-105">You can use the **PIN Policy** page to provide personal identification number (PIN) authentication to users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="6c9eb-106">要使用 PIN 身份验证，请确保在 Web 服务设置中选中“启用 PIN 身份验证”****。</span><span class="sxs-lookup"><span data-stu-id="6c9eb-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="6c9eb-107">按照以下步骤创建用户级别或站点级别的 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="6c9eb-107">Follow these steps to create a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-create-a-user-or-site-pin-policy"></a><span data-ttu-id="6c9eb-108">创建用户或站点 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="6c9eb-108">To create a user or site PIN policy</span></span>

1.  <span data-ttu-id="6c9eb-109">从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.</span><span class="sxs-lookup"><span data-stu-id="6c9eb-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="6c9eb-110">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="6c9eb-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="6c9eb-111">在左侧导航栏中，单击“安全性”****，然后单击“PIN 策略”****。</span><span class="sxs-lookup"><span data-stu-id="6c9eb-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="6c9eb-112">在“PIN 策略”**** 页上，单击“新建”****，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="6c9eb-112">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="6c9eb-p102">要创建用户级别的策略，请单击“用户策略”****。在“新建 PIN 策略”**** 的“名称”**** 中，键入描述该策略的名称。</span><span class="sxs-lookup"><span data-stu-id="6c9eb-p102">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="6c9eb-p103">要创建站点级别的策略，请单击“站点策略”****。在“选择站点”**** 搜索字段中，键入要为其创建策略的站点的全部或部分名称。在得到的站点列表中，单击所需的站点，然后单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="6c9eb-p103">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="6c9eb-118">在“说明”**** 字段中，键入 PIN 策略的说明。</span><span class="sxs-lookup"><span data-stu-id="6c9eb-118">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="6c9eb-p104">在“最小 PIN 长度”**** 字段中，键入或选择希望允许的最小 PIN 长度。默认的最小长度为 5 位数。</span><span class="sxs-lookup"><span data-stu-id="6c9eb-p104">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="6c9eb-p105">为了能够指定锁定用户前允许的最大登录尝试次数，请选中“指定最大登录尝试数”**** 复选框。如果未选择此选项，允许的最大尝试次数将根据 PIN 长度自动确定。默认情况下，最大尝试次数自动确定。</span><span class="sxs-lookup"><span data-stu-id="6c9eb-p105">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="6c9eb-124">如果选中了“指定最大登录尝试数”**** 复选框，请在“最大登录尝试次数”**** 中键入或选择希望允许的最大登录尝试次数。</span><span class="sxs-lookup"><span data-stu-id="6c9eb-124">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="6c9eb-p106">要使 PIN 过期，请选中“启用 PIN 有效期”**** 复选框。如果未选择此选项，PIN 将永不过期。默认情况下，PIN 永不过期。</span><span class="sxs-lookup"><span data-stu-id="6c9eb-p106">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="6c9eb-128">如果选中了“启用 PIN 有效期”**** 复选框，请在“PIN 有效期(天)”**** 中键入或选择 PIN 保持有效的天数。</span><span class="sxs-lookup"><span data-stu-id="6c9eb-128">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="6c9eb-p107">在“PIN 历史记录计数”**** 中，键入用户可以重复使用某个 PIN 之前，必须创建的 PIN 数目。默认情况下，用户可以重复使用其 PIN。</span><span class="sxs-lookup"><span data-stu-id="6c9eb-p107">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="6c9eb-p108">要允许在 PIN 中使用数字的通用模式，如“1234”和“8888”，请选中“允许通用模式”**** 复选框。如果未选择此选项，则仅允许使用数字的复杂模式。默认情况下，仅允许使用数字的复杂模式。</span><span class="sxs-lookup"><span data-stu-id="6c9eb-p108">To allow common patterns of digits in PINs, such as "1234" and "8888", select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6c9eb-134">我们建议您不要允许使用通用模式。</span><span class="sxs-lookup"><span data-stu-id="6c9eb-134">We recommend that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="6c9eb-135">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="6c9eb-135">Click **Commit**.</span></span>
    

