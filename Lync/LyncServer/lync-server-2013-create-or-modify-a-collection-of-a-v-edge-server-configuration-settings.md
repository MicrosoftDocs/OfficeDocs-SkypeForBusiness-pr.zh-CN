---
title: 创建或修改 A/V 边缘服务器配置设置的集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a4010c209e1231c47c328d616f686f55fc89008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改 A/V 边缘服务器配置设置的集合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

A/V 边缘服务为内部用户 (登录到你的组织网络的用户) 提供一种方法, 以便与外部用户 (未登录到你的组织网络的用户) 共享音频和视频。 A/V 边缘服务主要通过使用 A/V 边缘配置设置进行管理, 可在网站范围或在服务范围内配置的设置 (即, 可针对单个 A/V 边缘服务器进行配置)。

安装 Lync Server 时, 将为你创建一个/V 边缘配置设置的全局集合。 除了这些, 你还可以使用 Windows PowerShell 和 CsAVEdgeConfiguration cmdlet 在网站范围或服务作用域 (即单个 A/V 边缘服务器) 上创建新设置。 如果您创建新设置, 请记住:

  - 在服务作用域 (即在单个服务器上) 中配置的设置优先于所有内容。

  - 在网站范围内配置的设置优先于在全局范围内配置的设置。 但是, 服务范围设置还将取代网站范围的设置。

  - 只有在单个服务器上没有配置任何服务设置且该服务器所在的网站没有网站设置的情况下, 才会使用全局范围内的设置。

然后, 你可以使用 CsAVEdgeConfiguration cmdlet 修改你的任何设置。 有关详细信息, 请参阅[新的-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))和[CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15)) cmdlet 的帮助主题。

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a>在网站范围内创建新的 A/V 边缘配置设置

  - 以下命令为雷德蒙站点的 A/V 边缘配置设置创建新的集合:
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a>在网站范围内创建自定义 A/V 边缘配置设置

  - 由于未包括任何其他参数, 因此这些新设置将使用 A/V 边缘服务的默认值。 或者, 你可以添加其他参数和参数值以创建自定义集合。 例如, 此命令将 MaxTokenLifetime 属性设置为4小时 (04 小时:00 分:00 秒):
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a>在服务范围内创建自定义 A/V 边缘配置设置

  - 此命令将创建一个类似的集合, 该集合应用于 A/V 边缘服务器 atl-edge-001.litwareinc.com:
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a>修改现有的 A/V 边缘配置设置

  - 在此示例中, CsAVEdgeConfiguration cmdlet 用于将雷德蒙站点的最大令牌生命周期更改为12个小时:
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a>另请参阅


[返回 Lync Server 2013 中的 A/V 边缘服务器配置信息](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[在 Lync Server 2013 中删除 A/V 边缘服务器配置设置的现有集合](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Lync Server 2013 中的音频/视频 (A/V) 边缘服务器](lync-server-2013-audio-video-a-v-edge-servers.md)  
[新-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))  
[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

