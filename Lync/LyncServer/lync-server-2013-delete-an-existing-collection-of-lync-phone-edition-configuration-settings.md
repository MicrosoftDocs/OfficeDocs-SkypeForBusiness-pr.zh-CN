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
ms.openlocfilehash: dbf7d49a14ce45550777c6c122cd799f6a511f76
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="49eff-102">删除 Lync Server 2013 中的现有 Lync Phone Edition 配置设置集合</span><span class="sxs-lookup"><span data-stu-id="49eff-102">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49eff-103">_**主题上次修改时间：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="49eff-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="49eff-104">如果不再希望使用运行 Lync Phone Edition 的设备的设置集合，请将其删除。</span><span class="sxs-lookup"><span data-stu-id="49eff-104">If you no longer want to use a collection of settings for devices running Lync Phone Edition, delete it.</span></span> <span data-ttu-id="49eff-105">如果您删除网站的集合，全局设置将应用于该网站中的电话。</span><span class="sxs-lookup"><span data-stu-id="49eff-105">If you delete a collection for a site, the global settings will apply to the phones in that site.</span></span> <span data-ttu-id="49eff-106">不能删除全局集合。</span><span class="sxs-lookup"><span data-stu-id="49eff-106">You cannot delete the global collection.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="49eff-107">你可能只想更改某些设置，而不是删除集合。</span><span class="sxs-lookup"><span data-stu-id="49eff-107">Instead of deleting a collection, you might just want to change some of the settings.</span></span> <span data-ttu-id="49eff-108">有关如何执行此操作的详细信息，请参阅<A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">在 Lync Server 2013 中创建或修改 Lync Phone Edition 配置设置的集合</A>。</span><span class="sxs-lookup"><span data-stu-id="49eff-108">For details about how to do so, see <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="49eff-109">删除 Lync Phone Edition 配置设置的集合</span><span class="sxs-lookup"><span data-stu-id="49eff-109">To delete a collection of Lync Phone Edition configuration settings</span></span>

1.  <span data-ttu-id="49eff-110">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="49eff-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="49eff-111">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="49eff-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="49eff-112">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="49eff-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="49eff-113">在左侧导航栏中，单击 "**客户端**"，然后单击 "**设备配置**" 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="49eff-113">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="49eff-114">在 "**设备配置**" 页面上，单击要删除的集合，单击 "**编辑**" 菜单，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="49eff-114">On the **Device Configuration** page, click the collection you want to delete, click the **Edit** menu, and then click **Delete**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="49eff-115">如果删除全局集合，则这些设置只会还原为默认设置。</span><span class="sxs-lookup"><span data-stu-id="49eff-115">If you delete the global collection, the settings just revert to the default settings.</span></span> <span data-ttu-id="49eff-116">该集合不会消失。</span><span class="sxs-lookup"><span data-stu-id="49eff-116">The collection does not go away.</span></span>

    
    </div>

5.  <span data-ttu-id="49eff-117">在确认框中，单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="49eff-117">In the confirmation box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="49eff-118">使用 Windows PowerShell Cmdlet 删除 Lync 手机版配置设置</span><span class="sxs-lookup"><span data-stu-id="49eff-118">Removing Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="49eff-119">你可以使用 Windows PowerShell 和**CsUCConfiguration** Cmdlet 删除 Lync 手机版配置设置。</span><span class="sxs-lookup"><span data-stu-id="49eff-119">You can delete Lync Phone Edition configuration settings by using Windows PowerShell and the **Remove-CsUCConfiguration** cmdlet.</span></span> <span data-ttu-id="49eff-120">你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="49eff-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="49eff-121">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="49eff-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="49eff-122">删除指定的 Lync Phone Edition 配置设置集合</span><span class="sxs-lookup"><span data-stu-id="49eff-122">To remove a specified collection of Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="49eff-123">此命令将删除应用于雷德蒙站点的 UC 电话配置设置：</span><span class="sxs-lookup"><span data-stu-id="49eff-123">This command deletes the UC phone configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="49eff-124">删除应用到网站范围的所有 Lync Phone Edition 配置设置</span><span class="sxs-lookup"><span data-stu-id="49eff-124">To remove all of the Lync Phone Edition configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="49eff-125">此命令将删除应用到服务作用域的所有 UC 手机配置设置：</span><span class="sxs-lookup"><span data-stu-id="49eff-125">This command removes all the UC phone configuration settings applied to the service scope:</span></span>
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a><span data-ttu-id="49eff-126">删除禁用电话锁定的所有 Lync Phone Edition 配置设置</span><span class="sxs-lookup"><span data-stu-id="49eff-126">To remove all of the Lync Phone Edition configuration settings where phone locking is disabled</span></span>

  - <span data-ttu-id="49eff-127">此命令将删除已禁用电话锁定的 UC 手机配置设置的任何集合：</span><span class="sxs-lookup"><span data-stu-id="49eff-127">This command deletes any collection of UC phone configuration settings where phone locking has been disabled:</span></span>
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

<span data-ttu-id="49eff-128">有关详细信息，请参阅[Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15))。</span><span class="sxs-lookup"><span data-stu-id="49eff-128">For details, see [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15)).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

