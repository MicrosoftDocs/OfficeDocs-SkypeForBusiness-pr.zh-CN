---
title: 删除客户端版本配置设置的现有集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of client version configuration settings
ms:assetid: 70bf1216-d0d2-45ce-881f-b8edadf3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898480(v=OCS.15)
ms:contentKeyID: 50873760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a71df7af1f0a6158cb61e780b44ed4227d32018
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="b6d9c-102">在 Lync Server 2013 中删除客户端版本配置设置的现有集合</span><span class="sxs-lookup"><span data-stu-id="b6d9c-102">Delete an existing collection of client version configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6d9c-103">_**主题上次修改时间:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b6d9c-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b6d9c-104">如果要删除以前为网站配置的客户端配置设置, 可以从 Lync Server 2013 控制面板或 Lync Server 2013 管理外壳中删除设置。</span><span class="sxs-lookup"><span data-stu-id="b6d9c-104">If you want to remove the client configuration settings that have been previously configured for a site, you can remove the settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-remove-client-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="b6d9c-105">使用 Lync Server "控制面板" 删除客户端配置设置</span><span class="sxs-lookup"><span data-stu-id="b6d9c-105">To remove client configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b6d9c-106">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b6d9c-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b6d9c-107">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="b6d9c-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b6d9c-108">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="b6d9c-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b6d9c-109">在左侧导航栏中, 单击 "**客户端**", 然后单击 "**客户端版本配置**导航" 按钮。</span><span class="sxs-lookup"><span data-stu-id="b6d9c-109">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="b6d9c-110">选择网站, 单击 "**编辑**", 单击 "**删除**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="b6d9c-110">Select the site, click **Edit**, click **Delete**, and then click **OK**.</span></span>

</div>

<div>

## <a name="removing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b6d9c-111">使用 Windows PowerShell Cmdlet 删除客户端版本配置设置</span><span class="sxs-lookup"><span data-stu-id="b6d9c-111">Removing Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b6d9c-112">你可以使用**CsClientVersionConfiguration** cmdlet 删除客户端版本配置设置。</span><span class="sxs-lookup"><span data-stu-id="b6d9c-112">You can delete client version configuration settings by using the **Remove-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="b6d9c-113">此 cmdlet 既可以从 Lync Server 2013 管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="b6d9c-113">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b6d9c-114">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="b6d9c-114">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-client-version-configuration-settings"></a><span data-ttu-id="b6d9c-115">删除指定的客户端版本配置设置集合</span><span class="sxs-lookup"><span data-stu-id="b6d9c-115">To remove a specified collection of client version configuration settings</span></span>

  - <span data-ttu-id="b6d9c-116">以下命令将删除应用于 Redmond 网站的客户端版本配置设置:</span><span class="sxs-lookup"><span data-stu-id="b6d9c-116">The following command removes the client version configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsClientVersionConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="b6d9c-117">删除应用到网站范围的所有客户端版本配置设置</span><span class="sxs-lookup"><span data-stu-id="b6d9c-117">To remove all the client version configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="b6d9c-118">此命令将删除在网站范围内配置的所有客户端版本配置设置:</span><span class="sxs-lookup"><span data-stu-id="b6d9c-118">This command removes all the client version configuration settings configured at the site scope:</span></span>
    
        Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-based-on-the-value-of-the-defaultaction-property"></a><span data-ttu-id="b6d9c-119">若要删除基于 DefaultAction 属性值的所有客户端版本配置设置</span><span class="sxs-lookup"><span data-stu-id="b6d9c-119">To remove all the client version configuration settings based on the value of the DefaultAction property</span></span>

  - <span data-ttu-id="b6d9c-120">此命令将删除默认操作设置为 "Block" 的所有客户端版本配置设置:</span><span class="sxs-lookup"><span data-stu-id="b6d9c-120">And this command removes all the client version configuration settings where the default action has been set to "Block":</span></span>
    
        Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block" | Remove-CsClientVersionConfiguration

</div>

<span data-ttu-id="b6d9c-121">有关详细信息, 请参阅[CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15)) Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="b6d9c-121">For details, see the Help topic for the [Remove-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

