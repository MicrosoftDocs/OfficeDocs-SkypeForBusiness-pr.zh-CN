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
ms.openlocfilehash: 7cc085cd6ac39c4712647795c5baf06eaa68f77a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中删除 A/V 边缘服务器配置设置的现有集合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-11-01_

A/V 边缘服务为内部用户（登录到你的组织网络的用户）提供一种方法，以便与外部用户（未登录到你的组织网络的用户）共享音频和视频。 A/V 边缘服务主要通过使用 A/V 边缘配置设置进行管理，可在网站范围或在服务范围内配置的设置（即，可针对单个 A/V 边缘服务器进行配置）。

安装 Lync Server 时，将为你创建一个/V 边缘配置设置的全局集合。 无法删除此全局集合。 但是，你可以使用 Windows PowerShell 和 CsAVEdgeConfiguration cmdlet 来 "重置" 全局集合;这只意味着全局集合中的所有属性值都将重置为其默认值。 例如，如果您已将 MaxTokenLifetime 属性设置为16小时，则该属性将重置为其默认值8小时。

但是，你可以使用 CsAVEdgeConfiguration cmdlet 删除你在网站范围或服务范围内创建的自定义设置集合。 如果您删除网站设置，则该网站中的 A/V 边缘服务器将由全局设置管理。 如果你删除了服务范围设置，则该服务器将由其网站设置（如果存在）或全局设置管理（如果没有可用的网站设置）。

有关详细信息，请参阅[CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15)) cmdlet 的帮助主题。

<div>

## <a name="to-reset-the-global-collection"></a>重置全局集合

  - 以下命令将重置 A/V 边缘配置设置的全局集合：
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a>从网站范围中删除集合

  - 此命令将删除应用于 Redmond 网站的 A/V 边缘配置设置：
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a>从服务范围中删除集合

  - 此命令将删除应用到 A/V 边缘服务器 atl-edge-001.litwareinc.com 的设置：
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>另请参阅


[返回 Lync Server 2013 中的 A/V 边缘服务器配置信息](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[在 Lync Server 2013 中创建或修改 A/V 边缘服务器配置设置的集合](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[Lync Server 2013 中的音频/视频（A/V）边缘服务器](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

