---
title: Lync Server 2013：配置 SNMP 应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an SNMP application
ms:assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412972(v=OCS.15)
ms:contentKeyID: 48185346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 252b6ec99d19b88259aacc2fc5681b585ae1bef2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-an-snmp-application-in-lync-server-2013"></a>在 Lync Server 2013 中配置 SNMP 应用程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-03_

Lync Server 2013 包含一个标准 web 服务接口，可用于将 Location 信息服务连接到与具有端口和交换机信息的 MAC 地址的简单网络管理协议（SNMP）应用程序。

如果安装了 SNMP 应用程序，并且 Location 信息服务未能在 location 数据库中找到匹配项，则位置信息服务将使用客户端提供的 MAC 地址自动查询应用程序。 然后，位置信息服务使用 SNMP 应用程序返回的端口和交换机信息再次查询位置数据库。

有关详细信息，请参阅[CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)。

<div>


> [!NOTE]  
> MAC 地址在运行 Windows 8 的计算机上不可用。



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a>配置 SNMP 应用程序 URL

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  运行以下 cmdlet 为 SNMP 应用程序配置 URL。
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

