---
title: Lync Server 2013：删除与设备不关联的设备更新文件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Device Update files not associated with a device
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994084(v=OCS.15)
ms:contentKeyID: 51803996
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1376e82ac29efbe2fcbf996445a75fc3bea1492d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a><span data-ttu-id="a5cc6-102">在 Lync Server 2013 中删除与设备不关联的设备更新文件</span><span class="sxs-lookup"><span data-stu-id="a5cc6-102">Remove Device Update files not associated with a device in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5cc6-103">_**上次修改的主题：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="a5cc6-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="a5cc6-104">每次将新设备更新上载到系统后，都会创建一个相应的设备更新规则。</span><span class="sxs-lookup"><span data-stu-id="a5cc6-104">Each time new device updates are uploaded to the system, a corresponding device update rule is created.</span></span> <span data-ttu-id="a5cc6-105">默认情况下，这些新的设备更新规则被分配到挂起状态。</span><span class="sxs-lookup"><span data-stu-id="a5cc6-105">By default, these new device update rules are assigned to the Pending state.</span></span> <span data-ttu-id="a5cc6-106">这意味着可以在测试设备上下载和安装这些规则，但不能在生产设备上进行测试，这使您能够在将更新提供给用户之前对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="a5cc6-106">This means that the rules can be downloaded and installed on test devices, but not on production devices, which enables you to test the updates before making them available to users.</span></span> <span data-ttu-id="a5cc6-107">根据这些测试，您可以接受并部署或拒绝并删除更新。</span><span class="sxs-lookup"><span data-stu-id="a5cc6-107">Based on the tests, you either accept and deploy or reject and delete the update.</span></span> <span data-ttu-id="a5cc6-108">当您拒绝更新时，设备更新将与其设备更新规则解除关联。</span><span class="sxs-lookup"><span data-stu-id="a5cc6-108">When you reject an update, the device update is disassociated from its device update rule.</span></span>

<div>


<span data-ttu-id="a5cc6-109">可以使用 Windows PowerShell 和**CsDeviceUpdateFile** cmdlet 删除不再与设备关联的设备更新文件。</span><span class="sxs-lookup"><span data-stu-id="a5cc6-109">Device update files that are no longer associated with a device can be removed by using Windows PowerShell and the **Clear-CsDeviceUpdateFile** cmdlet.</span></span> <span data-ttu-id="a5cc6-110">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="a5cc6-110">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a5cc6-111">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上<A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="a5cc6-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


  - <span data-ttu-id="a5cc6-112">例如，以下命令将删除 Web 服务器 atl-cs-001.litwareinc.com 上不再与设备关联的任何设备更新规则：</span><span class="sxs-lookup"><span data-stu-id="a5cc6-112">For example, the following command removes any device update rules on the Web server atl-cs-001.litwareinc.com that are no longer associated with a device:</span></span>
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

<span data-ttu-id="a5cc6-113">有关详细信息，请参阅[CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="a5cc6-113">For details, see the Help topic for the [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

