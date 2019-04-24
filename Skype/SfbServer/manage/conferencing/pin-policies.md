---
title: 管理 Business Server （英文） 中 Skype 电话拨入式会议 PIN 策略
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: 摘要： 了解如何管理业务服务器中 Skype 电话拨入式会议 PIN 策略。
ms.openlocfilehash: 29fd3e2fff1628eaa96d7296e8fe9d7b9183d690
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197819"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="f4ce7-103">管理 Business Server （英文） 中 Skype 电话拨入式会议 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="f4ce7-103">Manage PIN policies for dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="f4ce7-104">**摘要：** 了解如何管理业务服务器中 Skype 电话拨入式会议 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-104">**Summary:** Learn how to manage PIN policies for dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="f4ce7-105">Skype 的组织中拥有 Active Directory 域服务 (AD DS) 凭据的企业服务器用户可以加入电话拨入式会议作为经过身份验证的用户使用个人标识号 (PIN)。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-105">Skype for Business Server users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="f4ce7-106">PIN 策略定义电话拨入式会议 PIN 工作方式的规则。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-106">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>
  
 <span data-ttu-id="f4ce7-p102">如果要在整个组织中使用相同的 PIN 策略，则可以使用全局 PIN 策略并根据需要对其进行修改。全局 PIN 策略在林级别定义电话拨入式会议 PIN 的规则。可以修改全局 PIN 策略，但是不能将其删除。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-p102">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed. The global PIN policy defines the rules for dial-in conferencing PINs at the forest level. You can modify the global PIN policy, but you cannot delete it.</span></span>
  
<span data-ttu-id="f4ce7-110">如果要将特定策略应用于某个站点或某个用户组，可以创建新的 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-110">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span>
  
<span data-ttu-id="f4ce7-111">PIN 策略既可以应用于少数用户，也可以应用于众多用户。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-111">PIN policies apply to users from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="f4ce7-112">如果为用户分配用户级别的 PIN 策略，则优先应用这些设置。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-112">If you assign a user-level PIN policy to a user, those settings take precedence.</span></span> <span data-ttu-id="f4ce7-113">如果没有分配用户策略，则将应用站点级别的 PIN 策略（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-113">If you do not assign a user policy, the site-level PIN policy applies, if it exists.</span></span> <span data-ttu-id="f4ce7-114">如果未应用用户策略或站点策略，则全局 PIN 策略会提供默认设置。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-114">If no user or site policies apply, global PIN policy provides the default settings.</span></span>
  
## <a name="view-information-about-pin-policies"></a><span data-ttu-id="f4ce7-115">查看有关 PIN 策略的信息</span><span class="sxs-lookup"><span data-stu-id="f4ce7-115">View information about PIN policies</span></span>

<span data-ttu-id="f4ce7-116">使用适用于业务 Server Control Panel Skype 或使用 Skype 业务 Server 命令行管理程序，您可以查看有关 PIN 策略的信息。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-116">You can view information about PIN policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f4ce7-117">查看有关使用适用于业务 Server Control Panel Skype 的 PIN 策略的信息</span><span class="sxs-lookup"><span data-stu-id="f4ce7-117">View information about PIN policies by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="f4ce7-118">从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.</span><span class="sxs-lookup"><span data-stu-id="f4ce7-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="f4ce7-119">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f4ce7-120">在左侧导航栏中，单击“**会议**”，然后单击“**PIN 策略**”。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-120">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="f4ce7-121">在“**PIN 策略**”页上，单击要查看的 PIN 策略，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-121">On the **PIN Policy** page, click the PIN policy that you want to view, click **Edit**, and then click **Show details**.</span></span>
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f4ce7-122">查看有关使用 Skype 业务 Server Management Shell 的 PIN 策略的信息</span><span class="sxs-lookup"><span data-stu-id="f4ce7-122">View information about PIN policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="f4ce7-123">若要查看有关 PIN 策略的信息，请使用 **Get-CsPinPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-123">To view information about PIN policies, use the **Get-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="f4ce7-124">例如，下面的命令返回有关 Identity 为 site:Redmond 的单个 PIN 策略的信息：</span><span class="sxs-lookup"><span data-stu-id="f4ce7-124">For example, the following command returns information about a single PIN policy with the Identity site:Redmond:</span></span>
  
```
Get-CsPinPolicy -Identity "site:Redmond"
```

<span data-ttu-id="f4ce7-125">有关详细信息，包括完整语法说明和参数的列表，，请参阅[Get-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-125">For more information, including a complete syntax description and list of parameters, see [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-the-global-pin-policy"></a><span data-ttu-id="f4ce7-126">修改全局 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="f4ce7-126">Modify the global PIN policy</span></span>

<span data-ttu-id="f4ce7-127">使用适用于业务 Server Control Panel Skype 或使用 Skype 业务 Server 命令行管理程序，您可以修改全局 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-127">You can modify the global PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f4ce7-128">使用适用于业务 Server Control Panel Skype 修改全局电话拨入式会议 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="f4ce7-128">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="f4ce7-129">从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.</span><span class="sxs-lookup"><span data-stu-id="f4ce7-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="f4ce7-130">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-130">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f4ce7-131">在左侧导航栏中，单击“**会议**”，然后单击“**PIN 策略**”。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-131">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="f4ce7-132">在“**PIN 策略**”页上，单击“**全局**”策略，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-132">On the **PIN Policy** page, click the **Global** policy, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="f4ce7-p105">在“编辑 PIN 策略”\*\*\*\* 的“最小 PIN 长度”\*\*\*\* 中，键入或选择希望允许的最小 PIN 长度。默认的最小长度为 5 位数。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-p105">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
6. <span data-ttu-id="f4ce7-p106">为了能够指定锁定用户前允许的最大登录尝试次数，请选中“指定最大登录尝试数”\*\*\*\* 复选框。如果未选择此选项，允许的最大尝试次数将根据 PIN 长度自动确定。默认情况下，最大尝试次数自动确定。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-p106">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
7. <span data-ttu-id="f4ce7-138">如果选中了“指定最大登录尝试数”\*\*\*\* 复选框，请在“最大登录尝试次数”\*\*\*\* 中键入或选择希望允许的最大登录尝试次数。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-138">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
8. <span data-ttu-id="f4ce7-p107">要使 PIN 过期，请选中“启用 PIN 有效期”\*\*\*\* 复选框。如果未选择此选项，PIN 将永不过期。默认情况下，PIN 永不过期。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-p107">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
9. <span data-ttu-id="f4ce7-142">如果选中了“启用 PIN 有效期”\*\*\*\* 复选框，请在“PIN 有效期(天)”\*\*\*\* 中键入或选择 PIN 保持有效的天数。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-142">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
10. <span data-ttu-id="f4ce7-p108">在“PIN 历史记录计数”\*\*\*\* 中，键入用户可以重复使用某个 PIN 之前，必须创建的 PIN 数目。默认情况下，用户可以重复使用其 PIN。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-p108">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
11. <span data-ttu-id="f4ce7-p109">要允许在 PIN 中使用数字的通用模式，如连续数字和重复数字集，请选中“允许通用模式”\*\*\*\* 复选框。如果未选择此选项，则仅允许使用数字的复杂模式。默认情况下，仅允许使用数字的复杂模式。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-p109">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f4ce7-148">出于安全原因，Microsoft 建议你不要允许使用通用模式。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-148">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
12. <span data-ttu-id="f4ce7-149">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-149">Click **Commit**.</span></span>
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f4ce7-150">使用 Skype 业务 Server 命令行管理程序修改全局电话拨入式会议 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="f4ce7-150">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="f4ce7-151">若要修改全局电话拨入式会议 PIN 策略，可使用 **Set-CsPinPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-151">To modify the global dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="f4ce7-p110">下面的命令更改配置为在组织中使用的所有 PIN 策略的 MinPasswordLength 的值。为执行此操作，该命令首先调用不带任何参数的 **Get-CsPinPolicy** cmdlet 以检索所有现有 PIN 策略的集合。然后，将此集合通过管道传递到 **Set-CsPinPolicy cmdlet**，后者将修改集合中每个策略的 MinPasswordLength 属性的值：</span><span class="sxs-lookup"><span data-stu-id="f4ce7-p110">The following command changes the value of the MinPasswordLength for all the PIN policies configured for use in the organization. To do this, the command first calls the **Get-CsPinPolicy** cmdlet without any parameters in order to retrieve a collection of all the existing PIN policies. That collection is then piped to the **Set-CsPinPolicy** cmdlet, which modifies the value of the MinPasswordLength property for each policy in the collection:</span></span>
  
```
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

<span data-ttu-id="f4ce7-155">有关详细信息，包括完整语法说明和参数的列表，，请参阅[Set-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-155">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="create-a-user-or-site-pin-policy"></a><span data-ttu-id="f4ce7-156">创建用户或站点 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="f4ce7-156">Create a user or site PIN policy</span></span>

<span data-ttu-id="f4ce7-157">使用适用于业务 Server Control Panel Skype 或使用 Skype 业务 Server 命令行管理程序，您可以创建的用户或站点 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-157">You can create a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f4ce7-158">使用适用于业务 Server Control Panel Skype 创建的用户或站点 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="f4ce7-158">Create a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f4ce7-159">从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.</span><span class="sxs-lookup"><span data-stu-id="f4ce7-159">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="f4ce7-160">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-160">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f4ce7-161">在左侧导航栏中，单击“**会议**”，然后单击“**PIN 策略**”。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-161">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="f4ce7-162">在“PIN 策略”\*\*\*\* 页上，单击“新建”\*\*\*\*，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="f4ce7-162">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="f4ce7-p111">要创建用户级别的策略，请单击“用户策略”\*\*\*\*。在“新建 PIN 策略”\*\*\*\* 的“名称”\*\*\*\* 中，键入描述该策略的名称。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-p111">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="f4ce7-p112">若要创建站点级别的策略，请单击“**站点策略**”。在“**选择站点**”搜索字段中，键入要为其创建策略的站点的全部或部分名称。在站点列表中，单击所需的站点，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-p112">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="f4ce7-168">在“说明”\*\*\*\* 字段中，键入 PIN 策略的说明。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-168">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="f4ce7-p113">在“最小 PIN 长度”\*\*\*\* 字段中，键入或选择希望允许的最小 PIN 长度。默认的最小长度为 5 位数。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-p113">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="f4ce7-p114">为了能够指定锁定用户前允许的最大登录尝试次数，请选中“指定最大登录尝试数”\*\*\*\* 复选框。如果未选择此选项，允许的最大尝试次数将根据 PIN 长度自动确定。默认情况下，最大尝试次数自动确定。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-p114">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="f4ce7-174">如果选中了“指定最大登录尝试数”\*\*\*\* 复选框，请在“最大登录尝试次数”\*\*\*\* 中键入或选择希望允许的最大登录尝试次数。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-174">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="f4ce7-p115">要使 PIN 过期，请选中“启用 PIN 有效期”\*\*\*\* 复选框。如果未选择此选项，PIN 将永不过期。默认情况下，PIN 永不过期。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-p115">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="f4ce7-178">如果选中了“启用 PIN 有效期”\*\*\*\* 复选框，请在“PIN 有效期(天)”\*\*\*\* 中键入或选择 PIN 保持有效的天数。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-178">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="f4ce7-p116">在“PIN 历史记录计数”\*\*\*\* 中，键入用户可以重复使用某个 PIN 之前，必须创建的 PIN 数目。默认情况下，用户可以重复使用其 PIN。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-p116">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="f4ce7-p117">要允许在 PIN 中使用数字的通用模式，如连续数字和重复数字集，请选中“允许通用模式”\*\*\*\* 复选框。如果未选择此选项，则仅允许使用数字的复杂模式。默认情况下，仅允许使用数字的复杂模式。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-p117">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f4ce7-184">出于安全原因，Microsoft 建议你不要允许使用通用模式。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-184">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="f4ce7-185">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-185">Click **Commit**.</span></span>
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f4ce7-186">使用 Skype 业务 Server 命令行管理程序创建的用户或站点 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="f4ce7-186">Create a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="f4ce7-187">若要创建用户或站点 PIN 策略，可使用 **New-CsPinPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-187">To create a user or site PIN policy, use the **New-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="f4ce7-p118">下面的命令创建 Identity 为 site:Redmond 的新 PIN 策略。此命令只包含一个可选参数 MinPasswordLength，该参数用于将 MinPasswordLength 属性设置为 7。其余所有策略属性都将配置为使用默认值。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-p118">The following command creates a new PIN policy with the Identity site:Redmond. This command includes just one optional parameter, MinPasswordLength, which is used to set the MinPasswordLength property to 7. All the remaining policy properties will be configured using the default values.</span></span>
  
```
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 <span data-ttu-id="f4ce7-191">有关详细信息，包括完整语法说明和参数的列表，，请参阅[新建 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-191">For more information, including a complete syntax description and list of parameters, see [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-a-user-or-site-pin-policy"></a><span data-ttu-id="f4ce7-192">修改用户或站点 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="f4ce7-192">Modify a user or site PIN policy</span></span>

<span data-ttu-id="f4ce7-193">使用适用于业务 Server Control Panel Skype 或使用 Skype 业务 Server 命令行管理程序，可以修改用户或站点 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-193">You can modify a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f4ce7-194">使用适用于业务 Server Control Panel Skype 修改的用户或站点 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="f4ce7-194">Modify a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="f4ce7-195">从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.</span><span class="sxs-lookup"><span data-stu-id="f4ce7-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="f4ce7-196">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-196">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f4ce7-197">在左侧导航栏中，单击“**会议**”，然后单击“**PIN 策略**”。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-197">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="f4ce7-198">在“**PIN 策略**”页上，单击要更改的 PIN 策略，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-198">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="f4ce7-199">在“**编辑 PIN 策略**”中，修改任意策略设置（不能修改的策略名称除外）。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-199">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>
    
6. <span data-ttu-id="f4ce7-200">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-200">Click **Commit**.</span></span>
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f4ce7-201">使用 Skype 业务 Server 命令行管理程序修改的用户或站点 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="f4ce7-201">Modify a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="f4ce7-202">若要修改电话拨入式会议 PIN 策略，可使用 **Set-CsPinPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-202">To modify the dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="f4ce7-p119">下面的命令修改分配给 Redmond 站点的 PIN 策略。在此示例中，此命令将 MinPasswordLength 属性的值更改为 10，这意味着新的 PIN 必须至少包含 10 位数字：</span><span class="sxs-lookup"><span data-stu-id="f4ce7-p119">The following command modifies the PIN policy assigned to the Redmond site. In this case, the command changes the value of the MinPasswordLength property to 10; that means that new PINs will have to contain at least 10 digits:</span></span>
  
```
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

<span data-ttu-id="f4ce7-205">有关详细信息，包括完整语法说明和参数的列表，，请参阅[Set-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-205">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="delete-a-user-or-site-pin-policy"></a><span data-ttu-id="f4ce7-206">删除用户或站点 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="f4ce7-206">Delete a user or site PIN policy</span></span>

<span data-ttu-id="f4ce7-207">使用适用于业务 Server Control Panel Skype 或使用 Skype 业务 Server 命令行管理程序，您可以删除用户或站点 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-207">You can delete a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f4ce7-208">使用适用于业务 Server Control Panel Skype 中删除用户或站点 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="f4ce7-208">Delete a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="f4ce7-209">从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.</span><span class="sxs-lookup"><span data-stu-id="f4ce7-209">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="f4ce7-210">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-210">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f4ce7-211">在左侧导航栏中，单击“**会议**”，然后单击“**PIN 策略**”。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-211">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="f4ce7-212">在“**PIN 策略**”页上，单击要更改的 PIN 策略，再单击“**编辑**”，然后单击“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-212">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Delete**.</span></span>
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f4ce7-213">使用 Skype 业务 Server 命令行管理程序中删除用户或站点 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="f4ce7-213">Delete a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="f4ce7-214">若要删除用户或站点 PIN 策略，可使用 **Remove-CsPinPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-214">To delete a user or site PIN policy, use the **Remove-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="f4ce7-p120">下面的命令将删除已在站点范围配置的所有 PIN 策略。为此，应使用带 Filter 参数的 **Get-CsPinPolicy** cmdlet 返回 Identity 以字符“site:”开头的所有策略的集合。然后将此集合通过管道传递到 **Remove-CsPinPolicy** cmdlet，后者会删除集合中的每一项：</span><span class="sxs-lookup"><span data-stu-id="f4ce7-p120">The following command removes all the PIN policies that have been configured at the site scope. To do this, use the **Get-CsPinPolicy** cmdlet, along with the Filter parameter, to return a collection of all the policies that have an Identity that begins with the characters "site:". This collection is then piped to the **Remove-CsPinPolicy** cmdlet, which deletes each policy in the collection:</span></span>
  
```
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

<span data-ttu-id="f4ce7-218">有关详细信息，包括完整语法说明和参数的列表，，请参阅[Remove-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="f4ce7-218">For more information, including a complete syntax description and list of parameters, see [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).</span></span>
  

