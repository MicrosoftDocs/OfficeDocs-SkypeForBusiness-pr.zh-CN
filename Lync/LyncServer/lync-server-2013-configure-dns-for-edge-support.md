---
title: Lync Server 2013：配置边缘支持的 DNS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS for edge support
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398756(v=OCS.15)
ms:contentKeyID: 48184894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79e1712b3425c7cce4020799b37f10aba894aeb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a>在 Lync Server 2013 中配置边缘支持的 DNS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-15_

你必须为内部和外部边缘接口配置域名系统 (DNS) 记录, 包括 Edge 服务器和反向代理接口。 默认情况下, Edge 服务器未加入域且不具有完全限定的域名 (完全限定的域名)。 边缘服务器仅由短 (计算机) 名称 (而不是完全限定的域名) 引用。 但是, 拓扑生成器使用 Fqdn 而不是短名称。 边缘服务器的名称必须与拓扑生成器使用的 FQDN 相匹配。 若要执行此操作, 请定义一个 DNS 后缀, 当与计算机名称组合时, 将生成预期的 FQDN。 在 "将 DNS 后缀添加到计算机名称" 和 "边缘服务器未加入域" 中, 使用以下过程将 DNS 后缀添加到计算机名称。

<div>


> [!NOTE]  
> 默认情况下, DNS 使用循环复用算法来旋转查询答案中返回的资源记录数据的顺序, 其中同一类型的多个资源记录对于所查询的 DNS 域名存在。 Lync Server 2013 的 DNS 负载平衡依赖于 DNS 负载平衡机制部分的 DNS 循环。 验证是否已禁用 "循环调度" 设置。 如果您使用的 DNS 服务器未运行 Windows 操作系统, 请验证是否启用了循环资源记录排序。



</div>

在 "**创建 DNS srv 记录**" 中使用以下过程来创建和验证每个 dns srv 记录。 使用 "**创建 DNS a 记录**" 中的过程定义外部用户访问所需的 DNS a 记录。 若要确认记录已配置并正常运行, 请参阅本主题中的 "**验证 DNS 记录**"。 有关支持外部用户访问所需的每条记录的详细信息, 请参阅[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)。

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a>向未加入域的边缘服务器上的计算机名称添加 DNS 后缀

1.  在计算机上, 单击 "**开始**", 右键单击 "**计算机**", 然后单击 "**属性**"。

2.  在 "**计算机名称、域和工作组设置**" 下, 单击 "**更改设置**"。

3.  在 "**计算机名称**" 选项卡上, 单击 "**更改**"。

4.  在 "**计算机名称/域更改**" 中, 单击 "**更多**"。

5.  在 " **DNS 后缀" 和 "NetBIOS 计算机名称**"**的 "此计算机的主 DNS 后缀**" 中, 键入内部域的名称 (例如, corp.contoso.com), 然后单击 **"确定"** 三次。

6.  重新启动计算机。

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a>创建 DNS SRV 记录

1.  在相应的 DNS 服务器上, 依次单击 "**开始**"、"**控制面板**"、"**管理工具**" 和 " **DNS**"。
    
    <div>
    

    > [!IMPORTANT]  
    > 您需要为远程用户和联盟伙伴配置 DNS, 以便有: 1 个外部 dns 查找的外部 DNS 条目;2) 由外围网络 (也称为 DMZ、隔离区域和屏蔽子网) 中的边缘服务器使用的条目, 包括运行 Lync Server 2013 的内部服务器的记录;和 3) 运行 Lync Server 2013 的内部客户端和服务器查找的内部 DNS 条目。

    
    </div>

2.  在 SIP 域的控制台树中, 展开 "**正向查找区域**", 然后右键单击安装了 Lync Server 2013 的域。

3.  单击 "**其他新记录**"。

4.  在 "**选择资源记录类型**" 中, 键入 "**服务位置 (SRV)**", 然后单击 "**创建记录**"。

5.  提供 DNS SRV 记录所需的所有信息。

</div>

<div>

## <a name="to-create-a-dns-a-record"></a>创建 DNS A 记录

1.  在 DNS 服务器上, 单击 "**开始**", 单击 **"控制面板**", 单击 "**管理工具**", 然后单击 " **DNS**"。

2.  在 SIP 域的控制台树中, 展开 "**正向查找区域**", 然后右键单击安装了 Lync Server 2013 的域。

3.  单击 "**新建主机 (A)**"。

4.  提供 DNS SRV 记录所需的所有信息。

</div>

<div>

## <a name="to-verify-a-dns-record"></a>验证 DNS 记录

1.  登录到域中的客户端计算机。

2.  单击 **“开始”**，然后单击 **“运行”**。

3.  在命令提示符处, 运行以下命令:
    
        nslookup <FQDN edge interface>

4.  验证您是否收到了解析为 FQDN 的相应 IP 地址的答复。

</div>

<div>

## <a name="see-also"></a>另请参阅


[为与托管 Exchange UM 的集成创建 DNS SRV 记录](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

