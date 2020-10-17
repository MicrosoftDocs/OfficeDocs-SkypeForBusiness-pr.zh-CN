---
title: Lync Server 2013：启用或禁用会议设备
description: Lync Server 2013：启用或禁用会议设备。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a conferencing device
ms:assetid: d5140e38-d015-4706-9bde-cf2fa748c36b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994070(v=OCS.15)
ms:contentKeyID: 51803981
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 761bc19536c889cced68ff586753f6800df0da59
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558078"
---
# <a name="enable-or-disable-a-conferencing-device-in-lync-server-2013"></a><span data-ttu-id="6d194-103">在 Lync Server 2013 中启用或禁用会议设备</span><span class="sxs-lookup"><span data-stu-id="6d194-103">Enable or disable a conferencing device in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d194-104">_**上次修改的主题：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="6d194-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="6d194-105">使用 **disable-csmeetingroom** Cmdlet 和 **disable-disable-csmeetingroom** cmdlet 启用和禁用会议设备。</span><span class="sxs-lookup"><span data-stu-id="6d194-105">Enable and disable a conferencing device by using the **Enable-CsMeetingRoom** cmdlet and the **Disable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="6d194-106">这些 cmdlet 可从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="6d194-106">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6d194-107">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。</span><span class="sxs-lookup"><span data-stu-id="6d194-107">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="enabling-a-conferencing-device"></a><span data-ttu-id="6d194-108">启用会议设备</span><span class="sxs-lookup"><span data-stu-id="6d194-108">Enabling a Conferencing Device</span></span>

  - <span data-ttu-id="6d194-109">若要启用会议设备，请使用 **disable-csmeetingroom** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6d194-109">To enable a conferencing device, use the **Enable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="6d194-110">启用会议设备时，必须包括会议设备标识、b) 的注册器池（将在其中托管聊天室帐户）的) ，以及 c) 要分配给该帐户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="6d194-110">When enabling a conferencing device, you must include a) the conferencing device identity, b) the Registrar pool where the room account will be homed, and c) the SIP address to be assigned to that account.</span></span>
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="disabling-a-conferencing-device"></a><span data-ttu-id="6d194-111">禁用会议设备</span><span class="sxs-lookup"><span data-stu-id="6d194-111">Disabling a Conferencing Device</span></span>

  - <span data-ttu-id="6d194-112">若要禁用会议设备，请使用 **disable-csmeetingroom** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6d194-112">To disable a conferencing device, use the **Disable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="6d194-113">请确保指定要禁用的会议设备的标识：</span><span class="sxs-lookup"><span data-stu-id="6d194-113">Make sure that you specify the identity of the conferencing device to be disabled:</span></span>
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<span data-ttu-id="6d194-114">有关详细信息，请参阅 [Enable-disable-csmeetingroom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) Cmdlet 和 [Disable-csmeetingroom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="6d194-114">For details, see the Help topics for the [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) cmdlet and the [Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

