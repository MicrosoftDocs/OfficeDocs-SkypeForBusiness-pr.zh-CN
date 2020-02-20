---
title: Lync Server 2013：启动服务器上的服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start services on servers
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48185912
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ac91d76cd060adfc9a20ae74da694c9a2cc608a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="start-services-on-servers-for-lync-server-2013"></a>为 Lync Server 2013 启动服务器上的服务

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-09-03_

要成功完成此过程，应以 RTCUniversalServerAdmins 组成员或委派了相应权限的用户身份登录。 有关委派权限的详细信息，请参阅[在 Lync Server 2013 中委派安装权限](lync-server-2013-delegate-setup-permissions.md)主题。

在服务器上安装本地配置存储后，安装 Lync Server 2013 组件，并在前端服务器或前端服务器上配置证书，必须在服务器上启动 Lync Server 2013 服务。 使用以下过程可在部署中的每台前端服务器上启动服务。

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a>启动 Standard Edition Server 或前端服务器上的服务

1.  在 Lync Server 部署向导中，在 " **Lync server 2013** " 页上，单击 "**步骤4：启动服务**" 旁边的 "**运行**"。

2.  在 "**启动服务**" 页上，单击 "**下一步**" 以启动服务器上的 Lync Server 服务。

3.  在“正在执行命令”**** 页上，成功启动所有服务后，单击“完成”****。
    
    <div>
    

    > [!IMPORTANT]  
    > 用于启动服务器上的服务的命令是报告实际上已启动服务的最佳方法。 该命令可能无法反映服务的实际状态。 建议使用紧随“启动服务”<STRONG></STRONG>之后的步骤“服务状态(可选)”<STRONG></STRONG>来打开 Microsoft 管理控制台 (MMC) 并确认服务已成功启动。 如果任何 Lync Server 服务尚未启动，则可以在 MMC 中右键单击该服务，然后单击 "<STRONG>启动</STRONG>"。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

