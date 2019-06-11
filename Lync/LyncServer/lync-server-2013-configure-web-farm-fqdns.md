---
title: Lync Server 2013：配置 Web 场 FQDN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure web farm FQDNs
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429722(v=OCS.15)
ms:contentKeyID: 48185481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 517e00baef63e3597c2f5b2b6621e62efb02ca62
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a>为 Lync Server 2013 配置 Web 场 FQDN

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-03-29_

在拓扑生成器中定义了标准版服务器、前端池、控制器或控制器池的配置时, 请配置外部 web 服务完全限定的域名 (FQDN)。 在托管在标准版服务器或前端池中的客户端登录过程中, 已配置的 web 服务 Fqdn 通过带内预配的方式发送。 如果需要添加或更改外部 web 服务 URL, 请使用拓扑生成器配置或重新配置 web 服务配置, 方法是使用本主题中的过程。

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a>为 web 服务配置外部池 FQDN

1.  启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。

2.  在拓扑生成器中, 在 "**标准版前端**"、"**企业版前端**" 和 "**控制器**" 下的控制台树中, 右键单击需要编辑的池名称, 然后单击 "**编辑属性**"。

3.  在 " **Web 服务**" 部分中, 添加或编辑**外部 Web 服务 FQDN**。

4.  查看和调整 HTTP 和 HTTPS 的**侦听端口**。 默认值将为:
    
      - **侦听端口:** HTTP 8080, HTTPS 4443
    
      - **已发布的端口:** HTTP 80, HTTPS 443
    
    如果**侦听端口**是外部 web 服务将配置为接收来自反向代理的请求的端口, 并且**已发布的端口**是由反向代理在外部发布的端口, 并且将传递给在带内配置期间的客户端。

5.  完成添加和更新后, 单击 **"确定"** 以继续。

6.  右键单击 " **Lync Server 2013**", 然后单击 "**发布**"。
    
    <div>
    

    > [!IMPORTANT]  
    > 发布成功完成后, 可能会显示一个链接, 通知你有需要采取的其他步骤。 链接 (如果单击) 会打开受拓扑生成器中所做更改影响的服务器的列表, 该列表要求你在列出的每台服务器上重新运行 Lync Server 部署向导, 以便更新添加、删除或更改的组件的配置。

    
    </div>

7.  为组织中的每个标准版服务器、前端池、控制器或控制器池重复这些步骤。

</div>

</div>

<span> </span>

</div>

</div>

</div>

