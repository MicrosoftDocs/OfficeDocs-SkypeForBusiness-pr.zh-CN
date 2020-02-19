---
title: 删除现有的客户端版本配置设置集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of client version configuration settings
ms:assetid: 70bf1216-d0d2-45ce-881f-b8edadf3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898480(v=OCS.15)
ms:contentKeyID: 50873760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1709d783bf47537cec25f06232d5782975444f6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134678"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="ad35f-102">在 Lync Server 2013 中删除客户端版本配置设置的现有集合</span><span class="sxs-lookup"><span data-stu-id="ad35f-102">Delete an existing collection of client version configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad35f-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="ad35f-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="ad35f-104">如果要删除以前为站点配置的客户端配置设置，可以从 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序中删除这些设置。</span><span class="sxs-lookup"><span data-stu-id="ad35f-104">If you want to remove the client configuration settings that have been previously configured for a site, you can remove the settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-remove-client-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="ad35f-105">使用 Lync Server 控制面板删除客户端配置设置</span><span class="sxs-lookup"><span data-stu-id="ad35f-105">To remove client configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="ad35f-106">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="ad35f-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ad35f-107">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="ad35f-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ad35f-108">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="ad35f-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ad35f-109">在左侧导航栏中，单击 "**客户端**"，然后单击 "**客户端版本配置**" 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="ad35f-109">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="ad35f-110">选择网站，单击 "**编辑**"，再单击 "**删除**"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="ad35f-110">Select the site, click **Edit**, click **Delete**, and then click **OK**.</span></span>

</div>

<div>

## <a name="removing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ad35f-111">使用 Windows PowerShell Cmdlet 删除客户端版本配置设置</span><span class="sxs-lookup"><span data-stu-id="ad35f-111">Removing Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ad35f-112">您可以使用**CsClientVersionConfiguration** cmdlet 删除客户端版本配置设置。</span><span class="sxs-lookup"><span data-stu-id="ad35f-112">You can delete client version configuration settings by using the **Remove-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="ad35f-113">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="ad35f-113">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ad35f-114">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="ad35f-114">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-client-version-configuration-settings"></a><span data-ttu-id="ad35f-115">删除指定的客户端版本配置设置集合</span><span class="sxs-lookup"><span data-stu-id="ad35f-115">To remove a specified collection of client version configuration settings</span></span>

  - <span data-ttu-id="ad35f-116">以下命令将删除应用于 Redmond 站点的客户端版本配置设置：</span><span class="sxs-lookup"><span data-stu-id="ad35f-116">The following command removes the client version configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsClientVersionConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="ad35f-117">删除应用到站点范围的所有客户端版本配置设置</span><span class="sxs-lookup"><span data-stu-id="ad35f-117">To remove all the client version configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="ad35f-118">此命令将删除在站点范围内配置的所有客户端版本配置设置：</span><span class="sxs-lookup"><span data-stu-id="ad35f-118">This command removes all the client version configuration settings configured at the site scope:</span></span>
    
        Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-based-on-the-value-of-the-defaultaction-property"></a><span data-ttu-id="ad35f-119">根据 DefaultAction 属性的值删除所有客户端版本配置设置</span><span class="sxs-lookup"><span data-stu-id="ad35f-119">To remove all the client version configuration settings based on the value of the DefaultAction property</span></span>

  - <span data-ttu-id="ad35f-120">此命令将删除默认操作已设置为 "Block" 的所有客户端版本配置设置：</span><span class="sxs-lookup"><span data-stu-id="ad35f-120">And this command removes all the client version configuration settings where the default action has been set to "Block":</span></span>
    
        Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block" | Remove-CsClientVersionConfiguration

</div>

<span data-ttu-id="ad35f-121">有关详细信息，请参阅[CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15)) Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="ad35f-121">For details, see the Help topic for the [Remove-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

