---
title: Lync Server 2013：删除现有会议策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing conferencing policy
ms:assetid: 709ed771-790f-4bf1-a4de-b37ca5168688
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688089(v=OCS.15)
ms:contentKeyID: 49733688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29d8801c8ee58a65a60495789fdca66d16ce0c66
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514619"
---
# <a name="delete-an-existing-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="2e18e-102">在 Lync Server 2013 中删除现有会议策略</span><span class="sxs-lookup"><span data-stu-id="2e18e-102">Delete an existing conferencing policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e18e-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="2e18e-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="2e18e-104">按照以下步骤删除用户级别或站点级别的会议策略。</span><span class="sxs-lookup"><span data-stu-id="2e18e-104">Follow these steps to delete a user-level or a site-level conferencing policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2e18e-105">无法删除全局会议策略。</span><span class="sxs-lookup"><span data-stu-id="2e18e-105">You cannot delete the global conferencing policy.</span></span>



</div>

<div>

## <a name="to-delete-a-site-or-user-conferencing-policy"></a><span data-ttu-id="2e18e-106">删除站点或用户会议策略</span><span class="sxs-lookup"><span data-stu-id="2e18e-106">To delete a site or user conferencing policy</span></span>

1.  <span data-ttu-id="2e18e-107">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="2e18e-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2e18e-108">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="2e18e-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2e18e-109">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="2e18e-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2e18e-110">在左侧导航栏中，单击“会议”\*\*\*\*，然后单击“会议策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2e18e-110">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="2e18e-111">在会议策略列表中，单击要删除的站点或用户策略，单击 " **编辑**"，然后单击 " **删除**"。</span><span class="sxs-lookup"><span data-stu-id="2e18e-111">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-conferencing-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2e18e-112">使用 Windows PowerShell Cmdlet 删除会议策略</span><span class="sxs-lookup"><span data-stu-id="2e18e-112">Removing Conferencing Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2e18e-113">您可以使用 Lync Server 命令行管理程序和 **set-csconferencingpolicy** cmdlet 删除会议策略。</span><span class="sxs-lookup"><span data-stu-id="2e18e-113">You can delete conferencing policies by using Lync Server Management Shell and the **Remove-CsConferencingPolicy** cmdlet.</span></span> <span data-ttu-id="2e18e-114">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2e18e-114">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2e18e-115">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="2e18e-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-conferencing-policy"></a><span data-ttu-id="2e18e-116">删除指定会议策略</span><span class="sxs-lookup"><span data-stu-id="2e18e-116">To remove a specified conferencing policy</span></span>

  - <span data-ttu-id="2e18e-117">以下命令删除 Identity 为 RedmondConferencingPolicy 的会议策略：</span><span class="sxs-lookup"><span data-stu-id="2e18e-117">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
    
        Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="2e18e-118">删除适用于每用户范围的所有会议策略</span><span class="sxs-lookup"><span data-stu-id="2e18e-118">To remove all of the conferencing policies applied to the per-user scope</span></span>

  - <span data-ttu-id="2e18e-119">以下命令删除在每用户范围配置的所有会议策略：</span><span class="sxs-lookup"><span data-stu-id="2e18e-119">The following command removes all the conferencing policies configured at the per-user scope:</span></span>
    
        Get-CsConferencingPolicy -Filter "tag:*" | Remove-CsConferencingPolicy

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-polices-that-allow-recording-by-external-users"></a><span data-ttu-id="2e18e-120">删除允许外部用户记录的所有会议策略</span><span class="sxs-lookup"><span data-stu-id="2e18e-120">To remove all of the conferencing polices that allow recording by external users</span></span>

  - <span data-ttu-id="2e18e-121">以下命令删除允许外部用户记录会议的所有会议策略：</span><span class="sxs-lookup"><span data-stu-id="2e18e-121">The following command deletes any conferencing policies that allow external users to record the conference:</span></span>
    
        Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy

</div>

<span data-ttu-id="2e18e-122">有关详细信息，请参阅 [set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsConferencingPolicy)。</span><span class="sxs-lookup"><span data-stu-id="2e18e-122">For details, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsConferencingPolicy).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

