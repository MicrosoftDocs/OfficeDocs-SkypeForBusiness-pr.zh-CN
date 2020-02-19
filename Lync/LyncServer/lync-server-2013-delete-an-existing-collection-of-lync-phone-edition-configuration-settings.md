---
title: 删除 Lync Phone Edition 配置设置的现有集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of Lync Phone Edition configuration settings
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49733574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac7ebd5c1c0340b8cbe406901290903f411fe11e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="e2a7a-102">在 Lync Server 2013 中删除 Lync Phone Edition 配置设置的现有集合</span><span class="sxs-lookup"><span data-stu-id="e2a7a-102">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2a7a-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e2a7a-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e2a7a-104">如果您不想再对运行 Lync Phone Edition 的设备使用设置集合，请将其删除。</span><span class="sxs-lookup"><span data-stu-id="e2a7a-104">If you no longer want to use a collection of settings for devices running Lync Phone Edition, delete it.</span></span> <span data-ttu-id="e2a7a-105">如果删除某一站点的集合，则全局设置将应用于该站点中的电话。</span><span class="sxs-lookup"><span data-stu-id="e2a7a-105">If you delete a collection for a site, the global settings will apply to the phones in that site.</span></span> <span data-ttu-id="e2a7a-106">不能删除全局集合。</span><span class="sxs-lookup"><span data-stu-id="e2a7a-106">You cannot delete the global collection.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="e2a7a-107">您可能不想删除集合，只是想更改其中的一些设置。</span><span class="sxs-lookup"><span data-stu-id="e2a7a-107">Instead of deleting a collection, you might just want to change some of the settings.</span></span> <span data-ttu-id="e2a7a-108">有关如何执行此操作的详细信息，请参阅<A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">在 Lync Server 2013 中创建或修改 Lync Phone Edition 配置设置的集合</A>。</span><span class="sxs-lookup"><span data-stu-id="e2a7a-108">For details about how to do so, see <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="e2a7a-109">删除 Lync Phone Edition 配置设置的集合</span><span class="sxs-lookup"><span data-stu-id="e2a7a-109">To delete a collection of Lync Phone Edition configuration settings</span></span>

1.  <span data-ttu-id="e2a7a-110">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="e2a7a-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e2a7a-111">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="e2a7a-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e2a7a-112">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="e2a7a-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e2a7a-113">在左侧导航栏中，单击“客户端”\*\*\*\*，然后单击“设备配置”\*\*\*\* 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="e2a7a-113">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="e2a7a-114">在“设备配置”\*\*\*\* 页上，单击要删除的集合，单击“编辑”\*\*\*\* 菜单，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e2a7a-114">On the **Device Configuration** page, click the collection you want to delete, click the **Edit** menu, and then click **Delete**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e2a7a-p104">如果删除全局集合，设置将只恢复为默认设置。集合不会消失。</span><span class="sxs-lookup"><span data-stu-id="e2a7a-p104">If you delete the global collection, the settings just revert to the default settings. The collection does not go away.</span></span>

    
    </div>

5.  <span data-ttu-id="e2a7a-117">在确认框中，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e2a7a-117">In the confirmation box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e2a7a-118">使用 Windows PowerShell Cmdlet 删除 Lync Phone Edition 配置设置</span><span class="sxs-lookup"><span data-stu-id="e2a7a-118">Removing Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e2a7a-119">您可以使用 Windows PowerShell 和**CsUCConfiguration** Cmdlet 删除 Lync Phone Edition 配置设置。</span><span class="sxs-lookup"><span data-stu-id="e2a7a-119">You can delete Lync Phone Edition configuration settings by using Windows PowerShell and the **Remove-CsUCConfiguration** cmdlet.</span></span> <span data-ttu-id="e2a7a-120">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e2a7a-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e2a7a-121">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="e2a7a-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="e2a7a-122">删除指定的 Lync Phone Edition 配置设置集合</span><span class="sxs-lookup"><span data-stu-id="e2a7a-122">To remove a specified collection of Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="e2a7a-123">此命令可删除应用于 Redmond 站点的 UC 电话配置设置：</span><span class="sxs-lookup"><span data-stu-id="e2a7a-123">This command deletes the UC phone configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="e2a7a-124">删除应用到站点范围的所有 Lync Phone Edition 配置设置</span><span class="sxs-lookup"><span data-stu-id="e2a7a-124">To remove all of the Lync Phone Edition configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="e2a7a-125">此命令可删除应用于服务范围的所有 UC 电话配置设置：</span><span class="sxs-lookup"><span data-stu-id="e2a7a-125">This command removes all the UC phone configuration settings applied to the service scope:</span></span>
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a><span data-ttu-id="e2a7a-126">删除禁用电话锁定的所有 Lync Phone Edition 配置设置</span><span class="sxs-lookup"><span data-stu-id="e2a7a-126">To remove all of the Lync Phone Edition configuration settings where phone locking is disabled</span></span>

  - <span data-ttu-id="e2a7a-127">此命令可删除已禁用电话锁定的所有 UC 电话配置设置集合：</span><span class="sxs-lookup"><span data-stu-id="e2a7a-127">This command deletes any collection of UC phone configuration settings where phone locking has been disabled:</span></span>
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

<span data-ttu-id="e2a7a-128">有关详细信息，请参阅[CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15))。</span><span class="sxs-lookup"><span data-stu-id="e2a7a-128">For details, see [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15)).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

