---
title: Lync Server 2013：验证地址
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate addresses
ms:assetid: aae557c9-e6f5-4d23-8af1-1d4cd7968c54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412808(v=OCS.15)
ms:contentKeyID: 48185108
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bf8ebf2dd3da00adbd4719dd749c59eeeee82b0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508619"
---
# <a name="validate-addresses-in-lync-server-2013"></a>在 Lync Server 2013 中验证地址

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-17_

在发布位置数据库之前，必须根据您的 SIP 中继或公用电话交换网 (PSTN) E9-1-1 服务提供商维护的主街道地址指南 (MSAG) 验证新位置。

有关 SIP 中继 E9-1-1 服务提供商的详细信息，请参阅 [为 Lync Server 2013 选择 E9-1-1 服务提供商](lync-server-2013-choosing-an-e9-1-1-service-provider.md)。

有关验证地址的详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：

  - **CsLisServiceProvider**

  - **CsLisServiceProvider**

  - **CsLisServiceProvider**

  - **CsLisCivicAddress**

  - **Test-CsLisCivicAddress**

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a>验证位于位置数据库中的地址

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  运行以下 cmdlet 以配置紧急服务提供程序连接。
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  运行以下 cmdlet 以验证位置数据库中的地址。
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    您还可以使用 **CsLisCivicAddress** cmdlet 来验证各个地址。

</div>

</div>

<span> </span>

</div>

</div>

</div>

