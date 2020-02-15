---
title: Lync Server 2013：查看 PIN 策略信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PIN policy inforrmation
ms:assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687985(v=OCS.15)
ms:contentKeyID: 49733575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ab1705d7af62b6a44d278b666e619fae119540c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-pin-policy-inforrmation-in-lync-server-2013"></a><span data-ttu-id="28acb-102">在 Lync Server 2013 中查看 PIN 策略信息</span><span class="sxs-lookup"><span data-stu-id="28acb-102">View PIN policy inforrmation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28acb-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="28acb-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="28acb-104">您可以使用 " **PIN 策略**" 选项卡查看使用 IP 电话连接到 Lync 2013 的用户的个人标识号（PIN）身份验证。</span><span class="sxs-lookup"><span data-stu-id="28acb-104">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Lync 2013 with IP Phones.</span></span> <span data-ttu-id="28acb-105">要使用 PIN 身份验证，请确保在 Web 服务设置中选中“启用 PIN 身份验证”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="28acb-105">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span> <span data-ttu-id="28acb-106">有关详细信息，请参阅[在 Lync Server 2013 中修改现有的 Web 服务配置设置](lync-server-2013-modify-existing-web-service-configuration-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="28acb-106">For details, see [Modify existing Web Service configuration settings in Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).</span></span>

<span data-ttu-id="28acb-107">按照以下步骤修改用户级别或站点级别的 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="28acb-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span>

<div>

## <a name="to-view-information-about-a-pin-policy-in-lync-server-control-panel"></a><span data-ttu-id="28acb-108">在 Lync Server 控制面板中查看有关 PIN 策略的信息</span><span class="sxs-lookup"><span data-stu-id="28acb-108">To view information about a PIN policy in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="28acb-109">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户，登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="28acb-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="28acb-110">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="28acb-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="28acb-111">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="28acb-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="28acb-112">在左侧导航栏中，单击“安全性”\*\*\*\*，然后单击“PIN 策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="28acb-112">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="28acb-113">在 " **PIN 策略**" 页上，单击某个策略，单击 "**编辑**"，然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="28acb-113">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="28acb-114">使用 Windows PowerShell Cmdlet 查看 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="28acb-114">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="28acb-115">您还可以使用 Windows PowerShell 和 Get-cspinpolicy cmdlet 查看 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="28acb-115">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="28acb-116">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="28acb-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="28acb-117">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="28acb-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-pin-policies"></a><span data-ttu-id="28acb-118">查看 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="28acb-118">To view PIN policies</span></span>

  - <span data-ttu-id="28acb-119">若要查看有关所有 PIN 策略的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="28acb-119">To view information about all your PIN policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsPinPolicy
    
    <span data-ttu-id="28acb-120">这将返回与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="28acb-120">That will return information similar to this:</span></span>
    
        Identity             : Global
        Description          :
        MinPasswordLength    : 5
        PINHistoryCount      : 0
        AllowCommonPatterns  : False
        PINLifetime          : 0
        MaximumLogonAttempts :

</div>

<span data-ttu-id="28acb-121">有关详细信息，请参阅[get-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsPinPolicy) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="28acb-121">For more information, see the help topic for the [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsPinPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="28acb-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28acb-122">See Also</span></span>


[<span data-ttu-id="28acb-123">在 Lync Server 2013 中修改现有的 Web 服务配置设置</span><span class="sxs-lookup"><span data-stu-id="28acb-123">Modify existing Web Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-modify-existing-web-service-configuration-settings.md)  
[<span data-ttu-id="28acb-124">在 Lync Server 2013 中创建新的 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="28acb-124">Create a new PIN policy in Lync Server 2013</span></span>](lync-server-2013-create-a-new-pin-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

