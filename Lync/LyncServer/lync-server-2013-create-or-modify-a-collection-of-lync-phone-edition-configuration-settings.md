---
title: 创建或修改 Lync Phone Edition 配置设置的集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Lync Phone Edition configuration settings
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49733683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af910ccffd65f14b7f11919ab66ae95acbf4e09
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="87f76-102">在 Lync Server 2013 中创建或修改 Lync Phone Edition 配置设置的集合</span><span class="sxs-lookup"><span data-stu-id="87f76-102">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87f76-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="87f76-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="87f76-104">安装 Lync Server 时，将获取 Lync Phone Edition 设置的全局集合。</span><span class="sxs-lookup"><span data-stu-id="87f76-104">When you install Lync Server, you get a global collection of Lync Phone Edition settings.</span></span> <span data-ttu-id="87f76-105">这些设置适用于部署中运行 Lync Phone Edition 的所有设备。</span><span class="sxs-lookup"><span data-stu-id="87f76-105">These settings apply to all devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="87f76-106">您可以随时更改这些设置。</span><span class="sxs-lookup"><span data-stu-id="87f76-106">You can change these settings at any time.</span></span> <span data-ttu-id="87f76-107">还可以设置适用于特定站点中的设备的设置的新集合。</span><span class="sxs-lookup"><span data-stu-id="87f76-107">You can also set up a new collection of settings that apply to the devices in a specific site.</span></span> <span data-ttu-id="87f76-108">站点设置优先于全局设置。</span><span class="sxs-lookup"><span data-stu-id="87f76-108">Site settings take precedence over global settings.</span></span>

<span data-ttu-id="87f76-109">配置设置包含集合名称、范围（全局或站点）、SIP 安全设置、日志记录级别、语音服务质量 (QoS) 级别、电话锁定设置和电话锁定详细信息（即，a) 解锁个人标识号 (PIN) 所需花费的时间和 b) 电话在自行锁定之前保持空闲状态的时间长度）。</span><span class="sxs-lookup"><span data-stu-id="87f76-109">Configuration settings consist of the collection name, scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, how long the a) unlock personal identification number (PIN) must be and b) phone stays idle before locking itself.</span></span>

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a><span data-ttu-id="87f76-110">为现有集合创建 Lync Phone Edition 配置设置的集合或编辑设置的详细</span><span class="sxs-lookup"><span data-stu-id="87f76-110">To create a collection of Lync Phone Edition configuration settings or edit settings for an existing collection</span></span>

1.  <span data-ttu-id="87f76-111">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="87f76-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="87f76-112">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="87f76-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="87f76-113">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="87f76-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="87f76-114">在左侧导航栏中，单击“客户端”\*\*\*\*，然后单击“设备配置”\*\*\*\* 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="87f76-114">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="87f76-115">在“设备配置”\*\*\*\* 页上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="87f76-115">On the **Device Configuration** page, do one of the following:</span></span>
    
      - <span data-ttu-id="87f76-116">若要创建新的 Lync Phone Edition 配置设置集合，请单击 "**新建**"，选择一个网站，单击 **"确定**"，查看默认设置，如果需要，请进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="87f76-116">To create a new collection of Lync Phone Edition configuration settings, click **New**, select a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
      - <span data-ttu-id="87f76-117">若要编辑某个现有集合中的任意设置，请依次单击该集合、“编辑”\*\*\*\* 菜单和“显示详细信息”\*\*\*\*，然后进行更改。</span><span class="sxs-lookup"><span data-stu-id="87f76-117">To edit any of the settings in an existing collection, click the collection, click the **Edit** menu, click **Show details**, and then make your changes.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="87f76-p103">若要继续使用全局集合的默认设置，请依次单击全局集合、“编辑”<STRONG></STRONG>菜单、“删除”<STRONG></STRONG>和“确定”<STRONG></STRONG>。这不会删除全局集合，而只是将设置重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="87f76-p103">To go back to using the default settings for the global collection, click the global collection, click the <STRONG>Edit</STRONG> menu, click <STRONG>Delete</STRONG>, and then click <STRONG>OK</STRONG>. This will not delete the global collection; it just resets the settings to the defaults.</span></span>

        
        </div>

5.  <span data-ttu-id="87f76-120">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="87f76-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="87f76-121">使用 Windows PowerShell Cmdlet 创建新的 Lync Phone Edition 配置设置</span><span class="sxs-lookup"><span data-stu-id="87f76-121">Creating New Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="87f76-122">您可以使用 Windows PowerShell 和**CsUCPhoneConfiguration** cmdlet 来创建 Lync Phone Edition 配置设置（仅限在网站范围内）。</span><span class="sxs-lookup"><span data-stu-id="87f76-122">You can create Lync Phone Edition configuration settings can (at the site scope only) by using Windows PowerShell and the **New-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="87f76-123">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="87f76-123">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="87f76-124">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="87f76-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="87f76-125">创建使用默认值的新 Lync Phone Edition 配置设置</span><span class="sxs-lookup"><span data-stu-id="87f76-125">To create new Lync Phone Edition configuration settings that use the default values</span></span>

  - <span data-ttu-id="87f76-126">此命令为 Redmond 站点创建一组新的 UC 电话配置设置：</span><span class="sxs-lookup"><span data-stu-id="87f76-126">This command creates a new set of UC phone configuration settings for the Redmond site:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="87f76-127">由于前面的命令中未指定参数（必需的 Identity 参数之外），因此新的配置设置集合将对其所有属性使用默认值。</span><span class="sxs-lookup"><span data-stu-id="87f76-127">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="87f76-128">创建新的 Lync Phone Edition 配置设置时更改单个属性值</span><span class="sxs-lookup"><span data-stu-id="87f76-128">To change a single property value when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="87f76-p105">若要创建使用不同属性值的设置，只需包含相应的参数和参数值。例如，默认情况下，若要创建需要电话锁定的 UC 电话配置设置的集合，请使用与以下内容类似的命令：</span><span class="sxs-lookup"><span data-stu-id="87f76-p105">To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of UC phone configuration settings that, by default, require phone locking, use a command like this:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="87f76-131">创建新的 Lync Phone Edition 配置设置时更改多个属性值</span><span class="sxs-lookup"><span data-stu-id="87f76-131">To change multiple property values when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="87f76-p106">可通过包含多个参数来修改多个属性值。例如，此命令强制电话锁定并将最小 PIN 长度设置为 8 位：</span><span class="sxs-lookup"><span data-stu-id="87f76-p106">Multiple property values can be modified by including multiple parameters. For example, this command enforces phone locking and also sets the minimum PIN length to 8 digits:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

<span data-ttu-id="87f76-134">有关详细信息，请参阅[CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15))。</span><span class="sxs-lookup"><span data-stu-id="87f76-134">For details, see [New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15)).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="87f76-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87f76-135">See Also</span></span>


[<span data-ttu-id="87f76-136">在 Lync Server 2013 中删除 Lync Phone Edition 配置设置的现有集合</span><span class="sxs-lookup"><span data-stu-id="87f76-136">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="87f76-137">在 Lync Server 2013 中配置 Lync Phone Edition 的安全设置</span><span class="sxs-lookup"><span data-stu-id="87f76-137">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="87f76-138">在 Lync Server 2013 中强制执行电话锁定</span><span class="sxs-lookup"><span data-stu-id="87f76-138">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

