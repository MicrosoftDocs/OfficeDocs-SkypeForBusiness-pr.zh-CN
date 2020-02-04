---
title: Lync Server 2013：查看 Lync Phone Edition 配置设置信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Lync Phone Edition configuration settings information
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49733564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a58450b1d69ce757f40194d179606f332e152d7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a><span data-ttu-id="846e4-102">在 Lync Server 2013 中查看 Lync Phone Edition 配置设置信息</span><span class="sxs-lookup"><span data-stu-id="846e4-102">View Lync Phone Edition configuration settings information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="846e4-103">_**主题上次修改时间：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="846e4-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="846e4-104">你可以查看有关运行 Lync Phone Edition 的设备的配置信息。</span><span class="sxs-lookup"><span data-stu-id="846e4-104">You can view configuration information about devices running Lync Phone Edition.</span></span> <span data-ttu-id="846e4-105">信息组织到集合中。</span><span class="sxs-lookup"><span data-stu-id="846e4-105">The information is organized into collections.</span></span> <span data-ttu-id="846e4-106">安装 Lync Server 时，将获得适用于部署中所有运行 Lync Phone Edition 的设备的 Lync 手机版设置的集合。</span><span class="sxs-lookup"><span data-stu-id="846e4-106">When you install Lync Server, you get a collection of Lync Phone Edition settings that apply to all the devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="846e4-107">您还可以为特定网站创建新的设置集合。</span><span class="sxs-lookup"><span data-stu-id="846e4-107">You can also create new collections of settings for a specific site.</span></span> <span data-ttu-id="846e4-108">网站设置优先于全局设置。</span><span class="sxs-lookup"><span data-stu-id="846e4-108">Site settings take precedence over global settings.</span></span> <span data-ttu-id="846e4-109">每个设置集合均包括名称、范围（全局或网站）、SIP 安全设置、日志记录级别、语音服务质量（QoS）级别、电话锁定设置和电话锁定详细信息，即解锁个人标识的最小长度电话锁定自身之前的数字（PIN）和时间。</span><span class="sxs-lookup"><span data-stu-id="846e4-109">Each collection of settings consists of a name, the scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, the minimum length of the unlock personal identification number (PIN) and time before the phone locks itself.</span></span>

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a><span data-ttu-id="846e4-110">查看有关运行 Lync Phone Edition 的设备的配置信息</span><span class="sxs-lookup"><span data-stu-id="846e4-110">To view configuration information about devices running Lync Phone Edition</span></span>

1.  <span data-ttu-id="846e4-111">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="846e4-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="846e4-112">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="846e4-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="846e4-113">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="846e4-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="846e4-114">在左侧导航栏中，单击 "**客户端**"，然后单击 "**设备配置**" 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="846e4-114">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="846e4-115">在 "**设备配置**" 页面上，单击要查看其相关信息的设置的集合。</span><span class="sxs-lookup"><span data-stu-id="846e4-115">On the **Device Configuration** page, click the collection of settings you want to view information about.</span></span> <span data-ttu-id="846e4-116">主页面上列出了名称、范围、SIP 安全设置、语音质量级别和电话锁定设置。</span><span class="sxs-lookup"><span data-stu-id="846e4-116">The name, scope, SIP security setting, voice quality level, and phone lock setting are listed on the main page.</span></span> <span data-ttu-id="846e4-117">若要查看日志记录级别和电话锁定的详细信息，请单击 "**编辑**" 菜单，然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="846e4-117">To view the logging level and phone lock details, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="846e4-118">使用 Windows PowerShell Cmdlet 查看 Lync 手机版配置信息</span><span class="sxs-lookup"><span data-stu-id="846e4-118">Viewing Lync Phone Edition Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="846e4-119">你可以使用 Lync Server 命令行管理程序和**CsUCPhoneConfiguration** Cmdlet 查看 Lync 手机版配置设置。</span><span class="sxs-lookup"><span data-stu-id="846e4-119">You can view Lync Phone Edition configuration settings by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="846e4-120">你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="846e4-120">You can run this cmdlet can from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="846e4-121">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="846e4-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a><span data-ttu-id="846e4-122">查看 Lync Phone Edition 配置信息</span><span class="sxs-lookup"><span data-stu-id="846e4-122">To view Lync Phone Edition configuration information</span></span>

  - <span data-ttu-id="846e4-123">若要查看有关所有 Lync Phone Edition 配置设置的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="846e4-123">To view information about all your Lync Phone Edition configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsUCPhoneConfiguration
    
    <span data-ttu-id="846e4-124">该命令将返回类似于以下内容的信息：</span><span class="sxs-lookup"><span data-stu-id="846e4-124">The command returns information similar to the following:</span></span>
    
        Identity             : Global
        CalendarPollInterval : 00:03:00
        EnforcePhoneLock     : True
        PhoneLockTimeout     : 00:10:00
        MinPhonePinLength    : 6
        SIPSecurityMode      : High
        VoiceDiffServTag     : 40
        Voice8021p           : 0
        LoggingLevel         : Off

</div>

<span data-ttu-id="846e4-125">有关详细信息，请参阅[CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="846e4-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="846e4-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="846e4-126">See Also</span></span>


[<span data-ttu-id="846e4-127">在 Lync Server 2013 中创建或修改 Lync Phone Edition 配置设置的集合</span><span class="sxs-lookup"><span data-stu-id="846e4-127">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="846e4-128">删除 Lync Server 2013 中的现有 Lync Phone Edition 配置设置集合</span><span class="sxs-lookup"><span data-stu-id="846e4-128">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="846e4-129">在 Lync Server 2013 中配置 Lync Phone Edition 的安全设置</span><span class="sxs-lookup"><span data-stu-id="846e4-129">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="846e4-130">在 Lync Server 2013 中强制执行电话锁定</span><span class="sxs-lookup"><span data-stu-id="846e4-130">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

