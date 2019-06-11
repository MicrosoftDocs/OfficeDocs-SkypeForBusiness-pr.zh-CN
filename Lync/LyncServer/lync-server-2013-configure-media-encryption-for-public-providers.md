---
title: Lync Server 2013：配置公共提供商的媒体加密
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media encryption for public providers
ms:assetid: a95814cf-c5a9-4652-8ffc-c469a2653153
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205149(v=OCS.15)
ms:contentKeyID: 48185036
ms.date: 12/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1496bda01456593066efd212241e3d930f1e2cc6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a>在 Lync Server 2013 中配置公共提供商的媒体加密

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-12-12_

如果你使用 Windows Live Messenger 实现音频/视频 (A/V) 联合, 则需要修改两个参数: Lync Server 加密级别和 EnablePublicCloudAccess 策略。 默认情况下, 加密级别设置为 "必需"。 必须将此设置更改为 "支持"。 如果 EnablePublicCloudAccess 策略设置为 false, 则需要将其设置为**True**。 你可以从 Lync Server 命令行管理程序中执行此操作。

<div>

## <a name="configure-federation-for-windows-live"></a>为 Windows Live 配置联合

1.  在前端服务器上启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management Shell**"。

2.  在命令提示符处, 键入以下命令:
    
       ```
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > 这是必需的步骤, 因为 Windows Live Messenger 不支持音频/视频加密。 该命令将你的全局策略设置为支持加密设置, 而不是需要加密音频/视频数据。 支持加密的客户仍将使用加密, 如 Lync 2013。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

