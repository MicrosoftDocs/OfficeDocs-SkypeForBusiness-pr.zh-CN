---
title: 删除会议配置设置的现有集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of meeting configuration settings
ms:assetid: 92ff8a91-05c5-4047-a533-5dff12f22299
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688136(v=OCS.15)
ms:contentKeyID: 49733736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10d564cf8fbcfb8c66df5e84841aae456913f1dc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="81eaf-102">删除 Lync Server 2013 中现有的会议配置设置集合</span><span class="sxs-lookup"><span data-stu-id="81eaf-102">Delete an existing collection of meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81eaf-103">_**主题上次修改时间:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="81eaf-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="81eaf-104">您可以删除网站或用户配置。</span><span class="sxs-lookup"><span data-stu-id="81eaf-104">You can delete a site or user configuration.</span></span> <span data-ttu-id="81eaf-105">无法删除全局配置。</span><span class="sxs-lookup"><span data-stu-id="81eaf-105">The global configuration cannot be removed.</span></span> <span data-ttu-id="81eaf-106">如果删除全局配置，该配置将自动重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="81eaf-106">If you delete the global configuration, it is automatically reset to the default values.</span></span>

<div>

## <a name="to-delete-a-site-or-user-meeting-configuration"></a><span data-ttu-id="81eaf-107">删除网站或用户会议配置</span><span class="sxs-lookup"><span data-stu-id="81eaf-107">To delete a site or user meeting configuration</span></span>

1.  <span data-ttu-id="81eaf-108">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="81eaf-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="81eaf-109">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="81eaf-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="81eaf-110">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="81eaf-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="81eaf-111">在左侧导航栏中, 单击 "**会议**", 然后单击 "**会议配置**"。</span><span class="sxs-lookup"><span data-stu-id="81eaf-111">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="81eaf-112">在会议配置的列表中，单击要删除的站点或池配置，单击“**编辑**”，然后单击“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="81eaf-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="81eaf-113">使用 Windows PowerShell Cmdlet 删除会议配置设置</span><span class="sxs-lookup"><span data-stu-id="81eaf-113">Removing Meeting Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="81eaf-114">可使用 Windows PowerShell 和 CsMeetingConfiguration cmdlet 删除会议设置。</span><span class="sxs-lookup"><span data-stu-id="81eaf-114">Meeting settings can be deleted by using Windows PowerShell and the Remove-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="81eaf-115">此 cmdlet 既可以从 Lync Server 2013 管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="81eaf-115">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="81eaf-116">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="81eaf-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-meeting-configuration-settings"></a><span data-ttu-id="81eaf-117">删除指定的会议配置设置集合</span><span class="sxs-lookup"><span data-stu-id="81eaf-117">To remove a specified collection of meeting configuration settings</span></span>

  - <span data-ttu-id="81eaf-118">此命令将删除应用于雷德蒙网站的会议配置设置:</span><span class="sxs-lookup"><span data-stu-id="81eaf-118">This command removes the meeting configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsMeetingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="81eaf-119">删除应用到网站范围的所有会议配置设置</span><span class="sxs-lookup"><span data-stu-id="81eaf-119">To remove all the meeting configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="81eaf-120">此命令将删除应用到网站范围的所有会议配置设置:</span><span class="sxs-lookup"><span data-stu-id="81eaf-120">This command removes all the meeting configuration settings applied to the site scope:</span></span>
    
        Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-that-admit-anonymous-users-by-default"></a><span data-ttu-id="81eaf-121">删除默认情况下承认匿名用户的所有会议配置设置</span><span class="sxs-lookup"><span data-stu-id="81eaf-121">To remove all the meeting configuration settings that admit anonymous users by default</span></span>

  - <span data-ttu-id="81eaf-122">这一方法将删除所有允许匿名用户默认获准的设置:</span><span class="sxs-lookup"><span data-stu-id="81eaf-122">And this one removes all the settings that allow anonymous users to be admitted by default:</span></span>
    
        Get-CsMeetingConfiguration | Where-Object {$_.AdmitAnonymousUsersByDefault -eq $True} | Remove-CsMeetingConfiguration

</div>

<span data-ttu-id="81eaf-123">有关详细信息, 请参阅[CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15)) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="81eaf-123">For more information, see the help topic for the [Remove-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

