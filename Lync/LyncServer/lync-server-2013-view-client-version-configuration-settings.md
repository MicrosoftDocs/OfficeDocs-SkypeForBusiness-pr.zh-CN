---
title: Lync Server 2013：查看客户端版本配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version configuration settings
ms:assetid: c72df4e6-a889-4cb6-86f7-8334d7774c6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923062(v=OCS.15)
ms:contentKeyID: 50675353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e376525d2e00a6b2c98674855ccb314984364a1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="85115-102">在 Lync Server 2013 中查看客户端版本配置设置</span><span class="sxs-lookup"><span data-stu-id="85115-102">View client version configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85115-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="85115-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="85115-104">客户端版本配置设置用于打开或关闭客户端版本控制。</span><span class="sxs-lookup"><span data-stu-id="85115-104">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="85115-105">全局客户端版本配置将随 Lync Server 2013 一起安装，并用于为整个服务器部署启用或禁用客户端版本控制。</span><span class="sxs-lookup"><span data-stu-id="85115-105">The global client version configuration installs with Lync Server 2013 and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="85115-106">当全局配置处于启用状态时，用户尝试登录后您所拥有的任何客户端版本策略都将生效。</span><span class="sxs-lookup"><span data-stu-id="85115-106">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="85115-107">您可以从 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序中查看客户端版本配置设置。</span><span class="sxs-lookup"><span data-stu-id="85115-107">You can view client version configuration settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="85115-108">由于匿名用户未与用户、站点或服务关联，因此匿名用户仅受全局级别策略的影响。</span><span class="sxs-lookup"><span data-stu-id="85115-108">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-view-client-version-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="85115-109">使用 Lync Server 控制面板查看客户端版本配置设置</span><span class="sxs-lookup"><span data-stu-id="85115-109">To view client version configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="85115-110">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="85115-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="85115-111">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="85115-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="85115-112">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="85115-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="85115-113">在左侧导航栏中，单击 "**客户端**"，然后单击 "**客户端版本配置**" 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="85115-113">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="85115-114">双击要查看的客户端版本配置的名称。</span><span class="sxs-lookup"><span data-stu-id="85115-114">Double-click the name of the client version configuration you want to view.</span></span>

</div>

<div>

## <a name="viewing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="85115-115">使用 Windows PowerShell Cmdlet 查看客户端版本配置设置</span><span class="sxs-lookup"><span data-stu-id="85115-115">Viewing Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="85115-116">您可以使用**CsClientVersionConfiguration** cmdlet 查看客户端版本配置设置。</span><span class="sxs-lookup"><span data-stu-id="85115-116">You can view client version configuration settings by using the **Get-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="85115-117">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="85115-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="85115-118">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="85115-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-client-version-configuration-information"></a><span data-ttu-id="85115-119">查看客户端版本配置信息</span><span class="sxs-lookup"><span data-stu-id="85115-119">To view client version configuration information</span></span>

  - <span data-ttu-id="85115-120">若要查看有关所有客户端版本配置设置的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="85115-120">To view information about all your client version configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientVersionConfiguration
    
    <span data-ttu-id="85115-121">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="85115-121">That will return information similar to this:</span></span>
    
        Identity      : Global
        DefaultAction : Allow
        DefaultURL    :
        Enabled       : True

</div>

<span data-ttu-id="85115-122">有关详细信息，请参阅[CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionConfiguration) Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="85115-122">For details, see the Help topic for the [Get-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

