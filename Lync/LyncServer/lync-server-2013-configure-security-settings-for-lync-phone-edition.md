---
title: Lync Server 2013：为 Lync Phone Edition 配置安全设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure security settings for Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48184464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ce54b51207cc74d4ea0a57b1e66334432a6029e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a><span data-ttu-id="1057c-102">在 Lync Server 2013 中配置 Lync Phone Edition 的安全设置</span><span class="sxs-lookup"><span data-stu-id="1057c-102">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1057c-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1057c-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1057c-104">通过 SIP 安全设置和电话锁定设置，帮助改进运行 Lync Phone Edition 的设备的安全性。</span><span class="sxs-lookup"><span data-stu-id="1057c-104">Help improve the security of devices running Lync Phone Edition via your SIP security setting and phone lock settings.</span></span>

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a><span data-ttu-id="1057c-105">为 Lync Phone Edition 配置安全设置</span><span class="sxs-lookup"><span data-stu-id="1057c-105">To configure security settings for Lync Phone Edition</span></span>

1.  <span data-ttu-id="1057c-106">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="1057c-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1057c-107">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="1057c-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1057c-108">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="1057c-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1057c-109">在左侧导航栏中，单击“客户端”\*\*\*\*，然后单击“设备配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1057c-109">In the left navigation bar, click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="1057c-110">在“设备配置”\*\*\*\* 页上的设备配置列表中，双击要更改安全设置的配置。</span><span class="sxs-lookup"><span data-stu-id="1057c-110">On the **Device Configuration** page, in the list of device configurations, double-click the configuration for which you want to change security settings.</span></span>

5.  <span data-ttu-id="1057c-p102">在“编辑设备配置”\*\*\*\* 的“SIP 安全”\*\*\*\* 中，指定 SIP 安全级别。默认级别为“高”\*\*\*\*，建议使用此级别。</span><span class="sxs-lookup"><span data-stu-id="1057c-p102">In **Edit Device Configuration**, in **SIP security**, specify the SIP security level. The default level is **High**, which we recommend using.</span></span>

6.  <span data-ttu-id="1057c-p103">在“编辑设备配置”\*\*\*\* 中的“电话锁定”\*\*\*\* 下，选中或清除“强制设备锁定”\*\*\*\* 复选框（默认为选中）并指定最小 PIN 长度（默认为 6 个字符）和超时期限（默认为 10 分钟）。建议使用这些默认值或增加 PIN 长度和/或减小超时期限。</span><span class="sxs-lookup"><span data-stu-id="1057c-p103">In **Edit Device Configuration**, under **Phone Lock**, select or clear the **Enforce device locking** check box (selected by default) and specify the minimum PIN length (6 characters by default) and timeout period (10 minutes by default). We recommend using these defaults or increasing the PIN length and/or decreasing the timeout period.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1057c-115">有关详细信息，请参阅<A href="lync-server-2013-enforce-phone-locking.md">在 Lync Server 2013 中强制执行电话锁定</A>。</span><span class="sxs-lookup"><span data-stu-id="1057c-115">For details, see <A href="lync-server-2013-enforce-phone-locking.md">Enforce phone locking in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1057c-116">使用 Windows PowerShell Cmdlet 为 Lync Phone Edition 电话配置安全设置</span><span class="sxs-lookup"><span data-stu-id="1057c-116">Configuring Security Settings for Lync Phone Edition Phones by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1057c-117">可以使用 Lync Server 命令行管理程序和**CsUCPhoneConfiguration** cmdlet 来管理安全设置。</span><span class="sxs-lookup"><span data-stu-id="1057c-117">Security settings can be managed by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="1057c-118">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="1057c-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1057c-119">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="1057c-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-modify-the-sip-security-mode"></a><span data-ttu-id="1057c-120">修改 SIP 安全模式</span><span class="sxs-lookup"><span data-stu-id="1057c-120">To modify the SIP security mode</span></span>

  - <span data-ttu-id="1057c-p105">此命令将 UC 电话设置全局集合的 SIPSecurityMode 设置为“中”。还可以将 SIP 安全性设置为“低”或“高”（默认值）。</span><span class="sxs-lookup"><span data-stu-id="1057c-p105">This command sets the SIPSecurityMode for the global collection of UC phone settings to Medium. SIP security could also be set to Low or High (the default value).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a><span data-ttu-id="1057c-123">修改最小 PIN 长度</span><span class="sxs-lookup"><span data-stu-id="1057c-123">To modify the minimum PIN length</span></span>

  - <span data-ttu-id="1057c-124">在此示例中，会将所有 UC 电话设置修改为需要 7 位最小 PIN 长度。</span><span class="sxs-lookup"><span data-stu-id="1057c-124">In this example, all the UC phone settings are modified to require a minimum PIN length of 7 digits.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

<span data-ttu-id="1057c-125">有关详细信息，请参阅[CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="1057c-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1057c-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1057c-126">See Also</span></span>


[<span data-ttu-id="1057c-127">管理 Lync Server 2013 身份验证</span><span class="sxs-lookup"><span data-stu-id="1057c-127">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="1057c-128">在 Lync Server 2013 中管理设备、电话和客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="1057c-128">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

