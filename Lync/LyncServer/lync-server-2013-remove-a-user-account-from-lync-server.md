---
title: Lync Server 2013：从 Lync Server 中删除用户帐户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a user account from Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49733596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97ee26fd15eb9df9174fd33cf9a45a6fe49411af
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-user-account-from-lync-server-2013"></a><span data-ttu-id="fbe50-102">从 Lync Server 2013 中删除用户帐户</span><span class="sxs-lookup"><span data-stu-id="fbe50-102">Remove a user account from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbe50-103">_**主题上次修改时间：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="fbe50-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="fbe50-104">你可以使用以下过程在 Lync Server 2013 中删除以前添加的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="fbe50-104">You can use the following procedure to remove a previously added user account in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fbe50-105">删除用户将导致你丢失为用户帐户配置的任何设置。</span><span class="sxs-lookup"><span data-stu-id="fbe50-105">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="fbe50-106">如果想要暂时禁用用户帐户，请参阅<A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">禁用或重新启用 Lync Server 2013 的用户帐户</A>主题。</span><span class="sxs-lookup"><span data-stu-id="fbe50-106">If you would like to temporarily disable a user account instead, see the topic <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a><span data-ttu-id="fbe50-107">使用 Lync Server 命令行管理程序删除用户帐户</span><span class="sxs-lookup"><span data-stu-id="fbe50-107">To remove a user account by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="fbe50-108">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="fbe50-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fbe50-109">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="fbe50-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fbe50-110">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="fbe50-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fbe50-111">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fbe50-111">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="fbe50-112">在 "**搜索用户**" 框中，键入要禁用或重新启用的用户帐户的所有或第一部分的显示名称、名字、姓氏、安全帐户管理器（SAM）帐户名称、SIP 地址或行统一资源标识符（URI），然后单击 "**查找**"。</span><span class="sxs-lookup"><span data-stu-id="fbe50-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="fbe50-113">在表中，单击要删除的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="fbe50-113">In the table, click the user account that you want to remove.</span></span>

6.  <span data-ttu-id="fbe50-114">在 "**操作**" 菜单上，选择 "**从 Lync Server 中删除**"，将出现一个对话框。</span><span class="sxs-lookup"><span data-stu-id="fbe50-114">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7.  <span data-ttu-id="fbe50-115">从对话框中，选择 **"确定"** 以删除用户。</span><span class="sxs-lookup"><span data-stu-id="fbe50-115">From the dialog box, select **OK** to remove the user.</span></span>

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fbe50-116">使用 Windows PowerShell Cmdlet 删除用户帐户</span><span class="sxs-lookup"><span data-stu-id="fbe50-116">Removing User Accounts by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fbe50-117">你可以使用 Move-csuser cmdlet 删除用户帐户。</span><span class="sxs-lookup"><span data-stu-id="fbe50-117">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="fbe50-118">此 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从远程会话 Windows PowerShell 运行。</span><span class="sxs-lookup"><span data-stu-id="fbe50-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="fbe50-119">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="fbe50-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-user-account"></a><span data-ttu-id="fbe50-120">删除用户帐户</span><span class="sxs-lookup"><span data-stu-id="fbe50-120">To remove a user account</span></span>

  - <span data-ttu-id="fbe50-121">若要删除用户帐户，请使用 Disable-Move-csuser cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fbe50-121">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="fbe50-122">例如：</span><span class="sxs-lookup"><span data-stu-id="fbe50-122">For example:</span></span>
    
        Disable-CsUser -Identity "Ken Myer"
    
    <span data-ttu-id="fbe50-123">此命令运行后，无法重新启用帐户及其以前的设置。</span><span class="sxs-lookup"><span data-stu-id="fbe50-123">After this command has run there is no way to re-enable the account and its previous settings.</span></span> <span data-ttu-id="fbe50-124">相反，你需要使用 Enable-Move-csuser cmdlet 为 Ken Myer 创建全新帐户。</span><span class="sxs-lookup"><span data-stu-id="fbe50-124">Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.</span></span>

</div>

<span data-ttu-id="fbe50-125">有关详细信息，请参阅 Disable cmdlet 的帮助主题[move-csuser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) 。</span><span class="sxs-lookup"><span data-stu-id="fbe50-125">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fbe50-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fbe50-126">See Also</span></span>


[<span data-ttu-id="fbe50-127">禁用或重新启用 Lync Server 2013 的用户帐户</span><span class="sxs-lookup"><span data-stu-id="fbe50-127">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="fbe50-128">启用和禁用 Lync Server 2013 的用户</span><span class="sxs-lookup"><span data-stu-id="fbe50-128">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

