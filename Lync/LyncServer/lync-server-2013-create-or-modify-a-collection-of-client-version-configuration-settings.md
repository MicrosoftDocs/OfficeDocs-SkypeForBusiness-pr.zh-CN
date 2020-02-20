---
title: 创建或修改客户端版本配置设置的集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of client version configuration settings
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898477(v=OCS.15)
ms:contentKeyID: 50873757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d4a3b270ecf35d9fbc33accd8c46909a6e8755b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151894"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="9dec8-102">在 Lync Server 2013 中创建或修改客户端版本配置设置的集合</span><span class="sxs-lookup"><span data-stu-id="9dec8-102">Create or modify a collection of client version configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9dec8-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9dec8-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9dec8-104">客户端版本配置设置用于打开或关闭客户端版本控制。</span><span class="sxs-lookup"><span data-stu-id="9dec8-104">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="9dec8-105">全局客户端版本配置与 Lync Server 一起安装，用于为整个服务器部署启用或禁用客户端版本控制。</span><span class="sxs-lookup"><span data-stu-id="9dec8-105">The global client version configuration installs with Lync Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="9dec8-106">您还可以为各个网站配置客户端版本配置设置。</span><span class="sxs-lookup"><span data-stu-id="9dec8-106">You can also configure client version configuration settings for individual sites.</span></span> <span data-ttu-id="9dec8-107">您可以从 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序创建或修改客户端版本配置设置。</span><span class="sxs-lookup"><span data-stu-id="9dec8-107">You can create or modify client version configuration settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="9dec8-108">由于匿名用户未与用户、站点或服务关联，因此匿名用户仅受全局级别策略的影响。</span><span class="sxs-lookup"><span data-stu-id="9dec8-108">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="9dec8-109">使用 Lync Server 控制面板创建或修改客户端版本配置设置</span><span class="sxs-lookup"><span data-stu-id="9dec8-109">To create or modify client version configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9dec8-110">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="9dec8-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9dec8-111">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="9dec8-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9dec8-112">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="9dec8-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9dec8-113">在左侧导航栏中，单击 "**客户端**"，然后单击 "**客户端版本配置**" 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="9dec8-113">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="9dec8-114">在 "**客户端版本配置**" 页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9dec8-114">On the **Client Version Configuration** page, do the following:</span></span>
    
      - <span data-ttu-id="9dec8-115">若要创建新的配置，请单击 "**新建**"，选择一个网站，单击 **"确定**名称"，然后更新设置。</span><span class="sxs-lookup"><span data-stu-id="9dec8-115">To create a new configuration, click **New**, select a site, click **OK** name, and update the settings.</span></span>
    
      - <span data-ttu-id="9dec8-116">若要修改配置，请选择该配置，单击 "**编辑**"，再单击 "**显示详细信息**"，然后对设置进行更改。</span><span class="sxs-lookup"><span data-stu-id="9dec8-116">To modify a configuration, select the configuration, click **Edit**, click **Show details**, and make changes to the settings.</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9dec8-117">使用 Windows PowerShell Cmdlet 创建或修改客户端版本配置设置</span><span class="sxs-lookup"><span data-stu-id="9dec8-117">Creating or Modifying Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9dec8-118">您可以使用**CsClientVersionConfiguration** cmdlet 创建客户端版本配置设置，并使用**CsClientVersionConfiguration** cmdlet 对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="9dec8-118">You can create client version configuration settings by using the **New-CsClientVersionConfiguration** cmdlet, and modify them by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="9dec8-119">这些 cmdlet 可从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="9dec8-119">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9dec8-120">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="9dec8-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a><span data-ttu-id="9dec8-121">创建新的客户端版本配置设置集合</span><span class="sxs-lookup"><span data-stu-id="9dec8-121">To create a new collection of client version configuration settings</span></span>

  - <span data-ttu-id="9dec8-122">以下命令将创建应用于 Redmond 站点的客户端版本配置设置的新集合。</span><span class="sxs-lookup"><span data-stu-id="9dec8-122">The following command creates a new collection of client version configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="9dec8-123">在此示例中，将禁用 Redmond 站点的客户端版本控制。</span><span class="sxs-lookup"><span data-stu-id="9dec8-123">In this example, client versioning is disabled for the Redmond site.</span></span>
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a><span data-ttu-id="9dec8-124">为网站启用客户端版本控制</span><span class="sxs-lookup"><span data-stu-id="9dec8-124">To enable client versioning for a site</span></span>

  - <span data-ttu-id="9dec8-125">此命令为 Redmond 站点启用客户端版本控制。</span><span class="sxs-lookup"><span data-stu-id="9dec8-125">This command enables client versioning for the Redmond site.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a><span data-ttu-id="9dec8-126">在整个组织中禁用客户端版本控制</span><span class="sxs-lookup"><span data-stu-id="9dec8-126">To disable client versioning throughout the organization</span></span>

  - <span data-ttu-id="9dec8-127">在此示例中，将对组织中使用的所有客户端版本配置设置禁用客户端版本控制。</span><span class="sxs-lookup"><span data-stu-id="9dec8-127">In this example, client versioning is disabled for all the client version configuration settings in use in the organization.</span></span>
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

<span data-ttu-id="9dec8-128">有关详细信息，请参阅[CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15))和[CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="9dec8-128">For details, see the Help topic for the [New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) and [Set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) cmdlets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

