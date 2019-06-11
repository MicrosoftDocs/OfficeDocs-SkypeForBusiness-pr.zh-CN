---
title: Lync Server 2013：配置 DNS 负载平衡
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS for load balancing
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48183540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e370d3b66e82b02bd5668fc1c9cab4ee41da759
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a>在 Lync Server 2013 中配置 DNS 负载平衡

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-01_

若要成功完成此过程, 你应至少作为域管理员组的成员或 DnsAdmins 组的成员登录到服务器或域。

域名系统 (DNS) 负载平衡平衡 Lync Server 2013 (如 SIP 流量和媒体流量) 独有的网络流量。 对于前端池、边缘池、控制器池和独立的中介池, DNS 负载平衡受支持。 配置为使用 DNS 负载平衡的池必须具有两个完全限定的域名 (Fqdn): 由 DNS 负载平衡 (例如 pool1.contoso.com) 使用的常规池 FQDN 和解析为池中服务器的物理 Ip 的常规池 FQDN以及池的 Web 服务 (例如, web1.contoso.net) 的另一个 FQDN, 它解析为池的虚拟 IP 地址。 有关 DNS 负载平衡的详细信息, 请参阅规划文档中[Lync Server 2013 中的 "DNS 负载平衡](lync-server-2013-dns-load-balancing.md)"。

<div>


> [!NOTE]  
> 客户端到服务器 HTTPS 流量仍需要硬件负载平衡。



</div>

在可以使用 DNS 负载平衡之前, 必须执行以下操作:

1.  替代内部 Web 服务池 FQDN。
    
    <div>
    

    > [!WARNING]  
    > 如果决定使用自定义的 FQDN 替代内部 web 服务, 则每个 FQDN 都必须与任何其他前端池、Director 或控制器池唯一。

    
    </div>

2.  创建 DNS A 主机记录以将池 FQDN 解析为池中所有服务器的 IP 地址。

3.  启用 IP 地址随机化, 或者对于 Windows Server DNS, 启用循环复用。
    
    <div>
    

    > [!NOTE]  
    > 默认情况下, 应启用循环复用。

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a>替代内部 Web 服务 FQDN

1.  启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。

2.  从控制台树中, 展开 "企业版前端池" 节点。

3.  右键单击该池, 单击 "**编辑属性**", 然后单击 " **Web 服务**"。

4.  在 "**内部 web 服务**" 下, 选中 "**替代 FQDN** " 复选框。

5.  键入将解析为池中服务器的物理 IP 地址的池 FQDN。

6.  在 "**外部 web 服务**" 下, 键入解析为池的虚拟 IP 地址的外部池 FQDN, 然后单击 **"确定"**。

7.  在控制台树中, 单击 " **Lync Server 2013**", 然后在 "**操作**" 窗格中, 单击 "**发布拓扑**"。

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a>为所有内部池服务器创建 DNS 主机 (A) 记录

1.  单击 "**开始**", 单击 "**所有程序**", 单击 "**管理工具**", 然后单击 " **DNS**"。

2.  在 " **DNS 管理器**" 中, 单击管理记录的 DNS 服务器以将其展开。

3.  单击 "**正向查找区域**" 将其展开。

4.  右键单击需要添加记录的 DNS 域, 然后单击 "**新建主机 (A 或 AAAA)**"。

5.  在 "**名称**" 框中, 键入主机记录的名称 (将自动追加域名)。

6.  在 "IP 地址" 框中, 键入单个前端服务器的 IP 地址, 然后选择 "**创建关联的指针 (PTR) 记录**", 或者**允许任何经过身份验证的用户使用同一所有者名称更新 DNS 记录**(如果适用)。

7.  继续为将参与 DNS 负载平衡的所有成员前端服务器创建记录。
    
    例如, 如果你有一个名为 pool1.contoso.com 和三个前端服务器的池, 你将创建以下 DNS 条目:
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>FQDN</th>
    <th>类型</th>
    <th>数据</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>主机 (A)</p></td>
    <td><p>192.168.1.1</p></td>
    </tr>
    <tr class="even">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>主机 (A)</p></td>
    <td><p>192.168.1.2</p></td>
    </tr>
    <tr class="odd">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>主机 (A)</p></td>
    <td><p>192.168.1.3</p></td>
    </tr>
    </tbody>
    </table>
    
    有关创建 DNS 主机 (A) 记录的详细信息, 请参阅[配置 Lync Server 2013 的 DNS 主机记录](lync-server-2013-configure-dns-host-records.md)。

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a>为 Windows Server 启用循环复用

1.  单击 "**开始**", 单击 "**所有程序**", 单击 "**管理工具**", 然后单击 " **DNS**"。

2.  展开 " **DNS**", 右键单击要配置的 DNS 服务器, 然后单击 "**属性**"。

3.  单击 "**高级**" 选项卡, 选择 "**启用循环**" 和 "**启用网络掩码排序**", 然后单击 **"确定"**。
    
    !["DNS 循环复用" 对话框](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "\"DNS 循环复用\" 对话框")

<div>


> [!NOTE]  
> 默认情况下, 应启用此功能。



</div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的 DNS 负载平衡](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

