---
title: 创建或修改 A/V 边缘服务器配置设置的集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 576fcb445eb37b92356ad9fdf36de716581ca6fa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改 A/V 边缘服务器配置设置的集合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

A/V 边缘服务为您的内部用户（已登录到您的组织网络的用户）提供一种与外部用户（未登录到您的组织网络的用户）共享音频和视频的方法。A/V 边缘服务主要通过使用 A/V 边缘配置设置进行管理，即可在站点范围或服务范围进行配置（也就是，可以针对个别 A/V 边缘服务器进行配置）的设置。

当您安装 Lync Server 时，将为您创建 A/V 边缘配置设置的全局集合。 除了这种情况外，还可以使用 Windows PowerShell 和 CsAVEdgeConfiguration cmdlet 在站点范围或服务范围（即，单个 A/V 边缘服务器）中创建新设置。 如果您创建新的设置，请记住：

  - 在服务范围（也就是，在个别服务器上）配置的设置的优先于一切。

  - 在站点范围配置的设置的优先于在全局范围配置的设置。然而，服务范围设置还将取代站点范围设置。

  - 只有未在个别服务器上配置任何服务设置，并且在服务器所在的站点没有站点设置时，才会使用全局范围的设置。

随后，可使用 Set-CsAVEdgeConfiguration cmdlet 修改任何设置。 有关详细信息，请参阅[CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))和[CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) cmdlet 的帮助主题。

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a>在站点范围创建新的 A/V 边缘配置设置

  - 以下命令为 Redmond 站点创建新的 A/V 边缘配置设置集合：
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a>在网站范围创建自定义 A/V 边缘配置设置

  - 由于未包含其他参数，因此这些新设置将使用 A/V 边缘服务的默认值。或者，您可以添加其他参数和参数值来创建自定义集合。例如，此命令将 MaxTokenLifetime 属性设置为 4 小时（04 小时:00 分钟:00 秒）：
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a>在服务范围创建自定义 A/V 边缘配置设置

  - 此命令将创建一个适用于 A/V 边缘服务器 atl-edge-001.litwareinc.com 的相似集合：
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a>修改现有的 A/V 边缘配置设置

  - 在此示例中，Set-CsAVEdgeConfiguration cmdlet 用于将 Redmond 站点的最大令牌生存期更改为 12 小时：
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中返回 A/V 边缘服务器配置信息](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[在 Lync Server 2013 中删除 A/V 边缘服务器配置设置的现有集合](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Lync Server 2013 中的音频/视频（A/V）边缘服务器](lync-server-2013-audio-video-a-v-edge-servers.md)  
[新 CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))  
[CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

