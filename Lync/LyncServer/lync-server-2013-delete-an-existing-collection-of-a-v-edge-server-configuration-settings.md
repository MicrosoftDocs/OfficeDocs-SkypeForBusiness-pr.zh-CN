---
title: 删除 A/V 边缘服务器配置设置的现有集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of A/V Edge Server configuration settings
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49733673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80a90e58c1dee8aacae052f916c6fdf6e260b7ba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514689"
---
# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中删除 A/V 边缘服务器配置设置的现有集合

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

A/V 边缘服务为您的内部用户（已登录到您的组织网络的用户）提供一种与外部用户（未登录到您的组织网络的用户）共享音频和视频的方法。A/V 边缘服务主要通过使用 A/V 边缘配置设置进行管理，即可在站点范围或服务范围进行配置（也就是，可以针对个别 A/V 边缘服务器进行配置）的设置。

当您安装 Lync Server 时，将为您创建 A/V 边缘配置设置的全局集合。 无法删除此全局集合。 但是，可以使用 Windows PowerShell 和 Remove-CsAVEdgeConfiguration cmdlet "重置" 全局集合;这只是意味着全局集合中的所有属性值都将重置为其默认值。 例如，如果您将 MaxTokenLifetime 属性设置为 16 小时，则该属性将重置为其 8 小时的默认值。

但是，可使用 Remove-CsAVEdgeConfiguration cmdlet 删除在站点作用域或服务作用域创建的自定义设置集合。如果您删除站点设置，则相应站点内的 A/V 边缘服务器将由全局设置进行管理。如果您删除服务作用域设置，则相应服务器之后将由其站点设置（如果存在）或由全局设置进行管理（如果没有可用的站点设置）。

有关详细信息，请参阅 [CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15)) cmdlet 的帮助主题。

<div>

## <a name="to-reset-the-global-collection"></a>重置全局集合

  - 以下命令重置 A/V 边缘配置设置的全局集合：
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a>从网站范围中移除集合

  - 此命令删除应用于 Redmond 站点的 A/V 边缘配置设置：
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a>从服务范围中移除集合

  - 此命令删除应用于 A/V 边缘服务器 atl-edge-001.litwareinc.com 的设置：
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中返回 A/V 边缘服务器配置信息](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[在 Lync Server 2013 中创建或修改 A/V 边缘服务器配置设置的集合](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[Lync Server 2013 中的音频/视频 (A/V) 边缘服务器](lync-server-2013-audio-video-a-v-edge-servers.md)  
[CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

