---
title: Lync Server 2013：为 Windows phone 启用或禁用推送通知
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling push notifications for Windows Phones
ms:assetid: a34f0c5c-4228-40e3-9d93-bc0b5df4895d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688162(v=OCS.15)
ms:contentKeyID: 49733767
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01a30a7e0effbcd9d80f30bccf68edb9804641f4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048115"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-push-notifications-for-windows-phones-in-lync-server-2013"></a><span data-ttu-id="7621d-102">在 Lync Server 2013 中为 Windows phone 启用或禁用推送通知</span><span class="sxs-lookup"><span data-stu-id="7621d-102">Enabling or disabling push notifications for Windows Phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7621d-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="7621d-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="7621d-104">即使移动应用程序处于非活动状态，也可以将徽章、图标或警报等推送通知发送到 Windows Phone。</span><span class="sxs-lookup"><span data-stu-id="7621d-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a Windows Phone even when the mobile application is inactive.</span></span> <span data-ttu-id="7621d-105">推送通知会将一些事件（例如，新的或错过的 IM 邀请和语音邮件）告知用户。</span><span class="sxs-lookup"><span data-stu-id="7621d-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="7621d-106">可以使用 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序启用或禁用 Windows Phone 设备的推送通知。</span><span class="sxs-lookup"><span data-stu-id="7621d-106">You can enable or disable push notifications for Windows Phone devices by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-enable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a><span data-ttu-id="7621d-107">使用 Lync Server 控制面板为 Windows Phone 启用推送通知</span><span class="sxs-lookup"><span data-stu-id="7621d-107">To enable push notifications for Windows Phone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="7621d-108">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="7621d-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7621d-109">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="7621d-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7621d-110">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="7621d-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7621d-111">在左侧导航栏中，单击“客户端”\*\*\*\*，然后单击“推送通知配置”\*\*\*\* 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="7621d-111">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="7621d-112">在 "**推送通知配置**" 页上，单击要编辑的网站，单击 "**编辑**" 菜单，然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="7621d-112">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="7621d-113">单击“启用 Microsoft 推送通知”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="7621d-113">Click the **Enable Microsoft push notifications** checkbox.</span></span>

6.  <span data-ttu-id="7621d-114">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7621d-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a><span data-ttu-id="7621d-115">使用 Lync Server 控制面板禁用 Windows Phone 推送通知</span><span class="sxs-lookup"><span data-stu-id="7621d-115">To disable push notifications for Windows Phone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="7621d-116">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="7621d-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7621d-117">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="7621d-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7621d-118">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="7621d-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7621d-119">在左侧导航栏中，单击“客户端”\*\*\*\*，然后单击“推送通知配置”\*\*\*\* 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="7621d-119">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="7621d-120">在 "**推送通知配置**" 页上，单击要编辑的网站，单击 "**编辑**" 菜单，然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="7621d-120">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="7621d-121">清除“启用 Microsoft 推送通知”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="7621d-121">Clear the **Enable Microsoft push notifications** checkbox.</span></span>

6.  <span data-ttu-id="7621d-122">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7621d-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-for-windows-phone-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7621d-123">使用 Windows PowerShell Cmdlet 为 Windows Phone 启用或禁用推送通知</span><span class="sxs-lookup"><span data-stu-id="7621d-123">Enabling or Disabling Push Notifications for Windows Phone by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7621d-124">您可以使用**CsPushNotificationConfiguration** Cmdlet 为 Windows Phone 启用或禁用推送通知。</span><span class="sxs-lookup"><span data-stu-id="7621d-124">You can enable or disable push notifications for Windows Phone by using the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="7621d-125">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7621d-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7621d-126">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="7621d-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-push-notifications-for-windows-phone"></a><span data-ttu-id="7621d-127">为 Windows Phone 启用推送通知</span><span class="sxs-lookup"><span data-stu-id="7621d-127">To enable push notifications for Windows Phone</span></span>

  - <span data-ttu-id="7621d-128">若要为 Windows Phone 启用推送通知，请将 EnableMicrosoftPushNotificationService 属性的值设置为 True （$True）。</span><span class="sxs-lookup"><span data-stu-id="7621d-128">To enable push notifications for Windows Phone set the value of the EnableMicrosoftPushNotificationService property to True ($True).</span></span> <span data-ttu-id="7621d-129">例如：</span><span class="sxs-lookup"><span data-stu-id="7621d-129">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone"></a><span data-ttu-id="7621d-130">禁用 Windows Phone 推送通知</span><span class="sxs-lookup"><span data-stu-id="7621d-130">To disable push notifications for Windows Phone</span></span>

  - <span data-ttu-id="7621d-131">若要禁用 Windows Phone 推送通知，请将 EnableMicrosoftPushNotificationService 属性的值设置为 False （$False）。</span><span class="sxs-lookup"><span data-stu-id="7621d-131">To disable push notifications for Windows Phone set the value of the EnableMicrosoftPushNotificationService property to False ($False).</span></span> <span data-ttu-id="7621d-132">例如：</span><span class="sxs-lookup"><span data-stu-id="7621d-132">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $False

</div>

<span data-ttu-id="7621d-133">有关详细信息，请参阅 [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="7621d-133">For more information, see the help topic for the [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7621d-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7621d-134">See Also</span></span>


[<span data-ttu-id="7621d-135">在 Lync Server 2013 中配置推送通知</span><span class="sxs-lookup"><span data-stu-id="7621d-135">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

