---
title: 'Lync Server 2013: 更改 Web 服务 URL'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 335c73a56da1d8b9a28e7089a7cc2238724a322b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-the-web-services-url-in-lync-server-2013"></a>在 Lync Server 2013 中更改 Web 服务 URL

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2015-11-16_

设置前端池和标准版服务器时, 可以选择配置外部 Web 场完全限定的域名 (FQDN) 和关联的端口。 如果您运行 Lync Server 部署向导时未配置此 URL, 则需要手动配置这些设置。 管理员通常不需要修改这些设置, 因为它们是推荐的和默认的端口。

<div>


> [!NOTE]  
> 配置标准版服务器时, 将会执行以下屏幕截图, 因此将禁用替代 FQDN 选项。 在前端池中配置企业版服务器时, 将启用该选项。



</div>

![编辑 Web 服务池设置](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "编辑 Web 服务池设置")

<div>

## <a name="to-configure-web-services"></a>配置 web 服务

1.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。

2.  启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。

3.  在拓扑生成器中, 在 "**标准版前端服务器**"、"**企业版前端池**" 和 "**目录池**" 下的控制台树中, 选择 "池名称"。 右键单击该名称, 单击 "**编辑属性**", 然后单击 " **Web 服务**"。

4.  添加或编辑**外部 Web 服务 FQDN**, 然后单击 **"确定"**。
    
    <div>
    

    > [!WARNING]  
    > 如果您有多个前端池或前端服务器, 则外部 Web 服务 FQDN 必须是唯一的。 例如, 如果你将前端服务器的外部 Web 服务 FQDN 定义为<STRONG>pool01.contoso.com</STRONG>, 则不能将<STRONG>Pool01.contoso.com</STRONG>用于其他前端池或前端服务器。 如果你还部署控制器, 则为任何控制器或控制器池定义的外部 Web 服务 FQDN 必须是任何其他 Director 或控制器池以及任何前端池或前端服务器的唯一。

    
    </div>

5.  验证是否为你的环境正确配置了侦听和已发布端口。

6.  对你的环境中的所有标准版服务器、前端池和控制器池重复这些步骤。

7.  在控制台树中, 单击 " **Lync Server 2013**", 然后在 "**操作**" 窗格中, 单击 "**发布拓扑**"。

配置侦听和发布端口时, 应注意以下几点要求:

  - 所示的侦听端口是针对每台前端服务器上的 Internet 信息服务器 (IIS) 配置的端口。

  - 对于 IIS, 内部和外部侦听端口必须不同。 对于外部侦听端口, 这些端口通常是相同的, 因为一个表示内部 web 流量的硬件负载平衡器, 另一个表示用于外部 web 流量的反向代理服务器。

  - 你可以替代前端池、Director 或控制器池上的内部 web 服务, 并定义自己的 FQDN。
    
    <div>
    

    > [!WARNING]  
    > 如果你决定使用自定义的 FQDN 替代内部 web 服务, 则每个 FQDN 都必须与任何其他前端池、Director 或控制器池唯一。

    
    </div>

  - 必须在反向代理或硬件负载平衡器上将已发布的端口配置为侦听端口。

  - 对于前端池 (在示例中未显示), 内部 SIP 池 FQDN 必须与内部 web 服务 FQDN 不同, 因为 web 流量通过硬件负载平衡器, 并且内部 SIP 池流量通过 DNS 负载平衡器进行传输. 必须满足此要求。

  - Lync Server 标准版部署不需要或允许覆盖内部 web 服务 FQDN, 因为此服务器无法进行负载平衡。

  - 如果你的环境中有一个硬件负载平衡器, 用于内部 SIP 和 web 流量, 拓扑生成器将无法进行区分。
    
    Web 服务 Fqdn 应该易于区分;这有助于确保 URL 重定向将客户定向到相应的服务器。 例如, 如果您有两个 Fqdn, 则可以考虑为一个 meeting.contoso.com 和另一个 conferencing.contoso.com 命名。 如果你的 Fqdn 具有更相似的名称, 例如 meet1.contoso.com 和 meet2.contoso.com, 则可能会遇到重定向问题。

外部 web 服务与外围网络中的反向代理协同工作。 它通过使用这些 web 服务向客户提供对外部访问的访问权限。 此处配置的 Fqdn 将在客户端登录时发送到客户端, 并用于在远程连接时将 HTTPS 连接回反向代理。 反向代理服务器将外部 web 服务 FQDN 转发到内部硬件负载平衡器, 或直接转发到池。 反向代理必须能够将外部 web 服务 FQDN 解析为内部 Web 服务器的 IP 地址。 外部 web 服务 FDQN 必须可在公共 Internet 中解析。

如果内部服务器是标准版服务器, 则内部 FQDN 是标准版服务器 FQDN。 如果内部服务器是一个前端池, 则 FQDN 是一个硬件负载平衡器虚拟 IP (VIP), 用于加载内部 web 场服务器的平衡。 在具有多个企业版服务器的前端池中需要硬件负载平衡器。 标准版服务器或单个企业版前端服务器不需要负载平衡器。

</div>

</div>

<span> </span>

</div>

</div>

</div>

