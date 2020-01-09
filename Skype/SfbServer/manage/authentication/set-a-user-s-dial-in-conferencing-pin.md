---
title: 在 Skype for Business 服务器中设置用户的电话拨入式会议 PIN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: 摘要：为 Skype for business 服务器设置用户的电话拨入式会议 PIN 码。
ms.openlocfilehash: 83d1aae54d6e8be4f31b5bd27b6a568d6d88db1e
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992279"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a><span data-ttu-id="7f622-103">在 Skype for Business 服务器中设置用户的电话拨入式会议 PIN</span><span class="sxs-lookup"><span data-stu-id="7f622-103">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="7f622-104">**摘要：** 为 Skype for business 服务器设置用户的电话拨入式会议 PIN 码。</span><span class="sxs-lookup"><span data-stu-id="7f622-104">**Summary:** Set a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="7f622-105">若要将电话拨入式会议作为经过身份验证的用户加入，使用 Active Directory 域服务（AD DS）凭据的 Skype for business 服务器用户需要一个个人识别码（PIN）。</span><span class="sxs-lookup"><span data-stu-id="7f622-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="7f622-106">如果用户忘记了电话拨入式会议 PIN 或未使用 Skype for business 服务器设置 PIN，则可以从 Skype for business 服务器控制面板设置用户的 PIN。</span><span class="sxs-lookup"><span data-stu-id="7f622-106">If a user forgets the dial-in conferencing PIN or has not set the PIN by using Skype for Business Server, you can set the user's PIN from Skype for Business Server Control Panel.</span></span> <span data-ttu-id="7f622-107">可以自动生成 PIN，或手动创建 PIN。</span><span class="sxs-lookup"><span data-stu-id="7f622-107">You can automatically generate the PIN or create one manually.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7f622-p102">可以将 PIN 的具体特征（如 PIN 的最小长度）配置为策略。除了全局策略，您还可以为各个站点或用户配置 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="7f622-p102">Specific characteristics of the PIN, such as its minimum length, can be configured as a policy. In addition to the global policy, you can configure a PIN policy for individual sites or users.</span></span> 
  
### <a name="to-set-a-users-pin"></a><span data-ttu-id="7f622-110">设置用户的 PIN</span><span class="sxs-lookup"><span data-stu-id="7f622-110">To set a user's PIN</span></span>

1. <span data-ttu-id="7f622-111">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="7f622-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="7f622-112">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="7f622-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="7f622-113">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7f622-113">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="7f622-114">使用下列方法之一查找用户：</span><span class="sxs-lookup"><span data-stu-id="7f622-114">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="7f622-115">在“搜索用户”\*\*\*\* 框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7f622-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="7f622-116">如果具有保存的查询，请单击“打开查询”\*\*\*\* 图标，使用“打开”\*\*\*\* 对话框来检索该查询（.usf 文件），然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7f622-116">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="7f622-117">（可选）指定附加搜索条件以缩小结果的范围：</span><span class="sxs-lookup"><span data-stu-id="7f622-117">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="7f622-118">a.</span><span class="sxs-lookup"><span data-stu-id="7f622-118">a.</span></span> <span data-ttu-id="7f622-119">单击“添加筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7f622-119">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="7f622-120">b.</span><span class="sxs-lookup"><span data-stu-id="7f622-120">b.</span></span> <span data-ttu-id="7f622-121">通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。</span><span class="sxs-lookup"><span data-stu-id="7f622-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="7f622-122">c.</span><span class="sxs-lookup"><span data-stu-id="7f622-122">c.</span></span> <span data-ttu-id="7f622-123">在“等于”\*\*\*\* 下拉列表中，单击运算符（例如“等于”\*\*\*\* 或“不等于”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="7f622-123">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="7f622-124">d.</span><span class="sxs-lookup"><span data-stu-id="7f622-124">d.</span></span> <span data-ttu-id="7f622-125">根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。</span><span class="sxs-lookup"><span data-stu-id="7f622-125">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="7f622-126">要向查询中添加附加搜索子句，请单击“添加筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7f622-126">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="7f622-127">e.i.</span><span class="sxs-lookup"><span data-stu-id="7f622-127">e.</span></span> <span data-ttu-id="7f622-128">单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7f622-128">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7f622-p108">如果锁定了 PIN，则必须解锁 PIN，然后才能对其进行设置。要解锁 PIN，请单击用户，再单击“操作”\*\*\*\*，然后单击“解锁 PIN”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7f622-p108">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="7f622-131">在搜索结果中单击某个用户，再单击“操作”\*\*\*\*，然后单击“设置 PIN”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7f622-131">Click a user in the search results, click **Action**, and then click **Set PIN**.</span></span>
    
7. <span data-ttu-id="7f622-132">在“设置 PIN”\*\*\*\* 对话框中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="7f622-132">In the **Set PIN** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="7f622-133">若要允许 Skype for business 服务器生成用户的 PIN，请选择 "**自动生成有效的 pin** （默认值）"。</span><span class="sxs-lookup"><span data-stu-id="7f622-133">To allow Skype for Business Server to generate the user's PIN, select **Automatically generate a valid PIN** (the default).</span></span>
    
   - <span data-ttu-id="7f622-134">要创建您自己的 PIN，请单击“手动输入特定 PIN”\*\*\*\*，单击文本框，然后键入满足 PIN 策略设置中指定的 PIN 要求的 PIN。</span><span class="sxs-lookup"><span data-stu-id="7f622-134">To create your own PIN, click **Manually enter a specific PIN**, click the text box, and then type a PIN that meets the PIN requirements specified in your PIN policy settings.</span></span>
    
8. <span data-ttu-id="7f622-135">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="7f622-135">Click **OK**.</span></span>
    
9. <span data-ttu-id="7f622-136">在“设置 PIN”\*\*\*\* 中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="7f622-136">In **Set PIN**, do one of the following:</span></span> 
    
   - <span data-ttu-id="7f622-137">选中“显示 PIN”\*\*\*\* 复选框以查看 PIN，然后复制 PIN，并使用组织的首选方法将其传达给用户。</span><span class="sxs-lookup"><span data-stu-id="7f622-137">Select the **Show PIN** check box to see the PIN, and then copy the PIN and communicate it to the user using your organization's preferred method.</span></span>
    
   - <span data-ttu-id="7f622-p109">单击“打开我的电子邮件应用程序以将新 PIN 发送给用户”\*\*\*\* 以通过电子邮件发送 PIN。如果您使用 Microsoft Office Outlook 作为电子邮件客户端，则会自动将 PIN 复制到新的电子邮件。如果使用其他电子邮件客户端，请选中“显示 PIN”\*\*\*\* 复选框以查看 PIN，然后将其复制到电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7f622-p109">Click **Open my email application to send the new PIN to the user** to send the PIN by email. If Microsoft Office Outlook is your email client, the PIN is automatically copied into a new email message. If you use a different email client, select the **Show PIN** check box to see the PIN and then copy it into your email message.</span></span>
    
10. <span data-ttu-id="7f622-141">单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7f622-141">Click **Close**.</span></span>
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7f622-142">使用 Windows PowerShell Cmdlet 分配用户 PIN</span><span class="sxs-lookup"><span data-stu-id="7f622-142">Assigning a User PIN by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7f622-143">还可以使用 Set-CsClientPin cmdlet 分配 PIN 号码。</span><span class="sxs-lookup"><span data-stu-id="7f622-143">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span></span> <span data-ttu-id="7f622-144">你可以从 Skype for Business Server Management Shell 或 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7f622-144">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7f622-145">有关使用远程 Windows PowerShell 连接到 Skype for Business 服务器的详细信息，请参阅博客文章["快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="7f622-145">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="7f622-146">在 Skype for Business 服务器中，此过程是相同的。</span><span class="sxs-lookup"><span data-stu-id="7f622-146">The process is the same in Skype for Business Server.</span></span> 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a><span data-ttu-id="7f622-147">自动为用户分配 PIN 号码</span><span class="sxs-lookup"><span data-stu-id="7f622-147">To auto-assign a PIN number to a user</span></span>

<span data-ttu-id="7f622-148">以下命令可将 PIN 号码分配给用户 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="7f622-148">The following command assigns a PIN number to the user Ken Myer.</span></span> <span data-ttu-id="7f622-149">由于未包括引脚参数，因此 Skype for Business 服务器将自动生成并分配 PIN 码。</span><span class="sxs-lookup"><span data-stu-id="7f622-149">Because the Pin parameter is not included, Skype for Business Server will automatically generate and assign the PIN number.</span></span>
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a><span data-ttu-id="7f622-150">为用户分配特定 PIN 号码</span><span class="sxs-lookup"><span data-stu-id="7f622-150">To assign a specific PIN number to a user</span></span>

<span data-ttu-id="7f622-151">此命令使用 Pin 参数为用户 Ken Myer 分配 PIN 号码 121989。</span><span class="sxs-lookup"><span data-stu-id="7f622-151">This command uses the Pin parameter to assign the PIN number 121989 to the user Ken Myer.</span></span>
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

<span data-ttu-id="7f622-152">有关详细信息，请参阅[CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="7f622-152">For more information, see the help topic for the [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) cmdlet.</span></span>
  

