---
title: Lync Server 2013：还原企业版成员服务器
description: Lync Server 2013：还原企业版成员服务器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition member server
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202191(v=OCS.15)
ms:contentKeyID: 51541523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f9838f030205d92988e185798d982f835122c9f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576048"
---
# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a>在 Lync Server 2013 中还原企业版成员服务器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-18_

如果运行以下服务器角色之一的服务器出现故障，请按照本主题中的过程还原服务器。 如果多个服务器出现故障，请针对每个服务器单独执行该过程。

  - Front End Server － 前端服务器

  - 中介服务器

  - 控制器

  - 持久聊天服务器

  - 边缘服务器

<div>


> [!TIP]  
> 我们建议您先获取系统的图像副本，然后再开始还原。 您可以将此图像用作回滚点，以防还原过程中出现问题。 您可能需要在安装操作系统和 SQL Server 后拍摄图像副本，并还原或重新注册证书。



</div>

<div>

## <a name="to-restore-a-member-server"></a>还原成员服务器

1.  从具有相同完全限定的域名 (FQDN) 为故障服务器的干净或新服务器开始，安装操作系统，然后还原或重新注册证书。
    
    <div>
    

    > [!NOTE]  
    > 按照您组织的服务器部署过程来执行该步骤。

    
    </div>

2.  从作为 RTCUniversalServerAdmins 组成员的用户帐户，登录到要还原的服务器。

3.  浏览到 Lync Server 安装文件夹或媒体，然后启动位于 \\ setup amd64Setup.exe 的 Lync Server 部署向导 \\ \\ 。

4.  按照部署向导的提示执行以下操作：
    
    1.  运行“步骤 1: 安装本地配置存储”**** 以安装本地配置文件。
    
    2.  运行 **步骤2：安装或删除 Lync Server 组件** 以安装 lync server 服务器角色。
    
    3.  运行“步骤 3: 请求、安装或分配证书”**** 以分配证书。
    
    4.  运行“步骤 4: 启动服务”**** 以在服务器上启动服务。
    
    有关运行部署向导的详细信息，请参阅部署文档以了解要还原的服务器角色。

</div>

</div>

<span> </span>

</div>

</div>

</div>

