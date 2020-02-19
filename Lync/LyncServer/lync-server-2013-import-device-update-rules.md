---
title: Lync Server 2013：导入设备更新规则
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
ms.openlocfilehash: abcb7b911d4f7cd21fd9fbb3ac232048db8691ba
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42131315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="import-device-update-rules-in-lync-server-2013"></a><span data-ttu-id="a7f83-102">在 Lync Server 2013 中导入设备更新规则</span><span class="sxs-lookup"><span data-stu-id="a7f83-102">Import Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7f83-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="a7f83-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="a7f83-104">只能使用 Windows PowerShell 和**CsDeviceUpdate** cmdlet 导入设备更新规则。</span><span class="sxs-lookup"><span data-stu-id="a7f83-104">Device update rules can be imported only by using Windows PowerShell and the **Import-CsDeviceUpdate** cmdlet.</span></span> <span data-ttu-id="a7f83-105">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="a7f83-105">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a7f83-106">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上<A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。</span><span class="sxs-lookup"><span data-stu-id="a7f83-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="to-import-device-update-rules-to-a-single-web-server"></a><span data-ttu-id="a7f83-107">将设备更新规则导入到单个 web 服务器</span><span class="sxs-lookup"><span data-stu-id="a7f83-107">To import device update rules to a single web server</span></span>

  - <span data-ttu-id="a7f83-108">以下命令将设备更新规则导入到 Web 服务器 atl-cs-001.litwareinc.com：</span><span class="sxs-lookup"><span data-stu-id="a7f83-108">The following command imports device update rules to the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

</div>

<div>

## <a name="to-import-device-update-rules-to-all-your-web-servers"></a><span data-ttu-id="a7f83-109">将设备更新规则导入到所有 web 服务器</span><span class="sxs-lookup"><span data-stu-id="a7f83-109">To import device update rules to all your web servers</span></span>

  - <span data-ttu-id="a7f83-110">在此示例中，将设备更新规则导入到组织中部署的所有 Web 服务器。</span><span class="sxs-lookup"><span data-stu-id="a7f83-110">In this example, device update rules are imported to all the Web servers deployed in your organization.</span></span> <span data-ttu-id="a7f83-111">若要使此命令正常运行， \\ \\必须\\共享文件夹 atl-fs-001.litwareinc.com 更新，并将其提供给所有 Web 服务器。</span><span class="sxs-lookup"><span data-stu-id="a7f83-111">For this command to work, the folder \\\\atl-fs-001.litwareinc.com\\Updates must be shared and available to all the Web servers.</span></span>
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

</div>

<span data-ttu-id="a7f83-112">有关详细信息，请参阅[CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="a7f83-112">For details, see the Help topic for the [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a7f83-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7f83-113">See Also</span></span>


[<span data-ttu-id="a7f83-114">在 Lync Server 2013 中查看有关设备更新规则的信息</span><span class="sxs-lookup"><span data-stu-id="a7f83-114">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)  
[<span data-ttu-id="a7f83-115">在 Lync Server 2013 中审批设备更新规则</span><span class="sxs-lookup"><span data-stu-id="a7f83-115">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

