---
title: 删除会议配置设置的现有集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of meeting configuration settings
ms:assetid: 92ff8a91-05c5-4047-a533-5dff12f22299
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688136(v=OCS.15)
ms:contentKeyID: 49733736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edf416af31b219c07691790b88d672d26768104d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514659"
---
# <a name="delete-an-existing-collection-of-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="f67e9-102">删除 Lync Server 2013 中现有的会议配置设置集合</span><span class="sxs-lookup"><span data-stu-id="f67e9-102">Delete an existing collection of meeting configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f67e9-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f67e9-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f67e9-p101">可以删除站点或用户配置。无法删除全局配置。如果删除全局配置，该配置将自动重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="f67e9-p101">You can delete a site or user configuration. The global configuration cannot be removed. If you delete the global configuration, it is automatically reset to the default values.</span></span>

<div>

## <a name="to-delete-a-site-or-user-meeting-configuration"></a><span data-ttu-id="f67e9-107">删除站点或用户会议配置</span><span class="sxs-lookup"><span data-stu-id="f67e9-107">To delete a site or user meeting configuration</span></span>

1.  <span data-ttu-id="f67e9-108">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="f67e9-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f67e9-109">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="f67e9-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f67e9-110">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="f67e9-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f67e9-111">在左侧导航栏中，单击 **“会议”**，然后单击 **“会议配置”**。</span><span class="sxs-lookup"><span data-stu-id="f67e9-111">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="f67e9-112">在会议配置列表中，单击要删除的站点或池配置，单击 " **编辑**"，然后单击 " **删除**"。</span><span class="sxs-lookup"><span data-stu-id="f67e9-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f67e9-113">使用 Windows PowerShell Cmdlet 删除会议配置设置</span><span class="sxs-lookup"><span data-stu-id="f67e9-113">Removing Meeting Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f67e9-114">可以使用 Windows PowerShell 和 Remove-CsMeetingConfiguration cmdlet 删除会议设置。</span><span class="sxs-lookup"><span data-stu-id="f67e9-114">Meeting settings can be deleted by using Windows PowerShell and the Remove-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="f67e9-115">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="f67e9-115">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f67e9-116">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="f67e9-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-meeting-configuration-settings"></a><span data-ttu-id="f67e9-117">删除指定的会议配置设置集合</span><span class="sxs-lookup"><span data-stu-id="f67e9-117">To remove a specified collection of meeting configuration settings</span></span>

  - <span data-ttu-id="f67e9-118">此命令删除应用于 Redmond 站点的会议配置设置：</span><span class="sxs-lookup"><span data-stu-id="f67e9-118">This command removes the meeting configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsMeetingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="f67e9-119">删除应用到站点范围的所有会议配置设置</span><span class="sxs-lookup"><span data-stu-id="f67e9-119">To remove all the meeting configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="f67e9-120">此命令删除应用于站点作用域的所有会议配置设置：</span><span class="sxs-lookup"><span data-stu-id="f67e9-120">This command removes all the meeting configuration settings applied to the site scope:</span></span>
    
        Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-that-admit-anonymous-users-by-default"></a><span data-ttu-id="f67e9-121">删除默认情况下承认匿名用户的所有会议配置设置</span><span class="sxs-lookup"><span data-stu-id="f67e9-121">To remove all the meeting configuration settings that admit anonymous users by default</span></span>

  - <span data-ttu-id="f67e9-122">添加此命令将删除所有默认允许匿名用户的设置：</span><span class="sxs-lookup"><span data-stu-id="f67e9-122">And this one removes all the settings that allow anonymous users to be admitted by default:</span></span>
    
        Get-CsMeetingConfiguration | Where-Object {$_.AdmitAnonymousUsersByDefault -eq $True} | Remove-CsMeetingConfiguration

</div>

<span data-ttu-id="f67e9-123">有关详细信息，请参阅 [get-csmeetingconfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15)) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="f67e9-123">For more information, see the help topic for the [Remove-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

