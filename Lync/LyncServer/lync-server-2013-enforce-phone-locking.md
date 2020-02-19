---
title: Lync Server 2013：强制执行电话锁定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enforce phone locking
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520963(v=OCS.15)
ms:contentKeyID: 48183594
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8473809982a58ccc966482cd72223e0b234dd9ec
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enforce-phone-locking-in-lync-server-2013"></a><span data-ttu-id="4fe20-102">在 Lync Server 2013 中强制执行电话锁定</span><span class="sxs-lookup"><span data-stu-id="4fe20-102">Enforce phone locking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fe20-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4fe20-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4fe20-104">出于安全考虑，可以锁定 Lync Phone Edition 设备。</span><span class="sxs-lookup"><span data-stu-id="4fe20-104">Lync Phone Edition devices can be locked for security purposes.</span></span> <span data-ttu-id="4fe20-105">如果您强制执行电话锁定，则运行 Lync Phone Edition 的设备将在您配置的一段时间后锁定。</span><span class="sxs-lookup"><span data-stu-id="4fe20-105">If you enforce phone lock, the device running Lync Phone Edition locks after a period of time that you configure.</span></span> <span data-ttu-id="4fe20-106">当电话锁定时，用户可以打电话，但不能访问日历和联系人信息、语音邮件或呼叫日志或使用搜索。</span><span class="sxs-lookup"><span data-stu-id="4fe20-106">When a phone is locked, a user can make calls but cannot access calendar and contact information, voice mail, or call logs or use search.</span></span> <span data-ttu-id="4fe20-107">若要解锁电话，用户可以输入 PIN。</span><span class="sxs-lookup"><span data-stu-id="4fe20-107">To unlock the phone, the user enters a PIN.</span></span>

<span data-ttu-id="4fe20-108">若要强制执行电话锁定，请使用 Lync Server 控制面板或 Lync Server PowerShell cmdlet 启用和配置电话锁定。</span><span class="sxs-lookup"><span data-stu-id="4fe20-108">To enforce phone lock, enable and configure it by using Lync Server Control Panel or Lync Server PowerShell cmdlets.</span></span> <span data-ttu-id="4fe20-109">您可以在全局范围内或仅在其配置了的站点内强制执行电话锁定。</span><span class="sxs-lookup"><span data-stu-id="4fe20-109">You can enforce phone lock globally or only within the site for which it is configured.</span></span>

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a><span data-ttu-id="4fe20-110">配置和强制实施电话锁定</span><span class="sxs-lookup"><span data-stu-id="4fe20-110">To configure and enforce the phone lock</span></span>

1.  <span data-ttu-id="4fe20-111">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="4fe20-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4fe20-112">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="4fe20-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4fe20-113">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="4fe20-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4fe20-114">单击“客户端”\*\*\*\*，然后单击“设备配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fe20-114">Click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="4fe20-115">在“设备配置”\*\*\*\* 选项卡上的设备配置列表中，双击要更改电话锁定设置的配置。</span><span class="sxs-lookup"><span data-stu-id="4fe20-115">On the **Device Configuration** tab, in the list of device configurations, double-click the configuration for which you want to change the phone lock settings.</span></span>

5.  <span data-ttu-id="4fe20-116">在“编辑设备配置”\*\*\*\* 对话框中，确认选中了“强制设备锁定”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="4fe20-116">In the **Edit Device Configuration** dialog box, verify that the **Enforce device locking** check box is selected.</span></span>

6.  <span data-ttu-id="4fe20-117">在 "**最小 PIN 长度**" 中，接受解锁 PIN 必须包含的最小位数数的默认值，或指定新值。</span><span class="sxs-lookup"><span data-stu-id="4fe20-117">In **Minimum PIN length**, accept the default value for the minimum number of digits that the unlock PIN must contain or specify a new value.</span></span> <span data-ttu-id="4fe20-118">PIN 长度的范围是4到15位数字，默认值为6。</span><span class="sxs-lookup"><span data-stu-id="4fe20-118">The range for the PIN length is four to 15 digits, and the default is six.</span></span>

7.  <span data-ttu-id="4fe20-119">在 "**电话锁定超时**" 中，接受电话锁定自身之前的最短时间长度的默认值，或指定新值。</span><span class="sxs-lookup"><span data-stu-id="4fe20-119">In **Phone lock time-out**, accept the default value for the minimum length of time before the phone locks itself or specify a new value.</span></span> <span data-ttu-id="4fe20-120">超时的范围是0到60分钟，默认值为10。</span><span class="sxs-lookup"><span data-stu-id="4fe20-120">The range for the timeout is 0 to 60 minutes, and the default is 10.</span></span> <span data-ttu-id="4fe20-121">以 HH： MM： SS 的格式输入值。</span><span class="sxs-lookup"><span data-stu-id="4fe20-121">Enter the value in the format HH:MM:SS.</span></span>

8.  <span data-ttu-id="4fe20-122">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4fe20-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4fe20-123">使用 Windows PowerShell Cmdlet 强制进行电话锁定</span><span class="sxs-lookup"><span data-stu-id="4fe20-123">Enforcing Phone Locking by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4fe20-124">可以通过使用 CsUCPhoneConfiguration cmdlet 来强制实施电话锁定。</span><span class="sxs-lookup"><span data-stu-id="4fe20-124">Phone locking can be enforced by using the Set-CsUCPhoneConfiguration cmdlet.</span></span> <span data-ttu-id="4fe20-125">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="4fe20-125">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4fe20-126">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="4fe20-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-phone-locking"></a><span data-ttu-id="4fe20-127">启用电话锁定</span><span class="sxs-lookup"><span data-stu-id="4fe20-127">To enable phone locking</span></span>

  - <span data-ttu-id="4fe20-128">以下命令可为 Redmond 站点启用电话锁定。</span><span class="sxs-lookup"><span data-stu-id="4fe20-128">The following command enables phone locking for the Redmond site.</span></span> <span data-ttu-id="4fe20-129">若要禁用电话锁定，请将 EnforcePhoneLock 属性设置为 False ($False)。</span><span class="sxs-lookup"><span data-stu-id="4fe20-129">To disable phone locking, set the EnforcePhoneLock property to False ($False).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a><span data-ttu-id="4fe20-130">启用电话锁定和修改电话锁定超时</span><span class="sxs-lookup"><span data-stu-id="4fe20-130">To enable phone locking and modify the phone lock timeout</span></span>

  - <span data-ttu-id="4fe20-131">此命令启用电话锁定，还将电话锁定超时设置为 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="4fe20-131">This command enables phone locking and also sets the phone lock timeout to 30 minutes.</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a><span data-ttu-id="4fe20-132">在整个组织中启用电话锁定</span><span class="sxs-lookup"><span data-stu-id="4fe20-132">To enable phone locking throughout the organization</span></span>

  - <span data-ttu-id="4fe20-133">在此示例中，在组织内使用的所有 UC 电话配置设置中都启用了电话锁定。</span><span class="sxs-lookup"><span data-stu-id="4fe20-133">In this example, phone locking is enabled on all the UC phone configuration settings in use in the organization.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

<span data-ttu-id="4fe20-134">有关详细信息，请参阅[CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="4fe20-134">For more information, see the help topic for the [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4fe20-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4fe20-135">See Also</span></span>


[<span data-ttu-id="4fe20-136">管理 Lync Server 2013 身份验证</span><span class="sxs-lookup"><span data-stu-id="4fe20-136">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="4fe20-137">在 Lync Server 2013 中管理设备、电话和客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="4fe20-137">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

