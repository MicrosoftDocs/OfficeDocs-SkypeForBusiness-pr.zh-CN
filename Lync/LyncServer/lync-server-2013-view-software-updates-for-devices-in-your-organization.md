---
title: Lync Server 2013：查看组织中设备的软件更新
description: Lync Server 2013：查看组织中设备的软件更新。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 833ab25315847b760271c63bbfca3ba8357e41c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558828"
---
# <a name="view-software-updates-for-devices-in-lync-server-2013"></a><span data-ttu-id="5db00-103">在 Lync Server 2013 中查看设备的软件更新</span><span class="sxs-lookup"><span data-stu-id="5db00-103">View software updates for devices in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5db00-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5db00-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5db00-105">使用 Lync Server 2013，可以使用设备更新 Web 服务查看和管理组织设备的软件更新。</span><span class="sxs-lookup"><span data-stu-id="5db00-105">With Lync Server 2013, you use Device Update Web service to view and manage software updates for your organization’s devices.</span></span> <span data-ttu-id="5db00-106">来自 Microsoft 支持网站的 .cab (cabinet) 文件中提供了这些更新 [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091) 。</span><span class="sxs-lookup"><span data-stu-id="5db00-106">These updates are available in .cab (cabinet) files from the Microsoft Support website at [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091).</span></span> <span data-ttu-id="5db00-107">下载 .cab 文件后，运行 **CSDeviceUpdate** cmdlet 将设备更新规则从 .cab 文件中导入。</span><span class="sxs-lookup"><span data-stu-id="5db00-107">After you download the .cab file, run the **Import-CSDeviceUpdate** cmdlet to import the device update rules from the .cab file.</span></span> <span data-ttu-id="5db00-108">有关 **CSDeviceUpdate** cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档中的 [import-CSDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) 。</span><span class="sxs-lookup"><span data-stu-id="5db00-108">For details about the **Import-CSDeviceUpdate** cmdlet, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="5db00-109">将新的更新部署到组织之前，请验证其在测试设备上是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="5db00-109">Before deploying a new update to your organization, verify that it functions correctly on a test device.</span></span>



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a><span data-ttu-id="5db00-110">查看 UC 设备的软件更新</span><span class="sxs-lookup"><span data-stu-id="5db00-110">To view software updates for UC devices</span></span>

1.  <span data-ttu-id="5db00-111">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="5db00-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5db00-112">在处的 Microsoft 支持网站中 [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091) ，将 .cab 文件下载到 Lync Server 2013 计算机上的某个位置 (例如，C： \\ Updates \\UCUpdates.cab) 。</span><span class="sxs-lookup"><span data-stu-id="5db00-112">From the Microsoft Support website at [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091), download the .cab file to a location on a Lync Server 2013 computer (for example, C:\\Updates\\UCUpdates.cab).</span></span>

3.  <span data-ttu-id="5db00-113">\\通过运行以下 cmdlet 之一，从 C： UpdatesUCUpdates.cab 文件中导入设备更新规则 \\ ：</span><span class="sxs-lookup"><span data-stu-id="5db00-113">Import the device update rules from the C:\\Updates\\UCUpdates.cab file by running one of the following cmdlets:</span></span>
    
      - <span data-ttu-id="5db00-114">如果 .cab 文件位于运行要更新的服务 (service:Redmond-websvc-2) 的计算机上，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="5db00-114">If the .cab file is located on the same computer as the one running the service to be updated (service:Redmond-websvc-2), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - <span data-ttu-id="5db00-115">如果 .cab 文件不在运行要更新的服务 (service:Redmond-websvc-3) 的计算机上，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="5db00-115">If the .cab file is located on a different computer than the one running the service to be updated (service:Redmond-websvc-3), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  <span data-ttu-id="5db00-116">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="5db00-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5db00-117">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="5db00-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

5.  <span data-ttu-id="5db00-118">在左侧导航栏中，单击 **“客户端”**，然后单击 **“设备更新”**。</span><span class="sxs-lookup"><span data-stu-id="5db00-118">In the left navigation bar, click **Clients**, and then click **Device Update**.</span></span>

6.  <span data-ttu-id="5db00-119">在 **“设备更新”** 页上，单击列表中的更新，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="5db00-119">On the **Device Update** page, click an update in the list, and then do one of the following:</span></span>
    
      - <span data-ttu-id="5db00-p103">**取消待处理的更新。** 要阻止将所选更新部署到组织的设备，请单击 **“操作”** 菜单，然后单击 **“取消待处理的更新”**。</span><span class="sxs-lookup"><span data-stu-id="5db00-p103">**Cancel a pending update.** To prevent the selected update from being deployed to your organization’s devices, click the **Action** menu, and then click **Cancel pending updates**.</span></span>
    
      - <span data-ttu-id="5db00-p104">**批准更新。** 要允许将所选更新部署到组织的设备，请单击 **“操作”** 菜单，然后单击 **“批准”**。</span><span class="sxs-lookup"><span data-stu-id="5db00-p104">**Approve an update.** To allow the selected update to be deployed to your organization’s devices, click the **Action** menu, and then click **Approve**.</span></span>
    
      - <span data-ttu-id="5db00-p105">**还原更新。** 要允许将先前批准的更新部署到组织的设备，请单击 **“操作”** 菜单，然后单击 **“还原”**。</span><span class="sxs-lookup"><span data-stu-id="5db00-p105">**Restore an update.** To allow a previously approved update to be deployed to your organization’s devices, click the **Action** menu, and then click **Restore**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5db00-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5db00-126">See Also</span></span>


[<span data-ttu-id="5db00-127">在 Lync Server 2013 中管理设备、电话和客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="5db00-127">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

