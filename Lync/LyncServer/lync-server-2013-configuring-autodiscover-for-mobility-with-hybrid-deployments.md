---
title: 使用混合部署配置移动性的自动发现
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Autodiscover for mobility with hybrid deployments
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215885(v=OCS.15)
ms:contentKeyID: 48706012
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1865cab188bace472996db6207de62ce8498976
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-mobility-with-hybrid-deployments"></a>在 Lync Server 2013 中使用混合部署配置移动性的自动发现

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-06-18_

混合部署是使用 Microsoft Lync Online 云服务和本地部署的配置。 在此类型的配置中, 自动发现服务必须能够找到用户实际所在的位置。 也就是说, "自动发现" 帮助查找用户帐户和托管用户帐户的服务器所在的位置, 无论该帐户是在本地部署还是在 Lync Online 部署中。

例如, 如果用户的帐户托管在 Lync Online 中的服务器上, 则在称为 "*发现*" 的过程中, 尝试查找用户的操作将如下所示:

  - 用户启动到本地部署的连接尝试**contoso.com**。

  - 该尝试将发送到 lyncdiscover.contoso.com, 它是与自动发现服务关联的 DNS 名称。

  - 自动发现指在 contoso.com 本地部署中假定的注册机构池, 并提供有关用户在 Lync Online 中托管的实际主服务器的信息。 然后, 自动发现将向用户发送**lync.com**联机自动发现服务的引用。

  - 用户启动到 lync.com online 自动发现服务的连接尝试, 并且能够找到用户的帐户和用户的主服务器。

若要使移动客户端能够发现用户主服务器所在的部署, 必须使用新的统一资源定位器 (URL) 配置自动发现服务。 执行以下操作以配置自动发现服务。

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>配置混合部署的自动发现

1.  使用 CsHostingProvider 检索属性 ProxyFQDN 的值。

2.  从 Lync Server 命令行管理程序中, 键入
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    其中\[标识\]替换为共享 SIP 地址空间的域名。

</div>

<div>

## <a name="see-also"></a>另请参阅


[CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))  
[Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

