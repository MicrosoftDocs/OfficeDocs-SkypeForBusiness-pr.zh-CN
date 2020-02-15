---
title: Lync Server 2013：配置辅助位置信息服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a secondary Location Information service
ms:assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398138(v=OCS.15)
ms:contentKeyID: 48183334
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50d63d8316c9ce18bdf8677686a655046601b326
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a>在 Lync Server 2013 中配置辅助位置信息服务

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-30_

Lync Server 2013 提供了可用于将位置信息服务指向辅助位置源（SLS）数据库的 web 服务接口。 连接到 SLS 数据库的 web 服务接口必须符合 Location Information service WSDL。 如果同时配置了位置数据库和辅助位置数据库，则位置信息服务首先查询位置数据库，如果找不到匹配项，则会将位置请求从客户端发送到 SLS 数据库。 如果该位置存在于 SLS 中，则位置信息服务随后会将该位置发送回客户端。

有关详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：

  - **CsWebServiceConfiguration**

<div>

## <a name="to-configure-secondary-location-database"></a>配置辅助位置数据库

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  运行以下 cmdlet 为辅助位置数据库位置配置 URL。
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

