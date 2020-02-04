---
title: Lync Server 2013：将会议设备移动到新的注册池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move a conferencing device to a new Registrar pool
ms:assetid: 26e02ca3-e881-4f90-8bf0-b13649108100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994025(v=OCS.15)
ms:contentKeyID: 51803934
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69afbc1dbb33f43f8ed6a1f056f7d4a610b110c4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-conferencing-device-to-a-new-registrar-pool-in-lync-server-2013"></a>将会议设备移动到 Lync Server 2013 中的新注册机构池

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-20_

使用**CsMeetingRoom** cmdlet 将会议设备从一个注册机构迁移到另一个注册机构。 此 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。

<div>


> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。



</div>

<div>


<div>

## <a name="moving-a-conferencing-device-to-a-new-registrar-pool"></a>将会议设备移动到新的注册池

  - 若要移动会议设备，必须指定要移动的聊天室的标识，然后将目标参数设置为设备将被移动到的注册机构池的完全限定的域名（FQDN）。 例如：
    
        Move-CsMeetingRoom -Target "atl-cs-001.litwareinc.com" -Identity "Room 14"

</div>

有关详细信息，请参阅[CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Move-CsMeetingRoom) Cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

