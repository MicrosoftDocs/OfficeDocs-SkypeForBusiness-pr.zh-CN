---
title: Lync Server 2013：删除用于外部用户访问的站点或用户策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a site or user policy for external user access
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c21b58715814b5bf08023662bff61b004b51896
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036130"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-site-or-user-policy-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="707dc-102">在 Lync Server 2013 中删除用于外部用户访问的站点或用户策略</span><span class="sxs-lookup"><span data-stu-id="707dc-102">Delete a site or user policy for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="707dc-103">_**上次修改的主题：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="707dc-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="707dc-104">您可以删除在 "**外部访问策略**" 页上的 "Lync Server 控制面板" 中列出的任何站点或用户策略。</span><span class="sxs-lookup"><span data-stu-id="707dc-104">You can delete any site or user policy that is listed in Lync Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="707dc-105">删除全局策略时不会真正删除该策略，而只是将其重置为不支持任何外部用户访问选项的默认设置。</span><span class="sxs-lookup"><span data-stu-id="707dc-105">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="707dc-106">有关重置全局策略的详细信息，请参阅[在 Lync Server 2013 中重置外部用户访问的全局策略](lync-server-2013-reset-the-global-policy-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="707dc-106">For details about resetting the global policy, see [Reset the global policy for external user access in Lync Server 2013](lync-server-2013-reset-the-global-policy-for-external-user-access.md).</span></span>

<div>

## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="707dc-107">删除外部用户访问的站点或用户策略</span><span class="sxs-lookup"><span data-stu-id="707dc-107">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="707dc-108">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="707dc-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="707dc-109">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="707dc-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="707dc-110">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="707dc-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="707dc-111">单击“外部用户访问”\*\*\*\*，再单击“外部访问策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="707dc-111">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="707dc-112">在“外部访问策略”\*\*\*\* 选项卡上，单击要删除的站点或用户策略，再单击“编辑”\*\*\*\*，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="707dc-112">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="707dc-113">当系统提示您确认删除时，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="707dc-113">When prompted to confirm the deletion, click **OK**.</span></span>

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="707dc-114">使用 Windows PowerShell Cmdlet 删除 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="707dc-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="707dc-115">可以使用 Windows PowerShell 和 Set-csexternalaccesspolicy cmdlet 删除外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="707dc-115">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="707dc-116">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="707dc-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="707dc-117">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="707dc-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="707dc-118">删除特定的外部访问策略</span><span class="sxs-lookup"><span data-stu-id="707dc-118">To remove a specific external access policy</span></span>

  - <span data-ttu-id="707dc-119">此命令删除适用于 Redmond 站点的外部访问策略：</span><span class="sxs-lookup"><span data-stu-id="707dc-119">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="707dc-120">删除应用于每用户作用域的所有外部访问策略</span><span class="sxs-lookup"><span data-stu-id="707dc-120">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="707dc-121">此命令删除在每用户范围配置的所有外部访问策略：</span><span class="sxs-lookup"><span data-stu-id="707dc-121">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="707dc-122">删除在禁用外部用户访问的所有外部访问策略</span><span class="sxs-lookup"><span data-stu-id="707dc-122">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="707dc-123">此命令删除已禁用外部用户访问的所有外部访问策略：</span><span class="sxs-lookup"><span data-stu-id="707dc-123">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy

</div>

<span data-ttu-id="707dc-124">有关详细信息，请参阅[set-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="707dc-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

