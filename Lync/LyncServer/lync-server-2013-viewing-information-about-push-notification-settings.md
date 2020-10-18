---
title: Lync Server 2013：查看有关推送通知设置的信息
description: Lync Server 2013：查看有关推送通知设置的信息。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing information about push notification settings
ms:assetid: be5c6b01-4294-4d17-9772-fed40201e8a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721868(v=OCS.15)
ms:contentKeyID: 49733801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44ee876df341833c93e97fd16664940629754a6d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580028"
---
# <a name="viewing-information-about-push-notification-settings-in-lync-server-2013"></a><span data-ttu-id="6500b-103">查看 Lync Server 2013 中的推送通知设置的相关信息</span><span class="sxs-lookup"><span data-stu-id="6500b-103">Viewing information about push notification settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6500b-104">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="6500b-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="6500b-105">即使移动应用程序处于非活动状态，也可以向移动设备发送推送通知（以徽章、图标或警告的形式）。</span><span class="sxs-lookup"><span data-stu-id="6500b-105">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="6500b-106">推送通知会将一些事件（例如，新的或错过的 IM 邀请和语音邮件）告知用户。</span><span class="sxs-lookup"><span data-stu-id="6500b-106">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="6500b-107">您可以使用 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序查看移动设备的信息推送通知设置。</span><span class="sxs-lookup"><span data-stu-id="6500b-107">You can view information push notifications settings for mobile devices by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-view-push-notification-information-from-lync-server-control-panel"></a><span data-ttu-id="6500b-108">从 Lync Server 控制面板查看推送通知信息</span><span class="sxs-lookup"><span data-stu-id="6500b-108">To view push notification information from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="6500b-109">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="6500b-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6500b-110">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="6500b-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6500b-111">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="6500b-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6500b-112">在左侧导航栏中，单击“客户端”\*\*\*\*，然后单击“推送通知配置”\*\*\*\* 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="6500b-112">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="6500b-113">在 " **推送通知配置** " 页上，单击要查看的网站，单击 " **编辑** " 菜单，然后单击 " **显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="6500b-113">On the **Push Notification Configuration** page, click the site you want to view, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-push-notification-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6500b-114">使用 Windows PowerShell Cmdlet 查看推送通知信息</span><span class="sxs-lookup"><span data-stu-id="6500b-114">Viewing Push Notification Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6500b-115">您可以使用 Windows PowerShell 和 **CsPushNotificationConfiguration** cmdlet 查看推送通知配置设置。</span><span class="sxs-lookup"><span data-stu-id="6500b-115">You can view push notification configuration settings by using Windows PowerShell and the **Get-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="6500b-116">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6500b-116">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6500b-117">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="6500b-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-push-notification-configuration-information"></a><span data-ttu-id="6500b-118">查看推送通知配置信息</span><span class="sxs-lookup"><span data-stu-id="6500b-118">To view push notification configuration information</span></span>

  - <span data-ttu-id="6500b-119">若要查看有关所有推送通知配置设置的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="6500b-119">To view information about all your push notification configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsPushNotificationConfiguration
    
    <span data-ttu-id="6500b-120">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="6500b-120">That will return information similar to this:</span></span>
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

</div>

<span data-ttu-id="6500b-121">有关详细信息，请参阅 [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="6500b-121">For more information, see the help topic for the [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6500b-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6500b-122">See Also</span></span>


[<span data-ttu-id="6500b-123">在 Lync Server 2013 中配置推送通知</span><span class="sxs-lookup"><span data-stu-id="6500b-123">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

