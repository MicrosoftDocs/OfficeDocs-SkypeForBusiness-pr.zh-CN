---
title: 创建或修改 Lync Phone Edition 配置设置的集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of Lync Phone Edition configuration settings
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49733683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3012ffeeb8dd4559ee05a45dd07becefd099691
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="e0f42-102">在 Lync Server 2013 中创建或修改 Lync Phone Edition 配置设置的集合</span><span class="sxs-lookup"><span data-stu-id="e0f42-102">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0f42-103">_**主题上次修改时间:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e0f42-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e0f42-104">安装 Lync Server 时, 将获得一个全局 Lync Phone Edition 设置集合。</span><span class="sxs-lookup"><span data-stu-id="e0f42-104">When you install Lync Server, you get a global collection of Lync Phone Edition settings.</span></span> <span data-ttu-id="e0f42-105">这些设置适用于你的部署中运行 Lync Phone Edition 的所有设备。</span><span class="sxs-lookup"><span data-stu-id="e0f42-105">These settings apply to all devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="e0f42-106">您可以随时更改这些设置。</span><span class="sxs-lookup"><span data-stu-id="e0f42-106">You can change these settings at any time.</span></span> <span data-ttu-id="e0f42-107">你还可以设置新的设置集合, 这些设置适用于特定网站中的设备。</span><span class="sxs-lookup"><span data-stu-id="e0f42-107">You can also set up a new collection of settings that apply to the devices in a specific site.</span></span> <span data-ttu-id="e0f42-108">网站设置优先于全局设置。</span><span class="sxs-lookup"><span data-stu-id="e0f42-108">Site settings take precedence over global settings.</span></span>

<span data-ttu-id="e0f42-109">配置设置包括集合名称、范围 (全局或网站)、SIP 安全设置、日志记录级别、语音服务质量 (QoS) 级别、电话锁定设置和电话锁定详细信息 (即 a) 解锁个人识别码的时间 (PIN) 在锁定自身之前, 必须是和 b 的电话保持空闲。</span><span class="sxs-lookup"><span data-stu-id="e0f42-109">Configuration settings consist of the collection name, scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, how long the a) unlock personal identification number (PIN) must be and b) phone stays idle before locking itself.</span></span>

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a><span data-ttu-id="e0f42-110">为现有集合创建 Lync Phone Edition 配置设置或编辑设置的集合</span><span class="sxs-lookup"><span data-stu-id="e0f42-110">To create a collection of Lync Phone Edition configuration settings or edit settings for an existing collection</span></span>

1.  <span data-ttu-id="e0f42-111">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="e0f42-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e0f42-112">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="e0f42-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e0f42-113">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="e0f42-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e0f42-114">在左侧导航栏中, 单击 "**客户端**", 然后单击 "**设备配置**" 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="e0f42-114">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="e0f42-115">在 "**设备配置**" 页面上, 执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="e0f42-115">On the **Device Configuration** page, do one of the following:</span></span>
    
      - <span data-ttu-id="e0f42-116">若要创建新的 Lync Phone Edition 配置设置, 请单击 "**新建**", 选择一个网站, 单击 **"确定**", 查看默认设置, 如果需要, 可进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="e0f42-116">To create a new collection of Lync Phone Edition configuration settings, click **New**, select a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
      - <span data-ttu-id="e0f42-117">若要编辑现有集合中的任何设置, 请单击该集合, 单击 "**编辑**" 菜单, 单击 "**显示详细信息**", 然后进行更改。</span><span class="sxs-lookup"><span data-stu-id="e0f42-117">To edit any of the settings in an existing collection, click the collection, click the **Edit** menu, click **Show details**, and then make your changes.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="e0f42-118">若要返回到使用全局集合的默认设置, 请单击全局集合, 单击 "<STRONG>编辑</STRONG>" 菜单, 单击 "<STRONG>删除</STRONG>", 然后单击<STRONG>"确定"</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="e0f42-118">To go back to using the default settings for the global collection, click the global collection, click the <STRONG>Edit</STRONG> menu, click <STRONG>Delete</STRONG>, and then click <STRONG>OK</STRONG>.</span></span> <span data-ttu-id="e0f42-119">这不会删除全局集合;它只是将设置重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="e0f42-119">This will not delete the global collection; it just resets the settings to the defaults.</span></span>

        
        </div>

5.  <span data-ttu-id="e0f42-120">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="e0f42-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e0f42-121">使用 Windows PowerShell Cmdlet 创建新的 Lync 手机版配置设置</span><span class="sxs-lookup"><span data-stu-id="e0f42-121">Creating New Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e0f42-122">你可以使用 Windows PowerShell 和**CsUCPhoneConfiguration** cmdlet 来创建 Lync Phone Edition 配置设置 (仅限在网站范围内)。</span><span class="sxs-lookup"><span data-stu-id="e0f42-122">You can create Lync Phone Edition configuration settings can (at the site scope only) by using Windows PowerShell and the **New-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="e0f42-123">你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e0f42-123">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e0f42-124">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="e0f42-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="e0f42-125">创建使用默认值的新 Lync 手机版配置设置</span><span class="sxs-lookup"><span data-stu-id="e0f42-125">To create new Lync Phone Edition configuration settings that use the default values</span></span>

  - <span data-ttu-id="e0f42-126">此命令为 Redmond 站点创建一组新的 UC 电话配置设置:</span><span class="sxs-lookup"><span data-stu-id="e0f42-126">This command creates a new set of UC phone configuration settings for the Redmond site:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="e0f42-127">由于上述命令中未指定参数（不包括必需的 Identity 参数），新的配置设置集合的所有属性都将使用默认值。</span><span class="sxs-lookup"><span data-stu-id="e0f42-127">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="e0f42-128">在创建新的 Lync Phone Edition 配置设置时更改单个属性值</span><span class="sxs-lookup"><span data-stu-id="e0f42-128">To change a single property value when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="e0f42-129">要创建使用不同属性值的设置，只需包含相应的参数和参数值。</span><span class="sxs-lookup"><span data-stu-id="e0f42-129">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="e0f42-130">例如, 若要创建一个 UC 电话配置设置的集合, 默认情况下, 需要电话锁定, 请使用如下所示的命令:</span><span class="sxs-lookup"><span data-stu-id="e0f42-130">For example, to create a collection of UC phone configuration settings that, by default, require phone locking, use a command like this:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="e0f42-131">创建新的 Lync Phone 版本配置设置时更改多个属性值</span><span class="sxs-lookup"><span data-stu-id="e0f42-131">To change multiple property values when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="e0f42-132">可以通过包含多个参数来修改多个属性值。</span><span class="sxs-lookup"><span data-stu-id="e0f42-132">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="e0f42-133">例如, 此命令强制执行电话锁定, 并且将最小 PIN 长度设置为8位:</span><span class="sxs-lookup"><span data-stu-id="e0f42-133">For example, this command enforces phone locking and also sets the minimum PIN length to 8 digits:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

<span data-ttu-id="e0f42-134">有关详细信息, 请参阅[CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15))。</span><span class="sxs-lookup"><span data-stu-id="e0f42-134">For details, see [New-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15)).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e0f42-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0f42-135">See Also</span></span>


[<span data-ttu-id="e0f42-136">删除 Lync Server 2013 中的现有 Lync Phone Edition 配置设置集合</span><span class="sxs-lookup"><span data-stu-id="e0f42-136">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="e0f42-137">在 Lync Server 2013 中配置 Lync Phone Edition 的安全设置</span><span class="sxs-lookup"><span data-stu-id="e0f42-137">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="e0f42-138">在 Lync Server 2013 中强制执行电话锁定</span><span class="sxs-lookup"><span data-stu-id="e0f42-138">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

