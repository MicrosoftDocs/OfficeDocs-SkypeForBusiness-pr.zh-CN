---
title: Lync Server 2013：更改 Web 服务 URL
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94424edc38cf1cc0eacac2638a4ed30a18f06779
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-the-web-services-url-in-lync-server-2013"></a>在 Lync Server 2013 中更改 Web 服务 URL

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2015-11-16_

设置前端池和 Standard Edition Server 时，可以选择配置外部 Web 场完全限定域名 (FQDN) 和关联端口。 如果您在运行 Lync Server 部署向导时未配置此 URL，则需要手动配置这些设置。 通常，管理员不需要修改这些设置，因为这些是建议的默认端口。

<div>


> [!NOTE]  
> 配置 Standard Edition server 时采用了以下屏幕截图，因此禁用了替代 FQDN 选项。 在前端池中配置 Enterprise Edition 服务器时，将启用该选项。



</div>

![编辑 Web 服务池设置](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "编辑 Web 服务池设置")

<div>

## <a name="to-configure-web-services"></a>配置 web 服务

1.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。

2.  启动拓扑生成器：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。

3.  在拓扑生成器中，在 " **Standard Edition 前端服务器**"、" **Enterprise edition 前端池**" 和 "**目录池**" 下的控制台树中，选择池名称。 右键单击该名称，再单击“编辑属性”****，然后单击“Web 服务”****。

4.  添加或编辑“外部 Web 服务 FQDN”****，然后单击“确定”****。
    
    <div>
    

    > [!WARNING]  
    > 如果您有多个前端池或前端服务器，则外部 Web 服务 FQDN 必须是唯一的。 例如，如果将前端服务器的外部 Web 服务 FQDN 定义为<STRONG>pool01.contoso.com</STRONG>，则不能将<STRONG>pool01.contoso.com</STRONG>用于另一个前端池或前端服务器。 如果还部署控制器，则为任何控制器或控制器池定义的外部 Web 服务 FQDN 必须与任何其他控制器或控制器池以及任何前端池或前端服务器都是唯一的。

    
    </div>

5.  验证是否已为环境正确配置侦听端口和已发布端口。

6.  对环境中的所有 Standard Edition Server、前端池和控制器池重复这些步骤。

7.  在控制台树中，单击“Lync Server 2013”****，然后在“操作”**** 窗格中，单击“发布拓扑”****。

配置侦听端口和发布端口时，应了解以下要求：

  - 显示的侦听端口是为每台前端服务器上的 Internet Information Server (IIS) 配置的端口。

  - IIS 的内部侦听端口和外部侦听端口必须不同。外部侦听端口通常是相同的，因为一个代表内部 Web 流量的硬件负载平衡器，一个代表外部 Web 流量的反向代理服务器。

  - 您可以重写前端池、控制器或控制器池上的内部 web 服务，并定义自己的 FQDN。
    
    <div>
    

    > [!WARNING]  
    > 如果决定使用自定义的 FQDN 覆盖内部 web 服务，则每个 FQDN 必须与任何其他前端池、控制器或控制器池都是唯一的。

    
    </div>

  - 必须在反向代理或硬件负载平衡器上将已发布端口配置为侦听端口。

  - 对于前端池（未在示例中显示），内部 SIP 池 FQDN 必须与内部 Web 服务 FQDN 不同，这是因为 Web 流量通过硬件负载平衡器进行传输，而内部 SIP 池流量通过 DNS 负载平衡器进行传输。必须满足此要求。

  - Lync Server Standard Edition 部署不需要或允许覆盖内部 web 服务 FQDN，因为无法对此服务器进行负载平衡。

  - 如果你的环境中具有用于内部 SIP 和 web 流量的硬件负载平衡器，则拓扑生成器无法进行区分。
    
    Web 服务 Fqdn 应易于区分; 而不是另一个。这有助于确保 URL 重定向将客户定向到适当的服务器。 例如，如果您有两个 Fqdn，则可以考虑为一个 meeting.contoso.com 和另一个 conferencing.contoso.com 命名。 如果您的 Fqdn 具有更相似的名称（如 meet1.contoso.com 和 meet2.contoso.com），则可能会遇到重定向问题。

在外围网络中，外部 Web 服务与反向代理结合使用。 它通过使用这些 web 服务向客户端提供对外部的访问权限。 此处配置的 FQDN 会在客户端登录时发送到客户端，并在远程连接时用于建立与反向代理的 HTTPS 连接。 反向代理服务器将外部 Web 服务 FQDN 转发到内部硬件负载平衡器或直接转发到池。 反向代理必须能够将外部 Web 服务 FQDN 解析为内部 Web 服务器的 IP 地址。 外部 Web 服务 FQDN 必须可以在公共 Internet 中进行解析。

如果内部服务器是 Standard Edition server，则内部 FQDN 为 Standard Edition server FQDN。 如果内部服务器是前端池，则 FQDN 是用于平衡内部 Web 场服务器负载的硬件负载平衡器虚拟 IP (VIP)。 在具有多个 Enterprise Edition Server 的前端池中，需要使用硬件负载平衡器。 Standard Edition Server 或单个 Enterprise Edition 前端服务器不需要使用负载平衡器。

</div>

</div>

<span> </span>

</div>

</div>

</div>

