---
title: Lync Server 2013：禁用或重新启用 Lync Server 的用户帐户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aea86048fa29e9b6a21aa040093edff3f53ffe27
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="2ac6e-102">禁用或重新启用 Lync Server 2013 的用户帐户</span><span class="sxs-lookup"><span data-stu-id="2ac6e-102">Disable or re-enable user account for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ac6e-103">_**主题上次修改时间：** 2016-04-04_</span><span class="sxs-lookup"><span data-stu-id="2ac6e-103">_**Topic Last Modified:** 2016-04-04_</span></span>

<span data-ttu-id="2ac6e-104">可以使用以下过程在 Lync Server 2013 中禁用以前启用的用户帐户，而不会丢失为用户帐户配置的 Lync 服务器设置。</span><span class="sxs-lookup"><span data-stu-id="2ac6e-104">You can use the following procedure to disable a previously enabled user account in Lync Server 2013 without losing the Lync Server settings that you configured for the user account.</span></span> <span data-ttu-id="2ac6e-105">由于您不会丢失 Lync Server 用户帐户设置，因此您可以重新启用以前启用的用户帐户，而无需重新配置用户帐户。</span><span class="sxs-lookup"><span data-stu-id="2ac6e-105">Because you do not lose the Lync Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="2ac6e-106">仅在 Active Directory 中禁用用户帐户<STRONG>不会</STRONG>阻止用户登录或使用 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="2ac6e-106">Simply disabling a user account in Active Directory <STRONG>will not</STRONG> stop a user from being able to sign into or use Lync Server.</span></span> <span data-ttu-id="2ac6e-107">这是因为 Lync 使用可优化身份验证过程的证书身份验证，并且这些客户证书在180天内有效。</span><span class="sxs-lookup"><span data-stu-id="2ac6e-107">This is because Lync uses certificate authentication that streamlines the authentication process, and these client certificates are valid for 180 days.</span></span> <span data-ttu-id="2ac6e-108">如果你想要停止禁用已为 Lync 访问 Lync Server 而启用的 Active Directory 帐户，则必须使用<STRONG>move-csuser</STRONG> cmdlet，或使用<STRONG>Lync server 控制面板</STRONG>，如本文中所述。</span><span class="sxs-lookup"><span data-stu-id="2ac6e-108">If you want to stop disabled Active Directory accounts that had been enabled for Lync from having access to Lync Server, you must use the <STRONG>Disable-CsUser</STRONG> cmdlet, or use the <STRONG>Lync Server Control Panel</STRONG> as laid out in this article.</span></span> <span data-ttu-id="2ac6e-109">一旦用户在 Lync 中处于禁用状态，并且中央管理存储已复制到用户将无法再登录的环境中。</span><span class="sxs-lookup"><span data-stu-id="2ac6e-109">Once the user is disabled in Lync and the Central Management store has been replicated in the environment the users will no longer be able to sign in.</span></span> <span data-ttu-id="2ac6e-110">同样，已登录用户将断开连接。</span><span class="sxs-lookup"><span data-stu-id="2ac6e-110">Also, users that are signed in will get disconnected.</span></span>



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a><span data-ttu-id="2ac6e-111">为 Lync Server 禁用或重新启用以前启用的用户帐户</span><span class="sxs-lookup"><span data-stu-id="2ac6e-111">To disable or re-enable a previously enabled user account for Lync Server</span></span>

1.  <span data-ttu-id="2ac6e-112">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="2ac6e-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2ac6e-113">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="2ac6e-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2ac6e-114">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="2ac6e-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2ac6e-115">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2ac6e-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="2ac6e-116">在 "**搜索用户**" 框中，键入要禁用或重新启用的用户帐户的所有或第一部分的显示名称、名字、姓氏、安全帐户管理器（SAM）帐户名称、SIP 地址或行统一资源标识符（URI），然后单击 "**查找**"。</span><span class="sxs-lookup"><span data-stu-id="2ac6e-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="2ac6e-117">在表中，单击要禁用或重新启用的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="2ac6e-117">In the table, click the user account that you want to disable or re-enable.</span></span>

6.  <span data-ttu-id="2ac6e-118">在 "**操作**" 菜单上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="2ac6e-118">On the **Action** menu, do one of the following:</span></span>
    
      - <span data-ttu-id="2ac6e-119">若要暂时禁用 Lync Server 2013 的用户帐户，请单击 " **Lync Server 暂时禁用**"。</span><span class="sxs-lookup"><span data-stu-id="2ac6e-119">To temporarily disable the user account for Lync Server 2013, click **Temporarily disable for Lync Server**.</span></span>
    
      - <span data-ttu-id="2ac6e-120">若要启用 Lync Server 2013 的用户帐户，请单击 " **Lync Server 重新启用**"。</span><span class="sxs-lookup"><span data-stu-id="2ac6e-120">To enable the user account for Lync Server 2013, click **Re-enable for Lync Server**.</span></span>

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="2ac6e-121">使用 Windows PowerShell 禁用或重新启用用户帐户</span><span class="sxs-lookup"><span data-stu-id="2ac6e-121">Using Windows PowerShell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="2ac6e-122">用户帐户可以暂时禁用，然后在稍后通过使用**move-csuser** cmdlet 重新启用。</span><span class="sxs-lookup"><span data-stu-id="2ac6e-122">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="2ac6e-123">你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2ac6e-123">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2ac6e-124">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="2ac6e-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-disable-a-user-account"></a><span data-ttu-id="2ac6e-125">禁用用户帐户</span><span class="sxs-lookup"><span data-stu-id="2ac6e-125">To disable a user account</span></span>

  - <span data-ttu-id="2ac6e-126">若要暂时禁用用户帐户，请将 Enabled 属性的值设置为 False （$False）。</span><span class="sxs-lookup"><span data-stu-id="2ac6e-126">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="2ac6e-127">例如：</span><span class="sxs-lookup"><span data-stu-id="2ac6e-127">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a><span data-ttu-id="2ac6e-128">重新启用用户帐户</span><span class="sxs-lookup"><span data-stu-id="2ac6e-128">To re-enable a user account</span></span>

  - <span data-ttu-id="2ac6e-129">若要重新启用已禁用的用户帐户，请将 Enabled 属性的值设置为 True （$True）。</span><span class="sxs-lookup"><span data-stu-id="2ac6e-129">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="2ac6e-130">例如：</span><span class="sxs-lookup"><span data-stu-id="2ac6e-130">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

<span data-ttu-id="2ac6e-131">有关详细信息，请参阅[move-csuser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="2ac6e-131">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2ac6e-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ac6e-132">See Also</span></span>


[<span data-ttu-id="2ac6e-133">为 Lync Server 2013 添加和启用用户帐户</span><span class="sxs-lookup"><span data-stu-id="2ac6e-133">Add and enable user account for Lync Server 2013</span></span>](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="2ac6e-134">启用和禁用 Lync Server 2013 的用户</span><span class="sxs-lookup"><span data-stu-id="2ac6e-134">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

