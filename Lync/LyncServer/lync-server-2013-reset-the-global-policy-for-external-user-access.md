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
ms.openlocfilehash: 971239018f3a8e1bcc92c036f50ed36616256ac7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-the-global-policy-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="de7dc-102">在 Lync Server 2013 中重置外部用户访问的全局策略</span><span class="sxs-lookup"><span data-stu-id="de7dc-102">Reset the global policy for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de7dc-103">_**主题上次修改时间：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="de7dc-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="de7dc-104">您不能完全删除全局策略。</span><span class="sxs-lookup"><span data-stu-id="de7dc-104">You cannot completely delete a global policy.</span></span> <span data-ttu-id="de7dc-105">使用全局策略中的 "**删除**" 选项仅将全局策略重置为默认设置，不包括对任何外部用户访问选项的支持。</span><span class="sxs-lookup"><span data-stu-id="de7dc-105">Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

<div>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="de7dc-106">将全局策略重置为默认设置</span><span class="sxs-lookup"><span data-stu-id="de7dc-106">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="de7dc-107">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="de7dc-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="de7dc-108">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="de7dc-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="de7dc-109">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="de7dc-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="de7dc-110">在左侧导航栏中，单击 "**外部用户访问**"，单击 "**外部访问策略**"。</span><span class="sxs-lookup"><span data-stu-id="de7dc-110">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="de7dc-111">在 "**外部访问策略**" 选项卡上，单击 "全局策略"，单击 "**编辑**"，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="de7dc-111">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="de7dc-112">当系统提示确认删除时，单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="de7dc-112">When prompted to confirm the deletion, click **OK**.</span></span> <span data-ttu-id="de7dc-113">将在页面顶部显示一条消息，通知您全局策略已重置。</span><span class="sxs-lookup"><span data-stu-id="de7dc-113">A message appears at the top of the page informing you that the global policy has been reset.</span></span>

</div>

<div>

## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="de7dc-114">使用 Windows PowerShell Cmdlet 重置全局外部访问策略</span><span class="sxs-lookup"><span data-stu-id="de7dc-114">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="de7dc-115">全局外部访问策略可以通过使用 Windows PowerShell 和 CsExternalAccessPolicy cmdlet 进行重置。</span><span class="sxs-lookup"><span data-stu-id="de7dc-115">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="de7dc-116">此 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从远程会话 Windows PowerShell 运行。</span><span class="sxs-lookup"><span data-stu-id="de7dc-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="de7dc-117">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="de7dc-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="de7dc-118">重置全局外部访问策略</span><span class="sxs-lookup"><span data-stu-id="de7dc-118">To reset the global external access policy</span></span>

  - <span data-ttu-id="de7dc-119">此命令将重置全局外部访问策略：</span><span class="sxs-lookup"><span data-stu-id="de7dc-119">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

</div>

<span data-ttu-id="de7dc-120">有关详细信息，请参阅[CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="de7dc-120">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

