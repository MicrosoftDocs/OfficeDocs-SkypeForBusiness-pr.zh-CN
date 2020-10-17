---
title: Lync Server 2013：创建设备以测试更新功能
description: Lync Server 2013：创建用于测试更新功能的设备。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a device to test update functionality
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48185466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d45d8970dc72abc8ea6095c879272394e34c54d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542168"
---
# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a><span data-ttu-id="22a26-103">在 Lync Server 2013 中创建用于测试更新功能的设备</span><span class="sxs-lookup"><span data-stu-id="22a26-103">Create a device to test update functionality in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22a26-104">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="22a26-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="22a26-105">可将测试设备添加到“测试设备”\*\*\*\* 页，然后使用此设备验证新更新的功能，之后再将更新部署到生产设备。</span><span class="sxs-lookup"><span data-stu-id="22a26-105">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="22a26-106">您可以在整个 Lync Server 环境中全局 () 或在单个站点中测试设备。</span><span class="sxs-lookup"><span data-stu-id="22a26-106">You can test a device globally (throughout your entire Lync Server environment) or within a single site.</span></span> <span data-ttu-id="22a26-107">可通过测试设备的媒体访问控制 (MAC) 地址或序列号标识测试设备。</span><span class="sxs-lookup"><span data-stu-id="22a26-107">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="22a26-108">添加设备时，它将显示在 Lync Server 控制面板的 " **测试设备** " 页上的列表中。</span><span class="sxs-lookup"><span data-stu-id="22a26-108">When you add a device, it appears in the list on the **Test Device** page of the Lync Server Control Panel.</span></span>

<div>

## <a name="to-add-a-test-device"></a><span data-ttu-id="22a26-109">添加测试设备</span><span class="sxs-lookup"><span data-stu-id="22a26-109">To add a test device</span></span>

1.  <span data-ttu-id="22a26-110">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="22a26-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="22a26-111">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="22a26-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="22a26-112">在左侧导航栏中，单击“客户端”\*\*\*\*，然后单击“测试设备”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22a26-112">In the left navigation bar, click **Clients**, and then click **Test Device**.</span></span>

3.  <span data-ttu-id="22a26-113">单击“新建”\*\*\*\*，然后单击“全局测试设备”\*\*\*\* 或“站点测试设备”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22a26-113">Click **New**, and then click either **Global test device** or **Site test device**.</span></span>

4.  <span data-ttu-id="22a26-114">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="22a26-114">Do one of the following:</span></span>
    
      - <span data-ttu-id="22a26-115">如果单击了“全局测试设备”\*\*\*\*，则跳到下一步。</span><span class="sxs-lookup"><span data-stu-id="22a26-115">If you clicked **Global test device**, skip to the next step.</span></span>
    
      - <span data-ttu-id="22a26-116">如果单击了“站点测试设备”\*\*\*\*，则从可用站点列表中选择一个站点，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22a26-116">If you clicked **Site test device**, select a site from the list of available sites, and then click **OK**.</span></span>

5.  <span data-ttu-id="22a26-117">在“新建测试设备”\*\*\*\* 上的“设备名称”\*\*\*\* 中，键入设备的名称。</span><span class="sxs-lookup"><span data-stu-id="22a26-117">In **New Test Device**, type a name for the device in **Device name**.</span></span>

6.  <span data-ttu-id="22a26-118">在“标识符类型”\*\*\*\* 下，单击“MAC 地址”\*\*\*\* 或“序列号”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22a26-118">Under **Identifier type**, click either **MAC address** or **Serial number**.</span></span>

7.  <span data-ttu-id="22a26-119">在“唯一标识符”\*\*\*\* 框中，键入设备的 MAC 地址或序列号。</span><span class="sxs-lookup"><span data-stu-id="22a26-119">In the **Unique identifier** box, type the MAC address or serial number of the device.</span></span>

8.  <span data-ttu-id="22a26-120">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22a26-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="22a26-121">使用 Windows PowerShell Cmdlet 创建测试设备</span><span class="sxs-lookup"><span data-stu-id="22a26-121">Creating Test Devices by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="22a26-122">可以使用 Windows PowerShell 和 New-CsTestDevice cmdlet 创建测试设备。</span><span class="sxs-lookup"><span data-stu-id="22a26-122">Test devices can be created by using Windows PowerShell and the New-CsTestDevice cmdlet.</span></span> <span data-ttu-id="22a26-123">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="22a26-123">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="22a26-124">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="22a26-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="22a26-125">使用此 cmdlet 创建测试设备时，必须执行以下两个操作：</span><span class="sxs-lookup"><span data-stu-id="22a26-125">When creating test devices using this cmdlet, you must do two things:</span></span>

  - <span data-ttu-id="22a26-126">指定 MACAddress 或 SerialNumber 为 IdentifierType。</span><span class="sxs-lookup"><span data-stu-id="22a26-126">Specify either MACAddress or SerialNumber as the IdentifierType.</span></span>

  - <span data-ttu-id="22a26-p104">指定设备标识时包括作用域。要在全局作用域创建新设备，请使用类似如下的语法：</span><span class="sxs-lookup"><span data-stu-id="22a26-p104">Include the scope when specifying the device Identity. To create a new device at the global scope use syntax similar to this:</span></span>
    
        -Identity "global/WindowsPhone"
    
    <span data-ttu-id="22a26-129">要在站点作用域创建测试设备，请使用类似如下的语法：</span><span class="sxs-lookup"><span data-stu-id="22a26-129">To create a test device at the site scope use syntax similar to this:</span></span>
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a><span data-ttu-id="22a26-130">使用 MAC 地址创建测试设备</span><span class="sxs-lookup"><span data-stu-id="22a26-130">To create a test device by using the MAC address</span></span>

  - <span data-ttu-id="22a26-131">以下命令在全局作用域创建测试设备，并使用 MAC 地址作为 IdentifierType：</span><span class="sxs-lookup"><span data-stu-id="22a26-131">This command creates a test device at the global scope, and using the MAC address as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a><span data-ttu-id="22a26-132">使用序列号创建测试设备</span><span class="sxs-lookup"><span data-stu-id="22a26-132">To create a test device by using the serial number</span></span>

  - <span data-ttu-id="22a26-133">以下命令在站点作用域（对于 Redmond 站点）创建测试设备，并使用序列号作为 IdentifierType：</span><span class="sxs-lookup"><span data-stu-id="22a26-133">This command creates a new test device at the site scope (for the Redmond site) and uses the serial number as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

<span data-ttu-id="22a26-134">有关详细信息，请参阅 [CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="22a26-134">For more information, see the help topic for the [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

