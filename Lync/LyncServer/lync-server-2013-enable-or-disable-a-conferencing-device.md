---
title: Lync Server 2013：启用或禁用会议设备
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
ms.openlocfilehash: 27a5ed5c138d1389f0a3d4882bcdd437b5e7919e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190675"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-conferencing-device-in-lync-server-2013"></a>在 Lync Server 2013 中启用或禁用会议设备

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-20_

使用**disable-csmeetingroom** Cmdlet 和**disable-disable-csmeetingroom** cmdlet 启用和禁用会议设备。 这些 cmdlet 可从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话中运行。

<div>


> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上<A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。



</div>

<div>


<div>

## <a name="enabling-a-conferencing-device"></a>启用会议设备

  - 若要启用会议设备，请使用**disable-csmeetingroom** cmdlet。 启用会议设备时，必须包括 a）会议设备标识 b）将在其中托管聊天室帐户的注册器池和 c）要分配给该帐户的 SIP 地址。
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="disabling-a-conferencing-device"></a>禁用会议设备

  - 若要禁用会议设备，请使用**disable-csmeetingroom** cmdlet。 请确保指定要禁用的会议设备的标识：
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

</div>

有关详细信息，请参阅[Enable-disable-csmeetingroom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) Cmdlet 和[Disable-csmeetingroom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

