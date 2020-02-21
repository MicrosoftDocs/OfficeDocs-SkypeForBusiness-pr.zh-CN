---
title: Lync Server 2013：设置用户的电话拨入式会议 PIN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a user's dial-in conferencing PIN
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520985(v=OCS.15)
ms:contentKeyID: 48183970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad28eb7214cb6762e8b0941f22da8b97966e9024
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200678"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-a-users-dial-in-conferencing-pin-in-lync-server-2013"></a><span data-ttu-id="58a51-102">在 Lync Server 2013 中设置用户的电话拨入式会议 PIN</span><span class="sxs-lookup"><span data-stu-id="58a51-102">Set a user's dial-in conferencing PIN in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58a51-103">_**上次修改的主题：** 2014-06-10_</span><span class="sxs-lookup"><span data-stu-id="58a51-103">_**Topic Last Modified:** 2014-06-10_</span></span>

<span data-ttu-id="58a51-104">若要以已通过身份验证的用户身份加入电话拨入式会议，则具有 Active Directory 域服务（AD DS）凭据的 Lync Server 2013 用户需要一个个人标识号（PIN）。</span><span class="sxs-lookup"><span data-stu-id="58a51-104">To join a dial-in conference as an authenticated user, a Lync Server 2013 user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="58a51-105">如果用户忘记了电话拨入式会议 PIN，或者没有使用 Lync Server 设置 PIN，则可以从 Lync Server 控制面板设置用户的 PIN。</span><span class="sxs-lookup"><span data-stu-id="58a51-105">If a user forgets the dial-in conferencing PIN or has not set the PIN by using Lync Server, you can set the user’s PIN from Lync Server Control Panel.</span></span> <span data-ttu-id="58a51-106">可以自动生成 PIN，或手动创建 PIN。</span><span class="sxs-lookup"><span data-stu-id="58a51-106">You can automatically generate the PIN or create one manually.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="58a51-107">可以将 PIN 的具体特征（如 PIN 的最小长度）配置为策略。</span><span class="sxs-lookup"><span data-stu-id="58a51-107">Specific characteristics of the PIN, such as its minimum length, can be configured as a policy.</span></span> <span data-ttu-id="58a51-108">除了全局策略，您还可以为各个站点或用户配置 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="58a51-108">In addition to the global policy, you can configure a PIN policy for individual sites or users.</span></span> <span data-ttu-id="58a51-109">有关配置 PIN 策略的详细信息，请参阅<A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">在 Lync Server 2013 中配置电话拨入式会议个人标识号码（PIN）规则</A>。</span><span class="sxs-lookup"><span data-stu-id="58a51-109">For details about configuring a PIN policy, see <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-set-a-users-pin"></a><span data-ttu-id="58a51-110">设置用户的 PIN</span><span class="sxs-lookup"><span data-stu-id="58a51-110">To set a user’s PIN</span></span>

1.  <span data-ttu-id="58a51-111">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="58a51-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="58a51-112">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="58a51-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="58a51-113">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="58a51-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="58a51-114">在左侧导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="58a51-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="58a51-115">使用下列方法之一查找用户：</span><span class="sxs-lookup"><span data-stu-id="58a51-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="58a51-116">在“搜索用户”\*\*\*\* 框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="58a51-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="58a51-117">如果具有保存的查询，请单击“打开查询”\*\*\*\* 图标，使用“打开”\*\*\*\* 对话框来检索该查询（.usf 文件），然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="58a51-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="58a51-118">（可选）指定附加搜索条件以缩小结果的范围：</span><span class="sxs-lookup"><span data-stu-id="58a51-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="58a51-119">单击“添加筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="58a51-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="58a51-120">通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。</span><span class="sxs-lookup"><span data-stu-id="58a51-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="58a51-121">在“等于”\*\*\*\* 下拉列表中，单击运算符（例如“等于”\*\*\*\* 或“不等于”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="58a51-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="58a51-122">根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。</span><span class="sxs-lookup"><span data-stu-id="58a51-122">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="58a51-123">要向查询中添加附加搜索子句，请单击“添加筛选器”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="58a51-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="58a51-124">单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="58a51-124">Click **Find**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="58a51-p104">如果锁定了 PIN，则必须解锁 PIN，然后才能对其进行设置。要解锁 PIN，请单击用户，再单击“操作”<STRONG></STRONG>，然后单击“解锁 PIN”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="58a51-p104">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click <STRONG>Action</STRONG>, and then click <STRONG>Unlock PIN</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="58a51-127">在搜索结果中单击某个用户，再单击“操作”\*\*\*\*，然后单击“设置 PIN”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="58a51-127">Click a user in the search results, click **Action**, and then click **Set PIN**.</span></span>

7.  <span data-ttu-id="58a51-128">在“设置 PIN”\*\*\*\* 对话框中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="58a51-128">In the **Set PIN** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="58a51-129">若要允许 Lync Server 2013 生成用户的 PIN，请选择 "**自动生成有效 PIN** （默认值）"。</span><span class="sxs-lookup"><span data-stu-id="58a51-129">To allow Lync Server 2013 to generate the user’s PIN, select **Automatically generate a valid PIN** (the default).</span></span>
    
      - <span data-ttu-id="58a51-130">要创建您自己的 PIN，请单击“手动输入特定 PIN”\*\*\*\*，单击文本框，然后键入满足 PIN 策略设置中指定的 PIN 要求的 PIN。</span><span class="sxs-lookup"><span data-stu-id="58a51-130">To create your own PIN, click **Manually enter a specific PIN**, click the text box, and then type a PIN that meets the PIN requirements specified in your PIN policy settings.</span></span>

8.  <span data-ttu-id="58a51-131">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="58a51-131">Click **OK**.</span></span>

9.  <span data-ttu-id="58a51-132">在“设置 PIN”\*\*\*\* 中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="58a51-132">In **Set PIN**, do one of the following:</span></span>
    
      - <span data-ttu-id="58a51-133">选中“显示 PIN”\*\*\*\* 复选框以查看 PIN，然后复制 PIN，并使用组织的首选方法将其传达给用户。</span><span class="sxs-lookup"><span data-stu-id="58a51-133">Select the **Show PIN** check box to see the PIN, and then copy the PIN and communicate it to the user using your organization's preferred method.</span></span>
    
      - <span data-ttu-id="58a51-p105">单击“打开我的电子邮件应用程序以将新 PIN 发送给用户”\*\*\*\* 以通过电子邮件发送 PIN。如果您使用 Microsoft Office Outlook 作为电子邮件客户端，则会自动将 PIN 复制到新的电子邮件。如果使用其他电子邮件客户端，请选中“显示 PIN”\*\*\*\* 复选框以查看 PIN，然后将其复制到电子邮件。</span><span class="sxs-lookup"><span data-stu-id="58a51-p105">Click **Open my email application to send the new PIN to the user** to send the PIN by email. If Microsoft Office Outlook is your email client, the PIN is automatically copied into a new email message. If you use a different email client, select the **Show PIN** check box to see the PIN and then copy it into your email message.</span></span>

10. <span data-ttu-id="58a51-137">单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="58a51-137">Click **Close**.</span></span>

</div>

<div>

## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="58a51-138">使用 Windows PowerShell Cmdlet 分配用户 PIN</span><span class="sxs-lookup"><span data-stu-id="58a51-138">Assigning a User PIN by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="58a51-139">您还可以使用 Unlock-csclientpin cmdlet 分配 PIN 号码。</span><span class="sxs-lookup"><span data-stu-id="58a51-139">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span></span> <span data-ttu-id="58a51-140">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="58a51-140">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="58a51-141">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="58a51-141">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-auto-assign-a-pin-number-to-a-user"></a><span data-ttu-id="58a51-142">将 PIN 号码自动分配给用户</span><span class="sxs-lookup"><span data-stu-id="58a51-142">To auto-assign a PIN number to a user</span></span>

  - <span data-ttu-id="58a51-143">以下命令可将 PIN 号码分配给用户 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="58a51-143">The following command assigns a PIN number to the user Ken Myer.</span></span> <span data-ttu-id="58a51-144">由于不包含 Pin 参数，因此 Lync Server 将自动生成并分配 PIN 号码。</span><span class="sxs-lookup"><span data-stu-id="58a51-144">Because the Pin parameter is not included, Lync Server will automatically generate and assign the PIN number.</span></span>
    
        Set-CsClientPin -Identity "Ken Myer" 

</div>

<div>

## <a name="to-assign-a-specific-pin-number-to-a-user"></a><span data-ttu-id="58a51-145">为用户分配特定的 PIN 号码</span><span class="sxs-lookup"><span data-stu-id="58a51-145">To assign a specific PIN number to a user</span></span>

  - <span data-ttu-id="58a51-146">此命令使用 Pin 参数为用户 Ken Myer 分配 PIN 号码 121989。</span><span class="sxs-lookup"><span data-stu-id="58a51-146">This command uses the Pin parameter to assign the PIN number 121989 to the user Ken Myer.</span></span>
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

</div>

<span data-ttu-id="58a51-147">有关详细信息，请参阅[unlock-csclientpin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="58a51-147">For more information, see the help topic for the [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="58a51-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58a51-148">See Also</span></span>


<span data-ttu-id="58a51-149">[拨入访问号码](https://technet.microsoft.com/library/gg133674\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="58a51-149">[Dial-in Access Number](https://technet.microsoft.com/library/gg133674\(v=ocs.15\))</span></span>  


[<span data-ttu-id="58a51-150">在 Lync Server 2013 中配置电话拨入式会议个人标识号码（PIN）规则</span><span class="sxs-lookup"><span data-stu-id="58a51-150">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

