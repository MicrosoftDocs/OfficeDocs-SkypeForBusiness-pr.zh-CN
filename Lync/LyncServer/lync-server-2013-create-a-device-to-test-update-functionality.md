---
title: Lync Server 2013：创建设备以测试更新功能
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
ms.openlocfilehash: 227ca68433cfcc41f966e220ffc826357b50d54b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a><span data-ttu-id="2c7d6-102">在 Lync Server 2013 中创建用于测试更新功能的设备</span><span class="sxs-lookup"><span data-stu-id="2c7d6-102">Create a device to test update functionality in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c7d6-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="2c7d6-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="2c7d6-104">可将测试设备添加到“测试设备”\*\*\*\* 页，然后使用此设备验证新更新的功能，之后再将更新部署到生产设备。</span><span class="sxs-lookup"><span data-stu-id="2c7d6-104">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="2c7d6-105">您可以在全局范围内（在整个 Lync Server 环境中）或在单个站点中测试设备。</span><span class="sxs-lookup"><span data-stu-id="2c7d6-105">You can test a device globally (throughout your entire Lync Server environment) or within a single site.</span></span> <span data-ttu-id="2c7d6-106">可通过测试设备的媒体访问控制 (MAC) 地址或序列号标识测试设备。</span><span class="sxs-lookup"><span data-stu-id="2c7d6-106">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="2c7d6-107">添加设备时，它将显示在 Lync Server 控制面板的 "**测试设备**" 页上的列表中。</span><span class="sxs-lookup"><span data-stu-id="2c7d6-107">When you add a device, it appears in the list on the **Test Device** page of the Lync Server Control Panel.</span></span>

<div>

## <a name="to-add-a-test-device"></a><span data-ttu-id="2c7d6-108">添加测试设备</span><span class="sxs-lookup"><span data-stu-id="2c7d6-108">To add a test device</span></span>

1.  <span data-ttu-id="2c7d6-109">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="2c7d6-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2c7d6-110">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="2c7d6-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="2c7d6-111">在左侧导航栏中，单击“客户端”\*\*\*\*，然后单击“测试设备”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c7d6-111">In the left navigation bar, click **Clients**, and then click **Test Device**.</span></span>

3.  <span data-ttu-id="2c7d6-112">单击“新建”\*\*\*\*，然后单击“全局测试设备”\*\*\*\* 或“站点测试设备”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c7d6-112">Click **New**, and then click either **Global test device** or **Site test device**.</span></span>

4.  <span data-ttu-id="2c7d6-113">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="2c7d6-113">Do one of the following:</span></span>
    
      - <span data-ttu-id="2c7d6-114">如果单击了“全局测试设备”\*\*\*\*，则跳到下一步。</span><span class="sxs-lookup"><span data-stu-id="2c7d6-114">If you clicked **Global test device**, skip to the next step.</span></span>
    
      - <span data-ttu-id="2c7d6-115">如果单击了“站点测试设备”\*\*\*\*，则从可用站点列表中选择一个站点，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c7d6-115">If you clicked **Site test device**, select a site from the list of available sites, and then click **OK**.</span></span>

5.  <span data-ttu-id="2c7d6-116">在“新建测试设备”\*\*\*\* 上的“设备名称”\*\*\*\* 中，键入设备的名称。</span><span class="sxs-lookup"><span data-stu-id="2c7d6-116">In **New Test Device**, type a name for the device in **Device name**.</span></span>

6.  <span data-ttu-id="2c7d6-117">在“标识符类型”\*\*\*\* 下，单击“MAC 地址”\*\*\*\* 或“序列号”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c7d6-117">Under **Identifier type**, click either **MAC address** or **Serial number**.</span></span>

7.  <span data-ttu-id="2c7d6-118">在“唯一标识符”\*\*\*\* 框中，键入设备的 MAC 地址或序列号。</span><span class="sxs-lookup"><span data-stu-id="2c7d6-118">In the **Unique identifier** box, type the MAC address or serial number of the device.</span></span>

8.  <span data-ttu-id="2c7d6-119">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c7d6-119">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2c7d6-120">使用 Windows PowerShell Cmdlet 创建测试设备</span><span class="sxs-lookup"><span data-stu-id="2c7d6-120">Creating Test Devices by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2c7d6-121">可以使用 Windows PowerShell 和 CsTestDevice cmdlet 创建测试设备。</span><span class="sxs-lookup"><span data-stu-id="2c7d6-121">Test devices can be created by using Windows PowerShell and the New-CsTestDevice cmdlet.</span></span> <span data-ttu-id="2c7d6-122">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="2c7d6-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2c7d6-123">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="2c7d6-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="2c7d6-124">使用此 cmdlet 创建测试设备时，必须执行以下两个操作：</span><span class="sxs-lookup"><span data-stu-id="2c7d6-124">When creating test devices using this cmdlet, you must do two things:</span></span>

  - <span data-ttu-id="2c7d6-125">指定 MACAddress 或 SerialNumber 为 IdentifierType。</span><span class="sxs-lookup"><span data-stu-id="2c7d6-125">Specify either MACAddress or SerialNumber as the IdentifierType.</span></span>

  - <span data-ttu-id="2c7d6-p104">指定设备标识时包括作用域。要在全局作用域创建新设备，请使用类似如下的语法：</span><span class="sxs-lookup"><span data-stu-id="2c7d6-p104">Include the scope when specifying the device Identity. To create a new device at the global scope use syntax similar to this:</span></span>
    
        -Identity "global/WindowsPhone"
    
    <span data-ttu-id="2c7d6-128">要在站点作用域创建测试设备，请使用类似如下的语法：</span><span class="sxs-lookup"><span data-stu-id="2c7d6-128">To create a test device at the site scope use syntax similar to this:</span></span>
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a><span data-ttu-id="2c7d6-129">使用 MAC 地址创建测试设备</span><span class="sxs-lookup"><span data-stu-id="2c7d6-129">To create a test device by using the MAC address</span></span>

  - <span data-ttu-id="2c7d6-130">以下命令在全局作用域创建测试设备，并使用 MAC 地址作为 IdentifierType：</span><span class="sxs-lookup"><span data-stu-id="2c7d6-130">This command creates a test device at the global scope, and using the MAC address as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a><span data-ttu-id="2c7d6-131">使用序列号创建测试设备</span><span class="sxs-lookup"><span data-stu-id="2c7d6-131">To create a test device by using the serial number</span></span>

  - <span data-ttu-id="2c7d6-132">以下命令在站点作用域（对于 Redmond 站点）创建测试设备，并使用序列号作为 IdentifierType：</span><span class="sxs-lookup"><span data-stu-id="2c7d6-132">This command creates a new test device at the site scope (for the Redmond site) and uses the serial number as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

<span data-ttu-id="2c7d6-133">有关详细信息，请参阅[CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="2c7d6-133">For more information, see the help topic for the [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

