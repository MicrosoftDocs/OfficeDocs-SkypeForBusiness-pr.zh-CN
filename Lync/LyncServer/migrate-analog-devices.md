---
title: 迁移模拟设备
description: 迁移模拟设备。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63f7f92142fb6a3ced37cded1a223038ec1876d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579398"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="3a812-103">迁移模拟设备</span><span class="sxs-lookup"><span data-stu-id="3a812-103">Migrate analog devices</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a812-104">_**上次修改的主题：** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="3a812-104">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="3a812-105">Lync Server 提供对模拟设备的支持。</span><span class="sxs-lookup"><span data-stu-id="3a812-105">Lync Server provides support for analog devices.</span></span> <span data-ttu-id="3a812-106">具体地说，支持的模拟设备是模拟音频电话和模拟传真机。</span><span class="sxs-lookup"><span data-stu-id="3a812-106">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="3a812-107">您可以配置合格的网关，以支持在 Lync Server 环境中使用模拟设备。</span><span class="sxs-lookup"><span data-stu-id="3a812-107">You can configure the qualified gateways to support the use of analog devices in your Lync Server environment.</span></span> <span data-ttu-id="3a812-108">从 Lync Server 2010 迁移到 Lync Server 2013 之后，您还必须迁移与模拟设备关联的 contact 对象。</span><span class="sxs-lookup"><span data-stu-id="3a812-108">After you migrate from Lync Server 2010 to Lync Server 2013, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="3a812-109">使用 Lync Server 命令行管理程序先检索与 Lync Server 2010 模拟设备关联的所有 contact 对象，然后将这些对象移至 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="3a812-109">Use Lync Server Management Shell to first retrieve all contact objects associated with the Lync Server 2010 analog devices, and then move those objects to the Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-analog-devices"></a><span data-ttu-id="3a812-110">迁移模拟设备</span><span class="sxs-lookup"><span data-stu-id="3a812-110">To migrate analog devices</span></span>

1.  <span data-ttu-id="3a812-111">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3a812-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3a812-112">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="3a812-112">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  <span data-ttu-id="3a812-113">验证是否已将所有 contact 对象移动到 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="3a812-113">Verify that all contact objects have been moved to the Lync Server 2013 pool.</span></span> <span data-ttu-id="3a812-114">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="3a812-114">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  <span data-ttu-id="3a812-115">确认所有联系人对象现在都与 Lync Server 2013 池相关联。</span><span class="sxs-lookup"><span data-stu-id="3a812-115">Verify that all the contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

