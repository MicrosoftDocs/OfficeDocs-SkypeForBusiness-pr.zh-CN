---
title: Lync Server 2013：启用或禁用 Iphone 的推送通知
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling push notifications for iPhones
ms:assetid: 8bbf531a-807f-4a8f-814a-94bfed8f97ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688122(v=OCS.15)
ms:contentKeyID: 49733719
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a73d0f32da5063f98da662e85ec531de6801a428
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-push-notifications-for-iphones-in-lync-server-2013"></a><span data-ttu-id="02814-102">在 Lync Server 2013 中启用或禁用 Iphone 的推送通知</span><span class="sxs-lookup"><span data-stu-id="02814-102">Enabling or disabling push notifications for iPhones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02814-103">_**主题上次修改时间：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="02814-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="02814-104">即使在移动应用程序处于非活动状态时，也可以将 "锁屏提醒"、图标或通知形式的推送通知发送到 iPhone。</span><span class="sxs-lookup"><span data-stu-id="02814-104">Push notifications, in the form of badges, icons, or alerts, can be sent to an iPhone even when the mobile application is inactive.</span></span> <span data-ttu-id="02814-105">推送通知通知用户诸如新的或错过的 IM 邀请和语音邮件等事件。</span><span class="sxs-lookup"><span data-stu-id="02814-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="02814-106">你可以通过使用 Lync Server 2013 控制面板或 Lync Server 2013 管理外壳程序启用或禁用 iPhone 的推送通知。</span><span class="sxs-lookup"><span data-stu-id="02814-106">You can enable or disable push notifications for iPhone by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-enable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a><span data-ttu-id="02814-107">使用 Lync Server "控制面板" 启用 iPhone 的推送通知</span><span class="sxs-lookup"><span data-stu-id="02814-107">To enable push notifications for iPhone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="02814-108">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="02814-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="02814-109">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="02814-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="02814-110">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="02814-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="02814-111">在左侧导航栏中，单击 "**客户端**"，然后单击 "**推送通知配置**" 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="02814-111">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="02814-112">在 "**推送通知配置**" 页面上，单击要编辑的网站，单击 "**编辑**" 菜单，然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="02814-112">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="02814-113">单击 "**启用 Apple 推送通知**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="02814-113">Click the **Enable Apple push notifications** checkbox.</span></span>

6.  <span data-ttu-id="02814-114">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="02814-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a><span data-ttu-id="02814-115">使用 Lync Server "控制面板" 禁用 iPhone 的推送通知</span><span class="sxs-lookup"><span data-stu-id="02814-115">To disable push notifications for iPhone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="02814-116">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="02814-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="02814-117">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="02814-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="02814-118">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="02814-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="02814-119">在左侧导航栏中，单击 "**客户端**"，然后单击 "**推送通知配置**" 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="02814-119">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="02814-120">在 "**推送通知配置**" 页面上，单击要编辑的网站，单击 "**编辑**" 菜单，然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="02814-120">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="02814-121">清除 "**启用 Apple 推送通知**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="02814-121">Clear the **Enable Apple push notifications** checkbox.</span></span>

6.  <span data-ttu-id="02814-122">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="02814-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-to-iphone-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="02814-123">使用 Windows PowerShell Cmdlet 启用或禁用对 iPhone 的推送通知</span><span class="sxs-lookup"><span data-stu-id="02814-123">Enabling or Disabling Push Notifications to iPhone by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="02814-124">通过使用**CsPushNotificationConfiguration** cmdlet，可以启用或禁用将通知推送到 Apple iPhone。</span><span class="sxs-lookup"><span data-stu-id="02814-124">Push notifications to Apple iPhone can be enabled or disabled by using the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="02814-125">你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="02814-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="02814-126">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="02814-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-push-notifications-for-iphone"></a><span data-ttu-id="02814-127">启用 iPhone 的推送通知</span><span class="sxs-lookup"><span data-stu-id="02814-127">To enable push notifications for iPhone</span></span>

  - <span data-ttu-id="02814-128">若要启用 iPhone 的推送通知，请将 EnableApplePushNotificationService 属性的值设置为 True （$True）。</span><span class="sxs-lookup"><span data-stu-id="02814-128">To enable push notifications for iPhone set the value of the EnableApplePushNotificationService property to True ($True).</span></span> <span data-ttu-id="02814-129">例如：</span><span class="sxs-lookup"><span data-stu-id="02814-129">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone"></a><span data-ttu-id="02814-130">禁用 iPhone 的推送通知</span><span class="sxs-lookup"><span data-stu-id="02814-130">To disable push notifications for iPhone</span></span>

  - <span data-ttu-id="02814-131">若要禁用 iPhone 的推送通知，请将 EnableApplePushNotificationService 属性的值设置为 False （$False）。</span><span class="sxs-lookup"><span data-stu-id="02814-131">To disable push notifications for iPhone set the value of the EnableApplePushNotificationService property to False ($False).</span></span> <span data-ttu-id="02814-132">例如：</span><span class="sxs-lookup"><span data-stu-id="02814-132">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False

</div>

<span data-ttu-id="02814-133">有关详细信息，请参阅[CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="02814-133">For more information, see the help topic for the [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="02814-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="02814-134">See Also</span></span>


[<span data-ttu-id="02814-135">在 Lync Server 2013 中配置推送通知</span><span class="sxs-lookup"><span data-stu-id="02814-135">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

