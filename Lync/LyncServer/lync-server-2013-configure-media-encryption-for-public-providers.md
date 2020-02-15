---
title: Lync Server 2013：为公用提供程序配置媒体加密
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media encryption for public providers
ms:assetid: a95814cf-c5a9-4652-8ffc-c469a2653153
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205149(v=OCS.15)
ms:contentKeyID: 48185036
ms.date: 12/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f1775a845c10797d145c7ee1ad5def3af729f4f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a>在 Lync Server 2013 中为公用提供程序配置媒体加密

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-12-12_

如果要实现与 Windows Live Messenger 的音频/视频（A/V）联合，则需要修改两个参数： Lync Server 加密级别和 EnablePublicCloudAccess 策略。 默认情况下，加密级别为“必需”。 必须将此设置更改为“支持”。 如果 nablePublicCloudAccess 策略设置为 False，则需要将其设置为“True”****。 您可以从 Lync Server 命令行管理程序中执行此操作。

<div>

## <a name="configure-federation-for-windows-live"></a>为 Windows Live 配置联合

1.  在前端服务器上启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management Shell**"。

2.  从命令提示符处，键入以下命令：
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > 上述步骤是必需步骤，因为 Windows Live Messenger 不支持音频/视频加密。 该命令会将您的全局策略设置为支持加密设置，而不会设置为要求音频/视频数据加密。 支持加密的客户端仍将使用加密，如 Lync 2013。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

