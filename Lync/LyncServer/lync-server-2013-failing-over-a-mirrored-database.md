---
title: Lync Server 2013：对镜像数据库进行故障转移
description: Lync Server 2013：对镜像数据库进行故障转移。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a mirrored database
ms:assetid: 70185476-e3d4-440a-9316-fa24b226343e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204991(v=OCS.15)
ms:contentKeyID: 48184450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc7c401157c79762f674721ca717296c0fe502db
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567688"
---
# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a>在 Lync Server 2013 中对镜像数据库进行故障转移

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-03-14_

如果已将后端数据库配置为使用具有见证的同步镜像，则故障转移是自动的。如果已配置没有见证的同步镜像，则可使用以下过程进行故障转移并返回数据库。即使也配置见证，也可以使用这些过程手动对数据库进行故障转移和故障回复。

<div>

## <a name="to-fail-over-your-back-end-database"></a>故障转移到后端数据库

1.  在故障转移之前，通过键入以下 cmdlet 确定哪个后端数据库是主体，哪个是镜像：
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  如果中央管理存储托管在此池中，请键入以下 cmdlet 以确定哪个是主体，后者是中央管理存储的镜像：
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  对用户数据库执行故障转移：
    
      - 如果主体已出现故障并且您要故障转移到镜像，请键入：
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - 如果镜像已出现故障并且您要故障转移到主体，请键入：
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  如果池承载中央管理服务器，请执行中央管理存储的故障转移。
    
      - 如果主体已出现故障并且您要故障转移到镜像，请键入：
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - 如果镜像已出现故障并且您要故障转移到主体，请键入：
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

