---
title: Lync Server 2013：导入设备更新规则
description: Lync Server 2013：导入设备更新规则。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import Device Update rules
ms:assetid: 919e9c87-912b-4bc9-92e7-5998fc2e0bf0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994056(v=OCS.15)
ms:contentKeyID: 51803967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a7b936a4b7be96332343e8f96134d5ba1b879be
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547848"
---
# <a name="import-device-update-rules-in-lync-server-2013"></a><span data-ttu-id="c8274-103">在 Lync Server 2013 中导入设备更新规则</span><span class="sxs-lookup"><span data-stu-id="c8274-103">Import Device Update rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8274-104">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c8274-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c8274-105">只能使用 Windows PowerShell 和 **CsDeviceUpdate** cmdlet 导入设备更新规则。</span><span class="sxs-lookup"><span data-stu-id="c8274-105">Device update rules can be imported only by using Windows PowerShell and the **Import-CsDeviceUpdate** cmdlet.</span></span> <span data-ttu-id="c8274-106">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="c8274-106">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8274-107">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。</span><span class="sxs-lookup"><span data-stu-id="c8274-107">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="to-import-device-update-rules-to-a-single-web-server"></a><span data-ttu-id="c8274-108">将设备更新规则导入到单个 web 服务器</span><span class="sxs-lookup"><span data-stu-id="c8274-108">To import device update rules to a single web server</span></span>

  - <span data-ttu-id="c8274-109">以下命令将设备更新规则导入到 Web 服务器 atl-cs-001.litwareinc.com：</span><span class="sxs-lookup"><span data-stu-id="c8274-109">The following command imports device update rules to the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

</div>

<div>

## <a name="to-import-device-update-rules-to-all-your-web-servers"></a><span data-ttu-id="c8274-110">将设备更新规则导入到所有 web 服务器</span><span class="sxs-lookup"><span data-stu-id="c8274-110">To import device update rules to all your web servers</span></span>

  - <span data-ttu-id="c8274-111">在此示例中，将设备更新规则导入到组织中部署的所有 Web 服务器。</span><span class="sxs-lookup"><span data-stu-id="c8274-111">In this example, device update rules are imported to all the Web servers deployed in your organization.</span></span> <span data-ttu-id="c8274-112">若要使此命令正常运行， \\ \\ \\ 必须共享文件夹 atl-fs-001.litwareinc.com 更新，并将其提供给所有 Web 服务器。</span><span class="sxs-lookup"><span data-stu-id="c8274-112">For this command to work, the folder \\\\atl-fs-001.litwareinc.com\\Updates must be shared and available to all the Web servers.</span></span>
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

</div>

<span data-ttu-id="c8274-113">有关详细信息，请参阅 [CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="c8274-113">For details, see the Help topic for the [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c8274-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8274-114">See Also</span></span>


[<span data-ttu-id="c8274-115">在 Lync Server 2013 中查看有关设备更新规则的信息</span><span class="sxs-lookup"><span data-stu-id="c8274-115">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)  
[<span data-ttu-id="c8274-116">在 Lync Server 2013 中审批设备更新规则</span><span class="sxs-lookup"><span data-stu-id="c8274-116">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

