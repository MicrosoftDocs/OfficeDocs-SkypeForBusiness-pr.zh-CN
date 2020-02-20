---
title: Lync Server 2013：重置外部用户访问的全局策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset the global policy for external user access
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e925043af26fd6b3226e42309ffa7033c645a2e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reset-the-global-policy-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="36ff6-102">在 Lync Server 2013 中重置外部用户访问的全局策略</span><span class="sxs-lookup"><span data-stu-id="36ff6-102">Reset the global policy for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36ff6-103">_**上次修改的主题：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="36ff6-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="36ff6-p101">无法完全删除全局策略。使用全局策略的“删除”\*\*\*\* 选项只能将全局策略重置为默认设置，不包括对任何外部用户访问选项的支持。</span><span class="sxs-lookup"><span data-stu-id="36ff6-p101">You cannot completely delete a global policy. Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

<div>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="36ff6-106">将全局策略重置为默认设置</span><span class="sxs-lookup"><span data-stu-id="36ff6-106">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="36ff6-107">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="36ff6-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="36ff6-108">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="36ff6-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="36ff6-109">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="36ff6-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="36ff6-110">在左侧导航栏中，单击“外部用户访问”\*\*\*\*，然后单击“外部访问策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="36ff6-110">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="36ff6-111">在“外部访问策略”\*\*\*\* 选项卡上，单击全局策略，再单击“编辑”\*\*\*\*，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="36ff6-111">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="36ff6-p103">当系统提示您确认删除时，单击“确定”\*\*\*\*。此时会在页面顶部显示一条消息，通知您已重置全局策略。</span><span class="sxs-lookup"><span data-stu-id="36ff6-p103">When prompted to confirm the deletion, click **OK**. A message appears at the top of the page informing you that the global policy has been reset.</span></span>

</div>

<div>

## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="36ff6-114">使用 Windows PowerShell Cmdlet 重置全局外部访问策略</span><span class="sxs-lookup"><span data-stu-id="36ff6-114">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="36ff6-115">可以使用 Windows PowerShell 和 Set-csexternalaccesspolicy cmdlet 重置全局外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="36ff6-115">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="36ff6-116">此 cmdlet 可从 Lync Server 2013 命令行管理程序或远程会话 Windows PowerShell 中运行。</span><span class="sxs-lookup"><span data-stu-id="36ff6-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="36ff6-117">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="36ff6-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="36ff6-118">重置全局外部访问策略</span><span class="sxs-lookup"><span data-stu-id="36ff6-118">To reset the global external access policy</span></span>

  - <span data-ttu-id="36ff6-119">此命令重置全局外部访问策略：</span><span class="sxs-lookup"><span data-stu-id="36ff6-119">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

</div>

<span data-ttu-id="36ff6-120">有关详细信息，请参阅[set-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="36ff6-120">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

