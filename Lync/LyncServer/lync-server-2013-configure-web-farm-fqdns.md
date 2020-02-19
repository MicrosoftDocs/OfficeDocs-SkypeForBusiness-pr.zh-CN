---
title: Lync Server 2013：配置 web 场 Fqdn
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web farm FQDNs
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429722(v=OCS.15)
ms:contentKeyID: 48185481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50813855e4181add65ff279933a952116768dcec
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a>为 Lync Server 2013 配置 web 场 Fqdn

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-29_

在拓扑生成器中定义了 Standard Edition server、前端池、控制器或控制器池的配置时，请配置一个外部 web 服务完全限定的域名（FQDN）。 在托管在 Standard Edition server 或前端池中的客户端登录过程中，配置的 web 服务的 Fqdn 是通过带内设置的方式发送的。 如果需要添加或更改外部 web 服务 URL，请使用拓扑生成器配置或重新配置 web 服务配置（使用本主题中的过程）。

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a>配置 Web 服务的外部池 FQDN

1.  启动拓扑生成器：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。

2.  在拓扑生成器中，在 " **Standard Edition 前端**"、" **Enterprise edition 前端**" 和 "**控制器**" 下的控制台树中，右键单击需要编辑的池名称，然后单击 "**编辑属性**"。

3.  在“Web 服务”**** 部分，添加或编辑“外部 Web 服务 FQDN”****。

4.  查看并调整 HTTP 和 HTTPS 的“侦听端口”****。默认值为：
    
      - **侦听端口：** HTTP 8080、HTTPS 4443
    
      - **发布端口：** HTTP 80、HTTPS 443
    
    其中“侦听端口”**** 是外部 Web 服务将配置为通过其接收来自反向代理的请求的端口，而“已发布端口”**** 是由反向代理外部发布的端口且用于在带内设置期间与客户端进行通信。

5.  在完成添加和更新后，单击“确定”**** 继续。

6.  右键单击 " **Lync Server 2013**"，然后单击 "**发布**"。
    
    <div>
    

    > [!IMPORTANT]  
    > 成功完成发布后，可能会显示一个链接，告知您需要执行其他步骤。 如果单击此链接，则会打开受拓扑生成器中所做更改影响的服务器列表，这将要求您在列出的每台服务器上重新运行 Lync Server 部署向导，以更新添加、删除或更改的组件的配置。

    
    </div>

7.  对组织中的每个 Standard Edition 服务器、前端池、控制器或控制器池重复这些步骤。

</div>

</div>

<span> </span>

</div>

</div>

</div>

